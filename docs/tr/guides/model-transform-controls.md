# Model Dönüştürme Kontrolleri Kılavuzu (Taşıma, Döndürme, Ölçekleme)

Baskı hazırlığında 3D modellerin baskı tablası üzerinde hassas şekilde konumlandırılması, döndürülmesi ve ölçeklenmesi kritik bir adımdır. MakerSpell; görsel karmaşadan uzak, hızlı ve hassas ayarlamalar yapmanızı sağlayan profesyonel dönüştürme panelleri sunar.

---

## 🎛️ Dönüştürme Modlarını Etkinleştirme

Sanal baskı tablası üzerindeki bir model seçildiğinde, üst düzenleyici araç çubuğundan üç ana uzamsal düzenleme aracına doğrudan erişilebilir:

1. **Taşı (Move)**: Modelin X, Y ve Z eksenlerindeki fiziksel konumunu milimetre cinsinden ayarlar.
2. **Döndür (Rotate)**: Modeli eksenler etrafında derece cinsinden döndürür.
3. **Ölçekle (Scale)**: Modeli orantılı veya serbest eksenli olarak yüzde ya da hedef milimetre boyutlarıyla yeniden boyutlandırır.

Bu araçlardan birine tıklandığında, çalışma alanının sol üst köşesinde kompakt bir kontrol kartı açılır. Kartın sağ üstündeki **Kapat (✕)** butonuna tıklanarak veya `Esc` tuşuna basılarak panel her an kapatılabilir.

---

## 📍 Taşı (Konum Kontrolü)

Taşıma paneli, modelin baskı tablasına göre dünya koordinatlarını gösterir:

- **Konum Girişleri (X, Y, Z)**: Milimetre cinsinden tam koordinatları girin.
  - **X Ekseni (Kırmızı rozet)**: Tablanın genişliği boyunca soldan sağa konumlandırma.
  - **Y Ekseni (Yeşil rozet)**: Tablanın derinliği boyunca önden arkaya konumlandırma.
  - **Z Ekseni (Mavi rozet)**: Düşey yüksekliği gösterir ve denetler. Varsayılan olarak modelin tabanı tablaya tam oturacak şekilde (`Z = 0`) otomatik hizalanır.
- **Ortala (Center) Butonu**: Modeli tek bir tıklamayla baskı tablasının tam merkezine taşır ve tabanını baskı yüzeyine oturtur.

---

## 🔄 Döndür (Açısal Kontrol)

Döndürme paneli, eksen bazında hassas açı kontrolü sağlar:

- **Döndürme Girişleri (X, Y, Z)**: Seçili eksen etrafında döndürmek için derece (`°`) cinsinden değer girin.
  - **X Ekseni (Kırmızı rozet)**: Eğim (önden arkaya devrilme).
  - **Y Ekseni (Yeşil rozet)**: Yuvarlanma (sağa sola devrilme).
  - **Z Ekseni (Mavi rozet)**: Sapma (tabla üzerinde yatay dönüş).
- **Sıfırla (Reset) Butonu**: Modelin yönelimini orijinal durumuna (`0.0°, 0.0°, 0.0°`) geri döndürür.

---

## 📐 Ölçekle (Boyutlar ve Yüzde)

Ölçekleme paneli; hem oransal yüzdeyi hem de mutlak fiziksel boyutları birlikte kontrol etmenizi sağlar:

- **Ölçek (% Satırı)**: Her eksen için hedef yüzde değerini girin (varsayılan `%100.0`).
- **Boyut (mm Satırı)**: X, Y ve Z için milimetre cinsinden hedef boyutları belirleyin. Milimetre değerini değiştirmek yüzde alanlarını, yüzdeyi değiştirmek ise milimetre boyutlarını otomatik olarak günceller.
- **Orantılı Ölçek Onay Kutusu**: İşaretli olduğunda, herhangi bir eksendeki boyut değişikliği modelin en-boy oranını korumak için diğer iki eksene eşit şekilde yansıtılır. İşaret kaldırıldığında her eksen bağımsız olarak serbestçe gerilebilir.
- **Sıfırla (Reset) Butonu**: Modeli orijinal 1:1 boyutuna (`%100.0`) geri döndürür.

---

## 💡 Kısayol Tuşları ve İpuçları

- **Doğrudan Kısayollar**: Taşıma için `M`, Döndürme için `R` ve Ölçekleme için `S` tuşuna basarak ilgili paneli hemen açabilirsiniz.
- **Gizmo Etkileşimi**: Sahnedeki 3D tutamaçları doğrudan fareyle sürükleyebilir veya paneldeki kutulara tam sayısal değerler yazabilirsiniz.
- **Ok Tuşları**: Giriş kutularından biri odaktayken klavyenizin yön tuşlarıyla değerleri hızlıca artırıp azaltabilirsiniz.
