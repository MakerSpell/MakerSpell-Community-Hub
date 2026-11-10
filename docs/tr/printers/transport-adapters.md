# Taşıma Katmanları (Transport Adapters) & Protokoller

MakerSpell, her yazıcının kullandığı fiziksel ağ protokolünü standart bir bağlantı sözleşmesine bağlayan modüler adaptörler içerir. Bu adaptörler ağ soketlerini, kimlik doğrulamalarını ve veri paketlemeyi yönetir.

---

## 1. Desteklenen Protokol Yetenekleri

Her taşıma adaptörü yazıcıyla aşağıdaki standart işlemler üzerinden iletişim kurar:
- **Cihaz Doğrulama (Probe):** Ağdaki cihazın modeli ve bellenim durumunu anlama.
- **Canlı Telemetri:** Nozul, tabla sıcaklıkları, fan hızları ve iş ilerleme akışı.
- **Dosya Transferi:** Dilimlenmiş G-code dosyalarını kablosuz yükleme.
- **İş Kontrolü:** Baskıyı duraklatma, sürdürme, iptal etme ve acil durdurma (M112).
- **Donanım Kumandası:** Manuel sıcaklık atama ve eksen konumlandırma.

---

## 2. Yerleşik Adaptörler ve Özellikleri

### 1. Moonraker Transport (`moonraker`)
- **Hedef Donanımlar:** Klipper çalıştıran tüm cihazlar (Voron, RatRig, Ender modlu, Sovol vb.).
- **Protokol:** WebSocket (`ws://<ip>:7125/websocket`) + JSON-RPC 2.0 ve HTTP REST API.
- **Yetenekler:**
  - Gerçek zamanlı nesne aboneliği (`server.database`, `printer.objects.query`).
  - G-code konsolu ve canlı terminal.
  - Nozul/tabla sıcaklık grafikleri ve ısıtıcı PID telemetrisi.
  - Virtual SD card üzerinden dosya yönetimi ve küçük resim (thumbnail) çekme.

### 2. Creality Local v2 (`creality_local` / `creality_v2`)
- **Hedef Donanımlar:** Creality K1, K1 Max, K1C, Ender-3 V3, Hi, Hi Combo.
- **Protokol:** HTTP Port 80 (`/info`, `/downloads/gcode/...`) + WebSocket Port 9999 (`{"method":"get","params":{"reqGcodeFile":1}}`).
- **Özel Özellikler:**
  - Creality OS dahili kamera akışı (`http://<ip>:8080/?action=stream`).
  - Dahili CFS (Creality Filament System) 4-renk RFID slot telemetrisi.
  - Tabla haritası (Bed mesh) verisi alma.
  - Kendi özelleştirilmiş dosya transfer endpoint'i (`/upload`).

### 3. OctoPrint v2 Bridge (`octoprint` / `octoprint_v2`)
- **Hedef Donanımlar:** OctoPrint kurulu Raspberry Pi veya Snapmaker U1/Artisan gibi OctoPrint uyumluluk köprüsü sunan cihazlar.
- **Protokol:** HTTP REST (`/api/version`, `/api/printer`, `/api/files/local`, `/api/job`) + API Key yetkilendirmesi.
- **Özel Özellikler:**
  - Snapshot ve canlı MJPEG webcam entegrasyonu (`/webcam/?action=stream`).
  - Güvenli `delegate` işlemleri.

### 4. Bambu Lab Local LAN Transport (`bambu_local`)
- **Hedef Donanımlar:** Bambu Lab X1C, P1S, P1P, A1, A1 Mini.
- **Protokol:** Yerel MQTT (`mqtts://<ip>:8883`) + FTPS (`ftps://<ip>:990`).
- **Güvenlik Kuralı:** Bulut köprüsü KULLANILMAZ. Sadece yazıcının "LAN Only Mode" şifresi ile yerel ağdan bağlanılır.
- **Safe-Mode:** `UPLOAD_ONLY` (Baskı başlatma cihaz ekranından yapılmalıdır).

### 5. Elegoo SDCP Transport (`elegoo_sdcp`)
- **Hedef Donanımlar:** Elegoo Centauri Carbon, Neptune 4 Serisi (SDCP arayüzü olanlar).
- **Protokol:** UDP Port 3000 Broadcast Keşfi + WebSocket Port 3030 JSON RPC.
- **Safe-Mode:** `UPLOAD_ONLY`.

---

## 3. Taşıyıcı Seçim Mantığı

MakerSpell bir yazıcıyı bağlarken şu akışla adaptörü seçer:

1. **Kullanıcı Tanımlı Profil:** Eğer cihaz için özel bir `profile-v2` atanmışsa, profildeki `channels` ve `operations` yürütülür.
2. **Otomatik Probe Eşleşmesi:** Probe yanıtında `Creality` imzası varsa `CrealityLocalTransport`, `Moonraker` imzası varsa `MoonrakerTransport` seçilir.
3. **Kullanıcı Değişimi:** Kullanıcı arayüzdeki "Yazıcı Ayarları" (`PrinterSettingsSheet`) üzerinden istediği adaptörü manuel olarak da seçebilir.
