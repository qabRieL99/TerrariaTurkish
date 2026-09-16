# QA Raporu — `en-US.NPCs.json` (NPC Adları)

- EN kaynak: `İngilizce Dosyalar/Terraria.Localization.Content.en-US.NPCs.json`
- TR çeviri: `TerrariaTurkce/Content/Localization/en-US.NPCs.json`
- Sözlük: `Terimler.md`
- Kapsam: 730 kayıt; eksik/fazla kayıt yok, yer tutucu uyumsuzluğu yok. ~51 özdeş kaydın bir kısmı doğrudur (`Tim`, `Fritz`, `Frankenstein`, `Lamia`, `Golem`, `Medusa`, `Paladin`, `Yeti`, `Krampus`, `Plantera` — tüm diller özel ad diye bırakır); ancak aşağıdaki tür adları diğer diller çevirmişken TR bırakmıştır. Olumlu: `Nymph→Orman Perisi`, `Mothron→Güvetron`, `DukeFishron→Dük Balıkejder`, `Skeletron→İskeletron`, tüm balçık adları `* Balçık` (`Kaka Balçık` dahil) sözlükle uyumludur.

## Detaylı Hata Listesi

## MAJOR

### #1 — MAJOR — Anlamsız ad (“Yaprakçığlığı”)

| EN | TR | Fix |
|---|---|---|
| `Everscream` | `Yaprakçığlığı` | `Sonsuzçığlık` |

Mevcut ad `yaprakçık` yazımına benzeyen anlamsız bir türevdir; de `Immerschrei`/fr `Hurléternel`/es `Gritoeterno` çığlık esprisini korur.

### #2 — MAJOR — Çevrilmemiş simgesel ad (Dryad)

| EN | TR | Fix |
|---|---|---|
| `Dryad` | `Dryad` | `Driyad` |

de/fr `Dryade`, es `Dríada`, ru `Дриада` yerelleştirmişken TR bırakmıştır; görünürlüğü yüksek dost NPC'dir.

### #3 — MAJOR — Çevrilmemiş tür adı (Harpy)

| EN | TR | Fix |
|---|---|---|
| `Harpy` | `Harpy` | `Harpi` |

Sözlük `Harpy=?` diye açık bırakmıştır; de `Harpyie`/fr `Harpie`/es `Arpía`/ru `Гарпия` çevirmiştir (`HarpyChest/Dresser` kayıtları da bu karara bağlanacaktır).

### #4 — MAJOR — Kısaltılmış dost adı (Trüf)

| EN | TR | Fix |
|---|---|---|
| `Truffle` | `Trüf` | `Yermantarı` |

Ad kesilmiş gibidir ve sözlük `Tuffle→Yermantarı` der; dost NPC adı sözlüğe çekilmelidir.

## MINOR

### #5 — MINOR — Çevrilmemiş espri adı (Eyezor)

| EN | TR | Fix |
|---|---|---|
| `Eyezor` | `Eyezor` | `Gözor` |

de `Schandfleck`/fr `Zombolaire`/es `Ojozor`/ru `Глазор` göz+jilet esprisini uyarlamışken TR İngilizce bırakmıştır.

### #6 — MINOR — Çevrilmemiş kelime oyunu (Herpling/Derpling)

| EN | TR | Fix |
|---|---|---|
| `Herpling` | `Herpling` | `Sersemçik` (karar tablosuna bakınız) |
| `Derpling` | `Derpling` | `Şapşal` (karar tablosuna bakınız) |

fr (`Bêta`/`Benêt`), es (`Lerduno`/`Tontuno`), ru (`Дурализень`) çevirmiştir; de bırakmıştır — iki yön de savunulabilir, sözlükte açık karar verilecek.

### #7 — MINOR — Çevrilmemiş tür adları (Wyvern/Lihzahrd)

| EN | TR | Fix |
|---|---|---|
| `Wyvern` | `Wyvern` | `Viverna` (karar tablosuna bakınız) |
| `Lihzahrd` | `Lihzahrd` | `Lizahrd` (karar tablosuna bakınız) |

de `Lindwurm`/fr `Vouivre`/es `Guiverno`/ru `Виверна` yerelleştirmiştir; özel ad politikası sözlükte kayda bağlanacak.

### #8 — MINOR — Yanlış araç (“Daire”)

| EN | TR | Fix |
|---|---|---|
| `Martian Saucer` | `Marslı Daire` | `Marslı Uçan Dairesi` |

`Daire` geometrik şekildir, UFO karşılığı `Uçan Daire` deyimidir; de `Marsianer-UFO`/fr `Soucoupe martienne` bunu doğrular.

### #9 — MINOR — Çevrilmemiş ad (Cyborg)

| EN | TR | Fix |
|---|---|---|
| `Cyborg` | `Cyborg` | `Siborg` |

es `Ciborg`/ru `Киборг` çeviriyazmış, de/fr bırakmıştır; düşük görünürlüklüdür, iki yön de kabul edilir ama karar kayda bağlanacak.

## Terminoloji Karar Tablosu

| Terim | Çeviriler (grep) | Karar |
|---|---|---|
| Everscream | `Yaprakçığlığı` (#1) | Karar: `Sonsuzçığlık`. |
| Dryad | `Dryad` (#2) | Karar: `Driyad` — sözlüğe işlenecek. |
| Harpy | `Harpy` (#3) | Karar: `Harpi` — sözlükteki `?` bu kararla doldurulacak. |
| Truffle | `Trüf` (#4) | Karar: `Yermantarı` (sözlük `Tuffle` kaydı genişletilecek). |
| Eyezor | `Eyezor` (#5) | Karar: `Gözor`. |
| Herpling / Derpling | EN (#6) | Karar: sözlükte açık hüküm (`Sersemçik`/`Şapşal` önerisi veya muafiyet). |
| Wyvern / Lihzahrd | EN (#7) | Karar: özel ad politikası sözlüğe yazılacak (`Viverna`/`Lizahrd` önerisi). |
| Cyborg | `Cyborg` (#9) | Karar: `Siborg` önerisi, düşük öncelik. |
| Slime / Goblin / Cultist | `Balçık` / `Cincüce` / `Tarikatçı` (tutarlı) | Karar: korunacak. |
| Efsanevi adlar (Golem/Medusa/Paladin/Yeti/Krampus/Plantera/Lamia/Tim/Fritz) | EN (doğru) | Karar: İngilizce kalır, düzeltilmeyecek. |

## Yerelleştirme Notları

- Dosya ~%93 çevrilidir; balçık ve dost NPC adlandırması örnek düzeydedir.
- Kalan iş: #1–#4 düzeltmeleri, sözlük güncellemesi (`Harpi`, `Driyad`, özel ad politikası, `Martian Saucer→Marslı Uçan Dairesi`).
