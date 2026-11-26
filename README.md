# WAVE Hunter - Web App Vulnerability Explorer

## Descripción del Producto

**WAVE Hunter** es un agente automatizado de pruebas de seguridad que identifica vulnerabilidades en aplicaciones web basándose en el OWASP Top 10 2025. Mediante inyección de payloads y análisis de respuestas HTTP, genera reportes detallados con matriz de riesgos y recomendaciones de remediación.

## ¿Qué hace WAVE Hunter?

WAVE Hunter automatiza la detección de vulnerabilidades críticas en aplicaciones web sin requerir conocimiento especializado. Es una herramienta CLI standalone diseñada para desarrolladores y equipos de seguridad en pequeñas empresas que necesitan validar la seguridad de sus aplicaciones antes del despliegue.

## Características Principales

- **8 Módulos de Prueba** (6 categorías OWASP 2025): SQL Injection, XSS, 
  Broken Authentication, Access Control (IDOR), CSRF, Security 
  Misconfiguration, Insecure Design, Exception Handling.
- **Análisis Automático**: Detecta vulnerabilidades mediante patrones y 
  análisis de respuestas HTTP.
- **Reportes PDF**: Genera reportes con matriz CVSS, hallazgos y 
  recomendaciones.
- **CLI Simple**: Interfaz de línea de comandos intuitiva y fácil de usar.
- **Standalone**: Sin dependencias externas, funciona en Windows, Linux, macOS.
- **Modular**: Arquitectura extensible para agregar nuevas pruebas.

## Uso Básico

```bash
waveh --url http://target.com
waveh --url https://vulnerable-app.local --output reporte.pdf
```

## ¿A quién va dirigido?

- Desarrolladores que desean validar seguridad de aplicaciones web.
- Equipos de seguridad en PYMEs sin acceso a herramientas profesionales.
- Estudiantes aprendiendo sobre ciberseguridad web.

## Limitaciones

- No reemplaza auditorías profesionales.
- Pruebas basadas en patrones, no análisis en profundidad.
- Requiere conectividad HTTP/HTTPS a la aplicación objetivo.
- No incluye análisis de código estático.

## Stack Tecnológico

- **Lenguaje**: Python 3.11+
- **HTTP Client**: requests, httpx
- **Parsing**: BeautifulSoup4
- **Reportes**: jinja2 + WeasyPrint
- **CLI**: click

## Instalación Rápida

```bash
git clone https://github.com/AZTLEXMX/WAVE_Hunter.git
cd WAVE_Hunter
pip install -r requirements.txt
waveh --url http://localhost:5000
```

## Ejemplo de Salida

```
============================================================
AGENTE DE PRUEBAS DE VULNERABILIDADES OWASP TOP 10
============================================================
Target: http://vulnerable-app.local
Módulos registrados: 8
============================================================

[1/8] Ejecutando SQLInjectionModule...
    └─ Hallazgos: 2

[2/8] Ejecutando XSSModule...
    └─ Hallazgos: 1

[3/8] Ejecutando BrokenAuthModule...
    └─ Hallazgos: 1

...

============================================================
MATRIZ DE RIESGOS
============================================================
CRÍTICA: 2
ALTA:    1
MEDIA:   1
BAJA:    0
───────────────────────
TOTAL:   4
============================================================

Escaneo completado
Vulnerabilidades encontradas: 4
Reporte guardado en: reporte.pdf
```

---

**Nombre del Proyecto**: WAVE Hunter

**Versión**: 1.0.0

**Estado**: En desarrollo

**Licencia**: GPL-3.0 license
