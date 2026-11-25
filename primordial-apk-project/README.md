# Primordial: APK project

This wraps the game (www/index.html) in an Android app using Capacitor.
You can build the APK in the cloud (easiest) or on your own computer.

## Option A: build in the cloud with GitHub (no installs)
1. Create a free GitHub account and a new empty repository.
2. Upload everything in this folder to it (keep the .github folder).
3. Open the repository's Actions tab. The "Build APK" workflow runs
   automatically (or press "Run workflow").
4. When it finishes (about 3 to 5 minutes), open the run and download
   the artifact "primordial-apk". Unzip it to get app-debug.apk.

## Option B: build on your own computer
Requirements: Node.js 18 or newer, Java 17, and Android Studio (for the Android SDK).
    npm install
    npx cap add android
    npx cap sync android
    cd android
    ./gradlew assembleDebug        (on Windows: gradlew.bat assembleDebug)
The APK is at android/app/build/outputs/apk/debug/app-debug.apk.
Or run "npx cap open android" and use Build > Build APK(s) in Android Studio.

## Installing on your phone
Copy app-debug.apk to your phone, open it, and allow "install unknown apps"
when Android asks. This is a debug-signed APK, fine for personal use but not
for the Play Store (that needs a release build signed with your own key).

## Updating the game
Replace www/index.html with a new version and build again.
Note: the game loads one Google Font online; offline it falls back to the system font.
