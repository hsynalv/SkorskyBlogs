---
slug: "network-e-ilk-adım"
tags:
  - "topology"
  - "lan-wan"
categories:
  - "network"
description: "network'e ilk adım"
title: "Network'e İlk Adım"
ID: "d66535f8-4397-4e74-b221-2c2f9189b885"
cover: "network.png"
date: "2022-06-07 12:00"
createdAt: 1654939008965
updatedAt: 1654939810942

---
Çoook uzun sürecek bir makale serisine başlıyoruz. CCNA-1 eğitimine paralel gidecek olan makale serimiz siber güvenlik ve network security çalışmak isteyenlere ilk adım için mükemmer bir fırsat olacağına eminim. O zaman başlayalım

## Network Bileşenleri
Bir ağa bağlanan ve ağ iletişimine katılan tüm bilgisayarlar, ana bilgisayarlar (host) olarak adlandırılırlar. Host'lar uç cihazlar olarak adlandırılabilir. Bazı hostlar da istemciler olarak adlandırılır. Bununla birlikte, host terimi özellikle ağ üzerinde iletişim amacıyla bir numara atanan cihazları ifade eder. Bu numara, belirli bir ağdaki hostu tanımlar. Bu numaraya Internet Protokolü (IP) adresi denir. IP adresi, hostu ve bu hostun bağlı olduğu ağı tanımlar.

Sunucular, ağdaki diğer uç aygıtlara e-posta veya web sayfaları gibi bilgiler sunmalarını sağlayan yazılımlara sahip bilgisayarlardır. Her hizmet ayrı sunucu yazılımı gerektirir. Örneğin, bir sunucunun ağa web hizmetleri sunabilmesi için, web sunucu yazılımı gereklidir. Sunucu yazılımına sahip bir bilgisayar birçok farklı istemciye aynı anda hizmet sağlayabilir.

![host-and-server](https://skorskyfiles.blob.core.windows.net/$web/articles/gunumuzde-network/host-andserver.png)

### End Devices - Uç Cihazlar
Son kullanıcıların en çok tanık olduğu cihazlardır. Kullandığımız tüm bilgisayarlar istisnalar hariç birer uç cihaz olarak adlandırılır. Bir uç cihazı diğerinden ayırmak için ağdaki her uç cihazın bir adresi vardır. Uç cihaz iletişim başlattığında, mesajın nereye gönderileceğini belirtmek için hedef uç cihazın adresini kullanır.

Bir uç cihaz, ağ üzerinden iletilen bir mesajın kaynağı veya hedefidir. 
### Intermediary Devices - Aracı Cihazlar

Aracı cihazlar, bağımsız uç cihazları ağa bağlar. Bir Internetwork oluşturmak için birden fazla ağa bağlanabilirler. Bu aracı cihazlar, bağlanabilirliği sağlar ve verilerin ağ üzerinden akmasını sağlar.

Aracı cihazlar mesajların ağ boyunca alacağı yolu belirlemek için ağ bağlantıları hakkındaki bilgilerle birlikte hedef uç cihazın adresini kullanır.
![araci-cihazlar](https://skorskyfiles.blob.core.windows.net/$web/articles/gunumuzde-network/araci-cihazlar.png)
Aracı ağ aygıtları bu işlevlerin bir kısmını veya tümünü gerçekleştirir:

-   İletişim sinyallerini yeniden üretme ve yeniden iletme
-   Ağ boyunca ve ağlar arasında hangi yolların bulunduğu hakkında bilgileri sağlama
-   Hata ve iletişim arızalarını diğer cihazlara bildirime
-   Bağlantı arızası gerçekleştiğinde veriyi alternatif yollar üzerinden yönlendirme
-   Mesajların önceliklerine göre, mesajları sınıflandırma ve yönlendirme
-   Güvenlik ayarlarına göre veri akışını engelleme veya izin verme
### Network Media
İletişim medya aracılığıyla bir ağ üzerinden iletilir. Medya, mesajın kaynaktan hedefe geçtiği kanalı sağlar.

Modern ağlar cihazları birbirine bağlamak için öncelikle üç tür medya kullanır:

-   **Kablolardaki metal teller** ⇒ Veriler elektriksel impulslara kodlanır.
-   **Kablolardaki cam veya plastik lifler (fiber optik kablo)** ⇒Veriler ışık darbelerine kodlanır.
-   **Kablosuz iletim** ⇒ Veriler, elektromanyetik dalgaların spesifik frekanslarının modülasyonu yoluyla kodlanır.
![network-media
](https://skorskyfiles.blob.core.windows.net/$web/articles/gunumuzde-network/network-media.png)

## Network Topolojileri
Network bileşenlerini öğrendiğimize göre artık network topolojilerine bir adım atabiliriz ancak çoook daha detaylı ayrı bir makaleye hakeden bir konu olduğu için sadece göz atacağız. Bir network kuracağımız zaman bunu tıpkı bir kağıda diyagram ya da şekil çizer gibi göstermek işimizi çok kolaylaştıracaktır. Burada asıl amaç hangi cihaz hangi cihaza bağlı, nerede ve nasıl bağlı olduğunun cevabını verebilmektir. 

### Network Gösterimi
Bir topoloji çizeceğiz fakat hangi şekilleri kullanarak? Gelin bunun cevabına birlikte bakalım.
![network-gösterimi](https://skorskyfiles.blob.core.windows.net/$web/articles/gunumuzde-network/agin-g%C3%B6sterimi.png)

Yukarıda her bir bileşeni gösterirken yaygın olarak gösterilen çizimleri verilmiştir. Tabii arada her ne kadar benzer olsa da farklılıklar meydana gelebilir.
### Topoloji Diyagramları

Topoloji diyagramları, bir ağ ile çalışan herkes için zorunlu belgelerdir. Ağın nasıl bağlandığına dair görsel bir harita sunarlar. Fiziksel ve mantıksal olmak üzere iki tür topoloji diyagramı vardır.
**Fizksel Topoloji Diyagramları**
Fiziksel topoloji diyagramları, aracı cihazların fiziksel konumunu ve kablo kurulumunu gösterir. Bu cihazların bulunduğu odaların bu fiziksel topolojide etiketlendiğini görebilirsiniz.
![fiziksel-topoloji](https://skorskyfiles.blob.core.windows.net/$web/articles/gunumuzde-network/fiziksel-topoloji.png)
**Mantıksal Topoloji Diyagramları**
Mantıksal topoloji diyagramları, cihazları, portları ve ağın adresleme şemasını göstermektedir. Hangi uç cihazların hangi aracı cihazlara bağlandığını ve hangi medyanın kullanıldığını görebilirsiniz.
![mantiksal-topoloji](https://skorskyfiles.blob.core.windows.net/$web/articles/gunumuzde-network/mantiksal-topoloji.png)
## Network Türleri

Artık ağları oluşturan bileşenlere ve bunların fiziksel ve mantıksal topolojilerdeki gösterimlerine aşina olduğumuza göre birçok farklı ağ türüne geçebiliriz.

Network türleri aşağıdakilere göre büyük ölçüde değişiklik gösterir:

-   Kapsanan alanın boyutu
-   Bağlı kullanıcı sayısı
-   Mevcut hizmetlerin sayısı ve türleri
-   Sorumluluk alanı

En yaygın iki ağ altyapısı türü Local Area Network (LAN) ve Wide Area Network (WAN'lar) 'dir. LAN, küçük bir coğrafi bölgedeki kullanıcılara ve son cihazlara erişim sağlayan bir ağ altyapısıdır. LAN genellikle bir işletme, ev veya küçük işletme ağı içindeki bir departmanda kullanılır. WAN, genellikle daha büyük bir şirket veya telekomünikasyon servis sağlayıcısı tarafından sahip olunan ve yönetilen geniş bir coğrafi alanda diğer ağlara erişim sağlayan bir ağ altyapısıdır. 

### LAN ve WAN

**LAN'lar**

LAN, küçük bir coğrafi alana yayılan bir ağ altyapısıdır. LAN'ların belirli özellikleri vardır:
-   LAN'lar ev, okul, ofis binası veya kampüs gibi sınırlı bir alandaki uç cihazları birbirine bağlar.
-   LAN genellikle tek bir kuruluş veya birey tarafından yönetilir. Yönetimsel kontrol, ağ düzeyinde uygulanır, güvenlik ve erişim kontrol politikalarını yönetir.
-   LAN'lar şekilde gösterildiği gibi dahili uç cihazlara ve ara cihazlara yüksek hızlı bant genişliği sağlar.

**WAN'lar**

WAN, geniş bir coğrafi alana yayılan bir ağ altyapısıdır. WAN'lar genel olarak servis sağlayıcıları (SS) veya İnternet Servis Sağlayıcıları (İSS) tarafından yönetilir.

WAN'lar belirli özelliklere sahiptir:

-   WAN'lar LAN'ları şehirler, eyaletler, bölgeler, ülkeler veya kıtalar arası gibi geniş coğrafi alanlarda birbirine bağlar.
-   WAN'lar genellikle çoklu servis sağlayıcıları tarafından yönetilir.
-   WAN'lar genel olarak LAN'lar arasında daha düşük hızlı bağlantılar sunar.
![lan-wan](https://skorskyfiles.blob.core.windows.net/$web/articles/gunumuzde-network/lan-wan.png)
###  İnternet
İnternet, birbirine bağlı ağların dünya çapında bir koleksiyonudur (internetworks veya kısaca internet). 
![internet](https://skorskyfiles.blob.core.windows.net/$web/articles/gunumuzde-network/internet.png)
İnternet herhangi bir şahıs veya gruba ait değildir. Bu, çeşitli altyapı boyunca etkili iletişim sağlamak, tutarlı ve yaygın olarak tanınan teknolojilerin ve standartların uygulanmasının yanı sıra birçok ağ yönetimi kurumunun işbirliğini gerektirir. İnternet protokollerinin ve süreçlerinin yapısını ve standardizasyonunu sürdürmeye yardımcı olmak için geliştirilmiş kuruluşlar vardır. Bu kuruluşlar arasında İnternet Mühendisliği Görev Gücü (IETF), Atanmış İsimler ve Sayılar için İnternet Şirketi (ICANN) ve İnternet Mimarisi Kurulu (IAB) ve diğer birçok kuruluş yer almaktadır.
### İntranet ve Extranet
İnternet terimine benzer iki terim daha vardır: Intranet ve Extranet

Intranet, genellikle bir kuruluşa ait LAN ve WAN'ların özel bir bağlantısına atıfta bulunmak için kullanılan bir terimdir. Bir intranet, yalnızca kuruluşun üyeleri, çalışanları veya yetkilendirilmiş diğer kişiler tarafından erişilebilir olacak şekilde tasarlanmıştır. Örnek olarak bir üniversitede olduğunuzu düşünün farklı kampüslerde olsanız bile aynı network içerisinden çıkarak Internet'e çıkarsınız. Üniversite ağı Intranet örneğidir.

Bir kuruluş, farklı bir kuruluş için çalışan ancak kuruluşun verilerine erişmesi gereken kişilere güvenli erişim sağlamak için bir extranet kullanabilir. Extranetlerin bazı örnekleri şunlardır :

-   Dış tedarikçilere ve yüklenicilere erişim sağlayan bir şirket
-   Hastalarına randevu alabilmeleri için doktorlara rezervasyon sistemi sağlayan bir hastane
-   İlçesindeki okullara bütçe ve personel bilgisi sağlayan yerel bir eğitim ofisi
![intranet-extranet](https://skorskyfiles.blob.core.windows.net/$web/articles/gunumuzde-network/intranet.png)