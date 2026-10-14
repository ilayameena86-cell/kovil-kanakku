# ஶ்ரீ ஏழைகாத்த அம்மன் வல்லடிகார சுவாமி திருக்கோவில், பல்லவராயன்பட்டி
## கோவில் கணக்கு செயலி — முழுமையான ZIP கோப்புத் தொகுப்பு & பதிவிறக்கம் (Full Project ZIP Export Bundle)

வணக்கம்! நமது **ஶ்ரீ ஏழைகாத்த அம்மன் வல்லடிகார சுவாமி திருக்கோவில் (பல்லவராயன்பட்டி)** கணக்கு நிர்வாகச் செயலிக்கான அனைத்து HTML திரைகள், JavaScript தர்க்கங்கள், தரவு கட்டமைப்புகள், ஆப் ஐகான், அம்மன் தரிசனப் படங்கள் மற்றும் GitHub Actions / Capacitor கட்டமைப்பு கோப்புகள் அடங்கிய முழுமையான ZIP தொகுப்பு வழிகாட்டி கீழே கொடுக்கப்பட்டுள்ளது.

---

### 📥 1. Stitch தளத்திலிருந்து ஒட்டுமொத்த ZIP கோப்பை ஒரே கிளிக்கில் பதிவிறக்கும் முறை:

1. **மேல் வலது மூலையில் உள்ள Export / பதிவிறக்க பொத்தான்:**
   - தங்களின் திரையின் மேல் வலது மூலையில் (Top Right Corner) உள்ள **Export** (அல்லது **Code / Download**) ஐகானைத் தொடவும்.
2. **Download as ZIP:**
   - அதில் உள்ள **"Download as ZIP"** அல்லது **"Export Project"** என்பதைத் தேர்ந்தெடுக்கவும்.
   - உடனடியாக உங்கள் கணினியில் **`kovil-kanakku-project.zip`** என்ற பெயரில் அனைத்து 20+ திரைகளும், சிஎஸ்எஸ், ஜாவாஸ்கிரிப்ட் மற்றும் படங்களுடன் ஒரே ஜிப் கோப்பாகப் பதிவிறக்கப்பட்டுவிடும்!

---

### 📦 2. ZIP கோப்பில் அடங்கியுள்ள முழுமையான திட்டக் கட்டமைப்பு (Project Structure):

```text
kovil-kanakku-project.zip
│
├── README.md                                  # முழுமையான திட்ட வழிகாட்டி & ஆவணங்கள்
├── package.json                               # Capacitor & npm நூலகங்கள்
├── capacitor.config.json                      # Capacitor முதன்மை Android & iOS உள்ளமைவு
│
├── .github/
│   └── workflows/
│       └── build-apk.yml                      # GitHub Actions மூலம் தானாக APK உருவாக்கும் CI/CD
│
├── assets/                                    # கோவில் மொபைல் ஆப் ஐகான் & புகைப்படங்கள்
│   ├── icon.png                               # 1024x1024 px கோவில் ஆப் ஐகான் லோகோ
│   ├── splash.png                             # 2732x2732 px ஸ்பிளாஷ் திரை பின்னணி
│   ├── amman-moolavar.jpg                     # மூலவர் அருள்மிகு ஏழைக்காத்த அம்மன் திருமேனி
│   ├── temple-gopuram.jpg                     # கோவில் கோபுரத் திருப்பணித் தோற்றம்
│   └── word-art-banner.png                    # 3D கோல்டன் தேவஸ்தான Word Art பேனர்
│
└── www/                                       # செயலியின் அனைத்து UI HTML திரைக் கோப்புகள்
    ├── index.html                             # முதன்மை ஆப் மையம் & சிங்கிள் பேஜ் ரூட்டர் (Router)
    │
    ├── splash.html                            # மொபைல் ஆப் ஸ்பிளாஷ் & லாகின் தொடக்கத் திரை
    ├── admin-dashboard.html                   # முதன்மை நிர்வாகி முகப்புத் திரை
    ├── public-dashboard.html                  # பொதுமக்கள் பார்வை மட்டும் (Read-Only) முகப்பு
    ├── darshan-views.html                     # மூலவர் & கோபுரம் திருக்காட்சி முகப்பு
    │
    ├── tax-entry.html                         # தலைக்கட்டு வரி பதிவு (கரை & தொலைபேசி தானியங்கி)
    ├── karai-family-registry.html             # 8 கரைகள் & குடும்பப் பதிவேடு மேலாண்மை
    ├── pending-vari-list.html                 # தலைக்கட்டு வரி நிலுவை பட்டியல் (Pending List)
    ├── festival-income-entry.html             # திருவிழா, நன்கொடை & உண்டியல் வரவு பதிவு
    ├── receipt-modal.html                     # ரசீது பதிவு உறுதிப்படுத்தல் பாப்-அப்
    │
    ├── expense-voucher.html                   # கோவில் செலவு பதிவு - திருப்பணி & திருவிழா வவுச்சர் முறை
    ├── expense-audit.html                     # மாதாந்திர & திருவிழா வாரியான மொத்த செலவு அறிக்கை
    │
    ├── balance-sheet.html                     # வரவு-செலவு இருப்புநிலை & CA தணிக்கை அறிக்கை (Audit)
    ├── festival-comparison.html               # திருவிழா வாரியான வரவு-செலவு ஒப்பீட்டு அறிக்கை
    ├── daily-cash-closing.html                # அன்றாட ரொக்க இருப்பு & தேதி வாரியான வசூல் அறிக்கை
    ├── export-reports.html                    # Excel (.xlsx) & PDF அறிக்கைகள் பதிவிறக்க மையம்
    │
    ├── whatsapp-broadcast.html                # ஊர் மக்களுக்கு வாட்ஸ்அப் பல்க் அறிவிப்பு & செய்தி
    ├── whatsapp-audit-share.html              # தணிக்கை அறிக்கை வாட்ஸ்அப் பகிர்வு முன்னோட்டம்
    ├── whatsapp-receipt.html                  # பக்தர்களுக்கான வாட்ஸ்அப் வண்ண மின்-ரசீது
    ├── whatsapp-reminder.html                 # நிலுவை தலைக்கட்டு வரி வாட்ஸ்அப் நினைவூட்டல்
    │
    ├── settings-master.html                   # அமைப்புகள் - திருவிழா, கரை, செலவு தலைப்புகள் மேலாண்மை
    ├── add-karai-modal.html                   # புதிய கரை / திருவிழா சேர்க்கும் பாப்-அப்
    ├── admin-users.html                       # நிர்வாகிகள் பயனர்பெயர் & கடவுச்சொல் அமைப்புகள்
    └── deactivated-admins.html                # முடக்கப்பட்ட நிர்வாகிகள் & மீண்டும் இயக்குதல்
```

---

### 💻 3. ZIP-ல் உள்ள முதன்மைக் கோப்புகளின் குறியீடுகள் (Core Configuration Files):

#### 📄 `package.json`
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
  "dependencies": {
    "@capacitor/android": "^6.1.2",
    "@capacitor/core": "^6.1.2"
  },
  "devDependencies": {
    "@capacitor/assets": "^3.0.5",
    "@capacitor/cli": "^6.1.2"
  },
  "author": "ஶ்ரீ ஏழைகாத்த அம்மன் தேவஸ்தான நிர்வாகம், பல்லவராயன்பட்டி",
  "license": "MIT"
}
```

#### ⚙️ `capacitor.config.json`
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

#### 🤖 `.github/workflows/build-apk.yml` (தானியங்கி GitHub Cloud APK பில்டர்)
```yaml
name: Build Kovil Kanakku Android APK

on:
  push:
    branches: [ "main" ]
  workflow_dispatch:

jobs:
  build:
    name: Build Android APK
    runs-on: ubuntu-latest

    steps:
    - name: Checkout Code
      uses: actions/checkout@v4

    - name: Setup Node.js 20
      uses: actions/setup-node@v4
      with:
        node-version: 20

    - name: Setup Java JDK 17
      uses: actions/setup-java@v4
      with:
        distribution: 'temurin'
        java-version: '17'

    - name: Install Dependencies
      run: |
        npm install
        npm install -g @capacitor/cli

    - name: Add Android Platform & Sync
      run: |
        npx cap add android || true
        npx cap sync android

    - name: Build Android Debug APK
      run: |
        cd android
        chmod +x gradlew
        ./gradlew assembleDebug --no-daemon

    - name: Upload APK Artifact
      uses: actions/upload-artifact@v4
      with:
        name: Kovil-Kanakku-Debug-APK
        path: android/app/build/outputs/apk/debug/app-debug.apk
        retention-days: 14
```

---

### 🚀 4. GitHub-ல் இந்த ZIP கோப்புகளைப் பதிவேற்றி APK பெறும் எளிய 3 படிகள்:

1. பதிவிறக்கிய ZIP கோப்பை உங்கள் கணினியில் அன்ஜிப் (Extract) செய்யவும்.
2. உங்கள் கணினியின் Terminal அல்லது Git Bash-ல்:
   ```bash
   git init
   git add .
   git commit -m "Upload Kovil Kanakku full project bundle"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/kovil-kanakku-mobile-app.git
   git push -u origin main
   ```
3. GitHub பக்கத்தில் **"Actions"** பகுதிக்குச் சென்றால், 2 நிமிடங்களில் **`Kovil-Kanakku-Debug-APK`** தயாராகிவிடும். அதைத் தொட்டு உங்கள் மொபைலில் இன்ஸ்டால் செய்து கொள்ளலாம்!
