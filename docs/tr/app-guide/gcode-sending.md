# G-code Gönderme & Dilimleme Entegrasyonu Kılavuzu

MakerSpell üzerinden dilimlediğiniz (veya dışarıdan aktardığınız) 3D modelleri yazıcınıza aktarmak son derece kolay ve güvenlidir.

---

## 1. Baskı Gönderme Adımları

1. 3D modelinizi hazırlayıp **"Dilimle"** butonuna basın.
2. Dilimleme tamamlandığında otomatik olarak **"G-code Gönder"** penceresi açılır.
3. Bu pencerede dilimlenen modelin temel parametreleri özetlenir:
   - Model adı ve tahmini baskı süresi
   - Harcanacak filament ağırlığı (gram) ve uzunluğu (metre)
   - Dilimleme nozul ve tabla sıcaklığı
4. **"Yazıcı Seç"** açılır kutusundan baskıyı göndermek istediğiniz çevrimiçi yazıcıyı seçin.
5. Yazıcınızda takılı olan filament ile model filamentleri otomatik eşleştirilir.
6. Alt kısımdaki iki seçenekten birine tıklayın:
   - **"Yalnızca Yükle":** Dosyayı yazıcının dahili hafızasına (SD kart veya eMMC) kaydeder, ancak baskıyı hemen başlatmaz.
   - **"Yükle ve Yazdır":** Dosyayı yazıcıya aktarır ve onayınızla baskı sürecini başlatır.

---

## 2. Safe-Mode Koruması Nedir?

Eğer seçtiğiniz yazıcı henüz laboratuvarımız tarafından tam test edilmemiş bir model ise (örneğin Bambu Lab LAN modu veya özel Klipper kurulumları), sistem sizi korumak için **Safe-Mode** moduna geçer:

- **"Yükle ve Yazdır"** butonu devre dışı bırakılır.
- Yalnızca **"Yalnızca Yükle"** butonu aktif olur.
- Dosya güvenle yazıcınıza aktarılır. Baskıyı başlatmak için yazıcınızın yanına gidip tablanın temiz olduğunu gözünüzle kontrol ettikten sonra ekrandan "Başlat" butonuna basmanız gerekir. Bu kural, olası kaza ve yangın risklerini önlemek için geliştirilmiştir.
