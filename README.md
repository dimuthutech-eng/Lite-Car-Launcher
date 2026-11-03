# Lite Car Launcher v1.0 — Android Studio project

This is **source code, not a compiled APK**. Android SDK/Gradle are required to build it.

## Build an APK
1. Open this folder in Android Studio (JDK 17, Android SDK 35).
2. Allow Gradle to sync and install requested SDK components.
3. Select **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
4. Find `app/build/outputs/apk/debug/app-debug.apk`.
5. Transfer the APK to the Android car head unit and install it.
6. Select Lite Car Launcher as the Home app if the device supports changing the default launcher.

## Notes
- Android 6.0+ target, landscape only. Device-specific car radio/Bluetooth apps may need custom package mappings.
- No internet permission, ads, analytics or background services.
- Some OEM head units lock their launcher; installation or Home selection may be blocked.
- This is an untested prototype. Do not operate the touchscreen while driving.
- QUERY_ALL_PACKAGES is used to list installed apps; Play Store distribution would require policy review.

## Build online with GitHub Actions (no Android Studio required)
1. Create a new GitHub repository, e.g. `LiteCarLauncher`.
2. Upload **the contents inside** this `LiteCarLauncher` folder to the repository root, including the hidden `.github/workflows/build-apk.yml` file. The easiest method is to extract the ZIP, then use Git to commit and push the entire folder contents. GitHub's web uploader may omit hidden files depending on how they are selected.
3. Open the repository's **Actions** tab and choose **Build Lite Car Launcher APK**.
4. Select **Run workflow** and wait for the build to finish.
5. Open the successful run and download the **LiteCarLauncher-debug-APK** artifact.
6. Unzip that artifact to get `app-debug.apk`, then copy it to the Android car player.

The APK is debug-signed for personal testing, not a production Play Store release. GitHub Actions builds require a GitHub account and Actions access. The build has not yet been verified on GitHub or on a car player.
