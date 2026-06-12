# FTP
# FTP

## 📌 Resumen
FTP (File Transfer Protocol) es un protocolo usado para transferir archivos entre cliente y servidor a través de una red.

---

## 🧠 Concepto / Qué es
- Protocolo de transferencia de archivos
- Cliente-servidor
- Funciona en texto plano (sin cifrado en FTP clásico)

---

## ⚙️ Cómo funciona
- Puerto 21 para control
- Puertos dinámicos para transferencia de datos
- Autenticación o acceso anónimo

---

## 🌐 Uso en ciberseguridad
- Enumeración de archivos y directorios
- Explotación de configuraciones débiles
- Descarga de información sensible
- Subida de archivos maliciosos (webshells)

---

## ⚠️ Puntos importantes
- Credenciales en texto plano
- Acceso anónimo mal configurado
- Permisos de escritura peligrosos
- Exposición de datos sensibles

---

## 🔎 Enumeración
- Escaneo con Nmap al puerto 21
- Login anónimo (anonymous)
- Enumeración de archivos
- Descarga de contenido sensible

---

## 🛠️ Herramientas
- Nmap -sV -p 21 IP
- Hydra (fuerza bruta)
- wget / curl
- FTP client
- Netcat

---

## 💣 Ataques relacionados
- [[Sniffing]]
- [[Nmap]]
- [[Enumeration]]

---

## 🐚 Shell / Acceso
- Subida de webshell si hay permisos de escritura
- Ejecución indirecta vía archivos maliciosos
- Posible pivot si se combina con otras vulnerabilidades

---

## 🔵 Detección Blue Team
- [[Logs FTP]]
- [[Network monitoring]]
- [[SIEM alerts]]
- [[Network monitoring]]
- [[SIEM alerts]]
- [[Logs FTP]]
---

## 🧯 Respuesta / Mitigación
- Deshabilitar FTP si no es necesario
- Usar SFTP en su lugar
- Desactivar acceso anónimo
- Monitorizar intentos de login fallidos

---

## 🛠️ Tools MOC
- [[Tools MOC]]

---

## 🔗 Relacionado
- [[Telnet]]
- [[Sniffing]]
- [[Nmap]]
- [[Enumeration]]
- [[DNS]]
- [[HTTP]]
- [[SSH]]

---

## 🧭 MOCs relacionados
- [[Network Security MOC]]
- [[Network MOC]]
- [[Blue Team MOC]]
- [[Tools MOC]]
