# SafeTrack Kids - Android Parental Control App
**100% Free, AirDroid-Style Architecture, Kotlin + Jetpack Compose**

This project is a complete, production-ready Android Studio application designed for family child safety, screen time management, battery/storage diagnostics, and parent-child device pairing.

---

## 🚀 Quick Start in Android Studio

1. **Unzip this archive** to a folder on your computer (e.g. `~/AndroidStudioProjects/SafeTrackKids`).
2. **Open Android Studio** (Ladybug, Koala, Iguana, or later).
3. Click **Open** (or File > Open...) and choose the unzipped `SafeTrackKids` folder.
4. Wait for Gradle Sync to finish (~1-2 minutes).
5. **Firebase Setup**:
   - Go to [Firebase Console](https://console.firebase.google.com) and create a free project under the **Spark ($0/mo)** plan.
   - Add an Android App with package name: `com.safetrack.kids`.
   - Download `google-services.json` and place it into the `app/` folder (replacing the placeholder).
   - In Firestore Database, deploy the rules found in `firestore.rules`.

---

## 📱 How to Install on a Real Android Phone

### Method A: Direct USB Cable (Fastest)
1. On your phone: **Settings > About Phone > Tap "Build Number" 7 times** to unlock Developer Options.
2. In **Settings > System > Developer Options**, turn on **USB Debugging**.
3. Plug the phone into your computer with a USB cable. Tap **"Allow USB Debugging"** on the phone screen.
4. In Android Studio, select your phone in the device dropdown toolbar.
5. Click the green **Run** button (or press `Shift + F10`). The app compiles and opens on your phone!

### Method B: Wireless Wi-Fi Debugging (No Cable Required)
1. Ensure both your computer and Android phone (Android 11+) are on the same Wi-Fi.
2. In Android Studio device dropdown, choose **"Pair Devices Using Wi-Fi"**.
3. On your phone: **Settings > Developer Options > Wireless Debugging > Pair device with QR code**.
4. Scan the QR code shown on your computer screen. Once paired, click Run!

### Method C: Build Standalone APK (To send to another device)
Run in terminal:
```bash
./gradlew assembleDebug
```
The APK will be generated at:
`app/build/outputs/apk/debug/app-debug.apk`
Transfer this file to any phone via Google Drive, WhatsApp, or Telegram, open it, and tap **Install**!

---

## 📦 How to Build the Final App to Deploy (Play Store / Release)

### 1. Generate a Production Keystore
```bash
keytool -genkeypair -v -keystore safetrack-release.jks -alias safetrack-release -keyalg RSA -keysize 2048 -validity 10000
```

### 2. Build Signed Release App Bundle (.aab) for Google Play
```bash
./gradlew bundleRelease
```
The bundle file is created at:
`app/build/outputs/bundle/release/app-release.aab`

### 3. Build Signed Release APK (.apk) for Direct Distribution
```bash
./gradlew assembleRelease
```
The APK file is created at:
`app/build/outputs/apk/release/app-release.apk`

### 4. Deploy to Google Play Store (Internal Testing - Instant 5-Minute Install)
1. Go to [Google Play Console](https://play.google.com/console).
2. Go to **Release > Testing > Internal testing**.
3. Upload `app-release.aab`.
4. Add your email address and family emails under the **Testers** tab.
5. Copy the **Join on Android** link and open it on the phone to install directly through the official Google Play Store!
