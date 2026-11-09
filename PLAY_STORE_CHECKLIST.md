# Google Play Store & AdMob Publishing Checklist for PaperScan

This folder (`play_store_publish/`) contains all necessary production build outputs, privacy policy, and store metadata to publish **PaperScan: Smart PDF Scanner** on the Google Play Store with Google AdMob monetisation active.

---

## 📁 Folder Structure

| File / Folder | Description |
| :--- | :--- |
| `build_outputs/app-release.aab` | **Production Android App Bundle** ready to upload to Play Console. |
| `build_outputs/app-release-unsigned.apk` | Production release APK output. |
| `STORE_LISTING.md` | Play Store text metadata (Title, Short/Full Description, Data Safety). |
| `PRIVACY_POLICY.md` | Markdown version of the Privacy Policy including AdMob disclosures. |
| `privacy_policy.html` | HTML version of Privacy Policy ready to host on GitHub Pages/Netlify. |
| `create_keystore.bat` | Windows batch script helper to generate your release signing keystore. |

---

## 🔑 Configured Production AdMob IDs

Your app is configured with **Production Mode Enabled** (`USE_TEST_ADS = false` in `AdConfig.kt`).

- **App ID (in `AndroidManifest.xml`)**: `ca-app-pub-1548750780670967~3956572125`
- **Banner Ad Unit ID**: `ca-app-pub-1548750780670967/8893379047`
- **Interstitial Ad Unit ID**: `ca-app-pub-1548750780670967/4836594868`
- **Rewarded Video Ad Unit ID**: `ca-app-pub-1548750780670967/4836594868`
- **Native Ad Unit ID**: `ca-app-pub-1548750780670967/9915475813`

---

## 🚀 Step-by-Step Publishing Guide

### Step 1: Sign the Android App Bundle
1. Run `create_keystore.bat` or generate a keystore in Android Studio (**Build > Generate Signed Bundle / APK**).
2. Sign `play_store_publish/build_outputs/app-release.aab`.

### Step 2: Upload to Google Play Console
1. Go to [Google Play Console](https://play.google.com/console).
2. Click **Create app** and name it `PaperScan: Smart PDF Scanner`.
3. Go to **Production > Create new release**.
4. Upload the signed `app-release.aab`.

### Step 3: Complete Play Store Listing & Declarations
1. Open `STORE_LISTING.md` and copy over Title, Short Description, and Full Description.
2. Under **App Content > Ads**, select **Yes, my app contains ads**.
3. Under **App Content > Data Safety**, select **Yes** (Device IDs collected/shared for advertising via Google AdMob).
4. Under **Privacy Policy**, paste the public URL of your hosted `privacy_policy.html`.

### Step 4: Link AdMob Account (Post-Publishing)
1. Once your app is published and live on Play Store, open your [Google AdMob Console](https://admob.google.com).
2. Go to **App settings**.
3. Under **App store details**, click **Add**.
4. Search for `com.paperscan.smart.pdf` or `PaperScan` and select your app.
5. AdMob will change **Approval status** from `Requires review` to `Approved`, and live ads will start serving to your users!
