# apkrecepcion

App Android (WebView modo kiosk) para cargar **https://convenios.bata.cl/recepcion/** a pantalla completa, sin navegación ni zoom.

## Estructura
- `app/src/main/java/com/bata/convenioskiosk/MainActivity.kt` → WebView bloqueado al dominio convenios.bata.cl
- `app/src/main/AndroidManifest.xml` → Permiso de Internet, actividad en pantalla completa
- `.github/workflows/build.yml` → Workflow para compilar y publicar APK como artefacto

## Cómo usar con GitHub Actions
1. Crea un repositorio vacío en tu GitHub llamado **apkrecepcion**.
2. En tu computador:
   ```bash
   git clone https://github.com/<tu-usuario>/apkrecepcion.git
   cd apkrecepcion
   # Copia el contenido de este proyecto dentro de esta carpeta (o descomprime el ZIP aquí)
   git add .
   git commit -m "init: proyecto Android + workflow"
   git push origin main
   ```
3. Ve a **Actions** en GitHub → ejecuta **Build APK** (o haz un push a `main`).
4. Al terminar, descarga **app-debug.apk** desde **Artifacts**.

## Build local (Android Studio)
- `Build → Build APK(s)` → `app/build/outputs/apk/debug/app-debug.apk`

## Notas
- La app desactiva zoom, navegación fuera del dominio, botón atrás y usa modo inmersivo.
- Si quieres un APK de **release** firmado: `Build → Generate Signed Bundle / APK…` y usa tu keystore.
