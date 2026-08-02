<div align="center">

# 📡 Grand Take Attendance

### *Smart, secure, Bluetooth-powered classroom attendance — no roll calls, no clipboards.*

**GTA** turns a teacher's phone into an attendance beacon and a student's phone into a one-tap check-in — all over Bluetooth Low Energy, no internet required.

[![Latest Release](https://img.shields.io/github/v/release/MegaMind2999/grand-take-attendance?style=for-the-badge&color=1E63F0&label=Latest%20Release)](https://github.com/MegaMind2999/grand-take-attendance/releases/latest)
[![Downloads](https://img.shields.io/github/downloads/MegaMind2999/grand-take-attendance/total?style=for-the-badge&color=06D6A0)](https://github.com/MegaMind2999/grand-take-attendance/releases)
[![Min SDK](https://img.shields.io/badge/Min%20SDK-24-00B4D8?style=for-the-badge)](#requirements)
[![License](https://img.shields.io/badge/License-Freeware-lightgrey?style=for-the-badge)](#license)

[⬇️ Download Latest APK](https://github.com/MegaMind2999/grand-take-attendance/releases/latest) · [✨ Features](#-features) · [📲 How It Works](#-how-it-works) · [🛠 About the Build](#-about-the-build)

</div>

---

## 📖 About

**Grand Take Attendance** is a native Android app built for classrooms that need fast, tamper-resistant attendance tracking without paper sign-in sheets or expensive hardware.

A **teacher** starts a BLE attendance session with a rotating session code. Nearby **students** running the app automatically discover the session, check in, and get an instant confirmation — all validated against each student's known device fingerprint to help flag proxy check-ins.

No accounts. No servers. No cellular data. Just Bluetooth.

---

## ✨ Features

| | |
|---|---|
| 🎓 **Dual Mode** | One app, two experiences — Student and Teacher, switchable via a hidden admin unlock |
| 📶 **BLE Attendance Sessions** | Teachers broadcast a live session; students check in automatically over Bluetooth LE |
| 🔒 **Device Fingerprinting** | Cross-checks each student's device against their attendance history to flag suspicious check-ins |
| 📊 **Per-Course History** | Every student can review attended days, timestamps, and session codes for each course |
| 🗑️ **Recycle Bin** | Deleted courses aren't gone forever — restore or permanently purge from one screen |
| 🎨 **Animated Backgrounds** | A subtle, theme-aware animated backdrop across the whole app (toggleable in Settings) |
| 🌓 **Light & Dark Themes** | Full Material 3 dynamic color support, tuned for both modes |
| 🔄 **Built-in Updates** | Checks this very repo's Releases page for new versions — no Play Store required |
| 🔐 **Local-Only Data** | Everything is stored on-device with Room + DataStore — nothing leaves the phone |

---

## 📲 How It Works

```
┌──────────────┐        BLE Advertise         ┌──────────────┐
│   Teacher    │ ───────────────────────────▶ │   Student    │
│  starts a    │                               │  app auto-   │
│  session     │ ◀─────────────────────────── │  detects &   │
│  with code   │        Student ID + Device    │  checks in   │
└──────────────┘                               └──────────────┘
        │                                              │
        ▼                                              ▼
  Records attendance,                          Confirmation + day
  flags unfamiliar devices                      count saved locally
```

1. **Teacher** opens the app, picks a course, and starts a session — this begins BLE advertising with a short numeric code.
2. **Student** opens the app; nearby active sessions are detected automatically via BLE scan.
3. The student's ID and device fingerprint are sent over; the teacher's app validates and records attendance.
4. Both sides get instant, on-screen confirmation — no manual entry.

---

## ⬇️ Download

Grab the latest signed APK straight from the **[Releases page](https://github.com/MegaMind2999/grand-take-attendance/releases/latest)**.

> **First-time install:** Since this isn't distributed via the Play Store, Android will ask you to allow installs from this source the first time — that's expected and safe for a sideloaded APK you trust.

Once installed, the app checks this repo for new versions right from **Settings → Check for Updates**, and can download & install updates in-app.

---

## 🔐 Permissions

| Permission | Why it's needed |
|---|---|
| `BLUETOOTH_SCAN` / `BLUETOOTH_ADVERTISE` / `BLUETOOTH_CONNECT` | Core BLE attendance functionality (Android 12+) |
| `ACCESS_FINE_LOCATION` / `ACCESS_COARSE_LOCATION` | Required by Android for BLE scanning on Android 11 and below |
| `POST_NOTIFICATIONS` | Download progress notification for in-app updates (Android 13+) |
| `REQUEST_INSTALL_PACKAGES` | Lets the app prompt you to install downloaded updates |
| `INTERNET` | Only used to check this repo's Releases API and download the update APK |

No data is ever transmitted off the device beyond the update check.

---

## 🛠 About the Build

This repository distributes the app as a **pre-built, signed APK only** — source code is not published here. Releases are versioned and published directly through the [Releases page](https://github.com/MegaMind2999/grand-take-attendance/releases), where the in-app updater also checks for new versions.

### Tech Stack

- **Kotlin** + **Jetpack Compose** (Material 3)
- **Room** for local persistence, **DataStore** for preferences
- **Navigation Compose** for in-app routing
- BLE via the Android Bluetooth LE APIs
- **FastExcel** for attendance export, **Lottie** for animations

---

## 🗺️ Roadmap

- [ ] CSV/Excel export polish
- [ ] Per-course analytics dashboard
- [ ] Optional cloud backup (opt-in)
- [ ] Multi-device session hand-off

---

## 🤝 Feedback & Issues

This repo distributes a binary-only release, so there's no source to submit pull requests against — but bug reports, feature requests, and general feedback are very welcome via [Issues](https://github.com/MegaMind2999/grand-take-attendance/issues).

---

## 📄 License

Distributed under a custom **Freeware / Binary Distribution License**. You're free to download and use the app, but redistribution and modification are restricted. See [`LICENSE`](./LICENSE) for the full terms.

---

<div align="center">

Made with 🔵 for classrooms that deserve better than a paper sign-in sheet.

</div>
