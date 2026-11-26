---
tags: [az-oyunlari, analiz]
---
# Öğretici Analiz (domino, ileride)

Maç sonu oyuncuya "burada şu hamle daha iyiydi" göstermek.

## İki tür analiz, karıştırılmaz
1. **"Senin bildiklerinle daha iyi hamle"** (ana analiz): yalnız oyuncunun o andaki gözlemiyle (`Observation`) çalışan ajanla yapılır: ISMCTS (`ismcts-rand@N`) veya melez. Oyuncunun göremediği elleri kullanmaz, bu yüzden adil bir öğretmendir.
2. **"Eller açıkken"** (oracle): tüm eller görülerek yapılan analiz. Yalnız bu etiketle gösterilir; oyuncuya "bilmen mümkün değildi" bağlamı verilmeden öneri gibi sunulmaz.

## Tezle ilişki
Tezde `tools/analyze_records.py` karar başı oracle pişmanlığı ve inanç kalitesini zaten ölçüyor. Öğretici analiz tezde ayrı bir bölüm olabilir (tez vault'u D-42); ürün tarafı (arayüz, metinler) bu vault'ta.

## Açık
- Hangi ajan ve bütçe (hız/kalite)? Sunucuda mı, cihazda mı?
- Hata eşiği: ne kadar kayıp "hata" sayılır?
