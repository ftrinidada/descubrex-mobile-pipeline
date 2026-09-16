# Arquitectura y operación

## Separación de responsabilidades

```text
descubreX-android/.github/workflows/  -> ejecuta CI y Google Play para Android
descubreX/.github/workflows/          -> ejecuta CI y TestFlight para iOS
descubrex-mobile-pipeline/            -> documentación y plantillas; no ejecuta releases de las apps
```

Cada aplicación conserva su workflow activo en su propio repositorio. El repositorio de plantillas sirve para aprender, revisar cambios y reutilizar una base segura sin mezclar secretos.

## Flujo de un release

1. Se actualiza la versión y build number dentro del repositorio de la app.
2. CI compila y valida el cambio.
3. Un tag `vX.Y.Z` o una ejecución manual inicia el workflow de release.
4. GitHub Actions recupera secretos del environment correspondiente, firma el artefacto y lo sube a pruebas.
5. La publicación en producción requiere una aprobación explícita y una revisión en la consola de la tienda.

## Entornos de GitHub

Android usa `internal-testing` para pruebas y `production` para la entrega final. iOS usa `testflight` y `production`. Los secretos se configuran en el repositorio de cada aplicación, no aquí.

## Actualizar una plantilla

Cuando se cambie un workflow real, replica el cambio de forma genérica en `templates/`, elimina nombres propios, IDs de paquete y rutas particulares, y explica el motivo en el commit. Nunca copies valores de secretos ni archivos de firma.
