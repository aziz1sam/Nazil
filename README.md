# Nazil — نازل

**Download your videos and audio directly to your Android phone.**

[Download Nazil 1.7](https://github.com/aziz1sam/Nazil/releases/tag/v1.7.0) · [All releases](https://github.com/aziz1sam/Nazil/releases) · [Report a problem](https://github.com/aziz1sam/Nazil/issues)

Nazil is an Android video and audio downloader for public YouTube, Instagram, TikTok, and other links supported by its download engine. It features an Arabic interface, four themes, actual available quality options, and a local media library. Downloads and media processing run on the phone without a dedicated Nazil server or account.

## What's new in 1.7

- Automatic download-engine checks with checksum verification, runtime validation, recovery after a failed update, and rollback to the previous engine.
- Fast Download on more devices using Android media tools for compatible MP4 video and AAC/M4A audio.
- Download **1–4 files together**, prioritize waiting requests, and set a speed limit per file, shared across its parallel connections.
- Library with local video thumbnails, original titles, duration, search, platform/media filters, sorting, and duplicate-link warnings.
- Optional **Lite** builds, about **62% smaller** on ARM64, with release resource shrinking in both variants.
- Includes the 1.6 improvements: network resume when supported, actual quality and size information, and actionable Arabic errors.

## Installation

Requires **Android 10 or later**. Choose the APK matching your device:

| Device | Full | Lite |
| --- | --- | --- |
| Most modern phones (ARM64) | [57.8 MB](https://github.com/aziz1sam/Nazil/releases/download/v1.7.0/Nazil-1.7-arm64.apk) | [22.2 MB](https://github.com/aziz1sam/Nazil/releases/download/v1.7.0/Nazil-1.7-lite-arm64.apk) |
| Compatible 32-bit phones (ARMv7) | [51.2 MB](https://github.com/aziz1sam/Nazil/releases/download/v1.7.0/Nazil-1.7-armv7.apk) | [20.7 MB](https://github.com/aziz1sam/Nazil/releases/download/v1.7.0/Nazil-1.7-lite-armv7.apk) |
| Compatible emulators/devices (x86_64) | [60.8 MB](https://github.com/aziz1sam/Nazil/releases/download/v1.7.0/Nazil-1.7-x86_64.apk) | [22.2 MB](https://github.com/aziz1sam/Nazil/releases/download/v1.7.0/Nazil-1.7-lite-x86_64.apk) |

Sizes use decimal MB. Full and Lite share the package and release signing certificate, so you can install either over the previous version without uninstalling and retain app data.

**Lite** uses Android codecs for compatible MP4 and AAC/M4A media. It does not provide general transcoding, such as Opus to AAC. **Full** retains FFmpeg for broader conversions when it can run on the device. Device codecs and source support still matter.

## How to use

1. Paste a public video link or share it to Nazil from another app.
2. Preview the available qualities and size information, then choose video or audio.
3. Optionally enable **Fast Download**: automatic selection or a maximum of **2, 4, 8, 12, 16, or 32 connections**.
4. Start downloading. View progress in notifications and completed media in **Library**.

The default folder is `Download/Nazil`; you can select another folder in Settings. Fast Download falls back to standard downloading when unsupported. Wi-Fi-only downloading, four themes, pause/resume, cancellation, and local history export remain available.

## Verification and limitations

- 33 unit tests passed; 17 distinct Android test cases passed across verification rounds. Final lint reported no errors or warnings.
- The two reported public Instagram reels and a public YouTube video downloaded with verified video/audio. Fast downloading, resume, engine update/rollback, and signed upgrade from 1.6 were also checked.
- Runtime tests used an Android 15 / API 35 x86_64 emulator with 4 KB pages. ARM64 and ARMv7 APKs were built and signature-verified, but were not newly tested on physical phones in this round. Android 10–13 and 16 KB devices were not tested in this round.
- Sites can change their behavior. Successful test links do not guarantee all links, private content, or protected media. Nazil does not include DRM bypass or site login.
- Resume requires source support. Android controls background scheduling; reopening the app may be necessary after force-stop or reboot. User-paused requests stay paused.
- Speed limits apply to newly started/resumed requests. HLS/DASH uses the normal download path when a speed cap is enabled. Reducing concurrency lets current downloads finish.
- Automatic updates update the **download engine**, not the app APK. Install a new APK release to update Nazil itself.

[Arabic update summary and verification](https://github.com/aziz1sam/Nazil/releases/tag/v1.7.0) · [Release notes](https://github.com/aziz1sam/Nazil/releases/download/v1.7.0/Release-notes-1.7.md) · [APK SHA-256 checksums](https://github.com/aziz1sam/Nazil/releases/download/v1.7.0/SHA256SUMS-1.7.txt)

## Source and building

The complete Android project is distributed as the **[Nazil-1.7-source.zip](https://github.com/aziz1sam/Nazil/releases/download/v1.7.0/Nazil-1.7-source.zip)** release asset. Use this asset for the app source; GitHub's automatically generated repository source archives contain this documentation repository.

Extract the archive and open `NazilAndroid` in Android Studio. The project uses JDK 17, Android SDK 35, Build Tools 34.0.0, and Gradle 8.9. The project README contains full build, test, licensing, and signing instructions. A development key is included; the private release signing key and local SDK configuration are excluded.

## Privacy

Nazil stores download history locally and does not send it to a dedicated analytics server. It connects to selected content platforms and the official GitHub download-engine source. History export is initiated by the user.

For feedback, include your Android version, Nazil version, the error message, and a public example link when possible. Do not include passwords or private session data.
