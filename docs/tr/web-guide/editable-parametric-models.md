# Tüm Platformlarda Düzenlenebilir (Parametrik) Modeller

Çoğu 3D model bitmiş bir şekildir — olduğu gibi basarsınız. **Düzenlenebilir modeller** farklıdır: geometrileri değiştirebileceğiniz sayılardan üretilir, böylece tek bir indirme yüzlerce ölçü, etiket veya varyanta dönüşebilir. MakerSpell, her pazaryeri bu özelliğe başka bir isim verse de tek bir filtreyle hepsinde bulmanızı sağlar.

## 1. Filtreyi açmak

1. **Browse** sayfasını açın.
2. Tek bir platform (tekli mod) veya birkaç platform (çoklu mod) seçin.
3. Sonuçların üstündeki kontrol çubuğunda **Düzenlenebilir (Parametrik)** düğmesine tıklayın.

Filtre açıkken düğme vurgulu kalır ve üstteki aktif filtre sayacı bir artar. Kapatmak için tekrar tıklayın.

> [!TIP]
> Filtre her iki modda da çalışır. Tekli platform modunda uygulanmaya devam eden tek genel filtredir — sıralama, zaman aralığı ve lisans o platformun kendi kontrollerine bırakılır.

## 2. Her platformda ne oluyor

Platformlara özel terimleri hatırlamanız gerekmez. MakerSpell tek filtreyi o pazaryerinin gerçekten desteklediği mekanizmaya çevirir:

| Platform | Gönderilen | Ne elde edersiniz |
| --- | --- | --- |
| Thingiverse | `customizable=1` | Thingiverse Customizer ile yayınlanmış modeller |
| Printables | OpenSCAD modelleme uygulaması | OpenSCAD ile üretilmiş, parametre editörünün kaynağı olan modeller |
| MakerWorld | `custom` ve `param` model etiketleri | Özelleştirilebilir ve parametrik tasarımlar birlikte |
| Thangs | Arama metnine eklenen `.scad` | Thangs dizinindeki OpenSCAD projeleri |
| GitHub | OpenSCAD kataloğu | Kaynağı parametrik `.scad` programı olan depolar |

Kendi düzenlenebilir model mekanizması olmayan platformlar filtre açıkken **atlanır**; böylece filtreyi sessizce yok sayan bir liste görmezsiniz.

> [!NOTE]
> MakerWorld sonuçları o platformun sunucularının normal yanıt vermesine bağlıdır. Sonuç gelmezse daha sonra tekrar deneyin veya başka bir platforma geçin — diğer kaynaklar etkilenmez.

## 3. Sonuçtan çalışan bir editöre

**Parametrik** rozetini taşıyan herhangi bir sonucu açın. Giriş yapmadan indirmeye izin veren platformlarda — Thingiverse, Printables ve GitHub — model sayfasındaki birincil düğme **3D Stüdyoda Özelleştir** olur:

- Stüdyo o model üzerinde açılır. Yazar düzenlenebilir kaynağı `.scad` dosyası olarak yayınladıysa parametreleri otomatik algılanır ve kaydırıcı/sayı alanları olarak görünür.
- Genişlik, yükseklik, duvar kalınlığı, delik çapı, metin gibi değerler için kaydırıcılar ve sayı alanları görünür.
- Memnun kaldığınızda sonucu ağ olarak dışa aktarın.

Dosya indirmek için hesap zorunlu olan platformlarda birincil düğme **MakerSpell Uygulamasında Aç** olarak kalır, çünkü masaüstü ve mobil uygulamalar o platformun oturumunu taşıyabilir. Model parametrikse stüdyo kısayolu ikincil düğme olarak yine görünür.

> [!IMPORTANT]
> Bir modeli düzenlemek kendi yerel varyantınızı oluşturur. Orijinal hiçbir zaman değişmez, ancak yayınladığınız her şey için yazarın lisansı geçerlidir.

## 4. Aradığınızı bulamadığınızda

| Belirti | Çözüm |
| --- | --- |
| Filtre açıkken hiç sonuç yok | Seçili platformda kelimelerinize uyan düzenlenebilir model olmayabilir — arama kutusunu temizleyin veya başka platformlar ekleyin |
| Sonuçlar konuyla ilgisiz | Filtreyi kapatıp modelin gerçekten parametrik olup olmadığını kontrol edin; bazı yazarlar sıradan modelleri de bu şekilde etiketliyor |
| Stüdyo açılıyor ama parametre yok | `.scad` kaynağında üst düzey parametre olmayabilir; kodu editörde yine okuyup düzenleyebilirsiniz |
| Bir platform hiç sonuç vermiyor | Bu kaynak, filtreyi uygulayamadığı için tasarım gereği atlanıyor |

## İlgili kılavuzlar

- [GitHub Parametrik Modeller (OpenSCAD)](parametric-github-models.md)
- [26 Platformlu 3D Model Arama ve Filtreler](model-search.md)
