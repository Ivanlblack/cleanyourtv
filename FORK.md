# Hartens quiet-header fork

A small, tested restyle of the CleanYourTV launcher for a 1080p Hartens HTY-43F11B-VS running Android 11 with 1 GB of RAM.

![Home on the Hartens HTY-43F11B-VS](docs/fork/hartens-home.jpg)

## What changes

- Greeting and two-line date use normal case, Outfit Regular and tighter spacing.
- Greeting is 16sp; the date is 18sp with no added line gap.
- The clock/date divider is vertically centred.
- The cinematic shelf omits the “Last opened” metadata and keeps the position dots directly below the app title.
- The top button row has equal 56dp top and right insets at 1920×1080.
- Everything else stays on the upstream CleanYourTV launcher.

The launcher remains offline and adds no permissions, dependencies, services or background work.

## Tested on

- TV: Hartens HTY-43F11B-VS
- Android: 11
- Display: 1920×1080, density 320 dpi
- Memory: 1 GB
- Launcher package: `com.gathin.tvhome`
- Base: upstream CleanYourTV main at `294d3d59dc2514e69fed557f46c1ecdfb87a95ec`
- Runtime check: default Home retained, no launcher crashes, about 49 MB total PSS

## Build

Use the upstream launcher build:

```sh
cd launcher
JAVA_HOME=/path/to/jdk-17 ANDROID_HOME=/path/to/android-sdk \
  ./gradlew --no-daemon testReleaseUnitTest lintRelease assembleRelease
```

Install over an existing build signed with the same debug key:

```sh
adb install -r launcher/app/build/outputs/apk/release/app-release.apk
```

The fork publishes source only. No prebuilt APK is committed.

