# Scirra Build Service Whitelist Request
## Template GitHub Issue

---

**Title:**
```
[Build Service] Please whitelist Cordova plugins: claude-admob-unityads-cordova
```

---

**Body:**

Hi @AshleyScirra and the Scirra team,

I've developed a Construct 3 AdMob mediation plugin and need the following Cordova plugin(s) whitelisted in the build service:

---

### Plugin 1 — Main AdMob Plugin (already whitelisted, for reference)

| Field | Value |
|---|---|
| **Package ID** | `community-admob-plus-cordova` |
| **Version** | `1.33.2` |
| **npm** | https://www.npmjs.com/package/community-admob-plus-cordova |
| **Status** | ✅ Already whitelisted (used by other plugins) |

---

### Plugin 2 — Unity Ads Adapter (NEW — requesting whitelist)

| Field | Value |
|---|---|
| **Package ID** | `claude-admob-unityads-cordova` |
| **Version** | `1.0.0` |
| **npm** | https://www.npmjs.com/package/claude-admob-unityads-cordova |
| **GitHub** | https://github.com/arcadesindo/claude-admob-unityads-cordova |
| **License** | MIT |
| **Platforms** | Android, iOS |

**What it does:**  
This is a background-only Cordova adapter plugin with no JavaScript API. It injects the Unity Ads AdMob mediation adapter into the Android/iOS build via a single Gradle dependency and CocoaPod:

- **Android:** `com.google.ads.mediation:unity:4.17.0.0` (Google's official Maven)
- **iOS:** `pod 'GoogleMobileAdsMediationUnity', '~> 4.17.0.0'` (Google's official CocoaPod)

Both dependencies are hosted on **Google's official repositories** (Google Maven / CocoaPods). There are no third-party or unknown sources involved.

**Why it's needed:**  
The Unity Ads adapter must be a separate Cordova plugin so that developers can opt-in to Unity Ads mediation without it being bundled into every APK by default. Only developers who add the `Claude AdMob Unity Ads` Construct 3 add-on will have this adapter included in their build.

**Safety:**  
- ✅ Open source (MIT license, full source on GitHub)  
- ✅ No JavaScript/runtime code — purely build-time dependency injection  
- ✅ Dependencies from Google's official repositories only  
- ✅ No ad revenue sharing or SDK obfuscation  

---

### C3 Add-on

The Construct 3 add-on that references this plugin is named **"Claude AdMob Unity Ads"** (ID: `Claude_AdMob_UnityAds`).

---

Please let me know if you need any additional information. Thank you!
