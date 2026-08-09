# Apna APK Builder — Setup Guide

Ye template kisi bhi website/web-app ko free APK mein convert karta hai, GitHub Actions ke zariye (bilkul free, koi Android Studio ki zaroorat nahi).

## Steps

### 1. Naya GitHub repo banao
- Public repo banao (koi bhi naam, e.g. `my-app-builder`)
- Is poore folder ka content us repo mein upload kar do ("Add file" → "Upload files", sab kuch drag-drop karo, folder structure preserve rakhna)

### 2. Apni app ki files daalo
- `www/` folder ke andar jo bhi tumhari zip file thi (HTML/CSS/JS/images) — sab replace kar do
- Zaroori: entry point ka naam `index.html` hi hona chahiye

### 3. App ka naam set karo
- `capacitor.config.json` file kholo
- `"appName"` ki value apne app ke naam se replace karo (e.g. `"PkStore"`)
- `"appId"` bhi apna rakh sakte ho (format: `com.yourname.appname`)

### 4. Icon set karo
- `assets/icon.png` ko apni icon image se replace karo (1024x1024 PNG best hai)
- `assets/splash.png` ko chaho to apna splash/loading screen image se replace kar do (2732x2732)

### 5. Commit / Upload
- Sab changes commit kar do (GitHub web pe "Commit changes" button)

### 6. Build dekho
- Repo ke "Actions" tab mein jao
- "Build APK" workflow chal raha hoga (~5-8 minute lagte hain)
- Green tick ka wait karo

### 7. APK download karo
- Us workflow run ke andar "Artifacts" section mein "app-apk" milega
- Usay download karo — ye ek **zip file** hogi
- Zip ko decompress karo — andar `app-debug.apk` milegi

### 8. Install
- APK ko phone pe transfer karo, "Install from unknown sources" allow karo, install kar do

---

## Notes
- Har baar jab tum `www/` folder ki files ya icon change karo aur commit karo, naya APK automatically ban jayega.
- Ye APK "debug" build hai — testing/personal use ke liye perfect hai. Agar Play Store pe publish karna ho to signing process alag hota hai (bata dena, wo bhi set up kar sakte hain).
- Agar build fail ho jaye, Actions tab mein red cross pe click karke error log dekh sakte ho — error paste kar dena, main fix kar dunga.
