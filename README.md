<div align="center">

<img src="assets/logo.png" alt="GameHub Remote Engine" width="180" />

# GameHub Remote Engine

**Kurumsal Uzak Masaüstü (RDP) Yönetim İstemcisi**

[![Son Sürüm](https://img.shields.io/github/v/release/yigitira92/GameHubRemoteEngine?label=s%C3%BCr%C3%BCm&color=0a66c2)](https://github.com/yigitira92/GameHubRemoteEngine/releases/latest)
[![Platform](https://img.shields.io/badge/platform-Windows%2010%20%7C%2011-0a66c2)](#sistem-gereksinimleri)
[![Mimari](https://img.shields.io/badge/mimari-x64-0a66c2)](#sistem-gereksinimleri)

**[⬇ En son sürümü indir](https://github.com/yigitira92/GameHubRemoteEngine/releases/latest/download/GameHubRemoteEngine-Setup.exe)**

</div>

---

## Genel bakış

GameHub Remote Engine, [Servervia Bilişim Yazılım ve Telekomünikasyon Hizmetleri Ltd. Şti.](https://gamehubserver.com.tr) tarafından Gamehubserver.com.tr operasyon ekibi için geliştirilmiş, çok sayıda Windows sunucusunu tek bir arayüzden yönetmeye olanak tanıyan kurumsal uzak masaüstü istemcisidir.

Uygulama; günlük operasyon akışında sık kullanılan sunuculara hızlı erişim, güvenli kimlik bilgisi saklama ve ekip genelinde tutarlı bir kullanıcı deneyimi sağlamak amacıyla tasarlanmıştır. Bu depo, uygulamanın resmi sürüm dağıtımı ve otomatik güncelleme akışı için kullanılmaktadır.

## Öne çıkan özellikler

GameHub Remote Engine, Windows'un standart Uzak Masaüstü istemcisinde (mstsc) bulunmayan veya sınırlı biçimde sunulan çok sayıda operasyonel özelliği tek bir arayüzde toplar.

### Çoklu oturum ve sekme yönetimi

- Birden fazla sunucuya aynı anda, tek pencere içinde sekmeli olarak bağlanma
- Sekmeler arasında klavye kısayollarıyla hızlı geçiş
- Her sekme için bağımsız oturum durumu, bant genişliği ve olay akışı
- Aktif sekmeyi ayrı bir pencerede ya da tam ekranda sürdürme

### Merkezi sunucu kütüphanesi

- Sınırsız sunucu kaydı; her kayıt için görünen ad, etiket ve açıklama alanı
- Anlık arama ve favori filtreleme
- Sunucu çoğaltma ile benzer yapılandırmaları tek tıkla türetme
- Bağlam menüsünden ana bilgisayar adını veya sunucu adını panoya kopyalama
- Gerektiğinde sunucuyu Windows'un kendi RDP istemcisinde açma seçeneği
- Varsayılan 3389 portu otomatik uygulanır; standart dışı portlar için `sunucu:port` biçimi desteklenir

### Gelişmiş kimlik bilgisi yönetimi

- Sunucu başına kullanıcı adı ve parola saklama; Windows Kimlik Bilgileri Yöneticisi'nden bağımsız
- Yeniden kullanılabilir kimlik bilgisi profilleri ile ortak hesapların tek noktadan yönetilmesi
- Parolalar yalnızca şifrelenmiş biçimde diske yazılır ve bellekte tutulan kasa sayesinde her bağlantıda yeniden sorulmaz
- Düzenleme iletişim kutusunda parola alanı güvenli biçimde önceden doldurulur; yanlışlıkla silme riski yoktur
- Operasyon ekibi için parolayı ekrana getirerek manuel paylaşmaya gerek kalmadan görme yardımcısı

### Akıllı bağlantı kurtarma

- Bağlantı kesildiğinde yapılandırılabilir aralıklarla otomatik yeniden bağlanma
- Uygulama kapatıldığında açık olan oturumların kaydedilmesi ve yeniden açılışta onayla geri yüklenmesi
- Sunucu erişilemez durumdayken kullanıcıya net geri bildirim
- Oturum durumu sürekli izlenir; gerçek zamanlı bağlantı ve veri akışı göstergesi sunulur

### Profil ve yapılandırma esnekliği

- Global varsayılan ayarlar, profil katmanı ve sunucu bazında üzerine yazma zinciri
- Ekran çözünürlüğü, renk derinliği, ses ve aygıt yönlendirme ayarları merkezi olarak belirlenebilir
- Tek bir sunucu için yapılan değişiklik diğer kayıtları etkilemez

### Modern arayüz ve erişilebilirlik

- Koyu ve açık tema; kurulum sırasında ilk tercih belirlenebilir ve uygulama içinde istenildiği zaman değiştirilebilir
- Türkçe ve İngilizce dil desteği; arayüzün tamamı yerelleştirilmiştir
- Bildirim alanına (system tray) küçültme ve pencereyi kapatma davranışının yapılandırılması
- Entegre olay günlüğü görüntüleyicisi; bağlantı, hata ve güncelleme olayları kronolojik olarak görüntülenir
- Kullanıcı tanımlı klavye kısayolları (önceki / sonraki sekme ve diğer eylemler)
- Yüksek DPI ve çoklu monitör desteği

### Güvenlik ve gizlilik

- Kimlik bilgileri yalnızca oturumu açan Windows hesabı tarafından çözülebilecek biçimde yerel olarak şifrelenir
- Parolalar, uygulama ve bellek dışında düz metin olarak hiçbir yere yazılmaz
- Uygulama herhangi bir telemetri, kullanım veya analitik verisi toplamaz
- Harici bir hesap, bulut servisi veya lisans sunucusu ile iletişim kurulmaz

### Bakım ve otomatik güncelleme

- Her açılışta sessiz sürüm kontrolü
- Yeni sürüm bulunduğunda kullanıcıya modern bir iletişim kutusu ile bildirim
- Onay üzerine güncelleme paketinin arka planda indirilmesi ve kurulumu
- Kişisel ayarlar, kayıtlı sunucular ve kimlik bilgileri güncellemelerden etkilenmez

## Sistem gereksinimleri

| Bileşen | Gereksinim |
|---|---|
| İşletim sistemi | Windows 10 sürüm 1809 veya üzeri (Windows 11 önerilir) |
| Mimari | x64 |
| Disk alanı | Yaklaşık 100 MB |
| Yetki | Kurulum sırasında Yönetici onayı |

## Kurulum

1. Yukarıdaki bağlantıdan kurulum dosyasını indirin.
2. Dosyayı çalıştırın. SmartScreen uyarısı görüntülenirse **Daha fazla bilgi → Yine de çalıştır** ile devam edin.
3. Kurulum sihirbazında kurulum dizinini, tema ve dil tercihinizi seçin.
4. Kurulum tamamlandığında uygulama seçilen ayarlarla açılır.

## Güncellemeler

Uygulama her açılışta sessizce sürüm kontrolü yapar. Yeni sürüm mevcut olduğunda kullanıcıya bildirilir; onay verildiğinde güncelleme paketi indirilir ve kurulumu başlatılır. Kişisel ayarlar, kayıtlı sunucular ve kimlik bilgileri güncelleme sürecinden etkilenmez.

## Kaldırma

Denetim Masası → Uygulamalar → *GameHub Remote Engine* → *Kaldır*

## Destek

Hata bildirimi ve öneri için [Issues](https://github.com/yigitira92/GameHubRemoteEngine/issues) bölümünü kullanabilirsiniz.

---

<div align="center">

© 2026 **Servervia Bilişim Yazılım ve Telekomünikasyon Hizmetleri Ltd. Şti.**

[gamehubserver.com.tr](https://gamehubserver.com.tr)

</div>
