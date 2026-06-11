# 🧾 Fawn

## 📌 Información General

- **Máquina:** Fawn
    
- **IP:** 10.129.1.14
    
- **Dificultad:** Very Easy
    
- **Fecha:** 08/06/2026
    
- **Estado:**  🟢 Completada
    

---

## 🎯 Objetivo

-  **User:** Obtener acceso inicial al sistema mediante servicios expuestos.
    
-  **Root:** Comprometer el sistema y obtener privilegios máximos.
    

---

## 🧠 Hipótesis Inicial

- **¿Qué creo que voy a encontrar?**
    - Maquina muy fácil, probablemente servicio mal configurado.
    - Posible acceso sin autentificación.
    - Servicio típico: FTP, HTTP,O SMB.
    - Buscar credenciales por defecto o acceso anónimo.
- **¿Qué haría un atacante?**
    - Escanear puertos abiertos.
    - Identificar servicios inseguros.
    - Intentar login anónimo o credenciales por defecto.

---

## 🌐 Enumeración

### 🔎 Nmap

```bash
nmap -sC -sV -Pn <10.129.1.14>
```

### 📊 Resultado
**PORT       STATE      SERVICE      VERSION**
21/tcp      open           ftp           vsftpd 3.0.3
### 🧠 Análisis
- FTP abierto, posible transferencia de datos.
- VSFTPD, servicio común, pocas vulnerabilidades conocidas en esta versión.
- Probar acceso anónimo (anonymous login).
**¿Por qué FTP es un servicio interesante para un atacante?**
 - Por que le da acceso directo a los archivos del sistema.
---

## 🚪 Servicios

### 🔹 Servicio: 
- FTP
#### **🔍 Objetivo** 
- Comprobar acceso con login anónimo.
- Enumerar archivos accesibles.
#### **💻 Comandos**
```bash
ftp 10.129.1.14
```
- User: anonymous / root / admin 

- Password: anonymous (si la pide) 
#### **📊 Output**
- Mediante el puerto 21 FTP hemos logrado entrar al servidor.
- 230 Login successful. Remote system type is UNIX. Using binary mode to transfer files.
#### **🧠 Insight**
- El servidor permite acceso anónimo / mala configuración.
- Exposición de archivos sin autenticación.
- posible filtración de credenciales flags.
---

## ⚔️ Explotación
- N o hay explotación, el fallo es la mala configuración.  
## 🧠 ¿Por qué funciona?
- El servidor FTP permite autenticación anónima.
- No hay control de acceso.
- Archivos sensibles expuestos públicamente. 
**¿Esto es una vulnerabilidad o una mala configuración?** 
 - Esto no es una vulnerabilidad del software, es una mala configuracion de permisos.
---

## 👑 Escalada de privilegios
- No se requiere escalada.
- Acceso directo a flag.
- Impacto directo por mala configuracion.
---

## 🏁 Flags

- **User:** 035db21c881520061c53e0536e44f815
    
- **Root:** NO se ha requerido escalada 
    

---

## 🛡️ SOC / Blue Team

### 🚨 Detección

- **Logs**:
    - Logs FTP (/var/log/vsftpd.log). 
- **Alertas:**
    - - Conexiones anónimas.
    -  Transferencias sospechosas.

### 🔐 Prevención
- Deshabilitar acceso anonimo.
- Usar atenticacionfuerte.
- Restringir acceso IP.
- Monitorizar logs.
---

## 🔗 Kill Chain

- Recon → FTP → Anonymous login → Acceso → Exfiltración de flag

---

## 🧠 Lecciones
- Las maquinas faciles enseñan malas configuracionesreales.
- FTP sigue siendo vector comun.
- Enumeracion basica = clave.
---