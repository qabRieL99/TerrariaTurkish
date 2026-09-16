# QA Raporu — `en-US.json` (Kök UI / Dünya Adı Üretici / Başlıklar / Jenerik)

- EN kaynak: `İngilizce Dosyalar/Terraria.Localization.Content.en-US.json`
- TR çeviri: `TerrariaTurkce/Content/Localization/en-US.json`
- Sözlük: `Terimler.md`
- Kapsam: 3699 kayıt; eksik/fazla kayıt yok, `{...}` yer tutucu uyumsuzluğu yok. 2412 özdeş kaydın çoğu doğrudur (komutlar `help/clear/exit`, kişi adları, `RandomWorldName_Composition` kalıpları, `DeathText '{0}.'`); ancak aşağıda belgelenen üç toplu liste + çekirdek düğmeler haksız yere İngilizce bırakılmıştır.

## Detaylı Hata Listesi

## CRITICAL

### #1 — CRITICAL — Çevrilmemiş toplu liste (Dünya adı sözcükleri, ~2082 kayıt)

| EN | TR | Fix |
|---|---|---|
| `Abandoned` | `Abandoned` | `Terk Edilmiş` |
| `Abode` | `Abode` | `Mesken` |
| `Ability` | `Ability` | `Yetenek` |
| `Abyss` | `Abyss` | `Dipsiz` |
| `Bliss` | `Bliss` (grep eğilimi) | `Mutluluk` |

Tablo temsilîdir; `RandomWorldName_Adjective` (~720), `RandomWorldName_Location` (~490), `RandomWorldName_Noun` (~872) altındaki 2000+ kayıt İngilizce bırakılmışken de-DE (`Verlassen`), fr-FR (`solitaire`), es-ES (`Abandonado`), ru-RU (`Заброшенный`) tamamını çevirmiştir (yalnızca ~11 maden adı `Adamantit` vb. çevrilmiş).

## MAJOR

### #2 — MAJOR — Çevrilmemiş çekirdek düğme

| EN | TR | Fix |
|---|---|---|
| `Enter` | `Enter` | `Gir` |

de `Eingabe`, fr `Saisir`, es `Aceptar`, it `Inserisci`, pl `Wprowadź`, ru `Вход` çevirmişken TR bırakmıştır; menü tutarlılığı bozulmuştur.

### #3 — MAJOR — Çevrilmemiş toplu liste (Oyun başlığı esprileri, 75 kayıt)

| EN | TR | Fix |
|---|---|---|
| `Terraria: Dig Peon, Dig!` | `Terraria: Dig Peon, Dig!` | `Terraria: Kaz Köylü, Kaz!` (`Terraria:` öneki korunur) |
| `Terraria: Epic Dirt` | `Terraria: Epic Dirt` | `Terraria: Destansı Toprak!` |

Tablo temsilîdir; `GameTitle.*` 75/76 kayıt İngilizce bırakılmışken de (`Terraria: Epischer Dreck`), fr (`Terre épique`), es (`¡Cava, peón! ¡Cava!`), ru (`Копай, раб, копай!`) çevirmiştir; her yükleme ekranında görünür.

### #4 — MAJOR — Eylem düğmesinde ad kullanımı

| EN | TR | Fix |
|---|---|---|
| `Save` | `Kayıt` | `Kaydet` |

Düğme eylem ister; aynı ekranlardaki `Oluştur/Sil/Uygula` eylemken `Kayıt` ad olarak kalmış, tutarlılık bozulmuştur.

### #5 — MAJOR — Anlam kaybı + yinelenen ad (zorluk kademeleri)

| EN | TR | Fix |
|---|---|---|
| `Hardcore` | `Zor` | `Zorlu` |
| `Mediumcore` | `Orta` | `Orta Derece` (karar tablosuna bakınız) |
| `Softcore` | `Klasik` | `Klasik` (korunur) |
| `Normal` | `Klasik` | `Normal` (yinelenen `Klasik` kaldırılmalı) |

`-core` (ölüm cezası kademesi) anlamı kaybolmuş ve `Softcore` ile `Normal` birebir aynı `Klasik` adını taşıyınca oyuncular iki kipi ayırt edemez.

### #6 — MAJOR — Anlaşılmaz uydurma sözcük (Favori)

| EN | TR | Fix |
|---|---|---|
| `Favorite` | `Gözdele` | `Favori` |
| `Unfavorite` | `Gözdeden Çıkar` | `Favorilerden Çıkar` |

`Gözdele` düğme için uzun ve belirsiz bir uydurmadır; diğer diller `Favorit/Favori` kökenini korur.

## MINOR

### #7 — MINOR — Çevrilmemiş dizgide çevirmen yazım hatası

| EN | TR | Fix |
|---|---|---|
| `Terraria: Suspicious Looking Eyeballs` | `Terraria: Suspicous Looking Eyeballs` | `Terraria: Şüpheli Bakışlı Gözler` |

Kayıt çevrilmediği gibi kaynakta olmayan `Suspicous` yazım hatası üretilmiş, inceleme eksikliğini kanıtlamıştır (#3 kapsamında yerelleştirilecek).

### #8 — MINOR — Çevrilmemiş çerçeve/tohum adları

| EN | TR | Fix |
|---|---|---|
| `Stone Gold` (MinimapFrame) | `Stone Gold` | `Taş Altın` |
| `Twig Leaf` (MinimapFrame) | `Twig Leaf` | `Dal Yaprak` |
| `Skyblock` (Seed) | `Skyblock` | `Gökada` |
| `The Constant` (Seed) | `The Constant` | `Değişmez` |

de (`Steingold`, `Walküre`), es (`Piedra dorada`, `Valquiria`) bu adları çevirmişken TR bırakmıştır (`Remix/Normal/Xbox` adları doğru bırakılmıştır).

### #9 — MINOR — Sözlük kayması (Usta/Bayrak/Afiş)

| EN | TR | Fix |
|---|---|---|
| `Master` | `Usta` | Sözlük `Efendi` diyor — karar tablosuna bakınız |
| `Banners` (GameUI.BannersTitle) | `Bayraklar` | `Sancaklar` (sözlük `Banner→Sancak`) |

Sözlükten sapılmıştır; oyun içi sancak sistemi `Sancak` kullanırken burada `Bayrak/Afiş` yazılmıştır.

### #10 — MINOR — Belirsiz yerleşim terimi

| EN | TR | Fix |
|---|---|---|
| `Town` (UI.EmoteCategoryTownNPCs) | `Semt` | `Kasaba` |
| `Housing` (UI.NPCHousing) | `Yerleşim` | `Konaklama` (sözlük `Housing→Konaklama`) |

`Semt` (ilçe) yeni oyuncu için belirsizdir; sözlük kararı da gözden geçirilmelidir.

## Terminoloji Karar Tablosu

| Terim | Çeviriler (grep) | Karar |
|---|---|---|
| RandomWorldName sözcükleri | ~2082 kayıt EN (#1) | Karar: toplu çevrilecek. |
| GameTitle esprileri | 75 kayıt EN (#3, #7) | Karar: `Terraria:` öneki korunarak çevrilecek. |
| Enter (düğme) | `Enter` (#2) | Karar: `Gir`. |
| Save (düğme) | `Kayıt` (#4) | Karar: `Kaydet`. |
| Favorite | `Gözdele` (#6) | Karar: `Favori`. |
| Hardcore/Mediumcore/Softcore/Normal | `Zor/Orta/Klasik/Klasik` (#5) | Karar: `Zorlu/Orta Derece/Klasik/Normal` — yinelenen `Klasik` kaldırılacak, sözlüğe işlenecek. |
| Master | `Usta` (#9, sözlük `Efendi`) | Karar: bilinçliyse sözlük `Usta` diye güncellenecek, değilse `Efendi` yapılacak. |
| Banner | `Sancak` (sistem) / `Bayrak/Afiş` (#9) | Karar: birleştirilecek — `Sancak`. |
| Town / Housing | `Semt/Yerleşim` (#10) | Karar: `Kasaba/Konaklama`; `Terimler.md` gözden geçirilecek. |
| Seed / Workshop / Loadout | `Tohum/Atölye/Dizilim` (tutarlı) | Karar: korunacak. |

## Yerelleştirme Notları

- Tarih/saat/sayı biçiminde sorun görülmemiştir; `%` öneki Türkçede doğrudur.
- Ölüm mesajları (`DeathTextGeneric`/`DeathText`, ~150 kayıt) genel olarak başarılıdır (`nalları dikti`, `canavar maması`, `Atlantis'i keşfetti`); yalnızca `Murked→karanlıklar tarafından yok edildi` (uydurma fail) ve `DeathSource` içindeki isteğe bağlı `hem de` renklendirmesi not edilir.
- Kalan iş: #1 (~2082), #3 (75) toplu çevirileri, #2/#4–#6 düğme düzeltmeleri, `Terimler.md` güncellemesi; `EmojiName` listesi Game dosyasındadır (Bkz. `QA_en-US.Game.md` #9).
