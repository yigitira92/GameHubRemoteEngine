# GameHub Remote Engine — v1.0.5

**Yayın tarihi:** 25 Nisan 2026
**Kanal:** Stable
**Sürüm türü:** Acil düzeltme (hotfix)

[![İndir](https://img.shields.io/badge/⬇_%C4%B0ndir-GameHubRemoteEngine--Setup.exe_(~71_MB)-22c55e?style=for-the-badge&logo=windows&logoColor=white)](https://github.com/yigitira92/GameHubRemoteEngine/releases/latest/download/GameHubRemoteEngine-Setup.exe)

---

## Düzeltme: Sonsuz "Güncelleme var" diyaloğu

v1.0.4'te ve önceki bazı sürümlerde, app açıldığında "Yeni sürüm var" diyaloğu **kendi sürümüne kendi sürümünü öneriyordu**:

```
Current version: 1.0.4+7e80fa1b92240c93f
New version:     1.0.4
```

**Neden:** .NET SDK'sı, build sırasında `InformationalVersion`'a otomatik olarak `+commit-hash` ekler (SourceLink özelliği). UpdateService'in version comparison fonksiyonu bu suffix'i tanımıyor, `int.Parse("4+7e80fa1...")` başarısız oluyor ve current sürümü `1.0.0` olarak okuyordu. Sonuç: latest tag `1.0.4` her zaman "newer" görünüyor → diyalog her açılışta beliriyor.

### v1.0.5 ile

- **Runtime fix:** `CurrentVersion` getter'ı suffix'i artık kırpıyor (`1.0.4+abc123` → `1.0.4`).
- **Defensive fix:** `IsNewer` Parse fonksiyonu da suffix temizliyor — her iki tarafta da güvenli.
- **Compile-time fix:** csproj'a `IncludeSourceRevisionInInformationalVersion=false` eklendi → suffix hiç oluşmuyor.

Üç kat koruma. Bundan sonra **kendi sürümünü kendine update teklif etmez**.

---

## Önceki sürümler

- [v1.0.4](https://github.com/yigitira92/GameHubRemoteEngine/releases/tag/v1.0.4) — Otomatik güncelleme race-condition hotfix
- [v1.0.3](https://github.com/yigitira92/GameHubRemoteEngine/releases/tag/v1.0.3) — Inno installer'sız sessiz güncelleme akışı
- [v1.0.2](https://github.com/yigitira92/GameHubRemoteEngine/releases/tag/v1.0.2) — Inno /VERYSILENT bayrağı
- [v1.0.1](https://github.com/yigitira92/GameHubRemoteEngine/releases/tag/v1.0.1) — Otomatik başlatma
- [v1.0.0](https://github.com/yigitira92/GameHubRemoteEngine/releases/tag/v1.0.0) — İlk genel sürüm

---

## Kurulum

**Mevcut kullanıcılar:** Uygulamanın bir sonraki açılışında otomatik güncelleme bildirimi görünür. v1.0.4'ten v1.0.5'e geçtikten sonra spurious "update available" diyaloğu artık görünmez.

**Yeni kurulum:** Yukarıdaki indirme bağlantısından `GameHubRemoteEngine-Setup.exe` dosyasını çalıştırın.

**Sistem gereksinimleri:**
- Windows 10 / 11 (x64)
- .NET 8 desktop runtime (paket içindeki setup tarafından otomatik temin edilebilir)

---

**Servervia Bilişim Yazılım ve Telekomünikasyon Hizmetleri Ltd. Şti.**
[gamehubserver.com.tr](https://gamehubserver.com.tr)
