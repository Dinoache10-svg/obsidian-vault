# Telnet

## 📌 Qué es
Protocolo de acceso remoto sin cifrado que transmite todo en texto plano.

---

## ⚠️ Riesgos
- Credenciales visibles en red
- Interceptación (sniffing)
- Obsoleto e inseguro

---

## 🧠 Uso en pentesting
- Detectar servicios abiertos en puerto 23
- Probar credenciales débiles
- Enumeración de servicios legacy

---

## 🔎 Cosas a probar
- Escaneo con Nmap (puerto 23)
- Conexión al servicio
- Intento de login
- Identificación de banner

---

## 🛠️ Comandos útiles

### 🔎 Nmap
- `nmap -sV -sC -p 23 <10.129.35.191>`

---

### 📡 Telnet
- `telnet <10.129.35.191>`

---

### 💬 Sesión Telnet
- `open <10.129.35.191>`
- `quit`