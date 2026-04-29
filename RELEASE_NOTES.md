# GameHub Remote Engine — v1.0.4

**Yayın tarihi:** 25 Nisan 2026
**Kanal:** Stable
**Sürüm türü:** Acil düzeltme (hotfix)

[![İndir](https://img.shields.io/badge/⬇_%C4%B0ndir-GameHubRemoteEngine--Setup.exe_(~71_MB)-22c55e?style=for-the-badge&logo=windows&logoColor=white)](https://github.com/yigitira92/GameHubRemoteEngine/releases/latest/download/GameHubRemoteEngine-Setup.exe)

---

## Düzeltme: Otomatik güncelleme "başarılı görünüp aslında olmuyordu"

Önceki sürümlerde (v1.0.0 / v1.0.1 / v1.0.2 / v1.0.3) otomatik güncelleme akışında bir yarış koşulu (race condition) vardı:

1. App, installer'ı `/VERYSILENT` modunda çalıştırırdı
2. App eş zamanlı olarak `Application.Shutdown()` çağırırdı
3. Installer, app henüz tam kapanmadan dosyayı kopyalamaya çalışırdı
4. **Dosya kilidi açık olmadığı için kopyalama başarısız olurdu**
5. `/SUPPRESSMSGBOXES` hatayı bastırırdı
6. Setup "Successful" döndürürdü → kullanıcıya "başarılı" mesajı gösterilirdi
7. App eski versiyonla yeniden açılırdı

Sonuç: kullanıcı güncellediğini düşünürdü ama dosyalar gerçekten değişmemişti.

### v1.0.4 ile

Installer artık **kendisi self-healing**:

- Kurulum başlamadan önce çalışan tüm `GameHubRemoteEngine.exe` instance'larını **zorla kapatır** (`taskkill /F`)
- **Dosya kilidi serbest kalana kadar bekler** (3 saniyeye kadar polling)
- Sonra dosya kopyalamaya başlar — race condition imkânsız
- Hala kilit kalırsa Inno'nun `restartreplace` bayrağı dosyayı **bir sonraki reboot'ta** otomatik değiştirir (Windows kuyruğu)

### Eski sürümlerden gelen güncellemeler

| Şu anda yüklü | → v1.0.4 davranışı |
|---------------|---------------------|
| v1.0.0 / v1.0.1 / v1.0.2 / v1.0.3 | ✅ **Bu sürüm gerçekten yüklenir** (eski race condition fix'lendi) |
| v1.0.4 → sonraki sürümler | ✅ Tamamen sessiz, helper-batch ile (v1.0.3'te eklenen) |

---

## Önceki sürümler

- [v1.0.3](https://github.com/yigitira92/GameHubRemoteEngine/releases/tag/v1.0.3) — Inno installer'sız sessiz güncelleme akışı
- [v1.0.2](https://github.com/yigitira92/GameHubRemoteEngine/releases/tag/v1.0.2) — Inno /VERYSILENT bayrağı
- [v1.0.1](https://github.com/yigitira92/GameHubRemoteEngine/releases/tag/v1.0.1) — Otomatik başlatma
- [v1.0.0](https://github.com/yigitira92/GameHubRemoteEngine/releases/tag/v1.0.0) — İlk genel sürüm

---

## Kurulum

**Mevcut kullanıcılar:** Uygulamanın bir sonraki açılışında otomatik güncelleme bildirimi görünür. Bu sefer **gerçekten yüklenecek**.

**Yeni kurulum:** Yukarıdaki indirme bağlantısından `GameHubRemoteEngine-Setup.exe` dosyasını çalıştırın.

**Sistem gereksinimleri:**
- Windows 10 / 11 (x64)
- .NET 8 desktop runtime (paket içindeki setup tarafından otomatik temin edilebilir)

---

**Servervia Bilişim Yazılım ve Telekomünikasyon Hizmetleri Ltd. Şti.**
[gamehubserver.com.tr](https://gamehubserver.com.tr)
