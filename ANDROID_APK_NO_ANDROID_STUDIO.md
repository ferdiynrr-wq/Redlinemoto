# Android Studio olmadan APK çıkarma

En kolay yol GitHub Actions kullanmaktır. Bilgisayarına Android Studio veya Flutter kurmana gerek yok.

## 1. GitHub hesabı
https://github.com adresinden ücretsiz hesap aç.

## 2. Yeni repository oluştur
Örneğin: `MotoTopluluk`

Repository'yi Public veya Private seçebilirsin.

## 3. ZIP'i aç
Bu ZIP'in içindeki bütün dosyaları GitHub repository'sine yükle. Özellikle `.github/workflows/build-apk.yml` dosyasının da yüklendiğinden emin ol.

## 4. Actions sekmesi
Repository'de `Actions` sekmesine gir.
`MotoTopluluk APK` workflow'unu seç.
`Run workflow` düğmesine bas.

## 5. APK'yı indir
İşlem tamamlanınca ilgili workflow çalışmasının içine gir.
`Artifacts` bölümünde `MotoTopluluk-APK` adlı dosyayı göreceksin.
İndirip ZIP'i aç. İçindeki `app-release.apk` dosyası Android telefona kurulabilir.

## ÖNEMLİ
Bu workflow şu an uygulamayı DEMO APK olarak derler. Firebase bilgileri verilmediği için gerçek çevrim içi üyelik/veritabanı özellikleri aktif değildir.

Gerçek sürüm için Firebase projesinin şu değerleri workflow secrets olarak eklenebilir:
- FIREBASE_API_KEY
- FIREBASE_APP_ID
- FIREBASE_MESSAGING_SENDER_ID
- FIREBASE_PROJECT_ID
- FIREBASE_STORAGE_BUCKET

Gerçek Firebase yapılandırması eklendiğinde aynı workflow ile çevrim içi sürüm APK'sı üretilebilir.

## Güvenlik
Telefon ve plaka gibi kişisel veriler genel üye listesinde herkese açık tutulmamalı. Gerçek sürümde bu alanları ayrı/private koleksiyona taşımak ve Firestore/Storage Security Rules ile erişimi sınırlandırmak gerekir.
