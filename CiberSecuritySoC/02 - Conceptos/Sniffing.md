# Sniffing

## 📌 Qué es (Feynman simple)
Sniffing es la técnica de interceptar y analizar el tráfico de red que viaja entre dispositivos.

👉 Es como “escuchar conversaciones” dentro de una red.

---

## 🧠 Concepto técnico
- Captura de paquetes en red
- Analiza tráfico en tiempo real o guardado
- Puede ser pasivo o activo
- Se usa con herramientas de captura de red

---

## ⚙️ Cómo funciona
- Los datos viajan en paquetes
- Un atacante intercepta esos paquetes
- Si el tráfico NO está cifrado → se puede leer todo

---

## ⚠️ Riesgos
- Robo de credenciales en texto plano
- Intercepción de sesiones
- Exposición de datos sensibles
- Ataques MITM (Man-in-the-Middle)

---

## 🔎 Uso en pentesting
- Captura de credenciales FTP / Telnet
- Análisis de tráfico HTTP sin HTTPS
- Reconocimiento de servicios
- Detección de protocolos inseguros

---
## 🛠️ Herramientas
- Wireshark
- tcpdump
- tshark
- bettercap

---
## 💣 Ataques relacionados
- [[FTP]]
- [[Telnet]]
- [[HTTP]]

---
## 🐚 Impacto (qué permite hacer)
- Robo de usuarios y contraseñas
- Secuestro de sesiones
- Análisis de redes internas
- Descubrimiento de servicios vulnerables

---
## 🔵 Detección Blue Team
- [[Network monitoring]]
- [[SIEM alerts]]
- IDS/IPS alerts

👉 Indicadores:
- tráfico sospechoso en red local
- ARP spoofing
- múltiples conexiones no normales

---
## 🧯 Respuesta / Mitigación
- Usar cifrado (HTTPS, SSH)
- Segmentación de red
- IDS/IPS activo
- Detección de ARP spoofing
- Monitorización constante

---
## 🛠️ Tools MOC
- [[Tools MOC]]

---
## 🔗 Relacionado
- [[Nmap]]
- [[DNS]]
- [[HTTP]]
- [[FTP]]
- [[Telnet]]

---
## 🧭 MOCs relacionados
- [[Network Security MOC]]
- [[Network MOC]]
- [[Blue Team MOC]]
- [[Tools MOC]]