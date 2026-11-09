# 🛠️ Yeni Bir Yazıcı Profili Ekleme Rehberi

Bu rehber, MakerSpell ekosistemine yeni bir 3D yazıcı modelini JSON sürücüsü (`profile-v2`) olarak eklemek isteyen geliştiriciler ve topluluk üyeleri için hazırlanmıştır.

---

## 📌 1. Hazırlık ve Gereksinimler

1. **Yazıcının Ağ Detayları:**
   - Yazıcının yerel IP adresi.
   - Kullandığı servis portları (Web: 80, Klipper/Moonraker: 7125, Creality: 9999, OctoPrint: 80/5000 vb.).
   - mDNS servis adı (`_moonraker._tcp.local`, `_printer._tcp.local` vb.).
2. **JSON Şeması:**
   Hazırlayacağınız dosya [profile-v2.schema.json](file:///D:/YazilimProgramlama/3DEticaretOtomasyon/community-hub/docs/schemas/profile-v2.schema.json) kurallarına %100 uymalıdır.

---

## 📌 2. Adım Adım Profil Oluşturma

### Adım 1: Dosyayı Oluşturun
`community-hub/docs/examples/` veya `makersync_app/assets/community_printers/profiles/` altında yeni bir dosya açın:
Örn: `mybrand-modelx-v2.json`.

### Adım 2: Temel Kimlik ve İzinleri Tanımlayın
```json
{
  "$schema": "../schemas/profile-v2.schema.json",
  "schemaVersion": 2,
  "id": "community.mybrand-modelx.v2",
  "version": "1.0.0",
  "identity": {
    "name": "MyBrand Model X",
    "models": ["Model X", "Model X Pro"],
    "status": "community"
  },
  "permissions": [
    "statusRead",
    "fileListRead",
    "fileUpload",
    "cameraRead"
    // DİKKAT: Cihaz laboratuvar doğrulanmış değilse "printStart" eklemeyiniz (Safe-Mode)!
  ]
}
```

### Adım 3: Kanalları ve Operasyonları Belirleyin
Yazıcının telemetri okuması için gerekli HTTP veya WebSocket kanallarını ekleyin. [Creality K1 Örneği](file:///D:/YazilimProgramlama/3DEticaretOtomasyon/community-hub/docs/examples/creality-k1-v2.json) veya [Snapmaker U1 Örneği](file:///D:/YazilimProgramlama/3DEticaretOtomasyon/community-hub/docs/examples/snapmaker-u1-v2.json) dosyalarını şablon alabilirsiniz.

### Adım 4: Telemetri (state) Eşleştirmesini Yapın
Yazıcının döndüğü sıcaklık ve durum anahtarlarını JSONPath ile eşleştirin:
```json
"state": {
  "temperature": {
    "hotendActual": "$.temperature.tool0.actual",
    "hotendTarget": "$.temperature.tool0.target",
    "bedActual": "$.temperature.bed.actual",
    "bedTarget": "$.temperature.bed.target"
  }
}
```

---

## 📌 3. Yerel Test ve Doğrulama

JSON dosyanızın doğruluğunu Flutter test suite üzerinden kontrol edin:

```powershell
cd makersync_app
flutter test test/community_printer_driver_v2_test.dart
```

Tüm testler yeşil yandığında profiliniz MakerSpell uygulaması tarafından hatasız yorumlanabilir demektir.

---

## 📌 4. Pull Request Gönderme

1. Profilinizi `community-hub` deposunda bir dal (branch) açarak ekleyin.
2. Cihazınızla yaptığınız test ekran görüntüsünü PR açıklamasına ekleyin.
3. Ekip ve topluluk incelemesinin ardından profil resmi kataloğa dahil edilecektir.
