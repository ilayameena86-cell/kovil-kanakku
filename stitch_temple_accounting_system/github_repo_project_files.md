# ஶ்ரீ ஏழைகாத்த அம்மன் வல்லடிகார சுவாமி திருக்கோவில், பல்லவராயன்பட்டி
## கோவில் கணக்கு மொபைல் செயலி — முழுமையான GitHub Repository & Project Files கட்டமைப்பு

இந்த ஆவணம் உங்கள் திட்டத்தை **GitHub**-ல் பதிவேற்றம் செய்து, **Capacitor Android / iOS APK** உருவாக்கத் தேவையான அனைத்து மூலக் கோப்புகளையும் (Files), கோப்புறைகளையும் (Folders) மற்றும் கட்டமைப்பு விபரங்களையும் வழங்குகிறது.

---

### 📂 GitHub களஞ்சியத்தின் முழுமையான கோப்பு வரிசை (GitHub Repository Structure)

```text
kovil-kanakku-mobile-app/
│
├── .gitignore                                 # Git தேவையற்ற கோப்புகளைத் தவிர்க்க
├── README.md                                  # முழுமையான திட்ட வழிகாட்டி மற்றும் அமைக்கும் முறை
├── package.json                               # திட்டத்தின் npm நூலகங்கள் மற்றும் கட்டளைகள்
├── capacitor.config.json                      # Capacitor முதன்மை உள்ளமைவுக் கோப்பு
│
├── .github/
│   └── workflows/
│       └── build-apk.yml                      # GitHub Actions மூலம் தானாக APK உருவாக்கும் CI/CD Script
│
├── assets/                                    # கோவில் மொபைல் ஆப் ஐகான் & ஸ்பிளாஷ் புகைப்படங்கள்
│   ├── icon.png                               # 1024x1024 px கோவில் ஆப் ஐகான் (கோபுரம் & அம்மன் லோகோ)
│   ├── splash.png                             # 2732x2732 px ஸ்பிளாஷ் திரை பின்னணி
│   ├── amman-moolavar.jpg                     # அருள்மிகு ஏழைக்காத்த அம்மன் திருமேனி
│   └── temple-gopuram.jpg                     # கோவில் கோபுரத் திருப்பணி தோற்றம்
│
└── www/                                       # மொபைல் செயலியின் அனைத்து UI திரைக் கோப்புகள்
    ├── index.html                             # முதன்மை ஆப் மையம் & SPA திரை வழிநடத்தி (Router)
    ├── css/
    │   └── tailwind.min.css                   # ஸ்டைலிங் கோப்பு
    ├── js/
    │   ├── app.js                             # ஆப் இயக்கம் & திரை வழிநடத்துதல் (Routing & LocalStorage)
    │   └── data.js                            # கரைகள், திருவிழாக்கள் & தொடக்கத் தரவுகள்
    │
    ├── splash.html                            # ஸ்பிளாஷ் & லாகின் தொடக்கத் திரை
    ├── admin-dashboard.html                   # முதன்மை நிர்வாகி முகப்புத் திரை
    ├── public-dashboard.html                  # பொதுமக்கள் பார்வை மட்டும் முகப்பு (Read-Only)
    ├── darshan-views.html                     # மூலவர் & கோபுரம் திருக்காட்சி முகப்பு
    │
    ├── tax-entry.html                         # தலைக்கட்டு வரி பதிவு (கரை & தொலைபேசி தானியங்கி)
    ├── karai-family-registry.html             # 8 கரைகள் & குடும்பப் பதிவேடு மேலாண்மை
    ├── pending-vari-list.html                 # தலைக்கட்டு வரி நிலுவை பட்டியல்
    ├── festival-income-entry.html             # திருவிழா, நன்கொடை & உண்டியல் வரவு பதிவு
    ├── receipt-modal.html                     # ரசீது பதிவு உறுதிப்படுத்தல் பாப்-அப்
    │
    ├── expense-voucher.html                   # கோவில் செலவு பதிவு - வவுச்சர் முறை
    ├── expense-audit.html                     # மாதாந்திர & திருவிழா வாரியான மொத்த செலவு அறிக்கை
    │
    ├── balance-sheet.html                     # வரவு-செலவு இருப்புநிலை & CA தணிக்கை அறிக்கை
    ├── festival-comparison.html               # திருவிழா வாரியான வரவு-செலவு ஒப்பீட்டு அறிக்கை
    ├── daily-cash-closing.html                # அன்றாட ரொக்க இருப்பு & வசூல் அறிக்கை
    ├── export-reports.html                    # Excel (.xlsx) & PDF அறிக்கைகள் பதிவிறக்க மையம்
    │
    ├── whatsapp-broadcast.html                # வாட்ஸ்அப் பல்க் அறிவிப்பு & செய்தி மையம்
    ├── whatsapp-audit-share.html              # தணிக்கை அறிக்கை வாட்ஸ்அப் பகிர்வு முன்னோட்டம்
    ├── whatsapp-receipt.html                  # பக்தர்களுக்கான வாட்ஸ்அப் வண்ண மின்-ரசீது
    ├── whatsapp-reminder.html                 # நிலுவை தலைக்கட்டு வரி வாட்ஸ்அப் நினைவூட்டல்
    │
    ├── settings-master.html                   # அமைப்புகள் - திருவிழா, கரை, செலவு தலைப்புகள்
    ├── add-karai-modal.html                   # புதிய கரை / திருவிழா சேர்க்கும் பாப்-அப்
    ├── admin-users.html                       # நிர்வாகிகள் பயனர்பெயர் & கடவுச்சொல் அமைப்புகள்
    └── deactivated-admins.html                # முடக்கப்பட்ட நிர்வாகிகள் & மீண்டும் இயக்குதல்
```

---

### 📄 1. `.gitignore` கோப்பு
```gitignore
# Node dependencies
node_modules/
npm-debug.log

# Capacitor & Android build artifacts
android/app/build/
android/.gradle/
android/local.properties
android/.idea/
*.apk
*.aab

# OS files
.DS_Store
Thumbs.db
```

---

### 📄 2. `package.json` கோப்பு
```json
{
  "name": "kovil-kanakku-mobile-app",
  "version": "1.0.0",
  "description": "ஶ்ரீ ஏழைகாத்த அம்மன் வல்லடிகார சுவாமி திருக்கோவில், பல்லவராயன்பட்டி - கோவில் கணக்கு மொபைல் செயலி",
  "main": "www/index.html",
  "scripts": {
    "start": "npx serve www",
    "build": "npx cap copy && npx cap sync",
    "generate:assets": "npx capacitor-assets generate --android",
    "open:android": "npx cap open android"
  },
  "keywords": ["temple", "accounts", "capacitor", "android", "tamil-nadu"],
  "author": "ஶ்ரீ ஏழைகாத்த அம்மன் தேவஸ்தான நிர்வாகம், பல்லவராயன்பட்டி",
  "license": "MIT",
  "dependencies": {
    "@capacitor/android": "^6.1.2",
    "@capacitor/core": "^6.1.2"
  },
  "devDependencies": {
    "@capacitor/assets": "^3.0.5",
    "@capacitor/cli": "^6.1.2"
  }
}
```

---

### 📄 3. `capacitor.config.json` கோப்பு
```json
{
  "appId": "org.pallavarayanpatti.kovilkanakku",
  "appName": "ஶ்ரீ ஏழைகாத்த அம்மன் கோவில் கணக்கு",
  "webDir": "www",
  "bundledWebRuntime": false,
  "server": {
    "androidScheme": "https"
  },
  "plugins": {
    "SplashScreen": {
      "launchShowDuration": 2000,
      "backgroundColor": "#7a1c1c",
      "androidSplashResourceName": "splash",
      "androidScaleType": "CENTER_CROP"
    }
  }
}
```

---

### 🤖 4. தானியங்கி Android APK பில்ட் ஸ்கிரிப்ட் (`.github/workflows/build-apk.yml`)
GitHub-ல் நீங்கள் கோப்புகளைப் பதிவேற்றியதும், உங்கள் கணினியில் Android Studio இல்லாவிட்டாலும் கூட **GitHub Actions Server மூலமாகவே தானாக APK உருவாக்க** உதவும் CI/CD கோப்பு:

```yaml
name: Build Temple App APK

on:
  push:
    branches: [ "main" ]
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout Code
      uses: actions/checkout@v4

    - name: Set up Node.js
      uses: actions/setup-node@v4
      with:
        node-version: 20

    - name: Set up JDK 17
      uses: actions/setup-java@v4
      with:
        distribution: 'temurin'
        java-version: '17'

    - name: Install Dependencies
      run: |
        npm install
        npm install -g @capacitor/cli

    - name: Initialize Android Platform
      run: |
        npx cap add android
        npx cap sync android

    - name: Build Android Debug APK
      run: |
        cd android
        chmod +x gradlew
        ./gradlew assembleDebug

    - name: Upload APK Artifact
      uses: actions/upload-artifact@v4
      with:
        name: Kovil-Kanakku-App-Debug-APK
        path: android/app/build/outputs/apk/debug/app-debug.apk
```

---

### 💻 5. GitHub-ல் பதிவேற்றம் செய்வதற்கான Git கட்டளைகள்:

```bash
# 1. புதிய களஞ்சியத்தை உங்கள் கணினியில் துவக்குங்கள்
git init
git add .
git commit -m "Initial commit: Kovil Kanakku complete mobile app project"

# 2. உங்கள் GitHub Repo லிங்க்கை இணைக்கவும்
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/kovil-kanakku-mobile-app.git

# 3. GitHub-க்கு பதிவேற்றவும்
git push -u origin main
```
