# Bicara Installers

Public download channel for Bicara client apps.

> **Looking for the production app?**
> - Android Owner / Team → install from the Play Store *(coming soon)*
> - iOS → App Store *(coming soon)*
> - Windows POS → see [latest release](../../releases/latest) below
>
> Pre-release builds in this repo (tags ending in `-dev.N`) point at the **demo backend** (`*.demo.bicara.ai`) and are intended for internal testing.

## Apps

| App | Platform | Where to install |
|---|---|---|
| Bicara POS | Windows | This repo (`pos-v*` releases) |
| Bicara Owner | Android | Play Store *(prod, coming soon)* / this repo `owner-android-v*-dev.*` *(test)* |
| Bicara Team | Android | Play Store *(prod, coming soon)* / this repo `team-android-v*-dev.*` *(test)* |
| Bicara Owner | iOS | App Store *(coming soon)* |
| Bicara Team | iOS | App Store *(coming soon)* |

## Release channels

Tags follow `<app>-v<semver>`. The semver tells you the channel:

| Channel | Version shape | Backend | GitHub label |
|---|---|---|---|
| Prod | `1.2.3` | `*.bicara.ai` | full release |
| Dev | `1.2.3-dev.N` | `*.demo.bicara.ai` | **Pre-release** |

Examples:

- `pos-v0.1.0` → `Bicara-POS-Setup-0.1.0.exe` — POS, prod backend
- `pos-v0.1.0-dev.1` → `Bicara-POS-Demo-Setup-0.1.0-dev.1.exe` — POS, demo backend
- `owner-android-v1.0.0-dev.1` → `bicara-owner-1.0.0-dev.1.apk` — Owner Android, demo backend
- `team-android-v1.0.0-dev.1` → `bicara-team-1.0.0-dev.1.apk` — Team Android, demo backend

Android prod APKs are not posted here — install the prod app from Play Store when available.

## Installation

### Windows POS

1. Download `Bicara-POS-Setup-<version>.exe` (prod) or `Bicara-POS-Demo-Setup-<version>.exe` (dev) from a release.
2. Run the installer. Windows SmartScreen will warn — click **More info** → **Run anyway** (the installer is unsigned NSIS).
3. Both prod and demo installers can coexist on the same machine (different appIds).

### Android (test channel)

1. On your Android phone, enable **Install from unknown sources** for your browser or file manager (Settings → Apps → \[browser\] → Install unknown apps).
2. Download `bicara-owner-<version>.apk` or `bicara-team-<version>.apk` from a matching pre-release.
3. Open the APK and install.

The dev APK uses package id `ai.bicara.owner.dev` / `ai.bicara.team.dev`, so it installs alongside the future Play Store version (`ai.bicara.owner` / `ai.bicara.team`) without conflict.

## Updating

There is no auto-update.

- **POS Windows:** download the new installer and run it; NSIS will replace the existing install.
- **Android:** download the new APK and tap install; Android will upgrade in place as long as the package id matches.

## Verifying which channel you have

- **POS:** Settings → About shows the loaded URL. `pos.bicara.ai` = prod; `pos.demo.bicara.ai` = dev.
- **Android:** Settings → Apps → Bicara Owner / Team → package name. `ai.bicara.owner` / `ai.bicara.team` = Play Store prod; suffix `.dev` = GitHub dev build.

## Reporting installer issues

File an issue here only for installation problems (download fails, installer errors, signature warnings). For app behavior issues, contact the Bicara team directly.
