# GameHub Remote Engine — v1.0.1

**Yayın tarihi:** 25 Nisan 2026
**Kanal:** Stable
**Sürüm türü:** Özellik güncellemesi
**Yükseltme:** Otomatik (mevcut v1.0.0 kurulumları açılışta yeni sürümü tespit eder)

Bilgisayar açılışında otomatik başlatma + otomatik yeniden bağlanma özelliği eklendi. Seçenekler ekranı bağlantı ayarları için ayrı bir sekmeye taşındı.

[![İndir](https://img.shields.io/badge/⬇_%C4%B0ndir-GameHubRemoteEngine--Setup.exe_(~71_MB)-22c55e?style=for-the-badge&logo=windows&logoColor=white)](https://github.com/yigitira92/GameHubRemoteEngine/releases/latest/download/GameHubRemoteEngine-Setup.exe)

---

## Yeni Özellikler

### Bilgisayar açıldığında otomatik başlatma + son oturumlara bağlanma

Seçenekler → **Bağlantı Ayarları** altında yeni bir kutucuk: **"Bilgisayar açıldığında otomatik başlat ve son oturumlara bağlan"**.

- Etkinleştirildiğinde Windows oturum açıldığında uygulama otomatik başlar.
- Önceki oturumda bağlı olduğunuz sunuculara onay sormadan tekrar bağlanır.
- Uygulama pencerelenmiş olarak gelir; tepside gizlenmez — Windows açılışında bağlanan sunucularınızı anında görürsünüz.
- Varsayılan olarak kapalı — kullanıcının açıkça etkinleştirmesi gerekir.

Teknik olarak `HKCU\Software\Microsoft\Windows\CurrentVersion\Run` altına EXE yolu yazılır; UAC izni gerektirmez. Uygulama kaldırıldığında kayıt otomatik temizlenir.

### Bağlantı Ayarları sekmesi

Seçenekler ekranındaki bağlantı davranışıyla ilgili tüm seçenekler tek bir sekmeye toplandı:

- Başlangıçta bağlı sunucuları yeniden bağlamak için sor
- Pencere kapatıldığında sistem tepsisine indir
- Bilgisayar açıldığında otomatik başlat ve son oturumlara bağlan
- Bağlantı koptuğunda otomatik yeniden bağlan + tekrar deneme aralığı
- Ağ Düzeyi Kimlik Doğrulaması (NLA) kullan

**Genel** sekmesi artık yalnızca dil + tema + UI tercihlerini içeriyor — daha temiz, daha hızlı bulunabilir.

---

## Önceki sürüm

[v1.0.0 sürüm notları](https://github.com/yigitira92/GameHubRemoteEngine/releases/tag/v1.0.0) — ilk genel sürüm.

---

## Kurulum

**v1.0.0 kullanıcıları:** Uygulamayı bir sonraki açılışınızda otomatik güncelleme diyaloğu görünür; "Güncelle" tuşuna basın, gerisini sihirbaz halleder. Ayarlarınız ve oturum bilgileriniz korunur.

**Yeni kurulum:** Yukarıdaki indirme bağlantısından `GameHubRemoteEngine-Setup.exe` dosyasını çalıştırın.

**Sistem gereksinimleri:**
- Windows 10 / 11 (x64)
- .NET 8 desktop runtime (paket içindeki setup tarafından otomatik temin edilebilir)

---

**Servervia Bilişim Yazılım ve Telekomünikasyon Hizmetleri Ltd. Şti.**
[gamehubserver.com.tr](https://gamehubserver.com.tr)
