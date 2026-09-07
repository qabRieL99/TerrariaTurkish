# Terraria Türkçe Yerelleştirme QA Raporu

**Kapsam:** `TerrariaTurkce/Content/Localization/` (TR) ↔ `İngilizce Dosyalar/` (EN) — 7 dosya çifti: `Game`, `Items`, `en-US` (çekirdek UI), `Legacy`, `NPCs`, `Projectiles`, `Town`.
**Sözlük:** `Terimler.md` bağlayıcı kabul edildi; sözlükle çelişen çeviriler raporlandı.
**Yöntem:** JSON anahtarları birebir karşılaştırıldı; yer tutucular (`{0}`, `{PlayerName}`, `{InputTrigger_*}`, `{$Legacy*}`, `\n`), etiketler, sayılar/birimler ve sözlük terimleri denetlendi. Kaynak değer okunmadan anahtar adından hüküm verilmedi.
**Rapor dili:** Türkçe (EN alıntılar dışında). Her hata bloğu: başlıkta önem + kısa başlık, üç sütunlu EN/TR/Fix tablosu ve tek cümlelik problem+gerekçe içerir. Her kayıt kendi satırındadır.

---

# 1. Ayrıntılı Hata Listesi

## 1.1 CRITICAL

### #1 — CRITICAL — Yüzde formatı bozuk: Dryad dünya durumu (Town.DryadSpecialText)
| EN | TR | Fix |
|---|---|---|
| `{0} is {1}% hallow, {2}% corrupt, and {3}% crimson.` | `{0} dünyası, %{1} kutsallık, %{2} yozlaşma ve %{3} kızıllık içeriyor.` | `{0}: %{1} kutsallık, %{2} yozlaşma ve %{3} kızıllık.` |
| `{0} is {1}% hallow, {2}% corrupt.` | `%{1} kutsallık, %{2} yozlaşma` | `%{1} kutsallık, %{2} yozlaşma` |

Problem + gerekçe tek cümle: EN `{1}%` (sayıdan sonra yüzde) iken TR `%{1}` yazılmış ve bu hata All/HallowCorrupt/HallowCrimson/CorruptCrimson/Corrupt/Crimson/Hallow olmak üzere 7 anahtarda tekrarlanıyor.

### #2 — CRITICAL — Undead tersine çevrilmiş: ölümsüz ≠ ölü (NPCs)
| EN | TR | Fix |
|---|---|---|
| `Undead Viking` | `Ölümsüz Viking` | `Ölü Viking` |
| `Undead Miner` | `Ölümsüz Madenci` | `Ölü Madenci` |

Problem + gerekçe tek cümle: Undead (hortlak/ölmüş) `Ölümsüz` (immortal) yapılmış, anlam tamamen tersine dönüyor.

### #3 — CRITICAL — Princess subjects denek yapılmış (Town.PrincessChatter)
| EN | TR | Fix |
|---|---|---|
| `I am so fabulously grateful for my subjects!` | `Deneklerim için inanılmaz derecede minnettarım!` | `Tebaama inanılmaz derecede minnettarım!` |

Problem + gerekçe tek cümle: Subjects (tebaa) `Denek` (deney kobayı) yapılmış, prenses sesi ve anlam bozuluyor.

### #4 — CRITICAL — Stinkbug kaba ve tutarsız (Town.TownNPCHousingFailureReasons)
| EN | TR | Fix |
|---|---|---|
| `This room is infested by a stinkbug!` | `Bu odada bir osuruk böceği istilası var!` | `Bu oda bir süne istilasına uğramış!` |

Problem + gerekçe tek cümle: NPC adı `Süne` iken burada kaba `osuruk böceği` kullanılmış, hem üslup hem tutarlılık bozuluyor.

### #5 — CRITICAL — Anchor demir sanılmış (Projectiles.Anchor)
| EN | TR | Fix |
|---|---|---|
| `Anchor` | `Demir` | `Çapa` |

Problem + gerekçe tek cümle: Gemi çapası/silah olan Anchor `Demir` (iron madeni) sanılmış, eşya tanınmaz hale gelmiş.

### #6 — CRITICAL — Walker aylak sanılmış (NPCs.MartianWalker)
| EN | TR | Fix |
|---|---|---|
| `Martian Walker` | `Marslı Aylak` | `Marslı Yürüyücü` |

Problem + gerekçe tek cümle: Yürüyen mech anlamındaki Walker `Aylak` (avare) ile karıştırılmış, false-friend hatası var.

### #7 — CRITICAL — Blood Shot kırmızı sanılmış (Projectiles)
| EN | TR | Fix |
|---|---|---|
| `Blood Shot` | `Kan Kırmızı` | `Kan Atışı` |
| `Blood Nautilus Shot` | `Kan Kırmızı` | `Kan Nautilus Atışı` |

Problem + gerekçe tek cümle: Shot (mermi/atış) renk olan `Kırmızı` sanılmış, hasar veren mermi renk adına dönüşmüş.

### #8 — CRITICAL — Daybloom bitki adı yanlış (Items.ItemName.DaybloomStaff)
| EN | TR | Fix |
|---|---|---|
| `Daybloom Staff` | `Günçiçeği Asası` | `Gündüzparlayan Asası` |

Problem + gerekçe tek cümle: Sözlük `Daybloom=Gündüzparlayan` iken `Günçiçeği` yazılmış ve dosya içi doğru kullanımla çelişiyor.

### #9 — CRITICAL — Moon Lord sözlük dışı (Items + Legacy)
| EN | TR | Fix |
|---|---|---|
| `Treasure Bag (Moon Lord)` | `Hazine Çantası (Ay Lordu)` | `Hazine Çantası (Ay Efendisi)` |
| `The Moon Lord has awoken!` | `Ay Lordu uyandı!` | `Ay Efendisi uyandı!` |

Problem + gerekçe tek cümle: Sözlük `Moon Lord=Ay Efendisi` iken `Ay Lordu` kullanılmış, boss adı dosya içinde çelişiyor.

### #10 — CRITICAL — Deathweed sözlük dışı (Items)
| EN | TR | Fix |
|---|---|---|
| `Hanging Corrupt Deathweed` | `Asma Yoz Ölümotu` | `Asma Yoz Ölükot` |
| `Hanging Crimson Deathweed` | `Asma Kızıl Ölümotu` | `Asma Kızıl Ölükot` |

Problem + gerekçe tek cümle: Sözlük `Deathweed=Ölükot` iken `Ölümotu` yazılmış, kritik terim hatası var.

### #11 — CRITICAL — RopeCoil yazım hatası (Items.ItemTooltip.RopeCoil)
| EN | TR | Fix |
|---|---|---|
| `Throw to create a climbable line of rope` | `Tırnılabilir bir halat fırlatmak için fırlat` | `Tırmanılabilir bir halat sırası oluşturmak için fırlat` |

Problem + gerekçe tek cümle: `Tırnılabilir` Türkçe bir kelime değildir ve tekrarlı anlatım `climbable` anlamını kaybettiriyor.

### #12 — CRITICAL — Housing sözlük ihlali (UI.NPCHousing)
| EN | TR | Fix |
|---|---|---|
| `Housing` | `Yerleşim` | `Konaklama` |

Problem + gerekçe tek cümle: Sözlük `Housing=Konaklama` derken en görünür konut sekmesinde `Yerleşim` yazıyor.

### #13 — CRITICAL — Banner üçe bölünmüş: Bayrak/Afiş (UI)
| EN | TR | Fix |
|---|---|---|
| `Banners Window` | `Bayrak Penceresi` | `Sancak Penceresi` |
| `Banners` | `Bayraklar` | `Sancaklar` |
| `Claim Banners` | `Afişleri Al` | `Sancakları Al` |

Problem + gerekçe tek cümle: Sözlük `Banner=Sancak` iken `Bayrak` ve `Afiş` kullanılmış, üçlü tutarlılık oyuncuyu yanıltıyor.

### #14 — CRITICAL — Kaydet butonu isimle yazılmış (UI.Save)
| EN | TR | Fix |
|---|---|---|
| `Save` | `Kayıt` | `Kaydet` |

Problem + gerekçe tek cümle: Buton eylem bildirmeli, isim olan `Kayıt` tıklanabilirliği zayıflatıyor.

### #15 — CRITICAL — Uydurma kelime Gözdele (UI + Legacy)
| EN | TR | Fix |
|---|---|---|
| `Favorite` | `Gözdele` | `Favori` |
| `Unfavorite` | `Gözdeden Çıkar` | `Favoriden Çıkar` |

Problem + gerekçe tek cümle: `Gözdele` standart Türkçe değildir ve üç anahtara yayılmış, yerleşik `Favori` kullanılmalı.

### #16 — CRITICAL — Birim çevrilmiş değer çevrilmemiş: mph→km/sa (GameUI)
| EN | TR | Fix |
|---|---|---|
| ` {0} mph` | `{0} km/sa` | `{0} mph` |
| ` ({0} mph W)` | ` ({0} km/sa B)` | ` ({0} mph B)` |

Problem + gerekçe tek cümle: Oyun sayısal değeri çevirmeden gönderiyor, birimi değiştirmek hızı yanlış gösteriyor.

### #17 — CRITICAL — Pylon Direk olmuş (Net.*Pylon*)
| EN | TR | Fix |
|---|---|---|
| `You are not close enough to a pylon to teleport with the pylon network` | `Direk ağına ışınlanmak için direğe yeterince yakın değilsin` | `Pilon ağıyla ışınlanmak için bir pilona yeterince yakın değilsin` |

Problem + gerekçe tek cümle: Işınlanma yapısı olan Pylon `Direk` (sıradan sopa) yapılmış, 5 pylon anahtarında aynı hata var.

### #18 — CRITICAL — Parti duyurusu yazım hatası (LegacyMisc.97/98)
| EN | TR | Fix |
|---|---|---|
| `is throwing a party` | `parti yapıyora` | `parti veriyor` |

Problem + gerekçe tek cümle: Sondaki fazla `a` (`yapıyora`) oyuncuya gösterilen duyuruyu bozuyor.

### #19 — CRITICAL — Buff Takviye yapılmış (LegacyMenu.83/157)
| EN | TR | Fix |
|---|---|---|
| `Quick Buff` | `Hızlı Takviye` | `Hızlı Güçlendirme` |

Problem + gerekçe tek cümle: Sözlük `Buff=Güçlendirme` derken `Takviye` kullanılmış, tutarlılık bozuluyor.

### #20 — CRITICAL — Yazım hataları: iksir/kullanarak (LegacyDialog)
| EN | TR | Fix |
|---|---|---|
| `Better buy some more healing potions.` | `Daha fazla iyileştirme ikisiri alsan iyi edersin.` | `Daha fazla iyileştirme iksiri alsan iyi edersin.` |
| `You can create a furnace out of torches, wood, and stone.` | `Meşale, odun ve taş kullanrak bir ocak işleyebilirsin.` | `Meşale, odun ve taş kullanarak bir ocak işleyebilirsin.` |

Problem + gerekçe tek cümle: En çok görülen tüccar/öğretici cümlelerde `ikisiri` ve `kullanrak` yazım hataları güveni zedeliyor.

### #21 — CRITICAL — Ammo ikiye bölünmüş (LegacyInterface.27)
| EN | TR | Fix |
|---|---|---|
| `Ammo` | `Kurşun` | `Cephane` |

Problem + gerekçe tek cümle: Sözlük `Ammo=Cephane` iken arayüzde `Kurşun` yazılmış, aynı kavram ikiye bölünmüş.

### #22 — CRITICAL — Anonsa eklenen ev anlamı (Game.Announcement)
| EN | TR | Fix |
|---|---|---|
| `{0} has arrived!` | `{0} evine vardı!` | `{0} geldi!` |

Problem + gerekçe tek cümle: Kaynakta `ev` yoktur ve bu anons boss/etkinlik gelişini bildiriyor, eve varışı değil.

## 1.2 MAJOR

### #23 — MAJOR — Harita nesneleri yanlış: Vase/Chandelier (Game.MapObject)
| EN | TR | Fix |
|---|---|---|
| `Vase` | `Saksı` | `Vazo` |
| `Chandelier` | `Şamdan` | `Avize` |

Problem + gerekçe tek cümle: Saksı çiçeklik, şamdan mumluktur; vazo ve tavan avizesi olan kaynak nesneler yanlış gösteriliyor.

### #24 — MAJOR — Nebula Bulut yapılmış (Game.BuffName, 9 kayıt + Bestiary)
| EN | TR | Fix |
|---|---|---|
| `Damage Nebula` | `Hasar Bulutu` | `Hasar Bulutsusu` |
| `Life Nebula` | `Yaşam Bulutu` | `Yaşam Bulutsusu` |
| `Mana Nebula` | `Sihir Bulutu` | `Sihir Bulutsusu` |
| `A purple lunar seal ... known as 'nebula'.` | `... 'nebula'yı temsil eder.` | `... 'bulutsu'yu temsil eder.` |

Problem + gerekçe tek cümle: Sözlük `Nebula=Bulutsu` ve `NebulaPillar=Bulutsu Sütunu` iken `Bulut` ve ham `nebula` kullanılmış.

### #25 — MAJOR — Vortex/Girdap ve Distorted (Game)
| EN | TR | Fix |
|---|---|---|
| `Distorted` | `Oransız` | `Çarpık` |
| `A ... void known as 'vortex'.` | `... 'vorteks' ...` | `... 'girdap' ...` |

Problem + gerekçe tek cümle: `Oransız` distorted karşılığı olamaz ve sözlük `Vortex=Girdap` iken `vorteks` bırakılmış.

### #26 — MAJOR — Eyeball Spring sözlük ihlali (Game + Projectiles)
| EN | TR | Fix |
|---|---|---|
| `Eyeball Spring` | `Zıplayan Göz` | `Göz Pınarı` |
| `An eyeball spring is following you` | `Bir göz yayı seni takip ediyor` | `Bir Göz Pınarı seni takip ediyor` |
| `Eye Spring` | `Zıplayan Göz` | `Göz Pınarı` |

Problem + gerekçe tek cümle: Sözlük `Eyeball Spring=Göz Pınarı` iken `Zıplayan Göz` ve `göz yayı` (helezon) kullanılmış, kendi içinde de çelişiyor.

### #27 — MAJOR — Minion hizmetkâr yapılmış (Game.Bestiary, 3 kayıt)
| EN | TR | Fix |
|---|---|---|
| `Minions from Etheria ...` | `Etheria'dan gelen hizmetkârlar...` | `Etheria'dan gelen yardakçılar...` |
| `... its minions greatly empowered.` | `... hizmetkârları büyük güç kazandı.` | `... yardakçıları büyük güç kazandı.` |
| `... powerful minions of light.` | `... güçlü ışık hizmetkârlarıyla ...` | `... güçlü ışık yardakçılarıyla ...` |

Problem + gerekçe tek cümle: Sözlük `Minion=Yardakçı` ve dosya içi çoğunluk öyleyken üç kayıtta `hizmetkâr` yazılmış.

### #28 — MAJOR — Mekanik tersine çevirmeler: Calm/StardustMinion/FairyQueen (Game)
| EN | TR | Fix |
|---|---|---|
| `Decreased enemy spawn rate` | `Azaltılmış düşman saldırganlığı` | `Azaltılmış düşman ortaya çıkma oranı` |
| `being eaten by cells` | `Hücreler tarafından yenilecekler` | `Hücreler tarafından yeniyorsun` |
| `The light of the fair folk illuminates all` | `Adil halkın ışığı her şeyi aydınlatır` | `Peri halkının ışığı her şeyi aydınlatır` |

Problem + gerekçe tek cümle: Spawn rate saldırganlık değildir, özne üçüncü çoğula dönmüş ve `fair folk` (periler) `adil halk` yapılmış.

### #29 — MAJOR — BuffDescription terim hataları: ObsidianSkin/ManaSickness/DeadCells/Glommer (Game)
| EN | TR | Fix |
|---|---|---|
| `Immune to lava` | `Lava bağışıklık` | `Lav bağışıklığı` |
| `Cannot consume anymore mana healing items` | `Artık mana iyileştirme eşyası tüketemezsin` | `Artık sihir yenileme eşyası tüketemezsin` |
| `Fresh buffs last longer` | `Yeni ürünler daha uzun süre dayanır` | `Yeni güçlendirmeler daha uzun sürer` |
| `It's fuzzy! And slimy...` | `Bulanık! Ve sümüksü...` | `Tüylü! Ve sümüksü...` |

Problem + gerekçe tek cümle: `Lava` İngilizce bırakılmış, sözlük `Mana=Sihir` ve `Buff=Güçlendirme` iken `mana` ve `ürün` yazılmış, `fuzzy` (tüylü) `bulanık` (blurry) yapılmış.

### #30 — MAJOR — Yükleme ipuçları oynanış yanlışları (Game.LoadingTips)
| EN | TR | Fix |
|---|---|---|
| `Water will break your fall.` | `Su düşüş hızını azaltır.` | `Suya düşersen düşüş hasarı almazsın.` |
| `Pirates are so unpredictable. First they invade your world, and then they move into your houses!` | `... sonra evlerine taşınırlar!` | `... sonra senin evlerine taşınırlar!` |
| `The Housing section of the Equipment Menu ...` | `Donanım Menüsü'nün Konaklama bölümü ...` | `Ekipman Menüsü'nün Konaklama bölümü ...` |

Problem + gerekçe tek cümle: Su düşüş hasarını engeller (hızı değil), `your houses` (senin evlerin) kendi evleri yapılmış ve Equipment `Donanım` (hardware) değil `Ekipman` olmalı.

### #31 — MAJOR — Biyom adları ve sözlük adları (Game)
| EN | TR | Fix |
|---|---|---|
| `'The Hallow', serves as a cure ...` | `'Kutsal', aşırı coşkulu ...` | `'Kutsallık', aşırı coşkulu ...` |
| `A curious deviation ... Tough 'mycanoids' defend the area.` | `Doğanın merak uyandıran bir sapması: ... dev mantarlar.` | `Doğanın merak uyandıran bir sapması: ... dev mantarlar. Sert mantarımsı yaratıklar bölgeyi savunur.` |
| `The Tavernkeep is a guest ...` | `Hancı, Etheria denen ...` | `Gazinocu, Etheria denen ...` |
| `You can use ... Pearlstone to make Hallow spread.` | `... İncitaş kullanabilirsin.` | `... Aktaş kullanabilirsin.` |

Problem + gerekçe tek cümle: Biyom adı `Kutsallık` iken `Kutsal` yazılmış, mycanoid cümlesi düşürülmüş, sözlük `Tavernkeep=Gazinocu` ve `Pearlstone=Aktaş` iken `Hancı` ve `İncitaş` yazılmış.

### #32 — MAJOR — Bar sistematik Külçe yazılmış (Items)
| EN | TR | Fix |
|---|---|---|
| `Bar` | `Külçe` | `Kalıp` |
| `Adamantite Bar` | `Adamantit Külçe` | `Adamantit Kalıp` |
| `Luminite Bar` | `Aysalit Külçe` | `Aysalit Kalıp` |

Problem + gerekçe tek cümle: Sözlük `Bar=Kalıp` iken sistematik `Külçe` kullanılmış, standart sapma var.

### #33 — MAJOR — Minecart Kamyonu yazılmış (Items + Legacy)
| EN | TR | Fix |
|---|---|---|
| `Minecart` | `Maden Kamyonu` | `Maden Arabası` |
| `Amber Minecart` | `Kehribar Maden Kamyonu` | `Kehribar Maden Arabası` |

Problem + gerekçe tek cümle: Sözlük `Minecart=Maden Arabası` iken 30+ kayıtta `Kamyonu` yazılmış, modern araç çağrışımı yapıyor.

### #34 — MAJOR — PickaxeAxe espri-referansı yanlış eşyaya bağlı (Items)
| EN | TR | Fix |
|---|---|---|
| `'Not to be confused with a hamdrill'` | `'Matbaltta karıştırmayasın'` | `'Hamdrill ile karıştırmayasın'` |

Problem + gerekçe tek cümle: `hamdrill` ayrı eşyayken `Matbalt` (Drax karşılığı) yazılmış, referans ters bağlanmış.

### #35 — MAJOR — Sentry/Crafting/Robe/Adept çelişkileri (Items)
| EN | TR | Fix |
|---|---|---|
| `Summons a sentry` | `Bir bekçi çağırır` | `Bir nöbetçi çağırır` |
| `Used for basic crafting` | `Temel üretim için kullanılır` | `Temel işleme için kullanılır` |
| `Amethyst Robe` | `Mortaş Biniş` | `Mortaş Cübbe` |
| `Adept` | `Uzman` | `Usta` |

Problem + gerekçe tek cümle: Sözlük `Sentry=Nöbetçi`, `Crafting=İşleme` iken `bekçi` ve `üretim` yazılmış, `Biniş` Mount ile çakışıyor ve `Adept=Uzman` sözlükteki `Expert=Uzman` ile çakışıyor.

### #36 — MAJOR — Mekanik anlatımı yanlış: Crystal Assassin (Items)
| EN | TR | Fix |
|---|---|---|
| `5% increased damage\n10% chance to save ammo` | `%5 artırılmış hasar\nCephane tüketimini %10 azaltır` | `%5 artırılmış hasar\n%10 olasılıkla cephane tüketmez` |

Problem + gerekçe tek cümle: `chance to save ammo` dosyanın 20+ kaydında `olasılıkla tüketmez` iken burada `tüketimi azaltır` (farklı mekanik) yazılmış.

### #37 — MAJOR — Doğum Yeri/Crafting/Orta/Hover/Emote/Kick (UI)
| EN | TR | Fix |
|---|---|---|
| `Spawn` | `Doğum Yeri` | `Doğuş Noktası` |
| `Crafting Window` | `Üretim Penceresi` | `İşleme Penceresi` |
| `Mediumcore` | `Orta` | `Orta Zorluk` |
| `Hover Text Boxes On` | `Yüzen Metin Kutuları: Açık` | `Açılır Metin Kutuları: Açık` |
| `Open Emotes Window` | `Duygu Penceresini Aç` | `İfade Penceresini Aç` |
| `Kick` | `Kros` | `Bas Davul` |

Problem + gerekçe tek cümle: `Doğum` biyolojik çağrışım yapıyor, sözlük `Crafting=İşleme` iken `Üretim` yazılmış, `Orta` ölüm cezasını dünyayla karıştırıyor, Hover süzülme değil üzerine gelme ve Emote duygu değil ifadedir, `Kros` davulda anlamsızdır.

### #38 — MAJOR — Loot/Ganimet çakışması ve hile uyarıları yarı İngilizce (UI)
| EN | TR | Fix |
|---|---|---|
| `(Far Greater Difficulty & Loot)` | `(Çok Daha Fazla Zorluk ve Ganimet)` | `(Çok Daha Fazla Zorluk ve Yağma)` |
| `Cheating attempt detected: Add tile spam` | `Hile girişimi algılandı: Add tile spam` | `Hile girişimi algılandı: Döşeme ekleme spamı` |

Problem + gerekçe tek cümle: Sözlük `Trophy=Ganimet` iken `Loot` da `Ganimet` yapılmış ve hile uyarılarının yarısı çevrilmemiş (`Tile=Döşeme` uygulanmamış).

### #39 — MAJOR — knockback yön hatası (LegacyTooltip.14-22)
| EN | TR | Fix |
|---|---|---|
| `No knockback / Strong knockback / % knockback` | `Geri tepme yok / Güçlü geri tepme / % geri tepme` | `Savurma yok / Güçlü savurma / % savurma` |

Problem + gerekçe tek cümle: `Geri tepme` recoil demektir, düşmanı savurma anlamındaki knockback karşılığı `Savurma` olmalı.

### #40 — MAJOR — Helmet/Pirate/LightPet/Ecto/Lunar (Legacy)
| EN | TR | Fix |
|---|---|---|
| `Helmet` | `Miğfer` | `Kask` |
| `Pirate Invasion` | `Korsan Akını` | `Korsan Baskını` |
| `Light Pet` | `Işık Tutucu` | `Işık Evcil Hayvanı` |
| `Ecto Mist` | `Koyu Sis` | `Ekto Sisi` |
| `Lunar Fragment` | `Aysal Parçacık` | `Göksel Parçacık` |

Problem + gerekçe tek cümle: Sözlük `Helmet=Kask`, `Pirate Invasion=Korsan Baskını`, `Lunar=Göksel` iken `Miğfer`, `Akın` ve uydurma `Aysal` yazılmış, `Ecto` özel ismi `Koyu` yapılmış.

### #41 — MAJOR — Elemental Saf yapılmış (NPCs, 4 kayıt)
| EN | TR | Fix |
|---|---|---|
| `Chaos Elemental` | `Saf Kaos` | `Kaos Elementali` |
| `Ice Elemental` | `Saf Buz` | `Buz Elementali` |
| `Sand Elemental` | `Saf Kum` | `Kum Elementali` |

Problem + gerekçe tek cümle: Element yaratığı olan Elemental `Saf` (pure) sanılmış, dört girdide sistematik hata var.

### #42 — MAJOR — Snatcher/Digs/Windy esprisi/Critters (Town)
| EN | TR | Fix |
|---|---|---|
| `Snatcher` | `Kapkaççı` | `Kapıcı Çiçek` |
| `These digs are great - loving the personal space.` | `Bu kazılar harika - kişisel alanı seviyorum.` | `Bu ev harika - kişisel alanı seviyorum.` |
| `Keep your talismans close... if you wind some, you lose some.` | `Tılsımlarını yakında tut... eğer biraz dolaşırsan, biraz kaybedersin.` | `Tılsımların yakınında olsun... kazanırsın da rüzgârda kaybedersin de.` |
| `I collected critters like you once...` | `Bir zamanlar senin gibi böcekler toplardım...` | `Bir zamanlar senin gibi yaratıklar toplardım...` |

Problem + gerekçe tek cümle: Orman bitkisi yankesici yapılmış, argo `digs` (ev) kazı sanılmış, win/wind kelime oyunu kaybolmuş ve critters (yaratıklar) böceklere daraltılmış.

### #43 — MAJOR — Aura Hava yapılmış + Goblin çevrilmemiş (Projectiles/NPCs)
| EN | TR | Fix |
|---|---|---|
| `Lightning Aura` | `Parlak Hava` | `Yıldırım Aurası` |
| `Hemogoblin Shark` | `Hemogoblin Köpekbalığı` | `Hemokincüce Köpekbalığı` |
| `Daybloom Pellet` | `Gündoğumu Peleti` | `Gündüzparlayan Peleti` |

Problem + gerekçe tek cümle: Büyü alanı olan Aura `Hava` (weather) yapılmış, sözlük `Goblin=Cincüce` ve `Daybloom=Gündüzparlayan` iken İngilizce ve `Gündoğumu` bırakılmış.

### #44 — MAJOR — Spazmatism özel ismi çevrilmiş (NPCs)
| EN | TR | Fix |
|---|---|---|
| `Spazmatism` | `Spazmatizm` | `Spazmatism` |

Problem + gerekçe tek cümle: Boss parçası özel isimdir ve `Retinazer` korunmuşken Türkçeleştirme tutarlılığı bozuyor.

## 1.3 MINOR

### #45 — MINOR — Balista Mancınık yapılmış (Game)
| EN | TR | Fix |
|---|---|---|
| `Ballista Panic!` | `Mancınık Ürküntüsü!` | `Balista Ürküntüsü!` |
| `Your ballistas rapidly shoot in panic!` | `Mancınıkların ürküntü içinde ateş ediyor!` | `Balistaların panik içinde hızla ateş ediyor!` |

Problem + gerekçe tek cümle: ArmorSetBonus beş kez `Balista` yazarken burada farklı silah olan `Mancınık` kullanılmış ve `rapidly` (hızla) düşürülmüş.

### #46 — MINOR — Sözlük yazımları: Alevpatlağı/Platin (Game)
| EN | TR | Fix |
|---|---|---|
| `Greatly enhances Flameburst effectiveness` | `Alev Patlaması verimliliğini ...` | `Alevpatlağı verimliliğini ...` |
| `Platinum` | `Platinyum` | `Platin` |

Problem + gerekçe tek cümle: Sözlük bitişik `Alevpatlağı` ve `Platin` verirken ayrık ve `Platinyum` yazılmış.

### #47 — MINOR — Eksik yönelme eki: bas → düğmesine bas (Game)
| EN | TR | Fix |
|---|---|---|
| `Press {InputTrigger_SmartCursor} to switch between Cursor Modes.` | `... {InputTrigger_SmartCursor} bas.` | `... {InputTrigger_SmartCursor} düğmesine bas.` |

Problem + gerekçe tek cümle: `Bas` geçişsiz kalmış, GamePad karşılığı `düğmesine bas` diyor.

### #48 — MINOR — knockback/immunity imla ikiliği (Items)
| EN | TR | Fix |
|---|---|---|
| `Increases the knockback of your minions` | `Yardakçılarının geritepmesini artırır` | `Yardakçılarının geri tepmesini artırır` |
| `Grants immunity to knockback` | `Geritepmeye dayanıklılık sağlar` | `Geri tepmeye karşı bağışıklık sağlar` |
| `69% chance to save ammo` | `%69 cephane tasarrufu olasılığı` | `%69 olasılıkla cephane tüketmez` |

Problem + gerekçe tek cümle: `geritepme` bitişik yazılmışken çoğunluk `geri tepme` ayrı yazıyor ve `immunity=bağışıklık` iken `dayanıklılık` ile standart cephane cümlesinden sapılmış.

### #49 — MINOR — Classic/Dizilim/Davul/Balık Gücü (UI)
| EN | TR | Fix |
|---|---|---|
| `Classic` | `Sıradan` | `Klasik` |
| `Shared with other loadouts` | `Diğer dizilimle paylaşılıyor` | `Diğer dizilimlerle paylaşılıyor` |
| `Floor Tom` | `Floor Tom` | `Alt Tom` |
| `{0}% fishing power` | `{0}% balık tutma gücü` | `{0} Balık Tutma Gücü` |

Problem + gerekçe tek cümle: Aynı EN iki TR'ye bölünmüş, çoğul eki düşmüş, davul setinin yarısı İngilizce kalmış ve balık gücü büyük/küçük harfte çelişiyor.

### #50 — MINOR — Hotbar/Required objects (Legacy)
| EN | TR | Fix |
|---|---|---|
| `Hotbar unlocked / Hotbar locked` | `Çubuk kilidi açıldı / Çubuk kilitlendi` | `Kısayol Çubuğu kilidi açıldı / Kısayol Çubuğu kilitlendi` |
| `Required objects:` | `Gerekli maddeler:` | `Gerekli nesneler:` |

Problem + gerekçe tek cümle: Menüde `Kısayol Çubuğu` iken arayüzde `Çubuk` bırakılmış ve `Madde` kimyasal çağrışım yapıyor.

### #51 — MINOR — Cardinal/Bulb/Leaf/Goop/Derp (NPCs/Projectiles/Town)
| EN | TR | Fix |
|---|---|---|
| `Cardinal` | `Kardinal` | `Kardinal Kuşu` |
| `Fungi Bulb` | `Mantar Ampul` | `Mantar Yumrusu` |
| `Leaf Blade` | `Çim Bıçağı` | `Yaprak Bıçak` |
| `Alien Goop` | `Uzaylı Çapağı` | `Uzaylı Balçığı` |

Problem + gerekçe tek cümle: Kuş türü papaz gibi bırakılmış, bitki soğanı elektrik ampulü yapılmış, yaprak çimle karıştırılmış ve yapışkan sıvı göz çapağı yapılmış.

## 1.4 STYLE

### #52 — STYLE — Boya tabancası ve başlık düzeni (UI)
| EN | TR | Fix |
|---|---|---|
| `Paint sprayer on` | `Boya tabancası açık` | `Boya Püskürtücü: Açık` |

Problem + gerekçe tek cümle: Sprayer tabanca değil püskürtücüdür ve komşu anahtarlar `X: Açık` düzenindeyken küçük harfle kurulmuş.

### #53 — STYLE — Yem lazım konuşma dili (UI)
| EN | TR | Fix |
|---|---|---|
| `Requires bait to catch fish` | `Balık yakalamak için yem lazım` | `Balık yakalamak için yem gerekli` |

Problem + gerekçe tek cümle: `lazım` günlük konuşmadır, bilgi kutusu diline `gerekli` uyuyor.

### #54 — STYLE — Obsidian Skin/Sihir tüketimi yalın (Items)
| EN | TR | Fix |
|---|---|---|
| `Provides immunity to lava` | `Lava dayanıklılık sağlar` | `Lav bağışıklığı sağlar` |
| `10% reduced mana cost` | `Sihir tüketimini %10 azaltır` | `Sihir maliyetini %10 azaltır` |

Problem + gerekçe tek cümle: Yalın hal ekiyle kurulan cümle standart `Lav bağışıklığı` ve `sihir maliyeti` kalıplarından sapıyor.

### #55 — STYLE — Golfer/Nemo esprileri sönmüş (Town)
| EN | TR | Fix |
|---|---|---|
| `When I offer you to go clubbing, I don't mean downtown. I mean like, with a five iron?` | `Eline sopayı al dediğimde, sana temizlik yapmanı söylemiyorum...` | `Seni clubbing'e davet ettiğimde şehirde eğlenmekten bahsetmiyorum. Beş numaralı sopayla, golf sopasıyla diyorum?` |
| `...so that another one will show up looking frantically for him instead!` | `...ki bir başkası onu bulmak için yüzsün!` | `...ki bu sefer bir başkası onu çılgınca arasın!` |

Problem + gerekçe tek cümle: Golf sopası/gece kulübü esprisi uydurma `temizlik` ile kaybolmuş ve kayıp balık göndermesi düz `yüzsün` ile sönmüş.

---

# 2. Terminoloji Karar Tablosu

| Term | Translations (grep) | Decision |
|---|---|---|
| Housing | Konaklama (sözlük) / Yerleşim, Bu konut | **Konaklama**; durum mesajları `Burası ...` kalıbına çekilsin |
| Banner | Sancak (sözlük) / Bayrak, Afiş | **Sancak**; tüm UI ve buff adları buna çekilsin |
| Bar | Kalıp (sözlük) / Külçe | **Kalıp**; tüm *Bar ve RecipeGroup düzeltilecek |
| Minecart | Maden Arabası (sözlük) / Maden Kamyonu, Vagon, Kamyon | **Maden Arabası** |
| Buff / Debuff | Güçlendirme / Zayıflatma (sözlük) / Takviye, ürün | **Güçlendirme / Zayıflatma** |
| Mana | Sihir (sözlük) / mana | **Sihir** |
| Crafting | İşleme (sözlük) / Üretim | **İşleme** |
| Sentry | Nöbetçi (sözlük) / bekçi | **Nöbetçi** |
| Minion | Yardakçı (sözlük) / hizmetkâr | **Yardakçı** |
| Tile | Döşeme (sözlük) / tile (ham) | **Döşeme** |
| Trophy / Loot | Ganimet / Ganimet (çakışma) | **Trophy=Ganimet, Loot=Yağma** |
| Lunar | Göksel (sözlük) / Aysal | **Göksel**; `Aysal Tarikatçı` sözlük istisnası ayrıca gözden geçirilsin |
| Moon Lord | Ay Efendisi (sözlük) / Ay Lordu | **Ay Efendisi** |
| Nebula | Bulutsu (sözlük) / Bulut, nebula (ham) | **Bulutsu** |
| Vortex | Girdap (sözlük) / vorteks | **Girdap** |
| Pylon | Pilon / Direk | **Pilon** (özel isim) |
| Emote | İfade / Duygu | **İfade** |
| Save (buton) | Kaydet / Kayıt | **Kaydet** (fiil) |
| Favorite | Favori / Gözdele | **Favori** |
| Robe | Cübbe (çoğunluk) / Biniş (sözlük) | **Cübbe**; sözlük güncellensin (Biniş Mount ile çakışıyor) |
| Helmet | Kask (sözlük) / Miğfer | **Kask** |
| Ammo | Cephane (sözlük) / Kurşun | **Cephane** |
| knockback | Savurma (Legacy önerisi) / Geri tepme, geri tepme | **Savurma** (düşmanı savurma); recoil ayrıca not düşülsün |
| immunity | bağışıklık / dayanıklılık | **bağışıklık** |
| Daybloom | Gündüzparlayan (sözlük) / Günçiçeği, Gündoğumu | **Gündüzparlayan** |
| Deathweed | Ölükot (sözlük) / Ölümotu | **Ölükot** |
| Eyeball Spring | Göz Pınarı (sözlük) / Zıplayan Göz, göz yayı | **Göz Pınarı** |
| Pearlstone | Aktaş (sözlük) / İncitaş | **Aktaş** |
| Floating Island | Süzülen Ada (sözlük) / Yüzen Ada | **Süzülen Ada** |
| Goblin | Cincüce (sözlük) / Hemogoblin (ham) | **Cincüce** (Hemokincüce dahil) |
| Deerclops | Geyikgöz (sözlük) / Deerclops (ham) | **Geyikgöz** |
| Dye Trader | Boya Tüccarı (sözlük+çoğunluk) / Dye Trader (ham) | **Boya Tüccarı** |
| Tavernkeep | Gazinocu (sözlük) / Hancı | **Gazinocu** |
| Steampunker | Steampunkçı / Steampunker (ham) | **Steampunkçı** |
| Pirate Invasion | Korsan Baskını (sözlük) / Korsan Akını | **Korsan Baskını** |
| Glowstick | Parlakçubuk (sözlük) / Işık Çubuğu | **Parlakçubuk** |
| Flameburst | Alevpatlağı (sözlük) / Alev Patlaması | **Alevpatlağı** (bitişik) |
| Ballista | Balista / Mancınık | **Balista** (mancınık farklı silahtır) |
| Elemental | Elementali / Saf | **Elementali** (Saf Kaos/Buz/Kum silinsin) |
| Undead | Ölü / Ölümsüz | **Ölü** (Ölümsüz yasaklı) |
| Stinkbug | Süne / osuruk böceği | **Süne** |
| Aura | Aura / Hava | **Aura** |
| Adept (Prefix) | Usta / Uzman (Expert ile çakışıyor) | **Usta** (Expert=Uzman korunur) |
| Mythril | Mitril / Mitrili | **Mitril** |
| Diamond | Elmas / Pırlanta | **Elmas** (item adlarında tekleşsin) |
| Crimtane/Crimstone | Kızıltaş / Kızıl, Kızıl Taş | **Kızıltaş** (bitişik) |

---

# 3. Yerelleştirme Notları

**Biçim ve yer tutucular:** `{0}`, `{PlayerName}`, `{WorldName}`, `{InputTrigger_*}`, `{$Legacy*}` ve `\n` yapıları genel olarak korunmuş; kritik placeholder kaybı yok. Ancak Dryad `%` konumu (`{1}%` → `%{1}`) ve `their banner` gibi koşul düşürmeler (Keyboard.8) oyuncuya yanlış bilgi veriyor; yüzde ve koşul cümleleri tek tek gözden geçirilmeli.

**Sayı/birim/yön:** `mph` değeri çevrilmeden birim `km/sa` yapılmış (hız yanlış gösterilir); `ft` ham bırakılmış. Karar: oyun değeri dönüştürmüyorsa birim ham (`mph`, yön `B/D`) bırakılmalı veya merkezi birim politikası seçilip tüm dosyalara uygulanmalı. Tarih/saat/para birimi bu sette yok; para ve yüzde her zaman sayıdan sonra (`%50` değil `%{n}` dizimine dikkat) yazılmalı.

**Büyük/küçük harf ve noktalama:** UI başlıklar (`Balık Tutma Gücü` vs `balık tutma gücü`), davul seti (`Floor Tom` ham) ve `X: Açık` düzeninde ikilik var; başlık standardı seçilip (öneri: başlıklarda Her Kelime Büyük) toplu uygulanmalı. Türkçe kesme işareti (`Stilist'i`, `Dünya'na`) ve `ki/de` yazımları ayrıca taranmalı.

**Kültürel uyarlama:** `clubbing` (golf sopası/gece kulübü), `fair folk` (periler), `digs` (ev), `win some/lose some + wind` ve Nemo göndermesi gibi espriler düz çevrilmiş; anlam korunarak Türkçe espri karşılığı bulunmalı, uydurma `temizlik` gibi eklemelerden kaçınılmalı. `osuruk böceği` gibi kaba karşılıklar E10+ tonuna çekilmeli (`Süne`).

**Kalan işler:** 1) Sözlük güncelle: `Robe=Biniş→Cübbe`, `Master=Efendi` (Usta Modu bağlamında doğal değil, not düş), `Biome=Biyom?` kesinleştir, `Lunar=Göksel` iken `Aysal Tarikatçı` istisnası açıklanmalı. 2) Toplu değiştir: `Külçe→Kalıp`, `Kamyon→Araba`, `Bulut→Bulutsusu`, `hizmetkâr→yardakçı`, `Takviye→Güçlendirme`, `Gözdele→Favori`, `Direk→Pilon`. 3) Eksik cümleler tamamlanmalı: UndergroundMushroom mycanoid cümlesi, Keyboard.8 `sancaklarına` koşulu. 4) `sen/siz` çizgisi ve `Donanım→Ekipman` taraması yapılmalı.
