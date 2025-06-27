# 🐬 SonarQube

Este directorio contiene la configuración, personalización y despliegue automatizado de SonarQube como parte de la infraestructura de seguridad.

Se utiliza la Developer Edition de SonarQube y se construye una imagen personalizada con plugins adicionales. Todo el proceso de contrucción y despliegue se gestiona mediante GitHub Actions y un runner local.

## 🧱 Estructura
```
apps/sonarqube/
├── base/          # Dockerfile e imagen base personalizada con plugins
├── config/        # Configuración adicional si se requiere (actualmente vacía)
├── VERSION        # Versión actual de la herramienta gestionada
├── CHANGELOG.md   # Historial de cambios (semver)
└── README.md      # Este archivo
```

## 🐳 Imagen Docker personalizada
Se construye una imagen basada en la edición Developer de SonarQube y se añaden los plugin deseados en la carpeta:
```swift
apps/sonarqube/base/plugins
```

Los `.jar` que se ubiquen en esa ruta se copiarán automáticamente a `/opt/sonarqube/extensions/plugin` durante la build.

## 🚀 Despliegue automático
El despliegue se realiza mediante un workflow de GitHub Actions localizado en `.github/workflows`.
Este workflow:
1. Valida la configuración YAML del `config/`.
2. Construye la imagen con `docker buildx`.
3. Inspecciona el contenido del contenedor.
4. Permite cargar la imagen resultante en el runner local.
5. Sube un artifact de la imagen construida.

El despliegue en sí requiere intervención manual (para ser lanzado desde el runner local, que se activará previamente).

## 🔌 Plugins 
- Creedengo
    - `creedengo-php`
    - `creedengo-python`
- OWASP Dependecy-Check Plugin for Sonar.

## 🔁 Versionado
La versión de la solución personalizada se mantiene en el archivo `VERSION`siguientdo (X.Y.Z). Este valor puede usarse como tag para el contenedor si se desea extender el flujo de CI/CD.
---
