# QA Raporu — `en-US.Town.json` (Kasaba NPC Diyalogları)

- EN kaynak: `İngilizce Dosyalar/Terraria.Localization.Content.en-US.Town.json`
- TR çeviri: `TerrariaTurkce/Content/Localization/en-US.Town.json`
- Sözlük: `Terimler.md`
- Kapsam: 2052 kayıt; eksik/fazla kayıt yok, `{...}` yer tutucu uyumsuzluğu yok. 1043 özdeş (EN==TR) kaydın tamamı özel adlardır (NPC/evcil hayvan adları: `Alfred`, `Molly`…) ve doğru şekilde bırakılmıştır; balçık cıvıltıları (`Burble bubble?` vb.) da bilinçli bırakılmış seslerdir.

## Detaylı Hata Listesi

## CRITICAL

### #1 — CRITICAL — Yanlış dost sözcük (“kazılar”)

| EN | TR | Fix |
|---|---|---|
| `These digs are great - loving the personal space.` | `Bu kazılar harika - kişisel alanı seviyorum.` | `Bu ev harika - kişisel alanı seviyorum.` |

`Digs` burada konaklama (ev) demektir, kazı değil; Hemşire evini överken çeviri kazıdan söz eder olmuştur.

### #2 — CRITICAL — Deyimin gerçek anlamla çevrilmesi

| EN | TR | Fix |
|---|---|---|
| `{NPCName} rubs me the wrong way. Maybe it's the weird clothing?` | `{NPCName} beni yanlış yönlendiriyor. Belki tuhaf kıyafetleridir?` | `{NPCName} sinirime dokunuyor. Belki tuhaf kıyafetlerindendir?` |

`Rub someone the wrong way` (sinirine dokunmak) deyimi `yanlış yönlendirmek` diye gerçek anlamıyla çevrilmiş, ruh hali cümlesi ters yöne gitmiştir.

### #3 — CRITICAL — Yanlış nesne (“saç tokası”)

| EN | TR | Fix |
|---|---|---|
| `I kinda want to go out there and collect heads of hair for wigs, but I kinda don't want to GO OUT THERE!` | `Oraya gidip peruk için saç tokası toplamak istiyorum gibi de, ama oraya gitmek de istemiyorum gibi!` | `Şu peruklar için dışarı çıkıp tutam tutam saç toplamak istiyorum gibi de, ama DIŞARI ÇIKMAK istemiyorum gibi!` |

`Heads of hair` (perukluk saç/tutam) `saç tokası` (toka) ile karıştırılmış, nesne tamamen değişmiştir.

### #4 — CRITICAL — Espri ve anlam kaybı (“clubbing” → “temizlik”)

| EN | TR | Fix |
|---|---|---|
| `When I offer you to go clubbing, I don't mean downtown. I mean like, with a five iron?` | `Eline sopayı al dediğimde, sana temizlik yapmanı söylemiyorum. Demeye çalıştığım, sopayı eline al da iki el atalım.` | `Seni kulübe götürmeyi teklif ettiğimde gece kulübünden söz etmiyorum. Golf sopasıyla, hani şu beş numaralı demirle oynamaktan söz ediyorum?` |

`Clubbing` (gece kulübü) esprisi `temizlik` diye uydurulmuş, kaynakta olmayan bir anlam eklenmiştir.

### #5 — CRITICAL — Yanlış sözcük (“cümbüş”)

| EN | TR | Fix |
|---|---|---|
| `Oops! I better hold on to my tiara, it's rather blustery out today!` | `Ups! Tacıma sarılsam iyi olur, bugün bayağı bir cümbüş burası!` | `Ups! Tacıma sarılsam iyi olur, bugün dışarısı bayağı rüzgarlı!` |

`Blustery` (rüzgarlı) `cümbüş` (eğlence) ile karıştırılmış, hava durumu cümlesi anlamsızlaşmıştır.

## MAJOR

### #6 — MAJOR — Kelime oyununun yanlış okunması (“wind”)

| EN | TR | Fix |
|---|---|---|
| `Keep your talismans close... if you wind some, you lose some.` | `Tılsımlarını yakında tut... eğer biraz dolaşırsan, biraz kaybedersin.` | `Tılsımlarına sahip çık... rüzgâra kaptırırsan kaybedersin.` |

`Wind` (sarmak) eylemi `dolaşmak` sanılmış; öneri rüzgâr anlamını nötr biçimde korur.

### #7 — MAJOR — Cümle içi sen/siz karışması

| EN | TR | Fix |
|---|---|---|
| `...Perhaps you could even use them any time you wish!` | `...Belki de onları dilediğiniz zaman kullanabilirsin!` | `...Belki de onları dilediğin zaman kullanabilirsin!` |

Aynı cümlede `dilediğiniz` (siz) ile `kullanabilirsin` (sen) karışmıştır; Barmen'in geri kalanı `sen` dilindedir.

### #8 — MAJOR — Uyarı kipinin geçmiş zamana çevrilmesi

| EN | TR | Fix |
|---|---|---|
| `Graveyards are spooky and very dangerous. I'd watch your step, kid.` | `Mezarlıklar ürkütücü ve çok tehlikelidir. Adımına dikkat ederdim evlat.` | `Mezarlıklar ürkütücü ve çok tehlikelidir. Adımına dikkat et evlat.` |

`I'd watch` (uyarı/öneri) geçmiş zaman kipi `ederdim` ile karşılanmış, uyarı anlamı kaybolmuştur.

### #9 — MAJOR — Yazım hatası (“san”)

| EN | TR | Fix |
|---|---|---|
| `You want boomerang bombs? Throw some out in that gust, they'll come back to you alright!` | `Bumerang bombaları ister misin? Onları bu rüzgara at, san geri döneceklerdir!` | `Bumerang bombası mı istiyorsun? Şu rüzgâra doğru at, sana geri dönecekler!` |

`Sana` sözcüğü `san` yazılmış ve `döneceklerdir` resmiyeti konuşma sesini bozmuştur.

### #10 — MAJOR — Korsan sesinin düzleşmesi + yanlış terim

| EN | TR | Fix |
|---|---|---|
| `Hardee harr... the sea be a pirate's graveyard! Ye landlubbers waste ye time!` | `Deniz bir korsan mezarlığıdır! Siz kara avcıları zamanınızı boşa harcıyorsunuz!` | `Harr harr... deniz bir korsanın mezarlığıdır be! Siz kara fareleri vaktinizi boşa harcıyorsunuz!` |

`Landlubber` (denize çıkmayan kişi) `kara avcısı` değildir ve gerekçesiz `siz` dili dosyanın `sen` baskın düzenini bozmaktadır.

## MINOR

### #11 — MINOR — Dünya nesnesi adı (küçük harf + sözlük)

| EN | TR | Fix |
|---|---|---|
| `If you combine lenses at a crimson altar, you might be able to find a way to summon a powerful monster. You will want to wait until night before using it, though.` | `Mercekleri bir kızıl sunakta birleştirirsen, güçlü bir canavarı çağırmanın bir yolunu bulabilirsin. Yine de kullanmadan önce geceye kadar beklemen gerekecek.` | `Mercekleri bir Kızıl Sunak'ta birleştirirsen, güçlü bir canavarı çağırmanın bir yolunu bulabilirsin. Yine de onu kullanmadan önce geceyi beklemen gerekecek.` |

Dünya nesnesi özel ad ister ve sözlük sıfat kuralı gereği `Kızıl Sunak` yazılmalıdır (Bkz. `QA_en-US.Game.md` #2).

## STYLE

### #12 — STYLE — Katı liste anlatımı (Dünya durumu)

| EN | TR | Fix |
|---|---|---|
| `{0} is {1}% hallow, {2}% corrupt, and {3}% crimson.` | `{0} dünyası, %{1} kutsallık, %{2} yozlaşma ve %{3} kızıllık içeriyor.` | `{0} dünyası: %{1} Kutsal, %{2} Yoz ve %{3} Kızıl.` |

Sözlük notu gereği sıfat konumunda `Kutsal/Yoz/Kızıl` kullanılmalı; `%` konumu Türkçede doğrudur, yalnızca liste serttir (`WorldStatusHallow/Corrupt/Crimson` kardeş kayıtlar da aynı karara tabidir).

## Terminoloji Karar Tablosu

| Terim | Çeviriler (grep) | Karar |
|---|---|---|
| Hitap (sen/siz) | ezici çoğunluk `sen` / #7, #10 `siz` sızıntısı | Karar: tüm NPC diyaloglarında `sen` — #7 ve #10 düzeltilecek. |
| digs (konaklama) | `kazılar` (#1) | Karar: `ev/mekân`, asla `kazı` değil. |
| landlubber | `kara avcıları` (#10) | Karar: `kara faresi` (denizci kayıt). |
| blustery | `cümbüş` (#5) | Karar: `rüzgarlı`. |
| heads of hair | `saç tokası` (#3) | Karar: `tutam saç`. |
| Crimson Altar | `kızıl sunak` (#11) | Karar: `Kızıl Sunak`. |
| Dryad (ad) | `Dryad` (bırakılmış) | Karar: özel ad olarak `Dryad` kalır (Bkz. `QA_en-US.NPCs.md`); sözlükte kayıt açılmayacak. |

## Yerelleştirme Notları

- Sayı/yüzde ve `{NPCName}` göndermeleri sağlamdır; `%` öneki Türkçede doğrudur.
- Dosyanın genel sesi ve `sen` tutarlılığı iyidir; espri/deyim cümleleri (#1–#6) yeniden yazım gerektirir.
- Kalan iş: `Terimler.md` dosyasına `kara faresi`, `tutam saç`, `Kızıl Sunak` kayıtları işlenecek.
