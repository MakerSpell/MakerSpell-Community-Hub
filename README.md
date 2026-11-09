# 🌐 MakerSpell Community Hub & Kullanıcı Kılavuzları

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![MakerSpell](https://img.shields.io/badge/MakerSpell-Ecosystem-indigo.svg)](https://www.makerspell.com)
[![Status: Active](https://img.shields.io/badge/Status-Live%20Hub-emerald.svg)](https://github.com/MakerSpell/MakerSpell-Community-Hub)

Welcome to the **MakerSpell Community Hub** — the official, open-source repository for community-driven 3D printer profiles, user guides for desktop/mobile and web platforms, and ecosystem documentation.

> **One platform, every 3D model, direct to your printer.**  
> MakerSpell connects 26 model repositories, cloud & local slicing engines, and multi-brand 3D printers into a unified workspace.

---

## 📚 Dokümantasyon ve Kullanım Rehberleri Ağacı

Tüm dokümanlar, Web sitesi ve Flutter masaüstü/mobil uygulaması içerisindeki "Dokümantasyon Görüntüleyici" tarafından dinamik olarak okunup kullanıcıya sunulacak şekilde yapılandırılmıştır.

Dokümantasyon indeks ve hiyerarşisi [`docs/manifest.json`](docs/manifest.json) dosyası üzerinden yönetilir.

```text
community-hub/
├── docs/
│   ├── manifest.json                  # Multilingual Navigation Index (en / tr)
│   ├── assets/                        # Shared Screenshots & Architecture Graphics
│   │   └── screenshots/               # app/ and web/ screenshots
│   ├── en/                            # English Documentation (Default & Global)
│   │   ├── app-guide/                 # Desktop & Mobile App User Guides (12 docs)
│   │   ├── web-guide/                 # Web Platform User Guides (7 docs)
│   │   ├── printers/                  # 3D Printer Connectivity & Protocols (5 docs)
│   │   ├── schemas/                   # Declarative JSON Driver Schema v2 (2 docs)
│   │   └── guides/                    # Developer, Contributor & Governance Guides (3 docs)
│   ├── tr/                            # Türkçe Dokümantasyon (Yerel Kılavuzlar)
│   │   ├── app-guide/                 # Masaüstü & Mobil Uygulama Kullanım Kılavuzları (12 doküman)
│   │   ├── web-guide/                 # Web Platformu Kullanım Kılavuzları (7 doküman)
│   │   ├── printers/                  # 3D Yazıcı Entegrasyonu & Bağlantı Arayüzleri (5 doküman)
│   │   ├── schemas/                   # Açık Topluluk JSON Sürücü Şeması v2 (2 doküman)
│   │   └── guides/                    # Geliştirici & Topluluk Rehberleri (3 doküman)
│   └── examples/                      # Example Printer Driver Profiles (Creality K1, Snapmaker U1)
```

---

## 🖨️ Desteklenen Donanım Uyumluluk Matrisi (Hardware Matrix)

| Donanım / Protokol | Durum | Kontrol Modu | Telemetri | Bellenim Gereksinimi |
| :--- | :--- | :--- | :--- | :--- |
| **Creality K1 / K1 Max / K1C** | 🟢 **Verified** | Tam İki Yönlü | Canlı Sıcaklık, Hazne, LiDAR, Kamera | CrealityOS / Moonraker |
| **Creality Ender-3 V3 (CoreXZ)** | 🟢 **Verified** | Tam İki Yönlü | Canlı Durum, Aşama Takibi | CrealityOS / Moonraker |
| **Creality Hi / Hi Combo** | 🟢 **Verified** | Tam İki Yönlü | 4-Renk CFS Telemetrisi, Kamera | CrealityOS v2 |
| **Snapmaker U1 / Artisan** | 🟢 **Verified** | Tam İki Yönlü | Takım Değiştirme Telemetrisi, MQTT | Snapmaker Extended FW |
| **Moonraker / Klipper Ekosistemi** | 🟢 **Verified** | Tam İki Yönlü | Tam WebSocket / REST Telemetrisi | Klipper / Moonraker |
| **OctoPrint v1 / v2 Ekosistemi** | 🟢 **Verified** | Tam İki Yönlü | MJPEG Webcam, REST API | OctoPrint 1.8+ |
| **Prusa MK4 / XL / MINI** | 🟡 **Community** | Safe-Mode Print | PrusaLink REST / Digest Auth | Firmware 5.0+ |
| **Bambu Lab (P1, X1, A1 Serisi)** | 🟡 **Community** | **Upload-Only (Safe-Mode)** | Yerel MQTT Broker (Bulutsuz) | Yerel Mod (`auto_start=false`) |
| **Elegoo / Anycubic / Voron** | 🟡 **Community** | **Upload-Only (Safe-Mode)** | Keşif & Hazırlık | Standart Firmware |

> [!IMPORTANT]
> **Topluluk Donanım Güvenlik Kuralı:** Doğrulanmamış veya topluluk tarafından eklenen tüm yazıcı profilleri katı bir biçimde **Safe-Mode (`UPLOAD_ONLY`)** kuralına tabidir. Dilimlenen dosyalar yazıcı hafızasına aktarılır; ancak ısıtma ve baskı başlatma fiziksel olarak cihaz başındaki operatör tarafından yapılmalıdır.

---

## 🤝 Katkıda Bulunma & Yeni Yazıcı Ekleme

Topluluk tarafından test edilmiş yeni yazıcı profillerini memnuniyetle karşılıyoruz!
Ayrıntılı adımlar için [Yeni Yazıcı Ekleme Kılavuzunu](docs/guides/adding-new-printer.md) inceleyebilirsiniz.

---

## 🔗 Resmi Ekosistem Bağlantıları

- **Web Platformu:** [makerspell.com](https://www.makerspell.com)
- **Topluluk Yazıcıları:** [makerspell.com/community-printers](https://www.makerspell.com/community-printers)
- **3D İndirimler & Kuponlar:** [makerspell.com/deals](https://www.makerspell.com/deals)
- **Fiyatlandırma & Üyelik:** [makerspell.com/pricing](https://www.makerspell.com/pricing)
- **Discord Topluluğu & Destek:** [makerspell.com/contact](https://www.makerspell.com/contact)

---

## ⚖️ Lisans

Bu proje **MIT Lisansı** ile dağıtılmaktadır. Detaylar için `LICENSE` dosyasına bakınız.
