# Parametrik 3B Model Stüdyosu & Üreteç

MakerSpell Stüdyo (`/studio/parametric`), doğrudan tarayıcınız üzerinden etkileşimli 3B modelleme ve kişiselleştirme ortamı sunar. İster fotoğraflarınızdan kişiye özel litofan gece lambaları üretin, ister atölyeniz için milimetrik organizatör kutuları tasarlayın; stüdyo gerçek 3B geometrileri derleyerek dilimleyiciye hazır STL dosyalarını anında indirmenizi sağlar.

## 1. Dahili Parametrik Şablonlar

Stüdyo, farklı kullanım senaryolarına yönelik hazır parametrik şablonlarla birlikte gelir:

| Şablon | En Uygun Kullanım | Temel Parametreler |
| --- | --- | --- |
| **Litofan Fotoğraf & Gece Lambası** | Kişiye özel kabartmalı tablolar, kavisli gece lambaları | Görsel yükleme, şekil (kavisli, düz, silindir, priz aparatı), genişlik, min/maks katman kalınlığı, kavis açısı |
| **Özel Kutu & Organizatör** | Donanım ve parça saklama kutuları, milimetrik çekmeceler | İç ölçü odaklı tasarım, iki eksenli $N \times M$ bölmeler, kapak tipi (geçmeli, kızaklı raylı, kapaksız), istiflenebilir kilit ayağı, tolerans kontrolü |
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
- **Canlı Bilgi Paneli (HUD) & Anlık Boyut Rozeti**: Sağ alt köşedeki panelde anlık üçgen sayısı, derleme süresi ve ekranın altında net **Dış Ölçüler ($G \times D \times Y$)**, **İç Kapasite** ve hesaplanan **İç Hacim ($cm^3$)** rozeti yer alır.
- **Saliseler İçinde Anlık Tepki**: Kutu düzenleyicide kaydırıcıları çekerken model 60 FPS hızında (<1 ms) anında yenilenir; derleme beklemesi olmadan hem kutu hem kapak anlık olarak şekil alır.
- **Desteksiz Baskı Yerleşimi**: "Kutu + Kapak" modu seçildiğinde, kapak düz yüzeyi tablaya oturacak şekilde 180° ters çevrilerek kutunun yanına yerleştirilir; böylece sıfır destekle doğrudan baskı alınabilir.

## 3. Harici Modeller & 3B Kabartma Yazılar (Thingiverse, GitHub)

Yalnızca dahili şablonlarla sınırlı değilsiniz. MakerSpell üzerinde **Düzenlenebilir (Parametrik)** filtresiyle model ararken:

1. Desteklenen herhangi bir model sayfasında **3B Stüdyoda Kişiselleştir** butonuna tıklayın.
2. Stüdyo, platform rozeti, model başlığı ve orijinal model bağlantısını içeren özel bir **Harici Model Kartı** açar.
3. Sol tarafta genişlik, yükseklik, et kalınlığı, metin alanları ve diğer tüm parametreler kaydırıcı kontrol olarak listelenir.
4. **Standart Kütüphaneler & 3B Kabartma Yazı Desteği**: Popüler OpenSCAD kütüphaneleri hiçbir ek kuruluma gerek kalmadan doğrudan kullanılabilir:
   - **MCAD**: Dişliler, rulmanlar, step motor yuvaları, standart kutular ve montaj donanımları.
   - **threads.scad**: Yüksek hassasiyetli metrik vida dişleri, cıvatalar ve kavanoz kapakları.
   - **Round-Anything**: Yumuşak kavisli köşeler (fillet), pahlar ve ergonomik yuvarlatmalar.
   - **Write.scad & DXF Tipografi**: Silindirler, evcil hayvan mama kapları ve etiketler üzerine kavisli 3B kabartma yazılar.
   - **Çoklu Parça İçe Aktarma**: Modele eşlik eden harici bileşenler (`import("part.stl")` veya vektör çizimler) otomatik olarak algılanıp derleme ortamına bağlanır.
5. Dahili parametrik şablonları denemek isterseniz **Dahili Şablonlar** butonuna basarak geçiş yapabilir, dilediğiniz an harici modelinize geri dönebilirsiniz.

## 4. Hızlandırılmış Manifold Tarayıcı Motoru & Taslak Modu

MakerSpell Stüdyo, yüksek performanslı hibrit bir derleme mimarisiyle çalışır:

- **Manifold CSG Motoru (10x-50x Daha Hızlı)**: Geometrik hesaplamalar modern Manifold boolean motoruyla çalıştırılır; karmaşık modeller doğrudan tarayıcınızda onlarca milisaniye içinde derlenir. Manifold uyumsuz eski şekillerde sistem kesintisiz olarak CGAL motoruna geri çekilerek %100 derleme garantisi sunar.
- **Doğrudan İkili STL Üretimi**: Bellek şişmesine yol açan metin dönüşümleri atlanarak doğrudan saf ikili STL üretilir; yüz binlerce üçgen içeren modellerde dahi anlık akıcılık korunur.
- **Gerçek Zamanlı Taslak (Draft) Modu**: Kaydırıcıları sürüklerken stüdyo hızlı taslak moduna (`Taslak`) geçerek geometriyi 100 milisaniye altında anlık olarak önizletir. Parmağınızı kaydırıcıdan çektiğinizde model tam çözünürlüklü detayla son haline getirilir.
- **Otomatik Bulut Geri Çekilme (Fallback)**: Düşük bellekli mobil cihazlarda veya eski tarayıcılarda sistem kesinti yaşatmadan otomatik olarak güvenli bulut derleyicisine geçiş yapar.

## 5. 3B Baskı İçin Dışa Aktarma & Uygulamada Dilimleme

Modelinizi istediğiniz ölçülere getirdikten sonra:

1. **STL İndir**: Üst menüdeki **STL İndir** butonuna tıklayarak ikili (binary) STL dosyasını anında cihazınıza kaydedin.
2. **Uygulamada Dilimle**: **Uygulamada Dilimle** butonuna tıkladığınızda model otomatik olarak MakerSync veya OrcaSlicer masaüstü uygulamanıza köprü bağlantıyla aktarılır.
3. Dosyayı dilimleme yazılımınızda (MakerSync, Bambu Studio, OrcaSlicer, PrusaSlicer, Creality Print vb.) açıp baskıya başlayabilirsiniz.

## 6. Bulut Kasasına Kaydetme & Mobil Senkronizasyon

MakerSpell entegre bir **Parametrik Bulut Kasası** içerir:

- **Kasaya Kaydet**: Stüdyo üst menüsündeki **Kasaya Kaydet** butonuna tıklayarak belirlediğiniz ölçüleri, bölme düzenini ve kapak tipini doğrudan bulut profilinize kaydedin.
- **Saf Reçete Senkronizasyonu**: Ağır 3B modeller yerine tasarımınız hafif bir parametre reçetesi olarak saklanır. Böylece anında **MakerSync mobil ve masaüstü uygulamanızla** senkronize olur.
- **Kasanıza Erişim**: **Profilim** (`/profile`) sayfasına gidip **Özelleştirilmiş Tasarımlar** sekmesine tıklayarak kayıtlı kutularınızı listeleyebilir, ölçüleri inceleyebilir, tek tıkla stüdyoda yeniden açabilir veya baskıya hazır STL dosyasını indirebilirsiniz.
- **Toplulukla Paylaşım**: Tasarımınızı kaydederken herkese açık yapmayı seçebilir, diğer üreticilerin sizin ölçülerinizi incelemesine ve remikslemesine olanak sağlayabilirsiniz.

## 7. Bağımsız Topluluk Vitrini & Tek Tıkla Remiksleme (`/studio/parametric/community`)

**Topluluk Vitrini**, maker'ların paylaştığı Gridfinity kutularını, koruma kılıflarını, anahtarlıkları ve atölye düzenleyicilerini sergileyen bağımsız bir galeridir:

- **Keşfet & Filtrele**: Modelleri kategorilere göre (Gridfinity, Parametrik Kutu, Anahtarlık, Litofan) filtreleyin veya arama kutusundan istediğiniz ölçüyü, aleti veya yazarı anında bulun.
- **Tek Tıkla Stüdyoda Remiksle**: Beğendiğiniz herhangi bir karttaki **Stüdyoda Remiksle** butonuna bastığınızda, modelin tüm milimetrik parametreleri doğrudan 3B Stüdyo sahnenize yüklenir. İster ölçüleri genişletin, ister ek bölmeler ekleyin; beklemeden düzenleyin.
- **Parametre Kopyalama & Paylaşma**: Tasarımın parametre reçetesini tek tıkla JSON olarak panoya kopyalayabilir veya doğrudan arkadaşlarınızla bağlantı paylaşabilirsiniz.
- **Sıfır Depolama Maliyeti**: Tüm topluluk modelleri yalnızca ~350 baytlık hafif JSON reçeteleri olarak depolanır; sunucu şişkinliği yaratmadan sınırsız remiks imkanı sunar.

## 8. Kutu İçi Sanal Nesne Testi & Fiziksel Uyum Simülatörü

Dilimleme yapıp filament harcamadan önce tasarladığınız kutunun içine gerçek fiziksel eşyalarınızın sığıp sığmadığını test edin:
- **Anında Nesne Yerleştirme**: Üst araç çubuğundaki veya sol paneldeki **Sanal Nesne Testi** butonuna tıklayarak simülatör penceresini açın. Popüler atölye nesnelerinden (18650 piller, AA/AAA piller, USB bellekler, SD kartlar, alyan uçları, M3 vidalar) birini seçin.
- **Gerçek Zamanlı Çarpışma Analizi**: 3B motoru kutunun iç hacmini anlık olarak hesaplar, yan yana baskı tablası (`both_plate`) kaydırmasını otomatik hesaba katar ve sığma durumunu yeşil tolerans paylarıyla, taşma durumunu ise X, Y ve Z eksenlerindeki milimetrik farklarla kırmızı uyarı şeklinde gösterir.
- **Yatış Şekli & Çoklu Paket Testi**: Nesneleri dik veya yatay olarak konumlandırabilir, 1'li, 2'li, 4'lü veya 6'lı paket halinde aralarında 2 mm boşluk bırakılarak kutuya dizilişini 3B sahnede görebilirsiniz.

## 9. Çoklu Format Çıktısı (STL & 3MF) ve Gerçek Zamanlı Filament Rengi

- **STL & 3MF Çift Format Çıktısı**: Üst araç çubuğundaki indirme düğmesinde yer alan açılır menüden **İkili STL** veya **Üretim 3MF** formatını seçebilirsiniz. 3MF formatı modelin milimetre ölçeğini, yüzey normallerini ve sahne rengini içerir; Bambu Studio, OrcaSlicer, PrusaSlicer ve Cura tarafından doğrudan renklendirilmiş olarak açılır.
- **3B Model & Filament Rengi Değiştirici**: Üst menüdeki **Renk** butonuna tıklayarak modelinizi popüler maker renklerine (Maker Mavisi, Saf Beyaz, Mat Siyah, Yakut Kırmızı, Prusa Turuncu, Bambu Yeşil, vb.) büründürebilir veya özel renk paletinden dilediğiniz rengi seçebilirsiniz. Seçilen renk anında 3B sahnede güncellenir, tarayıcıda hatırlanır ve 3MF dosyasına gömülür.

> [!IMPORTANT]
> İndirilen STL ve 3MF dosyaları standart ikili formatta ve doğru yüzey normalleriyle üretildiğinden ek bir ağ onarımı gerektirmeden tüm masaüstü dilimleyicilerde sorunsuz çalışır.
