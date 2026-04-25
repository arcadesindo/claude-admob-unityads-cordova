# claude-admob-unityads-cordova

Unity Ads mediation adapter Cordova plugin for Google AdMob.  
Designed to be used alongside **[community-admob-plus-cordova](https://github.com/EYALIN/community-admob-plus)** and the **Claude AdMob** Construct 3 plugin.

---

## What this plugin does

This is a **background/adapter-only** Cordova plugin. It has no JavaScript API.  
Its sole purpose is to inject the Unity Ads AdMob mediation adapter into your Android and iOS build, enabling Unity Ads to compete as a bidder in your AdMob mediation waterfall.

### Android
Adds the following Gradle dependency:
```gradle
implementation("com.google.ads.mediation:unity:4.17.0.0")
```

### iOS
Adds the following CocoaPod:
```ruby
pod 'GoogleMobileAdsMediationUnity', '~> 4.17.0.0'
```

---

## Requirements

| Requirement | Version |
|---|---|
| cordova | >= 9.0.0 |
| cordova-android | >= 9.0.0 |
| cordova-ios | >= 6.0.0 |
| community-admob-plus-cordova | >= 1.33.0 |
| Unity Ads adapter | >= 4.16.0.1 (open bidding) |

> ⚠️ **Open Bidding requires adapter 4.16.0.1 or higher.**  
> This plugin defaults to **4.17.0.0** which is the latest version as of April 2025.

---

## Installation (via Construct 3)

This plugin is meant to be used via the **Claude AdMob Unity Ads** Construct 3 add-on (`.c3addon`).  
Simply add the add-on to your Construct 3 project alongside **Claude AdMob**, and this Cordova plugin will be automatically included in your APK/IPA build.

---

## Manual Installation (Cordova CLI)

```bash
cordova plugin add claude-admob-unityads-cordova
```

With custom adapter version:
```bash
cordova plugin add claude-admob-unityads-cordova \
  --variable ANDROID_ADAPTER_VERSION=4.17.0.0 \
  --variable IOS_ADAPTER_VERSION=4.17.0.0
```

---

## Unity Ads Setup (IMPORTANT — Read Before Using)

For open bidding to work, you **must** complete the following steps in the Unity Ads and AdMob dashboards:

### Step 1 — Unity Ads Dashboard

1. Go to [Unity Ads Monetization Dashboard](https://dashboard.unity3d.com/monetization)
2. Create a new **Project** → select **"I will use Mediation"** → choose **"Google AdMob"** as mediation partner
3. Under **Placements**, create a new Ad Unit and select **Bidding** as the setup type
4. Note down your **Game ID** and **Bidding Placement ID**

> ⚠️ You cannot reuse a waterfall Placement ID for bidding. You must create a **new** Bidding Placement ID.

### Step 2 — AdMob Dashboard

1. Go to your AdMob ad unit → **Mediation** tab
2. Under the **Bidding** section, click **Add ad source** → select **Unity Ads**
3. Click **"Sign a partnership agreement"** to link your Unity Ads account
4. Enter your **Game ID** and **Bidding Placement ID** from Step 1

### Step 3 — Revenue Reporting

> ℹ️ Bidding revenue from Unity Ads is **paid by Google**, NOT by Unity.  
> Revenue will appear in your **AdMob/Google account**, not in the Unity Monetization Dashboard.

---

## Variables

| Variable | Default | Description |
|---|---|---|
| `ANDROID_ADAPTER_VERSION` | `4.17.0.0` | Unity Ads AdMob adapter version for Android |
| `IOS_ADAPTER_VERSION` | `4.17.0.0` | Unity Ads AdMob adapter version for iOS |

---

## Compatibility Table

| Adapter Version | Unity Ads SDK | Min AdMob SDK |
|---|---|---|
| 4.17.0.0 | 4.17.0 | 25.2.0 |
| 4.16.6.0 | 4.16.6 | 24.9.0 |
| 4.16.0.1 | 4.16.0 | 24.3.0 |

---

## License

MIT
