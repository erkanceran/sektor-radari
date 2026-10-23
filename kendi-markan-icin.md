# Radarı kendi markan için kur

Hazır dosyaları kullanmadan, aynı radarı kendi markan için Claude'a yazdırmanın yolu. Her adımda Claude'a ne yazacağın aşağıda.

Toplam süre: 30-40 dakika. Free hesapta da çalışır; yalnızca son adımdaki zamanlama ücretli planlarda var, Free için alternatifi K6'da.

## Başlamadan önce

- claude.ai'de **Settings > Capabilities** bölümünde **Code execution and file creation** açık olsun. Claude dosya üretebilsin ve skill'ler çalışabilsin diye bu gerekli.
- Bu adımları proje dışında, boş bir sohbette yap. Dosyalar hazır olunca projeyi kuracaksın.

Not: claude.ai'de "skill'i sohbetle oluştur" diye ayrı bir düğme yok (22 Ekim 2026 itibarıyla). Aşağıdaki yöntemde Claude skill dosyasını sohbette yazıp zip olarak veriyor, sen de indirip yüklüyorsun.

---

## K1 · Marka dosyalarını oluştur

İki yol var. Markanı iyi biliyorsan **K1-A** daha hızlı: bilgileri tek seferde verirsin, Claude üç dosyayı hemen hazırlar. Cevaplardan emin değilsen **K1-B**'yi kullan: Claude soruları tek tek sorar, düşünmene yardım eder.

### K1-A · Bilgileri ver, dosyaları al (hızlı yol)

Aşağıdaki prompt Kıtırca markasının bilgileriyle dolu; olduğu gibi yapıştırırsan çalışır. Kendi markan için her satırda iki noktadan sonraki kısmı kendi bilginle değiştir; bilmediğin satırı boş bırak.

```
Markam için bir sektör radarı kuruyorum. Aşağıdaki bilgilere göre üç ayrı markdown dosyası oluştur ve indirilebilir olarak ver.

Marka bilgileri:
- Marka adı, sektörü ve ürünleri: Kıtırca; paketli atıştırmalık; kraker, gofret, çikolatalı bar
- Pazar ve satıldığı zincirler: Türkiye; Migros, CarrefourSA, A101, ŞOK; ayrıca yerel marketler
- Konumlandırma: uygun fiyatlı, aile odaklı, okul ve ofis atıştırmalığı
- Hedef kitle: satın alan 25-45 yaş ebeveynler; tüketen 8-16 yaş çocuk ve gençler; ara öğün için ofis çalışanları
- Bu dönemin gündemi: bu ay kakaolu gofret serisinin lansmanı; hammadde maliyetleri nedeniyle planlanan fiyat güncellemesi; devam eden okul dönemi kampanyası
- Hassas konular: fiyat artışı tepkisi; ambalaj ve şeker içeriği tartışmaları; çocuklara yönelik reklam düzenlemeleri
- Takip ettiğim rakipler: Ülker, Eti, Torku; tuzlu atıştırmalıkta PepsiCo Türkiye
- Okuduğum sektör siteleri: foodinlife.com.tr, perakende.org, marketingturkiye.com.tr, dunya.com, aa.com.tr
- İzlemek istediğim konular: kakao fiyatı; şeker ve hammadde maliyetleri; atıştırmalık yeni ürün; gıda fiyat düzenlemesi; çocuklara yönelik gıda reklamı düzenlemesi; ambalaj ve geri dönüşüm düzenlemesi

Dosyalar:
1. marka-profili.md: marka, hedef kitle, bu dönemin gündemi, hassas konular
2. rakipler.md: rakipler ve her biri için neden izlendiği; radarın rakip haberlerinde neye bakacağı (yeni ürün, fiyat, kanal anlaşması, kriz)
3. kaynaklar.md: öncelikli siteler, arama konuları, zaman aralığı (varsayılan son 96 saat)

Bu bilgilerde olmayan bir şeyi uydurma; eksik alanı boş bırak ve [doldurulacak] yaz. Bir bilgi çelişkili ya da belirsizse dosyaları oluşturmadan önce bana sor.
```

### K1-B · Claude sorsun, sen cevapla

```
Markam için bir sektör radarı kuruyorum. Bana aşağıdaki soruları TEK TEK sor, her seferinde cevabımı bekle. Hepsi bitince üç ayrı markdown dosyası oluştur ve indirilebilir olarak ver:

1. marka-profili.md: marka adı, sektör, ürünler, pazar, konum, hedef kitle, bu dönemin gündemi (lansman, fiyat, kampanya, kriz), hassas konular
2. rakipler.md: izlenecek 3-6 rakip ve her biri için neden izlendiği
3. kaynaklar.md: 4-6 sektör sitesi, 5-8 arama konusu, varsayılan zaman aralığı (son 96 saat)

Sorular:
- Markanın adı, sektörü ve ürünleri ne?
- Hangi pazarda satıyorsunuz? Ürününüz hangi market zincirlerinde ve kanallarda var?
- Hedef kitle kim? Satın alan ile kullanan farklı mı?
- Bu dönem gündemde ne var: lansman, fiyat değişikliği, kampanya, kriz?
- Hangi konular hassas?
- Takip ettiğin rakipler kimler?
- Hangi sektör sitelerini okuyorsun, hangi konuları izlemek istiyorsun?

Cevaplarımda olmayan bir bilgiyi uydurma; o alanı boş bırak ve [doldurulacak] yaz.
```

---

## K2 · Proje talimatını yazdır

Aynı sohbette devam et.

```
Şimdi bu radar için Claude projesinin "Instructions" alanına yapıştıracağım proje talimatını yaz. Şunları içersin:

- Bu projenin hangi marka için sektör radarı olduğu
- Claude'un rolü: pazarlama ekibine sabah brifingi hazırlayan analist
- Hangi bilginin hangi dosyada olduğu (marka-profili.md, rakipler.md, kaynaklar.md)
- Çalışma kuralları: brifing istendiğinde "sektor-radari" skill'ini kullan; Türkçe, kısa ve net yaz; haberde olmayanı ekleme; emin değilsen "belirsiz" yaz; her iddiaya kaynak linki ve tarih koy; eksik bilgi varsa sor

En fazla 20 satır olsun. Düz metin olarak ver, kopyalayıp yapıştıracağım.
```

---

## K3 · Skill'i Claude'la birlikte yaz

Skill yazmayı bilmen gerekmiyor. Aşağıdaki prompt'la Claude sana birkaç soru sorar, cevaplarından skill'i kendisi oluşturur ve zip olarak verir. Emin olmadığın soruda "öneriyi kullan" yazman yeterli. Aynı sohbette devam et; Claude markanı K1'den biliyor.

```
Şimdi bu radar için bir Claude skill'i oluşturmak istiyorum. Skill'in ne olduğunu ve nasıl yazıldığını bilmiyorum, bana yol göster.

Önce skill'in ne işe yaradığını iki cümleyle anlat. Sonra aşağıdaki konularda bana TEK TEK soru sor ve her seferinde cevabımı bekle. Her sorunun altına bu radar için kendi önerini de yaz; "öneriyi kullan" dersem onu al.
1. Skill hangi cümleyle çalışsın? (ör. "Radarı çalıştır")
2. Çalışmadan önce hangi bilgileri okusun, bulamazsa ne yapsın?
3. Haberleri nerede ve hangi zaman aralığında arasın? (Varsayılan önerin son 96 saat olsun.)
4. Bir haberi neye göre önemli sayalım, neye göre eleyelim?
5. Brifing nasıl görünsün: kaç madde, her maddede ne olsun, nasıl etiketlensin?
6. Asla yapmaması gereken şeyler ne?

Sorular bitince cevaplarımı kısaca özetle ve onayımı iste. Onaylarsam skill'i şu kurallarla oluştur:
- Klasör adı "sektor-radari" olsun; içinde SKILL.md ve references/cikti-sablonu.md bulunsun.
- SKILL.md en üstte YAML frontmatter ile başlasın: name sektor-radari olsun; description ne yaptığını ve hangi cümleyle çalışacağını söyleyen, 200 karakteri geçmeyen tek bir cümle olsun ve içinde iki nokta üst üste (:) geçmesin.
- SKILL.md'de şu bölümler olsun: Ne zaman kullanılır, Girdiler, Adımlar, Kriter, Çıktı, Kısıtlar.
- Adımlarda her haberin linkini açıp tarihini ve iddiasını doğrulama adımı mutlaka olsun.
- cikti-sablonu.md'de brifing şablonu ve doldurulmuş bir örnek olsun.
- Her şey Türkçe olsun. Skill'de marka adı geçmesin; marka bilgisi her seferinde proje dosyalarından okunsun.
Sonra klasörü zip'le. Zip açıldığında en üstte doğrudan "sektor-radari" klasörü olsun. Zip'i indirilebilir olarak ver.
```

Zip indirilmezse: Claude'dan SKILL.md ve cikti-sablonu.md içeriklerini metin olarak iste, bilgisayarında `sektor-radari/SKILL.md` ve `sektor-radari/references/cikti-sablonu.md` olarak kaydet, `sektor-radari` klasörünü zip'le.

---

## K4 · Kur

1. **Skill'i yükle:** Customize > Skills > **+** > Create skill > **Upload a skill** ile zip'i seç ve skill'i aç.
2. **Projeyi oluştur:** Projects > Create project. Ad: `Sektör Radarı · [Marka adın]`.
3. **Talimatı yapıştır:** K2'de aldığın metni projenin **Instructions** alanına yapıştır.
4. **Dosyaları yükle:** K1'deki üç dosyayı projeye yükle.

Menü adları arayüz diline ve sürüme göre farklı görünebilir.

---

## K5 · Dene ve iyileştir

Proje içinde yeni sohbet aç, web araması açık olsun.

```
Radarı çalıştır. En fazla 3 madde.
```

Sonucu iyileştirmek için aynı sohbette:

```
Bu brifingi değerlendir: maddeler gerçekten bu hafta bir karar gerektiriyor mu, kaynaklar güncel mi, rakip haberi var mı? Eksik gördüklerini say. Her eksiğin skill'den mi proje dosyalarından mı kaynaklandığını söyle ve neyi nasıl değiştirmem gerektiğini yaz.
```

Skill'i değiştirmen gerekirse K3'teki sohbete dön, değişikliği iste, yeni zip'i yükle.

---

## K6 · Döngü (Pro ve üstü)

Proje içinde:

```
Bu projede hafta içi her sabah 08:30'da "Radarı çalıştır." komutunu çalıştıracak bir zamanlanmış görev kur. Brifingi markdown formatında yaz. Kurmadan önce görevin bu projenin dosyalarına ve sektor-radari skill'ine erişebildiğini doğrula. Erişemiyorsa bunu söyle ve marka, rakip ve kaynak bilgilerini görevin talimatına ekle.
```

Claude görevin adını, zamanını ve talimatını önerir; **Schedule** ile onayla. İlk çalışmanın sonucunu kontrol et.

Free hesapta zamanlanmış görev yok. İki pratik yol:
- Hafta içi 08:30'a tekrarlanan bir takvim hatırlatıcısı kur, açıklamasına projenin linkini koy. Bildirim gelince projeyi açıp "Radarı çalıştır." yaz.
- Arama limitini korumak için kaynaklar.md'deki konulara Google Alerts kur; sabah gelen e-postayı projeye yapıştırıp şunu yaz: "Web araması yapma. Aşağıdaki haberleri radar kurallarına göre değerlendir ve brifingi yaz." 
