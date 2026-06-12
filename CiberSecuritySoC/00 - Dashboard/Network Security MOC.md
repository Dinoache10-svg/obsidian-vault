# 🌐 Network Security MOC

---

## 🟢 Servicios (Superficie de ataque)
- [[FTP]]
- [[Telnet]]
- [[SSH]]
- [[HTTP]]
- [[HTTPS]]
- [[DNS]]
- [[Nmap]]
- [[Sniffing]]
---

## 🔴 Capa de ataque (Offensive)
- [[Nmap]]
- [[Sniffing]]
- [[Enumeration]]
- [[FTP]]
- [[Telnet]]
- [[HTTP]]
- [[DNS]]
---

## 🔵 Capa Blue Team (Defensa y detección)
- [[Network monitoring]]
- [[SIEM alerts]]
- [[Logs FTP]]
- [[Logs Telnet]]
- [[Logs HTTP]]
- [[DNS logs]]
- [[FTP]]
- [[Telnet]]
- [[HTTP]]
- [[DNS]]
---

## 🟡 Protocolos seguros vs inseguros
- [[FTP]] ↔ [[SFTP]]
- [[Telnet]] ↔ [[SSH]]
- [[HTTP]] ↔ [[HTTPS]]

---

## 🟣 Flujo de ataque (mental model SOC)
- [[Nmap]] → descubrimiento
- [[Enumeration]] → análisis
- [[Sniffing]] → interceptación
- acceso → [[FTP]] / [[Telnet]]
- web attack → [[HTTP]]
- resolución → [[DNS]]

---

## 🧪 Casos SOC (práctica)
- FTP credential leak
- Telnet brute force
- HTTP sniffing case
- DNS exfiltration case

---

## 🛠️ Herramientas clave
- [[Nmap]]
- [[Wireshark]]
- [[tcpdump]]
- [[Burp Suite]]
- [[Hydra]]

---
## 🧠 Conceptos clave Blue Team
- [[Logs]]
- [[Alerting]]
- [[Detection rules]]
- [[False positives]]

---
## 🧭 MOCs relacionados
- [[Network MOC]]
- [[Blue Team MOC]]
- [[Tools MOC]]