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
| F-01 | **2 kişilik domino** | Kurallar (kullanıcıdan), tezde R-xx + motor seçeneği + test + mutant | 4 kişilik davranış bit bit aynı kalır. Bot: aynı arama ajanı 2 kişide çalışır mı, ayrıca ölçülür |
| F-02 | **Oyun yaratma + arkadaş davet** | Backend oda modeli | Şu an oda otomatik eşleşiyor; davet kodu/bağlantısı, boş koltuklara bot, 2 veya 4 kişilik seçimi |
| F-03 | **Telefon uygulaması (Capacitor)** | Arayüz kararlı olmalı | Aynı TypeScript kodu (tez D-32); Android önce mi, iOS mu: U-03 |
| F-05 | **Sesli sohbet (sonra)** | F-02 odalar + davet | Yalnız arkadaş özel odalarında; WebRTC; ayrıntı A-04, [[01 - Vizyon]] |
| F-04 | Öğretici maç sonu analizi | Tezde analiz bölümü | [[05 - Öğretici Analiz]] |

Gerekçe (öneri): F-01 motor kuralı gerektirir ve tezi en çok etkileyen iş, erken netleşmeli; F-02 hem 2 hem 4 kişilik odaları kapsar, bu yüzden F-01'in kural kararından sonra; F-03 en son, çünkü arayüz değişirken paketlemek tekrar iş çıkarır.

## Faz U2: Loto, nərd
- [ ] Loto kuralları (kullanıcıdan), gerçek parasız
- [ ] Nərd kuralları (kullanıcıdan), bot yaklaşımı

## Faz U3: Şahmat
- [ ] Motor ve lisans incelemesi (GPL)
