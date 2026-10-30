# Privacy Policy — Trace (`0.0.1v`)

**Effective Date:** October 30, 2026  
**Version:** `0.0.1v`  
**Developer:** [muneebwanee](https://github.com/muneebwanee)  
**Official Repository:** [https://github.com/muneebwanee/Trace](https://github.com/muneebwanee/Trace)

## 1. Core Privacy Commitment: Zero Data Collection
**Trace collects zero personal data.** Trace is architected from the ground up as a 100% offline-first, local-only personal diary. We do not operate any backend servers, analytics databases, telemetry endpoints, crash-reporting trackers, or advertising networks. Your thoughts belong exclusively to you and never leave your device unless you explicitly export or sync them to your own personal storage.

## 2. Information We Do NOT Collect
Trace does **not** collect, log, transmit, process, rent, or sell:
- **Personal Identifiers**: No names, email addresses, phone numbers, account usernames, or passwords.
- **Journal Content**: No diary entries, timestamps, word counts, search queries, or calendar activity.
- **Device & Network Telemetry**: No IP addresses, MAC addresses, Advertising IDs (IDFA / GAID), browser fingerprints, or hardware serial numbers.
- **Location Data**: No GPS coordinates, Wi-Fi positioning, or IP-based geolocation.
- **Usage Analytics or Crash Logs**: No Google Analytics, Firebase, Sentry, Mixpanel, Facebook SDK, or third-party tracking scripts.

## 3. How Your Data Is Stored Locally On-Device
All application state is stored strictly inside your device's local sandboxed storage:
- `trace_journal_entries_clean_v2`: Stores your daily stream entries, date labels, and text strictly on-device.
- `trace_dark_mode_v1`: Stores your Light (`#F5F5F3`) or Dark (`#161615`) theme preference.
- `trace_font_choice_v1`, `trace_custom_font_data_v1`, `trace_custom_font_name_v1`: Stores your selected editorial typeface and any locally uploaded font file.
- **Native Widget Storage**: On Android (`SharedPreferences` under `trace_widget_prefs`) and iOS/iPadOS (`App Group UserDefaults` under `group.com.muneebwanee.trace`), today's preview snippet and 7-day dot rhythm are shared solely between the main Trace app and your local Home Screen Widget on the same device.

## 4. User-Initiated Cloud Sync & File Exports
If you choose to back up or export your diary, the transfer occurs directly between your device and the storage destination you select through your operating system's native file/cloud APIs:
1. **Apple iOS, iPadOS & macOS**: Optional iCloud sync uses Apple's native `NSUbiquitousKeyValueStore` and security-scoped iCloud Drive document folders tied to your personal Apple ID. The developer has zero access to your iCloud account.
2. **Google Android**: Optional cloud sync and file exports use Android's native Storage Access Framework (`Intent.ACTION_CREATE_DOCUMENT` / `Intent.ACTION_OPEN_DOCUMENT`) and Android Auto Backup (`BackupManager`) linked to your personal Google Drive or local device storage. The developer has zero access to your Google Drive.
3. **Microsoft Windows, Linux & Web**: Exports (`.pdf`, `.txt`, `.md`, `.json`) are written directly to the local folder you choose via the native OS file dialog.

## 5. Zero External Network Requests on Startup
Unlike web wrappers that load stylesheets or scripts from external CDNs on every launch, Trace embeds its complete utility stylesheet, icon set, and export logic directly inside the local application bundle. Launching Trace makes **zero outbound network requests**.

## 6. Instant On-Device Data Deletion ("Right to Erasure")
You have complete, immediate control over your data at all times:
- **In-App One-Tap Wipe**: Open **Settings → Data Safety → Erase All Local Diary Data → Confirm Permanent Wipe** to immediately and permanently purge all journal entries, custom fonts, and cached preferences from your device.
- **OS-Level Uninstall**: Uninstalling Trace from your device removes its local sandboxed storage directory.

## 7. Compliance with Global Privacy Regulations (GDPR, UK GDPR, CCPA/CPRA, DPDP Act, COPPA)
- **EU / UK GDPR & India DPDP Act**: Because **muneebwanee** does not collect, determine the purposes of processing, or receive any personal data from your device, you act as the sole controller and custodian of your personal journal entries.
- **California CCPA / CPRA**: We do not "sell" or "share" personal information as defined under the CCPA/CPRA, nor do we collect sensitive personal information.
- **Children's Privacy (COPPA)**: Trace collects zero personal information from anyone, including children under the age of 13 (or 16 in applicable jurisdictions), complying fully with COPPA and global age-rating standards.

## 8. Contact & Source Transparency
Because Trace is source-available under the **Trace Non-Commercial License (TNCL) 1.0**, anyone can inspect the source code at **[https://github.com/muneebwanee/Trace](https://github.com/muneebwanee/Trace)** to verify that zero tracking or data collection exists.
