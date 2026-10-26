# 🐍 مار و پله — نسخه اندروید

بازی کلاسیک «مار و پله» به‌صورت اپلیکیشن اندروید. کل بازی یک فایل HTML است که درون یک WebView بومی اجرا می‌شود و فونت وزیرمتن هم به‌صورت آفلاین داخل اپ قرار دارد.

**سازنده: [دانیال افشاری](https://t.me/sahandsoft) | تلگرام: [سهند سافت](https://t.me/sahandsoft)**

## ⬇️ دانلود APK

آخرین نسخه از صفحه Releases ریپو قابل دانلود است:

```
https://github.com/anonymousleoric-cpu/marpeleh/releases/latest/download/Marpeleh-release.apk
```

## 🏗 بیلد خودکار با GitHub Actions

با هر push روی `main`، فایل workflow ‏`.github/workflows/android.yml` اجرا می‌شود:

1. نصب JDK 17 و Gradle 8.7
2. ساخت APK نسخه debug و release (امضاشده، قابل نصب)
3. آپلود Artifact و به‌روزرسانی Release ‏`v1.0`

اجباراً نیازی به اندروید استودیو نیست — همه‌چیز روی سرورهای گیت‌هاب بیلد می‌شود.

## 🗂 ساختار پروژه

```
marpeleh-android/
├── .github/workflows/android.yml   ← بیلد خودکار APK
├── app/
│   ├── build.gradle                ← تنظیمات ماژول
│   └── src/main/
│       ├── AndroidManifest.xml
│       ├── java/com/sahandsoft/marpeleh/MainActivity.java  ← WebView بازی
│       ├── res/                    ← آیکون و تم
│       └── assets/www/             ← کل بازی (index.html + فونت آفلاین)
├── settings.gradle
└── build.gradle
```

## 🛠 بیلد محلی (اختیاری)

```bash
gradle assembleDebug    # خروجی: app/build/outputs/apk/debug/
```

- minSdk: 24 (اندروید ۷ به بالا)
- targetSdk / compileSdk: 34
- بدون هیچ وابستگی خارجی (بدون AndroidX) — سریع و سبک
