# 🗂️ Construye tu Portafolio de Ciberseguridad

> Un portafolio técnico es tu CV real en seguridad. No lo que dices que sabes — lo que puedes demostrar.

---

## ¿Por qué importa el portafolio?

En ciberseguridad, las empresas contratan evidencia, no títulos. Un repositorio GitHub bien documentado, un writeup publicado o un script funcional valen más en una entrevista técnica que una certificación sin práctica real.

Esta universidad está diseñada para que **cada módulo genere un entregable publicable**.

---

## Tipos de entregables por módulo

### 🔴 Módulos Ofensivos

| Módulo | Entregable sugerido | Plataforma de publicación |
|---|---|---|
| OSINT | Script de recon automatizado | GitHub |
| Pentesting | Reporte profesional (anónimo) | GitHub / Blog |
| Vulnerabilidades | Script de escaneo personalizado | GitHub |
| Explotación Web | Writeup de lab DVWA/OWASP | GitHub / Medium |
| Post-Explotación | Writeup HTB/THM con metodología | GitHub / HTB |
| Forense | Informe de análisis de imagen de disco | GitHub |
| Ingeniería Social | Campaña de simulación documentada | GitHub (privado opción) |
| Criptografía | Script de análisis de hashes | GitHub |

### 🔵 Módulos Defensivos

| Módulo | Entregable sugerido | Plataforma de publicación |
|---|---|---|
| Riesgos | Matriz de riesgo (Markdown/PDF) | GitHub |
| Blue Team | Entorno Wazuh Docker + reglas propias | GitHub |
| SOC Operations | Playbook de IR en Markdown | GitHub |
| DevSecOps | Pipeline CI/CD completo | GitHub (repo público) |
| Hardening | Script de hardening Linux | GitHub |
| Compliance | Checklist de cumplimiento | GitHub |
| Threat Intel | Análisis ATT&CK de campaña APT | GitHub / Blog |

### 🤖 Módulos IA

| Módulo | Entregable sugerido | Plataforma de publicación |
|---|---|---|
| Agentes OSINT | Pipeline automatizado | GitHub |
| Agentes Pentest | Agente de recon con LLM | GitHub |
| LLM Security | Reporte de auditoría | GitHub / Blog |
| Automatización | Bot de alertas Telegram | GitHub |

---

## Formato de un buen entregable

Cada proyecto que publiques debería tener:

```markdown
# Nombre del proyecto

## ¿Qué hace?
Descripción en 2–3 oraciones. Para qué sirve y en qué contexto.

## Prerrequisitos
Qué herramientas/OS/conocimientos necesitas.

## Instalación y uso
```bash
git clone ...
pip install -r requirements.txt
python tool.py --target ejemplo.com
```

## Ejemplo de output
(Captura de pantalla o bloque de texto)

## Lo que aprendí
Qué técnica, herramienta o concepto practicaste.

## Módulo relacionado
Enlace al módulo de esta universidad.
```

---

## Cómo publicar writeups

### En GitHub (repositorio propio)
1. Crea un repo con el formato: `writeup-[plataforma]-[nombre-maquina]`
2. Documenta con Markdown: objetivo, reconocimiento, explotación, post-explotación.
3. Agrega el módulo relacionado y el nivel HTB/THM.
4. **Nunca publiques** flags, contraseñas reales o datos de entornos productivos.

### En Medium o blog personal
1. Explica el proceso con capturas de pantalla.
2. Usa el formato: Recon → Explotación → Lecciones aprendidas.
3. Etiqueta con `#ciberseguridad #pentesting #ctf`.

---

## Cómo mostrar tu portafolio en LinkedIn

Cada entregable puede ser un post de LinkedIn siguiendo esta estructura:

```
🔐 Nuevo módulo completado: [NOMBRE]

✅ Lo que practiqué:
- [Técnica 1]
- [Técnica 2]

🧪 Proyecto: [Descripción breve del entregable]

🔗 Código/writeup: [Enlace a GitHub]

#ciberseguridad #portafolio #aprendiendohaciendo
```

---

## Nivel progresivo de portafolio

| Nivel | Qué muestra | Señal para empresas |
|---|---|---|
| 🟢 Básico | Scripts simples, notas técnicas, primeros CTFs | Curiosidad y disposición a aprender |
| 🟡 Intermedio | Labs documentados, writeups HTB/THM, pipelines | Conocimiento técnico aplicado |
| 🔴 Avanzado | Herramientas propias, agentes IA, reportes de pentest | Perfil contratrable para roles entry-level |

---

## Portafolio mínimo viable para buscar empleo

Para empezar a aplicar a roles entry-level en ciberseguridad, necesitas al menos:

- [ ] 3 writeups de CTF o HTB/THM documentados
- [ ] 1 script de automatización de seguridad publicado
- [ ] 1 entorno de lab propio (Docker o VM) documentado
- [ ] 1 informe técnico (reporte de pentest o análisis forense)
- [ ] README profesional en tu GitHub con bio y proyectos destacados
- [ ] LinkedIn actualizado con proyectos enlazados

---

*[← Volver al README](./README.md) · [🗺️ Ver Rutas](./RUTAS.md) · [📋 Ver Módulos](./MODULOS.md)*
