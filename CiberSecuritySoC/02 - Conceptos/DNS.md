# DNS

## 📌 Qué es (Feynman simple)
DNS es el sistema que traduce nombres de dominio (como google.com) a direcciones IP.

👉 Es como la agenda de contactos de Internet.

---

## 🧠 Concepto técnico
- Sistema de resolución de nombres
- Convierte dominios en direcciones IP
- Funciona en puerto 53 (UDP/TCP)

---

## ⚙️ Cómo funciona
- El cliente pregunta: “¿qué IP tiene este dominio?”
- El servidor DNS responde con la IP
- Se pueden usar varios servidores en cadena

---

## ⚠️ Riesgos
- DNS spoofing
- DNS poisoning
- Exfiltración de datos
- Resolución maliciosa

---

## 🔎 Uso en ciberseguridad
- Enumeración de dominios
- Descubrimiento de subdominios
- Reconocimiento de infraestructura
- Detección de tráfico sospechoso

---

## 🧪 Ejemplos de ataque
- Redirección a páginas falsas
- Captura de tráfico mediante DNS falso
- Exfiltración de datos vía DNS

---

## 🛠️ Herramientas
- nslookup
- dig
- dnsenum
- amass

---

## 💣 Ataques relacionados
- [[Sniffing]]
- [[Enumeration]]
- [[Nmap]]

---

## 🐚 Impacto
- Redirección de tráfico
- Robo de información
- Control de resolución de dominios
- Persistencia en red

---

## 🔵 Detección Blue Team
- [[Network monitoring]]
- [[SIEM alerts]]

👉 Indicadores:
- consultas DNS sospechosas
- dominios raros
- tráfico DNS elevado

---

## 🧯 Mitigación
- DNS seguro (DNSSEC)
- monitorización de consultas
- filtrado DNS
- uso de resolvers confiables

---

## 🛠️ Tools MOC
- [[Tools MOC]]

---

## 🔗 Relacionado
- [[HTTP]]
- [[FTP]]  
- [[Telnet]]  
- [[SSH]]
- [[Sniffing]]
- [[Nmap]]

---

## 🧭 MOCs relacionados
- [[Network Security MOC]]
- [[Network MOC]]
- [[Blue Team MOC]]
- [[Tools MOC]]