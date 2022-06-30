---
slug: "network-tehditleri-ve-zararli-yazilimlar"
categories: []
ID: "4b73cc67-ecb9-4ccc-9498-218af735459c"
description: "network-tehditleri"
title: "Ağ Tehditleri ve Zararlı Yazılımlar"
tags: []
cover: "malware.png"
date: "2022-07-01"
createdAt: 1656629450258

---
## Tehdit, Güvenlik Açığı ve Risk
Zararlı yazılımlara başlamadan önce ağ güvenliği ile ilgili birkaç terimi incelemek faydalı olacaktır. 

- **Tehdit** - **Threat** ⇒ Veri veya ağın kendisi gibi bir varlık için potansiyel bir tehlike.
- **Güvenlik açığı** - **Vulnerability** ⇒ Bir sistemde veya tasarımında bir tehdit tarafından sömürülebilecek bir zayıflık.
- **Saldırı yüzeyi** - **Attack surface** ⇒ Saldırı yüzeyi, belirli bir sistemdeki saldırganın erişebildiği güvenlik açıklarının toplam toplamıdır. Saldırı yüzeyi, bir saldırganın sisteme girebileceği ve sistemden veri alabileceği farklı noktaları açıklar. Örneğin, işletim sisteminizin ve web tarayıcınızın her ikisinin de güvenlik yamalarına ihtiyacı olabilir. Her biri saldırılara karşı savunmasızdır ve ağda veya internette maruz kalırlar. Birlikte, tehdit aktörünün yararlanabileceği bir saldırı yüzeyi oluştururlar.
- **Istismar** - **Exploit** ⇒ Bir varlığın güvenliğini aşmak üzere bir güvenlik açığından yararlanmak için kullanılan mekanizma. Açıklardan yararlanma girişimleri uzak veya yerel olabilir. Uzaktan yararlanma, hedef sisteme önceden erişmeden ağ üzerinden çalışan bir istismardır. Saldırganın bu güvenlik açığından yararlanabilmesi için son sistemde bir hesaba ihtiyacı yoktur. Yerel bir istismarda, tehdit aktörünün son sisteme bir tür kullanıcı veya yönetim erişimi vardır. Yerel bir istismar, saldırganın son sisteme fiziksel erişimi olduğu anlamına gelmez.
-  **Risk** ⇒   Belirli bir tehdidin bir varlığın belirli bir güvenlik açığından yararlanma ve istenmeyen bir sonuçla sonuçlanma olasılığı.

## Tehdit Aktörleri
Birçok farklı tehdit aktörü vardır kısaca açıklamak gerekirse;

- **Script kiddies** ⇒ 1990'larda ortaya çıktı ve gençlere veya deneyimsiz tehdit aktörlerine zarar vermek için mevcut senaryoları, araçları ve istismarları çalıştıran, ancak genellikle kar amacı gütmeyen kişilere atıfta bulunuyor.
- **Vulnerability brokers** ⇒ Genellikle istismarları keşfetmeye ve bazen ödüller veya ödüller için satıcılara bildirmeye çalışan gri şapkalı bilgisayar korsanlarını ifade eder.
- **Hacktivist** ⇒ Farklı siyasi ve sosyal fikirlere karşı toplanan ve protesto eden gri şapkalı bilgisayar korsanlarını ifade eden bir terimdir. Hacktivistler, makaleler, videolar yayınlayarak, hassas bilgileri sızdırarak ve dağıtılmış hizmet reddi (DDoS) saldırıları gerçekleştirerek kuruluşları veya hükümetleri açıkça protesto ederler.
- **Cybercriminals** ⇒ Serbest meslek sahibi olan veya büyük siber suç örgütleri için çalışan siyah şapkalı bilgisayar korsanları için kullanılan bir terimdir. Her yıl, siber suçlular tüketicilerden ve işletmelerden milyarlarca dolar çalmaktan sorumludur.
- **State-spoensered** ⇒ Devlet destekli bilgisayar korsanları, hükümet sırlarını çalan, istihbarat toplayan ve yabancı hükümetlerin, terörist grupların ve şirketlerin ağlarını sabote eden tehdit aktörleridir. Dünyadaki çoğu ülke, devlet destekli bilgisayar korsanlığına bir dereceye kadar katılmaktadır. Bir kişinin bakış açısına bağlı olarak, bunlar beyaz şapka veya siyah şapka korsanlarıdır.

## Zararlı Yazılımlar
Uç cihazlar özellikle kötü amaçlı yazılım saldırılarına eğilimlidir. Verilere, ana bilgisayarlara veya ağlara zarar vermek, bozmak, çalmak veya genel olarak başka bir "kötü" veya gayrimeşru eylemde bulunmak için özel olarak tasarlanmış kod veya yazılımdır. Kötü amaçlı yazılımlar hakkında bilgi sahibi olmak önemlidir, çünkü tehdit aktörleri ve çevrimiçi suçlular, güvenlik açıklarından yararlanmaya yardımcı olmak için kullanıcıları kötü amaçlı yazılım yüklemeleri için sık sık kandırmaya çalışır. Buna ek olarak, kötü amaçlı yazılımlar o kadar hızlı bir şekilde değişir ki, kötü amaçlı yazılımdan koruma yazılımları yeni tehditleri durduracak kadar hızlı güncellenemediğinden, kötü amaçlı yazılımla ilgili güvenlik olayları son derece yaygındır.

 ### Virüsler ve Türleri
  
  Virüs, kendisinin bir kopyasını başka bir programa ekleyerek yayılan bir kötü amaçlı yazılım türüdür. Program çalıştırıldıktan sonra, virüsler bir bilgisayardan diğerine yayılarak bilgisayarlara bulaşır. Çoğu virüsün yayılması için insan yardımına ihtiyacı vardır. Örneğin, birisi virüslü bir USB sürücüsünü bilgisayarına bağladığında, virüs bilgisayara girer. Virüs daha sonra yeni bir USB sürücüsüne bulaşabilir ve yeni bilgisayarlara yayılabilir. Virüsler uzun bir süre uykuda kalabilir ve daha sonra belirli bir saat ve tarihte etkinleşebilir.

Basit bir virüs, yürütülebilir bir dosyadaki ilk kod satırına kendini yükleyebilir. Etkinleştirildiğinde, virüs diskte diğer yürütülebilir dosyaları denetleyebilir, böylece henüz bulaşmamış tüm dosyalara bulaşabilir. Virüsler, ekranda resim görüntüleyenler gibi zararsız olabilir veya sabit sürücüdeki dosyaları değiştirenler veya silenler gibi yıkıcı olabilir. Virüsler, algılanmayı önlemek için mutasyona uğrayacak şekilde de programlanabilir.

Çoğu virüs artık USB bellek sürücüleri, CD'ler, DVD'ler, ağ paylaşımları ve e-posta yoluyla yayılmaktadır. E-posta virüsleri yaygın bir virüs türüdür.

Bazı virüs türlerine ait bilgiler tabloda verilmiştir
| Virüs Türü |İşlevi  |
|--|--|
|Boot| İşletim sistemi açılışında çalışarak kendini yükler|
|Web Scripting| Web sayfaları ve tarayıcılarındaki açıkları istismar eder|
|Hijacker|Web tarayıcı fonksiyonları ele geçirerek farklı sayfalara yönlendirme yapar|
|Resident|RAM’e yerleşerek kalıcılık sağlar|
|Polymorphic|Antivirüsten kaçmak için kodunu her açılışta yeniler|
|Makro(VBA)|Kendi kodunu dosyalara eklerler|

### Worms (Solucanlar)

Solucanlar virüsler gibi sistem içinde çoğalırlar ancak virüslerden farklı olarak dosya ve programlara bulaşmazlar. Ayrıca insan etkileşimi veya herhangi bir tetikleyiciye ihtiyaç duymadan kendi kendine çoğalabilirler. 

Arka kapı (Backdoor) yaratma, dosya silme, veri sızdırma, BOTNET'e sokma (zombie makine yapma) gib işlevleri vardır.

Solucanlar, internetteki en yıkıcı saldırılardan bazılarından sorumludur. 2001 yılında, Code Red solucanı başlangıçta 658 sunucuya bulaşmıştı. 19 saat içinde solucan 300.000'den fazla sunucuya bulaşmıştı.

En bilinen solucan saldırısı ise [Stuxnet](https://tr.wikipedia.org/wiki/Stuxnet)'dir. *İlk siber silah* olarak da bilinir. Amerika tarafından İran nükleer çalışmalarını sekteye uğratatmak için kullanılmıştır.

### Trojans (Truva Atları)

Tarihteki hikayesine benzer şekilde faydalı gözüken bir program vb. yardımcılığı ile sisteme girer ve sistem içinde amacını sessizce yerine getirir. Truva atı konsepti esnektir. Anında hasara neden olabilir, sisteme uzaktan erişim sağlayabilir veya bir arka kapıdan erişim sağlayabilir. Ayrıca, uzaktan talimat verildiği gibi, "parola dosyasını bana haftada bir kez gönder" gibi eylemleri de gerçekleştirebilir. Kötü amaçlı yazılımların siber suçluya veri gönderme eğilimi, saldırı göstergeleri için giden trafiği izleme ihtiyacını vurgulamaktadır.
Belirli bir hedefe sahip olanlar gibi özel olarak yazılmış Truva atlarının tespit edilmesi zordur.

Truva atları neden oldukları hasara veya bir sistemi ihlal etme biçimlerine göre sınıflara ayrılır.
|Truva atı Türü| İşlev - Tarif  |
|--|--|
| Remote Access | Yetkisiz uzaktan erişimi etkinleştirir. |
| Data Sending |    Tehdit aktörüne parolalar gibi hassas veriler sağlar. |
| Destructive | Dosyaları bozar veya siler. |
| Proxy | Saldırıları başlatmak ve diğer yasa dışı etkinlikleri gerçekleştirmek için kurbanın bilgisayarını kaynak cihaz olarak kullanır. |
| FTP | Son cihazlarda yetkisiz dosya aktarım hizmetlerini etkinleştirir. |
| Antivirüs disabler | Virüsten koruma programlarının veya güvenlik duvarlarının çalışmasını durdurur.  |
| Denial of Service (DoS) | Ağ etkinliğini yavaşlatır veya durdurur. |
| Keylogger | Bir web formuna girilen tuş vuruşlarını kaydederek kredi kartı numaraları gibi gizli bilgileri etkin bir şekilde çalmaya çalışır. |

### Spywares (Casus Yazılımlar)
İşletim sistemlerine bulaşarak farkındasız olarak kullanıcının hassas bilgilerini ifşa ederler
Parolalar, e mail adresleri , web tarayıcı geçmişi Sistem bilgileri , log dosyaları , kullanıcı aktiviteleri gibi bilgileri edinip sahibine iletmeyi hedefler.

### Rootkit'ler
Çalışma mantığı olarak işletim sistemi çekirdeğine sızması nedeniyle en tehlikeli virüs türleri arasındandır. Sistem içerisinde tam yetkiyle çalıştığı için eylemlerinde sınır yoktur. Ayrıca tespit edilebilmleri ve silinmeleri oldukça zordur. IoT cihazlarını da hedef alabilirler.
Virüs worms ve trojan'ların tüm işlevlerini bünyesinde barındırır.

Bazı Rootkit türlerini kısaca açıklayalım
|  |  |
|--|--|
| Kernel Rootkit | Çekirdek (Kernel) seviyesinde çalışır |
| Firmware Rootkit  | Donanıma gömülü işletim sistemlerini hedefler
|App Rootkit |Çekirdeğe değil , uygulamalara kod enjekte ederler|
| Mem Rootkit  | Çekirdekte değil , RAM’de çalışırlar ve iyi gizlenirler |
| BootLoader Rootkit  | Boot kayıtlarına yerleşir , dosya sisteminde ve antivirüslerde görünmezler |
| Library Rootkit  | Kütüphane dosyalarını enfekte ederler |
| Hypervisor Rootkit  | Sanallaştırma platformu katmanlarına yerleşirler , iyi gizlenirler |

### Ransomwares (Fidye Yazılımları)

Tehdit aktörleri, yüklerini taşımak için ve diğer kötü amaçlı nedenlerle virüsleri, solucanları ve Truva atlarını kullandılar. Ancak, kötü amaçlı yazılımlar gelişmeye devam ediyor.

Şu anda, en baskın kötü amaçlı yazılım fidye yazılımıdır. Fidye yazılımı, virüslü bilgisayar sistemine veya verilerine erişimi reddeden kötü amaçlı yazılımlardır. Siber suçlular daha sonra bilgisayar sistemini serbest bırakmak için ödeme talep ediyor.

Fidye yazılımı, tarihteki en karlı kötü amaçlı yazılım türü haline gelmek için gelişti. 2016'nın ilk yarısında, hem bireysel hem de kurumsal kullanıcıları hedefleyen fidye yazılımı kampanyaları daha yaygın ve güçlü hale geldi.

Düzinelerce fidye yazılımı çeşidi var. Fidye yazılımı, sistem dosyalarını ve verilerini şifrelemek için sıklıkla bir şifreleme algoritması kullanır. Bilinen fidye yazılımı şifreleme algoritmalarının çoğunluğu kolayca çözülemez ve kurbanlara istenen fiyatı ödemekten başka çok az seçenek bırakır. Ödemeler genellikle Bitcoin ile ödenir, çünkü bitcoin kullanıcıları anonim kalabilir. Bitcoin, kimsenin sahip olmadığı veya kontrol etmediği açık kaynaklı, dijital bir para birimidir.

Kötü amaçlı yazılımlama olarak da bilinen e-posta ve kötü amaçlı reklamcılık, fidye yazılımı kampanyaları için vektörlerdir. Sosyal mühendislik, kendilerini güvenlik teknisyenleri olarak tanımlayan siber suçluların evleri arayıp kullanıcıları fidye yazılımını kullanıcının bilgisayarına indiren bir web sitesine bağlanmaya ikna etmeleri gibi kullanılır.

Bu liste, internet geliştikçe büyümeye devam edecektir. Yeni kötü amaçlı yazılımlar her zaman geliştirilecektir. Siber güvenlik operasyonlarının temel amacı, yeni kötü amaçlı yazılımlar hakkında bilgi edinmek ve bunları derhal nasıl azaltmaktır.

## Antivirüslerin Çalışma Prensiplerinin Temeli


- **Byte-Signature** ⇒ Yazılımın (virüsün) makine dilindeki karşılığından bir bölümü alınarak tanınır.
- **Hash-Signature** ⇒ Yazılımın **hash** değeri alınarak tanınır . En ufak bir değişiklikte tanınamaz olacağı için risklidir
- **Heuristic** ⇒ Sezgisel tanıdır . Kodun içeriğinden çok davranışları izlenerek tanınmaya çalışılır Performans ve zaman kaybettirebilir.
Bu konuyu daha detaylı bir başka makalemizde inceleyeceğiz.

