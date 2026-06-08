# 🗺️ Rutas de Aprendizaje

> Elige tu camino. Cada ruta tiene una secuencia lógica, prerrequisitos, duración estimada y un proyecto final que puedes publicar en tu portafolio.

---

## 🟢 Ruta 1 — Fundamentos

**Para quién:** Personas sin experiencia en ciberseguridad. Puedes venir de IT, desarrollo o simplemente ser curioso.

**Duración estimada:** 4–6 semanas a ritmo de 1–2 horas diarias.

**Prerrequisitos:** Ninguno. Solo ganas de aprender.

### Secuencia de módulos

| Semana | Tema | Carpeta | Resultado |
|---|---|---|---|
| 1 | Linux básico y línea de comandos | `05-RECURSOS/` | Navegar y operar en terminal sin ayuda |
| 2 | Redes: TCP/IP, DNS, HTTP | `05-RECURSOS/` | Entender cómo fluye el tráfico en internet |
| 3 | Git y GitHub para seguridad | `05-RECURSOS/` | Publicar tu primer repo técnico |
| 4 | Introducción a criptografía | `01-CIBERSEGURIDAD/08-criptografia/` | Usar OpenSSL para cifrar/descifrar |
| 5 | OSINT básico | `01-CIBERSEGURIDAD/01-reconocimiento-osint/` | Ejecutar búsqueda OSINT con theHarvester |
| 6 | Primer CTF sencillo | `04-LABORATORIOS/ctf-writeups/` | Writeup publicado en GitHub |

**Proyecto de portafolio final:** Writeup de tu primer CTF + repositorio personal de notas técnicas.

---

## 🔴 Ruta 2 — Red Team / Seguridad Ofensiva

**Para quién:** Personas que ya manejan Linux, redes básicas y quieren aprender a auditar sistemas.

**Duración estimada:** 3–4 meses a ritmo de 1–2 horas diarias.

**Prerrequisitos:** Ruta Fundamentos completada o conocimiento equivalente.

### Secuencia de módulos

| Mes | Tema | Carpeta | Resultado |
|---|---|---|---|
| 1 | OSINT avanzado + reconocimiento pasivo | `01-CIBERSEGURIDAD/01-reconocimiento-osint/` | Script de recon automatizado |
| 1 | Análisis de vulnerabilidades con Nmap y Nuclei | `01-CIBERSEGURIDAD/03-analisis-vulnerabilidades/` | Informe de escaneo profesional |
| 2 | Explotación web (OWASP Top 10) | `01-CIBERSEGURIDAD/04-explotacion-web/` | Writeup de lab OWASP WebGoat/DVWA |
| 2 | Metasploit y Impacket básico | `01-CIBERSEGURIDAD/02-pentesting-red-team/` | Lab explotado y documentado |
| 3 | Post-explotación y escalada de privilegios | `01-CIBERSEGURIDAD/05-post-explotacion/` | Writeup HTB o THM |
| 3 | Ingeniería social + GoPhish | `01-CIBERSEGURIDAD/07-ingenieria-social/` | Campaña de phishing simulado |
| 4 | Forense básico | `01-CIBERSEGURIDAD/06-forense-digital/` | Análisis de imagen de disco |
| 4 | Proyecto final: Reporte de pentest completo | `04-LABORATORIOS/` | Reporte profesional publicable |

**Certificación recomendada al finalizar:** eJPT (eLearnSecurity Junior Penetration Tester)

**Proyecto de portafolio final:** Reporte de pentesting completo sobre lab propio — formato ejecutivo y técnico.

---

## 🔵 Ruta 3 — Blue Team / Defensa

**Para quién:** Personas con conocimiento de sistemas y redes que quieren trabajar en SOC, incident response o hardening.

**Duración estimada:** 3–4 meses.

**Prerrequisitos:** Ruta Fundamentos + conocimiento básico de Linux/Windows.

### Secuencia de módulos

| Mes | Tema | Carpeta | Resultado |
|---|---|---|---|
| 1 | Gestión de riesgos (ISO 27001 / NIST) | `02-SEGURIDAD-INFORMACION/01-gestion-riesgos/` | Matriz de riesgo de empresa ficticia |
| 1 | Hardening Linux con CIS Benchmarks | `02-SEGURIDAD-INFORMACION/05-hardening/` | Script de hardening publicado |
| 2 | Wazuh SIEM: despliegue y reglas | `02-SEGURIDAD-INFORMACION/02-blue-team-defensa/` | Entorno Wazuh levantado en Docker |
| 2 | Threat Hunting con YARA y Sigma | `02-SEGURIDAD-INFORMACION/07-threat-intelligence/` | Reglas YARA propias |
| 3 | SOC Operations y playbooks | `02-SEGURIDAD-INFORMACION/03-soc-operations/` | Playbook de respuesta a ransomware |
| 3 | Threat Intelligence y MITRE ATT&CK | `02-SEGURIDAD-INFORMACION/07-threat-intelligence/` | Análisis de campaña APT con ATT&CK Navigator |
| 4 | Compliance: GDPR + Ley 1581/2009 CO | `02-SEGURIDAD-INFORMACION/06-compliance-normativas/` | Checklist de cumplimiento |
| 4 | Proyecto final: SOC en miniatura | `04-LABORATORIOS/docker-labs/` | Lab SOC Docker reproducible |

**Certificación recomendada al finalizar:** CompTIA Security+

**Proyecto de portafolio final:** Entorno SOC en Docker con reglas de detección personalizadas y playbook de IR.

---

## ⚙️ Ruta 4 — DevSecOps

**Para quién:** Desarrolladores o sysadmins que quieren integrar seguridad en pipelines de CI/CD.

**Duración estimada:** 2–3 meses.

**Prerrequisitos:** Saber programar (Python o cualquier lenguaje) + conocimiento de Git.

### Secuencia de módulos

| Semana | Tema | Carpeta | Resultado |
|---|---|---|---|
| 1–2 | Docker seguro: imágenes, secrets, rootless | `02-SEGURIDAD-INFORMACION/04-devsecops/` | Dockerfile seguro con escáner integrado |
| 3–4 | Secret scanning: TruffleHog y GitLeaks | `02-SEGURIDAD-INFORMACION/04-devsecops/` | Pipeline que bloquea commits con secretos |
| 5–6 | SAST/DAST: Semgrep, ZAP en CI | `02-SEGURIDAD-INFORMACION/04-devsecops/` | Workflow de GitHub Actions con análisis |
| 7–8 | Hardening de infraestructura como código | `02-SEGURIDAD-INFORMACION/05-hardening/` | Playbook Ansible de hardening |
| 9–10 | Kubernetes básico + políticas de seguridad | `02-SEGURIDAD-INFORMACION/04-devsecops/` | Cluster con Pod Security Standards |
| 11–12 | Proyecto final: pipeline DevSecOps completo | `04-LABORATORIOS/docker-labs/` | Repo con CI/CD seguro end-to-end |

**Certificación recomendada al finalizar:** AWS Security Specialty o CKS (Certified Kubernetes Security)

**Proyecto de portafolio final:** Repositorio con pipeline CI/CD completo con escaneo de secretos, SAST, DAST y hardening automatizado.

---

## 🤖 Ruta 5 — IA Aplicada a Seguridad

**Para quién:** Personas con Python básico que quieren automatizar reconocimiento, análisis y triage con IA.

**Duración estimada:** 2–3 meses.

**Prerrequisitos:** Python básico (funciones, listas, APIs REST).

### Secuencia de módulos

| Semana | Tema | Carpeta | Resultado |
|---|---|---|---|
| 1–2 | Automatización Python para seguridad | `03-AI-AGENTS-TOOLS/05-automatizacion-python/` | Scripts de escaneo y alerta |
| 3–4 | Pipelines OSINT con Python + APIs | `03-AI-AGENTS-TOOLS/01-agentes-osint/` | Pipeline que agrega inteligencia de múltiples fuentes |
| 5–6 | Integrar LLMs: Anthropic API + Ollama | `03-AI-AGENTS-TOOLS/02-agentes-pentest/` | Agente que resume resultados de Nmap |
| 7–8 | Seguridad de LLMs: OWASP LLM Top 10 | `03-AI-AGENTS-TOOLS/03-llm-security/` | Reporte de auditoría de un chatbot |
| 9–10 | Prompt Injection y AI Red Teaming | `03-AI-AGENTS-TOOLS/03-llm-security/` | Lab de ataque a modelo IA |
| 11–12 | Proyecto final: agente de seguridad completo | `04-LABORATORIOS/` | Agente publicado en GitHub |

**Herramientas clave:** Python 3.12 · Anthropic SDK · Ollama · LangChain · Telegram Bot API.

**Proyecto de portafolio final:** Agente de IA que automatiza una tarea de seguridad real (OSINT, triage, reporting o detección).

---

## 🔀 Rutas combinadas recomendadas

| Objetivo laboral | Rutas sugeridas | Certificaciones |
|---|---|---|
| SOC Analyst L1/L2 | Fundamentos → Blue Team | Security+ → CySA+ |
| Pentester Junior | Fundamentos → Red Team | eJPT → OSCP |
| DevSecOps Engineer | Fundamentos → DevSecOps | Security+ → CKS |
| AI Security Researcher | Fundamentos → IA Aplicada → Red Team | Sin cert específica aún |
| Security Generalist | Fundamentos → Blue Team → Red Team | Security+ → CEH |

---

*[← Volver al README](./README.md) · [📋 Ver todos los módulos](./MODULOS.md)*
