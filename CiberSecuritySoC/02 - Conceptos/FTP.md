# FTP

## 📌 Resumen
FTP (File Transfer Protocol) es un protocolo usado para transferir archivos entre cliente y servidor a través de una red.

---

## 🧠 Concepto / Qué es
- Protocolo de transferencia de archivos
- Cliente-servidor
- Funciona en texto plano (sin cifrado en FTP clásico)

---

## ⚙️ Cómo funciona (si aplica)
FTP utiliza un modelo cliente-servidor:
- Puerto 21 para control
- Puertos dinámicos para transferencia de datos
- Permite autenticación o acceso anónimo

---

## 🌐 Uso en ciberseguridad
- Pentesting: enumeración de archivos y accesos anónimos
- Explotación de configuraciones débiles
- Descarga de archivos sensibles
- Subida de webshells si hay permisos

---

## ⚠️ Puntos importantes
- Credenciales en texto plano (FTP sin TLS)
- Acceso anónimo mal configurado
- Permisos de escritura peligrosos
- Exposición de archivos sensibles

---

## 🔎 Qué probar / Enumeración
- Escaneo con Nmap al puerto 21
- Login anónimo (anonymous)
- Enumeración de archivos
- Descarga de contenido sensible
- Prueba de subida de archivos

---

## 🛠️ Comandos

### Comando principal
```bash
ftp <>```
```

## 🧰Herramientas
- Nmap -sV -p 21 IP
- Hydra (Fuerza Bruta)
- wget/curl (descarga)

## 🧰🔗Herramientas Relacionadas
- Nmap
- Hydra
- Netcat
- Ftp Client
## Relacionado
- [[Nmap]]
- [[Enumeracion de Servicios]]
- [[Telnet]]
- [[Sniffing]]


