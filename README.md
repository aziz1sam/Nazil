# Nazil

**Download your videos to your phone.**

[Download the latest release](https://github.com/aziz1sam/Nazil/releases/latest)

Nazil is an Android video and audio downloader for YouTube, Instagram, TikTok, and other platforms supported by its download engine. It features an Arabic interface, four visual themes, quality selection, and a local media library.

## Features

- Save videos as **MP4** and audio as **M4A**.
- Paste a link or share it directly to Nazil from another app.
- Preview video information when available from the source.
- Choose 360p, 480p, 720p, 1080p, or the best available quality.
- Enable **Fast Download** with automatic connection selection or a maximum of **2, 4, 8, 12, 16, or 32 connections**.
- Automatically fall back to standard downloading when splitting is unavailable.
- Track downloads through progress notifications and retry interrupted transfers.
- Browse, search, play, share, and delete saved files.
- Choose from four themes and customize the download folder.
- Enable Wi-Fi-only downloads and update the download engine from Settings.

## Installation

Requires **Android 10 or later**.

Download the APK matching your device from the [Releases](https://github.com/aziz1sam/Nazil/releases) section:

| APK variant | Device |
| --- | --- |
| [ARM64 APK](https://github.com/aziz1sam/Nazil/releases/download/v1.5.0/Nazil-1.5-arm64.apk) | Most modern Android phones |
| [ARMv7 APK](https://github.com/aziz1sam/Nazil/releases/download/v1.5.0/Nazil-1.5-armv7.apk) | Compatible 32-bit Android devices |
| [x86_64 APK](https://github.com/aziz1sam/Nazil/releases/download/v1.5.0/Nazil-1.5-x86_64.apk) | Compatible emulators and x86_64 devices |

Open the APK and follow Android's installation prompts. Updates signed with the same release key can be installed over the existing version.

## How to use

1. Paste a video link or share it to Nazil.
2. Select video or audio and your preferred quality.
3. Optionally enable Fast Download.
4. Start downloading and find the completed file in **Library**.

The default download folder is **`Download/Nazil`**.

## What's new in 1.5

- Fixed Instagram downloads when ready MP4 formats omit codec information.
- Bundled an updated download engine, without requiring a manual engine update after installation.
- Added Android-based video/audio merging when the bundled FFmpeg cannot run on a device.
- Verified video and audio downloads using the two reported Instagram reels and a public YouTube video on an Android emulator.

## Privacy and availability

Nazil processes downloads on the device and stores its download history locally. It does not require a dedicated download server or a Nazil account. It connects to the selected content platforms and GitHub for download-engine updates.

Availability depends on the platform and the content's access restrictions. Quality limits apply when the source provides video dimensions. Fast Download depends on source support and does not guarantee a speed increase. Interrupted transfers can resume when supported by the source.

## Feedback

Use [Issues](https://github.com/aziz1sam/Nazil/issues) to report a problem or request a feature. Include your Android version, Nazil version, the error message, and a public example link when possible. Do not include passwords or private session data.
