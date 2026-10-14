# ஶ்ரீ ஏழைகாத்த அம்மன் வல்லடிகார சுவாமி திருக்கோவில், பல்லவராயன்பட்டி
## கோவில் கணக்கு செயலி — முழுமையான ZIP திட்டக் கட்டமைப்பு & கோப்புத் தொகுப்பு (Project ZIP Bundle Structure & Export Guide)

---

### 📦 முழுமையான திட்டக் கட்டமைப்பு (Complete Project ZIP Directory Structure)

கீழே கொடுக்கப்பட்டுள்ள முழுமையான கோப்பு அமைப்பில் உங்கள் திட்டத்தை ஒரு ZIP கோப்பாக நீங்கள் ஒழுங்கமைக்கலாம்:

```text
kovil-kanakku-project.zip
│
├── README.md                                  # முழுமையான திட்ட வழிகாட்டி & ஆவணங்கள்
├── package.json                               # Capacitor & npm சார்ந்த கட்டமைப்பு நூலகங்கள்
├── capacitor.config.json                      # Capacitor முதன்மை Android & iOS உள்ளமைவு
│
├── assets/                                    # கோவில் மொபைல் ஆப் ஐகான் & ஸ்பிளாஷ் படங்கள்
│   ├── icon.png                               # 1024x1024 px கோவில் ஆப் ஐகான் (கோபுரம் & அம்மன் லோகோ)
│   ├── splash.png                             # 2732x2732 px முழு ஸ்பிளாஷ் திரை பின்னணி
│   ├── amman-moolavar.jpg                     # மூலவர் அருள்மிகு ஏழைக்காத்த அம்மன் திருமேனி
│   ├── temple-gopuram.jpg                     # கோவில் கோபுரத் திருப்பணித் தோற்றம்
│   └── word-art-banner.png                    # 3D கோல்டன் தேவஸ்தான Word Art பேனர்
│
└── www/                                       # மொபைல் செயலியின் அனைத்து UI HTML திரைக் கோப்புகள்
    ├── index.html                             # முதன்மை ஆப் மையம் & சிங்கிள் பேஜ் ரூட்டர் (Router)
    ├── splash.html                            # மொபைல் ஆப் ஸ்பிளாஷ் & லாகின் தொடக்கத் திரை
    ├── admin-dashboard.html                   # முதன்மை நிர்வாகி முகப்புத் திரை
    ├── public-dashboard.html                  # பொதுமக்கள் பார்வை மட்டும் (Read-Only) முகப்பு
    ├── darshan-views.html                     # மூலவர் & கோபுரம் திருக்காட்சி முகப்பு
    │
    ├── tax-entry.html                         # தலைக்கட்டு வரி பதிவு (கரை & மொபைல் எண் தானியங்கி)
    ├── karai-family-registry.html             # 8 கரைகள் மற்றும் குடும்பப் பதிவேடு மேலாண்மை
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

### 💻 1. `package.json` கோப்பு உள்ளடக்கம்:
```json
{
  "name": "kovil-kanakku-app",
  "version": "1.0.0",
  "description": "ஶ்ரீ ஏழைகாத்த அம்மன் வல்லடிகார சுவாமி திருக்கோவில் - கோவில் கணக்கு மொபைல் செயலி",
  "main": "www/index.html",
  "scripts": {
    "build": "npx cap copy && npx cap sync",
    "open:android": "npx cap open android",
    "generate:assets": "npx capacitor-assets generate --android"
  },
  "dependencies": {
    "@capacitor/android": "^6.0.0",
    "@capacitor/core": "^6.0.0"
  },
  "devDependencies": {
    "@capacitor/assets": "^3.0.0",
    "@capacitor/cli": "^6.0.0"
  },
  "author": "பல்லவராயன்பட்டி தேவஸ்தான நிர்வாகம்",
  "license": "MIT"
}
```

---

### ⚙️ 2. `capacitor.config.json` கோப்பு உள்ளடக்கம்:
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

### 📥 Stitch இடைமுகத்திலிருந்து ZIP அல்லது HTML கோப்புகளைப் பதிவிறக்கும் முறை:

1. **ஒட்டுமொத்த ப்ராஜெக்ட் எக்ஸ்போர்ட் (Direct Export / Download):**
   - தங்களின் திரையின் மேல் வலது மூலையில் உள்ள **Export** அல்லது **Download (ZIP / Code)** பொத்தானைக் கிளிக் செய்து, அனைத்துத் திரைகளின் குறியீடுகளையும் (HTML, CSS, JS) ஒரே கிளிக்கில் ஜிப் (ZIP) கோப்பாகப் பதிவிறக்கிக் கொள்ளலாம்.

2. **கோப்புகளை ஒழுங்கமைத்தல் (Folder Placement):**
   - பதிவிறக்கம் செய்த ZIP கோப்பை அன்ஜிப் செய்து, மேலே குறிப்பிடப்பட்டுள்ளவாறு `www/` கோப்புறைக்குள் உங்கள் HTML திரைகளை இட்டு `assets/` கோப்புறையில் லோகோ மற்றும் படங்களை வைத்து உடனே ஆண்ட்ராய்டு APK உருவாக்கலாம்.
