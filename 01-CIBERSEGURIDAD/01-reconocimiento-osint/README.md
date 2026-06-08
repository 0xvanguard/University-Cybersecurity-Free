# 🔍 Módulo 01 — Reconocimiento OSINT

> **Objetivo Principal:** Recopilar, correlacionar y analizar información pública sobre un objetivo usando herramientas OSINT profesionales, sin interactuar directamente con el sistema objetivo.

[![Nivel](https://img.shields.io/badge/Nivel-Básico-green?style=flat-square)]()
[![Duración](https://img.shields.io/badge/Duración-2--3%20semanas-blue?style=flat-square)]()
[![Lab Docker](https://img.shields.io/badge/Lab-Docker%20incluido-orange?style=flat-square)](./laboratorio/)
[![Portafolio](https://img.shields.io/badge/Entregable-Dashboard%20OSINT-purple?style=flat-square)](./portafolio/)

---

## 📋 Resumen del módulo

| Atributo | Detalle |
|---|---|
| 🏷️ **Nivel** | Básico (sin experiencia previa requerida) |
| ⏱️ **Duración estimada** | 2–3 semanas (4–6h por semana) |
| 🎯 **Resultado esperado** | Crear un informe OSINT profesional sobre un objetivo autorizado |
| 🧪 **Práctica verificable** | Lab Docker con objetivo local + reto final contra dominio propio |
| 🗂️ **Portafolio** | Reporte OSINT anonimizado publicable en GitHub/LinkedIn |
| 🔗 **Sigue a** | — (primer módulo recomendado) |
| 🔗 **Conduce a** | [Módulo 02 — Pentesting / Red Team](../02-pentesting-red-team/) |

---

## 🗺️ Contenido del módulo

```
01-reconocimiento-osint/
├── README.md                    ← Estás aquí
├── teoria/
│   └── 01-fundamentos-osint.md  ← Conceptos base, metodología, fases
├── herramientas/
│   ├── theharvester.md          ← Emails, subdominios, IPs
│   ├── spiderfoot.md            ← Reconocimiento automatizado
│   └── google-dorks.md          ← Búsquedas avanzadas en Google
├── laboratorio/
│   ├── README-lab.md            ← Instrucciones del lab
│   └── docker-compose.yml       ← Entorno reproducible
└── portafolio/
    └── TEMPLATE-reporte-osint.md ← Plantilla de reporte profesional
```

---

## ⚡ Inicio rápido

```bash
# 1. Clonar el repo
git clone https://github.com/0xvanguard/--Universidad-abierta-de-ciberseguridad-en-espa-ol.git
cd --Universidad-abierta-de-ciberseguridad-en-espa-ol/01-CIBERSEGURIDAD/01-reconocimiento-osint/

# 2. Leer la teoría primero (20 min)
cat teoria/01-fundamentos-osint.md

# 3. Levantar el lab
cd laboratorio/
docker compose up -d

# 4. Ejecutar theHarvester contra el objetivo de práctica
theharvester -d testphp.vulnweb.com -b google,bing,crtsh -l 200
```

---

## 🎯 ¿Qué sabrás hacer al terminar?

- [ ] Ejecutar un proceso OSINT completo en 5 fases (planificación → recolección → análisis → correlación → reporte)
- [ ] Recopilar subdominios, emails y tecnologías de un dominio objetivo
- [ ] Identificar infraestructura expuesta usando Shodan y Censys sin tocar el sistema
- [ ] Crear Google Dorks para filtrar información sensible indexada
- [ ] Generar un reporte OSINT en formato ejecutivo + técnico
- [ ] Publicar tu primer entregable de portafolio

---

## ⚖️ Aviso ético

> OSINT es legal cuando se aplica a **objetivos propios o con autorización escrita**. Nunca apliques estas técnicas contra personas, organizaciones o infraestructura sin permiso explícito. Cumplimiento con Ley 1273/2009 (Colombia) · GDPR · CFAA.

---

**[⬆ Volver al inicio](../../README.md)** · **[📖 Leer teoría →](./teoria/01-fundamentos-osint.md)** · **[🧪 Ir al lab →](./laboratorio/README-lab.md)**
