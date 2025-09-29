# Flutter Demo Bank (with Biometric Lock)

**Features**
- Biometric authentication gate (Fingerprint / Face ID) using `local_auth`
- Clean navigation with bottom nav bar & pages (Bills, Transfers, Topup, Tuition, Payments, Wallet, Card Services, Bank Services, Express, Vouchers, Finance, More)
- Arabic UI titles
- Ready `pubspec.yaml`

## How to run
1) Copy this folder into your Flutter workspace and run:
```bash
flutter pub get
flutter run
```

2) Android setup (`android/app/src/main/AndroidManifest.xml`):
```xml
<uses-permission android:name="android.permission.USE_BIOMETRIC"/>
<uses-permission android:name="android.permission.USE_FINGERPRINT"/>
```
Ensure `compileSdkVersion` and `targetSdkVersion` >= 28.

3) iOS setup (`ios/Runner/Info.plist`):
```xml
<key>NSFaceIDUsageDescription</key>
<string>نستخدم Face ID/Touch ID لتأمين تسجيل الدخول.</string>
```

> Note: This package provides only the source (lib/ + pubspec). Use `flutter create .` to generate platform folders if needed, then replace the generated `lib/` and `pubspec.yaml` with these ones.

## Structure
```
lib/
  main.dart
  security/biometric_auth.dart
  screens/
    lock_gate.dart
    home_page.dart
    pages.dart
```


## Routes (GoRouter)
- /login → شاشة الدخول
- /home → القشرة الرئيسية
- /settings → الإعدادات (تفعيل/تعطيل القفل عند الرجوع)
- /bills, /transfers, /topup, /tuition, /payments, /wallet, /card, /bank, /express, /vouchers, /finance, /more

## Biometric on Resume
- يمكن تفعيله من الإعدادات (يستخدم Flutter Secure Storage لحفظ الخيار)
