MÚSICO DIGITAL KEYS — PROYECTO ANDROID (CAPACITOR)

ESTE ZIP ES UN PROYECTO PARA GENERAR UN APK, NO ES UN APK YA COMPILADO.

REQUISITOS (Windows):
- Node.js LTS
- Android Studio con Android SDK instalado
- Java JDK compatible con Android Studio
- Conexión a Internet para descargar dependencias la primera vez

PASOS:
1. Extrae este ZIP en una carpeta sin caracteres extraños.
2. Abre PowerShell en esa carpeta.
3. Ejecuta: npm install
4. Ejecuta: npx cap add android
5. Ejecuta: npx cap sync android
6. Ejecuta: npx cap open android
7. En Android Studio: Build > Build Bundle(s) / APK(s) > Build APK(s)
8. Busca el APK de debug en android/app/build/outputs/apk/debug/app-debug.apk

PARA CAMBIAR EL HTML: edita www/index.html y ejecuta npx cap sync android antes de recompilar.

ALMACENAMIENTO:
- La app guarda archivos .mdkeys en IndexedDB del WebView de Android y los restaura al reiniciar.
- Es persistente mientras no se borren los datos de la app ni se desinstale.
- No garantiza espacio ilimitado ni recuperación tras desinstalación.
- Los archivos grandes se leen en memoria por el importador original: algunos teléfonos pueden quedarse sin memoria.
- Las descargas desde Cloudflare R2 requieren configuración CORS para el origen de la app (normalmente https://localhost).
- La URL r2.dev es para desarrollo y puede estar limitada; usar dominio propio en producción.
- Para almacenamiento de pianos enormes (>700 MB) de forma fiable y streaming de samples se necesita una siguiente versión con almacenamiento nativo y lectura parcial.
- MIDI USB en Android WebView no tiene garantizada compatibilidad; hay que probarlo y posiblemente añadir puente nativo.
- No distribuir bancos de muestras sin licencia para redistribución.

CORS R2 (ejemplo de regla; ajustar al dominio definitivo):
[ {"AllowedOrigins":["https://localhost"],"AllowedMethods":["GET","HEAD"],"AllowedHeaders":["*"],"ExposeHeaders":["Content-Length"],"MaxAgeSeconds":3600} ]

El proyecto no incluye claves secretas ni tokens.
