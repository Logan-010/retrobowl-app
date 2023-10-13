Retrobowl app
---
to start, i DO NOT own the rights to the retrobowl game, and i am in no way whatsoever affiliated with the team behind retrobowl.

second, there is already an app for retrobowl. Download that instead.

This is a simple project to make retrobowl compatable with my phone via the web version. But rather than simply going to a website to play it i wanted to over complicate things.

This project takes the static retrobowl page assets and loads them via Tauri.

I have only tested this with android but i guess you can build this for iOS too.

to build (windows):

```
cargo install tauri-cli --version "^2.0.0-alpha"
rustup target add aarch64-linux-android armv7-linux-androideabi i686-linux-android x86_64-linux-android
```

Install android studio,
Open Powershell:

```
[System.Environment]::SetEnvironmentVariable("JAVA_HOME", "C:\Program Files\Android\Android Studio\jbr", "User")
```

use the SDK Manager in Android Studio to install:
Android SDK Platform
Android SDK Platform-Tools
NDK (Side by side)
Android SDK Build-Tools
Android SDK Command-line Tools

Open powershell again
```
[System.Environment]::SetEnvironmentVariable("ANDROID_HOME", "$env:LocalAppData\Android\Sdk", "User")
[System.Environment]::SetEnvironmentVariable("NDK_HOME", "$env:LocalAppData\Android\Sdk\ndk\25.0.8775105", "User")
cargo tauri android init
cargo tauri android build
```