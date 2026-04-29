# GameHub Remote Engine — v1.0.3

**Yayın tarihi:** 25 Nisan 2026
**Kanal:** Stable
**Sürüm türü:** İyileştirme
**Yükseltme:** Otomatik

[![İndir](https://img.shields.io/badge/⬇_%C4%B0ndir-GameHubRemoteEngine--Setup.exe_(~71_MB)-22c55e?style=for-the-badge&logo=windows&logoColor=white)](https://github.com/yigitira92/GameHubRemoteEngine/releases/latest/download/GameHubRemoteEngine-Setup.exe)

---

## Otomatik güncelleme artık installer'sız

Önceki sürümlerde otomatik güncelleme akışı Inno Setup installer'ını çalıştırıyordu — `/VERYSILENT` bayrağıyla bile installer'ın kısa bir progress UI'sı görünebiliyordu. Bu sürümle birlikte tamamen yeni bir akış devreye girdi:

**Yeni akış:**
1. Uygulama açılışta GitHub'da yeni sürümü tespit eder, kullanıcıya sorar.
2. Kullanıcı onaylarsa **tek başına `GameHubRemoteEngine.exe` portable dosyası** indirilir (installer değil).
3. Küçük bir helper script eski EXE'yi yenisiyle yerinde değiştirir.
4. Uygulama otomatik olarak yeni sürümle yeniden açılır.

**Kullanıcı deneyimi:**
- ❌ Installer wizard yok
- ❌ Progress bar yok
- ❌ "Welcome / Directory / Ready" sayfaları yok
- ✅ Tek bir UAC izin penceresi (Program Files'a yazmak için zorunlu)
- ✅ Uygulama kapanır → ~3 saniye sonra yeni sürümle açılır

Discord, 1Password, Slack gibi profesyonel masaüstü uygulamalarındaki silent-update deneyimi.

**Manuel kurulum:** Setup.exe dosyasını hâlâ ayrıca paylaşıyoruz; ilk kurulum için klasik wizard'ı kullanır. Yalnızca otomatik güncelleme akışı sessize alındı.

---

## Önceki sürümler

- [v1.0.2](https://github.com/yigitira92/GameHubRemoteEngine/releases/tag/v1.0.2) — Inno /VERYSILENT bayrağı
- [v1.0.1](https://github.com/yigitira92/GameHubRemoteEngine/releases/tag/v1.0.1) — Bilgisayar açıldığında otomatik başlatma
- [v1.0.0](https://github.com/yigitira92/GameHubRemoteEngine/releases/tag/v1.0.0) — İlk genel sürüm

---

## Kurulum

**Mevcut kullanıcılar:** Uygulamanın bir sonraki açılışında otomatik güncelleme bildirimi görünür. v1.0.0/v1.0.1 → v1.0.3 geçişi eski installer akışıyla yapılır (eski sürümün update servisi yeni mantığı bilmiyor). Bu sürümden sonraki **her güncelleme installer'sız** olacak.

**Yeni kurulum:** Yukarıdaki indirme bağlantısından `GameHubRemoteEngine-Setup.exe` dosyasını çalıştırın.

**Sistem gereksinimleri:**
- Windows 10 / 11 (x64)
- .NET 8 desktop runtime (paket içindeki setup tarafından otomatik temin edilebilir)

---

**Servervia Bilişim Yazılım ve Telekomünikasyon Hizmetleri Ltd. Şti.**
[gamehubserver.com.tr](https://gamehubserver.com.tr)
