# Sektör Radarı

Claude'da her sabah sektör haberlerini tarayan, markanı etkileyenleri risk, fırsat ya da içerik fikri diye ayıran ve kaynaklı kısa bir brifing yazan bir asistan. Bu repo, "Yapay Zekâ ile Kendi Asistanlarınızı Yaratmak" atölyesinde (İstanbul Bilgi Üniversitesi, 24 Ekim 2026) kurulan radarın bütün dosyalarını ve promptlarını içerir.

Bütün dosyaları tek seferde indirmek için: **Code > Download ZIP**.

## İçindekiler

| Dosya | Ne işe yarar |
|---|---|
| [`REHBER.pdf`](REHBER.pdf) | Kurulumun adım adım anlatıldığı ana rehber |
| [`hazir-dosyalar/`](hazir-dosyalar) | Örnek marka Kıtırca için kurulu radar: skill paketi, proje talimatı ve projeye yüklenecek üç dosya |
| [`hazir-promptlar.md`](hazir-promptlar.md) | Atölyede ekranda yazılan bütün promptlar: zayıf prompt karşılaştırması, radarı çalıştırma, her sabah otomatik çalıştırma (e-postalı hali dahil) |
| [`kendi-markan-icin.md`](kendi-markan-icin.md) | Dosyaları, proje talimatını ve skill'i kendi markan için Claude'a yazdırma adımları |
| [`telefonda-sesli-dinle.md`](telefonda-sesli-dinle.md) | Brifingi iPhone ya da Android telefonda sesli dinlemek için ayarlar |

`hazir-dosyalar/` içinde:

- `sektor-radari-skill.zip`: yüklenecek skill paketi (zip'i açmadan olduğu gibi yükle)
- `proje-talimati.txt`: projenin Instructions alanına yapıştırılacak metin
- `marka-profili.md`, `rakipler.md`, `kaynaklar.md`: projeye yüklenecek üç dosya

REHBER.pdf'te klasör adları numaralı geçer. Repodaki karşılıkları:

| REHBER.pdf'te | Repoda |
|---|---|
| 1-hazir-dosyalar | `hazir-dosyalar/` |
| 2-hazir-promptlar | `hazir-promptlar.md` |
| 3-kendi-markan | `kendi-markan-icin.md` |
| 4-telefonda-dinle | `telefonda-sesli-dinle.md` |

## Başlamadan önce

1. claude.ai'ye giriş yap. Free hesap yeterli; tek fark, her sabah otomatik çalıştırma yalnızca ücretli planlarda var.
2. **Settings > Capabilities** bölümünde **Code execution and file creation** seçeneğini aç. Skill'ler bu açık olmadan çalışmaz.
3. Radarı çalıştıracağın sohbette web aramasının açık olduğundan emin ol.

Menü adları arayüz diline ve sürüme göre farklı görünebilir.

## Yol 1: Hazır dosyalarla kur (yaklaşık 15 dakika)

1. **Skill'i yükle.** Customize > Skills > **+** > Create skill > **Upload a skill** ile `hazir-dosyalar/sektor-radari-skill.zip` dosyasını seç. Yüklendikten sonra skill'in açık olduğunu kontrol et.
2. **Projeyi oluştur.** Projects > Create project. Ad olarak `Sektör Radarı · Kıtırca` yazabilirsin.
3. **Talimatı yapıştır.** `proje-talimati.txt` içindeki metnin tamamını projenin **Instructions** alanına yapıştır.
4. **Dosyaları yükle.** `marka-profili.md`, `rakipler.md` ve `kaynaklar.md` dosyalarını projenin dosyalar bölümüne yükle.
5. **Radarı çalıştır.** Proje içinde yeni bir sohbet aç, web aramasının açık olduğunu kontrol et ve [`hazir-promptlar.md`](hazir-promptlar.md) içindeki ilk prompt'u yaz: `Radarı çalıştır. En fazla 3 madde.`
6. **Brifingi oku.** Bir linke tıklayıp haberin gerçekten orada olduğuna bak. "Belirsiz" işaretli maddeler hata değil; radar emin olmadığı şeyi böyle işaretler.

## Yol 2: Kendi markan için kur (30-40 dakika)

[`kendi-markan-icin.md`](kendi-markan-icin.md) dosyasını sırayla izle:

1. Marka dosyalarını Claude'a hazırlat (K1).
2. Proje talimatını yazdır (K2).
3. Claude'un sorularını cevaplayarak skill'i yazdır ve zip olarak indir (K3).
4. Yol 1'deki kurulum adımlarını kendi dosyalarınla yap (K4).
5. Radarı çalıştır, sonucu değerlendir ve iyileştir (K5).

Önce Yol 1 ile radarın nasıl çalıştığını görmeni, sonra Yol 2 ile kendi markana uyarlamanı öneririm.

## Her sabah çalıştırmak

Ücretli planlarda (Pro, Max, Team, Enterprise) [`hazir-promptlar.md`](hazir-promptlar.md) içindeki 2. bölümle zamanlanmış görev kurabilirsin. Claude bir öneri gösterir, **Schedule** ile onaylarsın. İlk çalışmanın sonucunu kontrol et.

Free planda zamanlanmış görev yok. Hafta içi 08:30'a bir takvim hatırlatıcısı kur ve açıklamasına projenin linkini koy; bildirim gelince projeyi açıp tek satırı yazman yeterli.

## Sorun çıkarsa

- **Skill görünmüyor ya da çalışmıyor:** "Code execution and file creation" açık mı, skill Customize > Skills'te açık mı, kontrol et.
- **Zip yüklenmiyor:** Zip açıldığında en üstte doğrudan `sektor-radari` klasörü olmalı, içinde `SKILL.md` bulunmalı.
- **Brifing boş geldi:** Son 96 saatte uygun haber olmayabilir; bu radarın doğru çalıştığını gösterir. Süreyi uzat: `Radarı çalıştır. Son 7 gün.`
- **Kullanım limiti doldu:** Madde sayısını 3'te tut ya da ertesi gün tekrar dene.
- **Bir link açılmıyor ya da tarih tutmuyor:** Aynı sohbette Claude'a "Brifingdeki linkleri tekrar aç ve tarihleri doğrula" yaz.

## Birkaç not

- Proje dosyalarına yalnızca paylaşmakta sakıncası olmayan bilgileri koy. Kurumsal kullanımda şirketinin yapay zekâ politikasına ve hesabının gizlilik ayarlarına bak.
- Brifing karar desteğidir. Önemli bir karar vermeden önce kaynağı aç ve oku.
- Plan ve özellik bilgileri 22 Ekim 2026'da Claude'un yardım sayfalarından kontrol edildi; değişebilir.

Sorular ve geri bildirim için LinkedIn: [linkedin.com/in/erkanceran](https://linkedin.com/in/erkanceran)
