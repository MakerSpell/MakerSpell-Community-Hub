# 📐 profile-v2 Tam Şema Spesifikasyonu (Full Specification)

MakerSpell deklaratif yazıcı sürücüsü `profile-v2`, JSON Schema Draft 2020-12 standartlarına uygun olarak tasarlanmıştır. Bu doküman, profil dosyasındaki tüm anahtar ve nesnelerin ayrıntılı teknik spesifikasyonunu içerir.

---

## 📌 1. Kök Düzey Alanlar (Root Fields)

| Alan | Tip | Zorunlu? | Açıklama |
| :--- | :--- | :--- | :--- |
| **`schemaVersion`** | `integer` | **Evet** | Değeri sabit `2` olmalıdır. |
| **`id`** | `string` | **Evet** | Profilin benzersiz kimliği. Biçim: `^[a-z0-9]+(?:[._-][a-z0-9]+)+$` (Örn: `community.creality-local-v2.experimental`). |
| **`version`** | `string` | **Evet** | SemVer sürüm dizesi (Örn: `2.0.1`). |
| **`channels`** | `object` | **Evet** | Ağ haberleşme kanalları. |
| **`operations`** | `object` | **Evet** | Tanımlanan ağ işlemleri. |
| **`state`** | `object` | **Evet** | Telemetri durum eşleştirmeleri. |
| **`identity`** | `object` | Hayır | Cihaz kimliği, marka/model eşleştirmeleri. |
| **`permissions`** | `array` | Hayır | Talep edilen izinler listesi. |
| **`discovery`** | `object` | Hayır | Ağ keşif ve probe kuralları. |
| **`actions`** | `object` | Hayır | UI butonlarıyla operasyonlar arasındaki bağlar. |
| **`media`** | `object` | Hayır | Kamera ve web paneli yolları. |
| **`ui`** | `object` | Hayır | Pano yerleşimi ve bileşen düzeni. |

---

## 📌 2. `identity` Bloğu

Yazıcının marka, model ve delegasyon detaylarını tanımlar:

```json
"identity": {
  "name": "Creality Local v2 Community Verified",
  "models": ["K1", "K1 Max", "Hi", "Hi Combo"],
  "status": "communityVerified",
  "replaces": "creality_local",
  "delegateContracts": ["filamentSlotControl"],
  "defaultFilamentSlots": [
    {
      "index": 0,
      "hasFilament": true,
      "slotLabel": "External spool"
    }
  ],
  "localFileMedia": {
    "channel": "web",
    "downloadPath": "/downloads/gcode/{{fileName}}",
    "thumbnailPath": "/downloads/humbnail/{{gcodeBaseName}}.png"
  }
}
```

- **`models`:** Bu profilin otomatik eşleşeceği model isimleri.
- **`status`:** `community` (deneysel/topluluk) veya `communityVerified` (onaylanmış).
- **`delegateContracts`:** Uygulamanın yerleşik adaptörüne devredilecek özel kontratlar (örneğin CFS yuva yönetimi).
- **`localFileMedia`:** Cihazın yerel dosya sistemindeki G-code ve küçük resim (thumbnail) indirme şablonu.

---

## 📌 3. `permissions` Dizisi

Uygulamanın bu profile tanıyacağı yetkileri kısıtlar. İzin verilmeyen işlemler çalışma zamanında engellenir:

```json
"permissions": [
  "statusRead",       // Durum ve telemetri okuma
  "fileListRead",     // Yazıcıdaki dosyaları listeleme
  "fileUpload",       // G-code yükleme
  "printStart",       // Baskı başlatma (Safe-Mode'da verilmez!)
  "printControl",     // Duraklat, devam et, iptal et
  "deviceControl",    // Sıcaklık, fan, eksen hareketleri
  "cameraRead",       // Canlı kamera görüntüsü
  "gcodeTransform"    // G-code başlığına dinamik parametre enjeksiyonu
]
```

---

## 📌 4. `discovery` Bloğu

Ağ keşfi sırasında cihazın nasıl taranacağını ve hangi probe isteğiyle doğrulanacağını tanımlar:

```json
"discovery": {
  "serviceTypes": ["_creality._tcp.local", "_cxswbox._tcp.local"],
  "ports": [80, 9999],
  "probes": [
    { "operation": "probeInfo", "weight": 3, "required": true },
    { "operation": "status", "weight": 2, "required": false }
  ]
}
```

- **`serviceTypes`:** Zeroconf / mDNS servis tipleri.
- **`ports`:** Cihazın dinlediği bilinen portlar.
- **`probes`:** Keşif anında çalıştırılacak operasyonlar. Ağırlığı (`weight`) yüksek olan ve `required: true` olan probe başarılı olursa cihaz bu profil ile eşleştirilir.

---

## 📌 5. `channels` Bloğu

Farklı protokollerde haberleşmek için açılacak soket ve HTTP kanallarını belirler:

```json
"channels": {
  "web": {
    "kind": "http",
    "scheme": "http",
    "port": 80,
    "timeoutMs": 3000,
    "maxResponseBytes": 1048576
  },
  "control": {
    "kind": "websocket",
    "scheme": "ws",
    "port": 9999,
    "path": "/",
    "timeoutMs": 5000,
    "maxResponseBytes": 8388608,
    "lifecycle": "perOperation"
  }
}
```

- **`kind`:** `http`, `websocket`, `mqtt` veya `udp`.
- **`lifecycle`:** WebSocket kanalları için `persistent` (sürekli açık) veya `perOperation` (istek atıldığında bağlanıp yanıt sonrası kapatılan).

---

## 📌 6. `operations` Bloğu

Yazıcıya gönderilecek istekleri ve beklenen yanıtları tanımlar:

### HTTP Örneği:
```json
"probeInfo": {
  "channel": "web",
  "method": "GET",
  "path": "/info",
  "map": "identity"
}
```

### WebSocket JSON-RPC / Raw Mesaj Örneği:
```json
"status": {
  "channel": "control",
  "send": {
    "json": { "method": "get", "params": { "reqGcodeFile": 1 } }
  },
  "receive": {
    "mode": "matching",
    "until": { "pathExists": "$.deviceState" },
    "maxMessages": 20
  },
  "map": "status"
}
```

### Dosya Yükleme (Upload) Örneği:
```json
"uploadFile": {
  "channel": "web",
  "method": "POST",
  "path": "/upload",
  "contentType": "multipart/form-data",
  "body": {
    "fileField": "file",
    "fileName": "{{fileName}}",
    "extraFields": { "print": "{{autoStart}}" }
  }
}
```

---

## 📌 7. `state` Bloğu (Telemetri Eşleştirme)

Yazıcının kendine özgü JSON çıktısını MakerSpell'in ortak telemetri modeline dönüştürür (JSONPath desteği ile):

```json
"state": {
  "printer": {
    "state": "$.deviceState",
    "isPrinting": { "path": "$.deviceState", "equals": "printing" },
    "isPaused": { "path": "$.deviceState", "equals": "paused" }
  },
  "temperature": {
    "hotendActual": "$.nozzleTemp",
    "hotendTarget": "$.nozzleTargetTemp",
    "bedActual": "$.bedTemp",
    "bedTarget": "$.bedTargetTemp"
  },
  "job": {
    "fileName": "$.curGcodeFile",
    "progress": { "path": "$.printProgress", "scale": 0.01 },
    "timeRemainingSeconds": "$.remainingTime"
  }
}
```

---

## 📌 8. `ui` Bloğu (Masaüstü & Mobil Yerleşim)

Yazıcı denetim sayfasında bileşenlerin hangi kolonda ve hangi sırada gösterileceğini deklaratif olarak belirler:

```json
"ui": {
  "pages": {
    "control": {
      "layout": "dashboard",
      "dashboard": {
        "version": 1,
        "columns": [
          {
            "span": 3,
            "sections": ["status", "camera", "job", "filaments"]
          },
          {
            "span": 2,
            "sections": ["device-controls", "motion", "files"]
          }
        ]
      }
    }
  }
}
```
- Masaüstünde 1100 piksel ve üzeri genişlikte 2 kolonlu pano (span 3 + span 2) kullanılır.
- Mobilde ve dar pencerelerde otomatik olarak tek kolon dikey listeye dönüşür.
