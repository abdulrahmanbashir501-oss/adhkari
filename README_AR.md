# مشروع أذكاري للأندرويد

تم تجهيز نسخة Android باستخدام Capacitor، مع الاحتفاظ بملف التطبيق الأصلي داخل `www/index.html`.

## المتطلبات
- Node.js إصدار 20 أو أحدث
- Android Studio
- Android SDK (يتم تثبيته من Android Studio)
- اتصال إنترنت أول مرة لتنزيل حزم Capacitor وGradle

## إنشاء تطبيق APK
1. فك ضغط المشروع.
2. افتح المجلد `adhkari_android` في VS Code أو Terminal.
3. نفّذ:

```bash
npm install
npx cap add android
npx cap sync android
npx cap open android
```

4. داخل Android Studio انتظر انتهاء Gradle Sync.
5. من القائمة اختر **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
6. بعد نجاح البناء اختر **locate** للوصول إلى ملف APK.

عادةً يكون الملف هنا:
`android/app/build/outputs/apk/debug/app-debug.apk`

## ملاحظات
- التطبيق يعمل محليًا ولا يحتاج إلى اتصال إنترنت بعد تثبيته.
- عدّادات الأذكار تحفظ تقدمها على نفس الجهاز باستخدام Local Storage.
- تم تعديل حساب تاريخ اليوم ليعتمد على تاريخ الجهاز المحلي بدل UTC.
- إذا عدّلت `www/index.html` لاحقًا، نفّذ `npx cap sync android` ثم أعد بناء APK.
- هذا مجلد مشروع قابل للبناء، وليس ملف APK مبنيًا بالفعل؛ يلزم Android Studio وAndroid SDK لإنتاج APK.
