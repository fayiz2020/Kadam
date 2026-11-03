# Kadam Android APK project

This project packages the existing Kadam expense tracker HTML app as an Android application using Capacitor. The original application logic and features are retained; a mobile WebView enhancement stylesheet improves touch targets, safe-area handling, navigation spacing, and small-screen layout.

## Build the APK with GitHub Actions

1. Create a GitHub repository (for example, `kadam-android`).
2. Upload **all files and folders in this project** to the repository root. Make sure `.github/workflows/build-apk.yml` is included; GitHub requires the folder name to be exactly `.github`.
3. Open the repository's **Actions** tab and allow workflows if GitHub asks.
4. Select **Build Kadam Android APK** → **Run workflow**. A push to `main` or `master` also starts a build.
5. When the run finishes successfully, open the run and download **Kadam-debug-apk** under Artifacts.
6. Extract the downloaded ZIP and install `app-debug.apk` on your Android phone. Android may ask you to allow installation from that source.

## Data and feature notes

- Expense records continue to use the app's local browser storage (`localStorage`) inside the app's private WebView data area. They are stored on that device, not automatically synchronized to Chrome or another phone.
- Keep using **Settings → Backup (.json)** regularly. You can import a backup on the Android app or another device.
- jsPDF and AutoTable are bundled locally by the workflow, so PDF generation does not depend on a CDN being reachable.
- The original app's image/PDF bill attachments and JSON backup/import controls remain in the HTML app. Test selecting and opening files on your target Android device after installing.
- This workflow creates a **debug APK** for direct testing/installation, not a Play Store release-signed APK.

## Project structure

```text
.
├── .github/workflows/build-apk.yml
├── www/index.html
├── package.json
├── capacitor.config.json
└── README.md
```
