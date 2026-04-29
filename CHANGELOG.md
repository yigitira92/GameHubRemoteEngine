# Değişiklik Geçmişi

GameHub Remote Engine üzerindeki tüm önemli değişiklikler bu dosyada belgelenir.
Format [Keep a Changelog](https://keepachangelog.com/tr/1.1.0/) prensiplerini takip eder; sürümleme [Semantic Versioning](https://semver.org/lang/tr/) kurallarına uyar.

---

## [1.0.1] — 2026-04-25

### Eklenenler

- **Bilgisayar açılışında otomatik başlatma + son oturumlara bağlanma**
  Seçenekler → Bağlantı Ayarları altında yeni bir kutucuk. Etkinleştirildiğinde Windows oturum açıldığında uygulama otomatik açılır ve önceki oturumda bağlı olduğunuz sunuculara onay sormadan tekrar bağlanır. Varsayılan olarak kapalı.

- **Bağlantı Ayarları sekmesi**
  Seçenekler ekranında bağlantı davranışıyla ilgili tüm seçenekler (yeniden bağlanma, NLA, tepsi, otomatik başlatma) ayrı bir sekmeye toplandı. Genel sekmesi artık yalnızca dil + tema + UI tercihlerini içerir.

### Değişenler

- Yeni sürümler artık otomatik güncelleme ile dağıtılır; v1.0.0 kullanıcıları açılışta güncelleme bildirimi görür.

[1.0.1]: https://github.com/yigitira92/GameHubRemoteEngine/releases/tag/v1.0.1

---

## [1.0.0] — 2026-04-25

İlk genel sürüm.

### Yetenekler

#### Bağlantı

- Tek tıkla bağlantı, tek pencerede çoklu sekme.
- 3 saniyelik TCP ön-kontrolü ile erişilemeyen makineler için hızlı geri bildirim.
- Otomatik yeniden bağlanma (uygulama bazında ayarlanabilir).
- Tam ekran modu — bağımsız pencerede sergileme + ekrana sığdırma.
- Açılışta sıralı yeniden bağlanma — son oturuma geri dönme onayında, kuyruktaki tüm makineler tek tek doğru şekilde bağlanır.
- "Windows Uzak Masaüstü ile aç" alternatifi (`ProcessStartInfo.ArgumentList` kullanılır; argv injection kapalı).

#### Çoklu oturum görünümü

- "Genel Bakış" modu — tüm aktif oturumların gerçek zamanlı önizleme tile'ları.
- 2 / 3 / 4 sütun arasında geçiş yapan döngü butonu (görünür glyph aktif sayıya göre değişir).
- `UniformGrid` düzeni — pencere genişliğinden bağımsız sütun sayısı korunur.
- Tile'a tıklayınca o oturuma odaklanma + tek-görünüme dönüş.
- Tile altbilgisi: sunucu adı, durum noktası, host, çalışma süresi, anlık bant genişliği.
- Status bar'da toplam bant genişliği rozeti — tüm bağlı oturumların kümülatif trafiği (2 sn throttled refresh).

#### Kenar çubuğu

- GameHubServer ürün adına göre otomatik kategorilenme.
- Sürükle-bırak ile kategori sırası (kalıcı).
- Manuel kategori ekleme / yeniden adlandırma / silme.
- Yıldız ile favori işaretleme; favoriler kategorilerin başına çıkar.
- Canlı arama (ad / IP / kategori; locale-safe).
- Sağ tıklama bağlam menüsü: Bağlan, Bağlantıyı kes, Adresi kopyala, İsmi kopyala, Windows RDP, Düzenle, Favoriler, Özellikler, Kaldır.

#### "Özellikler" diyaloğu (GameHubServer sunucuları için)

- Atanmış IP, Kullanıcı adı, Durum (renkli pill), Kayıt Tarihi, Sonraki Ödeme Tarihi.
- Asenkron yükleme + yükleniyor / hata / başarılı durumları için ayrı görünümler.

#### Sunucu envanteri

- Manuel sunucu ekleme, düzenleme (`F2`), silme (`Delete`).
- Modal "Sunucuları içe aktar" diyaloğu — checkbox listesi, "Tümünü seç", arama, ilerleme çubuğu.
- Önceden içe aktarılmış servislerin "Zaten içe aktarılmış" etiketiyle işaretlenmesi.
- IP normalleştirme (`5-144-177-226` → `5.144.177.226`).

#### Klavye kısayolları

- `Ctrl + N` — Yeni sunucu ekle
- `F2` — Düzenle
- `Delete` — Sil
- `Ctrl + ,` — Seçenekler
- `Ctrl + Alt + ←` / `→` — Önceki / Sonraki oturum
- `Enter` — Bağlan
- Tüm kısayollar focus context bilinçli (RDP ActiveX odaktayken müdahale etmez).

#### Arayüz

- Windows 11 stili özel başlık çubuğu (WindowChrome).
- Açık + Koyu tema; tüm bileşenler tema farkındalığı ile çalışır.
- Modern ince kaydırma çubuğu (sadece thumb'lı, hover-darken).
- Yuvarlatılmış bağlam menüleri (MDL2 ikonları, drop shadow).
- Status pill'leri kare köşeli (CornerRadius=4).
- Hesap avatar dropdown — giriş durumu + panel aksiyonları.
- Yüksek-DPI desteği (PerMonitorV2).

#### Status bar ve sistem tepsisi

- Toplam indirme / yükleme bant genişliği rozeti.
- Tek görünüm ↔ Genel Bakış toggle.
- Bildirim zili — son olayları açan popup.
- Pencereyi kapatınca tepsiye küçültme (varsayılan).
- Tepsi sağ tık menüsü: Göster / Çık.

#### Otomatik güncelleme

- Açılışta tek seferlik kontrol (GitHub Releases üzerinden).
- Engellenmeyen indirme diyaloğu.
- Inno Setup ile yerinde güncelleme; ayarlar + DPAPI kasası korunur.

#### GameHubServer panel entegrasyonu (opsiyonel)

- OAuth2 + PKCE ile sistem tarayıcısı üzerinden giriş.
- JWT bazlı oturum tokenları (HMAC-SHA256, family bazlı refresh rotasyonu).
- "Tüm cihazlardan çıkış yap" desteği.
- Servis envanterinin manuel içe aktarımı.
- Sunucu başına şifrelerin panel üzerinden çekilmesi.
- Refresh token süresi dolduğunda "Tekrar giriş yapılsın mı?" diyaloğu.

#### Yerelleştirme

- Birinci dil **Türkçe**, alternatif olarak **English** yerleşik.
- Tarih / sayı formatlaması aktif kültüre saygı duyar.

### Güvenlik

#### Yerel

- DPAPI tabanlı şifre saklama (CurrentUser kapsamı + uygulamaya özel entropi).
- GameHubServer access + refresh token'ları da DPAPI şifreli; decrypt sonrası düz metin byte buffer'ları `finally` bloğunda sıfırlanır.
- `data/` ve `secrets/` klasörleri sıkılaştırılmış NTFS DACL ile oluşturulur (yalnızca CurrentUser + SYSTEM).
- Üretim sürümünde diske log dosyası yazılmaz; bant genişliği desenleri, oturum süreleri, host adları iz bırakmaz.
- Şifre kopyalama eylemleri sonrası 30 saniye içinde otomatik pano temizleme.

#### Ağ ve kimlik doğrulama

- Yalnızca HTTPS; HSTS zorunlu.
- OAuth2 + PKCE; onay ekranı her girişte zorunlu.
- JWT HMAC-SHA256 ile imzalanır; algorithm whitelist (`HS256` only).
- Family bazlı refresh rotasyonu + sızıntı tespiti.
- Logout family-revoke için refresh token zorunlu.
- IP başına giriş + müşteri başına şifre açma kotaları (60/dk).
- OAuth state değeri loglara yazılmaz.

#### Sunucu tarafı (GameHubServer panel)

- Admin panelinde durum-değiştirici tüm POST'lar session-bound CSRF nonce taşır.
- Rate limiter scope allowlist (bilinmeyen scope log + fail-open).
- Tüm `/servers/*` endpoint'leri `userid` ile scope'lu (IDOR-safe).
- Login sonrası OAuth flow her zaman onay ekranı gösterir.
- Denetim günlüğü her şifre açma, giriş, refresh, çıkış ve admin aksiyonu için.

### Build ve dağıtım

- Tek dosyalı self-contained EXE.
- PDB sembolleri Release build'lerinde tüm projelerden çıkarılır.
- Inno Setup installer ilk kurulumda tema + dil onboarding ile.

[1.0.0]: https://github.com/yigitira92/GameHubRemoteEngine/releases/tag/v1.0.0
