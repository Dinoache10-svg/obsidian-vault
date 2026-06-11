# Nmap

## 📌 Qué es (Feynman simple)
Nmap es una herramienta que permite descubrir dispositivos, puertos abiertos y servicios en una red.

👉 Es como un radar que escanea sistemas.

---

## 🧠 Concepto técnico
- Escáner de red
- Detecta hosts activos
- Identifica puertos y servicios
- Puede ejecutar scripts (NSE)

---

## ⚙️ Cómo funciona
- Envía paquetes a un objetivo
- Analiza las respuestas
- Determina estado de puertos (open, closed, filtered)

---

## ⚠️ Riesgos
- Reconocimiento por atacantes
- Detección de servicios vulnerables
- Mapeo de red interna

---

## 🔎 Uso en ciberseguridad
- Descubrimiento de hosts
- Enumeración de servicios
- Identificación de versiones
- Auditoría de red

---

## 🧪 Ejemplos de uso
- Escaneo rápido
- Detección de servicios
- Scripts NSE
- Identificación de sistemas

---

## 🛠️ Comandos

### Escaneo básico
```bash
nmap <IP>
```
### Deteccion de servicios
```bash
nmap -sC -sV -p- <IP>
```
### Escaneo completo
```bash
nmap -sC -sV -p- <IP>
```

---
## 💣 Ataques relacionados
- [[Enumeration]]  
- [[FTP]]  
- [[Telnet]]  
- [[HTTP]]  
- [[DNS]]


---

## 🐚 Impacto

- Descubrimiento de infraestructura
- Identificación de servicios vulnerables
- Preparación de ataques

---

## 🔵 Detección Blue Team

- [[Network monitoring]]
- [[SIEM alerts]]

👉 Indicadores:

- múltiples escaneos de puertos
- tráfico anómalo
- patrones repetitivos

---

## 🧯 Mitigación

- IDS/IPS
- firewall
- rate limiting
- detección de escaneos

---

## 🛠️ Tools MOC

- [[Tools MOC]]

---

## 🔗 Relacionado

- [[FTP]]
- [[Telnet]]
- [[HTTP]]
- [[DNS]]

---

## 🧭 MOCs relacionados

- [[Network Security MOC]]
- [[Network MOC]]
- [[Blue Team MOC]]
- [[Tools MOC]]