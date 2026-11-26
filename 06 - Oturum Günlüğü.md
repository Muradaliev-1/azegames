---
tags: [az-oyunlari, gunluk]
---
# Oturum Günlüğü

Yeni oturum en üste eklenir.

## 2026-11-27 · Oturum 1 devamı
- F-01 motoru tez reposunda bitti: `Round2`/`Match2` (R-20..R-28), tez commit `a0cd8b0`; 215 test geçti, `--only 2p` 11/11, 4 kişilik iz bit bit aynı (T-2P0). Tam mutasyon (238) tezde koşuyor.
- **Yerelde 2 kişilik oyun (kullanıcı: "Evet, yerelde kur"):** motor arka uca senkronlandı (`DOMINO_VERSION` a0cd8b0). Arka uç: `ws/{ad}?mode=2` bekleme olmadan tek insan + bot odası açar; zorunlu çekişler `drew` mesajıyla yayınlanır (kim, kaç taş; taşlar gizli); durumda `num_players`, `boneyard_size`; 2 kişide pas yokluğu gösterilmez (R-28). Bot 2 kişide `greedy` (arama ajanları 4 kişilik gözlem varsayıyor; güç ölçülmedi). Kayıt ayrı dosyada (`records/demo2p.jsonl`), başlangıç bazarı ve çekişlerle, `Round2` ile yeniden oynatılabilir. Arayüz: lobide "Bota karşı (2 kişi)", yalnız karşı koltuk, HUD'da bazar sayısı, çekiş bildirimi, büyüyen el taşları üst üste binerek sığar.
- Testler: arka uç `tests/run.py` 16 geçti (T-DM9, T-DM9b, T-DM9c yeni); arka uç mutasyonu 30 mutant (7 yeni "2p"); arayüz `vitest` 22 geçti (M-8..M-10, G-3, G-4 yeni), `tsc` temiz, uçtan uca 9/9 (4 kişilik, değişmedi) + E-8 (2 kişilik, telefon boyu, 2 tur) geçti. Tarayıcıda elle de denendi (masaüstü ve telefon boyu): çekiş, tur sonu, sonraki tur son taşı koyanla başlıyor.
- Commit/push yok: `domino-ai-backend` ve `domino-ai-frontend` repolarına ve canlıya dokunulmadı (değişiklikler yerel çalışma ağacında). Canlıya almak kullanıcı onayı ister.
- Açık: 2 kişilik bot (arama ajanını 2 kişiye uyarlamak tez kodunda iş: belief/search 4 koltuk varsayıyor); 2 kişilik arkadaş odası (iki insan) F-02 ile.

## 2026-11-26 · Oturum 1 (kuruluş)
**Hedef:** Tezden ayrı çok oyunlu uygulama projesini kurmak, domino ilk özellik sırasını belirlemek.
**Yapılanlar**
- Vault açıldı: 00..06 notları (`.obsidian/` oluşturulmadı, kullanıcı kendisi açacak)
- Karar A-01 (tek uygulama, ayrı vault ve repo); tez vault'unda karşılığı D-42
- Domino ilk özellik sırası onaylandı: F-01 2 kişilik → F-02 davet → F-03 Capacitor (A-03, [[02 - Yol Haritası]])
- Özel repo `Muradaliev-1/azegames` kullanıcı tarafından açıldı, vault push edildi (A-02)
- 2 kişilik ana kurallar alındı, ilk tur başlangıcı dahil ([[04 - Oyun Kuralları]])
- Domino'ya Telefon (365) ve ayarlanabilir kurallar eklendi (A-05, F-06..F-08); Telefon motoru uygulama reposunda yazılacak; Telefon kurallarının bir kısmı alındı
**Testler:** Uygulama kodu yazılmadı.
- 2 kişilik kurallar tamamlandı, tezde R-20..R-28
**Açık:** U-01..U-03
