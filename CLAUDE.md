# SimpleNavigation — Claude Code Guide

## Project Overview
Single-module Android app using Jetpack Compose + Material 3. Currently a starter template (displays "Hello Android!"), intended to grow into a navigation demo.

- **Package:** `com.sergey1988r.simplenavigation`
- **Min SDK:** 26 (Android 8.0)
- **Compile/Target SDK:** 36
- **Language:** Kotlin 2.0.21
- **UI:** Jetpack Compose with Material Design 3

## Build Commands

```bash
# Build debug APK
./gradlew assembleDebug

# Run unit tests
./gradlew test

# Run instrumented tests (requires device/emulator)
./gradlew connectedAndroidTest

# Check for lint issues
./gradlew lint

# Clean build
./gradlew clean
```

## Project Structure

```
app/src/main/
├── java/com/sergey1988r/simplenavigation/
│   ├── MainActivity.kt          # Entry point, Compose host
│   └── ui/theme/
│       ├── Theme.kt             # Material 3 theme, dynamic color
│       ├── Color.kt             # Color palette (light/dark)
│       └── Type.kt              # Typography
├── AndroidManifest.xml
└── res/
    └── values/
        ├── strings.xml
        ├── colors.xml
        └── themes.xml
```

## Key Conventions

- **No XML layouts** — UI is 100% Jetpack Compose
- **Dependency versions** managed via `gradle/libs.versions.toml` (version catalog) — add new deps there, not inline in build files
- **Single activity** architecture — new screens are Composables, not Activities
- **Material 3** — use `MaterialTheme` tokens, not hardcoded colors or dimensions
- **Edge-to-edge** display is enabled — account for window insets in new screens
