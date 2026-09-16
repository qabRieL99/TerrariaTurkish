# QA Raporu — `en-US.Game.json` (Game / Bestiary / Buff / Ölüm Dışı Oyun Metinleri)

- EN kaynak: `İngilizce Dosyalar/Terraria.Localization.Content.en-US.Game.json`
- TR çeviri: `TerrariaTurkce/Content/Localization/en-US.Game.json`
- Sözlük: `Terimler.md` (kararlarda önceliklidir)
- Kapsam: 2337 kayıt; eksik/fazla kayıt yok (0/0), `{...}` yer tutucu uyumsuzluğu yok, boş TR kayıtlarının tamamı kaynakta da boş (çevirmen hatası değil).

Not: `<Skeletron>` → `<İskeletron>` etiket farkı bilinçli yerelleştirmedir (es-ES de `<Esqueletrón>` kullanıyor; `Terimler.md` `Skeletron→İskeletron` diyor), teknik hata değildir.

## Detaylı Hata Listesi

## CRITICAL

### #1 — CRITICAL — Zehir yerine “ağ” yazılması

| EN | TR | Fix |
|---|---|---|
| `Weapon Imbue: Poison` | `Silah Kaplaması: Ağı` | `Silah Kaplaması: Zehir` |

`Ağı` balık ağı demektir, zehirle ilgisi yoktur ve oyuncu yanlış eşyayı arayacağı için anlam tamamen bozulmuştur.

### #2 — CRITICAL — Sözlük ihlali + düşman türünün yanlış çevrilmesi

| EN | TR | Fix |
|---|---|---|
| `Manipulated through the hive mind of the Crimson, Creepers serve as the brain's eyes and orbit around it for defense in numbers.` | `Crimson'ın kovan zihninde manipüle edilen örümcekler, beynin gözleri olarak hizmet eder ve savunmada sayı üstünlüğü için etrafında dolanır.` | `Kızıllık'ın kovan zihniyle yönlendirilen Sürüngenler, beynin gözleri olarak görev yapar ve savunma için sayı üstünlüğüyle etrafında dolanır.` |

`Creeper` tür adı `örümcekler` değildir ve `Crimson` sözlük karşılığı `Kızıllık` dururken İngilizce bırakılmıştır (Bkz. `QA_en-US.Town.md` — `Kızıl Sunak` kararı).

## MAJOR

### #3 — MAJOR — Eklenen yanlış bilgi (“evine”)

| EN | TR | Fix |
|---|---|---|
| `{0} has arrived!` | `{0} evine vardı!` | `{0} geldi!` |

Kaynakta olmayan `evine` bilgisi eklenmiştir ve bu metin konaklamayla ilgisiz gelişlerde de kullanıldığı için (diğer 6 dilde de yalnızca “geldi” vardır) yanlıştır.

### #4 — MAJOR — Bozuk dilbilgisi (bağışıklık)

| EN | TR | Fix |
|---|---|---|
| `Immune to lava` | `Lava bağışıklık` | `Lava karşı bağışıklık` |

İki ad yan yana getirilmiş, ek ve yönelme bağı kurulmamıştır; ayrıca `Lava` adı eşya adında `Lav` diye çevriliyken burada İngilizce kalmıştır.

### #5 — MAJOR — Yanlış oyun terimi (“doğum noktası”)

| EN | TR | Fix |
|---|---|---|
| `You can change your spawn point by placing and using a bed.` | `Bir yatak yerleştirerek ve kullanarak doğum noktanı değiştirebilirsin.` | `Bir yatak yerleştirip kullanarak yeniden doğma noktanı değiştirebilirsin.` |
| `You can set a new spawn point by placing and using a bed.` (LoadingTips_Default.6, TR: `...yeni bir doğum noktası...`) | `...yeni bir doğum noktası belirleyebilirsin.` | `...yeni bir yeniden doğma noktası belirleyebilirsin.` |

`Doğum noktası` doğum yeri demektir, oyundaki `yeniden doğma (respawn) noktası` kavramını karşılamaz.

### #6 — MAJOR — Sözlük ihlali (Hallow temizlenmesi)

| EN | TR | Fix |
|---|---|---|
| `Ghouls cleansed by the Hallow possess a psychedelic saliva that renders their victims confused and distracted by visions and mirages.` | `Hallow tarafından temizlenen hortlaklar, kurbanlarının hayalleri ve seraplarıyla kafasını karıştıran ve dikkatini dağıtan bir tükürüğe sahiptir.` | `Kutsallık tarafından arındırılan hortlaklar, kurbanlarının zihinlerini hayaller ve seraplarla bulandırıp dikkatlerini dağıtan halüsinojenik bir tükürüğe sahiptir.` |

Dosyanın geri kalanında doğru kullanılan `Kutsallık` burada `Hallow` bırakılmış ve `psychedelic` karşılığı düşmüştür.

### #7 — MAJOR — Sözlük tutarsızlığı (Skeletron)

| EN | TR | Fix |
|---|---|---|
| `Mechanically reconstructed for reviving Cthulhu, this Skeletron has more arms than ever before, and a variety of fierce weapons.` | `Cthulhu'yu canlandırmak için mekanik olarak yeniden inşa edilen bu Skeletron, her zamankinden daha fazla kola ve çeşitli sert silahlara sahip.` | `Cthulhu'yu canlandırmak için mekanik olarak yeniden inşa edilen bu İskeletron, her zamankinden daha fazla kola ve çeşitli sert silahlara sahip.` |

Aynı dosyadaki `SkeletronText` etiketleri `İskeletron` kullanırken burada `Skeletron` yazılmış, sözlük ve dosya içi tutarlılık bozulmuştur.

### #8 — MAJOR — Karakter sesi kırılması (sen/siz)

| EN | TR | Fix |
|---|---|---|
| `<Skeletron> You can save 15% using code: CHIPPY` | `<İskeletron> Kod kullanarak %15 tasarruf edebilirsiniz: CHIPPY` | `<İskeletron> Kod kullanarak %15 tasarruf edebilirsin: CHIPPY` |

Aynı konuşmadaki Taunt1/2 `sen` diliyle (`görüşürüz`, `unutma`) kurulmuşken Taunt3 `siz` diline geçmiştir (Bkz. `QA_en-US.Town.md` — dosya genelinde `sen` kararı).

### #9 — MAJOR — Çevrilmemiş toplu liste (EmojiName, 151 kayıt)

| EN | TR | Fix |
|---|---|---|
| `heart` | `heart` | `kalp` |
| `angry` | `angry` | `kızgın` |
| `cry` | `cry` | `ağlama` |
| `beach` | `beach` | `plaj` |

Tablo yalnızca temsilîdir; `EmojiName.*` altındaki 151 kaydın tamamı İngilizce bırakılmışken de-DE (`herz`), fr-FR (`coeur`), es-ES (`corazón`), it-IT (`cuore`), pl-PL (`serce`) tamamını çevirmiştir.

### #10 — MAJOR — Çevrilmemiş harita nesneleri

| EN | TR | Fix |
|---|---|---|
| `Tungsten` | `Tungsten` | `Tungsten` → `Volfram` (karar tablosuna bakınız; en azından tutarlı bir TR karşılık) |
| `Larva` | `Larva` | `Larva` |

Diğer dillerin tamamı bu iki adı yerelleştirmiştir (de `Wolfram/Larve`, fr `Tungstène/Larve`, es `Tungsteno/Larva`, ru `Вольфрам/Личинка`), TR olduğu gibi bırakmıştır.

## MINOR

### #11 — MINOR — UI etiketinde yanlış sözcük (“Patron”)

| EN | TR | Fix |
|---|---|---|
| `Boss Enemy` | `Patron` | `Boss` |

`Patron` işveren demektir ve filtre etiketinde belirsizdir; diğer dillerin tamamı `Boss` sözcüğünü korumuştur.

### #12 — MINOR — Kısaltma kaybı (“Kitap No”)

| EN | TR | Fix |
|---|---|---|
| `Bestiary ID` | `Kitap No` | `Yaratık Kitabı No` |

Sözlük `Bestiary→Yaratık Kitabı` derken çıplak `Kitap` göndermeyi kaybettirmiştir.

### #13 — MINOR — Eklenen bilgi (“rastgele”)

| EN | TR | Fix |
|---|---|---|
| `Increased damage, Decreased life regen, Causes status effects` | `Artırılmış hasar, azaltılmış sağlık yenilenmesi, rastgele olumsuz bir etki` | `Artırılmış hasar, azalmış sağlık yenilenmesi, durum etkilerine yol açar` |

Kaynakta `rastgele` (random) sözcüğü yoktur, çevirmen tarafından eklenmiştir.

## STYLE

### #14 — STYLE — Abartılı karşılık (“Ölümsüz”)

| EN | TR | Fix |
|---|---|---|
| `Become invulnerable to damage!` | `Ölümsüz ol!` | `Hasara karşı dokunulmaz ol!` |

Tanrı modu hasara dokunulmazlıktır, ölümsüzlük değildir; önerilen ifade mekaniği doğru anlatır.

## Terminoloji Karar Tablosu

| Terim | Çeviriler (grep) | Karar |
|---|---|---|
| Crimson | `Kızıllık` (çoğunluk) / `Crimson` (#2) / `kızıl` (sıfat, doğru) | Karar: `Kızıllık` (ad), sıfatken `Kızıl` — #2 düzeltilecek; `Terimler.md` notuyla uyumlu (Bkz. `QA_en-US.Town.md` `Kızıl Sunak`). |
| Hallow | `Kutsallık` (çoğunluk) / `Hallow` (#6) | Karar: `Kutsallık` — #6 düzeltilecek. |
| Skeletron | `İskeletron` (etiketler) / `Skeletron` (#7) | Karar: `İskeletron` — #7 düzeltilecek. |
| spawn point | `doğum noktası` (#5) | Karar: `yeniden doğma noktası` — LoadingTips 5/6 düzeltilecek. |
| Boss (etiket) | `Patron` (#11) | Karar: UI etiketlerinde `Boss` korunacak. |
| Bestiary | `Yaratık Kitabı` (çoğunluk) / `Kitap` (#12) | Karar: `Yaratık Kitabı`, kısaltılmayacak. |
| EmojiName | tamamı EN (#9) | Karar: çevrilecek (`kalp`, `kızgın` vb.). |
| Tungsten / Larva | tamamı EN (#10) | Karar: TR karşılık verilecek (`Volfram`/`Larva` önerisi sözlüğe işlenecek). |
| Slime / Corruption | `Balçık` / `Yozlaşma` (tutarlı) | Karar: mevcut kullanım doğru, korunacak. |

## Yerelleştirme Notları

- Sayı/yüzde/yer tutucu bütünlüğü örneklemde sağlamdır (`%15`, `%66.2`, `{0}` korunmuş); `{$...}` göndermeleri çevrilmemeli.
- Ölüm mesajları bu dosyada değil, kök dosyadadır (`DeathTextGeneric`/`DeathText`); oradaki genel kalite iyidir (Bkz. `QA_en-US.md`).
- Kalan iş: #9 EmojiName toplu çevirisi (151 kayıt), #10 harita nesnesi kararı, `Terimler.md` güncellemesi (`yeniden doğma noktası`, `Volfram`).
