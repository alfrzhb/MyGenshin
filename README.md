# MyGenshin — Android Learning Project (Incomplete Repository)

An Android Studio / Gradle project originally labeled as a submission for **Dicoding — Belajar Membuat Aplikasi Android untuk Pemula**.

The repository name suggests a Genshin-related Android application, but the checked-in files on the default branch do **not** contain the application module or its source code. This README documents **what is actually available**, rather than claiming screens or features that cannot be verified.

> **Status: incomplete source snapshot / not buildable as checked in.** The default `main` branch contains Gradle project configuration and launch scripts, but no `app/` module, `gradle/` wrapper directory, or `gradle/libs.versions.toml` version catalog. The earlier README described UI, navigation, user input, and lifecycle features without implementation evidence in the repository.

## What is currently present?

| Path | Purpose | Status |
| --- | --- | --- |
| `settings.gradle.kts` | Repository configuration and the declaration `include(":app")` | Present |
| `build.gradle.kts` | Android and Kotlin plugin aliases (`libs.plugins...`) | Present |
| `gradle.properties` | Project-wide Gradle properties | Present |
| `gradlew` and `gradlew.bat` | Gradle launcher scripts | Present |
| `.gitignore` | Local/IDE/build-file exclusions | Present |
| `local.properties` | Machine-specific local SDK configuration | **Tracked; should normally be local-only** |
| `app/` | Android application source, manifest, resources and module build file | **Missing** |
| `gradle/libs.versions.toml` | Version catalog defining the plugin aliases | **Missing** |
| `gradle/wrapper/` | Gradle wrapper JAR/properties required by wrapper scripts | **Missing** |

The missing files mean this repository **cannot currently be presented as a reproducible Android application**.

## Intended project context

This appears to be an early Android learning/submission repository. A complete application of this type would normally include an Android manifest, Kotlin or Java activity classes, Gradle module configuration, and resources.

Those are **requirements for a complete project**, not features verified in the current code. The repository does not provide enough evidence to describe specific screens, character listings, navigation patterns, or functionality.

## How to restore a buildable repository

If the original Android Studio project is still available on a local device or backup:

1. Recover the full `app/` directory, including `app/build.gradle.kts`, `src/main/AndroidManifest.xml`, Kotlin/Java source files and any resources.
2. Restore `gradle/wrapper/gradle-wrapper.properties` and the associated wrapper JAR from the same trusted project/build setup.
3. Restore `gradle/libs.versions.toml` (or replace aliases with explicit Gradle plugin versions in a deliberate build migration).
4. Verify the Android Gradle Plugin, Kotlin, SDK, and Gradle versions are compatible.
5. Keep `local.properties` and any local secrets out of version control; review the currently tracked file and remove it from Git tracking if appropriate. Do not copy another developer's SDK path.
6. Run Gradle sync and build through Android Studio, then test the application on an emulator or device.
7. After a successful build, update this README with features and screenshots supported by the restored code.

### Verification commands after restoration

Only **after** the missing module, catalog, and wrapper have been recovered:

~~~bash
# macOS/Linux
./gradlew :app:assembleDebug

# Windows PowerShell
.\gradlew.bat :app:assembleDebug
~~~

These commands are provided as future checks, **not as steps that currently work** on this incomplete checkout.

## Repository structure (current)

~~~text
MyGenshin/
├── .gitignore
├── README.md
├── build.gradle.kts
├── gradle.properties
├── gradlew
├── gradlew.bat
├── local.properties         # Tracked local configuration — review!
└── settings.gradle.kts      # Declares :app, which is not present
~~~

## Limitations

- No Android screens, assets, app logic or APK are available to inspect.
- There is no demonstrated working build, test suite or release artifact in the checked-in default branch.
- Prior descriptions of features, navigation, and UI behavior were speculative and have been removed.
- **Do not publish machine-local paths, API keys, keystore files or private configuration.** Audit files already committed and the Git history before making this repository public or reusing its contents.

## Related Android projects

For examples of Android applications with source code and documented functionality, see:

- [DiceRoller](https://github.com/alfrzhb/DiceRoller) — Kotlin / Jetpack Compose dice app
- [StoryApp](https://github.com/alfrzhb/StoryApp) — Kotlin Android story-sharing app
- [Asclepius](https://github.com/alfrzhb/Asclepius) — on-device TensorFlow Lite image classification demonstration

---

**Documentation principle:** only claim an implemented feature after its source and build path are available for verification.