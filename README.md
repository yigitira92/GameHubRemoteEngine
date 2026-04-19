<div align="center">

<img src="https://github.com/yigitira92/GameHubRemoteEngine/releases/download/v1.0.0/GameHubRemoteEngine-Setup.exe" alt="GameHub Remote Engine" width="180" />

# GameHub Remote Engine

**Oyun sunucusu operasyonları için özel geliştirilmiş, modern Windows uzak masaüstü yöneticisi.**

[![Latest Release](https://img.shields.io/github/v/release/yigitira92/GameHubRemoteEngine?label=son%20sürüm&color=2B5F9F)](https://github.com/yigitira92/GameHubRemoteEngine/releases/latest)
[![Downloads](https://img.shields.io/github/downloads/yigitira92/GameHubRemoteEngine/total?label=indirme&color=2B5F9F)](https://github.com/yigitira92/GameHubRemoteEngine/releases)
[![Platform](https://img.shields.io/badge/Windows-10%2F11%20x64-0078D4?logo=windows&logoColor=white)](#sistem-gereksinimleri)

[**İndir**](https://github.com/yigitira92/GameHubRemoteEngine/releases/latest/download/GameHubRemoteEngine-Setup.exe) · [Özellikler](#özellikler) · [Kurulum](#kurulum) · [Güvenlik](#güvenlik--gizlilik) · [Gamehubserver.com.tr](https://gamehubserver.com.tr)

</div>

---

## Nedir?

**GameHub Remote Engine**, [Gamehubserver.com.tr](https://gamehubserver.com.tr) operasyon ekibi için **Servervia Bilişim Yazılım ve Telekomünikasyon Hizmetleri Ltd. Şti.** tarafından özel olarak geliştirilen, profesyonel bir uzak masaüstü (RDP) yöneticisidir. Onlarca Windows sunucuyu tek ekrandan yönetmek, hızlı bağlanmak, favorileri ayırmak, bağlantı kopunca otomatik toparlanmak ve kimlik bilgilerini güvenli tutmak için sıfırdan tasarlandı.

Windows'un yerleşik Uzak Masaüstü Bağlantısı (`mstsc.exe`) ve klasik RDCMan ile karşılaştırıldığında:

| | Windows RDP | RDCMan (klasik) | **GameHub Remote Engine** |
|---|---|---|---|
| Modern arayüz (açık + koyu tema) | ❌ | ❌ | ✅ |
| Şifreleri güvenli saklama | Kısmi | Kısmi | ✅ DPAPI |
| Bağlantı kopunca otomatik yeniden bağlanma | ❌ | ❌ | ✅ Akıllı |
| Çoklu oturum, anlık geçiş | Pencere bazlı | ✅ | ✅ Sidebar + state senkron |
| Canlı bant genişliği göstergesi | ❌ | ❌ | ✅ |
| Olay günlüğü (bildirimler) | ❌ | ❌ | ✅ |
| Otomatik güncelleme | ❌ | ❌ | ✅ |
| Erişilemeyen sunucu için ön-uyarı | ❌ | ❌ | ✅ TCP probe |
| Kimlik yardımcısı (şifre kopyalama) | ❌ | ❌ | ✅ |

---

## Özellikler

### 🎨 Modern arayüz

- **Windows 11 tarzı özel başlık çubuğu** — ince, akıcı, doğal drag behavior
- **Açık & Koyu tema** — anında geçiş, tüm pencereler (Options, About, Update dialog, tray popup) tema-duyarlı
- **İki dil** — Türkçe / English, Options'tan anlık değiştirilebilir (yeniden başlatma yok)
- **Resizable sidebar** — sürükle-bırak ile genişlik ayarı, seçili sunucu sol kenarında accent çizgi ile vurgulu
- **Durum çubuğu** — sunucu sayısı, aktif oturum, canlı bant genişliği, olay günlüğü zili

### 🔌 Hızlı & güvenilir bağlantı

- **Tek tık bağlantı** — sunucuya çift-tıkla veya Enter
- **Pre-flight erişilebilirlik kontrolü** — bağlanmadan önce 3 saniyelik TCP probe; makine kapalıysa hızlı uyarı, ActiveX kara kutusunda bekletmez
- **Otomatik yeniden bağlanma** — bağlantı beklenmedik şekilde koptuğunda yapılandırılabilir gecikmeyle yeniden bağlar; kullanıcının bilinçli kesmelerine dokunmaz, hiç bağlanamayan oturumları da loop'a sokmaz
- **Varsayılan port 3389** — `host` veya `host:port` yazımları otomatik işlenir
- **NLA toggle** — Network Level Authentication'ı problem çıkaran sunucular için kapatabilme
- **Çoklu oturum** — istediğin kadar sunucuya aynı anda bağlan, sidebar'dan aralarında geçiş yap
- **Tam ekran** — Windows kaynaklı "bilinmeyen yayımcı" uyarılarını bastıran özel overlay bar (minimize, tam ekrandan çık, kapat)

### 🔐 Güvenlik & gizlilik

- **Windows DPAPI şifreli yerel saklama** — şifreler `%LocalAppData%\GameHubRemoteEngine\secrets\` altında, **yalnızca Windows hesabının kendisi açabilir**; başka kullanıcılar veya başka makineye kopyalayıp okuyanlar erişemez
- **Hafıza-içi cache** — şifreler uygulama açılırken bir kez decrypt edilir, her bağlantı için diskten tekrar çözülmez (hem hız hem güvenlik)
- **Plaintext disk sızıntısı yok** — hiçbir log satırı şifre içermez; DPAPI blob dosyalarından başka yerde şifre tutulmaz
- **Otomatik temizlik** — uygulama kaldırılırken "kayıtlı sunucularım da silinsin mi?" diye sorar, onay verirsen her şey tertemiz gider

### 🧑‍💼 İş akışı kolaylıkları

- **Favoriler** — yıldızla işaretlediğin sunucular listenin başına gelir, hiçbir özel kategori yok, karmaşa yok
- **Akıllı arama** — isim, IP/hostname, kullanıcı adı, açıklama, etiket — hepsinde eş zamanlı
- **Sağ-tık menü** — Bağlan · Adresi kopyala · İsmi kopyala · Windows RDP'de aç · Düzenle · Çoğalt · Favoriye ekle · Kaldır; her biri ayrı ikon + kısayol tuşu hinti
- **Klavye kısayolları** — `Ctrl+N` yeni sunucu, `F2` düzenle, `Delete` sil, `Ctrl+,` ayarlar, `Ctrl+Alt+←/→` oturumlar arası geçiş
- **Duplicate** — mevcut sunucuyu tek tıkla klonla (şifre + ayarlar dahil)
- **Tepsi entegrasyonu** — pencereyi kapatınca tepsiye iner (opsiyonel), tepsi çift-tık geri getirir

### 💡 Kimlik yardımcısı

Windows bazen RDP'de kendi kimlik giriş penceresini açar (özellikle "Beni hatırla" ilk kurulumda). GameHub Remote Engine bu durumu algılar ve **4 saniye içinde** ekranın köşesinde yardımcı bir popup çıkarır:

- Kullanıcı adını ve şifreyi gösterir (gizle/göster + **Kopyala** butonu)
- "Windows penceresinde **Beni hatırla** kutucuğunu işaretleyin, bir sonraki bağlantıda otomatik doldurulacak" hatırlatıcısı
- Non-modal — Windows kimlik penceresini engellemez, yan yana durur

### 📊 Canlı telemetri

- **Durum çubuğunda** indirme/yükleme pill'leri — seçili oturumun anlık bant genişliği, gerçek zamanlı
- Farklı sunucuya geçince pill'ler o sunucunun trafiğine göre güncellenir
- Sidebar'daki her sunucuda **canlı status dot** (yeşil=bağlı, amber=bağlanıyor, kırmızı=başarısız, gri=offline)

### 🔔 Olay günlüğü

Durum çubuğu sağındaki zil ikonu, her önemli olayı zaman damgasıyla biriktirir:
- Bağlandı / bağlantı koptu / yeniden bağlanılıyor
- Sunucu eklendi / silindi / düzenlendi
- Güncelleme bulundu / indiriliyor / hazır
- Pre-flight başarısız, TCP timeout, kimlik doğrulama hataları

Zilin üzerinde **okunmamış sayısı** amber badge ile görünür; popup'ı açınca otomatik "okundu" olarak işaretlenir. 150 olaylık ring buffer — uzun oturumlarda şişmez.

### 🚀 Otomatik güncelleme

- **Her açılışta** GitHub Releases API'sinden en son sürüm kontrol edilir
- Yeni sürüm varsa **modern 4-aşamalı dialog** açılır:
  1. "Yeni sürüm mevcut — v1.0.1. İndirilsin mi?"
  2. Canlı progress bar (indiriliyor...)
  3. "Güncelleme hazır. Şimdi yeniden başlatılsın mı?"
  4. Hata durumunda açıklayıcı mesaj
- Setup.exe arka planda `%TEMP%`'e iner, restart'ta Inno upgrade moduna geçip dosyaları değiştirir — ayarlar ve kayıtlı sunucular korunur

---

## Kurulum

### Sistem gereksinimleri

- **Windows 10 1809 (17763)** veya üzeri — **Windows 11 önerilir**
- **x64 işlemci** (ARM64 henüz desteklenmiyor)
- **~100 MB disk alanı**
- **Yönetici onayı** (Program Files'a kurulum için — UAC prompt)

> .NET 8 ayrıca kurulum gerekmez — tüm runtime installer'ın içinde gömülü.

### İndirme & kurulum

1. **[GameHubRemoteEngine-Setup.exe](https://github.com/yigitira92/GameHubRemoteEngine/releases/latest/download/GameHubRemoteEngine-Setup.exe)** dosyasını indir (~71 MB).
2. Çalıştır:
   - **SmartScreen** uyarısı çıkarsa → **Daha fazla bilgi** → **Yine de çalıştır** (uygulama code-sign edilmiş değil, ama açık kaynak release'lerimiz güvenlidir).
   - **UAC** onayı iste → Evet de (Program Files'a kurulum için gerekli).
3. Sihirbaz akışı:
   - **Kurulum konumu** — `C:\Program Files\GameHub Remote Engine\` (değiştirebilirsin)
   - **Appearance** — Light veya Dark tema seç
   - **Language** — English veya Türkçe seç
   - **Shortcuts** — masaüstü kısayolu opsiyonel
4. Sihirbaz biter, uygulama otomatik açılır (ya da "Launch" checkbox'ından sen başlatırsın).

### İlk bağlantı

1. Sol sidebar altındaki **+** düğmesine tıkla (ya da `Ctrl+N`).
2. Sunucu bilgilerini gir:
   - **IP Adresi:** `192.168.1.10` veya `5.144.177.241:3390` (port opsiyonel, varsayılan 3389)
   - **İsim:** otomatik doldurulur, elle değiştirebilirsin
   - **Kullanıcı adı:** sunucuda RDP için yetkili hesap
   - **Şifre:** düz metin gir — anında DPAPI ile şifrelenerek diske yazılır
3. **Kaydet** → sunucu sidebar'da belirir.
4. Sunucuya **çift tıkla** veya **Enter** — bağlantı başlar.

### Kaldırma

**Ayarlar → Uygulamalar → GameHub Remote Engine → Kaldır**

Kaldırma sihirbazı tamamlandıktan sonra bir diyalog:  
> *"Also delete your saved servers, passwords and application settings?"*

- **Evet** → `%LocalAppData%\GameHubRemoteEngine\` klasörü komple silinir (data + logs + secrets)
- **Hayır** → sadece Program Files'daki uygulama dosyaları silinir; tekrar kurduğunda sunucuların geri gelir

---

## Güvenlik & gizlilik

Tüm kullanıcı verisi **yerel**, **bu Windows hesabına özel**, **şifreli** saklanır:

```
%LocalAppData%\GameHubRemoteEngine\
├── data\
│   ├── workspace.json    (sunucu listesi — şifre YOK, sadece referans)
│   └── workspace.db      (SQLite — alternatif backend)
├── logs\
│   └── rdcclone-YYYYMMDD.log  (Serilog — şifre içermez)
└── secrets\
    └── {guid}.dpapi      (DPAPI şifreli şifre blobları)
```

**DPAPI (Data Protection API)** Windows'un kullanıcıya özel şifreleme servisidir:
- Şifre çözme anahtarı, Windows kullanıcı hesabınızla birleşir
- Başka bir kullanıcı (Admin bile) blob dosyasını çözemez
- Başka bir makineye kopyalansa çözülemez
- Salt olarak `RdcClone/DPAPI/v1` sabit string kullanılır (entropy)

**Ağ trafiği:**
- RDP bağlantıları doğrudan sunucuna gider — ortada hiçbir proxy/sunucumuz yok
- Uygulamanın yaptığı tek dış istek: **GitHub Releases API**'ye `GET /repos/yigitira92/GameHubRemoteEngine/releases/latest` (her açılışta bir kere, güncelleme kontrolü için)
- Hiçbir telemetri, hiçbir anonim kullanım istatistiği, hiçbir analytics gönderilmez

---

## Auto-update protokolü (teknik)

1. Uygulama açılırken `GET https://api.github.com/repos/yigitira92/GameHubRemoteEngine/releases/latest`
2. Yanıttaki `tag_name` (örn. `v1.0.1`) mevcut assembly version'dan yeniyse UI dialog'u açılır
3. User onaylarsa, `assets[].browser_download_url` üzerinden `GameHubRemoteEngine-Setup.exe` **HttpClient ile streaming** indirilir (`%TEMP%` altına)
4. İndirme sırasında `Content-Length` header'ından yüzde hesaplanıp dialog'a iletilir
5. User restart derse, Setup.exe çalıştırılır + mevcut app `Application.Shutdown()` ile temiz kapanır
6. Inno Setup upgrade modu dosyaları değiştirir, yeni sürüm başlar

Delta update **yok** — her güncellemede tam ~71 MB iner. Basitlik ve güvenilirlik için tercih edildi; ~13 MB olan app için kabul edilebilir. Delta istenirse ileride Velopack/Squirrel entegre edilebilir.

---

## Geliştirici

**Servervia Bilişim Yazılım ve Telekomünikasyon Hizmetleri Ltd. Şti.**  
[gamehubserver.com.tr](https://gamehubserver.com.tr)

Bu uygulama Gamehubserver.com.tr operasyonu için özel olarak sipariş üzerine geliştirilmiştir. Kaynak kodu açık değildir — bu depo yalnızca release binary'lerini ve otomatik güncelleme feed'ini barındırır.

Hata bildirimi, öneri veya destek için: **[GitHub Issues](https://github.com/yigitira92/GameHubRemoteEngine/issues)**

---

<div align="center">

Made with ⚡ for [Gamehubserver.com.tr](https://gamehubserver.com.tr) · © 2026 Servervia Ltd. Şti.

</div>
