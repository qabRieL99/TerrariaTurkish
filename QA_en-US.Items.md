# QA Raporu — `en-US.Items.json` (Eşyalar / İpotoraklar / Ön Ekler)

- EN kaynak: `İngilizce Dosyalar/Terraria.Localization.Content.en-US.Items.json`
- TR çeviri: `TerrariaTurkce/Content/Localization/en-US.Items.json`
- Sözlük: `Terimler.md`
- Kapsam: 9209 kayıt; eksik/fazla kayıt yok, `{...}` yer tutucu uyumsuzluğu yok. Özdeş kayıtların çoğu doğrudur (ressam imzaları, `{$CommonItemTooltip}` göndermeleri, `CombineFormat` kalıpları); `ItemName` altında kalan 60 özdeş adın çoğu özel ad niteliğindedir.

## Detaylı Hata Listesi

## MAJOR

### #1 — MAJOR — Tablo resmi adında anlam kayması

| EN | TR | Fix |
|---|---|---|
| `Living Gore` | `Yaşayan Cinayet` | `Yaşayan Vahşet` |

`Gore` kan/vahşet imgeleri demektir, `cinayet` (murder) değildir; de-DE (`Lebendiges Blut`), fr-FR (`Carnage vivant`), es-ES (`Sangre viviente`) de kan/vahşet sözcüğü kullanır.

### #2 — MAJOR — İki satırın birleştirilmesi, ikinci % kaybı

| EN | TR | Fix |
|---|---|---|
| `20% increased summon damage and melee critical strike chance\n20% increased movement speed` | `%20 artırılmış çağrı hasarı ile yakın dövüş kritik vuruş olasılığı ve hareket hızı` | `Çağrı hasarını ve yakın dövüş kritik vuruş olasılığını %20 artırır\nHareket hızını %20 artırır` |

İki İngilizce satır tek satırda birleştirilmiş, ikinci `%20` kapsamı kaybolmuştur (kardeş kayıt `ApprenticeAltPants` doğru şekilde iki satırdır).

### #3 — MAJOR — Ön ek çakışması (iki farklı ön eke aynı ad)

| EN | TR | Fix |
|---|---|---|
| `Sighted` | `Keskin` | `İsabetli` |
| `Sharp` | `Keskin` | `Keskin` (korunur) |

İki farklı ön ek aynı `Keskin` adını taşıyınca menzil/yakın dövüş ayrımı oyunda ayırt edilemez.

### #4 — MAJOR — Yanlış işlev fiili (“yapar”)

| EN | TR | Fix |
|---|---|---|
| `Places sandcastles using Sand Blocks\n{$CommonItemTooltip.PlacementStyle}` | `Kum Bloklarını kullanarak kumdan kale yapar\n{$CommonItemTooltip.PlacementStyle}` | `Kum Blokları kullanarak kumdan kale yerleştirir\n{$CommonItemTooltip.PlacementStyle}` |

`Places X` kalıbı dosyanın her yerinde `yerleştirir` ile karşılanırken burada `yapar` yazılmış, yerleştirilebilir eşya kuralı bozulmuştur.

## MINOR

### #5 — MINOR — Sözlük çakışması (Adept = Uzman)

| EN | TR | Fix |
|---|---|---|
| `Adept` | `Uzman` | `Yetkin` |

Sözlük `Expert→Uzman` dediği için büyü ön eki zorluk kademesiyle aynı adı taşımıştır; de/fr de ikisini ayrı tutar.

### #6 — MINOR — Yanlış kavram (“Kanlı”)

| EN | TR | Fix |
|---|---|---|
| `Murderous` | `Kanlı` | `Gaddar` |

`Kanlı` (Bloody) ayrı bir kavramdır, `Murderous` katil ruhlu demektir; diğer diller cinayet türevi kullanır.

### #7 — MINOR — Kaba kayıt (“Manyak”)

| EN | TR | Fix |
|---|---|---|
| `Manic` | `Manyak` | `Manik` |

Diğer tüm ön ekler yansız sıfatken argo/kaba sözcük kayıt kırmıştır; `Manik` standart Türkçe terimdir.

### #8 — MINOR — Sistematik tutarsızlık (Bolt → “Ok”)

| EN | TR | Fix |
|---|---|---|
| `Amber Bolt` | `Kehribar Ok` | `Kehribar Cıvata` |
| `Amethyst Bolt` | `Ametist Oku` (grep ile doğrulanan eğilim) | `Ametist Cıvata` |
| `Water Bolt` | `Su Oku` (grep ile doğrulanan eğilim) | `Su Cıvatası` |

`Ok` yay mermisidir, büyü mermisi `Cıvata` olmalıdır; dosya zaten 6/10 mücevher mermisinde `Cıvata` kullanır (`Elmas Cıvata` vb.), azınlık kayıtlar buna çekilmelidir (Bkz. `QA_en-US.Projectiles.md` #5 — aynı kural mermi adlarında da geçerlidir).

### #9 — MINOR — Sayı biçimi ve yerelleşmemiş ad

| EN | TR | Fix |
|---|---|---|
| `Provides 7 seconds of immunity to lava` | `Lava karşı yedi saniyelik bağışıklık sağlar` | `Lav karşısında 7 saniyelik bağışıklık sağlar` |

Eşya adı `Lav Tılsımı` diye çevrilmişken açıklamada `Lava` kalmış ve 350+ ipucunda rakam kullanılırken burada sayı yazıyla yazılmıştır.

### #10 — MINOR — İpucu satır sırasının ters çevrilmesi

| EN | TR | Fix |
|---|---|---|
| `...minions by 1 / ...sentries by 1 / ...damage by 22%` (`StardustHelmet`) | `Azami yardakçı sayısını 1 artırır / Çağrı hasarını %22 artırır / Azami nöbetçi sayısını 1 artırır` | Kaynak sırası korunmalı: `Azami yardakçı sayısını 1 artırır / Azami nöbetçi sayısını 1 artırır / Çağrı hasarını %22 artırır` |

Satır sırası kaynaktan sapmış, set bonusu okunurken karışıklığa yol açabilir.

### #11 — MINOR — Uydurma sözcük (“Mitsel”)

| EN | TR | Fix |
|---|---|---|
| `Mythical` | `Mitsel` | `Efsunlu` (sözlük kararına bakınız) |

`Mitril` madeninden türetilmiş uydurma sözcük, `Mystic→Gizemli` ile de çakışır; normal mitolojik sıfat kullanılmalıdır.

## Terminoloji Karar Tablosu

| Terim | Çeviriler (grep) | Karar |
|---|---|---|
| Bar (külçe) | `Külçe` (tutarlı 20+ kayıt) / sözlük `Kalıp` | Karar: `Külçe` doğrudur, sözlük düzeltilecek (`Bar külçe→Külçe`, mobilya `Bar→Bar`); hiçbir `Külçe` kaydı `Kalıp` yapılmayacak. |
| Bolt (büyü mermisi) | `Cıvata` (çoğunluk) / `Ok` (#8 azınlık) | Karar: `Cıvata` — azınlık kayıtlar düzeltilecek. |
| Sighted / Sharp | ikisi de `Keskin` (#3) | Karar: `Sighted→İsabetli`, `Sharp→Keskin`. |
| Adept | `Uzman` (#5, `Expert` ile çakışır) | Karar: `Yetkin`. |
| Murderous | `Kanlı` (#6) | Karar: `Gaddar`. |
| Mana / Minion / Mount | `Sihir` / `Yardakçı` / `Binek` (tutarlı) | Karar: korunacak. |
| Madenler / Ahşaplar | `Klorofit/Adamantit/Mitril/Orikalkum` / `Abanoz/Akahşap/Gölgeahşap` (tutarlı) | Karar: korunacak. |

## Yerelleştirme Notları

- Sayı/yüzde bütünlüğü örneklemde sağlamdır (SDMG %66, Mısır Şekeri %33 vb. korunmuş); `{$...}` göndermeleri çevrilmemeli.
- Çağırma/yerleştirme/ateşleme fiilleri tutarlıdır (#4 tek istisnadır).
- Kalan iş: #8 `Bolt→Cıvata` toplu geçişi, `Terimler.md` güncellemesi (`Bar→Külçe` düzeltmesi, `Yetkin/Gaddar/Manik/İsabetli/Efsunlu` kayıtları).
