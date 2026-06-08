<div align="center">

# 🔴 01 — CIBERSEGURIDAD

**Seguridad ofensiva · Red Team · OSINT · Pentesting**

*"Think like an attacker to defend like a pro."*

</div>

---

## 🎯 Propósito

Esta sección agrupa todo el conocimiento, herramientas y laboratorios relacionados con **seguridad ofensiva**. Cada subdominio sigue la cadena de ataque (Cyber Kill Chain / MITRE ATT&CK) desde reconocimiento hasta post-explotación.

> ⚖️ **Aviso:** Todas las técnicas aquí documentadas asumen **autorización explícita** sobre el objetivo. Solo se aplican en HTB, THM, CTFs, máquinas propias o con scope contractual firmado.

---

## 🗺️ Mapa de subdominios

| # | Subdominio | Fase Kill Chain | Tácticas MITRE |
|---|---|---|---|
| 01 | [Reconocimiento OSINT](./01-reconocimiento-osint/) | Reconnaissance | TA0043 |
| 02 | [Pentesting / Red Team](./02-pentesting-red-team/) | Múltiples | TA0001-TA0011 |
| 03 | [Análisis de Vulnerabilidades](./03-analisis-vulnerabilidades/) | Weaponization | TA0042 |
| 04 | [Explotación Web](./04-explotacion-web/) | Exploitation | TA0001 |
| 05 | [Post-Explotación](./05-post-explotacion/) | Actions on Objectives | TA0003-TA0008 |
| 06 | [Forense Digital](./06-forense-digital/) | Análisis | — |
| 07 | [Ingeniería Social](./07-ingenieria-social/) | Initial Access | TA0001 |
| 08 | [Criptografía](./08-criptografia/) | Transversal | — |

---

## 📂 Estructura tipo de cada subdominio

```
NN-nombre/
├── herramientas/      ← Una carpeta por herramienta + README con uso
├── tecnicas/          ← Procedimientos paso a paso
├── laboratorios/      ← Labs reproducibles (Docker / Vagrant)
└── README.md          ← Índice del subdominio
```

---

## 🔍 01 — Reconocimiento OSINT

> **Objetivo:** mapear la superficie de ataque sin tocar al objetivo.

**Herramientas clave:**
- `theHarvester` — emails, subdominios, hosts
- `Subfinder` / `Amass` — enumeración de subdominios
- `SpiderFoot` — automatización OSINT modular
- `Photon` — crawler con foco en intel
- `Osintgram` — Instagram OSINT
- `Nexfil` — username enumeration cross-platform

**Categorías de OSINT:**
- HUMINT digital (perfiles, redes sociales)
- DOMINT (dominios, DNS, certificados — `crt.sh`, `Censys`, `Shodan`)
- IMINT (imágenes — EXIF, geolocalización)
- TECHINT (stack técnico — `Wappalyzer`, `WhatWeb`, `BuiltWith`)

📁 [`./01-reconocimiento-osint/`](./01-reconocimiento-osint/)

---

## ⚔️ 02 — Pentesting / Red Team

> **Objetivo:** simular adversarios con metodología.

**Metodologías documentadas:**
- **PTES** — Penetration Testing Execution Standard
- **OWASP Testing Guide v4.2**
- **MITRE ATT&CK** — TTPs catalogados
- **OSSTMM** — Open Source Security Testing Methodology

**Stack ofensivo:**
- `Metasploit Framework` — explotación + post-exploit
- `Impacket` — toolkit Python para AD/SMB/Kerberos
- `BloodHound` + `SharpHound` — análisis de relaciones AD
- `CrackMapExec` / `NetExec` — pivoting AD
- `Sliver` / `Mythic` — C2 frameworks modernos (educativo)

📁 [`./02-pentesting-red-team/`](./02-pentesting-red-team/)

---

## 🕳️ 03 — Análisis de Vulnerabilidades

> **Objetivo:** identificar debilidades técnicas explotables.

**Herramientas:**
- `Nmap` + scripts NSE (`vulners`, `vulscan`)
- `Nuclei` — 10K+ templates de YAML
- `Nikto` — web server scanner
- `OpenVAS` / `Greenbone` — vuln management
- `Trivy` / `Grype` — SCA para imágenes Docker

**Bases de datos consultadas:**
- NVD (NIST) · CVE Mitre · ExploitDB · GTFOBins · LOLBAS · Vulners

📁 [`./03-analisis-vulnerabilidades/`](./03-analisis-vulnerabilidades/)

---

## 🌐 04 — Explotación Web

> **Objetivo:** dominar OWASP Top 10 con prácticas reales.

**OWASP Top 10 (2021) cubierto en `./04-explotacion-web/owasp-top10/`:**

| ID | Categoría |
|---|---|
| A01 | Broken Access Control |
| A02 | Cryptographic Failures |
| A03 | Injection (SQLi, NoSQLi, OS Command, LDAP) |
| A04 | Insecure Design |
| A05 | Security Misconfiguration |
| A06 | Vulnerable & Outdated Components |
| A07 | Identification and Authentication Failures |
| A08 | Software and Data Integrity Failures |
| A09 | Security Logging and Monitoring Failures |
| A10 | Server-Side Request Forgery (SSRF) |

**Stack:** `Burp Suite Pro/Community` · `OWASP ZAP` · `SQLMap` · `FFUF` · `Gobuster` · `Hakrawler`

📁 [`./04-explotacion-web/`](./04-explotacion-web/)

---

## 🚀 05 — Post-Explotación

> **Objetivo:** mantener acceso, escalar y moverse lateralmente.

| Subcarpeta | Foco |
|---|---|
| `privilege-escalation/` | LinPEAS · WinPEAS · GTFOBins · LOLBAS · sudo abuse · SUID |
| `lateral-movement/` | Pass-the-Hash · Pass-the-Ticket · WMI · WinRM · SMB relay |
| `persistence/` | Cron · systemd services · scheduled tasks · registry keys |

📁 [`./05-post-explotacion/`](./05-post-explotacion/)

---

## 🔬 06 — Forense Digital

> **Objetivo:** análisis post-incidente y extracción de evidencia.

**Herramientas:**
- `Autopsy` / `The Sleuth Kit` — disk forensics
- `Volatility` / `Volatility3` — memory forensics
- `ExifTool` — metadatos
- `Wireshark` / `tshark` — network forensics
- `KAPE` — triage rápido (Windows)
- `plaso` / `log2timeline` — timeline forense

📁 [`./06-forense-digital/`](./06-forense-digital/)

---

## 🎭 07 — Ingeniería Social

> **Objetivo:** comprender el vector humano (siempre con autorización + ética).

**Herramientas:**
- `GoPhish` — phishing campaigns con dashboard
- `Social-Engineer Toolkit (SET)` — múltiples vectores
- `Evilginx2` — adversary-in-the-middle (educativo)
- `King Phisher` — alternativa a GoPhish

**Categorías:**
- Phishing (correo) · Vishing (voz) · Smishing (SMS)
- Pretexting · Baiting · Tailgating

📁 [`./07-ingenieria-social/`](./07-ingenieria-social/)

---

## 🔐 08 — Criptografía

> **Objetivo:** entender primitivas, romperlas en CTF y aplicarlas correctamente.

**Conceptos:**
- Simétrica (AES, ChaCha20) vs Asimétrica (RSA, ECC)
- Funciones hash (SHA-2/3, BLAKE3) y collisions
- HMAC · KDFs (PBKDF2, Argon2, scrypt)
- TLS handshake · perfect forward secrecy
- PKI · X.509 · OCSP

**Herramientas:**
- `OpenSSL` · `Hashcat` · `John the Ripper` · `CyberChef` · `RsaCtfTool`

📁 [`./08-criptografia/`](./08-criptografia/)

---

## 💼 Ramas laborales — Carrera profesional (26 paths)

> Más allá de las áreas de conocimiento, aquí están las **rutas de carrera** mapeadas a CISSP + NIST NICE + emergentes 2024-2026. Cada una con descripción, stack, certificaciones, roadmap 12 meses, salarios Colombia (local + remoto) y conexiones cruzadas.

### 🏛️ 7 ramas clásicas CISSP (dominios)

| Rama | Tier salarial | Mid-USD/mes |
|---|---|---|
| [`seguridad-redes/`](./seguridad-redes/) | B | $1,700-3,200 |
| [`seguridad-aplicaciones/`](./seguridad-aplicaciones/) | A | $2,000-4,000 |
| [`seguridad-informacion-datos/`](./seguridad-informacion-datos/) | B/A | $1,800-3,500 |
| [`seguridad-operacional/`](./seguridad-operacional/) | C/B | $1,300-2,800 |
| [`seguridad-nube/`](./seguridad-nube/) | A | $2,000-4,000 |
| [`seguridad-endpoint/`](./seguridad-endpoint/) | B | $1,700-3,200 |
| [`seguridad-iot-ot/`](./seguridad-iot-ot/) | A | $2,200-4,200 |

### 🎯 14 especialidades NIST NICE (roles)

| Rama | Tier | Mid-USD/mes |
|---|---|---|
| [`analista-soc/`](./analista-soc/) | B | $1,400-2,500 |
| [`pentester-red-team/`](./pentester-red-team/) | A | $2,000-4,000 |
| [`threat-hunter/`](./threat-hunter/) | A | $2,200-4,500 |
| [`forense-digital/`](./forense-digital/) | B | $1,800-3,500 |
| [`grc-compliance/`](./grc-compliance/) | C/B | $1,300-2,800 |
| [`arquitecto-seguridad/`](./arquitecto-seguridad/) | A/S | $5,000-9,000 (sr) |
| [`security-engineer/`](./security-engineer/) | A | $2,200-4,300 |
| [`incident-responder/`](./incident-responder/) | A/B | $2,000-4,000 |
| [`vulnerability-manager/`](./vulnerability-manager/) | B | $1,700-3,200 |
| [`cryptographer/`](./cryptographer/) | **S** | $2,500-5,000 |
| [`security-analyst/`](./security-analyst/) | C/B | $1,200-2,500 |
| [`penetration-tester-specialized/`](./penetration-tester-specialized/) | A/S | $2,500-5,000 |
| [`malware-analyst/`](./malware-analyst/) | **S** | $2,500-5,000 |
| [`security-consultant/`](./security-consultant/) | B/A | $2,000-4,000 |

### 🚀 5 emergentes 2024-2026

| Rama | Tier | Mid-USD/mes |
|---|---|---|
| [`ia-security/`](./ia-security/) | **S** | $2,500-5,000 |
| [`seguridad-cadena-suministro/`](./seguridad-cadena-suministro/) | A | $2,200-4,300 |
| [`seguridad-defensiva-blue-team/`](./seguridad-defensiva-blue-team/) | B/A | $2,000-4,000 |
| [`threat-intelligence/`](./threat-intelligence/) | B/A | $2,000-4,000 |
| [`bug-bounty-hunting/`](./bug-bounty-hunting/) | Variable | P50: $2-8K/año |

> **Tier salarial:** **S** = premium escaso · **A** = alta demanda · **B** = demanda media-alta · **C** = entry/generalista
> Salarios reflejan empresas con presencia LATAM. Ver cada README para tabla completa local + remoto + breakdown por nivel (Junior / Mid / Senior).

---

## 🧭 Cómo usar esta sección

1. Identifica la **fase de la kill chain** en la que necesitas trabajar.
2. Entra al subdominio correspondiente.
3. Revisa el README del subdominio → carpeta `tecnicas/` para teoría.
4. Pasa a `herramientas/` para uso práctico.
5. Replica en `laboratorios/` con un entorno controlado.

> Si buscas **carrera profesional** en lugar de área de conocimiento, ve a la sección [Ramas laborales](#-ramas-laborales--carrera-profesional-26-paths) ↑

---

<div align="center">

**[⬅ Volver al README principal](../README.md)** · **[🔵 Ir a Defensiva →](../02-SEGURIDAD-INFORMACION/)**

</div>
