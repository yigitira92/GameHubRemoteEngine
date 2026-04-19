# GameHub Remote Engine

Gamehubserver.com.tr operasyon ekibi için [Servervia Bilişim Yazılım ve Telekomünikasyon Hizmetleri Ltd. Şti.](https://gamehubserver.com.tr) tarafından geliştirilen kurumsal uzak masaüstü (RDP) yönetim uygulaması.

Bu depo yalnızca resmi sürümlerin dağıtımı ve otomatik güncelleme akışı için kullanılmaktadır. Kaynak kodu kapalıdır.

**[En son sürümü indir →](https://github.com/yigitira92/GameHubRemoteEngine/releases/latest/download/GameHubRemoteEngine-Setup.exe)**

---

## Uygulama hakkında

GameHub Remote Engine, çok sayıda Windows sunucusunu tek bir arayüzden yönetmek üzere tasarlanmış bir uzak masaüstü istemcisidir. Windows'un yerleşik `mstsc.exe` aracı ile RDCMan'ın işlevsel eksikliklerini kapatmak amacıyla, operasyon personelinin günlük iş akışına odaklanarak geliştirilmiştir.

Uygulamanın temel yetenekleri:

- Sunucu envanteri, favori yönetimi ve alan tabanlı arama.
- Bağlantı kopmalarında akıllı yeniden bağlanma; hatalı kimlik veya erişilemeyen makinelerde sonsuz döngüye girmeyen koruma mantığı.
- Windows Data Protection API (DPAPI) üzerinden, oturumu açan Windows hesabına özel, şifreli yerel kimlik bilgisi saklama.
- Açık ve koyu tema, Türkçe ve İngilizce dil desteği; kurulum sihirbazında ilk tercih alınır, çalışma sırasında Ayarlar üzerinden değiştirilebilir.
- GitHub Releases üzerinden yayınlanan sürümlerin açılışta denetlenip indirilip uygulanması.
- Oturum başına anlık bant genişliği ölçümü; durum çubuğunda olay günlüğü ve bildirim sayacı.

## Sistem gereksinimleri

| Bileşen | Gereksinim |
|---|---|
| İşletim sistemi | Windows 10 sürüm 1809 (build 17763) veya üzeri; Windows 11 önerilir |
| Mimari | x64 (ARM64 desteklenmemektedir) |
| Disk alanı | Yaklaşık 100 MB |
| .NET çalışma zamanı | Dahili — ayrı kurulum gerektirmez |
| Ayrıcalık | Kurulum sırasında Yönetici onayı (Program Files dizinine yazma) |

## Kurulum

1. Yukarıdaki indirme bağlantısından `GameHubRemoteEngine-Setup.exe` dosyasını indirin.
2. Dosyayı çalıştırın. Uygulama kod imzalı olmadığından Windows SmartScreen uyarısı görüntülenebilir; **Daha fazla bilgi → Yine de çalıştır** seçeneği ile devam edin.
3. Kullanıcı Hesabı Denetimi (UAC) onayı verin. Uygulama `C:\Program Files\GameHub Remote Engine\` dizinine kurulacaktır.
4. Sihirbaz sırasında tema (Light/Dark) ve dil (English/Türkçe) tercihlerinizi belirtin. Bu tercihler yalnızca ilk kurulumda sorulur; sonraki güncellemelerde korunur.
5. Kurulum tamamlandığında uygulama seçilen tema ve dille açılır.

### İlk bağlantının eklenmesi

1. Sol kenardaki sunucu listesinin üstündeki **+** düğmesine tıklayın (veya `Ctrl+N`).
2. IP adresi, görünen ad, kullanıcı adı ve şifre alanlarını doldurun. Port verilmediği takdirde 3389 varsayılır; `host:port` biçimi de geçerlidir.
3. Kaydedin. Sunucu listede belirir; çift tıklama veya Enter ile bağlantı başlar.

### Kaldırma

Denetim Masası → Uygulamalar → *GameHub Remote Engine* → *Kaldır* adımlarından kaldırılır. Kaldırma işleminin sonunda uygulama, kayıtlı sunucuların, şifrelerin ve ayarların (`%LocalAppData%\GameHubRemoteEngine\`) da silinip silinmeyeceğini sorar. Seçim kullanıcıya bırakılmıştır.

## Güvenlik ve gizlilik

Tüm kullanıcı verisi yerel olarak, kullanıcıya özel dizinde tutulur:

```
%LocalAppData%\GameHubRemoteEngine\
├── data\      (sunucu listesi, ayarlar)
├── logs\     (uygulama günlükleri; kimlik bilgisi içermez)
└── secrets\ (DPAPI ile şifrelenmiş parola blobları)
```

Parolalar Windows DPAPI kullanılarak, oturumu açan Windows hesabına bağlı anahtarla şifrelenir. Şifrelenmiş dosyalar başka bir kullanıcı veya başka bir makine tarafından çözülemez.

Uygulama aşağıdaki dış bağlantı dışında hiçbir ağ trafiği üretmez:

- Güncelleme denetimi için açılışta yapılan tek istek: `GET https://api.github.com/repos/yigitira92/GameHubRemoteEngine/releases/latest`

Telemetri, kullanım istatistiği veya anonim veri toplama yoktur. RDP trafiği, GameHub Remote Engine ile sunucu arasında doğrudan akar; herhangi bir aracı hizmet üzerinden geçmez.

## Otomatik güncelleme

Uygulama her açılışta GitHub Releases üzerinden en güncel sürüm numarasını sorgular. Yüklü sürümden daha yeni bir sürüm yayımlanmışsa bir iletişim penceresi kullanıcıya sunulur. Kullanıcı onay verirse kurulum dosyası arka planda indirilir, tamamlandığında uygulamanın yeniden başlatılarak kurulumun uygulanması önerilir. Güncelleme sırasında kullanıcı ayarları, sunucu listesi ve kayıtlı kimlik bilgileri korunur.

Güncelleme kontrolü yalnızca açılışta yapılır; çalışma sırasında arka planda ek sorgu gönderilmez.

## Destek

Hata bildirimi, öneri ve özellik talepleri için bu deponun [Issues](https://github.com/yigitira92/GameHubRemoteEngine/issues) bölümü kullanılabilir.

---

© 2026 Servervia Bilişim Yazılım ve Telekomünikasyon Hizmetleri Ltd. Şti.  
[gamehubserver.com.tr](https://gamehubserver.com.tr)
