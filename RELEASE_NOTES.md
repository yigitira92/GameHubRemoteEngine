# GameHub Remote Engine — v1.0.0

**Yayın tarihi:** 25 Nisan 2026
**Kanal:** Stable
**Sürüm türü:** İlk genel sürüm

İlk genel sürüm. Oyuncuların ve oyun sunucusu işletmecilerinin onlarca Windows VDS / Dedicated sunucuya hızlı, güvenli ve düzenli bir biçimde erişebilmesi için tasarlanmış bir Windows uzak masaüstü istemcisi.

[![İndir](https://img.shields.io/badge/⬇_%C4%B0ndir-GameHubRemoteEngine--Setup.exe_(~71_MB)-22c55e?style=for-the-badge&logo=windows&logoColor=white)](https://github.com/yigitira92/GameHubRemoteEngine/releases/latest/download/GameHubRemoteEngine-Setup.exe)

---

## Bağlantı ve oturum yönetimi

- Tek tıkla bağlantı; tek pencerede çoklu sekme ile paralel oturumlar.
- Bağlanmadan önce 3 saniyelik **TCP ön-kontrolü**: erişilemeyen makineler hızlı, açıklayıcı bir hata diyaloğu ile geri döner; ActiveX'in 10 saniyelik sessiz beklemesi yaşanmaz.
- **Otomatik yeniden bağlanma** ağ kopmalarında (uygulama bazında ayarlanabilir).
- **Tam ekran modu** — bağımsız pencerede sergileme, ekrana sığdırma, ana pencereye geri dönüş.
- **Kimlik bilgisi yardımcısı** — Windows kimlik bilgisi prompt'u açıldığında, depolanan şifreyi tek tıkla kopyalama imkânı sağlayan yan panel.
- **Pano otomatik temizleme** — şifre kopyalama eylemleri sonrası 30 saniye içinde panonun otomatik temizlenmesi (yalnızca pano hâlâ uygulamanın yazdığı değeri içeriyorsa).
- "Windows Uzak Masaüstü ile aç" alternatifi (mstsc.exe direkt çağrısı; argv ile güvenli geçiş).
- **Açılışta sıralı yeniden bağlanma** — son oturuma geri dönme onayı verildiğinde, kuyruktaki tüm makineler tek tek doğru şekilde bağlanır.

## Çoklu sunucu paneli

- **"Genel Bakış"** modu — tüm aktif oturumların gerçek zamanlı önizleme tile'ları yan yana.
- **Sütun döngü butonu** — satır başına 2 / 3 / 4 sütun arasında geçiş; içindeki glyph aktif sütun sayısına göre değişir.
- `UniformGrid` düzeni — pencere genişliğinden bağımsız olarak seçilen sütun sayısı korunur.
- Tile'a tıklayınca o oturuma odaklanma + otomatik tek-görünüme geri dönüş.
- Tile altbilgisi: oturum adı, durum noktası, host, **çalışma süresi sayacı**, **canlı bant genişliği** (indirme + yükleme).
- Status bar'da **toplam bant genişliği rozeti** — tüm bağlı oturumların kümülatif trafiği (2 saniyelik throttled refresh).

## Kenar çubuğu, kategoriler ve arama

- Sunucuların **GameHubServer ürün adına göre otomatik gruplanması** (Ko Vds, Radore Vds, vb.).
- Sürükle-bırak ile **kategori sırası değiştirme** (kalıcı, restart sonrası korunur).
- Manuel kategori ekleme, yeniden adlandırma, silme.
- **Yıldız ile favori işaretleme** — favoriler her kategorinin başına çıkar.
- **Canlı arama** — ad / IP / kategoriye göre filtreleme; Türkçe-uyumlu, locale-safe karşılaştırma.
- Sunucu satırlarında durum noktası + bağlantı pill'i + favori yıldızı.
- Sağ tıklama bağlam menüsü: Bağlan, Bağlantıyı kes, Adresleri kopyala, Windows RDP ile aç, Düzenle, Favoriler, Özellikler, Kaldır.

## "Özellikler" diyaloğu

GameHubServer panelinden içe aktarılmış sunucular için, sağ tık → **Özellikler** ile salt-okunur metadata görünümü:

- **Atanmış IP** — birincil IP, monospace hizalı
- **Kullanıcı adı** — servis kullanıcı adı
- **Durum** — Active / Suspended / diğer (renkli pill ile)
- **Kayıt Tarihi** — `tr-TR` locale ile formatlanmış (örn. "5 Mayıs 2026")
- **Sonraki Ödeme Tarihi** — bir sonraki fatura tarihi

Asenkron yükleme + spinner; panel ulaşılamadığında özel hata durumu.

## Sunucu envanteri yönetimi

- **Manuel sunucu ekleme** (Ad, Host, Kullanıcı, Domain, Şifre).
- **Düzenleme** (`F2`) — şifre alanını boş bırakırsanız mevcut korunur.
- **Silme** (`Delete`) — onay diyaloğu ile.
- **Modal "Sunucuları içe aktar" diyaloğu** — checkbox listesi, "Tümünü seç", IP/ada göre arama, ilerleme çubuğu.
- Önceden içe aktarılmış servislerin diyalogda **"Zaten içe aktarılmış"** etiketi ile işaretlenmesi.
- **IP normalleştirme** — `5-144-177-226` benzeri yazımları otomatik `5.144.177.226`'ya dönüştürme.

## Klavye kısayolları

| Kısayol | Aksiyon |
|---------|---------|
| `Ctrl + N` | Yeni sunucu ekle |
| `F2` | Seçili sunucuyu düzenle |
| `Delete` | Seçili sunucuyu sil |
| `Ctrl + ,` | Seçenekler |
| `Ctrl + Alt + ←` | Önceki oturum |
| `Ctrl + Alt + →` | Sonraki oturum |
| `Enter` | Seçili sunucuya bağlan |

Tüm kısayollar focus context bilinçlidir — RDP ActiveX odaktayken kullanıcı tuş basışları doğal olarak uzak makineye iletilir.

## Arayüz ve tema

- **Windows 11 stili özel başlık çubuğu** (WindowChrome) — Min / Max / Close + hesap avatar dropdown.
- **Açık + Koyu tema** — Seçenekler ekranından canlı geçiş; tüm bileşenler tema farkındalığı ile çalışır.
- **Modern ince kaydırma çubuğu** — sadece thumb'lı, hover-darken / drag-darken efekti.
- **Yuvarlatılmış bağlam menüleri** — MDL2 ikonları, drop shadow, danger-row kırmızı vurgu.
- **Status pill'leri** kare köşeli (CornerRadius=4), tutarlı görünüm.
- **Hesap avatar dropdown** — giriş durumu, e-posta, panel aksiyonları.
- Yüksek-DPI desteği (PerMonitorV2).

## Sistem tepsisi (Tray)

- Pencereyi kapatınca tepsiye küçültme (varsayılan; Seçenekler'den ayarlanabilir).
- Tepsi simgesinden çift tıkla pencereyi geri getirme.
- Sağ tık menüsü: **Göster** / **Çık**.
- İlk küçültmede bilgi balonu (sadece bir kez gösterilir).

## Olay günlüğü

- Status bar'daki bildirim zilinden açılır panel.
- Seviye-bazlı renk kodlaması (Bilgi / Başarı / Uyarı / Hata).
- "Hepsini temizle" eylemi.
- Bağlantı, içe aktarma, panel girişi, hata mesajları otomatik kaydedilir.

## Otomatik güncelleme

- Açılışta tek seferlik kontrol (GitHub Releases üzerinden).
- Yeni sürüm bulununca engellenmeyen indirme diyaloğu.
- Inno Setup sihirbazı yerinde günceller; ayarlar, DPAPI kasası, GameHubServer oturum tokenları korunur.

## GameHubServer panel entegrasyonu (opsiyonel)

[gamehubserver.com.tr](https://gamehubserver.com.tr) hesabınız varsa:

- **OAuth2 + PKCE** ile sistem tarayıcısı üzerinden giriş; onay ekranı her girişte zorunlu olarak gösterilir.
- **JWT** oturum tokenları (HMAC-SHA256, family bazlı refresh rotasyonu, sızıntı tespiti).
- **"Tüm cihazlardan çıkış yap"** desteği.
- Servis envanterinin manuel içe aktarımı (sessiz auto-sync yok).
- Sunucu başına şifrelerin panel üzerinden çekilmesi.
- Servis detaylarının (IP, kullanıcı, durum, tarihler) salt-okunur görüntülenmesi.
- Refresh token süresi dolduğunda kullanıcıya **"Tekrar giriş yapılsın mı?"** modal diyaloğu.

---

## Güvenlik kontrolleri

Üretim seviyesinde varsayılanlar; kapsamlı ön-yayın denetimine karşı doğrulanmıştır.

### Yerel veri koruma

- **Sunucu şifreleri** Windows DPAPI ile şifrelenir (CurrentUser kapsamı + uygulamaya özel entropi). Plaintext yalnızca tek bir bağlantı çağrısı süresince var olur.
- **GameHubServer access + refresh token'ları** da DPAPI şifreli. Decrypt sonrası düz metin byte buffer'ları **`finally` bloğunda sıfırlanır** — heap dump senaryolarında token sızıntısı engellenir.
- **`data/` ve `secrets/` klasörleri** sıkılaştırılmış NTFS DACL ile oluşturulur — yalnızca CurrentUser FullControl + SYSTEM; inheritance kapalı.
- **Üretim sürümünde diske log dosyası yazılmaz.** `%LocalAppData%\GameHubRemoteEngine\logs\` klasörü oluşturulmaz; bant genişliği desenleri, oturum süreleri ve host adları diskte iz bırakmaz.
- Pano otomatik temizleme (30 saniye, parola yöneticisi davranışı).

### Ağ ve kimlik doğrulama

- **Yalnızca HTTPS.** Düz HTTP, panelin API girişinde reddedilir; HSTS başlığı zorunlu.
- **OAuth2 + PKCE** akışı — state + code-verifier kriptografik olarak rastgele.
- **Onay ekranı her girişte zorunlu** — auto-completion bypass'lanmış senaryolar engellenir.
- **JWT** HMAC-SHA256 ile imzalanır; algorithm whitelist (sadece `HS256`).
- **Family bazlı refresh rotasyonu** ve sızıntı tespiti — aynı refresh token'ın iki kez kullanılması durumunda tüm aile otomatik iptal.
- **OAuth state değeri** loglardan temizlenmiş — CSRF nonce yazdırılmıyor.
- **Logout family-revoke için refresh token zorunlu** — 15 dakikalık access token tek başına bir oturum ailesini iptal edemez.
- **IP başına giriş kotası** + **müşteri başına şifre açma kotası** (60/dk) — brute-force koruması.

### Süreç güvenliği

- "Windows Uzak Masaüstü ile aç" eylemi `ProcessStartInfo.ArgumentList` kullanır — kötü niyetli isimli sunucular `mstsc.exe`'ye ek bayrak sokuşturamaz.
- Tüm COM property write'ları RDP ActiveX'e dispatcher üzerinden geçer; STA disiplini zorunlu.
- IPv6 host parsing (RFC 3986 bracket notation) güvenli implementasyon.

### Sunucu tarafı (GameHubServer panel)

- **Admin panelindeki tüm durum-değiştirici POST eylemleri** session-bound CSRF nonce taşır (`hash_equals` ile sabit-zaman doğrulama).
- **Rate limiter scope allowlist** — bilinmeyen scope'lar log + fail-open.
- **Tüm `/servers/*` endpoint'leri** `userid` ile scope'lu — IDOR koruması zorunlu.
- **Login sonrası OAuth flow her zaman onay ekranı gösterir** — code auto-issue etmek yerine onay sayfasına redirect.
- **Denetim günlüğü** her şifre açma, giriş, refresh, çıkış ve admin aksiyonu için.

---

## Build ve dağıtım

- **Tek dosyalı self-contained EXE** — ayrı .NET 8 runtime kurulumu gerekmez.
- **PDB sembolleri** Release build'lerinde tüm projelerden çıkarılır; daha küçük artifact, stack trace'lerde iç sembol sızması yok.
- **Inno Setup installer** ilk kurulumda tema + dil onboarding sorar (yeni sürümlerde atlanır).

---

## Kurulum

1. Yukarıdaki **İndir** butonundan kurulum dosyasını indirin.
2. UAC onayı verip çalıştırın.
3. Sihirbaz tema (Açık / Koyu) ve dil (Türkçe / English) tercihinizi sorar.
4. Yükleme tamamlanınca uygulama otomatik açılır.
5. `Ctrl + N` ile manuel sunucu ekleyebilir, ya da avatar menüsünden gamehubserver.com.tr'ye giriş yapıp envanterinizi içe aktarabilirsiniz.

**Sistem gereksinimleri:**
- Windows 10 / 11 (x64)
- .NET 8 desktop runtime (paket içindeki setup tarafından otomatik temin edilebilir)

---

**Servervia Bilişim Yazılım ve Telekomünikasyon Hizmetleri Ltd. Şti.**
[gamehubserver.com.tr](https://gamehubserver.com.tr)
