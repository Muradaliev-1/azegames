---
tags: [az-oyunlari, karar]
---
# Karar Günlüğü

Yeni karar en üste eklenir. Biçim: ID · tarih · karar · gerekçe · geri alınabilir mi.

## A-04 · 2026-11-26 · Sesli sohbet sonraya; açılırsa yalnız arkadaş özel odalarında
Kullanıcı fikri ve kararı (başka oturum üzerinden iletildi). Gerekçe: rastgele/sıralamalı maçta partnere el bilgisi sızdırmak haksızlık. Ses kaydedilmez; ses açık oyunlar kayıtta işaretlenir ve tez için temiz insan verisi sayılmaz. Ön koşul F-02. Ayrıntı [[01 - Vizyon]]. Geri alınabilir: evet.

## A-03 · 2026-11-26 · Domino ilk özellik sırası: F-01 2 kişilik → F-02 oyun yaratma + davet → F-03 Capacitor
Kullanıcı onayı (önerilen sıra). Gerekçe: F-01 motor kuralı gerektirir, tezi etkileyen tek iş, erken netleşmeli; F-02 hem 2 hem 4 kişilik odaları kapsar; F-03 arayüz oturunca. 2 kişilik kurallar kısmen alındı ([[04 - Oyun Kuralları]]): 7'şer taş + 14'lük bazar, yalnız zorunluyken çekme, puanlama 4 kişilikle aynı; ilk tur 1|1, yoksa 2|2 … 6|6, yoksa 0|0 sahibi başlar, hiçbiri yoksa yeniden dağıtım. Geri alınabilir: evet.

## A-02 · 2026-11-26 · Uygulama reposu: özel `Muradaliev-1/azerbaycan-oyunlari`
Kullanıcı onayı (ad ve özel olması). Şimdilik yalnız bu vault'u (`docs/`) içerir; repo kökü `C:\Users\murad\Downloads\DominoAI\docs\`. Backend/frontend kodunun buraya taşınması U-01. Geri alınabilir: evet.

## A-01 · 2026-11-26 · Tek çok oyunlu uygulama, tezden ayrı proje ve ayrı vault
Kullanıcı kararları (2026-11-26): (1) Tek uygulama; içinden domino, nərd, şahmat ve loto oynanır. (2) Uygulama notları tez vault'undan ayrı bir Obsidian vault'unda: `C:\Users\murad\Downloads\DominoAI\docs\`. (3) Tez reposu `Muradaliev-1/domino-research` tek başına kalır, uygulama ayrı. Tez tarafında karşılığı: tez vault'u D-42 (tez D-34'teki demo rolü bu projeye dönüştü). Tez yalnız domino motoru, insan verisi ve olası öğretici analiz bölümüyle ilgilenir. Mevcut `domino-ai-backend` / `domino-ai-frontend` repoları ve Render/Vercel bağlantıları şimdilik değişmez (U-01). Geri alınabilir: evet.

## Açık sorular
- **U-01** Mevcut demo repoları (backend, frontend) yeni uygulama reposuna taşınacak mı (tek repo / ayrı repolar), Render/Vercel bağlantıları ne olacak? Şimdilik dokunulmuyor.
- **U-02** Uygulama adı (mağaza adı) ne olacak?
- **U-03** Capacitor paketinde önce Android mi, iOS mu? (iOS için Apple geliştirici hesabı ve Mac gerekir; doğrulanacak.)
