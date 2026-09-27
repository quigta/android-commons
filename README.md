# 🚀 quigta / android-commons

Shared parent Gradle build script for modern Android applications built with Jetpack Compose & Kotlin.

---

## 🛠️ Usage in Any New Android App

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

## 📜 License
MIT License
