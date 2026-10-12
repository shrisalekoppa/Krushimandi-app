# 🌾 KrushiMandi App (ಕೃಷಿ ಮಂಡಿ / कृषि मंडी) — Version 2.0

> **Empowering Indian Farmers with Real-Time Mandi Commodity Intelligence, Variety Analytics, Harvest Sell Timing Advisor, Weather Risk Assessment & Offline-First Farm Operations.**

[![Android Version](https://img.shields.io/badge/Platform-Android-3DDC84.svg?logo=android&logoColor=white)](https://developer.android.com)
[![Kotlin](https://img.shields.io/badge/Kotlin-2.0.0-7F52FF.svg?logo=kotlin&logoColor=white)](https://kotlinlang.org)
[![Jetpack Compose](https://img.shields.io/badge/Jetpack%20Compose-M3-4285F4.svg?logo=jetpackcompose&logoColor=white)](https://developer.android.com/jetpack/compose)
[![Room Database](https://img.shields.io/badge/Database-Room%20%2F%20SQLite-FFA000.svg?logo=sqlite&logoColor=white)](https://developer.android.com/training/data-storage/room)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](LICENSE)
[![Release](https://img.shields.io/badge/Release-v2.0%20(Build%202)-success.svg)](https://github.com)

---

## 📑 Table of Contents

- [Overview](#-overview)
- [Key Features & Module Descriptions](#-key-features--module-descriptions)
  - [1. Live & Cached All-India Mandi Prices](#1-live--cached-all-india-mandi-prices)
  - [2. Commercial Plantation & Variety Sub-Catalog](#2-commercial-plantation--variety-sub-catalog)
  - [3. Harvest Sell-Timing Advisor & Weather Analytics](#3-harvest-sell-timing-advisor--weather-analytics)
  - [4. Storage ROI & Holding Profitability Calculator](#4-storage-roi--holding-profitability-calculator)
  - [5. Historical Price Trends & Interactive Charts](#5-historical-price-trends--interactive-charts)
  - [6. 24/7 Price Target Monitoring & Alerts](#6-247-price-target-monitoring--alerts)
  - [7. Farmer WhatsApp Bulletin & CSV Export](#7-farmer-whatsapp-bulletin--csv-export)
  - [8. Deep Multi-Language Native Support](#8-deep-multi-language-native-support)
  - [9. Offline-First Resilience](#9-offline-first-resilience)
  - [10. Google Agri Search & Knowledge Base](#10-google-agri-search--knowledge-base)
- [App Architecture & Directory Structure](#-app-architecture--directory-structure)
- [Database Schema & Data Models](#-database-schema--data-models)
- [Prerequisites & Build Guide](#-prerequisites--build-guide)
- [Uploading / Syncing to GitHub](#-uploading--syncing-to-github)
- [Release Notes — v2.0](#-release-notes--v20)

---

## 🌾 Overview

**KrushiMandi App** is a next-generation agricultural market intelligence Android application built specifically for Indian farmers, farmer producer organizations (FPOs), commission agents, and agricultural traders. 

In India, wholesale market rates across APMC (Agricultural Produce Market Committee) mandis can fluctuate drastically from day to day and district to district. Additionally, farm fields frequently face erratic cellular reception. **KrushiMandi App** bridges this information gap by:
1. Providing transparent, variety-level daily modal, minimum, and maximum rates.
2. Caching data locally in an embedded **Room SQLite database** for 100% offline access.
3. Offering intelligent harvest sell-timing advice driven by arrival volumes, moisture factors, and weather forecasts.
4. Enabling one-tap localized WhatsApp sharing with fellow growers and cooperatives.

---

## 🚀 Key Features & Module Descriptions

### 1. Live & Cached All-India Mandi Prices
- **Daily Rates**: Displays Modal (`₹ / Qtl`), Minimum, and Maximum prices per quintal for major agricultural markets across Karnataka, Maharashtra, Gujarat, Kerala, Tamil Nadu, Andhra Pradesh, and North Indian grain hubs.
- **Arrival Volumes**: Tracks daily inbound supply in quintals (Qtl) or bags to indicate market supply pressure.
- **Smart Filters**: Multi-tiered filtering by State, Commodity, Category, Variety sub-class, and Search query.
- **Price Gainers & Volatility**: Instant visual badges for price changes (`+₹` gain in green, `-₹` drop in red).

### 2. Commercial Plantation & Variety Sub-Catalog
Unlike generic trackers that lump varieties into single categories, KrushiMandi provides specialized sub-variety catalogs for high-value cash crops:
- **Areca Nut (ಅಡಿಕೆ / सुपारी)**:
  - *Rashi (ರಾಶಿ)*, *Bette (ಬೆಟ್ಟೆ)*, *Gorabalu (ಗೊರಬಲು)*, *Chali / Koka (ಚಾಲಿ / ಕೊಕಾ)*, *Api*, *Fabre*.
- **Coconut & Copra (ತೆಂಗಿನಕಾಯಿ / ಕೊಬ್ಬರಿ / नारियल)**:
  - *Mill Copra*, *Ball Copra (ಉಂಡೆ ಕೊಬ್ಬರಿ)*, *Tender Coconut*, *Grade-A Whole Nut*.
- **Cocoa (ಕೋಕೋ / कोको)**:
  - *Wet Beans (ಹಸಿ ಬೀಜ)*, *Dry Beans (ಒಣ ಬೀಜ)*, *CAMPCO Grade*.
- **Banana (ಬಾಳೆಹಣ್ಣು / केला)**:
  - *Yelakki / Puttabale (ಏಲಕ್ಕಿ ಬಾಳೆ)*, *Nendran (ನೇಂದ್ರನ್)*, *Robusta (ರೋಬಸ್ಟಾ)*, *Grand Naine (ಜಿ-9)*, *Red Banana (ಕೆಂಪು ಬಾಳೆ)*.
- **Spices & Condiments**:
  - *Black Pepper (ಕಾಳುಮೆಣಸು)*: Malabar Garbled, Ungarbled.
  - *Green Cardamom (ಏಲಕ್ಕಿ)*: 7mm, 8mm Bold.
  - *Ginger (ಶುಂಠಿ)*: Fresh Green, Dry Ginger (Shunti).
  - *Turmeric (ಅರಿಶಿನ)*: Finger, Bulb.
- **Cereals, Pulses & Oilseeds**:
  - *Wheat (Sharbati, Lokwan)*, *Paddy (Basmati 1121, Sona Masoori)*, *Soybean (Yellow)*, *Chana (Desi, Kabuli)*, *Mustard (Black, Yellow)*, *Cotton (Medium/Long Staple)*.

### 3. Harvest Sell-Timing Advisor & Weather Analytics
- **Recommendation Engine**: Categorizes market timing into:
  - `RECOMMENDED TO HOLD`: Supply drying up, price expected to rise.
  - `SELL NOW (RISK AHEAD)`: Inbound harvest flush or damp weather could crash local APMC rates.
  - `GOOD TIME TO SELL`: Favorable pricing window above 30-day moving average.
- **Weather Agri-Risk Alerts**: Highlights local rain risk, humidity impact on open-air drying yards (especially crucial for Arecanut and Black Pepper processing), and logistics delays.

### 4. Storage ROI & Holding Profitability Calculator
- Interactive financial tool allowing farmers to calculate whether it makes economic sense to store produce in a warehouse or cold storage vs. selling immediately at farm gate:
  - **Inputs**: Quantity (Quintals), Current Mandi Rate, Expected Holding Period (Months), Warehouse Fee per Month, Projected Future Mandi Rate.
  - **Outputs**: Total Warehousing Cost, Estimated Quality Shrinkage Loss, Net Gain / Loss per Quintal, Overall Holding Profit.

### 5. Historical Price Trends & Interactive Charts
- Visual price trends across customizable intervals: **7 Days**, **1 Month**, and **3 Months**.
- Displays high watermarks, low boundaries, and average trading ranges with clean Compose Canvas vector visualization.

### 6. 24/7 Price Target Monitoring & Alerts
- Create personalized price targets:
  - *“Notify me when Shimoga Areca Rashi rises above ₹56,000/Qtl”*
  - *“Notify me if Indore Soybean falls below ₹4,200/Qtl”*
- Status indicators (`Monitoring 24/7`, `Triggered`, `Paused`) with active badge counter in the top app bar.

### 7. Farmer WhatsApp Bulletin & CSV Export
- **One-Tap WhatsApp Bulletin**: Formats a clean, readable text report with emojis, mandi names, and prices ready to send to WhatsApp farming groups, cooperative societies, and APMC traders.
- **CSV Data Export**: Generate clean tabular CSV data for accounting, ledger keeping, or cooperative documentation.

### 8. Deep Multi-Language Native Support
- Seamless one-tap language switcher in the header:
  - **English (EN)**
  - **Kannada (ಕನ್ನಡ)** — Complete regional terms for Karnataka mandis (*ಬೆಟ್ಟೆ, ರಾಶಿ, ಗೊರಬಲು, ಕೊಬ್ಬರಿ, ಏಲಕ್ಕಿ*).
  - **Hindi (हिन्दी)** — Full vernacular support for Northern & Central Indian markets.

### 9. Offline-First Resilience
- Built with an embedded **Room SQLite Database**.
- Automatically seeds and updates cached records.
- Toggleable **Offline Field Mode**: lets users test or work strictly with offline records when travelling across low-connectivity fields.

### 10. Google Agri Search & Knowledge Base
- In-app Google Search screen configured for agricultural queries, MSP announcements, government schemes (PM-Kisan, PMFBY), pest alerts, and mandi market rules.

---

## 🏛️ App Architecture & Directory Structure

KrushiMandi follows Google's recommended Android MVVM (Model-View-ViewModel) and Clean Architecture principles:

```
KrushiMandi/
├── app/
│   ├── build.gradle.kts                # App-level dependencies, Room, Compose, SDK 36
│   └── src/
│       ├── main/
│       │   ├── AndroidManifest.xml     # Permissions & Application config
│       │   ├── java/com/example/
│       │   │   ├── MainActivity.kt     # Entry point with edge-to-edge Compose container
│       │   │   ├── data/
│       │   │   │   ├── local/          # Room Database, Daos, SQLite Entities
│       │   │   │   │   ├── AppDatabase.kt
│       │   │   │   │   ├── Daos.kt
│       │   │   │   │   └── Entities.kt
│       │   │   │   ├── localization/   # Multilingual taxonomy (EN, ಕನ್ನಡ, हिन्दी)
│       │   │   │   │   └── AppLanguage.kt
│       │   │   │   ├── model/          # Kotlin Domain Models & Crop Variety Catalog
│       │   │   │   │   ├── CropModels.kt
│       │   │   │   │   └── CropVarietyCatalog.kt
│       │   │   │   └── repository/     # Repository layer with Offline Cache & Sync logic
│       │   │   │       ├── MandiMockDataSource.kt
│       │   │   │       └── MandiRepository.kt
│       │   │   └── ui/
│       │   │       ├── MainAppScreen.kt # Navigation Scaffold & App-level State
│       │   │       ├── components/     # Reusable Compose Widgets
│       │   │       │   ├── LanguageSelector.kt
│       │   │       │   ├── MandiCardsAndFilters.kt
│       │   │       │   └── MandiChart.kt
│       │   │       ├── screens/        # Primary Feature Screens
│       │   │       │   ├── DashboardScreen.kt
│       │   │       │   ├── MarketPricesScreen.kt
│       │   │       │   ├── TrendsAnalyticsScreen.kt
│       │   │       │   ├── SellTimingAdvisorScreen.kt
│       │   │       │   ├── AlertsScreen.kt
│       │   │       │   ├── ReportsExportScreen.kt
│       │   │       │   ├── ProfileScreen.kt
│       │   │       │   └── GoogleSearchScreen.kt
│       │   │       ├── theme/          # Material 3 Color Palette, Typography & Shapes
│       │   │       │   ├── Color.kt
│       │   │       │   ├── Theme.kt
│       │   │       │   └── Type.kt
│       │   │       └── viewmodel/      # Centralized UI StateFlow Management
│       │   │           └── MandiViewModel.kt
│       │   └── res/
│       │       ├── drawable/           # Custom Adaptive Agricultural Icons
│       │       │   ├── ic_launcher_background.xml
│       │       │   └── ic_launcher_foreground.xml
│       │       └── values/
│       │           ├── colors.xml
│       │           ├── strings.xml     # App launcher name: "KrushiMandi App"
│       │           └── themes.xml
├── build.gradle.kts                    # Top-level Gradle config
├── settings.gradle.kts                 # Project name: "KrushiMandi App"
├── metadata.json                       # AI Studio Platform sync metadata
└── README.md                           # Project documentation (this file)
```

---

## 🗄️ Database Schema & Data Models

The app persists structured data offline using Room:

1. **`mandi_records` table**:
   - `id`: Unique identifier (String primary key).
   - `commodity`: Crop name (e.g., `Areca Nut`, `Coconut`, `Soybean`).
   - `variety`: Sub-variety (e.g., `Rashi`, `Ball Copra`, `Yellow`).
   - `market`: APMC Mandi name (e.g., `Shivamogga`, `Sagar`, `Indore`).
   - `district` & `state`: Geographic location.
   - `minPrice`, `maxPrice`, `modalPrice`: Double rates (`₹ / Qtl`).
   - `arrivals`: Double (Volume in Quintals).
   - `date`: Timestamp string.
   - `isFavorite`: Boolean flag for quick farmer watchlist.
   - `priceHistoryJson`: Serialized historical price points for 7D/1M/3M charts.

2. **`price_alerts` table**:
   - `id`, `cropName`, `marketName`, `targetPrice`, `isAbove`, `isActive`, `createdTimestamp`.

3. **`sync_meta` table**:
   - Tracks cache timestamps, total cached records count, and offline mode preferences.

---

## 🛠️ Prerequisites & Build Guide

### Prerequisites
- **Android Studio**: Ladybug (2024.2.1) or newer.
- **JDK**: Java 17 or Java 21.
- **Android SDK**: API 36 (target), API 24+ (minimum supported).

### Building via Command Line
```bash
# Clone the repository
git clone https://github.com/shrisalekoppa/krushimandi-app.git
cd krushimandi-app

# Build Debug APK
gradle assembleDebug

# Run Robolectric & Unit Tests
gradle :app:testDebugUnitTest
```

The compiled APK will be generated at:
```
app/build/outputs/apk/debug/app-debug.apk
```

---

## 📤 Uploading / Syncing to GitHub

To push this project to your GitHub account (`shrisalekoppa`) as a new repository named **`krushimandi-app`**:

### Option 1: 1-Click Export via Google AI Studio (Recommended)
1. In the Google AI Studio top toolbar, click on the **Settings** or **Export** icon.
2. Select **"Push to GitHub"** (or **"Export to GitHub"**).
3. Connect your GitHub account (`shrisalekoppa@gmail.com`).
4. Type the new repository name: **`krushimandi-app`**.
5. Select **Public** or **Private**, and click **Create & Push**.
   *AI Studio will automatically create the remote repo and push all branches and commits!*

### Option 2: Push via Local Git CLI
The workspace is pre-initialized with a clean commit on branch `main`. If you have a GitHub Personal Access Token or SSH key:
```bash
# Add your remote GitHub repo URL
git remote add origin https://github.com/shrisalekoppa/krushimandi-app.git

# Push to your new repository
git push -u origin main
```

---

## 📦 Release Notes — v2.0 (Build 2)

- **New App Branding**: Renamed to **KrushiMandi App** (ಕೃಷಿ ಮಂಡಿ / कृषि मंडी) across manifests, resources, and platform metadata.
- **Version Code 2 & Version Name 2.0**: Official release update in `app/build.gradle.kts`.
- **Specialized Commercial Crops**: Deep catalog support for Areca Nut varieties (Rashi, Bette, Gorabalu, Chali), Coconut (Mill/Ball Copra), Cocoa, Bananas, Spices, and Cash Crops.
- **Offline Room Database**: Full offline caching with automated schema migration and sync metadata.
- **Sell-Timing & Weather Risk Engine**: Multi-factor decision support to maximize harvest profits and protect crops from post-harvest weather hazards.
- **Storage ROI Calculator**: Quantitative financial holding analyzer for warehouse rentals.
- **Trilingual UI**: 100% native localization in English, Kannada, and Hindi.
- **Repository-Ready**: Includes pre-configured `.gitignore`, clean git commit history, and comprehensive documentation.

---

### 👨‍🌾 Designed for the Hardworking Farmers of India
*Empowering agriculture through transparent data, modern technology, and accessible design.*
