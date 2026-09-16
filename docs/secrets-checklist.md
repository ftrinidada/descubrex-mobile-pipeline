# Checklist de secretos

Configura estos valores como **Environment secrets** en el repositorio de la aplicación correspondiente. No los agregues a este repositorio ni al chat.

## Android

- `ANDROID_KEYSTORE_B64`
- `ANDROID_KEYSTORE_PASSWORD`
- `ANDROID_KEY_ALIAS`
- `ANDROID_KEY_PASSWORD`
- `PLAY_SERVICE_ACCOUNT_JSON`
- Variables de backend requeridas por el build, por ejemplo `SUPABASE_URL` y `SUPABASE_ANON_KEY`

## iOS

- `ASC_KEY_ID`
- `ASC_ISSUER_ID`
- `ASC_KEY_B64`
- `IOS_TEAM_ID`
- `IOS_DISTRIBUTION_CERTIFICATE_B64`
- `IOS_DISTRIBUTION_CERTIFICATE_PASSWORD`
- `IOS_PROVISIONING_PROFILE_B64`

Antes de un release, confirma que el environment correcto tiene todos los secretos, que el certificado y perfil siguen vigentes, y que el build number no se ha usado antes.
