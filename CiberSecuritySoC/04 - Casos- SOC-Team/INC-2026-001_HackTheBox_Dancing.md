# 🛡️ Incident Report - INC-2026-001_HackTheBox_Dancing

---

## 📌 1. Información General

- **Fecha de detección:** 09/06/2026
    
- **Analista:** HackGru1010
    
- **Tipo de incidente:** Acceso no autorizado / Enumeración SMB / Exfiltración de información.
    
- **Severidad:** Baja - Media (entorno laboratorio / HTB).
    
- **Estado:** Cerrado (simulado).
    
- **Fuente de detección:** Analisis de trafico SMB + enumeracion de red (Nmap / smbclient).
    

---

## 🧭 2. Resumen Ejecutivo
 
 - Se detectó actividad de enumeración y acceso no autenticado a servicios SMB en el sistema objetivo **Dancing (HTB)**. El atacante realizó reconocimiento de puertos, identificó el servicio SMB expuesto y accedió a recursos compartidos con configuración de acceso anónimo. Posteriormente, se extrajeron archivos desde un recurso compartido sin autenticación, evidenciando una mala configuración de permisos en el servicio SMB.
---

## 🚨 3. Evento Detectado

- **Regla / Alerta:** Acceso anonimo a recurso SMB compartido.
    
- **Descripción:** Conexión SMB sin credenciales validas y descarga de archivos desde share publico.
    
- **Sistema afectado:**  10.129.37.134 (Dancing - HTB)
    
- **Usuario afectado (si aplica):** Invitado / Anonymous
    
- **IP origen:** 192.168.126.130
    
- **IP destino:** 10.129.37.134
    
- **Puerto / Servicio:** TCP 445 / SMB
    

---

## 🕒 4. Línea de Tiempo (Timeline)

|Hora|Evento|
|---|---|
|||
|||

---

## 📊 5. Logs Analizados

```
(pegar logs relevantes aquí)
```

- **Fuente del log:**
    
- ## **Eventos clave identificados:**
    - Autenticacion anonima permitida.
    - acceso a shares sin restriccion.
    - Descarga de archivos sensibles (flag).

---

## 🔍 6. Análisis Técnico

### ¿Qué pasó?
- El sistema SMB del host objetivo permitió acceso anónimo a recursos compartidos sin autenticación, lo que permitió la enumeración y extracción de archivos.
### ¿Cómo ocurrió?
 - E l atacante escaneo el sistema con Nmap.
 - Detecto puerto 445 abierto (SMB).
 - Accedió usando smbclient sin credenciales.
 - Descargo archivos del recurso compartido.
### ¿Quién atacó?
 - Atacante identificado (IP externa vía VPN HTB). Actividad consistente con un usuario realizando pruebas de penetración en entorno controlado.
---

## 🎯 7. Indicadores de Compromiso (IoC)

- **IP(s):** 192.168.126.130
    
- **Dominio(s):** 
    
- **Hash(es):**
    
- **URL(s):**
    
- **Archivo(s):** 
- flag.txt
- Archivos dentro del share WorkShares.
    

---

## 🧠 8. Tácticas y Técnicas (MITRE ATT&CK)

## **Tácticas:**
- Discovery (TA0007).
- Collection (TA0009).
- Exfiltration (TA0010).
## **Técnicas:**
- T1135 - Network Share Discovery.
- T1046 - Network Service Scanning.
- T1039 - Data from Network Shared Drive.

---

## 💥 9. Impacto

- **Sistemas afectados:** Servidor SMB (Dancing HTB).
    
- **Datos comprometidos:** Archivos del recurso compartido (incluyendo flag).
    
- **Disponibilidad:** No afectada.
    
- **Riesgo para el negocio:** Alto en entorno real (exposición de información sensible vía SMB anónimo).
    

---

## 🔐 10. Respuesta al Incidente

### Acción tomada
- Acceso identificado y documentado. No se aplican acciones en entorno HTB.
### Contención
- En entorno real: deshabilitar acceso anónimo SMB.
### Erradicación
- Eliminar permisos de guest/anonymous en shares.
### Recuperación
- Reconfigurar SMB con autenticación obligatoria.
---

## 🧪 11. Evidencias

- Capturas de enumeración SMB (smbclient)
- Listado de shares accesibles
- Descarga de archivos desde WorkShares
- Logs de Samba con sesión anónima
---

## 🛠️ 12. Recomendaciones

- Deshabilitar **SMB anonymous access**
- Implementar autenticación obligatoria en shares
- Revisar permisos de carpetas compartidas
- Monitorizar accesos SMB no autenticados
- Aplicar segmentación de red para servicios internos
---

## 🧠 13. Lecciones Aprendidas

- SMB expuesto sin hardening es un vector crítico de ataque.
- El acceso anónimo sigue siendo una mala práctica frecuente.
- La enumeración de shares es una fase clave del reconocimiento en pentesting.
- Pequeñas malas configuraciones pueden derivar en exposición total de información.
---

## 📎 14. Referencias

- Microsoft SMB Security Best Practices
- MITRE ATT&CK Framework
- Documentación Hack The Box - Dancing
- Samba Documentation (smb.conf security settings)
---