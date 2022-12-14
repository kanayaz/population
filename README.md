# population
DÜNYA NÜFUS VERİLERİNE DAYANARAK ÜLKELERİN GELECEK NÜFUSLARININ
TAHMİNLENMESİ


14 Kasım 2022 yi 15 kasım 2022 ye bağlayan gece dünya tarihinde önemli bir tarih
oldu. Bu tarihte dünya nüfusu 8 milyara ulaştı ve dünya literatürüne bugün 8 milyar günü
olarak geçti. 1925 yılında 2 milyar olan nüfusumuz 1974 yılında bunu katlayarak 4 milyar
seviyelerine geldi. Dünya nüfusunun 2 milyardan 4 milyara çıkması 49 yıl alırken, bu nüfusu
tekrar ikiye katlaması 47 yıl sürdü.
Bugün dünya nüfusu artışa devam etmekle birlikte gitgide nüfus artış hızının düştüğü
gözlenmektedir. Nüfusumuzun 9 milyar seviyesini aştıktan sonra 10 milyara ulaşmadan nüfus
artış hızının eksiye döneceği ve nüfusun tekrar 8 milyarın altına düşeceğine dair
hesaplamalar bulunmaktadır.
İstatistiksel olarak bugüne kadar yaşanmış en iyi durumdayız. İnsanlar daha uzun
yaşıyor, geçen nesillere göre yiyeceğe, temiz suya ve sağlık hizmetlerine erişim daha kolay,
çok daha az insan fakirlik sınırının altında yaşıyor.
Her ne kadar dünyada haberler iyi olsa da ülkelerin nüfus ve olanaklarına göre bu
durumun tersine yaşandığı ülkelerde mevcuttur. Günümüzde en kalabalık ülkenin Çin Halk
Cumhuriyeti olduğu bilinmektedir ancak nüfus artış hızının yavaşlamasıyla birlikte Çin yakın
bir gelecekte dünyanın en kalabalık ikinci ülkesi konumuna düşecektir. Nüfus artış hızı
yükselmeye devam eden ve şu anda en kalabalık ikinci ülke konumunda bulunan Hindistan
yakın bir gelecekte birinci sırayı alacaktır. 
Bu veriler ışığında yapılan çalışmamızda ülkelerin dünya nüfusundaki yeri ve yıllara
göre nüfusunun alacağı hali görmek adına dünya bankası nüfus verilerine dayalı olarak lineer
regresyon kullanarak hesaplama yapıldı.
Bu işlem için yine dünya bankasının sitesi üzerinde data bölümünde bulunan veriler
ile çalıştık. İlgili sayfa da verileri üç farklı şekilde alabiliyorduk. Bu şekiller csv, xml ve xlsx veri
tipleriydi. Öncelikle csv dosyası olarak aldık ancak dosya içerisinde Python tarafından
tanınmayacak şekilde veriler olduğu görüldü. Bu nedenle xlsx tipindeki verileri bilgisayara
indirerek dosyada bulunan data sayfası csv dosyası olarak dışa aktarıldı.
Elde ettiğimiz veri seti 1960 yılından 2021 yılına kadar olan 266 ülkeye ait nüfus
verileridir. Veri seti içerisinde ülke Country Name, Country Code, Indicator Name ve Indıcator
Code sütünları bulunmaktadır.
Çalışmaya başlarken ilk olarak ilgili kütüphaneler sisteme eklendi. Bu kütüphaneler
öncelikli olarak pandas, matplotlib ve sklearn kütüphanesidir. Ayrıca arka planda oluşacak
bazı hataların atlanabilmesi ve ekrana yansıtılmaması amacıyla warning kütüphanesi ile
ignore tipindeki hata mesajları filtrelenmiştir.
Sonrasında edinilen veri seti programımıza import edilerek dataframe olarak
kaydedilmiştir.
Sonrasında elde bulunan veri setiyle ilgili elde bulunan verileri gözlemek amacıyla bazı
denemeler yapıldı.
Veri setinin ilk 5 satırı.
Veri setinin son 5 satırı.
Veri setiyle ilgili bazı bilgiler.
Bu aşamadan sonra veriseti üzerinden model eğitilmesi ve regresyon analizi yaparak
nüfusun belirlenmesi üzerine çalışıldı. Bu aşamada 4 adet fonksiyon geliştirildi. İlk fonksiyon
modelin eğitilmesi amacıyla oluşturulan populatıonreg fonksiyonudur.
İkinci fonksiyon model eğitilmesi için yapılan düzenlemeler, sonucun gösterilmesi ve
bu verilerin matplot lib kütüphanesi kullanılarak analiz edilen verilerin gösterilmesini
içermektedir.
Burada öncelikli olarak gereksiz sütunlar silinmiş ve veriler içinde sadece verilen
ülkeye ait nüfus verileri ile yıl verilerinin kalması saglanmıştır. Sonrasında dataset transpoze
edilerek yıl ve nüfus verileri satır halinden sütun haline çevrilmiştir. Daha önce incelediğimiz 
verilerde null veri bulunmamasına rağmen dropna metodu kullanılarak bundan emın
olunmuştur. İndexlerin düzenlenmesinden sonra veriler integer haline getirilip veriler test ve
train veriler olarak yapılandırılmıştır.
Elde edilen veriler ilk fonksiyona gönderilerek model eğitimi tamamlanmış ve
sonrasında gelen regresyon doğrusu yıl ile çarpılıp bir düzeltme fonksiyonundan geçirilip
nüfus verisi ile grafik çizdirilmiştir.
Aynı işlem tüm dünya nüfusu için 3. Fonksiyonda da yapılmıştır.
Burada elde edilen fonksiyon aslında 4. fonksiyondan alınan verileri ülke kısıtlaması
olmadan modeli eğitmektedir. Son fonksiyonumuzda gereksiz satırlar temizlenmiş ve sütun
toplamları alınarak dünya nüfusu verileri hesaplanmış ve eğitime gönderilmiştir.
Sonrasında main fonksiyonunda ülke ve yıl adları alınıp fonksiyonlara gönderilmiştir.
Regresyon verileri içerisinde train verileri kırmızı işaretlenirken test verileri mavi
gösterilmiştir. Ülkemiz için yapılan hesaplamaya göre 2023 yılı nüfusumuzun 85 519 614,
2030 yılında 96 076 004 olacağı öngörülmüştür.
Dünya nüfusu için yapılan hesaplama da ise 2030 yılında 8 528 648 226 olacağı 2040
yılında ise 9 338 074 482 olacağı öngörülmüştür
