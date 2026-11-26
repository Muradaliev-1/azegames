---
tags: [az-oyunlari, vizyon]
---
# Vizyon

## Ne
Tek uygulama, içinden dört oyun: **domino, nərd, şahmat, loto**. Arkadaşla oynama (davet), botla oynama, telefonda (PWA → Capacitor ile iOS/Android) ve tarayıcıda.

## Neden ayrı proje
Tez demosunun rolü (tez D-34: tez demosu + insan verisi aracı) bir ürün fikrine büyüdü. Tez jürisi tez reposunu temiz ve odaklı görmeli; ürün işleri ayrı vault ve ayrı repoda yürür (A-01).

## Oyun sırası
1. **Domino** önce: motor, sızıntısız bot, arayüz ve canlı demo zaten var. Fark: ölçülmüş güçlü bot, ileride öğretici analiz ([[05 - Öğretici Analiz]]).
2. **Loto** ve **nərd** sonra.
   - Loto **gerçek parasız** olur. Para (ya da paraya çevrilebilir bir şey) girerse önce kumar mevzuatı incelenir; o zamana kadar konu kapalı.
   - Nərd: kurallar kullanıcıdan alınacak ([[04 - Oyun Kuralları]]); bot yaklaşımı ayrı karar.
3. **Şahmat** en son. Açık kaynak motorla bot ucuz, ama pazar çok dolu. **Lisansa dikkat:** yaygın açık kaynak şahmat motorlarının bir kısmı GPL lisanslı; uygulamaya gömülürse lisans yükümlülükleri doğabilir. Motor seçilmeden önce lisansı ayrıca incelenir (henüz incelenmedi).

## Sonra: sesli sohbet (A-04)
Şimdilik yapılmıyor. Ön koşul: odalar ve davet sistemi (F-02).
- **Yalnız arkadaşların kurup davet ettiği özel odalarda açık.** Rastgele eşleşmede ve sıralamalı maçta kapalı: partnere el bilgisi sızdırmak haksızlık olur.
- Ses kaydedilmez.
- Kontroller: mikrofonu kapatma, oyuncu susturma, bas-konuş.
- Güvenlik ve hukuk: reşit olmayan kullanıcılar için şikâyet ve engelleme; KVKK, Azerbaycan veri kuralları, mağaza onayı (incelenmedi).
- Teknik: WebRTC. 4 kişilik odada doğrudan bağlantı yeter; büyük ölçekte ses sunucusu veya servis gerekir (maliyet).
- **Tez verisi:** ses açık oynanan oyunlar temiz insan verisi sayılmaz; kayıtta "ses açıktı" işareti olmalı (tez D-27'deki `team_full_info` etiketine benzer).

## Rakip ortamı (bilinen)
- Domino: "Yerli Domino" (devsoft.az), Google Play'de yaygın (tez D-34'te kayıtlı). Aynı ürünle doğrudan yarışmak hedef değil; fark yapay zekâ ve analiz.
- Diğer oyunlar için pazar araştırması yapılmadı.

## Kapsam dışı (şimdilik)
Gerçek para, bahis, reklam/uygulama içi satın alma kararları, mağaza yayını. Her biri ayrı karar gerektirir.
