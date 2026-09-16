# QA Raporu — `en-US.Legacy.json` (Klasik Menü / Arayüz / Diyalog)

- EN kaynak: `İngilizce Dosyalar/Terraria.Localization.Content.en-US.Legacy.json`
- TR çeviri: `TerrariaTurkce/Content/Localization/en-US.Legacy.json`
- Sözlük: `Terimler.md`
- Kapsam: 1216 kayıt; eksik/fazla kayıt yok, `{...}` yer tutucu uyumsuzluğu yok. 81 özdeş kaydın tamamı doğrudur (simgeler `←/→`, klavye düzeni `abc / ABC / !@#`, sohbet komutları `/playing//players//roll`, `{$ItemName.*}` göndermeleri). `LegacyDialog` (392), `LegacyInterface` (126), `LegacyWorldGen` (94) altlarında özdeş kayıt yoktur; örneklemde ton, emir kipleri ve espriler korunmuştur (`Toprak bloklarıma bi' bak`).

## Detaylı Hata Listesi

## MINOR

### #1 — MINOR — Düşen port yuvası

| EN | TR | Fix |
|---|---|---|
| `Running on port ` | `Portta çalışıyor` | `Şu portta çalışıyor: ` |

Kaynak sondaki boşlukla port numarasının ekleneceğini gösterir; mevcut çeviri birleştirme noktasını düşürmüştür (çok oyunculu barındırma ekranında denetlenecek — Bağlam Gerekli).

### #2 — MINOR — Tutarsız yuva sözcüğü

| EN | TR | Fix |
|---|---|---|
| `Equipped in social slot` | `Sosyal kısmında kuşanıldı` | `Sosyal yuvada kuşanıldı` |

Oyun başka yerde `yuva` kullanırken (`Görünüş yuvası`) burada `kısım` yazılmış, tutarlılık bozulmuştur.

## STYLE

### #3 — STYLE — Tuş adı (bilinçli bırakma, işlemsiz)

| EN | TR | Fix |
|---|---|---|
| `Backspace` | `Backspace` | Değişiklik yok (isteğe bağlı: `Geri Al (Backspace)`) |

de (`Rücktaste`), fr (`Retour arrière`) çevirmiş olsa da TR klavyelerde `Backspace` yazdığı için bırakılması doğrudur; yalnızca tamlık için listelenmiştir.

## Terminoloji Karar Tablosu

| Terim | Çeviriler (grep) | Karar |
|---|---|---|
| Corruption / Crimson (sıfat) | `Yozlaşma` / `Kızıl` (LegacyMisc.101–102) | Karar: mevcut kullanım örnek niteliğinde doğrudur (ad `Kızıllık/Yozlaşma`, sıfat `Kızıl/Yoz`); korunacak (Bkz. `QA_en-US.Game.md`). |
| Goblin | `Cincüce` (tutarlı, örn. `cincüce ordusu`) | Karar: korunacak. |
| Dresser / Chest | `Şifonyer` / `Sandık` (tutarlı) | Karar: korunacak. |
| slot | `yuva` (çoğunluk) / `kısım` (#2) | Karar: `yuva` — #2 düzeltilecek, sözlüğe `slot→yuva` işlenecek. |

## Yerelleştirme Notları

- Bu dosya projenin en iyi çevrilmiş dosyasıdır; toplu boşluk yoktur, yer tutucu bütünlüğü tamdır.
- Kalan iş yoktur (#1 yalnızca oyun içi birleştirme denetimi ister); sözlüğe `slot→yuva` kaydı önerilir.
