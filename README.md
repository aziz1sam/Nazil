# Nazil — نازل

**Download videos and audio directly to your Android phone.**

[Download Nazil 1.12](https://github.com/aziz1sam/Nazil/releases/tag/v1.12.0) · [All releases](https://github.com/aziz1sam/Nazil/releases) · [Report a problem](https://github.com/aziz1sam/Nazil/issues)

Nazil is an Arabic Android downloader for public links supported by yt-dlp. Downloading and media processing run on the phone without a dedicated Nazil server or account. The existing four layouts, independent colors, rearrangeable sections and saved appearance profiles remain available.

## What's new in 1.12

- **Automatic link analysis:** paste or share one link to see the title, thumbnail, available qualities and their sizes. Estimates and unknown sizes are labeled. Changing the link cancels outdated work; short-lived metadata caching reduces repeated analysis.
- **Overall download progress:** combine video/audio bytes when their sizes are available, then show processing and saving separately. Completion is recorded after validation and successful publication.
- **Per-site traffic control:** up to two active downloads per site within the global 1–4 file limit. Explicit server `Retry-After` waits survive process restart, while other sources can continue. Automatic retries stop after five consecutive rate-limit responses; waits are bounded to 24 hours.
- **Optional site defaults:** open **More** to remember quality, video/audio choice and destination for that site. Each new request keeps its destination; paused, scheduled or failed requests can select a replacement folder.
- **Content-aware duplicate checks:** use the extractor's media identity when available, distinguish different video qualities, and retain the option to download another copy. Batch selection also skips equivalent extracted items.
- **Media integrity checks:** inspect expected tracks, duration and readable samples near the beginning/end before publishing. This is container/sample validation, not full decoding of every frame.
- **Scheduled downloads:** choose an earliest start time, Wi-Fi and/or charger conditions. Jobs and requests persist across reboot; changing conditions preserves resumable parts. Android controls the actual execution time.
- **Safe temporary cleanup:** review removable bytes and bytes retained for resume. Cleanup preserves active, waiting, scheduled and user-paused transfers, with confirmation before deletion.
- **Appearance-only sharing:** export/import colors, section order and saved profiles separately from download history. Review the effective colors and confirm before replacing appearance.
- **Local library player:** play compatible saved video/audio, resume near the saved position, seek and select 0.75×–2× speed. Playback pauses when leaving the app and resources are released on close. External-player opening remains available.

This release also incorporates the previously prepared **1.11 stability improvements**: durable interrupted-download recovery, adaptive direct-file connections, bounded expired-link refresh and automatic verified engine maintenance. Technical engine controls and the old information footer are hidden from Settings; history export remains available. HLS/DASH parallel fragments continue to use the engine's own path.

## Installation

Requires **Android 10 or later**. Choose the architecture and variant matching your device:

| Device | Full | Lite |
| --- | --- | --- |
| Most modern phones (ARM64) | [58.2 MB](https://github.com/aziz1sam/Nazil/releases/download/v1.12.0/Nazil-1.12-arm64.apk) | [22.5 MB](https://github.com/aziz1sam/Nazil/releases/download/v1.12.0/Nazil-1.12-lite-arm64.apk) |
| Compatible 32-bit phones (ARMv7) | [51.5 MB](https://github.com/aziz1sam/Nazil/releases/download/v1.12.0/Nazil-1.12-armv7.apk) | [21.0 MB](https://github.com/aziz1sam/Nazil/releases/download/v1.12.0/Nazil-1.12-lite-armv7.apk) |
| Compatible emulators/devices (x86_64) | [61.2 MB](https://github.com/aziz1sam/Nazil/releases/download/v1.12.0/Nazil-1.12-x86_64.apk) | [22.6 MB](https://github.com/aziz1sam/Nazil/releases/download/v1.12.0/Nazil-1.12-lite-x86_64.apk) |

Sizes use decimal MB. Full includes FFmpeg for broader supported conversion; Lite uses Android's MP4/AAC processing and is smaller. They share the package, version and signing certificate and can be installed over each other. Keep the architecture compatible with the phone.

Paste a link, review quality/size and tap Download. Fast Download uses a user-selected connection ceiling of Auto/2/4/8/12/16/32, adapts direct-file concurrency and falls back when unsupported. Optional scheduling and site defaults are under More. Find ongoing work in Downloads and saved media in Library.

## Existing features

- Up to 50 links per batch with previews and selection; 1–4 concurrent files, priority and per-file speed limits shared by parallel parts.
- Actual-file renaming, search, platform/media filters, thumbnails, and selection of up to 100 files for sharing or confirmed deletion.
- Optional JSON backup of general settings, appearance and download history, with review before restore. Imported entries remain historical records and do not start downloads. Media files, resume parts, folder permissions, site defaults and playback positions need separate handling.
- Editable problem reports exclude URLs, titles, raw errors and history by default; sharing is initiated by the user.
- GitHub app updates select the architecture/variant and verify size, SHA-256, package, version and signing certificate before opening Android's installer. Android requests installation approval.
- Readable errors, pause/resume, storage preflight, Wi-Fi-only downloading and verified automatic engine updates with recovery.

## Verification and limitations

Both Full and Lite passed **68 JVM tests each**, Android Lint, and emulator runs reporting **57 tests on Android 15/API 35 (4 KB pages), 22 on Android 11/API 30 (4 KB), and 30 on Android 17/API 37 (16 KB)** per variant. These are repeated test runs across platforms, not 218 distinct tests. A signed upgrade from 1.11 to 1.12, including Full → Lite → Full, preserved the three completed records, settings and original installation time.

- Runtime testing uses emulators; physical ARM phones remain untested at the user's request. ARM64/ARMv7 APKs are separately built and signature-verified.
- On 16 KB systems the app uses Android's compatible MP4/AAC processing. Some bundled FFmpeg dependencies retain 4 KB alignment, so general Full-version conversions on 16 KB devices remain limited. Successful emulator examples do not certify every device or format.
- Current live download checks use public samples and a controlled expired-link fixture. YouTube/Instagram were not comprehensively retested for this release. Site availability, authentication restrictions and source changes can prevent individual downloads. No DRM bypass or site login is included.
- Scheduling specifies an earliest time, not an exact alarm. Background limits, force-stop and device policy can delay work; reopening the app may be required. User-paused requests stay paused.
- Overall byte totals depend on source metadata. Integrity checks inspect container samples and do not prove every byte/frame is intact. Resuming saved parts requires matching source identity and validators.
- The native player depends on the phone's codecs. It pauses when the app leaves the foreground; background-audio service features are outside this release.
- File operations depend on document-provider capabilities and permissions. Unknown sizes are estimates. Safe cleanup deliberately retains parts belonging to resumable requests.

[Arabic validation report](https://github.com/aziz1sam/Nazil/releases/download/v1.12.0/Nazil-1.12-update-report.md) · [Arabic and English release notes](https://github.com/aziz1sam/Nazil/releases/download/v1.12.0/Nazil-1.12-release-notes.md) · [APK checksums](https://github.com/aziz1sam/Nazil/releases/download/v1.12.0/SHA256SUMS-1.12.txt)

## Screenshots

Actual emulator captures; the current visual design is retained. Home/player are from Lite on Android 17; Settings is signed Full on Android 15. The public sample clip is Big Buck Bunny via W3Schools.

| Link analysis | Library player | Settings footer hidden |
| --- | --- | --- |
| ![Link analysis](https://github.com/aziz1sam/Nazil/releases/download/v1.12.0/Nazil-1.12-home.png) | ![Library player](https://github.com/aziz1sam/Nazil/releases/download/v1.12.0/Nazil-1.12-player.png) | ![Settings footer hidden](https://github.com/aziz1sam/Nazil/releases/download/v1.12.0/Nazil-1.12-settings-bottom.png) |

## Source and building

Download **[Nazil-1.12-source.zip](https://github.com/aziz1sam/Nazil/releases/download/v1.12.0/Nazil-1.12-source.zip)** for the complete Android project. GitHub's automatic repository archives contain this documentation repository.

Extract the archive and open `NazilAndroid` in Android Studio. Build with JDK 17, Android SDK 35, Build Tools 34.0.0 and Gradle 8.9. The project README contains build, test, licensing and signing instructions. The development key is included; the private release signing key and local SDK configuration are excluded.

## Privacy

History, site defaults, appearance and playback positions are stored locally. Nazil connects to selected sources, official engine releases and this GitHub repository for update checks. It does not send history to a dedicated analytics server. Backup files contain history URLs; appearance-only exports do not include download history or destination permissions. Export/import and report sharing require user actions.

For a problem report, include your Android/Nazil version and readable error. Add a public example link when appropriate; keep passwords and session data private.
