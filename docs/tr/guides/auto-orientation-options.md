# Otomatik Yönlendirme Seçenekleri Rehberi

Karmaşık 3D modelleri baskıya hazırlarken, modelin tabla üzerindeki en doğru açı ve yönelimini bulmak baskı süresini ciddi oranda kısaltabilir, destek malzemesi israfını azaltır ve yüzey kalitesini artırır.

MakerSpell, üst düzenleme araç çubuğundan doğrudan erişilebilen akıllı bir Otomatik Yönlendirme menüsü sunar.

---

## 🧭 Seçenekler Menüsünü Açma

1. Sanal baskı tablası üzerindeki bir modeli seçin.
2. Üst araç çubuğundaki **Otomatik Yönlendir (Auto Orient)** simgesine tıklayın.
3. Düzenleyici çubuğunun hemen altında **Otomatik yönlendirme seçenekleri** başlıklı açılır pencere görüntülenir.

---

## ⚙️ Yönlendirme Stratejileri

Açılır pencerede üç farklı optimizasyon modu bulunur:

| Mod | Strateji ve Kullanım Alanı |
|---|---|
| **Varsayılan (Default)** | **Dengeli tabla teması ve sarkma yönetimi.** Güçlü ilk katman yapışması ile hafif sarkma açıları arasında optimum dengeyi kurar. Genel 3D modeller ve figürler için önerilir. |
| **Destek hacmini en aza indir (Minimize support volume)** | **Sıkı sarkma cezası.** En az destek yapısı gerektiren açıları önceler. Organik formlar, detaylı minyatürler ve destek temizliği zor olan karmaşık yüzeyler için idealdir. |
| **Baskı süresini en aza indir (Minimize print time)** | **Düşük Z yüksekliği profili.** Modelin dikey yüksekliğini ve dolayısıyla toplam katman sayısını düşürür. Hızlı üretim hedeflenen fonksiyonel parçalar ve braketler için idealdir. |

---

## 🚀 Eylemler

- **Yönlendir (Orient)**: Seçilen stratejiyi kullanarak model geometrisini analiz eder, en uygun rotasyon açılarını hesaplar ve modeli otomatik taban sıfırlamasıyla (Z-snap) tablaya yerleştirir.
- **Sıfırla (Reset)**: Modelin rotasyonunu başlangıç değerlerine `(0°, 0°, 0°)` döndürür ve tabanla temasını korur.

---

## 💡 İpuçları ve Öneriler

- **Tabla Yapışması**: Otomatik yönlendirme sonrasında modelin tabla ile temas eden yüzey alanının yeterli olduğundan emin olun. Taban alanı darsa, Baskı Ayarları altından Kenarlık (Brim) veya Fare Kulakları (Mouse Ears) ekleyebilirsiniz.
- **Çoklu Modeller**: Otomatik yönlendirme seçili model bazında çalışır. Tablanızdaki her modeli kendi geometrisine göre ayrı ayrı optimize edebilirsiniz.
