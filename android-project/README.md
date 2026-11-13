# 客戶導航助手 - Android 專案

此為使用 WebView 包裝的 Android 專案，可透過 Android Studio 或線上服務編譯成 APK。

---

## 📁 專案結構說明

```
android-project/
├── app/
│   ├── src/
│   │   └── main/
│   │       ├── assets/
│   │       │   └── index.html          ← 主要 App 畫面 (HTML)
│   │       ├── java/com/customernavigator/
│   │       │   └── MainActivity.java   ← 主 Activity (WebView 設定)
│   │       ├── res/
│   │       │   ├── layout/
│   │       │   │   └── activity_main.xml
│   │       │   ├── mipmap-*/           ← App 圖示 (需自行放入 PNG)
│   │       │   └── values/
│   │       │       └── strings.xml     ← App 名稱
│   │       └── AndroidManifest.xml
│   └── build.gradle
├── gradle/wrapper/
│   └── gradle-wrapper.properties
├── build.gradle
├── settings.gradle
└── gradle.properties
```

---

## 🚀 編譯方式（三選一）

### 方法一：Android Studio（推薦）

1. 下載安裝 [Android Studio](https://developer.android.com/studio)
2. 開啟 Android Studio → **File → Open** → 選擇 `android-project` 資料夾
3. 等待 Gradle 同步完成
4. 點擊上方 **Build → Build Bundle(s)/APK(s) → Build APK(s)**
5. APK 輸出位置：`app/build/outputs/apk/debug/app-debug.apk`

### 方法二：Buildozer / 線上免費編譯服務

使用 [Appetize.io](https://appetize.io) 或 [GoNative.io](https://gonative.io) 等服務上傳本專案自動打包。

### 方法三：命令列編譯（需已安裝 JDK 17+ 與 Android SDK）

```bash
cd android-project
./gradlew assembleDebug
```

---

## ⚠️ 注意事項

- **App 圖示**：需在 `res/mipmap-*/` 資料夾放入對應尺寸的 `ic_launcher.png` 與 `ic_launcher_round.png`
  - mdpi: 48×48
  - hdpi: 72×72
  - xhdpi: 96×96
  - xxhdpi: 144×144
  - xxxhdpi: 192×192
- **Google Maps 連結**：App 在手機上點擊「導航到這」按鈕，會自動開啟 Google Maps App
- **資料儲存**：使用 localStorage，資料存於手機本地，不會上傳至伺服器
- **最低 Android 版本**：Android 5.0（API 21）以上

