# DNS logs

## 📌 Qué es (Feynman simple)
DNS logs son registros de todas las consultas que se hacen a un servidor DNS.

👉 Es como un historial de “qué páginas ha preguntado una red”.

---

## 🧠 Concepto técnico
- Registra consultas DNS (dominios → IP)
- Incluye hora, origen y dominio consultado
- Generado por servidores DNS o resolvers

---

## ⚙️ Qué contiene un log DNS
- IP del cliente
- Dominio solicitado
- Tipo de registro (A, AAAA, TXT, MX)
- Respuesta del servidor
- Timestamp

---

## ⚠️ Qué riesgos detecta
- acceso a dominios maliciosos
- malware comunicándose con C2
- DNS tunneling
- exfiltración de datos

---

## 🔵 Uso en Blue Team (SOC)
- detección de malware
- análisis de tráfico sospechoso
- hunting de dominios raros
- investigación de incidentes

---

## 🔎 Ejemplos de eventos sospechosos
- dominios aleatorios largos (DGA)
- múltiples consultas repetidas
- consultas a dominios recién creados
- tráfico DNS excesivo

---

## 🧪 Relación con ataques
- [[DNS]]
- [[Sniffing]]
- [[HTTP]]

---

## 🛠️ Herramientas
- Wireshark
- Zeek
- SIEM (Splunk / Sentinel)
- tcpdump

---

## 🧯 Respuesta / Mitigación
- bloqueo de dominios maliciosos
- DNS filtering
- uso de resolvers seguros
- detección de tunneling

---

## 🛠️ Tools MOC
- [[Tools MOC]]

---

## 🔗 Relacionado
- [[DNS]]
- [[SIEM alerts]]
- [[Network monitoring]]

---

## 🧭 MOCs relacionados
- [[Network Security MOC]]
- [[Blue Team MOC]]
- [[Network MOC]]