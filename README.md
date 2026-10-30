# Trace `0.0.1v`

*A stream of your life.*  
*A daily mirror ritual.*  
*All your past, here.*

[Android Play Store Build](https://github.com/muneebwanee/Trace/actions/workflows/build-android-playstore.yml) • 
[iOS \& iPadOS App Store Build](https://github.com/muneebwanee/Trace/actions/workflows/build-ios-appstore.yml) • 
[Windows Store Build](https://github.com/muneebwanee/Trace/actions/workflows/build-windows-store.yml) • 
[Linux Store Build](https://github.com/muneebwanee/Trace/actions/workflows/build-linux-store.yml) • 
[Latest Release](https://github.com/muneebwanee/Trace/releases) • 
[License: TNCL 1.0](https://github.com/muneebwanee/Trace/blob/main/LICENSE) 
[](https://github.com/muneebwanee)

**[Download Official Builds](https://github.com/muneebwanee/Trace/releases)** • **[Inspect \& Contribute](./Contributing.md)** • **[License (TNCL 1.0)](./LICENSE)** • **[Report Issue](https://github.com/muneebwanee/Trace/issues)**


## Philosophy

> *"Simple doesn't mean empty. Today proved that."*

**Trace (`0.0.1v`)** is an ultra-minimalist, two-tone daily stream diary crafted for **Android**, **iOS**, **iPadOS**, **macOS**, **Windows**, **Linux**, and **Web** by **[muneebwanee](https://github.com/muneebwanee)**.

Most journaling apps bury your thoughts under noisy streaks, neon dashboards, and cluttered toolbars. Trace strips everything back to two quiet tones — **Warm Paper (`#F5F5F3`)** and **Soft Ink (`#222220`)**, inverting cleanly to **Deep Ink (`#161615`)** in Dark Mode — along a single continuous vertical timeline. Every day of your life expands naturally down one calm page with zero internal scroll boxes, accompanied only by a live ticking clock and the words you choose to leave behind.

## Universal Store & Device Compatibility

| Platform / Store | Build Artifacts | Key Capabilities |
| :--- | :--- | :--- |
| **Android (Google Play & Direct APK)** | `Trace_PlayStore_API36.aab` & `Trace_Universal_API36.apk` | Targets **API 36 (Android 16)** (`minSdk 24`), native Edge-to-Edge `WindowInsets` (`systemBars \| displayCutout \| ime`) status-bar & cutout safe-area padding, Auto-Theme Editorial Home Screen Widget, Storage Access Framework PDF/File export, and Google Drive sync |
| **iOS & iPadOS (Apple App Store & Sideload)** | `Trace_muneebwanee.ipa` | Native SwiftUI universal app for iPhone & iPad, WidgetKit Auto-Theme Editorial Home Screen Widget (`TraceWidget`), iCloud Key-Value & iCloud Drive Folder sync, and native `UIGraphicsPDFRenderer` A4 PDF export |
| **Windows (Microsoft Store & Desktop)** | `Trace_Windows_Store.appx` & `Trace_Windows_Setup.exe` | Native Electron desktop package for Windows 10/11 (`x64`) with offline utility stylesheet, local OneDrive/folder auto-backup, and full-text diary search |
| **Linux (Flathub, Snap, AppImage & Debian)** | `Trace_Linux_x86_64.AppImage` & `Trace_Linux_amd64.deb` | Portable Linux `AppImage`, Debian/Ubuntu `.deb`, plus Flathub (`io.github.muneebwanee.Trace.yml`) and Snapcraft (`snapcraft.yaml`) manifests |
| **Web & Desktop PWA** | `trace_journal_app.html` | 100% self-contained single-file offline web app with zero external CDN dependencies and instant (`<15ms`) startup |

| Area | Implementation in Trace (`0.0.1v`) | Why It Matters |
| :--- | :--- | :--- |
| **Custom Easing Tokens** | `--ease-out: cubic-bezier(0.23, 1, 0.32, 1)` & `--ease-drawer: cubic-bezier(0.32, 0.72, 0, 1)` | Built-in CSS easings feel weak; custom cubic-bezier curves start fast and settle naturally under `240ms`. |
| **Pointer-Down Press Feedback** | `button:active { transform: scale(0.97); }` (`140ms var(--ease-out)`) + `touch-action: manipulation` | Responds the instant a finger or cursor presses down with zero `300ms` double-tap delay. |
| **1:1 Sheet Drag & Momentum Flick** | Pointer-captured `translateY` tracking + upward rubber-banding + flick velocity (`v > 0.35 px/ms`) | Bottom sheets (`Settings` & `Legal Reader`) track your finger 1:1 and dismiss smoothly on a quick downward flick. |
| **Origin-Aware Drawers & Never `scale(0)`** | Header drawers (`#calendarDrawer`, `#searchBarPanel`) enter from `scale(0.98) translateY(-4px)` with `transform-origin: top right` | Elements never appear from `scale(0)` nowhere; popovers and drawers scale from their trigger direction. |
| **Capability-Gated `:hover`** | All `:hover` rules wrapped inside `@media (hover: hover) and (pointer: fine)` | Prevents sticky hover states on touchscreens while keeping crisp hover feedback for mouse/trackpad users. |
| **Dynamic Viewport & Safe Areas** | `100dvh`, `interactive-widget=resizes-content`, `overscroll-behavior: contain`, and native Android `WindowInsets` | Eliminates mobile URL-bar overflow, pull-to-refresh scroll hijacking, and Android status-bar/cutout overlap. |
| **Editorial Measure & Accessibility** | `max-width: 65ch` on diary entries, `tabular-nums` on live clocks, and full `@media (prefers-reduced-motion: reduce)` support | Keeps line lengths comfortable for long-form reading and respects vestibular accessibility preferences. |

## Core Features

- **Strict Two-Tone Aesthetic (Auto Light & Dark Mode)**: Crafted exclusively with Warm Paper (`#F5F5F3`) and Soft Ink (`#222220`), automatically respecting your device's system appearance or toggling instantly via the header Sun / Moon icon (`#161615`).
- **100% Offline-First & Zero External Dependencies**: All layout utilities, typography fallbacks, and vector icons are embedded directly inside the application bundle so Trace launches in under `15ms` even in Airplane Mode or on restricted networks.
- **Full-Height Continuous Diary Stream (No Internal Scroll Boxes)**: Every entry expands vertically as you write so 100% of your words for every date remain visible inline along the vertical node/rail stream.
- **Auto-Theme Architectural Editorial Home Screen Widgets (Android & iOS)**:
  - **Dynamic Light & Dark Theme Sync**: Automatically switches between Warm Archival Paper (`#F4F3EE`) and Deep Obsidian Ink (`#121211`) to match your active Trace theme or system appearance.
  - **Editorial Serif Timepiece & 7-Day Stream Rhythm**: Displays a live `HH:mm` editorial serif clock (`38sp`), a recessed date capsule (`EEE · MMM D`), a 7-day weekly stream rhythm matrix (`S M T W T F S` with `●` written days, `◎` today, and `·` quiet days), and live `XD · YW` stats.
  - **3 Functional Tap Zones**: Tap the clock to open your live diary stream, tap the date capsule or 7-day rhythm matrix to open the monthly Calendar Drawer, or tap the bottom reflection card to jump straight to today's entry and start writing.
- **Typeset PDF Diary & Multi-Format Exports**: Export your diary as a multi-page A4 **PDF (`Trace_Diary.pdf`)**, **Plain Text (`.txt`)**, **Markdown (`.md`)**, or **JSON Archive (`.json`)**.
- **Comprehensive In-App Legal, Privacy & Data Safety Center**: Includes full long-form **Terms of Service**, **Privacy Policy (Zero Telemetry)**, **Store EULA**, **Data Safety & Instant Local Wipe**, and the **Trace Non-Commercial License (TNCL) 1.0** accessible offline via `Settings → Terms • Privacy • EULA • Data Safety • TNCL 1.0`.

## Repository Structure

```text
Trace/
├── Trace_Android_PlayStore.zip                  # Android API 36 Gradle project + Auto-Theme Widget
├── Trace_iOS_AppStore.zip                       # iOS/iPadOS SwiftUI project + WidgetKit Extension
├── Trace_Windows_Store.zip                      # Windows Electron (.appx & .exe) project
├── Trace_Linux_Store.zip                        # Linux Electron (.AppImage, .deb, Flathub, Snap) project
├── trace_journal_app.html                       # Standalone 100% offline Web/PWA application
├── README.md                                    # Project documentation
├── CONTRIBUTING.md                              # Developer & contributor guidelines under TNCL 1.0
├── LICENSE                                      # Trace Non-Commercial License (TNCL) 1.0
├── TERMS_OF_SERVICE.md                          # Full Terms of Service
├── PRIVACY_POLICY.md                            # Full Zero-Telemetry Privacy Policy
├── EULA.md                                      # Multi-store End-User License Agreement
└── .github/
    └── workflows/
        ├── build-android-playstore.yml          # Builds signed Play Store .aab & universal .apk
        ├── build-ios-appstore.yml               # Builds unsigned/ad-hoc iOS & iPadOS .ipa
        ├── build-windows-store.yml              # Builds Microsoft Store .appx & Setup .exe
        └── build-linux-store.yml                # Builds Linux .AppImage & .deb packages
```

## Inspecting Code, Private Modifications & Contributing (TNCL 1.0)

Trace is source-available under the **[Trace Non-Commercial License (TNCL) 1.0](./LICENSE)**:
- **Inspect & Verify**: Developers and security researchers are encouraged to inspect the source code to verify our 100% offline, zero-telemetry architecture.
- **Private Personal Modifications**: You may clone and modify Trace privately for your own personal, non-commercial use on devices you personally own or control.
- **Official Repository Contributions**: You may fork [`github.com/muneebwanee/Trace`](https://github.com/muneebwanee/Trace) to develop and submit Pull Requests back to our official repository (see **[CONTRIBUTING.md](./Contributing.md)**).
- **Redistribution Restricted**: Redistributing standalone copies or compiled binaries, publishing releases on forks, uploading clones to app stores, or using Trace commercially is strictly prohibited without prior written permission from **[muneebwanee](https://github.com/muneebwanee)**.

## Privacy & License

- **100% Offline & Zero Telemetry**: Trace collects zero personal data, runs zero analytics or tracking SDKs, and stores all journal entries locally on your device. See **[PRIVACY\_POLICY.md](./Privacy_Policy.md)** and **[TERMS\_OF\_SERVICE.md](./Terms_Of_Service.md)**.
- **Author**: Developed by **[muneebwanee](https://github.com/muneebwanee)**
- **License**: Governed by the **[Trace Non-Commercial License (TNCL) 1.0](./LICENSE)** (`Copyright (c) 2026 muneebwanee. All Rights Reserved`).
