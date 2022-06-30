---
tags:
  - "osi"
  - "tcp/ip"
  - "protocol"
ID: "4bfd6bc2-9bf5-458f-a384-5789e098f6db"
description: "Herkese merhabalar, bugün uzun soluklu bir seriye başlıyoruz. Ethernet prokolleri ve protokol paketleri nelerdir bunlara bakacağız. "
title: "İnternet Protokol ve Modelleri"
categories:
  - "network"
slug: "internet-protokol-ve-modelleri"
cover: "internet-protokol.png"
date: "2022-06-09 19:00"
createdAt: 1654792441731
updatedAt: 1654900199480

---


Herkese merhabalar, bugün uzun soluklu bir seriye başlıyoruz. İnternet protokolleri ve protokol paketleri nelerdir bunlara bakacağız. 

## Ağ Protokollerine Genel Bakış
Tıpkı insanların iletişiminde olduğu gibi bilgisayarlarda kendilerine özgü bir dil kullanır. Bizdeki dilin bilgisayarlardaki karşılığı protokol olarak adlandırılır ve her uç cihaz birbiriyle iletişim kurarken bu protokollere uymak zorundadır. 

Ağ protokolleri, cihazlar arasında mesaj alışverişi için ortak bir biçim ve kurallar kümesi tanımlar. Protokoller, yazılım, donanım veya her ikisinde de uç cihazlar ve aracı cihazlar tarafından uygulanır. Her ağ protokolünün kendi işlevi, biçimi ve iletişim kuralları vardır.

Tabloda ağ üzerinde iletişim kurmak için gerekli protokoller listelenmiştir. Hadi onlara bakalım. 

|Protokol Türü|Açıklama  |
|--|--|
| Ağ İletişim Protokolleri | Ağ iletişim protkolleri, iki veya daha fazla cihazın bir veya daha fazla ağ üzerinden iletişim kurmasını sağlar. Ethernet teknolojileri ailesi IP, TCP, HTTP ve daha pek çok protokol içerir. |
|Ağ Güvenlik Protokolleri|Ağ güvenlik protokolleri, kimlik doğrulama, veri bütünlüğü ve veri şifreleme sağlamak için verileri korur. Güvenli protokol örnekleri arasında SSH, SSL ve TLS bulunur.|
|Yönlendirme Protokolleri|Yönlendirme protokolleri, yönlendiricilerin rota bilgilerini değiştirmesini, yol bilgilerini karşılaştırmasını ve ardından hedef ağa giden en iyi yolu seçmesini sağlar. seçmesini sağlar. Yönlendirme protokollerine örnek olarak Open Shortest Path First (OSPF) ve Border Gateway Protocol (BGP) verilebilir.|
|Hizmet Bulma Protokolleri|Hizmet bulma protokolleri, cihazların veya hizmetlerin otomatik olarak algılanması için kullanılır. Hizmet bulma protokollerine örnek olarak IP adresi tahsisi için hizmetleri keşfeden DHCP ve isimden IP adresine çeviri gerçekleştirmek için kullanılan DNS verilebilir.|

## Protokol Paketlerinin Gelişimi
Protokol paketi, kapsamlı ağ iletişim hizmetleri sağlamak için birlikte çalışan bir dizi protokoldür. 1970'lerden bu yana, bazıları standart bir kuruluş tarafından geliştirilmiş, bazıları ise çeşitli satıcılar tarafından geliştirilmiş olan birkaç farklı protokol paketi bulunmaktadır.

Günümüzde en çok bilinen iki protokol modeli OSI Referans Modeli ve TCP/IP Protokol Paketidir. 

## Katmanlı Model Kullanmanın Avantajları

Bir ağın nasıl çalıştığı gibi karmaşık kavramları açıklamak ve anlamak zor olabilir. Bu nedenle, bir ağın işlemlerini yönetilebilir katmanlara dönüştürmek için katmanlı bir model kullanılır.

Ağ protokollerini ve işlemlerini tanımlamak için katmanlı bir model kullanmanın faydaları şunlardır:

- Belirli bir katmanda işleyen protokoller uyarınca davrandıkları tanımlı bilgilere  üst ve alt katmanlarla tanımlı bir arayüze sahip olduğu için protokol tasarımına yardımcı olmak
- Farklı satıcıların ürünleri birlikte çalışabildiği için rekabeti teşvik etmek
- Bir katmandaki teknoloji veya yetenek değişikliklerinin yukarıdaki ve altındaki diğer katmanları etkilemesini önlemek
- Ağ işlevlerini ve yeteneklerini tanımlamak için ortak bir dil sağlamak

![tcpip-osi](https://skorskyfiles.blob.core.windows.net/$web/articles/internet-protokol-ve-modelleri/tcp-%C4%B1p-vs-osi.png)

## OSI Referans Modeli

OSI modeli (Open System Interconnection) yedi katmandaki protokolleri uygulamak için bir bilgisayar ağ çerçevesi tanımlar. Ağ oluşturma terimlerindeki bir protokol, bir tür müzakere ve iki ağ kuruluşu arasında kuraldır. OSI modelini ISO International Organization for Standardization geliştirmiştir. Amaç aslında iki bilgisayar arasındaki iletişimin nasıl olacağını tanımlamaktan başka bir şey değildir.

OSI öncesindeki dönemde, yalnızca bilgisayar donanımı üreten kuruluşlara özgü ağlar vardı. Bu ağların özellikleri, çoğunlukla yalnızca o üreticinin donanımının bağlanmasına izin verecek biçimde tanımlanmıştı. Onlardan ayrı olarak OSI, çeşitli üreticilerin ürünlerinin bağlanabileceği bir ağ için, bir sektör etkinliği olarak ortaya çıkmıştır. OSI Modeli herhangi bir donanım ya da bilgisayar ağı tipine göre değişiklik göstermemektedir. OSI’nin amacı ağ mimarilerinin ve protokollerinin bir ağ ürünü bileşeni gibi kullanılmasını sağlamaktır. OSI modeli 7 katmana ayrılmıştır.
Bu katmanları bir sonraki makalemizde daha ayrıntılı anlatacağım. 

## TCP/IP Protokol Paketi
TCP ve IP birleşerek TCP/IP protokol ailesini oluşturmaktadır. Bu sayede bilgisayarlar arasında birden fazla iletişim metodu kullanılabilmektedir. Bu iletişim sırasında kullanılan TCP/IP katmanları ise aşağıdaki gibi belirtilmiştir.

- **1.Katman – Application layer - Uygulama katmanı**
Uygulama katmanında, veri paketini göndermek isteyen uygulama ve kullandığı dosya biçimi tespit edilerek gönderilen veri paketinin türüne göre farklı protokoller devreye girer (HTTP, SMTP, FTP, Telnet, vs.) ve programlarla Taşıma protokollerinin haberleşmesi sağlanır. Ardından görev artık Taşıma katmanındadır. Taşıma katmanıyla da iletişim portlar aracılığıyla gerçekleşir.
- **2.Katman – Transport layer -Taşıma katmanı**
Taşıma katmanı aslında uçtan uca iletişim ile ilgilenen katmandır. Yani verinin nasıl gönderileceği belirlenir. Ayrıca veri güvenliği ve hata kontrolü gibi işlemler bu katmanda yapılır. TCP ve UDP protokolleri bu katmanda çalışır. Taşıma katmanı, veri paketi gönderirken İnternet katmanı ile veri alırken de Uygulama katmanı ile iletişim halindedir.
- **3.Katman – Internet layer - İnternet katmanı**
Bu katmanda verinin kaynaktan hedefe yönlendirilmesi sağlanır. Kaynak IP adresi bu katmanda veriye eklenir. Genel olarak bu katman ağdaki verilen paketlenmesinden, ele alınmasından ve yönlendirilmesinden sorumludur.
- **4. Katman – Network layer - Ağ katmanı**
Ağ Erişim Katmanı, fiziksel ağa erişim sağlar yani gönderilen verilen son durağıdır. Verilerin fiziksel olarak 1 ve 0’lara dönüştürülerek taşınması sağlanır. Ethernet, FDDI, Token Ring, ATM, OC, HSSI ve hatta Wi-Fi, tüm ağ ara yüzlerine örnektir. Ethernet Ağ Arayüzü Katmanında kullanılan ve veri iletiminin fiziksel görünümünü sağlayan en yaygın kablolu yerel ağ teknolojisidir.

Günümüzde, TCP/IP protokol paketi birçok protokol içerir ve yeni hizmetleri desteklemek için gelişmeye devam eder. Daha popüler olanlardan bazıları şekilde gösterilmiştir.

![tcp-ıp-protokol-paketi](https://skorskyfiles.blob.core.windows.net/$web/articles/internet-protokol-ve-modelleri/tcp-%C4%B1p-protokol-paketi.png)

Yukarıda bahsedilen protokolleri her katman için biraz daha detaylı inceleyelim.

###   Application Layer - Uygulama Katmanı

**Name System**

- **DNS - Domain Name System** 
skorskyblog.me gibi alan adlarını IP adreslerine çevirir.

**Host Config - Host Yapılandırma**

- **DHCPv4 - Dynamic Host Configuration Protocol v4** 
 IPv4 için DHCPv4 sunucusu, başlangıçta DHCPv4 istemcilerine IPv4 adresleme bilgilerini dinamik olarak atar ve artık ihtiyaç duyulmadığında adreslerin yeniden kullanılmasına izin verir.
 
-  **DHCPv6 - Dynamic Host Configuration Protocol V6** 
IPv6 için DHCPv6, DHCPv4'e benzer. DHCPv6 sunucusu, başlangıçta DHCPv6 istemcilerine IPv6 adresleme bilgilerini dinamik olarak atar.

-   **SLAAC - StateLess Address Auto Configuration**  
Bir aygıtın DHCPv6 sunucusu kullanmadan IPv6 adresleme bilgilerini almasını sağlayan bir yöntem.

**E-mail**

-   **SMTP - Simple Mail Transfer Protocol**
İstemcilerin bir posta sunucusuna ve sunucuların diğer sunuculara e-posta göndermesini sağlar.
 
-   **POP3 - Post Office Protocol 3**
İstemcilerin bir posta sunucusundan e-posta almasını ve e-postayı istemcinin yerel posta uygulamasına indirmesini sağlar.

-   **IMAP - Internet Message Access Protocol**
İstemcilerin, bir posta sunucusunda depolanan e-postalara erişebilmesinin yanı sıra sunucuda e-postaların korumasını da sağlar.

**File Transfer - Dosya Transferi**

-   **FTP - File Transfer Protocol** 
Bir hosttaki kullanıcının başka bir hosttaki dosyalara ağ üzerinden erişmesini veya aktarmasını sağlayan kuralları belirler. FTP güvenilirdir, bağlantı odaklı ve onaylı bir dosya dağıtım protokolüdür.

-   **SFTP - Secure File Transfer Protocol**
Secure Shell (SSH) protokolünün bir uzantısı olarak SFTP, dosya aktarımının şifrelendiği güvenli bir dosya aktarım oturumu oluşturmak için kullanılabilir. SSH, genellikle bir cihazın komut satırına erişmek için kullanılan güvenli uzaktan oturum açma yöntemidir.

-   **TFTP - Trivial File Transfer Protocol**
En iyi çaba gerektiren, onaylı olmayan dosya teslimi ile basit, bağlantısız bir dosya aktarım protokolü. FTP'den daha az ek yük kullanır.

**Web and Web Service**

-   **HTTP - Hyper-Text Transfer Protocol**
World Wide Web'de metin, grafik görüntü, ses, video ve diğer multimedya dosyalarını alıp vermesini sağlayan bir dizi kurallar bütünüdür.

-   **HTTPS** - World Wide Web üzerinden değiştirilen verileri şifreleyen güvenli bir HTTP formudur.

-   **REST - Representational State Transfer**
Web uygulamaları oluşturmak için uygulama programlama arayüzlerini (API'ler) ve HTTP isteklerini kullanan bir web hizmetidir.

###   Transport Layer - Taşıma Katmanı

**Connection Oriented - Bağlantı Odaklı**

- **TCP - Transmission Control Protocol**
Ayrı ana bilgisayarlarda çalışan süreçler arasında güvenilir iletişimi sağlar ve başarılı teslimatı doğrulayan güvenilir ve onaylı iletimler sağlar.

**Connectionless - Bağlantısız**

- **UDP - User Datagram Protocol**
Bir hostta çalışan bir işlemin, başka bir hostta çalışan bir işleme paket göndermesini sağlar. Ancak, UDP başarılı iletimini doğrulamaz.

###   Internet Layer - İnternet Katmanı
 
**Internet Protocol - Internet Protokolü**

-   **IPv4**
Taşıma katmanından ileti kesimlerini alır, iletileri paketler ve ağ üzerinden uçtan uca teslim etmek için paketleri adresler. IPv4, 32 bit adres kullanır.

-   **IPv6**
IPv4'e benzerdir ancak 128-bit adres kullanır.

-   **NAT - Network Address Translation**
Özel bir ağdaki IPv4 adreslerini, genel olarak benzersiz genel IPv4 adreslerine çevirir.

**Messagign - Mesajlaşma**

-   **ICMPv4**
Paket dağıtımındaki hatalar hakkında bir hedef hosttan kaynak hosta geri bildirim sağlar.

-   **ICMPv6**
ICMPv4 ile benzer işlevsellik sağlar, ancak IPv6 paketleri için kullanılır.

-   **ICMPv6 ND**
Adres çözümlemesi ve yinelenen adres algılaması için kullanılan dört protokol iletisini içerir.

**Routing Protocols - Yönlendirme Protokolleri**

-   **OSPF - Open Shortest Path First**
OSPF açık standart bir iç yönlendirme protokolüdür.

-   **EIGRP - Interior Gateway Routing Protocol**
Bant genişliği, gecikme, yük ve güvenilirliğe dayalı kompozit metrik kullanan, Cisco tescilli bir yönlendirme protokolüdür.

-   **BGP - Border Gateway Protocol**
Internet Servis Sağlayıcıları (ISS) arasında kullanılan açık standart dış ağ geçidi yönlendirme protokolüdür. BGP aynı zamanda ISS'ler ile büyük özel müşterileri arasında yönlendirme bilgileri alışverişinde bulunmak için yaygın olarak kullanılmaktadır.

### Network Access Layer - Ağ Erişim Katmanı
    
**Adress Resolution - Adres Çözümleme**
    
- **ARP**
Adres Çözümleme Protokolü. IPv4 adresi ile donanım adresi arasında dinamik adres eşlemesi sağlar.
    
**Data Link Prtocols - Veri Bağlantısı Protokolleri**
    
- **Ethernet**
 Ağ erişim katmanının kablolama ve sinyalizasyon standartlarını tanımlar.
 
- **WLAN - Wireless Local Area Network**
2,4 GHz ve 5 GHz radyo frekanslarında kablosuz sinyal verme kurallarını tanımlar.

Hangi katmanda hangi protokol var öğrendik şimdi sıra bu katmanlar ne işe yarıyor ona bakalım. Ama o da bir başka makalenin konusu olsun. :)