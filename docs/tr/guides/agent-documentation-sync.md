# 🤖 Yapay Zeka Ajanları İçin Doküman Güncelleme Kuralı (Agent Documentation Sync Rule)

> **TÜM AI AJANLARI İÇİN KESİN VE TAVİZSİZ PROTOKOL:**  
> (Antigravity, Claude, Cursor, Windsurf, Command Code, Copilot, ChatGPT)

---

## 📌 1. Kuralın Tanımı: Sıfır Kod İfşası & Kullanım Odaklılık

MakerSpell ekosisteminde masaüstü ve mobil Flutter uygulamasına (`makersync_app`) veya web platformuna (`web/`) **herhangi bir yeni özellik, arayüz, ekran, buton veya işlevsellik eklendiğinde ya da değiştirildiğinde**;
o özelliğin **`community-hub/docs/`** altında belgelenmesi **KESİNLİKLE ZORUNLUDUR**.

### ⚠️ EN KRİTİK GÜVENLİK VE TİCARİ SIR KURALI:
- **KOD DETAYI ASLA YAZILMAYACAKTIR:** Dokümantasyon sayfalarına projenin kaynak kodlarını, dahili Dart/TypeScript/backend sınıflarını, iç mimarisini veya ticari sırlarını açığa çıkaracak hiçbir kod parçacığı (code snippet) YAZILMAYACAKTIR.
- **KULLANICI REHBERİ FORMATI:** Dokümantasyon yalnızca ve sadece **son kullanıcının veya maker'ın uygulamayı ve web sitesini adım adım nasıl kullanacağını** anlatan rehberler (`User Guide / How-to`) içerecektir.
  - *Örnek Doğru Yaklaşım:* "Ağ Yazıcıları sekmesini açın, sağ üstteki Tara butonuna basın, cihazınız listede belirdiğinde Bağlan'a tıklayın."
  - *Örnek Hatalı Yaklaşım:* "NetworkPrinterProvider sınıfı _scan() metodunu çağırır ve mDNS soketini dinler." (BU YASAKTIR).

---

## 📌 2. Adım Adım Güncelleme Kontrol Listesi

Bir özellik tamamlandığında ajan sırasıyla şu adımları izlemelidir:

1. **İlgili Rehber Klasörünü Seç:**
   - Masaüstü veya Mobil Flutter arayüzünde yeni bir özellik/ekran varsa -> `community-hub/docs/app-guide/`
   - Web sitesinde (`makerspell.com`) yeni bir sayfa, arama filtresi veya özellik varsa -> `community-hub/docs/web-guide/`
   - Yeni bir yazıcı protokolü veya donanım desteğiyse -> `community-hub/docs/printers/`
2. **Kullanım Kılavuzunu Yaz / Güncelle:**
   - Kullanıcının ekranda göreceği butonları, adımları, uyarıları ve faydaları açık, anlaşılır bir dille açıklayın.
3. **Manifestoyu Güncelle:**
   - Yeni sayfa eklendiyse veya başlık değiştiyse `community-hub/docs/manifest.json` dosyasına işleyin.
4. **Log ve Vault Bildirimi:**
   - Yapılan güncellemeyi `MakerSpell-Vault/agents/antigravity_printer_connection_interface_logs.md` (veya ilgili ajanın günlüğüne) kaydedin.
