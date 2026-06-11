**🧾 {{MEOW}}**

## 📌 Información General

- **Máquina:**  {{MEOW}}
    
- **IP:** 10.129.35.191
    
- **Dificultad:** Very Easy
    
- **Fecha:** {{09/06/2026}}
    
- **Estado:** 🟢 Completada 
     

---

## 🎯 Objetivo

-  **User:** Obtener acceso inicial al sistema mediante servicio expuesto. 
    
-  **Root:** Comprometer el sistema y obtener privilegios máximos.
    

---

## 🧠 Hipótesis Inicial

 **¿Qué creo que voy a encontrar?**
- Servicio expuesto sin autentificación o con credenciales débiles.
- Posible servicio legado  (Telnet, FTP o HTTPantiguo).
- Sistema Linux con configuracion insegura.
 **¿Qué haría un atacante?**
 - Escanear puertos abiertos.
 - Identificar servicios inseguros.
 - Intentar login anonimo o credenciales por defecto.


---

## 🌐 Enumeración

### 🔎 Nmap

```bash
nmap -sC -sV -Pn <10.129.35.191>
```

### 📊 Resultado
PORT   STATE   SERVICE  VERSION
23/tcp  open    telnet     Linux telnetd    
### 🧠 Análisis
- Solo hay un servicio expuesto: Telnet (23 TCP).
- Telnet transmite datos en texto plano / Alto riesgo.
- Probable acceso directo sin credenciales o credenciales por defecto.

---

## 🚪 Servicios

### 🔹 Servicio: Telnet (23)

#### 🔍 Objetivo
 Acceso remoto al sistema.
#### 💻 Comandos
telnet <10.129.35.191>
#### 📊 Output
Meow login: root
#### 🧠 Insight
- No hay banner de protección real.
- Servicio sin Hardening.
- Superficie de ataque mínima / Maquina diseñada para acceso directo.
---

## ⚔️ Explotación
Nos conectamos por Telnet: telnet 10.129.35.191, Cuando nos solicita login: root no nos pide password directamente y si te lo pide le das a enter y password vacío y entras, acceso conseguido. root@meow:~#
## 🧠 ¿Por qué funciona?
- Telnet no cifra credenciales.
- Sistema permite login root sin password.
- Mala configuracion del servicio de acceso remoto.
---

## 👑 Escalada de privilegios
- No es necesaria. Ya estamos como root.
---

## 🏁 Flags

- **User:** b40abdfe23665f766f9c61ecba8a4c19
    
- **Root:** No se ha requerido escalada.
    

---

## 🛡️ SOC / Blue Team

### 🚨 Detección

 Logs: 
- Conexiones entrantes a Telnet (23/TCP)
- Intentos de login sin autentificacion.
 Alertas:
 - Acceso remoto a servicio legacy.
 - Login root sin credenciales.
    

### 🔐 Prevención
- Deshabilitar Telnet completamente.
- Usar SSH con claves publicas.
- Restringir acceso por firewall.
- Auditoria de servicios expuestos.
---

## 🔗 Kill Chain

Recon → Port Scan → Telnet Discovery → Login Attempt → Root Access → Full Compromise

---

## 🧠 Lecciones
- Telnet nunca debe usarse en producción.
- Servicios legacy son puntos de entrada criticos.
- La enumeracion inicial es clave (solo 1 puerto = exploit directo).
- "Muy facil" no significa "sin aprendizaje" es base de auditoria real.
---