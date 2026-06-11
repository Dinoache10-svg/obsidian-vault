# 🧾 {{DANCING}}

## 📌 Información General

- **Máquina:**  {{DANCING}}
    
- **IP:** 10.129.37.134
    
- **Dificultad:** Very Easy
    
- **Fecha:** 09/06/2026
    
- **Estado:**   🟢 Completada
     

---

## 🎯 Objetivo

-  **User:** 5f61c10dffbc77a704d76016a22f1664

-  **Root:** - ❌ No aplica (máquina sin escalada real / nivel enumeración SMB)
    

---

## 🧠 Hipótesis Inicial

 **¿Qué creo que voy a encontrar?**
- Creo que la maquina es Windows debido a la presencia de SMB (puerto 445 típico de entornos Windows).
- posible mala configuración de SMB.
- acceso anónimo habilitado.
- Shares mal protegidos o numerables.
- permisos débiles en recursos compartidos.
 
 **¿Qué haría un atacante?**
 - Enumerar SMB sin credenciales.
 - Buscar shares accesibles (guest / anonymous).
 - Extraer archivos sensibles y credenciales.

---

## 🌐 Enumeración
- 
### 🔎 Nmap
Escanear puertos
```bash
nmap -sC -sV -Pn <10.129.37.134>
```

### 📊 Resultado
  - 135/TCP / msrpc (Microsoft RPC).
  - 139/TCP / netbios-ssn.
  - 445/TCP / SMB (Microsoft-ds).
  - 5985/TCP / WinRM (HTTPAPI 2.0).
---
### 🧠 Análisis
### 🔹 SMB (445)
- Vector principal de enumeración inicial.
- Acceso a shares. 
- Enumeración de usuarios.  
- Posible anonymous login.  
  
### 🔹 NetBIOS / RPC (139 / 135)  
- Soporte a enumeración de usuarios.  
- Servicios legacy Windows.  
  
### 🔹 WinRM (5985)  
- 🔥 MUY IMPORTANTE  
- Posible acceso remoto si hay credenciales válidas.
- Posible vector de movimiento lateral o acceso remoto.
---

## 🚪 Servicios

### 🔹 Servicio: SMB (principal)

#### 🔍 Objetivo
 - Identificar shares accesibles, permisos y posibles vectores de acceso anónimo.
 ---
#### 💻 Comandos
- Listar Shares:
```shell 
smbclient -L //10.129.37.134 -N
```
- Enumeración completa:
```shell
enum4linux -a 10.129.37.134
```
- Validar acceso manual a share:
```shell
smbclient //10.129.37.134/<share> -N
```
---
#### **📊 Output**
- ADMIN$ / Share administrativo (requiere privilegios).
- C$ / Disco raíz del sistema (requiere privilegios).
- IPC$ / Canal de comunicación interprocesos.
- WorkShares / 🔥Share potencialmente interesante.
#### **🧠 Insight**
 **Durante la enumeración SMB se busca:**
 -  Usuarios del sistema (nombres validos para brute force o reutilización).
 - Archivos sensibles.
 - Backups.
 - .txt / .config / .ini
 - Credenciales en texto plano.
 - Shares mal configurados.
 - Acceso anónimo (guest).
 - Permisos de escritura.
 - Posible rutas de escalada inicial (scripts, logs, configs).
 **Si un share tiene permisos de escritura (write = yes), implica:**
 - Posible subida de archivos maliciosos.
 - Ejecución remota indirecta (dependiendo del servicio).
 - Modificación de scripts o configs usados por el sistema.
 - Vector potencial para RCE o persistencia.
### 🌐 Enumeración
 - Los shares administrativos (ADMIN$ y C$) están presentes pero no accesibles / sistema. correctamente protegido a nivel administrativo.
 - IPC$ responde, pero no permite enumeración de usuarios ni dominio / restricciones activas.
 - WorkShares es el único share no estándar / posible vector de interés.
 **Conclusion:**
  - No hay enumeración de usuarios vía SMB.
  - No hay acceso anónimo profundo al sistema.
  - El punto de ataque se desplaza a WorkShares.
---

## ⚔️ Explotación
### 🎯 Vector principal identificado

El único share no administrativo es:
- WorkShares.
Esto indica:
- Posible share creado por usuarios.
- Posible almacenamiento de archivos compartidos.
- Potencial exposición. 
- credenciales.
- backups.
- documentos internos.
---
### **LOS 3 ARCHIVOS MAS CRITICOS EN WORKSHARES**
**Archivo de Credenciales / Texto Plano**
 - .txt
 - .ini
 - .config
 - .xml
  
  **Backups / Comprimido**
   - .zip
   - .rar
   - .bak
   - .old

**Scripts / Automatizacion**
 - .PS1 (PowerShell).
 - .bat
 - .sh
 
## 🧠 ¿Por qué funciona?
  **Archivo de Credenciales / Texto Plano**
   - Suelen contener usuarios y contraseñas directamente.
   - Error humano típico.
  
  **Backups / Comprimido**
 - Contienen versiones antiguas.
 - Configs olvidadas.
 - Base de datos o dumps.
 Muchas veces dentro hay: 
  - Passwords.
  - Keys.
  - Scripts.
  
  **Scripts / Automatización**
   - Suelen tener credenciales hardcodeadas.
   - Rutas internas.
   - Comandos administrativos.
## 🚪 Acceso a WorkShares

### 💻 Comando
Acceso al Share
```bash
smbclient //10.129.37.134/WorkShares -N
```
Listar Archivos ```
```shell
cd James.P
```
Entrar al directorio
```shell
ls
```

### 📊 Resultado
 - Acceso concedido sin autenticación.
 - Sesión SMB abierta como usuario anónimo.
### 🧠 Insight
 El share WorkShares permite acceso sin credenciales, lo que indica:
  - Exposición de información interna.
  - Posible filtración de credenciales.
  - Vector directo para compromiso inicial.
### 🧠 Análisis del contenido del share

**Se identifican dos directorios:**
- Amy.J
- James.P

**Esto indica**:
- Probables usuarios del sistema
- Estructura típica de perfiles de usuario en Windows
- Posible almacenamiento de archivos personales o credenciales
👉 Esto ya esta dando usuarios validos del sistema.
## 🚪 Enumeración SMB - WorkShares

### 📂 Estructura encontrada
 - Amy.J/
 - worknotes.txt
 - James.P/
 - flag.txt
### 🧠 Insight
El share contiene dos directorios que parecen corresponder a usuarios del sistema:
- Amy.J → posible usuario con información operativa.
- James.P → posible usuario con flag o datos sensibles.
## 🧠 Insight de Seguridad
**Se observa:**
- Estructura de usuarios expuesta públicamente.
- Separación por directorios personales.
- Archivos sensibles accesibles sin autenticación.
**Esto implica:**
- Fuga de información interna.
- Enumeración directa de usuarios del sistema.
-  Posible credencial reutilizable o flag expuesta.
## 🧠 Worknotes - Análisis
**Contenido encontrado:**
- start apache server on the linux machine.
- secure the ftp server.
- setup winrm on dancing.
## 🧠 Insight de seguridad
**El archivo revela información de administración interna:**
- Existe infraestructura mixta (Linux + Windows).
- Se menciona FTP (posible vector histórico o activo).
- WinRM está configurado en la máquina "Dancing."
- Esto confirma que el siguiente vector de ataque es WinRM (5985).
## 🧠 Estado de la máquina

### ✔ SMB
- Acceso anónimo disponible.
- Shares enumerados.
- Directorios de usuarios identificados.
- Archivos revisados (sin credenciales).
### ❌ Resultado
- No hay credenciales explotables en SMB.
- SMB ya cumplió su función: **recolección de información, no explotación final**.
## 🧠 Pivot real de ataque
**El archivo confirma que:**
- WinRM está configurado (5985 ya visto en Nmap).
- El acceso remoto está previsto como vía de administración.
- Por lo tanto, el siguiente paso lógico NO es SMB.
-  Es validación de credenciales para WinRM.
## 🧠 Pivot real
**La credencial NO está en WinRM ni SMB directamente.**
Está en uno de estos sistemas auxiliares:
- FTP (muy probable)
- Apache (posible web leak)
## 👑 Escalada de privilegios

---

## 🏁 Flags
5f61c10dffbc77a704d76016a22f1664
- User: 
    
- Root:
    

---

## 🛡️ SOC / Blue Team

### 🚨 Detección

 Logs: 

 Alertas:
 

### 🔐 Prevención

---

## 🔗 Kill Chain



---

## 🧠 Lecciones

---