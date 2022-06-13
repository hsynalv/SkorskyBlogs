---
tags:
  - "topology"
  - "osi"
description: "Topoloji diyagramları"
title: "Topoloji Diyagramları"
ID: "b08cf121-a883-424d-816c-12f661405026"
categories:
  - "network"
slug: "Topology Diyagramları"
cover: "cover1.jpg"
date: "2022-06-13 12:00"
createdAt: 1655159511772
updatedAt: 1655159535168

---
Topoloji diyagramlarına daha önceki [Network'e ilk Adım](https://skorskyblog.me/network/tr/network-e-ilk-ad%C4%B1m#topoloji-diyagramlar%C4%B1)
makalemizde değinmiştik ancak artık OSI katmanlarına devam etmeden önce topoloji diyagramlarına daha detaylı bakmamız gerekiyor. Kısa bir hatırlatma yaparak başlayalım. Topoloji diyagramlarını iki gruba ayırmıştık;

**Fizksel Topoloji Diyagramları**
Fiziksel topoloji diyagramları, aracı cihazların fiziksel konumunu ve kablo kurulumunu gösterir. Bu cihazların bulunduğu odaların bu fiziksel topolojide etiketlendiğini görebilirsiniz.
![fiziksel-topoloji](https://skorskyfiles.blob.core.windows.net/$web/articles/gunumuzde-network/fiziksel-topoloji.png)
**Mantıksal Topoloji Diyagramları**
Mantıksal topoloji diyagramları, cihazları, portları ve ağın adresleme şemasını göstermektedir. Hangi uç cihazların hangi aracı cihazlara bağlandığını ve hangi medyanın kullanıldığını görebilirsiniz.
![mantiksal-topoloji](https://skorskyfiles.blob.core.windows.net/$web/articles/gunumuzde-network/mantiksal-topoloji.png)

 
## LAN Topolojileri

### Mesh – Örgü Ağ Topolojisi

Örgü ağ topolojisinde her cihaz, özel bir noktadan noktaya bağlantı aracılığıyla ağdaki diğer tüm cihazlara bağlanır. Adanmış/dedicated dediğimiz bu topolojide, bağlantının yalnızca iki bağlı cihaz için veri taşıdığı anlamına gelir. Diyelim ki ağda n tane cihazımız olsun, o zaman her cihaz ağdaki (n-1) cihazlara bağlanmalıdır. N cihazlık bir örgü topolojisindeki bağlantı sayısı n (n-1) / 2 olacaktır.

 **Mesh – Örgü topolojisinin avantajları**

-  İki cihaz arasında özel bir bağlantı olduğundan veri trafiği sorunu yoktur, bu da bağlantının yalnızca bu iki cihaz için mevcut olduğu anlamına gelir. Bu yüzden bu bağlantı güvenlidir.
- . Mesh topolojisi güvenilir ve sağlamdır. Çünkü bir bağlantının başarısızlığı diğer bağlantıları ve ağdaki diğer cihazlar arasındaki iletişimi asla etkilemez.
-  Mesh topolojisi güvenlidir çünkü noktadan noktaya bir bağlantı vardır ve bu nedenle yetkisiz erişim hiç bir zaman mümkün değildir.
- Arıza tespiti bu topololijide oldukça kolaydır.

 **Mesh – Örgü topolojisinin dezavantajları**

-  Topolojiyi oluşturmak ve bağlanmak için gereken kablo miktarı çok sıkıcı bir hal alabilir.
-  Her aygıtın diğer aygıtlara bağlanması gerektiğinden, gereken Giriş / Çıkış bağlantı noktası sayısı çok büyük olmaktadır.
- Ölçeklenebilme sorunu vardır. Çünkü ağ üzerindeki her bir cihaz özel noktadan noktaya bağlantıya sahiptir. Bu yüzden aynı anda çok sayıda cihaza veri göndermek mümkün değildir.

### Star – Yıldız Ağ Topolojisi

Yıldız – Star topolojisinde, ağdaki her cihaz hub adı verilen merkezi bir cihaza bağlanır. Ağ topolojileri bakımından, Mesh topolojisinin aksine, yıldız topolojisi cihazlar arasında doğrudan iletişime izin vermez, bir cihazın hub aracılığıyla iletişim kurması gerekir. Bir cihaz diğer cihaza veri göndermek isterse, önce verileri hub’a göndermesi ve ardından hub bu verileri belirlenen cihaza iletmesi gerekir.

 **Yıldız topolojisinin avantajları**

-  Daha ucuzdur, çünkü her aygıt yalnızca bir Giriş / Çıkış bağlantı noktasına ihtiyaç duyar ve bir bağlantıyla hub’a bağlanması gerekir.
-  Kurulumu daha kolaydır
-  Her aygıtın yalnızca hub’a bağlanması gerektiğinden daha az kablo gereksinimi duyar.
- Sağlamdır, eğer bir bağlantı başarısız olursa, diğer bağlantılar çalışmaya devam edecektir.
-  Bağlantı kolayca tanımlanabildiği için, hata tespiti kolaydır.

 **Yıldız topolojisinin dezavantajları**

-  Hub bozulursa, ağ sistemi çöker, cihazların hiçbiri hub olmadan veri alış verişi yapamaz.
-  Hub, yıldız topolojisinin merkezi sistemidir bu yüzden daha fazla kaynak ve düzenli bakım gerektirir.

### Bus – Yol Ağ Topolojisi
Bus topolojisinde bir ana kablo vardır ve tüm cihazlar bu ana kablo üzerinden bağlanır. Ayrıca merhez hattını ana kabloya bağlayan tap adı verilen bir cihaz bulunur. Tüm veriler ana kablo üzerinden iletildiği için, bir ana kablonun sahip olabileceği mesafe ve bağlanabilecek 30 adet cihaz sınırı vardır. Bu yüzden bu mesafe ince koaksiyel kablo kullanıldığında 300, kalın koaksiyel kablo kullanıldığında ise 185 metredir.

**Bus topolojisinin avantajları**

-  Kolay kurulumu vardır, her kablonun omurga kablosuyla birleştirilmesi gerekir.
-  Mesh ve star topolojisine göre daha az kablo gerektirir.
    

 **Veri yolu topolojisinin dezavantajları**

-  Arıza tespiti zordur.
-  Omurga kablosuyla bağlayabileceğiniz cihaz sayısı sınırlı olduğu için ölçeklendirilemez.

### Halka – Ring Ağ Topolojisi
Bu topolojide her cihaz, her iki tarafındaki iki cihaza bağlanır. Bir cihazın her iki tarafındaki cihazlarla sahip olduğu iki noktadan noktaya bağlantısı bulunmaktadır. Ayrıca bu yapı bir halka oluşturur, bu nedenle halka topolojisi olarak adlandırılmıştır. Bundan dolayı bir cihaz başka bir cihaza veri göndermek isterse, verileri bir yönde gönderir. Bu yüzden halka topolojisindeki her cihaz bir tekrarlayıcıya sahiptir. Eğer alınan veriler başka bir cihaza yönelikse, tekrarlayıcı bu verileri amaçlanan cihaz alana kadar iletir.

**Halka Topolojisinin Avantajları**

-  Kurulumu kolaydır.
-  Topolojiye bir cihaz eklemek veya çıkarmak için yönetim daha kolaydır, sadece iki bağlantının değiştirilmesi yeterlidir.
    

 **Halka Topolojisinin Dezavantajları**

-  Bir bağlantı hatası, başarısızlık nedeniyle sinyal ileri gitmeyeceğinden tüm ağ düşebilir.
-  Tüm veriler bir çember içinde dolaştığı için veri trafiği sorunu oluşur.

### Hibrit Ağ Topolojisi

İki veya daha fazla topolojinin bir kombinasyonu, hibrit topoloji olarak bilinir. Örneğin, yıldız ve ağ topolojisi kullandığımız bir sistem olduğunu varsayalım. Böylece bu kombinasyona hibrit topoloji diyebiliriz.

 **Hibrit topolojinin avantajları**

-  Gereksinime göre topolojiyi seçebiliriz.
-  Diğer bilgisayar ağlarını farklı topolojilere sahip mevcut ağlara bağlayabiliriz. Böylelikle, ölçeklenebilir bir ağ sistemi elde ederiz.
    

 **Hibrit topolojinin dezavantajları**

-  Arıza tespiti çok zordur.
-  Kurulum zor ve karmaşıktır.
-  Tasarımı karmaşıktır, bu nedenle bakımı zordur ve dolayısıyla pahalıdır.


![topologies](https://skorskyfiles.blob.core.windows.net/$web/articles/topolojiler/topologies.png)


## WAN Topolojileri

- ** Point to Point**
Bu en basit ve en yaygın WAN topolojisidir. İki uç nokta arasında kalıcı bir bağlantıdan oluşur.

Bir kaynak ve hedef düğüm, birden çok aracı cihaz kullanılarak dolaylı olarak bir coğrafi mesafe boyunca birbirine bağlanabilir. Ancak, ağda fiziksel cihazların kullanımı, şekilde gösterildiği gibi mantıksal topolojiyi etkilemez. Şekilde, ara fiziksel bağlantıların eklenmesi mantıksal topolojiyi değiştirmeyebilir. Mantıksal noktadan noktaya bağlantı aynıdır.
![noktadan-noktaya](https://skorskyfiles.blob.core.windows.net/$web/articles/topolojiler/noktadan-noktaya.png)
- ** Hub and Spoke**
Merkezi yerleşkenin noktadan noktaya bağlantıları kullanarak şube tesislerini birbirine bağladığı yıldız topolojisi WAN sürümüdür. Şube siteleri merkezi siteden geçmeden diğer şube siteleriyle veri alışverişi yapamaz.
![hub-and-spoke](https://skorskyfiles.blob.core.windows.net/$web/articles/topolojiler/hub-and-spoke.png)
- ** Mesh - Örgü**
Bu topoloji yüksek kullanılabilirlik sağlar, ancak her uç sistemin diğer tüm sistemlerle birbirine bağlanmasını gerektirir. Dolayısıyla yönetimsel ve fiziksel maliyetler yüksek olabilir. Her bağlantı temelde diğer düğüme noktadan noktaya bağlantıdır.
![mesh](https://skorskyfiles.blob.core.windows.net/$web/articles/topolojiler/mesh.png)
> Hibrit, herhangi bir topolojinin bir varyasyonu veya kombinasyonudur. Örneğin, kısmi bir mesh, bazılarının, ancak hepsinin değil, uç aygıtlarının birbirine bağlı olduğu bir karma topolojidir.
## Half and Full-Duplex İletişim
LAN topolojilerini anlatırken dubleks iletişimi anlamak önemlidir, çünkü iki cihaz arasındaki veri iletiminin yönünü ifade eder. İki yaygın dubleks modu vardır.

### Half-duplex communication

Birbirine bağlanmış iki cihaz veri iletimi yaparken aynı anda hem veri gönderip hem veri alamaz. Sadece tek yönlü iletişim vardır. Veri göndermek için önce gelen verinin sonlanmasını beklemek zorundadır. . Ethernet hub'lu WLAN'lar ve eski veri yolu topolojileri tek yönlü modu kullanır. Tek Yönlü, paylaşılan medyada tek bir aygıtın aynı anda göndermesine veya almasına izin verir. 

### Full-duplex communication

Birbirine bağlanmış iki cihaz veri iletimi yaparken aynı anda hem veri gönderip hem veri alabilir. Çift yönlü iletişim vardır. Ethernet Switch'leri varsayılan olarak tam çift yönlü modda çalışır, ancak Ethernet hub'ı gibi bir aygıta bağlandığında tek yönlü olarak çalışabilirler.
![half-and-full-duplex](https://skorskyfiles.blob.core.windows.net/$web/articles/topolojiler/half_full_duplex.png)

Artık topolojileri biliyoruz sıra Ağ katmanında. Bir sonraki makalede görüşmek üzere