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

Görünüm alanı, modelinizi gerçek zamanlı aydınlatma, tam tabla sıfırlama ve fiziksel ölçülerle üç boyutlu olarak gösterir:

- **Baskı Tablası Hizalama**: Tüm modeller fiziksel 3B yazıcı koordinatlarıyla tam uyumlu şekilde dik açıyla konumlandırılır ve tabanı baskı ızgarasının ($Y = 0$) tam üzerine sıfırlanır.
- **Genişletilmiş Çalışma Alanı**: Stüdyoya girildiğinde ana menü çubuğu otomatik olarak 72 piksellik kompakt simge moduna geçerek 3B tuval için maksimum ekran alanı açar.
- **Döndürme (Yörünge)**: Sol fare tuşuna basılı tutarak sürükleyin (dokunmatik ekranlarda tek parmakla kaydırın).
- **Yakınlaşma / Uzaklaşma**: Fare tekerleğini çevirin (dokunmatik ekranlarda iki parmakla kıstırma hareketi yapın).
- **Tel Kafes (Wireframe) Modu**: Üst araç çubuğundaki **Tel Kafes** butonuna tıklayarak poligon yoğunluğunu, üçgen yapısını ve iç duvar örüntülerini inceleyin.
- **Arkadan Işık Vurma**: Litofan modellerinde **Işık Açık / Işık Kapalı** butonunu kullanarak ışığın yarı saydam filament katmanlarından nasıl geçtiğini simüle edin.
- **Canlı Bilgi Paneli (HUD)**: Sağ alt köşedeki panelde anlık üçgen (poligon) sayısı, milimetre cinsinden model boyutları ($X \times Y \times Z$) ve derleme süresi gösterilir.

## 3. Harici Modeller & 3B Kabartma Yazılar (Thingiverse, GitHub)

Yalnızca dahili şablonlarla sınırlı değilsiniz. MakerSpell üzerinde **Düzenlenebilir (Parametrik)** filtresiyle model ararken:

1. Desteklenen herhangi bir model sayfasında **3B Stüdyoda Kişiselleştir** butonuna tıklayın.
2. Stüdyo, platform rozeti, model başlığı ve orijinal model bağlantısını içeren özel bir **Harici Model Kartı** açar.
3. Sol tarafta genişlik, yükseklik, et kalınlığı, metin alanları ve diğer tüm parametreler kaydırıcı kontrol olarak listelenir.
4. **Kabartmalı 3B Yazı Desteği**: Gelişmiş ve klasik yazı tipi motorları (`Write.scad` ve DXF vektör fontları) tam desteklenir; böylece evcil hayvan mama kaplarındaki kavisli isim kabartmaları, anahtarlıklar ve etiketler eksiksiz üretilir.
5. Dahili parametrik şablonları denemek isterseniz **Dahili Şablonlar** butonuna basarak geçiş yapabilir, dilediğiniz an harici modelinize geri dönebilirsiniz.

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
