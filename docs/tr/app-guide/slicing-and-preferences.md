# ⚙️ Dilimleme Ayarları & Tercihler Kılavuzu

MakerSpell, popüler açık kaynak dilimleme motoru **OrcaSlicer** entegrasyonu ile modellerinizi doğrudan uygulama içinden dilimlemenizi sağlar.

---

## 📌 1. Temel Baskı Profilleri

Ekranın sağ panelindeki dilimleme ayarlarından ihtiyacınıza uygun hazır profili seçebilirsiniz:
- **Kalite (0.12 mm / 0.16 mm):** Minyatürler ve pürüzsüz yüzey gerektiren figürler için ince katman yüksekliği.
- **Standart (0.20 mm):** Günlük kullanım, prototipler ve genel modeller için hız/kalite dengesi.
- **Hızlı / Taslak (0.28 mm):** Büyük mekanik parçalar ve test baskıları için yüksek hız.

---

## 📌 2. Dolgu (Infill) Seçenekleri

- **Dolgu Yoğunluğu:** Parçanın mukavemetine göre `%10` ile `%100` arasında doluluk seçin (dekoratif eşyalar için `%15` önerilir).
- **Dolgu Deseni:**
  - **Gyroid:** Her yönde eşit mukavemet ve nozul çarpmalarını önleyen en popüler desen.
  - **Grid / Çapraz:** Hızlı ve kolay basılan klasik desen.
  - **Honeycomb:** Maksimum ağırlık/mukavemet oranı sunan petek yapı.

---

## 📌 3. Destek (Support) Yapıları

Modelde havada asılı kalan (overhang) açılı yüzeyler varsa:
- **Ağaç Destek (Tree Support):** Kolay sökülebilen, az malzeme harcayan ve yüzeyde iz bırakmayan modern destek türü.
- **Standart Destek (Normal):** Dikey bloklar şeklinde yükselen klasik destek.
- **Yalnızca Tablaya Değenler:** Modelin kendi gövdesi üzerine destek dikilmesini engelleyen koruma seçeneği.
