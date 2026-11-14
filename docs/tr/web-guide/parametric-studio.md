# Parametrik 3B Model Stüdyosu & Üreteç

MakerSpell Stüdyo (`/studio/parametric`), doğrudan tarayıcınız üzerinden etkileşimli 3B modelleme ve kişiselleştirme ortamı sunar. İster fotoğraflarınızdan kişiye özel litofan gece lambaları üretin, ister atölyeniz için milimetrik organizatör kutuları tasarlayın; stüdyo gerçek 3B geometrileri derleyerek dilimleyiciye hazır STL dosyalarını anında indirmenizi sağlar.

## 1. Dahili Parametrik Şablonlar

Stüdyo, farklı kullanım senaryolarına yönelik hazır parametrik şablonlarla birlikte gelir:

| Şablon | En Uygun Kullanım | Temel Parametreler |
| --- | --- | --- |
| **Litofan Fotoğraf & Gece Lambası** | Kişiye özel kabartmalı tablolar, kavisli gece lambaları | Görsel yükleme, şekil (kavisli, düz, silindir, priz aparatı), genişlik, min/maks katman kalınlığı, kavis açısı |
| **Parametrik Kutu & Kapak** | Donanım ve parça saklama kutuları, milimetrik çekmeceler | Genişlik, uzunluk, yükseklik, köşe yuvarlama, duvar kalınlığı, kapak tipi (raylı sürgülü, geçmeli, kapaksız), iç bölmeler |
| **Gridfinity Modüler Kutu** | Atölye ve çekmece düzenleme modülleri | Grid birimleri (42 mm katları), yükseklik birimleri (7 mm katları), alma dudağı eğimi, etiket rafı, mıknatıs yuvaları |
| **3B Kabartma İsimlik & Anahtarlık** | Çift renk baskıya uygun anahtarlık ve etiketler | Metin içeriği, yazı boyutu, kabartma yüksekliği, taban kalınlığı, anahtarlık halka deliği |
| **Açık Kaynak Kod Düzenleyici** | Kendi algoritmik tasarımlarınızı deneme | Doğrudan kod yazımı ve parametrelerin (kaydırıcılar, kutucuklar, listeler) arayüze otomatik çıkarımı |

> [!TIP]
> Her şablon, 3B baskının fiziksel sınırlarına uygun güvenli minimum ve maksimum değer aralıklarıyla donatılmıştır; böylece modeliniz baskı sırasında kırılma veya deformasyon yaşamayacak şekilde güvenle üretilir.

## 2. 3B Etkileşimli Görünüm Alanı

Görünüm alanı, modelinizi gerçek zamanlı aydınlatma ve fiziksel ölçülerle üç boyutlu olarak gösterir:

- **Döndürme (Yörünge)**: Sol fare tuşuna basılı tutarak sürükleyin (dokunmatik ekranlarda tek parmakla kaydırın).
- **Yakınlaşma / Uzaklaşma**: Fare tekerleğini çevirin (dokunmatik ekranlarda iki parmakla kıstırma hareketi yapın).
- **Tel Kafes (Wireframe) Modu**: Üst araç çubuğundaki **Tel Kafes** butonuna tıklayarak poligon yoğunluğunu, üçgen yapısını ve iç duvar örüntülerini inceleyin.
- **Arkadan Işık Vurma**: Litofan modellerinde **Işık Açık / Işık Kapalı** butonunu kullanarak ışığın yarı saydam filament katmanlarından nasıl geçtiğini simüle edin.
- **Canlı Bilgi Paneli (HUD)**: Sağ alt köşedeki panelde anlık üçgen (poligon) sayısı, milimetre cinsinden model boyutları ($X \times Y \times Z$) ve derleme süresi gösterilir.

## 3. Harici Modelleri Kişiselleştirme (Thingiverse, Printables, GitHub)

Yalnızca dahili şablonlarla sınırlı değilsiniz. MakerSpell üzerinde **Düzenlenebilir (Parametrik)** filtresiyle model ararken:

1. Desteklenen herhangi bir model sayfasında **3B Stüdyoda Kişiselleştir** butonuna tıklayın.
2. Stüdyo, modelin kaynak kodunu otomatik olarak çözümler ve yapılandırılabilir seçeneklerini okur.
3. Sol tarafta genişlik, yükseklik, et kalınlığı gibi bulunan tüm parametreler kaydırıcı kontrol olarak listelenir.
4. Kaydırıcıları değiştirdiğinizde güncel 3B geometri saniyeler içinde yeniden derlenir.

## 4. Donanım Hızlandırmalı Tarayıcı Motoru & Taslak Modu

MakerSpell Stüdyo, hibrit bir derleme mimarisiyle çalışır:

- **İstemci Tarafında WebAssembly (WASM)**: Geometrik hesaplamalar doğrudan cihazınızın tarayıcısında çalıştırılır. İlk ziyarette 3 MB altına sıkıştırılan motor bileşenleri Service Worker ile kalıcı olarak önbelleğe alınır ve sonraki girişlerde sıfır ağ gecikmesi sunar.
- **Gerçek Zamanlı Taslak (Draft) Modu**: Kaydırıcıları sürüklerken stüdyo hızlı taslak moduna (`Taslak`) geçerek geometriyi 200 milisaniye altında anlık olarak önizletir. Parmağınızı kaydırıcıdan çektiğinizde model tam çözünürlüklü detayla son haline getirilir.
- **Otomatik Bulut Geri Çekilme (Fallback)**: Düşük bellekli mobil cihazlarda veya eski tarayıcılarda sistem kesinti yaşatmadan otomatik olarak güvenli bulut derleyicisine geçiş yapar.

## 5. 3B Baskı İçin Dışa Aktarma & Uygulamada Dilimleme

Modelinizi istediğiniz ölçülere getirdikten sonra:

1. **STL İndir**: Üst menüdeki **STL İndir** butonuna tıklayarak ikili (binary) STL dosyasını anında cihazınıza kaydedin.
2. **Uygulamada Dilimle**: **Uygulamada Dilimle** butonuna tıkladığınızda model otomatik olarak MakerSync veya OrcaSlicer masaüstü uygulamanıza köprü bağlantıyla aktarılır.
3. Dosyayı dilimleme yazılımınızda (MakerSync, Bambu Studio, OrcaSlicer, PrusaSlicer, Creality Print vb.) açıp baskıya başlayabilirsiniz.

> [!IMPORTANT]
> İndirilen dosyalar standart ikili STL formatında ve doğru yüzey normalleriyle üretildiğinden ek bir ağ onarımı gerektirmeden tüm masaüstü dilimleyicilerde sorunsuz çalışır.
