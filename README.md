
# Vaultra - Secure Personal & Family Financial Manager

**Vaultra** is a cutting-edge, privacy-first personal and family finance manager built for Android 15 (Target SDK 35) in Java 17. It combines military-grade local database encryption (SQLCipher) with advanced multi-metric analytics, intelligent bill reminders, P2P family sync, and private cloud backup.

---

## 🌟 Key Highlights & Features

### 1. 🔒 Military-Grade On-Device Security & Privacy
* **SQLCipher AES-256 Encryption**: Fully encrypted SQLite database (`valutra_secure.db`) supporting 16 KB page size optimization for Android 15.
* **Hardware-Backed Android Keystore**: Cryptographic database passphrases (`DbKey`) secured in device hardware keystores.
* **Interactive Stealth & Privacy Shield**: 1-click Stealth Mode toggle (`ivStealthToggle`) on the Home Screen masking sensitive balances with a frosted glass mist overlay.
* **Biometric Unlock**: Biometric fingerprint/face authentication (`BiometricHelper`).

### 2. 🎨 Vibrant Fintech UI/UX & Glassmorphism Design
* **3D Metallic Hero Card**: Net worth overview card with a 3D gradient backdrop (`bg_hero_card.xml`), live point scrubbing (`TrendChartView`), time ranges (**7D**, **1M**, **3M**, **1Y**), and metric switching (**Net Worth**, **Assets**, **Liabilities**).
* **3x2 Symmetrical Feature Grid**: Elevated Material 3 launcher cards with soft tinted pastel backgrounds for **Bank Balances**, **Loans & Cards**, **Expenses**, **Investments**, **Reminders**, and **Pending Attention**.
* **Nordic Pulse Financial Health Score**: Circular progress gauge evaluating real-time wealth scores (0–100) and actionable spending recommendations.
* **Edge-to-Edge Experience**: Translucent system bars with `Ui.applyInsets()` drawing content seamlessly across modern displays.

### 3. 💰 Multi-Account Wealth & Portfolio Management
* **Bank Accounts & Deposits**: Savings, Current, Salary, Fixed Deposits (FD), and Recurring Deposits (RD) with split progress balance breakdown (`barA`/`barB`).
* **Cards & EMI Outflows**: Outstanding credit card balances, loan tenure tracking, and monthly EMI outflows.
* **Investment Portfolio**: Stock holdings, mutual funds, and portfolio valuation analytics.

### 4. ⏰ Smart Bill Reminders & Attention Queue
* **Flexible Scheduling**: Custom alert times and daily advance lead-up notifications.
* **Recurring End Conditions**: Stop recurring bills using an **End Date** or **Repeat Count** (e.g. 12 EMIs).
* **Attention Required Queue**: Completed reminder transactions automatically route through the **Pending Review** queue so you confirm payment source accounts.

### 5. ☁️ Google Drive Backup & P2P Family Sync
* **Private Google Drive Backup**: Periodically backs up encrypted databases to your personal Google Drive App Data Folder with 1-click manual trigger and auto-sync options.
* **Decentralized P2P Wi-Fi Sync**: Secure peer-to-peer Wi-Fi and QR code synchronization using zero-knowledge encryption keys (`family_key`) without external cloud servers.

---

## 🛠️ Tech Stack & Architecture

* **Language**: Java 17
* **Database**: SQLCipher for Android (v4.6.1) + Android SQLite
* **UI**: Material Components 3 (MD3)
* **Target SDK**: 35 (Android 15) | **Min SDK**: 26 (Android 8.0)
* **Concurrency & Background Jobs**: WorkManager v2.9.1
* **Cloud & Auth**: Google Drive API (v3), Credentials Play Services Auth, Google Mobile Ads

---

## 📦 Building & Publishing APKs

The Gradle build script automatically generates custom-named APK files formatted as `Vaultra_v{version}_{buildType}.apk`.

### 1. Build Signed Release APK
Run the following Gradle task:
```bash
./gradlew assembleRelease
```
The output signed APK will be created at:
`app/build/outputs/apk/release/Vaultra_v1.0_release.apk`

### 2. Build Debug APK
Run the following Gradle task:
```bash
./gradlew assembleDebug
```
The output debug APK will be created at:
`app/build/outputs/apk/debug/Vaultra_v1.0_debug.apk`

### 3. Upload to GitHub Releases / APK Mirror
* Upload `Vaultra_v1.0_release.apk` to **GitHub Releases** or **APK Mirror**.
* Ensure your `versionCode` and `versionName` in [`app/build.gradle`](file:///E:/MK%20DigiTek/ValutraJava_v6_191012026_1100PM_New_UI_Theme_Selection/app/build.gradle) are incremented for future updates.
