# HTTP

## 📌 Qué es (Feynman simple)
HTTP es el protocolo que permite que navegadores y servidores web se comuniquen.

👉 Es como enviar cartas en papel sin sobre: cualquiera puede leerlas.

---

## 🧠 Concepto técnico
- Protocolo de comunicación web
- Cliente (navegador) ↔ servidor
- Basado en texto plano (sin cifrado en HTTP)

---

## ⚙️ Cómo funciona
- El navegador envía una petición (request)
- El servidor responde (response)
- Todo viaja en texto legible si no hay HTTPS

---

## ⚠️ Riesgos
- Robo de credenciales en formularios
- Intercepción de sesiones
- Manipulación de tráfico web
- Ataques MITM

---

## 🔎 Uso en ciberseguridad
- Análisis de tráfico web
- Interceptación de credenciales
- Enumeración de endpoints
- Detección de vulnerabilidades web

---

## 🧪 Ejemplos de ataque
- Captura de cookies de sesión
- Robo de formularios login
- Inyección en tráfico no cifrado
- Redirecciones maliciosas

---

## 🛠️ Herramientas
- Burp Suite
- Wireshark
- curl
- browser dev tools

---

## 💣 Ataques relacionados
- [[Sniffing]]
- [[Nmap]]
- [[Enumeration]]
- [[DNS]]
---

## 🐚 Impacto (qué permite hacer)
- Robo de credenciales web
- Secuestro de sesiones
- Análisis de tráfico HTTP
- Reconocimiento de aplicaciones

---

## 🔵 Detección Blue Team
- [[Network monitoring]]
- [[SIEM alerts]]

👉 Indicadores:
- tráfico HTTP sin cifrar
- login sin HTTPS
- cookies expuestas

---

## 🧯 Respuesta / Mitigación
- Migrar a HTTPS
- Forzar TLS
- HSTS activado
- Monitorización de tráfico web

---

## 🛠️ Tools MOC
- [[Tools MOC]]

---

## 🔗 Relacionado
- [[FTP]]
- [[Telnet]]
- [[Sniffing]]
- [[DNS]]  
- [[SSH]]
---

## 🧭 MOCs relacionados
- [[Network Security MOC]]
- [[Network MOC]]
- [[Blue Team MOC]]
- [[Tools MOC]]