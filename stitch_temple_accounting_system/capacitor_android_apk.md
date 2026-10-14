# ஶ்ரீ ஏழைகாத்த அம்மன் வல்லடிகார சுவாமி திருக்கோவில், பல்லவராயன்பட்டி
## கோவில் கணக்கு மொபைல் செயலி - Capacitor மூலம் Android APK உருவாக்கும் முழுமையான வழிகாட்டி (Step-by-Step Guide)

---

### 📌 முன்னுரை
நமது கோவில் கணக்கு செயலியின் அனைத்து திரைகளும் (முகப்பு, தலைக்கட்டு வரி, செலவு, வவுச்சர், தணிக்கை அறிக்கை, WhatsApp பகிர்வு) ஏற்கனவே அதிநவீன **HTML, Tailwind CSS, JavaScript** கொண்டு முழுமையான மொபைல் UI ஆக உருவாக்கப்பட்டுள்ளன. 

**Capacitor (CapacitorJS)** தொழில்நுட்பத்தைப் பயன்படுத்தி, எந்தவொரு கூடுதல் மறு-குறியீட்டுத் தேவையும் இல்லாமல் (No re-coding needed), மிக எளிதாக **15 நிமிடங்களில்** நேரடி **Android APK (மற்றும் iOS App)** கோப்பாக மாற்ற முடியும்.

---

### 🛠️ தேவைப்படும் மென்பொருட்கள் (Prerequisites)
1. **Node.js (LTS Version)** - கணினியில் நிறுவவும் ([nodejs.org](https://nodejs.org))
2. **Android Studio** - ஆண்ட்ராய்டு APK கட்டமைக்க ([developer.android.com/studio](https://developer.android.com/studio))
3. **Java JDK 17 அல்லது 21** (Android Studio-வுடன் தானாகவே வரும்)

---

### 📂 படி 1: செயலிக் கோப்புகள் மற்றும் திட்டக் கட்டமைப்பு (Project Setup)

1. உங்கள் கணினியில் புதிய கோப்புறையை (Folder) உருவாக்கவும்:
   ```bash
   mkdir kovil-kanakku-app
   cd kovil-kanakku-app
   ```

2. திட்டத்தை ஆரம்பித்து (Initialize npm), Capacitor நூலகங்களை நிறுவவும்:
   ```bash
   npm init -y
   npm install @capacitor/core @capacitor/cli @capacitor/android
   ```

3. செயலிக் கோப்புகளை சேமிக்க `www` அல்லது `dist` என்ற கோப்புறையை உருவாக்கவும்:
   ```bash
   mkdir www
   ```
   > 💡 **குறிப்பு:** நமது கோவில் கணக்கு வலைத்தள HTML/CSS/JS திரைக் கோப்புகளை (முகப்புத் திரை `index.html`, இதர திரைகள், படங்கள் மற்றும் லோகோ `app-icon.png`) இந்த `www` ஃபோல்டருக்குள் நகலெடுக்கவும் (Copy-Paste).

---

### ⚙️ படி 2: Capacitor அமைப்புகளை அமைத்தல் (Capacitor Configuration)

Capacitor திட்டத்தை நமது கோவில் பெயருடன் துவக்கவும்:
```bash
npx cap init "Kovil Kanakku" "org.pallavarayanpatti.kovilkanakku" --web-dir www
```

திட்டத்தின் மூலத்தில் `capacitor.config.json` கோப்பு உருவாகும். அதில் கீழ்வரும் அமைப்புகள் உள்ளதா என சரிபார்க்கவும்:
```json
{
  "appId": "org.pallavarayanpatti.kovilkanakku",
  "appName": "ஶ்ரீ ஏழைகாத்த அம்மன் கோவில் கணக்கு",
  "webDir": "www",
  "bundledWebRuntime": false,
  "server": {
    "androidScheme": "https"
  }
}
```

---

### 🤖 படி 3: Android இயங்குதளத்தை இணைத்தல் (Add Android Platform)

1. Android தளத்தை இணைக்கவும்:
   ```bash
   npx cap add android
   ```
   *(இது திட்டத்திற்குள் ஒரு முழுமையான `android` ஸ்டுடியோ கோப்புறையை உருவாக்கும்)*

2. வலைக்கோப்புகளை Android தளத்திற்கு ஒத்திசைக்கவும் (Sync / Copy):
   ```bash
   npx cap copy
   npx cap sync
   ```

---

### 🖼️ படி 4: கோவில் ஆப் ஐகான் & ஸ்பிளாஷ் திரை பொருத்துதல் (App Icon & Splash Screen)

நாம் ஏற்கனவே உருவாக்கிய **அருள்மிகு அம்மன் & கோபுர திருவுருவ லோகோ (App Icon)** மற்றும் **ஸ்பிளாஷ் திரையை** தானாகவே அனைத்து ஆண்ட்ராய்டு அளவுகளுக்கும் உருவாக்க:

1. Capacitor Assets கருவியை நிறுவவும்:
   ```bash
   npm install @capacitor/assets --save-dev
   ```

2. மூலக் கோப்புறையில் `assets` என்ற ஃபோல்டரை உருவாக்கி, அதில்:
   - `assets/icon.png` (1024x1024 கோவில் ஆப் ஐகான்)
   - `assets/splash.png` (2732x2732 கோவில் ஸ்பிளாஷ் திரை)
   என சேமிக்கவும்.

3. ஐகான்களை தானாக உருவாக்க கட்டளையிடவும்:
   ```bash
   npx capacitor-assets generate --android
   ```

---

### 📱 படி 5: Android Studio-வில் திறந்து APK உருவாக்குதல் (Generate APK)

1. திட்டத்தை Android Studio-வில் திறக்கவும்:
   ```bash
   npx cap open android
   ```

2. Android Studio திறந்ததும், கீழே உள்ள Gradle Build தானாக முடிவடையும் வரை 1 நிமிடம் காத்திருக்கவும்.

3. **சோதனை APK (Debug APK) உருவாக்க:**
   - Android Studio மேல் மெனுவில் **Build > Build Bundle(s) / APK(s) > Build APK(s)** என்பதை அழுத்தவும்.
   - சில வினாடிகளில் build முடிந்து, கீழ் வலது மூலையில் *"APK(s) generated successfully"* என்ற அறிவிப்பு வரும். அதில் **"locate"** என்பதை அழுத்தினால்:
     `app/build/outputs/apk/debug/app-debug.apk` என்ற உங்கள் மொபைலில் இன்ஸ்டால் செய்யக்கூடிய APK தயாராகிவிடும்!

4. **வெளியீட்டு APK (Production / Release Signed APK) உருவாக்க:**
   - மேல் மெனுவில் **Build > Generate Signed Bundle / APK...** தேர்வு செய்யவும்.
   - **APK** என்பதைத் தேர்ந்தெடுத்து **Next** அழுத்தவும்.
   - கோவில் நிர்வாகத்திற்கான புதிய Keystore கடவுச்சொல்லை உருவாக்கி, **release** என்பதைத் தேர்ந்தெடுத்து **Finish** அழுத்தவும்.
   - இப்போது Play Store அல்லது வாட்ஸ்அப் மூலம் ஊர் மக்களுக்கு பகிரக்கூடிய அதிகாரப்பூர்வமான **`app-release.apk`** தயாராகிவிடும்!

---

### 📲 படி 6: மொபைலில் நிறுவுதல் (Installation on Mobile Phone)

1. உருவான `app-release.apk` அல்லது `app-debug.apk` கோப்பை உங்கள் வாட்ஸ்அப் அல்லது கூகுள் டிரைவ் மூலம் உங்கள் மொபைலுக்கு அனுப்பவும்.
2. மொபைலில் அதைத் தொட்டுத் திறக்கவும் (Open).
3. *"Install from Unknown Sources"* அனுமதி கேட்டால், *"Allow / அனுமதி"* கொடுக்கவும்.
4. இப்போது உங்கள் மொபைல் திரையில் **"ஶ்ரீ ஏழைகாத்த அம்மன் கோவில் கணக்கு"** என்ற நமது அழகிய கோவில் ஐகானுடன் மொபைல் செயலி இயங்கும்!

---

### 🌟 கூடுதல் நன்மைகள்:
* **ஆஃப்லைன் வசதி (Offline Support):** இணையம் இல்லாவிட்டாலும் உள்ளூர் தரவுகள் இயங்கும்.
* **நேரடி WhatsApp பகிர்வு:** ரசீது மற்றும் தணிக்கை அறிக்கைகளை மொபைலின் சொந்த WhatsApp மூலம் ஒரே க்ளிக்கில் அனுப்பலாம்.
* **அதிவேகம் & குறைவான அளவு:** இந்த APK அளவு வெறும் **3MB முதல் 5MB** மட்டுமே இருக்கும்.
