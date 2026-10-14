# ஶ்ரீ ஏழைகாத்த அம்மன் வல்லடிகார சுவாமி திருக்கோவில், பல்லவராயன்பட்டி
## GitHub Actions மூலம் தானாக APK பில்ட் செய்து மொபைலில் பதிவிறக்கும் முழுமையான வழிகாட்டி (GitHub Actions Cloud APK Build & Download Guide)

---

### 🌟 முன்னுரை
உங்கள் சொந்தக் கணினியில் **Android Studio** போன்ற பெரிய மென்பொருட்களை நிறுவ வேண்டிய அவசியமே இல்லை! நீங்கள் கோவில் கணக்கு செயலிக் குறியீடுகளை (HTML, CSS, JS, Assets) **GitHub**-ல் பதிவேற்றம் செய்தவுடன், **GitHub Actions சேவையகம் தானாகவே கிளவுடில் (Cloud)** இயங்கி உங்கள் **Android APK (`app-debug.apk`)** கோப்பை உருவாக்கிவிடும்.

---

### 🚀 படி 1: GitHub களஞ்சியத்தில் CI/CD Workflow கோப்பை அமைத்தல்

உங்கள் திட்டத்தின் மூலத்தில் பின்வரும் கோப்புறையையும் கோப்பையும் உருவாக்கவும்:
`.github/workflows/build-apk.yml`

```yaml
name: Build Kovil Kanakku Android APK

on:
  push:
    branches: [ "main" ]          # main கிளையில் குறியீடு பதிவேறும் போது தானாக இயங்கும்
  workflow_dispatch:               # தேவைப்படும் போது "Run workflow" பொத்தான் மூலமும் இயக்கலாம்

jobs:
  build:
    name: Build Android APK
    runs-on: ubuntu-latest

    steps:
    - name: 1. குறியீட்டைப் பெறுதல் (Checkout Code)
      uses: actions/checkout@v4

    - name: 2. Node.js 20 நிறுவுதல்
      uses: actions/setup-node@v4
      with:
        node-version: 20

    - name: 3. Java JDK 17 அமைத்தல்
      uses: actions/setup-java@v4
      with:
        distribution: 'temurin'
        java-version: '17'

    - name: 4. திட்ட நூலகங்கள் & Capacitor நிறுவுதல்
      run: |
        npm install
        npm install -g @capacitor/cli

    - name: 5. Android தளத்தை இணைத்தல் & ஒத்திசைத்தல்
      run: |
        npx cap add android || true
        npx cap sync android

    - name: 6. Android APK கட்டமைத்தல் (Gradle Build)
      run: |
        cd android
        chmod +x gradlew
        ./gradlew assembleDebug --no-daemon

    - name: 7. உருவான APK-வை பதிவிறக்கத்திற்குப் பதிவேற்றுதல் (Upload Artifact)
      uses: actions/upload-artifact@v4
      with:
        name: Kovil-Kanakku-Debug-APK
        path: android/app/build/outputs/apk/debug/app-debug.apk
        retention-days: 14        # 14 நாட்கள் வரை பதிவிறக்கம் செய்யக் கிடைக்கும்
```

---

### 📤 படி 2: குறியீட்டை GitHub-க்கு பதிவேற்றுதல் (Push Code)

உங்கள் கணினியிலுள்ள Terminal அல்லது Git Bash-ல்:

```bash
git add .
git commit -m "Auto APK build setup: Kovil Kanakku Mobile App"
git push origin main
```

---

### ⚡ படி 3: GitHub-ல் APK தானாக உருவாவதைக் கவனித்தல் (Watching the Build)

1. உங்கள் இணைய உலாவியில் (Browser) **GitHub.com** திறந்து, உங்கள் கோவில் செயலிக் களஞ்சியத்திற்குச் செல்லவும் (Repository).
2. களஞ்சியத்தின் மேல் மெனுவில் **"Actions"** என்ற தாவலைத் (Tab) தொடவும்.
3. அங்கே **"Build Kovil Kanakku Android APK"** என்ற பணி இயங்கத் தொடங்குவதைக் காணலாம்:
   - 🟡 **மஞ்சள் நிற வட்டம் (In Progress):** கிளவுட் சர்வரில் APK உருவாகிறது (சுமார் 2 முதல் 4 நிமிடங்கள் எடுக்கும்).
   - 🟢 **பச்சை நிற சரி குறி (Passed / Success):** உங்கள் கோவில் கணக்கு மொபைல் APK வெற்றிகரமாகத் தயாராகிவிட்டது என்று பொருள்!

---

### 📲 படி 4: உருவான APK-வை மொபைல் அல்லது கணினியில் பதிவிறக்கும் முறை (Download APK)

1. பச்சை நிறச் சரி குறி வந்த அந்த **Workflow Run** பெயரைக் கிளிக் செய்து உள்ளே செல்லவும்.
2. அந்தப் பக்கத்தின் கீழ் பகுதியில் உள்ள **"Artifacts"** என்ற தலைப்பிற்குச் செல்லவும்.
3. அங்கே **`Kovil-Kanakku-Debug-APK`** என்ற பெயரில் ஒரு ஜிப் (ZIP) கோப்பு இருக்கும்.
4. அந்தப் பெயரைத் தொட்டதும், உங்கள் கோவில் கணக்கு மொபைல் செயலி உடனே பதிவிறக்கம் செய்யப்படும்!

---

### 📱 படி 5: மொபைலில் நிறுவுதல் (Installation on Phone)

1. பதிவிறக்கம் செய்த ஜிப் கோப்பைத் திறந்தால் (Unzip), அதனுள் **`app-debug.apk`** கோப்பு இருக்கும்.
2. இந்தக் கோப்பை உங்கள் மொபைலுக்கு **WhatsApp** அல்லது **Google Drive** வழியாக அனுப்பித் தொடவும்.
3. *"Install from unknown sources"* என்று அனுமதி கேட்டால் **"Allow / அனுமதி"** அளிக்கவும்.
4. இப்போது உங்கள் மொபைல் திரையில் **"ஶ்ரீ ஏழைகாத்த அம்மன் கோவில் கணக்கு"** அதிகாரப்பூர்வ செயலி இன்ஸ்டால் ஆகி இயங்கும்!

---

### 💡 கூடுதல் பயனுள்ள குறிப்பு (Workflow Dispatch):
எந்த நேரத்திலும் புதிய குறியீடு பதிவேற்றாமலேயே மீண்டும் புதிய APK உருவாக்க விரும்பினால்:
- **GitHub > Actions > Build Kovil Kanakku Android APK** கிளிக் செய்து, வலதுபுறம் உள்ள **"Run workflow"** பொத்தானை அழுத்தினால் உடனே புதிய APK உருவாகிவிடும்.
