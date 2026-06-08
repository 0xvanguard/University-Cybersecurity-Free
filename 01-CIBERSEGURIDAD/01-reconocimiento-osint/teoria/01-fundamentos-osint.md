# 📖 Fundamentos de OSINT

> *"El reconocimiento es el 70% de un pentest exitoso. La mayoría falla porque subestima esta fase."*

---

## ¿Qué es OSINT?

**OSINT (Open Source Intelligence)** es la recopilación y análisis de información disponible públicamente para producir inteligencia accionable. No requiere acceso no autorizado, no deja huellas en el sistema objetivo, y es 100% legal cuando se usa con autorización.

La diferencia entre un atacante novato y un profesional está en el reconocimiento: el novato lanza exploits a ciegas; el profesional primero entiende perfectamente el objetivo.

---

## Las 5 fases del reconocimiento OSINT

```
┌─────────────────────────────────────────────────────────┐
│                                                         │
│  1. PLANIFICACIÓN  →  Define alcance, objetivos, límites │
│         ↓                                               │
│  2. RECOLECCIÓN   →  Fuentes pasivas, sin tocar target  │
│         ↓                                               │
│  3. PROCESAMIENTO →  Normalizar, limpiar, clasificar    │
│         ↓                                               │
│  4. ANÁLISIS      →  Correlacionar, encontrar patrones  │
│         ↓                                               │
│  5. REPORTE       →  Documentar hallazgos + evidencias  │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

---

## Fuentes de información (la taxonomía OSINT)

### 🌐 Infraestructura y dominios
| Fuente | Qué revela | Herramienta |
|---|---|---|
| DNS / WHOIS | Registrador, fechas, servidores NS | `whois`, `dig`, `nslookup` |
| Certificados TLS | Subdominios no publicados | `crt.sh`, `certspotter` |
| BGP / ASN | Rangos de IP propios de la org | `bgp.he.net`, `ipinfo.io` |
| Shodan / Censys | Puertos abiertos, banners, versiones | `shodan`, `censys.io` |
| Subdominios | Infraestructura oculta | `theHarvester`, `amass`, `subfinder` |

### 👤 Personas y correos
| Fuente | Qué revela | Herramienta |
|---|---|---|
| LinkedIn | Empleados, tecnologías usadas, estructura org | Manual + `linkedin2username` |
| GitHub | Emails en commits, tokens expuestos, código interno | `gitleaks`, búsqueda manual |
| Hunter.io | Patrón de emails corporativos | `theHarvester`, `hunter.io` |
| HaveIBeenPwned | Cuentas en brechas conocidas | API pública |

### 🖥️ Tecnología expuesta
| Fuente | Qué revela | Herramienta |
|---|---|---|
| Wappalyzer / BuiltWith | Stack tecnológico del sitio web | Extensión de navegador |
| Wayback Machine | Versiones antiguas con endpoints ocultos | `waybackurls`, `gau` |
| Google Dorks | Archivos sensibles indexados por error | Manual |
| Pastebin / GitHub | Credenciales, configs, keys filtradas | `pwnbin`, búsqueda manual |

---

## Google Dorks — Búsquedas de poder

Google Dorks son operadores avanzados de búsqueda que permiten encontrar información que normalmente no aparece en búsquedas normales.

### Operadores esenciales

| Operador | Uso | Ejemplo |
|---|---|---|
| `site:` | Limitar a un dominio | `site:empresa.com` |
| `filetype:` | Tipo de archivo específico | `filetype:pdf confidencial` |
| `inurl:` | Texto en la URL | `inurl:admin inurl:login` |
| `intitle:` | Texto en el título | `intitle:"index of" passwords` |
| `intext:` | Texto en el cuerpo | `intext:"password" filetype:txt` |
| `""` | Frase exacta | `"John Smith" "empresa.com"` |
| `-` | Excluir término | `site:empresa.com -www` |

### Dorks de práctica (uso en tus propios dominios únicamente)

```bash
# Archivos de configuración expuestos
site:empresa.com filetype:env OR filetype:cfg OR filetype:config

# Paneles de administración
site:empresa.com inurl:admin OR inurl:dashboard OR inurl:panel

# Documentos internos
site:empresa.com filetype:pdf OR filetype:xlsx OR filetype:docx

# Páginas de error con stack traces
site:empresa.com "sql syntax" OR "mysql_fetch" OR "undefined index"

# Subdominios menos conocidos
site:*.empresa.com -www -mail
```

---

## Metodología de un reconocimiento real

### Fase 1 — Perimetro externo (pasivo)
```bash
# 1. WHOIS básico
whois dominio.com

# 2. Registros DNS
dig dominio.com ANY
dig +short MX dominio.com
dig +short NS dominio.com

# 3. Subdominios via certificados (sin enviar paquetes al target)
curl -s "https://crt.sh/?q=%.dominio.com&output=json" | jq '.[].name_value' | sort -u
```

### Fase 2 — Enumeración de infraestructura
```bash
# 4. theHarvester — emails, subdominios, IPs, empleados
theharvester -d dominio.com -b google,bing,crtsh,linkedin -l 300 -f resultado-dominio

# 5. Búsqueda en Shodan (requiere cuenta gratuita)
shodan search "org:\"Nombre Empresa\"" --fields ip_str,port,org,hostnames

# 6. Wayback Machine — URLs históricas
waybackurls dominio.com | grep -E "\.php|\.asp|\.env" | sort -u
```

### Fase 3 — Reconocimiento de personas
```bash
# 7. Búsqueda de emails con patrón
# En theHarvester los emails aparecen en el output
# Validar formato con hunter.io (interfaz web)

# 8. GitHub — buscar la organización
# Buscar: org:nombre-empresa en GitHub
# Revisar commits recientes buscando emails y posibles secretos
```

---

## Conceptos clave

**Reconocimiento pasivo vs. activo:**
- **Pasivo:** No interactúas con el objetivo. Buscas en Google, Shodan, crt.sh. Cero riesgo legal. OSINT puro.
- **Activo:** Envías paquetes al objetivo (ping, nmap, dirbusting). Empieza el pentest real. Requiere autorización.

**Superficie de ataque:**
Todo lo que un atacante puede ver y potencialmente explotar: dominios, IPs, puertos, emails, tecnologías, empleados, credenciales filtradas.

**Huella digital:**
La suma de toda la información pública sobre un objetivo. Tu trabajo en OSINT es mapear esa huella antes de que lo haga un atacante real.

---

## ✅ Checklist de reconocimiento completo

```
DOMINIO Y DNS
  □ WHOIS (registrador, fechas, datos de contacto)
  □ Registros A, MX, NS, TXT, SPF, DMARC
  □ Subdominios via crt.sh
  □ Subdominios via theHarvester
  □ Rangos de IP / ASN

INFRAESTRUCTURA
  □ Tecnologías web (Wappalyzer)
  □ Shodan/Censys (puertos, servicios, versiones)
  □ Wayback Machine (endpoints históricos)
  □ Google Dorks (archivos expuestos)

PERSONAS
  □ Empleados en LinkedIn
  □ Patrón de emails corporativos
  □ Emails en resultados de búsqueda
  □ Revisión de GitHub de la organización
  □ HaveIBeenPwned (cuentas en brechas)

INFORMACIÓN FILTRADA
  □ Pastebin / GitHub (credenciales, configs)
  □ Documentos públicos con metadata
  □ Código fuente expuesto accidentalmente
```

---

**[← Volver al módulo](../README.md)** · **[→ Herramientas: theHarvester](../herramientas/theharvester.md)**
