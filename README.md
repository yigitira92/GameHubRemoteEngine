<div align="center">

<img src="assets/logo.png" alt="GameHub Remote Engine" width="140" />

# GameHub Remote Engine

### Oyuncular için Windows Uzak Masaüstü İstemcisi

Knight Online, MMO ve oyun sunucularınızı tek bir modern arayüzden güvenle yönetin.
Birden fazla VDS'iniz mi var? Hepsini aynı pencerede tutun, tek tıkla bağlanın, oturumları yan yana izleyin.

[![Sürüm](https://img.shields.io/github/v/release/yigitira92/GameHubRemoteEngine?label=s%C3%BCr%C3%BCm&color=2563eb&style=for-the-badge)](https://github.com/yigitira92/GameHubRemoteEngine/releases/latest)
[![Platform](https://img.shields.io/badge/platform-Windows%2010%20%2F%2011%20x64-0078d4?style=for-the-badge)](https://github.com/yigitira92/GameHubRemoteEngine/releases/latest)
[![Lisans](https://img.shields.io/badge/lisans-Tescilli-555?style=for-the-badge)](#lisans)

[![İndir](https://img.shields.io/badge/⬇_%C4%B0ndir-GameHubRemoteEngine--Setup.exe_(~71_MB)-22c55e?style=for-the-badge&logo=windows&logoColor=white)](https://github.com/yigitira92/GameHubRemoteEngine/releases/latest/download/GameHubRemoteEngine-Setup.exe)

[Sürüm notları](RELEASE_NOTES.md) · [Değişiklik geçmişi](CHANGELOG.md) · [Destek](#destek)

</div>

---

## Genel Bakış

**GameHub Remote Engine**, oyuncuların ve oyun sunucusu işletmecilerinin onlarca Windows VDS / Dedicated sunucuya hızlı, güvenli ve düzenli bir biçimde erişebilmesi için tasarlanmıştır. Microsoft'un resmi RDP ActiveX bileşenini (`mstscax`) modern bir WPF arayüzünün altına yerleştirir; üzerine kategori, favori, çoklu sekme, **canlı çoklu sunucu paneli** ve sıkı güvenlik kontrolleri ekler.

[gamehubserver.com.tr](https://gamehubserver.com.tr) müşterileri için **GameHubServer panel entegrasyonu** ile sunucu envanterinizi tek tıkla içe aktarabilir, şifreleri panel üzerinden çekebilirsiniz. Bağımsız bir RDP istemcisi olarak da kullanılabilir — istediğiniz Windows sunucusuna manuel ekleyip bağlanabilirsiniz.

---

## Öne Çıkan Yetenekler

- **Canlı çoklu sunucu paneli** — Tüm bağlı oturumların gerçek zamanlı önizlemelerini 2/3/4 sütunlu bir gridde aynı anda izleyin. Hangi sunucunun online/offline olduğunu tek bakışta görün.
- **Çoklu sekme yönetimi** — Onlarca sunucuyu tek pencerede tutun, sekmeler arasında saniyeler içinde geçin.
- **DPAPI ile şifre koruması** — Sunucu şifreleri Windows DPAPI ile şifrelenir; başka bir kullanıcıya veya makineye kopyalansa bile çözülemez.
- **Otomatik yeniden bağlanma** — Ağ kopması olursa uygulama otomatik tekrar bağlanır; manuel müdahale gerekmez.
- **Bilgisayar açıldığında otomatik başlatma** — Windows oturum açtığında uygulama otomatik açılır ve son bağlandığınız sunuculara onay sormadan tekrar bağlanır. Seçenekler → Bağlantı Ayarları'ndan etkinleştirilir.
- **Hızlı bağlantı tespiti** — 3 saniyelik TCP ön-kontrolü; erişilemeyen makineler için 10 saniye beklemezsiniz.
- **GameHubServer panel girişi** — gamehubserver.com.tr hesabınızla giriş yapın, sunucu listenizi tek tıkla içe aktarın, şifreleri otomatik çekin.
- **Favoriler ve kategoriler** — En sık kullandığınız sunucuları yıldızlayın; otomatik veya manuel kategorilerle düzenleyin.
- **Canlı bant genişliği takibi** — Her oturum için anlık indirme/yükleme hızı; status bar'da toplam trafik.
- **Oturum süresi sayacı** — Her bağlantı için bağlı kalma süresi otomatik takip edilir.
- **Açık + Koyu tema** — Anlık geçiş; her bileşen tema farkındalığı ile çalışır.
- **Türkçe + İngilizce arayüz**.
- **Otomatik güncelleme** — Yeni sürümler açılışta tespit edilir, onay sonrası yerinde uygulanır; ayarlarınız ve kasanız korunur.
- **Sıfır iz bırakma** — Üretim sürümünde diske günlük dosyası yazılmaz; bant genişliği desenleri ve oturum süreleri makinenizde iz bırakmaz.
- **Canlı arama** — Sunucu listesinde ad / IP / kategori bazlı anlık filtreleme.
- **Tam ekran modu** — Tek tuşla bağımsız pencerede sergileme; çoklu monitör desteği.

---

## Tüm Özellikler

### Bağlantı Yönetimi

- Tek tıkla bağlantı, çoklu sekme desteği
- 3 saniyelik TCP ön-kontrolü ile erişilemeyen makineler için hızlı geri bildirim
- Otomatik yeniden bağlanma (ağ kopmalarında, ayarlanabilir)
- **Bilgisayar açıldığında otomatik başlatma + son oturumlara bağlanma** — Windows ile birlikte uygulama otomatik açılır, önceki oturumda bağlı olduğunuz sunuculara onay sormadan tekrar bağlanır. Varsayılan olarak kapalı; Seçenekler → Bağlantı Ayarları'ndan etkinleştirilir.
- Bağlantı durumu için canlı göstergeler (Bağlanıyor / Bağlı / Yeniden Bağlanıyor / Başarısız / Çevrimdışı)
- Sekme başına bant genişliği ölçeri (anlık indirme + yükleme hızı)
- Oturum çalışma süresi sayacı
- Tam ekran modu — özel pencerede sergileme + ekrana sığdırma
- Pano ile pano arasında **30 saniyelik otomatik şifre temizleme** (parola yöneticisi davranışı)
- "Bağlantıyı Windows Uzak Masaüstü ile aç" alternatifi

### Çoklu Sunucu Paneli (Genel Bakış)

- Aktif tüm oturumların eş zamanlı **canlı önizleme tile'ları**
- Satır başına 2 / 3 / 4 sütun arasında dinamik geçiş yapan sütun döngü butonu
- Tile'a tıklayınca o oturuma odaklanma (otomatik tek-görünüme geri dönüş)
- Tile altbilgisinde sunucu adı, durum noktası, host bilgisi, çalışma süresi, anlık bant genişliği
- Status bar'da **toplam bant genişliği rozeti** (tüm bağlı oturumların kümülatif trafiği)
- Pencere boyutundan bağımsız olarak seçilen sütun sayısı korunur

### Kenar Çubuğu ve Düzen

- Sunucuların **GameHubServer ürün adına göre otomatik kategorilenmesi** (Ko Vds, Radore Vds, vb.)
- Kategori sırasını sürükle-bırak ile değiştirme (kalıcı)
- Manuel kategori oluşturma, yeniden adlandırma, silme
- Yıldızla **favori işaretleme** — favoriler her kategorinin başına çıkar
- Ad / IP / kategoriye göre **canlı arama** (Türkçe-uyumlu)
- Sunucu satırlarında durum noktası + bağlantı pill'i + favori yıldızı
- Sağ tıklama bağlam menüsü: Bağlan, Bağlantıyı kes, Adresi kopyala, İsmi kopyala, Windows RDP ile aç, Düzenle, Favoriler, **Özellikler**, Kaldır

### "Özellikler" Diyaloğu (GameHubServer entegrasyonu)

GameHubServer'dan içe aktarılmış sunucular için, sağ tık → **Özellikler** ile salt-okunur bilgi görünümü:

- **Atanmış IP** — birincil IP, monospace hizalı
- **Kullanıcı adı** — servis kullanıcı adı
- **Durum** — Active / Suspended / diğer (renkli pill ile)
- **Kayıt Tarihi** — servisin oluşturulma tarihi (Türkçe locale ile)
- **Sonraki Ödeme Tarihi** — bir sonraki fatura tarihi

Asenkron yükleme + yükleniyor / hata / başarılı durumları için ayrı görünümler.

### Sunucu Envanteri Yönetimi

- Manuel sunucu ekleme (Ad, Host, Kullanıcı, Domain, Şifre)
- Düzenleme (`F2`) — şifre alanını boş bırakırsanız mevcut korunur
- Silme (`Delete`) — onay diyaloğu ile
- GameHubServer panelinden **manuel içe aktarma diyaloğu** — checkbox listesi, "Tümünü seç", IP/ada göre arama, ilerleme çubuğu
- Önceden içe aktarılmış servislerin diyalogda etiketlenmesi
- IP normalleştirme — `5-144-177-226` benzeri yazımları otomatik `5.144.177.226`'ya çevirme
- Şifre yenileme — panel üzerinden tek sunucu için tekrar çekme

### Status Bar

- Giriş durumu ve toplam sunucu sayısı
- Aktif oturum sayısı
- **Tek görünüm ↔ Genel Bakış** toggle butonu
- **Toplam indirme / yükleme rozeti** — tüm bağlı oturumlar için kümülatif bant genişliği (2 saniyelik refresh)
- Bildirim zili — son olayları açan popup

### Olay Günlüğü

- Bildirim zili açılır panelinde son olayların listesi
- Seviye-bazlı renk kodlaması (Bilgi / Başarı / Uyarı / Hata)
- "Hepsini temizle" eylemi
- Bağlantı, içe aktarma, panel girişi, hata mesajları gibi olaylar

### Otomatik Güncelleme

- Açılışta tek seferlik kontrol (GitHub Releases üzerinden)
- Yeni sürüm bulununca engellenmeyen indirme diyaloğu
- Tetiklenen Inno Setup sihirbazı yerinde günceller
- Kullanıcı ayarları, DPAPI kasası, GameHubServer oturum tokenları korunur

### GameHubServer Entegrasyonu (Opsiyonel)

[gamehubserver.com.tr](https://gamehubserver.com.tr)'de hesabınız varsa, sunucularınızı tek tek elle eklemek zorunda değilsiniz. Sağ üstteki avatar simgesinden tek tıkla giriş yapın — tarayıcıda hesabınıza giriş yapıp uygulamaya yetki verdiğinizde, tüm aktif VDS'leriniz seçilebilir bir liste olarak gelir.

Yapabilecekleriniz:

- **Sunucularını tek tıkla içe aktar** — VDS envanterinizi seçim listesinden kenar çubuğuna ekleyin. İstediklerinizi seçin, gerisini geçin.
- **Şifreleri otomatik çek** — Her sunucu için şifre panelden güvenle alınır; kendi yazmanıza gerek yok.
- **Servis detaylarını görüntüle** — Bir sunucuya sağ tıklayıp **Özellikler** dediğinizde atanmış IP'sini, kullanıcı adını, durumunu, kayıt tarihini ve sonraki ödeme tarihini panelden canlı olarak görürsünüz.
- **Önceden eklenenleri tekrar eklemez** — İçe aktarma ekranında zaten kenar çubuğunda olan sunucular "Zaten içe aktarılmış" etiketiyle işaretlenir.
- **Tüm cihazlardan çıkış yap** — Tek tıkla diğer bilgisayarlarınızda açık kalan oturumları kapatın.
- **Her giriş için onay ekranı** — Tarayıcıda her zaman bir onay sayfası görürsünüz; uygulama habersiz olarak hesabınıza erişemez.

GameHubServer hesabınız yoksa endişelenmeyin — uygulama bağımsız bir RDP istemcisi olarak da kullanılabilir. Her sunucuyu `Ctrl + N` ile manuel ekleyebilirsiniz.

---

## Güvenlik

Sunucu şifreleriniz ve oturum bilgileriniz, kişisel verinizdir. Onları korumak için kullandığımız temel ilkeler:

- **Şifreler diske yalnızca şifrelenmiş olarak yazılır.** Windows'un yerleşik şifreleme sistemi (DPAPI) kullanılır; şifre dosyaları başka bir kullanıcıya veya makineye kopyalansa bile çözülemez. Sadece sizin Windows hesabınız açabilir.
- **Şifrelerinize sadece bağlantı sırasında erişilir.** Programın geri kalanında şifreler bellekte tutulmaz; bağlantı kurulduktan sonra serbest bırakılır.
- **Pano (clipboard) otomatik temizlenir.** Bir şifreyi kopyaladıktan 30 saniye sonra, başka bir şey kopyalamadıysanız pano kendi kendine temizlenir — parola yöneticilerinin davranışıyla aynı.
- **Diske günlük tutulmaz.** Hangi sunucuya, ne zaman, ne kadar süre bağlandığınız bilgisi diskte iz bırakmaz. Bant genişliği desenleri ve oturum süreleri makinenizde kayıt altına alınmaz.
- **gamehubserver.com.tr ile iletişim güvenlidir.** Tüm panel iletişimi şifreli kanal üzerinden geçer; uygulamaya yetki verirken her seferinde tarayıcıda bir onay ekranı görürsünüz — habersiz erişim mümkün değildir.
- **Hesabınızı tüm cihazlardan tek tıkla kapatabilirsiniz.** Şüpheli durumda avatar menüsünden "Tüm cihazlardan çıkış yap" diyerek farklı bilgisayarlardaki açık oturumlarınızı sonlandırabilirsiniz.

---

## Sistem Gereksinimleri

| | |
|---|---|
| **İşletim sistemi** | Windows 10 sürüm 1809 (build 17763) veya üzeri · Windows 11 |
| **Mimari** | x64 |
| **.NET runtime** | .NET 8 desktop runtime (kurulumda otomatik temin edilebilir) |
| **Bellek** | 512 MB minimum, 2 GB önerilir |
| **Ekran çözünürlüğü** | 1280 × 800 minimum, 1920 × 1080 önerilir |
| **Ağ** | Hedef RDP sunucularına TCP 3389 erişimi |
| **Opsiyonel** | gamehubserver.com.tr hesabı (panel senkronu için) |

---

## Kurulum

1. Yukarıdaki **İndir** butonundan `GameHubRemoteEngine-Setup.exe` dosyasını indirin.
2. Dosyayı çalıştırın. UAC onayı verin.
3. Kurulum sihirbazı **ilk yüklemede** tema (Açık / Koyu) ve dil (Türkçe / English) tercihinizi sorar — bu seçimler daha sonra **Seçenekler** ekranından (`Ctrl + ,`) değiştirilebilir.
4. Yükleme tamamlandığında uygulama otomatik açılır.
5. Sunucu eklemek için iki yol vardır:
   - **Manuel:** `Ctrl + N` ile sunucu ekle diyaloğu
   - **Panelden:** Sağ üstteki avatar simgesi → "gamehubserver.com.tr'ye giriş yap" → tarayıcıda onay → "Sunucuları içe aktar"

Sonraki sürümler otomatik güncelleme ile dağıtılır; kullanıcı eylemi gerekmez.

---

## Sürüm Stratejisi

- **Stable kanal**: GitHub Releases üzerinden yayınlanır; her sürüm için kurulum dosyası, sürüm notları ve değişiklik geçmişi bulunur.
- **Auto-update**: Açılışta yeni sürüm kontrolü yapılır, kullanıcı onayı ile uygulanır.
- **Yedek geriye uyumluluk**: Eski sürümlerin oluşturduğu kullanıcı verisi (sunucu listesi, DPAPI kasası) yeni sürümlerde sorunsuz okunur.

---

## Destek

Hata bildirimi veya özellik talebi için [GitHub Issues](https://github.com/yigitira92/GameHubRemoteEngine/issues/new) üzerinden bize ulaşabilirsiniz.

---

## Lisans

GameHub Remote Engine, **tescilli yazılımdır**.
© Servervia Bilişim Yazılım ve Telekomünikasyon Hizmetleri Ltd. Şti. — Tüm hakları saklıdır.

Pakete dahil mstscax ActiveX bileşeni Microsoft'a aittir; standart Windows lisans şartları altında yeniden dağıtım izinlidir.

Bu repo yalnızca dağıtım kanalı olarak hizmet verir (kurulum dosyaları + sürüm notları). Ürünün kaynak kodu dağıtılmaz.

---

<div align="center">

**Servervia Bilişim** tarafından geliştirilmektedir
[gamehubserver.com.tr](https://gamehubserver.com.tr)

</div>
