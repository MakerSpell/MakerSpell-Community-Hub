# Cihaz Denetim Panosu (Kamera, Sıcaklık ve Eksenler)

Bir yazıcının detayına girdiğinizde karşınıza çıkan **Cihaz Denetim Panosu**, masaüstünde 2 kolonlu optimize edilmiş bir kumanda masası sunar.

### Cihaz Denetim Panosu Her Ekranda

Aynı kumanda masası cihazınıza göre yeniden düzenlenir. Karşılaştırmak için bir cihaz seçin:

<div class="device-viewer">
<input class="dv-input" type="radio" name="dv-controls" id="dv-controls-desktop" checked>
<input class="dv-input" type="radio" name="dv-controls" id="dv-controls-tablet">
<input class="dv-input" type="radio" name="dv-controls" id="dv-controls-mobile">
<div class="dv-tabs">
<label for="dv-controls-desktop"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><rect x="2" y="3" width="20" height="14" rx="2"/><path d="M8 21h8"/><path d="M12 17v4"/></svg><span class="dv-label">Masaüstü</span><span class="dv-size">1280 px</span></label>
<label for="dv-controls-tablet"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><rect x="4" y="2" width="16" height="20" rx="2"/><path d="M12 18h.01"/></svg><span class="dv-label">Tablet</span><span class="dv-size">768 px</span></label>
<label for="dv-controls-mobile"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><rect x="7" y="2" width="10" height="20" rx="2.5"/><path d="M11 18h2"/></svg><span class="dv-label">Mobil</span><span class="dv-size">412 px</span></label>
</div>
<div class="dv-panels">
<figure class="dv-panel">
<img src="../../assets/screenshots/app/app-printer-controls-desktop.png" alt="Cihaz Denetim Panosu — Masaüstü" loading="lazy">
<figcaption><strong>Masaüstü</strong> — Canlı kamera ve hareket pedi geniş bir monitörde yan yana durur.</figcaption>
</figure>
<figure class="dv-panel">
<img src="../../assets/screenshots/app/app-printer-controls-tablet.png" alt="Cihaz Denetim Panosu — Tablet" loading="lazy">
<figcaption><strong>Tablet</strong> — İki bölüm de görünür kalır, ancak daha uzun ve dokunma öncelikli bir düzene geçer.</figcaption>
</figure>
<figure class="dv-panel">
<img src="../../assets/screenshots/app/app-printer-controls-mobile.png" alt="Cihaz Denetim Panosu — Mobil" loading="lazy">
<figcaption><strong>Mobil</strong> — Paneller tek parmakla kaydırılan tek kolona dönüşür.</figcaption>
</figure>
</div>
<div class="dv-hint">Yerleşimler 1280 px, 768 px ve 412 px genişlikte alınmıştır.</div>
</div>

---

## 1. Sol Kolon: Canlı İzleme ve Görüntü

- **Canlı Kamera Yayını:**
  Yazıcınızın dahili kamerası varsa akış otomatik başlar. Gecikmesiz video üzerinden ilk katman yapışmasını ve baskı sürecini izleyebilirsiniz.
- **Aktif İş Durumu:**
  Hangi dosyanın basıldığı, katman sayısı (Örn: *120 / 450*), kalan süre ve ilerleme yüzdesi canlı olarak takip edilir.
- **Çok Renkli Filament Yuvaları:**
  Yazıcınıza bağlı CFS veya AMS ünitesindeki bobinlerin rengi ve malzeme türü (PLA, PETG, ABS) görsel olarak listelenir.

---

## 2. Sağ Kolon: Manuel Kontroller ve Donanım Ayarları

- **Sıcaklık Ayarları:**
  - **Nozul Sıcaklığı:** Hızlı ön ısıtma hazır ayarları (PLA 200°C, PETG 240°C, ABS 260°C) veya manuel derece girişi.
  - **Tabla Sıcaklığı:** Tablayı ısıtma ve soğutma düğmeleri.
  - **Hazne / Kabin Işığı:** Cihaz içi aydınlatmayı açıp kapatma düğmesi.
- **Fan Hızları:**
  - Model Soğutma Fanı, Arka Egzoz Fanı ve Yan Fan hızlarını yüzde cinsinden ayarlayabilirsiniz.
- **XYZ Eksen Hareketi & Sıfırlama (Homing):**
  - Dairesel kontrol pedi üzerinden X ve Y eksenlerini kaydırabilir, Z eksenini yukarı/aşağı hareket ettirebilirsiniz.
  - Hareket adım büyüklüğünü (`0.1 mm`, `1 mm`, `10 mm`, `100 mm`) seçebilirsiniz.
  - Ortadaki Home butonuyla veya alttaki **"Tüm Eksenleri Başlangıca Al"** düğmesiyle kafayı sıfırlayabilirsiniz.
  - *Güvenlik Notu:* Yazıcı baskı yaparken eksen hareket butonları kazaları önlemek için otomatik kilitlenir.
- **Yerel Dosya Listesi & Baskı Geçmişi:**
  - Yazıcının hafızasındaki eski dosyaları görebilir, silebilir veya geçmiş baskıların süre raporlarını inceleyebilirsiniz.
