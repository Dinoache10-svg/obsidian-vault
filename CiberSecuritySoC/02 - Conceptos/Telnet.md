# Telnet

## 📌 Qué es (Feynman simple)
Telnet es como hablar con un servidor a través de una conexión remota donde TODO lo que dices viaja en texto plano, sin ningún tipo de cifrado.

👉 Es como enviar contraseñas en una postal abierta.

---
## 🧠 Concepto técnico
- Protocolo de acceso remoto
- Funciona en texto plano
- Usa el puerto 23
- Obsoleto e inseguro

---
## ⚙️ Cómo funciona
- Cliente se conecta al servidor
- Comunicación directa sin cifrado
- Todo el tráfico puede ser interceptado

---
## ⚠️ Riesgos
- Credenciales visibles en red
- Intercepción de tráfico (sniffing)
- Acceso no autorizado
- Protocolos legacy inseguros

---
## 🔎 Enumeración
- Escaneo con Nmap al puerto 23
- Identificación de servicio Telnet
- Revisión de banners
- Intento de conexión manual

---
## 🧪 Uso en pentesting
- Detección de servicios abiertos
- Prueba de credenciales débiles
- Acceso a sistemas legacy
- Enumeración de usuarios

---
## 🛠️ Comandos

### 🔎 Nmap
```bash
nmap -sV -sC -p 23 <10.129.35.191>
```
---
## 💣 Ataques relacionados
- [[Sniffing]]
- [[Nmap]]
- [[Enumeration]]

---
## 🐚 Shell / Acceso
- Posible acceso remoto si hay credenciales débiles
- Ejecución de comandos en sistemas legacy
- Punto inicial para movimiento lateral

---
## 🔵 Detección Blue Team
- [[Logs Telnet]]
- [[Network monitoring]]
- [[SIEM alerts]]

👉 Indicadores:

- intentos repetidos de login
- tráfico en puerto 23
- credenciales en texto plano

---
## 🧯 Respuesta / Mitigación
- Deshabilitar Telnet
- Sustituir por SSH
- Bloquear puerto 23
- Monitorizar tráfico en claro

---
## 🛠️ Tools MOC
- [[Tools MOC]]

---
## 🔗 Relacionado
- [[FTP]]
- [[HTTP]]
- [[DNS]]
- [[Nmap]]
- [[SSH]]
---
## 🧭 MOCs relacionados
- [[Network Security MOC]]
- [[Network MOC]]
- [[Blue Team MOC]]
- [[Tools MOC]]