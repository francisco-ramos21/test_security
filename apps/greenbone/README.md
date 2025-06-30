# 🦴 Greenbone Community Edition
Este directorio contiene la configuración y despliegue de la herramienta de escaneo de volnerabilidades **Greenbone CE (GVM/OpenVAS)**, adaptada para la infraestructura de Onestic.
Se utiliza la versión **estable más reciente** de los contenedores oficiales de Greenbone, ejecutados de forma local medianta `docker-compose`.

## 📁 Estructura
```
apps/greenbone/
├── base/          # (Pendiente) Dockerfile o personalizaciones futuras
├── config/        # Archivos de configuración como docker-compose.yml
├── VERSION        # Versión lógica asignada a la configuración
├── CHANGELOG.md   # Historial de cambios
└── README.md      # Este archivo
```
## 📦 Contenedores utilizados
Se usan las imágenes oficiales de Greenbone Community Edition desde su registro:
- `registry.community.greenbone.net/community/gsa:stable`
- `registry.community.greenbone.net/community/gvmd:stable`
- `registry.community.greenbone.net/community/ospd-openvas:stable`
Estas se orquestan mediante `docker-compose` en la carpeta `config`.
