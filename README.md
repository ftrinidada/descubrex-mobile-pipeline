# DescubreX Mobile Pipeline

Plantillas y documentación para el pipeline de publicación de las aplicaciones DescubreX.

Este repositorio explica el proceso y conserva ejemplos reutilizables. Los workflows que se ejecutan realmente permanecen en los repositorios de cada aplicación, porque GitHub Actions solo ejecuta archivos ubicados en `.github/workflows/` del repositorio que recibe el cambio.

## Rutas de los pipelines activos

| Plataforma | Repositorio de la aplicación | Workflow de CI | Workflow de release |
| --- | --- | --- | --- |
| Android | [ftrinidada/descubreX-android](https://github.com/ftrinidada/descubreX-android) | `.github/workflows/ci.yml` | `.github/workflows/release.yml` |
| iOS | [ftrinidada/descubreX](https://github.com/ftrinidada/descubreX) | `.github/workflows/ci.yml` | `.github/workflows/release.yml` |

Los archivos bajo `templates/` son copias genéricas de referencia: cambiarlos no publica ni altera una app.

## Qué contiene

- `templates/android/`: CI y release para construir un AAB y subirlo a Google Play.
- `templates/ios/`: CI y release para compilar, firmar y subir un IPA a TestFlight.
- `docs/`: arquitectura, rutas activas y checklist de configuración.

## Seguridad

Este repositorio no debe contener keystores, `.p12`, `.mobileprovision`, llaves `.p8`, archivos JSON de cuentas de servicio, contraseñas ni valores de secretos. Los workflows usan nombres de secretos de GitHub Actions, nunca valores reales.

Lee [la arquitectura y operación](docs/architecture.md) antes de copiar una plantilla.
