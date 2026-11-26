---
tags: [az-oyunlari, giris]
guncelleme: 2026-11-26
---
# START HERE (Azerbaycan Oyunları uygulaması)

> **Claude için:** Uygulama işine başlarken önce bu dosyayı, sonra [[03 - Karar Günlüğü]]'nü ve [[06 - Oturum Günlüğü]]'nün son girişini oku. Tez işleri bu vault'ta değil, tez vault'unda (`C:\Users\murad\Projects\domino-research\docs\Domino-Tez\`) tutulur.

## Proje (tek cümle)
Domino, nərd, şahmat ve lotonun tek uygulamada oynandığı, arkadaş davetli, telefonda da çalışan bir "Azerbaycan oyunları" uygulaması. Domino tarafı tez projesinin motorunu ve sızıntısız botunu kullanır.

## Tezle ilişki (sınır)
- Tez reposu `Muradaliev-1/domino-research` tek başına kalır, uygulama ürün ayrıntısı oraya yazılmaz (tez vault'u D-42).
- Domino motoru (`domino/`) tezde geliştirilir ve testlenir; uygulama onu **tek yönlü kopya** olarak alır (`tools/sync_domino.py`, `DOMINO_VERSION`). Kopyada elle değişiklik yok.
- Motoru etkileyen kurallar (ör. 2 kişilik domino) tez `03 - Kurallar.md`'ye R-xx kimlikleriyle yazılır, motorda seçenek olur; 4 kişilik davranış bit bit aynı kalır (test + mutant).
- Uygulama işi tez işini engellemez. Tez önceliklidir.

## Çalışma ilkeleri
1. **Uydurma kural yok.** Her oyunun kuralı kullanıcıdan alınır ([[04 - Oyun Kuralları]]); belirsiz nokta açık soru olarak yazılır.
2. **Bot hile yapmaz.** Domino botu yalnız kendi gözlemini görür (tez ilkesi). "Eller açıkken" analizi ayrı ve etiketli ([[05 - Öğretici Analiz]]).
3. **Test olmadan "bitti" yok.** Gerçek test çıktısı raporlanır.
4. **Canlıya (Render/Vercel) ve GitHub'a push kullanıcı onayıyla.**
5. Her anlamlı değişiklikten hemen sonra bu vault güncellenir.

## Kimlikler
| Önek | Anlamı | Yer |
|---|---|---|
| A-xx | Uygulama kararı | [[03 - Karar Günlüğü]] |
| U-xx | Açık soru | [[03 - Karar Günlüğü]] (Açık sorular) |
| F-xx | Özellik | [[02 - Yol Haritası]] |
| K-<oyun>-xx | Oyun kuralı (dominonun motor kuralları tezde R-xx) | [[04 - Oyun Kuralları]] |

## Durum (2026-11-27)
- F-01: 2 kişilik 101 motoru tez reposunda hazır (`Round2`/`Match2`); **yerel demoda oynanıyor** (bota karşı, `?mode=2`, bot şimdilik `greedy`), testli; demo repolarına commit/push ve canlı yok (onay bekliyor).
- Vault açıldı (iskelet). Uygulama kodu henüz yok; mevcut domino demosu ayrı repolarda canlıda:
  - backend `C:\Users\murad\Downloads\DominoAI\backend` → `Muradaliev-1/domino-ai-backend` → Render (FastAPI + WebSocket, bot `ismcts-rand@200`)
  - frontend `C:\Users\murad\Downloads\DominoAI\frontend` → `Muradaliev-1/domino-ai-frontend` → Vercel (TypeScript + Vite + DOM, PWA)
  - Bu iki repo ve Render/Vercel bağlantıları şimdilik olduğu gibi kalır; yeni yapıya taşınması ayrı karar (U-01).
- Domino ilk özellik sırası: [[02 - Yol Haritası]]. Domino'da iki oyun türü: 101 ve Telefon (365) (A-05).

- Repo: özel `Muradaliev-1/azegames` (A-02), kökü bu `docs/` klasörü, dal `main`.
- Domino sırası onaylı (A-03). 2 kişilik ana kurallar alındı: 7'şer taş + 14'lük bazar, yalnız zorunluyken çekme, ilk tur 1|1 → 2|2 → … → 6|6 → 0|0 (hiçbiri yoksa yeniden dağıtım), puanlama 4 kişilikle aynı.

## Sıradaki işler
1. ~~2 kişilik kurallar (R-20..R-28) ve motor seçeneği~~ bitti (2026-11-27, tez `a0cd8b0`, 215 test, 11/11 mutant).
2. ~~Arka uca senkron + 2 kişilik oda (yerel)~~ bitti (2026-11-27). Kalan: demo repolarına commit ve canlıya alma (kullanıcı onayı), 2 kişilik güçlü bot.
3. Oyun yaratma + arkadaş davet akışının tasarımı (F-02), içinde kendi kurallarıyla masa (F-06, A-05).
4. Telefon (365): kalan kural soruları ([[04 - Oyun Kuralları]]), motor uygulama reposunda (A-05).

## Vault haritası
- [[01 - Vizyon]] · [[02 - Yol Haritası]] · [[03 - Karar Günlüğü]]
- [[04 - Oyun Kuralları]] · [[05 - Öğretici Analiz]] · [[06 - Oturum Günlüğü]]
