# 🛡️ Security Infrastructure
Este repositorio centraliza la gestión, configuración, despliegue y automatización de las herramientas de seguridad utilizadas por Onestic.

Su propósito es servir como punto único de referencia para el mantenimiento de todas las herramientas, facilitando el control de versiones, la integración entre servicios y la estandarización de entornos, todo orquestado mediante pipelines CI/CD.

---
## 📁 Estructura General

```bash
.
├── apps/                 # Herramientas de seguridad (una carpeta por herramienta)
├── containers/           # Imágenes base personalizadas (Dockerfiles con hardening y ajustes internos)
├── .github/workflows/    # Workflows de GitHub Actions para CI/CD
└── README.md             # Este archivo
```

## 🚀 Objetivos Principales
- **Centralización:** Todo el código, configuración, y lógica de despliegue de herramientas de seguridad en único punto.
- **Automatización:** Validaciones, pruebas, construcción de imagenes y despliegues completamente automatizados mediante GitHub Actions.
- **Estandarización:** Uso de imágenes base personalizadas, patrones comunes de configruación y convenciones compartidas entre herramientas.
- **Integraciones aisladas:** Cada integración entre herramientas se define desde la que inicia la conexión, y en ambos extremos si es necesario, siempre dentro de la carpeta correspondiente.
---
## 🔁 Versionado
Cada herramienta gestiona su propio versionado local en el archivo `VERSION` :
```textplain
MAJOR.MINOR.PATCH
````
> Ejemplo: `2025.3.0` indica que se utiliza la versión personalizada de una imagen.
---
## ⚙️ CI/CD
Los workflows de CI/CD están definidos en `.github/workflows/` y se encargan de:
- Validación de sintaxis y estructura de carpetas.
- Construcción y publicación de imágenes personalizadas.
- Despliegue automático de herramientas (cuando aplique)
- Instalación de plugins o configuraciones post-deploy

> **Nota:** Durante la fase de desarrollo inicial, estos workflows pueden fallar o estar incompletos. Se recomienda desactivar temporalmente las notificaciones por correo.
---
Para más información, consulta los `README`específicos.