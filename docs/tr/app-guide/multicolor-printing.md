# 🎨 Çok Renkli Baskı ve Filament (CFS / AMS) Yönetimi

MakerSpell, çok renkli ve çok malzemeli 3D baskı sistemlerini (Creality CFS, Snapmaker AMS vb.) akıllı bir şekilde yönetmenizi sağlar.

---

## 📌 1. Filament Yuvalarını Görüntüleme

Uygulamanın kontrol panosunda ve G-code gönderme ekranında yazıcınızın kaç filament yuvasına sahip olduğu listelenir:
- Her yuvanın üzerindeki renk simgesi, takılı filamentin rengini gösterir (Beyaz, Siyah, Kırmızı, Mavi vb.).
- Filamentin türü (Örn: *Hyper PLA*, *PETG-HF*, *TPU*) otomatik okunur veya manuel seçilebilir.
- Yuva boş ise simge gri renkte görünür.

---

## 📌 2. Model ile Yuvaları Eşleştirme

İki veya daha fazla renk içeren bir model bastırmak istediğinizde:
1. G-code gönderici ekranı modeldeki renkleri inceler.
2. Yazıcınızdaki yuvalarla en yakın renkleri otomatik eşleştirir.
3. Eğer modeldeki renk yazıcınızda takılı değilse, sistem sizi uyarır ve hangi yuvanın o renk yerine kullanılacağını seçmenize olanak tanır.
4. Eşleştirme onaylandıktan sonra baskı doğrudan çok renkli olarak başlar.

---

## 📌 3. Harici Makara (Spool Holder) Kullanımı

Eğer CFS veya AMS ünitesi kullanmıyor, doğrudan yazıcının arkasındaki makara tutucudan baskı alıyorsanız:
- Sistem tek yuvalı "Harici Makara" moduna geçer.
- Herhangi bir yuva seçimi yapmanıza gerek kalmadan tek renkli baskınızı güvenle başlatabilirsiniz.
