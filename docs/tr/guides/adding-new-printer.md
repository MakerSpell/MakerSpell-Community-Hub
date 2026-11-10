# Yeni Bir Yazıcı Profili Ekleme ve Test Etme Rehberi

MakerSpell, farklı marka ve modeldeki 3D yazıcıları sisteme dahil etmek için açık ve deklaratif bir sürücü profili (`profile-v2`) mimarisi kullanır. Bu rehber; yeni bir yazıcı modelini MakerSpell Masaüstü veya Mobil uygulaması üzerinden **herhangi bir kodlama veya geliştirici aracına ihtiyaç duymadan**, doğrudan uygulama arayüzünden nasıl içe aktaracağınızı, test edeceğinizi ve kullanıma alacağınızı adım adım açıklamaktadır.

---

## 1. Hazırlık: Profil Dosyası (.json)

Yazıcınızı tanıtan profil, standart bir `.json` metin dosyasıdır. Dosya içerisinde temel olarak şu bilgiler yer alır:

1. **Yazıcı Kimliği (Identity):** Marka adı, desteklenen model isimleri ve profil kimlik numarası (örn: `community.mybrand-modelx.v2`).
2. **Ağ Kanalları (Channels):** Yazıcının yerel ağda dinlediği bağlantı protokolü ve servis portu (Örn: HTTP / WebSocket portu `80`, `7125` veya `9999`).
3. **İşlemler (Operations):** Yazıcıdan durum bilgisi almak veya dosya transfer etmek için kullanılan endpoint yolları (Örn: `/api/status`, `/printer/info`).
4. **Telemetri Haritalaması (State):** Nozul ve tabla sıcaklıkları gibi canlı değerlerin JSON yanıtından okunacağı anahtarlar.

> [!TIP]
> Profilinizin yapısını oluştururken [profile-v2 Şartnamesi](file:///D:/YazilimProgramlama/3DEticaretOtomasyon/community-hub/docs/schemas/profile-v2-specification.md) sayfasındaki açık şemayı ve örnek profilleri inceleyebilirsiniz.

---

## 2. Adım Adım Uygulama İçi İçe Aktarma ve Doğrulama

### Adım 1: Sürücü Yönetim Ekranını Açın
1. MakerSpell uygulamasını (Masaüstü veya Mobil) başlatın.
2. Sol menüden veya üst çubuktan **Ayarlar** (`Settings`) bölümüne gidin.
3. **"3D Yazıcı Sürücüleri ve Bağlantı Kuralları"** (`Printer Connection & Interface Rules`) seçeneğini açın.

### Adım 2: JSON Profil Dosyasını Seçin
1. Ekranın sağ üst köşesinde yer alan **"Profil İçe Aktar (.json)"** (klasör/dosya simgesi) butonuna dokunun.
2. Açılan yerel dosya penceresinden (Windows Gezgini, macOS Finder veya Mobil Dosyalar) hazırladığınız `.json` profil dosyasını seçin.

### Adım 3: Otomatik Şema ve Güvenlik Denetimi
Dosya seçildiği anda MakerSpell doğrulama motoru devreye girer:
- **Şema Doğrulaması:** Dosyanın sözdizimi, zorunlu alanları ve kanal tanımları saniyeler içinde taranır. Eğer eksik veya hatalı bir alan varsa hata ayrıntısı net bir uyarı kutusuyla gösterilir.
- **Safe-Mode (Fiziksel Donanım Güvenliği):** Henüz laboratuvarımızda fiziksel stres testlerinden geçmemiş tüm topluluk donanımları için otomatik olarak **"Güvenli Mod (Safe-Mode)"** rozeti aktif edilir. Bu modda dosya transferi yapılabilir; ancak donanım güvenliğiniz için baskının fiziksel olarak başlatılması makine panelinden operatör onayına bırakılır.

---

## 3. Canlı Cihaz Bağlantı Testi (In-App Connectivity Test)

Doğrulama penceresi açıkken profili sisteme kaydetmeden önce yazıcınızla canlı olarak test edebilirsiniz:

1. Penceredeki **"Yazıcı IP / Hostname"** alanına yazıcınızın yerel ağdaki IP adresini girin (örn: `192.168.1.120`). Eğer ağda bağlı bir yazıcınız varsa IP adresi otomatik doldurulur.
2. **"Bağlantıyı Test Et"** (`Test Connection`) butonuna tıklayın.
3. Uygulama, profilinizde tanımlı servis portuna ve durum endpoint'ine doğrudan test isteği gönderir:
   - ✅ **Yeşil Onay Rozeti:** Yazıcıdan başarılı yanıt alındığında ağ gecikmesi (örn: `42 ms`) ve bağlantı durumu yeşil onay işaretiyle raporlanır.
   - ❌ **Kırmızı Hata Uyarısı:** Eğer IP adresi hatalıysa, port kapalıysa veya yanıt alınamadıysa bağlantı hatası ekranda listelenir.

---

## 4. Profili Etkinleştirme veya Düzenleme

- **Doğrudan Kullanım:** Test başarılı olduğunda pencerenin altındaki **"Yükle ve Etkinleştir"** (`Install & Activate`) butonuna basarak profili anında cihazınıza kaydedebilir ve yazıcınızla iletişim kurmaya başlayabilirsiniz.
- **Dahili Görsel Editörle Özelleştirme:** İsterseniz penceredeki **"Editörde Aç"** (`Open in Editor`) seçeneğini kullanarak butonları, göstergeleri, kamera akışını veya özel kontrol panellerini MakerSpell'in dahili Form ve Görsel Önizleme editöründen düzenleyebilirsiniz.

---

## 5. Topluluk Kataloğuna Katkıda Bulunma (Opsiyonel)

Hazırladığınız ve cihazınızda başarıyla test ettiğiniz profilin diğer kullanıcıların da erişimine açılmasını isterseniz:
1. Profilinizi [MakerSpell Community Hub](https://github.com/MakerSpell/MakerSpell-Community-Hub) deposuna Pull Request olarak iletebilirsiniz.
2. Topluluk incelemesinin ardından sürücünüz resmi kataloğa dahil edilerek tüm küresel kullanıcılara sunulur.
