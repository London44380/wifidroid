[![Android](https://img.shields.io/badge/Platform-Android-3DDC84?style=for-the-badge&logo=android&logoColor=white)](https://android.com)
[![API](https://img.shields.io/badge/API%2B-brightgreen?style=for-the-badge)](https://android-arsenal.com/api?level=30)
[![Kotlin](https://img.shields.io/badge/Kotlin-7F52FF?style=for-the-badge&logo=kotlin&logoColor=white)](https://kotlinlang.org)
[![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)](LICENSE)

<img width="1516" height="1687" alt="generated-image(1)" src="https://github.com/user-attachments/assets/3e8bfd79-8bfe-4dae-9473-dbde5d3298ca" />

**⚠️ FOR EDUCATIONAL AND AUTHORIZED TESTING ONLY ⚠️**

## 🎯 About The Project

**WifiDroid** is a powerful Android application designed for network security
to evaluate WiFi network resilience through controlled, high-frequency
connection attempts. Built with **Kotlin** and leveraging Android's official
`WifiNetworkSuggestion` API, this tool simulates connection stress tests to identify potential
DoS vulnerabilities in WiFi infrastructure.

This updated version introduces **native French ISP box compatibility** (Orange Livebox,
Free Freebox, SFR, Bouygues Bbox), full WPA2/WPA3 Transition Mode support, a
Tailwind-inspired red dark theme, a robust permission persistence system, and a
**fully customizable manual profile** for any router worldwide.

---

## 🔑 Key Differentiators

| Feature | Details |
|---|---|
| ✅ **No Root Required** | Operates entirely within Android's security framework |
| ⚡ **High Performance** | Up to 6.5+ attempts per second via coroutine-based batching |
| 🇫🇷 **French ISP Profiles** | Native support for Livebox / Freebox / SFR Box / Bbox |
| ⚙️ **Custom Profile** | Manual SSID, password, security mode and band for any router |
| 🔐 **WPA3 Ready** | WPA2, WPA3 SAE, and WPA2/WPA3 Transition Mode |
| 🛡️ **Legal Safeguards** | Built-in warnings, confirmation dialogs, Art. 323-1 CP notice |
| 📊 **Advanced Analytics** | Real-time metrics, colored log, progress visualization |
| 🎨 **Tailwind Red Dark Theme** | Material Design 3 with Tailwind CSS-inspired red/gray palette |
| 🔒 **Privacy Focused** | Zero data collection, no external connections |
| 🔁 **Permission Persistence** | Auto-detects WiFi access revocation and guides user to Settings |

---

## ✨ Features

### Core Functionality

- 🔄 **Automated Stress Testing** — Configurable iteration counts (1–1000+) with batch processing
- 📈 **Real-time Monitoring** — Live progress bar, attempts/s, success rate, elapsed time
- 📝 **Colored Activity Log** — Timestamped entries with color-coded log levels (success/error/warning/debug)
- 🎯 **Smart Retry Logic** — Graceful handling of duplicate SSIDs and Android internal errors
- ⚙️ **Flexible Security Config** — OPEN / WPA2-PSK / WPA3-SAE / WPA2+WPA3 Transition
- 🚀 **Coroutine Architecture** — Non-blocking engine using `Dispatchers.IO` + `StateFlow` / `SharedFlow`

### 🌐 Router / ISP Profiles

| ISP / Type | Model | Security | 6 GHz Band | Notes |
|---|---|---|---|---|
| 🟠 Orange | Livebox 4 / 5 / 6 | WPA2 only | ❌ | Legacy mode |
| 🟠 Orange | **Livebox 7 / S (Wi-Fi 7)** | WPA3 Personal Compatibility | ✅ WPA3 forced | RSNO mode |
| 🔵 Free | Freebox Pop / Ultra / Delta / Revolution | WPA2/WPA3 Transition | ➖ | Since Mar 2025 |
| 🔴 SFR | Box 8 / THD | WPA2/WPA3 Transition | ➖ | |
| 🟡 Bouygues | Bbox Wi-Fi 6 / 7 | WPA2/WPA3 Transition | ➖ | |
| ⚙️ **Custom** | **Any router worldwide** | **Manual selection** | **Manual selection** | **Full control** |

> **Custom profile** lets you manually set any SSID, password, security mode
> (OPEN / WPA2 / WPA3 / Transition) and target band (ANY / 2.4 GHz / 5 GHz / 6 GHz).
> Ideal for non-French routers, enterprise access points, or any custom lab setup.
>
> Auto-selection of security mode is applied for ISP profiles.
> Livebox 7 on 6 GHz band automatically forces WPA3 SAE.

### 📊 Performance Metrics

- Success / failure rate percentage
- Average attempts per second (real-time)
- Total test duration
- Detailed error categorization (duplicate, disallowed, internal, limit exceeded)

### 🛡️ Safety Mechanisms

- Emergency stop button (mid-test abort)
- Permission validation before every test
- **Auto-detection of WiFi suggestion access revocation** with direct link to Android Settings

### 🎨 User Interface

- Tailwind CSS-inspired red dark theme
- Material Design 3 components (Cards, TextInput, Buttons, ProgressBar)
- ISP / Band / Security spinners with auto-selection
- **Custom profile option** — full manual control over all parameters
- Scrollable colored terminal-style activity log
- Live 2×2 metrics grid (attempts / rate / success % / elapsed)

### Permissions Required

| Permission | Purpose |
|---|---|
| `ACCESS_FINE_LOCATION` | Required by Android for WiFi scanning |
| `CHANGE_WIFI_STATE` | Submit network suggestions |
| `NEARBY_WIFI_DEVICES` | Android 13+ WiFi operations |

> ⚠️ Android also requires a **special app approval** for `WifiNetworkSuggestion`.
> The app automatically detects if this access is revoked and redirects you to:
> **Settings → Apps → Special app access → Wi-Fi control**
