# FTP

## 📌 Qué es
Protocolo de transferencia de archivos entre cliente y servidor.

Se usa para subir y descargar archivos en sistemas remotos.

## ⚠️ Riesgos
- Credenciales en texto plano (si no es FTPS)
- Acceso anónimo mal configurado
- Permite subida de archivos maliciosos
- Enumeración de directorios expuesta

## 🧠 Uso en pentesting
- Comprobar acceso anónimo (anonymous login)
- Descargar archivos sensibles
- Subir webshells si hay permisos de escritura
- Enumerar contenido del servidor

## 🔎 Cosas a probar
- ftp anonymous login
- get / download files
- put (subida de archivos)
- banner grabbing con Nmap

## 🛠️ Comandos útiles
- ftp <IP>
- ls
- get archivo.txt
- put shell.php

## 🔗 Relacionado
[[Nmap]]
[[Telnet]]
[[Enumeración de servicios]]
[[Webshell]]
[[Escalada de privilegios]]