# Nazil — نازل

**Download videos and audio directly to your Android phone.**

[Download Nazil 1.9](https://github.com/aziz1sam/Nazil/releases/tag/v1.9.0) · [All releases](https://github.com/aziz1sam/Nazil/releases) · [Report a problem](https://github.com/aziz1sam/Nazil/issues)

Nazil is an Android video and audio downloader for public YouTube, Instagram, TikTok, and other links supported by its download engine. It has an Arabic interface, four themes, actual available quality options, and a local media library. Downloads and media processing run on the phone without a dedicated Nazil server or account.

## What's new in 1.9

- **Batch links:** paste or share up to 50 public links, preview each source, choose the files and audio/video quality, then add the selected items to the queue. Equivalent links are deduplicated; existing requests and unavailable qualities are skipped. Failures are shown per link.
- **File management:** rename the actual saved file while keeping its extension; select up to 100 files to share or delete, confirm deletion, and check the space used by available library files. Failed deletions keep their history records.
- **Optional backup:** export settings and history to JSON, validate an import, then review and confirm restore. Imported entries remain historical records and do not start downloads. Media files, temporary parts and folder permissions are not copied. The backup contains history URLs; choose a trusted destination.
- **Problem report:** review and edit version, device, engine and readable error information before sharing. Download URLs, titles, raw errors and history are excluded from the generated report. Nothing is sent automatically.
- **Incomplete source responses:** bounded retry for truncated HTTP responses during preview or download, respecting pause, cancellation and network-wait states.

This release also includes the **1.8 improvements**, which were not published as a separate release:

- **App updates from GitHub:** check for a newer stable release, show its changes, select the device architecture and Full/Lite variant, and verify APK size, checksum, package, version and signing certificate before opening Android's installer. Android asks the user to approve installation.
- **Storage preflight:** check the output folder and available space before downloading, including estimated temporary space for merging.
- **Detailed progress:** downloaded bytes, current speed, estimated remaining time, actual connections and the merge/audio preparation stage.

## Installation

Requires **Android 10 or later**. Choose the APK matching your device:

| Device | Full | Lite |
| --- | --- | --- |
| Most modern phones (ARM64) | [58.0 MB](https://github.com/aziz1sam/Nazil/releases/download/v1.9.0/Nazil-1.9-arm64.apk) | [22.3 MB](https://github.com/aziz1sam/Nazil/releases/download/v1.9.0/Nazil-1.9-lite-arm64.apk) |
| Compatible 32-bit phones (ARMv7) | [51.3 MB](https://github.com/aziz1sam/Nazil/releases/download/v1.9.0/Nazil-1.9-armv7.apk) | [20.8 MB](https://github.com/aziz1sam/Nazil/releases/download/v1.9.0/Nazil-1.9-lite-armv7.apk) |
| Compatible emulators/devices (x86_64) | [61.0 MB](https://github.com/aziz1sam/Nazil/releases/download/v1.9.0/Nazil-1.9-x86_64.apk) | [22.3 MB](https://github.com/aziz1sam/Nazil/releases/download/v1.9.0/Nazil-1.9-lite-x86_64.apk) |

Sizes use decimal MB. Full and Lite share the package and release signing certificate. Install over the previous version without uninstalling to retain app data. **From 1.7 or older, install the new APK manually once**; 1.8 and newer include the app updater under Settings.

**Lite** uses Android codecs for compatible MP4 and AAC/M4A media and is about **62% smaller** on ARM64. It does not provide general transcoding such as Opus to AAC. **Full** retains FFmpeg for broader conversions when it can run on the device. Device codecs and source support still matter.

## How to use

1. Paste a public video link or share it to Nazil from another app.
2. Preview available qualities and size information, then choose video or audio.
3. Optionally enable **Fast Download**: automatic selection or a maximum of **2, 4, 8, 12, 16, or 32 connections**.
4. Start downloading. View progress in notifications and completed media in **Library**.
5. For several links, open **Batch links**, preview them and select the items to queue.

The default folder is `Download/Nazil`; select another folder in Settings. Fast Download falls back to standard downloading when unsupported. Download **1–4 files together**, prioritize waiting requests and set a per-file speed limit shared across its parallel connections. The app retains pause/resume, cancellation, Wi-Fi-only downloading, engine updates with rollback, thumbnails, search, platform/media filters and duplicate-link warnings.

## Verification and limitations

- **46 unit tests passed**. Across verification rounds, **29 distinct Full** and **24 distinct Lite** Android test cases passed. Following the final transport fix, seven targeted Lite download tests passed in one round; Full passed six, then its YouTube case passed in an isolated recheck after a format-unavailable response. Final lint reported no issues.
- Both reported public Instagram reels and a public YouTube video downloaded with verified video/audio. Tests also cover network resume, fast video/audio downloads, capped downloading with the screen off, batch selection/cancellation, backup validation/restore, actual file operations, report preview and state after activity recreation.
- Signed upgrade from 1.8 and switching Full → Lite → Full succeeded without uninstalling.
- Runtime tests used **Android 15 / API 35, x86_64, 4 KB pages**. ARM64 and ARMv7 APKs were built and signature-verified; physical-phone tests remain pending at the user's request. Android 10–13 and 16 KB devices were not tested in this round.
- Sites can change their formats and availability. Successful examples do not guarantee every link, device, private content or protected media. Nazil does not include DRM bypass or site login.
- Resume requires source support. Android controls background scheduling; reopening the app may be necessary after force-stop or reboot. User-paused requests stay paused.
- Speed limits apply to newly started/resumed requests. HLS/DASH uses the normal path with a speed cap. Reducing concurrency lets current downloads finish.
- File operations in document or cloud folders depend on provider support and permissions. Unknown library sizes are marked as estimates.
- The app updater's local APK validation and signed manual upgrade were tested. Installation end to end from a newer published GitHub release remains a later validation step.

[Arabic validation report](https://github.com/aziz1sam/Nazil/releases/download/v1.9.0/Nazil-1.9-validation.md) · [English release notes](https://github.com/aziz1sam/Nazil/releases/download/v1.9.0/Release-notes-1.9.md) · [APK SHA-256 checksums](https://github.com/aziz1sam/Nazil/releases/download/v1.9.0/SHA256SUMS-1.9.txt)

## Screenshots

| Batch links | Backup and restore | Problem report preview |
| --- | --- | --- |
| ![Batch links](https://github.com/aziz1sam/Nazil/releases/download/v1.9.0/Nazil-1.9-batch.png) | ![Backup settings](https://github.com/aziz1sam/Nazil/releases/download/v1.9.0/Nazil-1.9-backup.png) | ![Report preview](https://github.com/aziz1sam/Nazil/releases/download/v1.9.0/Nazil-1.9-report.png) |

## Source and building

Download **[Nazil-1.9-source.zip](https://github.com/aziz1sam/Nazil/releases/download/v1.9.0/Nazil-1.9-source.zip)** for the complete Android project. GitHub's automatically generated repository source archives contain this documentation repository.

Extract the archive and open `NazilAndroid` in Android Studio. The project uses JDK 17, Android SDK 35, Build Tools 34.0.0 and Gradle 8.9. The project README contains full build, test, licensing and signing instructions. A development key is included; the private release signing key and local SDK configuration are excluded.

## Privacy

Nazil stores download history locally and does not send it to a dedicated analytics server. It connects to selected content platforms, the official GitHub download-engine source and this repository for app update checks. Backup/export/import and problem-report sharing are initiated by the user. Backup files contain history URLs; media files and folder permissions need separate transfer.

For feedback, use the editable in-app problem report or include your Android version, Nazil version and the error message. Add a public example link only when appropriate. Do not include passwords or private session data.
