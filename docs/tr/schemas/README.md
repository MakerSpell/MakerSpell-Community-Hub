# 📋 JSON Sürücü & Profil Şeması (v2) Genel Bakış

MakerSpell'in dinamik yazıcı sürücü mimarisinin temel taşı **`profile-v2.schema.json`** spesifikasyonudur.

Bu şema, herhangi bir 3D yazıcının haberleşme protokolünü, ağ keşif kurallarını, telemetri haritalarını, donanım kontrollerini ve arayüz yerleşimini tek bir deklaratif JSON dosyası halinde tanımlamayı mümkün kılar.

---

## 📌 1. Neden Kod Yerine JSON Sürücüsü?

Geleneksel 3D baskı yazılımlarında (Creality Print, Bambu Studio, Cura vb.) yeni bir yazıcı eklemek için kaynak kodun değiştirilmesi, derlenmesi ve tüm kullanıcılara yeni bir masaüstü/mobil sürüm dağıtılması gerekir.

MakerSpell'de ise:
1. **Dinamik Yayın:** Yeni bir yazıcı profili GitHub Community Hub üzerinden yayınlanır.
2. **Anında İndirme:** MakerSpell uygulamaları (Masaüstü, Web, Mobil) yayınlanan profili indirir, SHA-256 ve JSON şemasıyla doğrular ve uygulamayı yeniden başlatmadan aktif eder.
3. **Sıfır Güvenlik Açığı (Sandboxing):** JSON dosyası saf veri tanımlar; işletim sistemi kodu, rastgele script veya yetkisiz alan adlarına HTTP isteği çalıştıramaz.

---

## 📌 2. Sürücü Dosyasının Ana Blokları

Bir `profile-v2` dosyası aşağıdaki temel bloklardan oluşur:

| Blok | Görevi |
| :--- | :--- |
| **`identity`** | Yazıcının adı, uyumlu olduğu modeller, doğrulama durumu (`community` veya `communityVerified`). |
| **`permissions`** | Profilin talep ettiği yetkiler (`statusRead`, `fileUpload`, `deviceControl`, `cameraRead` vb.). |
| **`discovery`** | mDNS servis tipleri (`_creality._tcp.local`), portlar ve cihazı tanımak için atılacak probe istekleri. |
| **`channels`** | Yazıcıyla konuşulacak ağ kanalları (`http`, `websocket`, portlar, zaman aşımları). |
| **`operations`** | HTTP veya WS üzerinden çalıştırılacak işlemler (`status`, `uploadFile`, `startPrint`, `pausePrint`, `setTemp` vb.). |
| **`actions`** | Arayüzdeki butonlara basıldığında operasyonların hangi argümanlarla tetikleneceğini bağlayan köprü. |
| **`state`** | Yazıcıdan dönen ham JSON yanıtındaki alanların MakerSpell standart telemetrisine (`temperature.hotend`, `job.progress`) JSONPath ile eşleştirilmesi. |
| **`ui`** | Yazıcı denetim sayfasının masaüstü ve mobildeki 2 kolonlu pano düzeni ve bileşen yerleşimleri. |
| **`media`** | Canlı kamera stream yolu ve yazıcı yerel web arayüzü linki. |

---

## 📌 3. Belgeler ve Referanslar

- [Tam profile-v2 Spesifikasyon Kılavuzu](file:///D:/YazilimProgramlama/3DEticaretOtomasyon/community-hub/docs/schemas/profile-v2-specification.md)
- [Resmi JSON Şema Dosyası (`profile-v2.schema.json`)](file:///D:/YazilimProgramlama/3DEticaretOtomasyon/community-hub/docs/schemas/profile-v2.schema.json)
- [Örnek Creality K1 v2 Profili](file:///D:/YazilimProgramlama/3DEticaretOtomasyon/community-hub/docs/examples/creality-k1-v2.json)
- [Örnek Snapmaker U1 v2 Profili](file:///D:/YazilimProgramlama/3DEticaretOtomasyon/community-hub/docs/examples/snapmaker-u1-v2.json)
