# Parametrik GitHub Modelleri (OpenSCAD)

MakerSpell, GitHub üzerinde OpenSCAD kaynak kodu olarak yayınlanan **parametrik 3B modelleri** de dizinler. STL dosyalarından farklı olarak bu modeller birer *koddur*: şekil, ayarlanabilir sayılardan (genişlik, yükseklik, duvar kalınlığı, delik çapı, etiket metni vb.) üretilir. Onları diğer modeller gibi gezebilir, daha sonra dışa aktarmadan önce bu sayıları değiştirmek üzere Parametrik Stüdyo'da açabilirsiniz.

> [!NOTE]
> Parametrik modeller topluluk tarafından kendi depo lisansları altında paylaşılır. Yazdırmadan veya yeniden satmadan önce model sayfasında gösterilen lisansa mutlaka göz atın.

## 1. Parametrik modelleri bulma

1. Ana menüden **Browse** (Keşfet) sayfasını açın.
2. Soldaki platform filtresinden **GitHub**'ı seçin — veya arama kutusuna **GitHub** yazarak yalnızca bu kaynağı arayın.
3. Aradığınızı yazın; örneğin *gridfinity*, *bracket*, *label*, *enclosure* ya da *openscad*.

GitHub'dan gelen kartlarda **Parametrik** etiketi görünür ve önizleme görseli doğrudan yazarın deposundan alınır; yani gördüğünüz şey projenin gerçekten ürettiği şeydir.

> [!TIP]
> Platform filtresi olmadan arama yaparsanız GitHub sonuçları diğer tüm pazaryerleriyle karışır. Yalnızca düzenlenebilir modeller istiyorsanız önce GitHub'a filtreleyin.

## 2. Model sayfasını okuma

Sonuçlardan birine tıklayarak detay sayfasını açın. Bir GitHub model sayfası şunları gösterir:

| Bölüm | Ne görürsünüz |
| --- | --- |
| Galeri | Proje deposundan ve dokümantasyonundan alınan görseller |
| Açıklama | Proje özeti ve kaç adet OpenSCAD kaynak dosyası içerdiği |
| Yazar | Avatarıyla birlikte depo sahibi ve orijinal projeye bağlantı |
| İstatistik | Yıldızlar (beğeni olarak) ve çatallamalar (indirme olarak) |
| Etiketler | Depo konu başlıkları; aramayı da bu etiketler besler |
| Lisans | Deponun belirttiği lisans |
| Kaynak dosyalar | İndirebileceğiniz veya stüdyoda açabileceğiniz `.scad` dosyaları |
| Eylemler | Kaydet, paylaş, Parametrik Stüdyo'da aç veya orijinal projeye git |

Bir depoda kullanılabilir ekran görüntüsü yoksa MakerSpell kırık bir görsel yerine temiz bir teknik çizim yer tutucusu çizer; hiçbir kart boş kalmaz.

## 3. Stüdyoda kişiselleştirme

GitHub model sayfasından **Customize in 3D Studio** (3B Stüdyoda Kişiselleştir) seçeneğine basın. Stüdyo, modelin kaynağı ekli olarak açılır; parametreleri kaydırıcı ve sayı alanlarına dönüştürür. Değerleri değiştirin, önizlemenin güncellenmesini izleyin ve sonucu dilimlemek üzere mesh olarak dışa aktarın.

> [!IMPORTANT]
> Bir GitHub modelini düzenlemek kendi yerel varyantınızı oluşturur. Orijinal depo asla değiştirilmez ve kişisel kullanım için parametreleri değiştirmek üzere yazardan izin almanız gerekmez — ancak yayınladığınız her şey için lisans hâlâ geçerlidir.

## 4. Dizini güncel tutma

GitHub dizini günde bir kez otomatik olarak yenilenir; yeni yayınlanan ve güncellenen projeler sizin bir şey yapmanıza gerek kalmadan görünür. Bir proje eskimiş görünüyorsa modeli açıp orijinal depo bağlantısından en son durumu doğrulayabilirsiniz.

## Sorun giderme

| Belirti | Çözüm |
| --- | --- |
| Hiç GitHub kartı görünmüyor | Arama kutusunu temizleyin, ardından platform filtresinden GitHub'ı yeniden seçin |
| Kartta teknik çizim yer tutucusu var | Bu projenin deposunda henüz görsel yok; modeli açıp kaynak dosyalara bakın |
| Model sayfasında görsel yok | Yukarıdakiyle aynı sebep — galeri kaynak dosya listesine düşer |
| Stüdyo "modelin parametresi yok" diyor | Proje, üst düzey parametre içermeyen düz `.scad` dosyaları içeriyor olabilir; yine de indirip yerelde düzenleyebilirsiniz |
