# Kazhutha Android App

This project wraps the production Kazhutha HTML game in a native Android WebView shell while keeping the game UI itself in HTML/CSS/JavaScript.

## App behavior

- Landscape-only gameplay (`sensorLandscape`)
- Full-screen immersive mode
- Local bundled HTML frontend
- Multiplayer API fixed to `https://kazhutha-online.onrender.com/api/game`
- JavaScript, DOM storage, WebGL/hardware acceleration, and audio enabled
- File-to-HTTPS access enabled so the bundled frontend can reach the Render backend
- External web links open in the phone browser; Kazhutha's own hosted links can remain in-app
- Kazhutha launcher icon included
- Android 12+ splash screen uses the Kazhutha icon
- Minimum Android version: Android 7.0 (API 24)

## Build the APK with GitHub Actions

Push the entire project to a GitHub repository. The included workflow `.github/workflows/build-apk.yml` automatically builds an installable debug APK. It can also be started manually from **Actions → Build Kazhutha APK → Run workflow**.

The downloadable artifact is named **Kazhutha-APK**, containing `Kazhutha.apk`.

## Build locally in Android Studio

Open this directory as an Android project, let Gradle sync, and use **Build → Build APK(s)**.

## Important server note

The Android app contains the frontend, but multiplayer remains server-authoritative on Render. The Render deployment must therefore be running the production `server.mjs`/`dist` package.
