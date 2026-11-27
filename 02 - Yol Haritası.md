---
tags: [az-oyunlari, yol-haritasi]
---
# Yol Haritası

Tez öncelikli; uygulama işleri tezi engellemez.

## Faz U0: Kuruluş
- [x] Uygulama vault'u (2026-11-26)
- [x] Uygulama GitHub reposu: özel `Muradaliev-1/azegames` (A-02, 2026-11-26)
- [ ] Mevcut demo repolarının (backend, frontend) yeni yapıdaki yeri (U-01)

## Faz U1: Domino (ilk özellikler, sıra)
Sıra kullanıcı tarafından onaylandı (2026-11-26, A-03).

| # | Özellik | Bağımlılık | Not |
|---|---|---|---|
| F-01 | **2 kişilik domino** | Kurallar (kullanıcıdan), tezde R-xx + motor seçeneği + test + mutant | **Motor bitti (2026-11-27, tez `a0cd8b0`); canlıda bota karşı oynanıyor** (2026-11-27; bot `greedy`). Güçlü 2 kişilik bot yapılmayacak (A-06). Kalan: iki insanlı oda (F-02) |
| F-02 | **Oyun yaratma + arkadaş davet** | Backend oda modeli | Şu an oda otomatik eşleşiyor; davet kodu/bağlantısı, boş koltuklara bot, 2 veya 4 kişilik seçimi |
| F-03 | **Telefon uygulaması (Capacitor)** | Arayüz kararlı olmalı | Aynı TypeScript kodu (tez D-32); Android önce mi, iOS mu: U-03 |
| F-05 | **Sesli sohbet (sonra)** | F-02 odalar + davet | Yalnız arkadaş özel odalarında; WebRTC; ayrıntı A-04, [[01 - Vizyon]] |
| F-04 | Öğretici maç sonu analizi | Tezde analiz bölümü | [[05 - Öğretici Analiz]] |
| F-06 | **Kendi kurallarıyla masa kurma** | F-02 | Oyun türü, oyuncu sayısı, takımlı/takımsız, bazar çekimi, Telefon ayarları (A-05); F-02'nin "oyun yarat" ekranının parçası |
| F-07 | **Telefon (365)** | Kurallar netleşmeli ([[04 - Oyun Kuralları]] açık sorular), ayrı motor | Yeni oyun türü; botu ayrıca gerekir (tez ajanı 101 için) |
| F-08 | 101'in 3 kişilik / takımsız 4 kişilik modları | Kurallar (kullanıcıdan) | Henüz alınmadı |

Gerekçe (öneri): F-01 motor kuralı gerektirir ve tezi en çok etkileyen iş, erken netleşmeli; F-02 hem 2 hem 4 kişilik odaları kapsar, bu yüzden F-01'in kural kararından sonra; F-03 en son, çünkü arayüz değişirken paketlemek tekrar iş çıkarır.

## Faz U2: Loto, nərd
- [ ] Loto kuralları (kullanıcıdan), gerçek parasız
- [ ] Nərd kuralları (kullanıcıdan), bot yaklaşımı

## Faz U3: Şahmat
- [ ] Motor ve lisans incelemesi (GPL)
