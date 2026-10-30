# Contributing to Trace (`0.0.1v`)

Thank you for your interest in inspecting, improving, and contributing to **Trace** (`https://github.com/muneebwanee/Trace`), developed by **[muneebwanee](https://github.com/muneebwanee)**.

Trace is governed by the **[Trace Non-Commercial License (TNCL) 1.0](https://www.google.com/search?q=./LICENSE)**. Under TNCL 1.0, developers are warmly encouraged to inspect the source code, make private modifications for personal use, and submit Pull Requests back to the official repository, while standalone redistribution of copies or binaries outside the official repository is restricted.

## 1. What You Can Do Under TNCL 1.0

| Activity | Permitted? | Notes |
| :--- | :--- | :--- |
| **Inspect & Audit Code** | Yes | Read, study, and audit all source files, widgets, and CI workflows. |
| **Private Personal Modifications** | Yes | Customize fonts, themes, or layouts locally on your own personal devices. |
| **Fork to Submit Pull Requests** | Yes | Fork [`muneebwanee/Trace`](https://github.com/muneebwanee/Trace) to develop and submit PRs back to `main`. |
| **Redistribute Standalone Copies / Binaries** | No | Do not publish standalone copies, forks with public releases, or store uploads without written permission from **muneebwanee**. |
| **Commercial Use or Rebranding** | No | Commercial distribution and removal of `muneebwanee` attribution are prohibited. |

## 2. Design Engineering & Motion Standards (`emilkowalski/skills`)

All UI and interaction contributions must adhere to Trace's strict two-tone aesthetic and the design engineering principles adapted from **[emilkowalski/skills](https://github.com/emilkowalski/skills)** (`emil-design-eng`, `mobile-native`, `apple-design`, and `review-animations`):

1. **Strict Two-Tone Palette**:
   - **Light Mode**: Warm Paper (`#F5F5F3` / `#F4F3EE`) and Soft Ink (`#222220` / `#1C1C1A`).
   - **Dark Mode**: Deep Ink (`#161615` / `#121211`) and Warm Paper Ink (`#F5F5F3` / `#F4F3EE`).
   - Never introduce third-party accent colors, badges, or decorative gradients.
2. **Easing, Duration & GPU-Only Motion**:
   - Use custom easing tokens: `--ease-out: cubic-bezier(0.23, 1, 0.32, 1)`, `--ease-in-out: cubic-bezier(0.77, 0, 0.175, 1)`, and `--ease-drawer: cubic-bezier(0.32, 0.72, 0, 1)`.
   - Never use `transition: all` or `ease-in` on UI interactions. Keep UI transitions under `300ms` (`120ms` for button press feedback, `180ms` for header drawers, `240ms` for bottom sheets).
   - Never animate from `scale(0)`; enter from `scale(0.96)` + `opacity: 0`.
   - Animate only GPU-composited properties (`transform` and `opacity`).
3. **Mobile-Native Platform Discipline**:
   - Every pressable control must respond immediately on pointer-down (`:active { transform: scale(0.97); }`) and include `touch-action: manipulation` + `user-select: none`.
   - Gate all `:hover` rules behind `@media (hover: hover) and (pointer: fine)` so touch screens never suffer from sticky hover states.
   - Honor `@media (prefers-reduced-motion: reduce)` by replacing spatial movement with gentle opacity cross-fades.
   - Maintain 100% offline execution (`<15ms` startup with zero external CDN dependencies).

## 3. Repository Architecture & Local Development

- **Web / PWA (`trace_journal_app.html`)**: Single-file, zero-dependency offline web application. Open directly in any browser or inspect via Chrome/Safari Web Inspector.
- **Android (`Trace_Android_PlayStore.zip`)**: Native Android Gradle project (`compileSdk 36`, `targetSdk 36`, `minSdk 24`) with `MainActivity.java` (`WindowInsets` safe-area handling + `AndroidBridge`) and `TraceWidgetProvider.java` (Auto-Theme Editorial Home Screen Widget).
- **iOS & iPadOS (`Trace_iOS_AppStore.zip`)**: Native SwiftUI project (`TraceApp/`) and WidgetKit extension (`TraceWidget/`) generated via `xcodegen generate` (`project.yml`).
- **Windows (`Trace_Windows_Store.zip`) & Linux (`Trace_Linux_Store.zip`)**: Electron desktop wrappers targeting `.appx` / `.exe` and `.AppImage` / `.deb` / Flathub / Snapcraft.

## 4. How to Submit a Pull Request

1. Fork [`https://github.com/muneebwanee/Trace`](https://github.com/muneebwanee/Trace) to your GitHub account.
2. Create a descriptive feature or bugfix branch (`git checkout -b fix/widget-layout` or `feat/keyboard-navigation`).
3. Test your changes offline and verify that no external network requests or non-GPU layout animations were introduced.
4. Open a Pull Request against `main` in [`muneebwanee/Trace`](https://github.com/muneebwanee/Trace) describing:
   - **What changed** and **Why** (include a `| Before | After | Why |` table for any UI or animation changes).
   - **Platforms tested** (Web, Android API 36, iOS/iPadOS, Windows, or Linux).

## 5. Contributor License Agreement

By opening a Pull Request or submitting a contribution to [`https://github.com/muneebwanee/Trace`](https://github.com/muneebwanee/Trace), you agree to Section 4 of the **[Trace Non-Commercial License (TNCL) 1.0](https://www.google.com/search?q=./LICENSE)**, granting **muneebwanee** a perpetual, worldwide, royalty-free, irrevocable license to include, distribute, and relicense your contribution as part of Trace.
