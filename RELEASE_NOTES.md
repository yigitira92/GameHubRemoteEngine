# GameHub Remote Engine — v1.0.2

**Yayın tarihi:** 25 Nisan 2026
**Kanal:** Stable
**Sürüm türü:** İyileştirme
**Yükseltme:** Otomatik

[![İndir](https://img.shields.io/badge/⬇_%C4%B0ndir-GameHubRemoteEngine--Setup.exe_(~71_MB)-22c55e?style=for-the-badge&logo=windows&logoColor=white)](https://github.com/yigitira92/GameHubRemoteEngine/releases/latest/download/GameHubRemoteEngine-Setup.exe)

---

## Otomatik güncelleme artık sessiz

Önceki sürümlerde otomatik güncelleme tetiklendiğinde Inno Setup wizard'ı 4–5 sayfalık bir akışla açılıyordu (Welcome / Directory / Ready / Installing / Finished). Aslında dosyalar yerinde değiştiriliyordu (fresh install değil, kullanıcı verisi korunuyordu) ama UI gürültüsü yüzünden "baştan kuruluyor" hissi veriyordu.

**Bu sürümle birlikte:**
- Wizard sayfaları **hiç açılmaz**.
- Uygulama otomatik kapanır → dosyalar yenilenir → uygulama yeni sürümde otomatik yeniden açılır.
- Discord, 1Password, Slack gibi profesyonel masaüstü uygulamalarındaki silent-update deneyimi.
- Kullanıcı sadece "kapandı, 2-3 saniye sonra yeni sürüm açıldı" gözlemler.

**Önceki davranışın korunduğu durum:** Setup'ı manuel olarak çift tıklayıp çalıştırırsan klasik Inno Setup wizard'ı açılır — manuel kurulumda kullanıcı her adımı görmek isteyebilir, bu yüzden sadece otomatik güncelleme akışı sessize alındı.

---

## Önceki sürümler

- [v1.0.1](https://github.com/yigitira92/GameHubRemoteEngine/releases/tag/v1.0.1) — Bilgisayar açıldığında otomatik başlatma + Bağlantı Ayarları sekmesi
- [v1.0.0](https://github.com/yigitira92/GameHubRemoteEngine/releases/tag/v1.0.0) — İlk genel sürüm

---

## Kurulum

**Mevcut kullanıcılar:** Uygulamanın bir sonraki açılışında otomatik güncelleme bildirimi görünür. Bu sürüme yükseltirken yine wizard pages görürsünüz (eski sürümün update servisi bu silent flag'i bilmiyordu) — ama **bu sürümden sonraki tüm güncellemeler sessiz olacak**.

**Yeni kurulum:** Yukarıdaki indirme bağlantısından `GameHubRemoteEngine-Setup.exe` dosyasını çalıştırın.

**Sistem gereksinimleri:**
- Windows 10 / 11 (x64)
- .NET 8 desktop runtime (paket içindeki setup tarafından otomatik temin edilebilir)

---

**Servervia Bilişim Yazılım ve Telekomünikasyon Hizmetleri Ltd. Şti.**
[gamehubserver.com.tr](https://gamehubserver.com.tr)
