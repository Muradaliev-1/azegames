---
tags: [az-oyunlari, kurallar]
---
# Oyun Kuralları

**İlke:** Kurallar yalnız kullanıcıdan alınır. Uydurma, "genelde böyledir" kuralı yazılmaz. Belirsiz nokta "Açık" olarak işaretlenir.

## Domino
Domino'da **iki oyun türü** var: **101** ve **Telefon (365)** (kullanıcı, 2026-11-26). Kullanıcı masa kurarken kuralları kendisi seçebilir (A-05, aşağıda "Ayarlanabilir kurallar").

### 101
- **4 kişilik (2'ye 2, 101 puan):** kaynak tez `03 - Kurallar.md` (R-01..R-19, onaylı). Burada kopyalanmaz.
- **2 kişilik:** motoru etkilediği için onaylanan kurallar tez `03 - Kurallar.md`'ye yeni R-xx kimlikleriyle yazılır; burada yalnız özet ve bağlantı tutulur.
  - Durum: alındı (2026-11-26), tez `03 - Kurallar.md` D bölümünde **R-20..R-28**. **Motorda (2026-11-27):** tez `domino/engine.py` `Round2`/`Match2`, tez commit `a0cd8b0`, 215 test, 11/11 mutant; 4 kişilik davranış bit bit aynı. Uygulama arka ucuna senkron henüz yapılmadı (kullanıcı onayıyla).
  - Özet: 7'şer taş, kalan 14 bazar; oynanabilir taşı yoksa bazardan **2'şer** çeker (taşı varken çekemez); **bazarın son 2 taşı çekilmez**; çekecek taş yoksa pas; çekilebilir taş yokken iki pas = kapanma; bazardakiler puana girmez. İlk tur 1|1 → 2|2 → … → 6|6 → 0|0 sahibi o çiftle; hiçbiri yoksa yeniden dağıtım. Sonraki turlar son taşı koyan başlar. Puanlama, 13 eşiği, bekleyen, 101 ve 1|1 yeniden başlama 4 kişilikle aynı.
  - 2'li çekişte iki taş birlikte alınır (ilk taş oynanabilir olsa da).
  - Yeniden başlamada 1|1 bazardaysa açılış merdivenle bulunur; çift yoksa yeniden dağıtım sınırsız. Açık kural sorusu yok.
  - Not (ölçüm): iki elde de merdiven çifti olmaması, yani yedi çiftin hepsinin bazarda olması, olasılıkla C(14,7)/C(28,7) ≈ %0,29 (200 000 dağıtımda %0,31). Bu yüzden yeniden dağıtım çok seyrek görülür.

### Telefon (365): kullanıcının anlattığı (2026-11-26)
- **Puan:** her oynayışta açık uçların toplamı **5'e bölünüyorsa** o toplam oynayan oyuncunun takımına yazılır; bölünmüyorsa puan **yok** (ör. 4 uç 6, 4, 3, 1 → 14 → 0 puan; kullanıcı örneği).
- **Hedef:** ilk **365**'e ulaşan kazanır; 365'e kadar oyun (turlar) devam eder.
- **4 yöne oynama:** masaya gelen ilk çiftin iki yanı da kapandıktan sonra o çiftin 4 tarafına da oynanabilir.
- **Dominant eşiği:** kazanan 365'e ulaştığında kaybeden **225'i geçemediyse** maç genel skora **2-0** yazılır, geçtiyse 1-0. Eşik masaya göre değişebilir (kullanıcı: 225, 235; ayar).
- **35 nokaut:** bir oynayışta **35** puan alan oyunu **doğrudan kazanır** (genel skora 1-0). Masa ayarı (aç/kapa).
- **Bazar çekimi:** masa ayarı: **tek-tek** ya da **cüt-cüt** (2'şer).
- **Oyuncu sayısı:** 2, 3, 4 (4'te takımlı ya da takımsız).

- **4 yön (cevap):** masaya gelen **ilk çift**, açılış taşı olmasa da sonradan gelse de; iki yanı kapanınca 4 yöne açılır. Sonraki çiftler açılmaz.
- **35 (cevap):** bir oynayışta yazılabilecek en yüksek puan zaten 35 (kullanıcı); yani nokaut = tam 35. Motor bunu bir değişmez olarak test eder (tek oynayışta > 35 olmamalı).
- **Tur sonu (cevap):** elini bitirene rakiplerin el toplamı **5'in katına yukarı yuvarlanarak** yazılır (12 → 15, 15 → 15).
- **Uç toplamı (cevap):** bir kolun ucunda duran çift **iki kez** sayılır (6|6 = 12). 4 yön açıldıktan sonra **4 ucun toplamı** alınır; çiftin henüz oynanmamış tarafı **0** sayılır (ör. 3 tarafa oynanmış, 4.'ye oynanmamışsa 3 uç toplanır).
- **Kapanma (cevap):** 101'deki gibi (R-10): el toplamları karşılaştırılır, düşük toplamlı kazanır, yüksek toplam yazılır.
- **Dağıtım (cevap):** oyuncu sayısı ne olursa olsun kişi başı **7** taş. Kalan bazar: 2 kişide 14, 3 kişide 7, 4 kişide 0.
- **Bazar (cevap):** tek-tek çekimde son **1**, cüt-cüt'te son **2** taş çekilmez.
- **13 eşiği yok** (cevap): Telefon'da 101'in 13 puan eşiği yok.

- **Dominant sınırı (cevap):** kaybeden tam 225'teyse **1-0**; 2-0 yalnız 225'in altında (eşik ≥ değer yeterli).
- **Kapanma puanı (cevap):** 5'e yukarı yuvarlanır; **eşitlik 101'deki gibi** (R-11: dört elin toplamı havuza, sonraki turu kazanan alır).
- **Başlangıç (cevap):** 101 gibi: ilk tur 1|1 (bazar varsa yoksa 2|2 … 6|6 … 0|0 merdiveni, hiçbiri yoksa yeniden dağıtım), sonraki turlar son taşı koyan, herhangi taşla.

### Telefon: açık sorular
- Tek oynayış sınırı: 35 en yüksek değer; uç toplamı kuralıyla motor testinde doğrulanacak.
- (Kapandı) Telefon'da R-19 (1|1 ile yeniden başlama) yok: kullanıcı teyit etti.

### 101: 3 kişilik ve 4 kişilik takımsız (cevap, 2026-11-26)
- **3 kişilik:** 4 kişilikle aynı kurallar, tek fark **bazar** var (7 taş).
- **4 kişilik:** ya takımlı (bugünkü 2'ye 2) ya da **herkes kendi eline** oynar.
- **Takımsız puan (cevap):** bitirene **tüm rakiplerin** el toplamı yazılır; kapanmada **en düşük el** kazanır, ötekilerin toplamını alır.
- **Takımsız kapanmada eşitlik (cevap, şimdilik):** en düşük el iki kişide eşitse yazılacak puan **ikiye bölünür**, ikisine yazılır. (Tek sayıda yarımın yuvarlanması açık.)
- **3 kişide açılış (cevap):** 2 kişilikteki merdiven (1|1, yoksa 2|2 … 6|6, yoksa 0|0; hiçbiri yoksa yeniden dağıtım).

### Ayarlanabilir kurallar (masa kurarken, A-05)
Kullanıcı isteği: oyunu yaratan kişi kuralları kendisi belirler. Bilinen ayarlar:
- Oyun türü: 101 / Telefon
- Oyuncu sayısı: 2, 3, 4 (4'te takımlı / takımsız)
- Bazar çekimi: tek-tek / cüt-cüt
- Telefon: dominant eşiği (ör. 205 / 225 / 235 / 265), 35 nokaut aç/kapa
- 101'in 3 kişilik ve takımsız 4 kişilik kuralları kısmen alındı (yukarıda, açık noktalarla).
Bot her ayar birleşiminde ayrıca test edilir. Tez ajanı yalnız 4 kişilik 101 için ölçüldü; diğer ayarlarda botun gücü ölçülmeden "güçlü" denmez.

## Loto
Kurallar alınmadı. Gerçek parasız.

## Nərd
Kurallar alınmadı.

## Şahmat
Standart kurallar (FIDE). Varyant istenirse kullanıcıdan alınır.
