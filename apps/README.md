# ⚙️ Aplicaciones de Seguridad

Este directorio contiene las distintas herramientas de seguridad utilizadas en Onestic, organizadas de forma modular y estandarizada para facilitar su despliegue, mantenimiento e integración mediante CI/CD.

---

## 📦 Estructura por aplicación

Cada subcarpeta bajo `apps/` representa una herramienta concreta y sigue la siguiente estructura base:
```tree
apps/<nombre_app>/
├── base/ # Dockerfile, entrypoint y recursos base del contenedor
├── config/ # Configuración interna (reglas, perfiles, conectores…)
├── VERSION # Versión semántica de la app (X.Y.Z)
├── CHANGELOG.md # Historial de cambios detallado
├── README.md # Información técnica específica de la herramienta
```
> 📌 Las integraciones con otras herramientas del respositorio se documentan/configuran **desde la herramienta que inicia la conexión**. Si requiere configuración en ambas, se documenta en ambas carpetas.
---
## 🧩 Aplicaciones actualmente integradas
| Aplicación | Descripción |
|------------|-------------|
|`wazuh`| SIEM y monitorización de seguridad |
|`greenbone`| Escáner de vulnerabilidades (OpenVAS)| |
|`opencti` | Plataforma de inteligencia de amenazas |
|`sonarqube` | Análisis de calidad de código fuente |

---
## 🔖 Política de versionado `X.Y.Z`
- `X` – Cambio **mayor** en la imagen base del contenedor (ej: cambio de imagen padre, reestructuración completa)
- `Y` – Cambio **menor** en la imagen base (mejoras, actualizaciones, nuevas dependencias)
- `Z` – Cambio en la **configuración funcional** (reglas, conectores, ajustes, integraciones)

> Ejemplo: `4.1.2`  
> `4` → nueva base del contenedor  
> `1` → mejoras menores en esa base  
> `2` → cambios funcionales internos
---
## ✅ Convención de commits por aplicación
Se sigue una convención clara para facilitar trazabilidad y automatización:
```scss
type(<app>): descripción
```
### Ejemplos
```scss
feat(wazuh): añadida nueva integración con Slack
fix(sonarqube): corregida configuración SAML
docs(greenbone): actualizada documentación
````
### Tipos permitidos
| Tipo | Descripción |
|------|-------------|
|`feat`|Nueva funcionalidad (base o config)|
|`fix`|Corrección de errores (configuración o imagen)|
|`chore`|Cambios sin impacto directo (estructura, metadata ...)|
|`refactor`|Reestructuración técnica (Dockerfile, estructura interna)|
|`docs`|Cambios solo en documentación|
---