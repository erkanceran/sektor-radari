# Hazır promptlar

Atölyede ekranda yazdığım bütün promptlar burada, gösterdiğim sırayla. Kutulardaki metni olduğu gibi kopyalayıp Claude'a yapıştır.

---

## 0. Karşılaştırma: zayıf prompt

Proje dışında, boş bir sohbette dene. Sonra aynı işi Kıtırca projesinde 1. prompt'la yap ve iki cevabı karşılaştır.

```
Sen deneyimli bir pazarlama uzmanısın. Sektör haberlerini takip et, önemli olanları bana söyle.
```

Cevap ya genel bir haber listesi olur ya da Claude "hangi sektör?" diye sorar. Sebebi prompt'ta görev, bağlam, kriter, çıktı ve kısıt eksik olması. Kıtırca projesinde bunların hepsi proje dosyalarında ve skill'de yazılı olduğu için tek cümle yetiyor.

---

## 1. Radarı çalıştır

Kıtırca projesi içinde yeni bir sohbet aç, web aramasının açık olduğunu kontrol et.

```
Radarı çalıştır. En fazla 3 madde.
```

Tam brifing için:

```
Radarı çalıştır.
```

Radar varsayılan olarak son 96 saatin haberlerine bakar. Daha geniş bir süre için:

```
Radarı çalıştır. Son 7 gün.
```

---

## 2. Her sabah otomatik çalıştır (ücretli planlar)

Proje içinde yaz. Claude görevin adını, zamanını ve talimatını önerir; **Schedule** ile onayla.

```
Bu projede hafta içi her sabah 08:30'da "Radarı çalıştır." komutunu çalıştıracak bir zamanlanmış görev kur. Brifingi markdown formatında yaz. Kurmadan önce görevin bu projenin dosyalarına ve sektor-radari skill'ine erişebildiğini doğrula. Erişemiyorsa bunu söyle ve marka, rakip ve kaynak bilgilerini görevin talimatına ekle.
```

---

### 2-b. E-posta ile

Gmail connector'ın bağlıysa brifing her sabah kendi Gmail adresine, e-postanın içinde biçimli olarak gelir. Görevin kendi çıktısı markdown olur.

```
Bu projede hafta içi her sabah 08:30'da "Radarı çalıştır." komutunu çalıştıracak bir zamanlanmış görev kur.
Her çalışmada ayrıca:
1. Brifingi Gmail ile bağlı Gmail hesabımın kendi adresine gönder. Konu: "Sektör Radarı · [bugünün tarihi]". Ek dosya koyma; brifing doğrudan e-postanın gövdesinde görünsün.
2. Gövdeyi HTML olarak yaz: başlıkta tarih, her madde ayrı bir kart, etiketler renkli (Risk kırmızı, Fırsat yeşil, İçerik fikri mavi, Belirsiz gri), kaynak linkleri tıklanabilir. Stilleri her HTML öğesinin içine satır içi (inline) yaz; e-posta programları ayrı stil bloklarını siliyor.
3. HTML'in yanına aynı brifingin düz metin sürümünü de koy; HTML göstermeyen e-posta programları onu gösterir.
4. Gönderim onay gerektirdiği için yapılamazsa e-postayı aynı içerikle taslak olarak kaydet.
5. Görevin kendi çıktısında brifingi markdown formatında yaz; sonuna e-postanın gönderildiğini ya da taslak olarak kaydedildiğini bir satırla ekle.
Kurmadan önce görevin bu projenin dosyalarına, sektor-radari skill'ine ve Gmail'e erişebildiğini doğrula. Dosyalara erişemiyorsa bunu söyle ve marka, rakip ve kaynak bilgilerini görevin talimatına ekle.
```

Gmail connector varsayılan olarak her gönderimden önce onay ister. Görev bu yüzden gönderemezse e-postayı taslak olarak bırakır; ilk çalışmadan sonra Gmail'deki taslaklara bak.
