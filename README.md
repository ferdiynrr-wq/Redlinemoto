# MotoTopluluk — Android & iOS MVP

Bu proje, motosiklet kullanıcılarının kendi kayıtlarını oluşturduğu bir topluluk uygulamasının Flutter başlangıç projesidir.

## Özellikler
- E-posta/şifre ile kayıt ve giriş
- Ad soyad
- Telefon
- Motosiklet marka/model
- Model yılı
- Plaka
- Şehir
- Profil fotoğrafı
- Motosiklet fotoğrafı
- Üye listesi
- Üye detayında iletişim bilgileri
- Firebase Authentication + Firestore + Storage
- Kullanıcının kendi profilini düzenlemesi
- Silme/çıkış altyapısı
- `verified` alanı ile yönetici tarafından teyit edilme altyapısı

## Neden Firebase?
Flutter tek kod tabanından Android ve iOS'a çıkış sağlayabilir. Firebase Authentication kullanıcı hesabını, Firestore profil kayıtlarını, Cloud Storage ise fotoğrafları tutmak için kullanılabilir. Firebase ayrıca Authentication + Firestore/Storage Security Rules ile erişim kontrolü sağlar.

## Kurulum
1. Flutter SDK kurun.
2. Firebase'de yeni proje oluşturun.
3. Android uygulaması ekleyin.
4. iOS uygulaması ekleyin.
5. Firebase Authentication > Email/Password'u açın.
6. Firestore Database oluşturun.
7. Storage oluşturun.
8. FlutterFire CLI ile:
   `flutterfire configure`
9. Oluşan `lib/firebase_options.dart` dosyasını projeye ekleyin.
10. Ardından:
   `flutter pub get`
   `flutter run`

## Firebase koleksiyonu
`users/{uid}`

Örnek:
```json
{
  "fullName": "Ad Soyad",
  "phone": "05xxxxxxxxx",
  "motorcycle": "Yamaha R25",
  "modelYear": 2015,
  "plate": "20 ABC 123",
  "city": "Denizli",
  "profilePhotoUrl": "",
  "motorcyclePhotoUrl": "",
  "verified": false,
  "createdAt": "server timestamp"
}
```

## Önemli gizlilik notu
Telefon ve plaka kişisel veri olabilir. Bu nedenle gerçek uygulamada:
- açık rıza ve aydınlatma metni,
- kullanıcı hesabını/profilini silme,
- telefon ve plaka için görünürlük tercihi,
- sadece gerekli kişilerin erişimi,
- Firebase Security Rules,
- yönetici yetkilendirmesi
uygulanmalıdır.

Bu MVP'de veritabanı kuralları ayrıca `firestore.rules` ve `storage.rules` dosyalarında örneklenmiştir.

## Mağazaya çıkış
Android için Play Store'a AAB üretilebilir:
`flutter build appbundle`

iOS için Apple/macOS geliştirme ortamında Xcode üzerinden archive/release gerekir.
