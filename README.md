# phishing_case-8815
# 🛡️ Incidente: Phishing por enlace acortado – Caso 8815

**ID del Caso:** 8815  
**Fecha:** 16-06-2015  
**Origen del ejercicio:** TryHackMe – Simulación SOC  
**Clasificación:** Medium – Phishing  

---

## 🔎 Resumen

Se identificó un intento de phishing mediante un correo enviado desde una dirección sospechosa, simulando ser de Amazon. El mensaje contenía un enlace acortado `bit.ly` que redireccionaba a una IP previamente reportada como maliciosa. Un usuario hizo clic en el enlace, pero el firewall de la organización bloqueó la conexión, previniendo una posible infección.

---

## 🧪 Análisis técnico

- **Remitente del correo:** `urgents@amazon.biz`
- **Destinatario:** `h.harris@thetrydaily.thm`
- **IP interna del usuario:** `10.20.2.17`
- **Enlace recibido:** `http://bit.ly/3sHkX3da12340`
- **IP de destino del enlace:** `67.199.248.10`

### Resultados de análisis:
- **VirusTotal:** 2 motores antivirus identifican el enlace/IP como maliciosos.
- **AbuseIPDB:** IP `67.199.248.10` reportada múltiples veces como maliciosa.
- **SIEM/FW:** El intento de conexión fue detectado y bloqueado por el firewall.
- **Acción del usuario:** Se confirmó que hizo clic, sin ejecución de payloads.

---

## 🧾 Indicadores de Compromiso (IOCs)

| Tipo       | Valor                            | Observaciones                                   |
|------------|----------------------------------|-------------------------------------------------|
| Email      | `urgents@amazon.biz`             | Suplantación de marca (Amazon)                  |
| URL        | `http://bit.ly/3sHkX3da12340`     | Acortador que redirige a dominio malicioso      |
| IP         | `67.199.248.10`                  | IP de destino reportada como maliciosa          |
| Usuario    | `h.harris@thetrydaily.thm`       | Usuario afectado                                |
| IP interna | `10.20.2.17`                     | Dirección IP del equipo del usuario             |

---

## 🗺️ Técnicas MITRE ATT&CK

- **T1566.002** – Phishing: Link  
- **T1204.001** – User Execution: Malicious Link

---

## 🚨 Clasificación final

✅ Confirmado Malicioso  
➡️ Sin impacto: el intento fue bloqueado por el firewall  
➡️ No se requiere escalamiento

---

## 🛡️ Acciones tomadas

- El enlace fue reportado y agregado a listas de bloqueo.
- Se notificó al usuario afectado para reforzar concientización.
- No se detectó actividad adicional relacionada a esta alerta.
- IP maliciosa monitoreada en otras reglas SIEM.

---

## 📘 Lecciones aprendidas

- La suplantación de marcas conocidas sigue siendo efectiva.
- El firewall evitó un posible compromiso.
- Necesidad continua de concientización para usuarios finales.

---

## 📎 Evidencias

### 📌 Alerta SIEM

![splunk1](https://github.com/user-attachments/assets/b34eebfa-8b90-4f37-9b7d-2420cb65f645)


### 📌 Análisis en VirusTotal

![caso1vt](https://github.com/user-attachments/assets/7129a975-e95c-4c83-ad54-319190aa86c6)


### 📌 Reporte en AbuseIPDB

![caso1abuse](https://github.com/user-attachments/assets/f591f1c2-4e45-4ac2-9e03-96bc5c33367a)

