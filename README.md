# 🚀 quigta / android-commons

A centralized suite of shared Gradle build scripts, Android libraries, and UI design kits for building modern, high-performance Android applications with **Jetpack Compose** and **Kotlin**.

---

## 🛠️ 1. Shared Parent Build Script (`common-build.gradle`)

Standardize Android SDK, Java compatibility, Kotlin toolchain, and Jetpack Compose dependencies across all your Android projects with a single line of code!

### **How to Use in Any New Android App:**

In your app's `app/build.gradle.kts`:

```kotlin
plugins {
    alias(libs.plugins.android.application)
    alias(libs.plugins.kotlin.compose)
    alias(libs.plugins.ksp)
}

// Apply shared build logic directly from GitHub!
apply(from = "https://raw.githubusercontent.com/quigta/android-commons/main/common-build.gradle")

android {
    namespace = "com.quigta.yournewapp"
    defaultConfig {
        applicationId = "com.quigta.yournewapp"
        targetSdk = 37
        versionCode = 1
        versionName = "1.0"
    }
}
```

---

## 🔄 2. Force App Update System (`sampoornaSanskritiVersion.json`)

The commons repo hosts a remote version control file (`sampoornaSanskritiVersion.json`) used to enforce mandatory force updates across your apps.

### **File Format (`sampoornaSanskritiVersion.json`):**
```json
{
  "minRequiredVersionCode": 1,
  "latestVersionCode": 1,
  "latestVersionName": "v1.0",
  "releaseNotes": "Official release with accurate calculations and bug fixes.",
  "updateUrl": "https://github.com/quigta/sampoorna-sanskriti"
}
```

### **How to Force an Update:**
When you release a breaking or required update:
1. Increase `versionCode` in your app's `build.gradle.kts`.
2. Update **`minRequiredVersionCode`** in `sampoornaSanskritiVersion.json` on GitHub to match or exceed the new version.
3. Any user running an older version code will automatically be blocked by the un-dismissable `ForceUpdateScreen`.

---

## 📜 License
MIT License - free to use in personal, open-source, and commercial projects.
