# Baskı Merkezi (Print Center) Kullanım Kılavuzu

Baskı Merkezi, birden fazla 3D yazıcı kullanan makerlar ve atölyeler için tasarlanmış merkezi operasyon ekranıdır.

### Baskı Merkezi Her Ekranda

Aynı canlı filo panosu cihazınıza göre kendini yeniden düzenler. Aşağıdaki ekran görüntüleri, adet bazlı üretim emirlerinin kuyruğa alındığı **Üretim Çiftliği** sekmesini gösterir; diğer sekmeler (Aktif, Hazır, Geçmiş, Bakım Çiftliği, İlerleme) aynı yerleşimi kullanır. Masaüstünde paneller geniş ızgarada yan yana durur:

![Baskı Merkezi ve Filo Takibi — Masaüstü](../../assets/screenshots/app/app-print-center-desktop.png)

Tablette kartlar dokunmaya elverişli bir ızgaraya akar:

![Baskı Merkezi ve Filo Takibi — Tablet](../../assets/screenshots/app/app-print-center-tablet.png)

Telefonda ise pano tek elle kaydırılabilen tek kolona dönüşür:

![Baskı Merkezi ve Filo Takibi — Mobil](../../assets/screenshots/app/app-print-center-mobile.png)

---

## 1. Baskı Merkezi Başlığı ve Özet Sayaçları

Ekranın üst kısmında yer alan mavi bilgi panosunda atölyenizin anlık özeti gösterilir:
- **Aktif İşler:** Şu anda tablaya baskı yapan veya ısınan cihaz sayısı.
- **Hazır Dosyalar:** Dilimlenmiş ve yazıcılara gönderilmeye hazır G-code dosyaları.
- **Çevrimiçi Yazıcılar:** Ağa bağlı ve iletişim kurulabilen toplam cihaz sayısı.

---

## 2. Yazıcı Durum Kartları

Listedeki her bir cihaz kartı üzerinde şu bilgiler canlı olarak güncellenir:

- **Baskı Durumu İndikatörü:**
  - 🟢 **Yeşil:** Cihaz hazır ve boşta (`Idle`).
  - 🔵 **Mavi / Animasyonlu:** Aktif baskı devam ediyor (`Printing`).
  - 🟡 **Sarı:** Baskı duraklatıldı (`Paused`).
  - 🔴 **Kırmızı / Soluk:** Cihaz kapalı veya ağdan düştü (`Offline`).
- **Canlı İlerleme:** Modelin yüzde kaçının tamamlandığı (`%65`) ve tahmini kalan süre (`14m 20s`).
- **Sıcaklık Değerleri:** Anlık ve hedef nozul / tabla sıcaklıkları (`220°C / 60°C`).
- **Hızlı Butonlar:**
  - **Duraklat / Devam Et:** Baskıyı acil durumlarda geçici olarak bekletir.
  - **İptal Et:** Onay kutusunun ardından baskıyı güvenle sonlandırır.
  - **Detay Paneli:** Yazıcının tam kontrol panosunu açar.
