FOOTBALL STATS - APLICACIÓN ANDROID NATIVA
==========================================

Este proyecto es una aplicación Android nativa hecha en Kotlin.
No necesita abrir la página web ni GitHub Pages. Lee los datos directamente
desde Firebase Realtime Database.

DATOS QUE MUESTRA
- Fuerza en vivo: campo "lectura"
- Último remate: campo "ultimoPico"
- Récord de sesión: campo "recordSesion"
- Cantidad de remates: campo "numeroGolpe"
- Estado: campo "estado"

REQUISITOS
- Una computadora con Android Studio instalado.
- Conexión a Internet para descargar los componentes de Gradle/Android.
- Un teléfono Android para instalar y probar el APK.

CÓMO GENERAR EL APK
1. Descomprimí FootballStatsAndroid.zip.
2. Abrí Android Studio.
3. Elegí "Open" y seleccioná la carpeta FootballStatsAndroid
   (la carpeta que contiene settings.gradle.kts).
4. Esperá a que termine "Gradle Sync".
5. Conectá el teléfono Android por USB o activá las opciones de desarrollador.
   También podés generar el APK sin conectar el teléfono.
6. En Android Studio elegí Build > Build Bundle(s) / APK(s) > Build APK(s).
7. Cuando termine, tocá "locate" en la notificación.
   El archivo suele quedar en:
   app/build/outputs/apk/debug/app-debug.apk
8. Pasá ese APK al teléfono, abrilo y aceptá instalar desde esa fuente
   si Android lo solicita.

FIREBASE
URL utilizada:
https://medidor-de-fuerza-2026-default-rtdb.firebaseio.com/medidor.json

La app realiza lecturas automáticas cada 1 segundo. El ESP8266 debe seguir
enviando los campos indicados arriba. Si aparece "Sin conexión con Firebase",
revisá que la base permita lectura y que el ESP8266 esté actualizando /medidor.

IMPORTANTE
- Esta versión es una app nativa de consulta: muestra los datos, no modifica
  ni calibra el ESP8266.
- No incluye autenticación. Para un prototipo escolar puede funcionar con
  reglas de lectura públicas, pero no conviene dejar la base abierta en un
  proyecto de uso real. Configurá reglas seguras antes de publicar la app.
- El APK de depuración es para instalar y probar. Para distribuir ampliamente
  se debe generar una versión firmada desde Android Studio.


COMPILACIÓN AUTOMÁTICA CON GITHUB ACTIONS
=========================================
El proyecto incluye .github/workflows/android-apk.yml.
Subí el contenido del proyecto Android al repositorio GitHub (en la raíz,
junto a los archivos de la página web). Al hacer push a la rama main,
GitHub Actions compilará el APK. También podés iniciarlo manualmente desde
la pestaña Actions > Build Football Stats APK > Run workflow.

Cuando termine correctamente:
1. Abrí la ejecución más reciente.
2. Bajá hasta Artifacts.
3. Descargá Football-Stats-APK.zip.
4. Descomprimí el ZIP y abrí app-debug.apk en tu Android.
