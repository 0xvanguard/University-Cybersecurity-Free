# Facultad: Purple Team / Colaboración Red–Blue

> **Rol de la facultad:** Unir el trabajo de **Red Team (ofensiva)** y **Blue Team (defensiva)** para diseñar, ejecutar y medir ejercicios donde ataque y defensa colaboran para mejorar las detecciones y la seguridad real del entorno.

---

## 1. Propósito de la Facultad Purple Team

Mientras que Red Team se centra en simular adversarios y Blue Team en detectar y responder, **Purple Team** busca que ambos trabajen juntos de forma estructurada.

En esta facultad el alumno aprenderá a:

- Traducir técnicas ofensivas concretas en **hipótesis de detección**.  
- Diseñar y ejecutar **ejercicios colaborativos** donde se dispara una técnica y se observa cómo responde el entorno.  
- Medir si las detecciones son suficientes, mejorarlas y documentar el resultado.  

El objetivo final es que el alumno entienda el ciclo completo: **ataque → detección → respuesta → mejora continua**, usando el mismo escenario (por ejemplo, la fintech NovaPay Labs) desde ambas perspectivas.

---

## 2. Objetivos de aprendizaje

Al completar los primeros módulos de Purple Team, el alumno debería ser capaz de:

1. Explicar qué es Purple Team y en qué se diferencia de ejercicios puramente Red o Blue.  
2. Tomar una técnica ofensiva simple (por ejemplo, intentos de login fallidos masivos contra el portal de merchants) y diseñar un **caso de detección** asociado.  
3. Ejecutar un ejercicio de Purple Team básico: disparar una actividad ofensiva controlada y observar cómo aparece en los logs/herramientas de monitoreo.  
4. Evaluar la efectividad de las detecciones existentes (¿hay alerta?, ¿se ve el patrón?, ¿falta contexto?) y proponer mejoras.  
5. Documentar el ejercicio en términos de tácticas/técnicas (por ejemplo, usando MITRE ATT&CK como mapa mental).  

---

## 3. Primera pieza Purple Team con NovaPay Labs

Para arrancar, se usará el escenario ya conocido de **NovaPay Labs**:

- Portal de merchants (ruta ofensiva: Recon + Pentest web).  
- Logs de firewall, autenticación y aplicación web (ruta Blue Team: Lab 01 + Lab 02 SOC).  

La primera pieza Purple Team consistirá en un **laboratorio integrado** donde el alumno:

- Ejecuta una actividad ofensiva sencilla (por ejemplo, intentos de login fallidos controlados contra el portal).  
- Observa cómo esos intentos aparecen en la plataforma de monitoreo (ELK/Wazuh).  
- Evalúa si la visibilidad actual sería suficiente para detectar una fuerza bruta básica.  
- Propone ajustes o ideas de detección.

---

## 4. Concepto de laboratorio Purple Team — "Login storm" controlado en NovaPay

> **Nombre tentativo:** Lab 01 — Ejercicio Purple Team básico: login fallidos contra el portal de merchants

### 4.1 Narrativa

La fintech NovaPay Labs quiere validar si su entorno está preparado para detectar un patrón simple pero común: **múltiples intentos de login fallidos** contra el portal de merchants.

Como equipo Purple Team, tendrás dos gorros:

- Con el gorro **Red**, simularás un pequeño "login storm" controlado contra el portal (sin llegar a DoS ni fuerza bruta agresiva).  
- Con el gorro **Blue**, revisarás cómo se reflejan esos intentos en los logs y en la herramienta SOC, y juzgarás si la detección actual sería suficiente.

### 4.2 Alcance

Incluido:

- Portal de merchants de NovaPay Labs en el entorno de laboratorio.  
- Generación controlada de intentos de login fallidos (por ejemplo, usando un script suave o pruebas manuales repetidas).  
- Revisión de logs de autenticación y aplicación web en la plataforma SOC (ELK/Wazuh) utilizada en el módulo Blue Team.  

Fuera de alcance:

- Ataques de fuerza bruta a gran escala.  
- Explotación de vulnerabilidades más avanzadas.  
- Cambios de configuración profundos en la plataforma SOC (más allá de ideas o pseudorreglas de detección).

### 4.3 Objetivos específicos del lab

Al terminar este laboratorio Purple Team, el alumno debería ser capaz de:

1. Ejecutar un conjunto de intentos de login fallidos de forma controlada contra el portal.  
2. Localizar esos eventos en los logs y en la herramienta SOC, confirmando que la telemetría los captura.  
3. Identificar el patrón (por ejemplo, N intentos fallidos en una ventana de tiempo) y valorar si existiría una alerta o si sería fácil definir una.  
4. Formular al menos **una propuesta de mejora de detección** (umbral, correlación, alerta) basada en lo observado.  

### 4.4 Material necesario

- Acceso al **portal de merchants** en el entorno de laboratorio.  
- Cuenta(s) de prueba o credenciales falsas permitidas para el ejercicio (para no usar cuentas reales).  
- Acceso a la **herramienta SOC** (ELK/Wazuh) donde se recojan logs de autenticación y aplicación web del portal.  
- Guía básica con:  
  - Cómo lanzar los intentos de login (manual o script proporcionado).  
  - Qué índice/fuente de datos revisar en la herramienta SOC.  

### 4.5 Tareas principales (a alto nivel)

1. **Fase Red (simulación de ataque):**  
   - Realizar un número definido de intentos de login fallidos hacia una cuenta de prueba (por ejemplo, 10–20 intentos en pocos minutos).  
   - Registrar la IP origen y el intervalo de tiempo aproximado.  

2. **Fase Blue (búsqueda y análisis):**  
   - En la herramienta SOC, filtrar los logs de autenticación para el rango de tiempo e IP origen utilizados.  
   - Confirmar que los intentos aparecen correctamente registrados (campos de usuario, resultado, IP, timestamp).  
   - Identificar si ya existe algún tipo de alerta o regla visible para este patrón.  

3. **Fase Purple (discusión y mejora):**  
   - Documentar el patrón observado (por ejemplo, "15 LOGIN_FAILURE para el mismo usuario en 3 minutos desde la IP X").  
   - Evaluar si un analista SOC podría detectarlo fácilmente en el día a día.  
   - Proponer una idea de regla o umbral (aunque sea en pseudocódigo) para generar una alerta ante este patrón.  

### 4.6 Entregables

- Una **ficha de evento SOC** específica para este ejercicio, usando la plantilla oficial, donde se detalle:
  - Clasificación del evento (autenticación, comportamiento sospechoso).  
  - Descripción del patrón de login fallidos.  
  - Análisis del impacto potencial.  
  - Recomendaciones de detección y respuesta.  
- Un mini resumen Purple Team (puede ser una sección adicional) donde el alumno explique:
  - Qué hizo como "Red".  
  - Qué observó como "Blue".  
  - Qué mejora propone para cerrar el ciclo.

---

## 5. Próximos pasos para la facultad Purple Team

A partir de este primer concepto, se podrán ir añadiendo:

- Un **README específico del primer módulo Purple Team** (por ejemplo, `01-ejercicios-colaborativos-basicos/`) con este lab como pieza central.  
- Labs adicionales que usen otras técnicas ofensivas simples (por ejemplo, exploración de rutas, ejecución de scripts en endpoints) y sus reflejos en la telemetría.  
- Una futura integración con módulos de IA/MLSecOps donde parte de la lógica de detección/mejora se automatice.

Esta primera pieza ya deja claro el espíritu Purple: usar lo ofensivo para fortalecer lo defensivo en un mismo escenario, con métricas y aprendizaje en ambas direcciones.
