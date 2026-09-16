# QA Raporu — `en-US.Projectiles.json` (Mermiler / Minyonlar / Binekler)

- EN kaynak: `İngilizce Dosyalar/Terraria.Localization.Content.en-US.Projectiles.json`
- TR çeviri: `TerrariaTurkce/Content/Localization/en-US.Projectiles.json`
- Sözlük: `Terimler.md`
- Kapsam: 1036 kayıt; eksik/fazla kayıt yok, `{...}` yer tutucu uyumsuzluğu yok. Boş TR kayıtları kaynakta da boştur. `Yoyo`/`UFO`/`Uzi` sınıfı özel adların bırakılması diğer dillerle uyumludur; `{$ItemName.*}` göndermeleri doğru korunmuştur.

## Detaylı Hata Listesi

## CRITICAL

### #1 — CRITICAL — Yanlış ad (“Demir”)

| EN | TR | Fix |
|---|---|---|
| `Anchor` | `Demir` | `Çapa` |

Gemi çapası silahı `demir` (metal) diye çevrilmiş, eşya↔mermi bağı kopmuş ve ad bütünüyle yanlıştır.

## MAJOR

### #2 — MAJOR — Mermi adının sıfata çevrilmesi

| EN | TR | Fix |
|---|---|---|
| `Sword Beam` | `Parlak Kılıç` | `Kılıç Işını` |

`Beam` (mermi hüzmesi) `parlak` sıfatı sanılmış; kardeş kayıtlar `Terra Işını`/`Gece Işını` düzenindedir ve de `Schwertstrahl`/fr `Rayon d'épée` hüzme anlamını doğrular.

### #3 — MAJOR — Sözlük ihlali (Daybloom)

| EN | TR | Fix |
|---|---|---|
| `Daybloom Pellet` | `Gündoğumu Peleti` | `Gündüzparlayan Peleti` |

Sözlük `Daybloom→Gündüzparlayan` derken `Gündoğumu` (sunrise, başka sözcük) yazılmıştır.

### #4 — MAJOR — Yanlış meslek (“Hazine”)

| EN | TR | Fix |
|---|---|---|
| `Spelunker Glowstick` | `Hazine Parlakçubuğu` | `Mağaracı Parlakçubuğu` |

`Spelunker` mağaracı/kaşif demektir, hazine değil; de `Höhlengänger`/fr `spéléo`/es `espeleólogo` da mağaracı kullanır (`Parlakçubuk` kısmı doğrudur).

### #5 — MAJOR — Sistematik sınıf hatası (Bolt → “Ok”)

| EN | TR | Fix |
|---|---|---|
| `Amber Bolt` | `Kehribar Ok` | `Kehribar Cıvata` |
| `Diamond Bolt` | `Elmas Cıvata` (doğru, korunur) | `Elmas Cıvata` |

`Ok` yay mermisidir, büyü mermisi `Cıvata` olmalıdır; dosya zaten 6/10 mücevher mermisinde `Cıvata` kullanır, azınlık (`Kehribar/Ametist/Su Oku`) buna çekilmelidir (Bkz. `QA_en-US.Items.md` #8 — aynı karar eşya tarafında da geçerlidir).

### #6 — MAJOR — Ters çevrilmiş ad (yay ↔ ok)

| EN | TR | Fix |
|---|---|---|
| `Phantasm` | `Hayali Yay` | `Hayali Ok` |

Kayıt ok mermisidir ama `Yay` (bow) yazılmış; kardeş kayıt `PhantasmalBolt→Hayali Cıvata` `Hayali` kısmının doğru olduğunu gösterir, yalnızca ad yanlıştır.

### #7 — MAJOR — Adın renk sıfatına çevrilmesi

| EN | TR | Fix |
|---|---|---|
| `Blood Shot` | `Kan Kırmızı` | `Kanlı Atış` |

`Shot` (atış) adı `Kırmızı` renk sıfatı sanılmış; de `Blutschuss`/fr `Tir de sang`/es `Tiro de sangre` atış anlamını korur.

## MINOR

### #8 — MINOR — Grup teriminin düzleşmesi (“Kötü”)

| EN | TR | Fix |
|---|---|---|
| `Crystal Vile Shard` | `Kötü Kristal Parçacık` | `Uğursuz Kristal Parça` |

`Vile` Yozlaşma grubu terimidir (`Vilethorn`), genel `kötü` sözcüğüne indirgenmiş; ayrıca küçültme eki `Parçacık`, diğer tüm kırık kayıtlarındaki `Parça` (`Kristal Parçası`) ile tutarsızdır.

### #9 — MINOR — Yanlış araç (“Çivi”)

| EN | TR | Fix |
|---|---|---|
| `Crystal Spike` | `Kristal Çivi` | `Kristal Diken` |
| `Slime Spike` | `Balçık Çivi` | `Balçık Dikeni` |

`Çivi` hırdavat demektir, hasar veren diken `Diken` olmalıdır.

### #10 — MINOR — Sözlük çakışması (“Sihirli”)

| EN | TR | Fix |
|---|---|---|
| `Enchanted Beam` | `Sihirli Işın` | `Büyülü Işın` |

`Sihir` sözlükte Mana karşılığıdır; büyülü eşya geleneği `Büyülü` yönündedir, `Sihirli Işın` mana hüzmesi gibi okunur.

## Terminoloji Karar Tablosu

| Terim | Çeviriler (grep) | Karar |
|---|---|---|
| Bolt (büyü mermisi) | `Cıvata` (çoğunluk) / `Ok` (#5 azınlık) | Karar: `Cıvata` — azınlık düzeltilecek (Bkz. `QA_en-US.Items.md` #8). |
| Arrow | `Ok` (tutarlı) | Karar: korunacak; #6 `Yay` hatası düzeltilecek. |
| Spike (diken) | `Çivi` (#9) | Karar: `Diken`. |
| Shard | `Parça(sı)` (çoğunluk) / `Parçacık` (#8) | Karar: `Parça`. |
| Slime | `Balçık` (tutarlı: `Yavru Balçık`, `Balçık Kırbacı/Kancası`) | Karar: korunacak. |
| Beam | `Işını` (çoğunluk) / `Parlak` (#2) | Karar: `Işın(ı)` — #2 düzeltilecek. |
| Daybloom | `Gündüzparlayan` (sözlük) / `Gündoğumu` (#3) | Karar: `Gündüzparlayan`. |
| Glowstick | `Parlakçubuk` (tutarlı) | Karar: korunacak; #4 yalnızca ön ad düzeltilecek. |

## Yerelleştirme Notları

- Sayı ve gönderme bütünlüğü sağlamdır; `{$...}` kalıpları çevrilmemeli.
- Bu dosya, eşya dosyasından zayıftır; #1–#7 düzeltilmeden sürüme alınmamalıdır.
- Kalan iş: `Bolt=Cıvata` ve `Spike=Diken` toplu standardizasyonu, `Terimler.md` güncellemesi (`Çapa`, `Kılıç Işını`, `Mağaracı`).
