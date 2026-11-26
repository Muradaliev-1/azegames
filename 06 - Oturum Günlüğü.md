---
tags: [az-oyunlari, gunluk]
---
# Oturum Günlüğü

Yeni oturum en üste eklenir.

## 2026-11-27 · Oturum 1 devamı
- F-01 motoru tez reposunda bitti: `Round2`/`Match2` (R-20..R-28), tez commit `a0cd8b0`; 215 test geçti, `--only 2p` 11/11, 4 kişilik iz bit bit aynı (T-2P0). Tam mutasyon (238) tezde koşuyor.
- Sıradaki: arka uca senkron (`tools/sync_domino.py`) ve 2 kişilik oda; canlıya (Render/Vercel) push kullanıcı onayıyla.

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
