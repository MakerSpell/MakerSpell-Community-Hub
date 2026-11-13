# 🌐 Yazıcıları Ağa Bağlama ve Eşleştirme Kılavuzu

MakerSpell uygulaması, yerel ağınızda açık olan yazıcıları bulmak için otomatik tarama teknolojisi kullanır.

---

## 1. Otomatik Ağ Taraması ile Yazıcı Ekleme

### Ağ Yazıcıları Her Ekranda

Bulunan aynı yazıcı filosu, elinizdeki ekrana uyum sağlar. Karşılaştırmak için bir cihaz seçin:

<div class="device-viewer">
<input class="dv-input" type="radio" name="dv-printers" id="dv-printers-desktop" checked>
<input class="dv-input" type="radio" name="dv-printers" id="dv-printers-tablet">
<input class="dv-input" type="radio" name="dv-printers" id="dv-printers-mobile">
<div class="dv-tabs">
<label for="dv-printers-desktop"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><rect x="2" y="3" width="20" height="14" rx="2"/><path d="M8 21h8"/><path d="M12 17v4"/></svg><span class="dv-label">Masaüstü</span><span class="dv-size">1280 px</span></label>
<label for="dv-printers-tablet"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><rect x="4" y="2" width="16" height="20" rx="2"/><path d="M12 18h.01"/></svg><span class="dv-label">Tablet</span><span class="dv-size">768 px</span></label>
<label for="dv-printers-mobile"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><rect x="7" y="2" width="10" height="20" rx="2.5"/><path d="M11 18h2"/></svg><span class="dv-label">Mobil</span><span class="dv-size">412 px</span></label>
</div>
<div class="dv-panels">
<figure class="dv-panel">
<img src="../../assets/screenshots/app/app-connecting-printers-desktop.png" alt="Ağ Yazıcıları — Masaüstü" loading="lazy">
<figcaption><strong>Masaüstü</strong> — Bulunan ağ yazıcıları pencerenin tüm genişliğini kullanır.</figcaption>
</figure>
<figure class="dv-panel">
<img src="../../assets/screenshots/app/app-connecting-printers-tablet.png" alt="Ağ Yazıcıları — Tablet" loading="lazy">
<figcaption><strong>Tablet</strong> — Her yazıcı satırı durum düğmesini başparmak menzilinde tutar.</figcaption>
</figure>
<figure class="dv-panel">
<img src="../../assets/screenshots/app/app-connecting-printers-mobile.png" alt="Ağ Yazıcıları — Mobil" loading="lazy">
<figcaption><strong>Mobil</strong> — Liste, makinenin başına yürürken bakabileceğiniz tam genişlikte kartlara dönüşür.</figcaption>
</figure>
</div>
<div class="dv-hint">Yerleşimler 1280 px, 768 px ve 412 px genişlikte alınmıştır.</div>
</div>

---

1. 3D yazıcınızın açık ve bilgisayarınız/telefonunuz ile **aynı Wi-Fi veya Ethernet ağına** bağlı olduğundan emin olun.
2. Uygulamanın üst menüsünden veya yan panelinden **"Ağ Yazıcıları"** sekmesini açın.
3. Sağ üst köşedeki **"Yenile / Tara"** butonuna tıklayın.
4. MakerSpell yerel ağınızdaki mDNS (Zeroconf) ve Klipper/Creality servislerini tarayacaktır.
5. Birkaç saniye içinde cihazınız (Örn: *Creality K1*, *Snapmaker U1*, *Moonraker*) listede belirecektir.
6. Cihaz kartının sağ tarafındaki durum indikatörü yeşil yandığında yazıcınız kontrol edilmeye hazırdır.

---

## 2. Manuel IP ile Yazıcı Ekleme

Eğer modeminiz ağ içi cihaz keşif paketlerini (mDNS) kısıtlıyorsa, cihazınızı doğrudan IP adresiyle ekleyebilirsiniz:

1. **"Ağ Yazıcıları"** ekranında sağ üstteki **"Yazıcı Ekle" (+)** butonuna tıklayın.
2. Açılan formda:
   - **Yazıcı Adı:** İstediğiniz bir isim verin (Örn: *Atölye K1*).
   - **IP Adresi:** Yazıcınızın ekranından öğrendiğiniz yerel IP adresini girin (Örn: `192.168.1.105`).
   - **Port:** Kullandığınız yazılımın portunu girin:
     - Klipper / Moonraker için varsayılan: `7125`
     - CrealityOS (K1, Ender-3 V3, Hi) için: `80`
     - OctoPrint için: `80` veya `5000`
   - **Protokol / Sürücü:** Cihaz tipinize uygun sürücüyü seçin (Örn: *Creality Local v2*, *Moonraker*, *OctoPrint*).
3. **"Bağlantıyı Test Et ve Kaydet"** butonuna basın. Başarılı onay mesajından sonra cihaz listenize eklenecektir.

---

## 3. Dinamik IP Değişimi Durumunda Ne Olur?

Modeminiz veya yazıcınız yeniden başlatıldığında IP adresi değişse bile, MakerSpell cihazınızı donanım kimliği (MAC / UUID) üzerinden hatırlar. Cihazınız yeni bir IP aldığında uygulama bunu arka planda otomatik algılar ve kontrolü kesintisiz sürdürür.

