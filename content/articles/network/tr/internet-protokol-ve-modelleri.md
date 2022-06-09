---
tags:
  - "osi"
  - "tcp/ip"
  - "protokol"
ID: "4bfd6bc2-9bf5-458f-a384-5789e098f6db"
description: "Herkese merhabalar, bugün uzun soluklu bir seriye başlıyoruz. Ethernet prokolleri ve protokol paketleri nelerdir bunlara bakacağız. "
title: "İnternet Protokol ve Modelleri"
categories:
  - "network"
slug: "internet-protokol-ve-modelleri"
cover: "cover3.jpg"
date: "2022-06-09 19:00"
createdAt: 1654792441731
updatedAt: 1654792627042

---
Herkese merhabalar, bugün uzun soluklu bir seriye başlıyoruz. Ethernet prokolleri ve protokol paketleri nelerdir bunlara bakacağız. 

## Ağ Protokollerine Genel Bakış
Tıpkı insanların iletişiminde olduğu gibi bilgisayarlarda kendilerine özgü bir dil kullanır. Bizdeki dilin bilgisayarlardaki karşılığı protokol olarak adlandırılır ve her uç cihaz birbiriyle iletişim kurarken bu protokollere uymak zorundadır. 

Ağ protokolleri, cihazlar arasında mesaj alışverişi için ortak bir biçim ve kurallar kümesi tanımlar. Protokoller, yazılım, donanım veya her ikisinde de uç cihazlar ve aracı cihazlar tarafından uygulanır. Her ağ protokolünün kendi işlevi, biçimi ve iletişim kuralları vardır.

Tablo, bir veya daha fazla ağ üzerinden iletişimi etkinleştirmek için gereken çeşitli iletişim kuralları türlerini listeler.
|Protokol Türü|Açıklama  |
|--|--|
| Ağ İletişim Protokolleri | Ağ iletişim protkolleri, iki veya daha fazla cihazın bir veya daha fazla ağ üzerinden iletişim kurmasını sağlar. Ethernet teknolojileri ailesi IP, TCP, HTTP ve daha pek çok protokol içerir. |
|Ağ Güvenlik Protokolleri|Ağ güvenlik protokolleri, kimlik doğrulama, veri bütünlüğü ve veri şifreleme sağlamak için verileri korur. Güvenli protokol örnekleri arasında SSH, SSL ve TLS bulunur.|
|Yönlendirme Protokolleri|Yönlendirme protokolleri, yönlendiricilerin rota bilgilerini değiştirmesini, yol bilgilerini karşılaştırmasını ve ardından hedef ağa giden en iyi yolu seçmesini sağlar. seçmesini sağlar. Yönlendirme protokollerine örnek olarak Open Shortest Path First (OSPF) ve Border Gateway Protocol (BGP) verilebilir.|
|Hizmet Bulma Protokolleri|Hizmet bulma protokolleri, cihazların veya hizmetlerin otomatik olarak algılanması için kullanılır. Hizmet bulma protokollerine örnek olarak IP adresi tahsisi için hizmetleri keşfeden DHCP ve isimden IP adresine çeviri gerçekleştirmek için kullanılan DNS verilebilir.|

## Protokol Paketlerinin Gelişimi
Protokol paketi, kapsamlı ağ iletişim hizmetleri sağlamak için birlikte çalışan bir dizi protokoldür. 1970'lerden bu yana, bazıları standart bir kuruluş tarafından geliştirilmiş, bazıları ise çeşitli satıcılar tarafından geliştirilmiş olan birkaç farklı protokol paketi bulunmaktadır.

Günümüzde en çok bilinen iki protokol modeli OSI Referans Modeli ve TCP/IP Protokol Paketidir. 

## OSI Referans Modeli

OSI modeli (Open System Interconnection) yedi katmandaki protokolleri uygulamak için bir bilgisayar ağ çerçevesi tanımlar. Ağ oluşturma terimlerindeki bir protokol, bir tür müzakere ve iki ağ kuruluşu arasında kuraldır. OSI modelini ISO International Organization for Standardization geliştirmiştir. Amaç aslında iki bilgisayar arasındaki iletişimin nasıl olacağını tanımlamaktan başka bir şey değildir.

OSI öncesindeki dönemde, yalnızca bilgisayar donanımı üreten kuruluşlara özgü ağlar vardı. Bu ağların özellikleri, çoğunlukla yalnızca o üreticinin donanımının bağlanmasına izin verecek biçimde tanımlanmıştı. Onlardan ayrı olarak OSI, çeşitli üreticilerin ürünlerinin bağlanabileceği bir ağ için, bir sektör etkinliği olarak ortaya çıkmıştır. OSI Modeli herhangi bir donanım ya da bilgisayar ağı tipine göre değişiklik göstermemektedir. OSI’nin amacı ağ mimarilerinin ve protokollerinin bir ağ ürünü bileşeni gibi kullanılmasını sağlamaktır. OSI modeli 7 katmana ayrılmıştır.
Bu katmanları bir sonraki makalemizde daha ayrıntılı anlatacağım. 

## TCP/IP Protokol Paketi
TCP ve IP birleşerek TCP/IP protokol ailesini oluşturmaktadır. Bu sayede bilgisayarlar arasında birden fazla iletişim metodu kullanılabilmektedir. Bu iletişim sırasında kullanılan TCP/IP katmanları ise aşağıdaki gibi belirtilmiştir.

1. Katman – Uygulama
2. Katman – Taşıma
3. Katman – İnternet
4. Katman – Ağ

Günümüzde, TCP/IP protokol paketi birçok protokol içerir ve yeni hizmetleri desteklemek için gelişmeye devam eder. Daha popüler olanlardan bazıları şekilde gösterilmiştir.![tcp-ıp-protokol-paketi](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/70b7e71d-cdfd-44f8-a924-a1f0ddd5b0be/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220609%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220609T150718Z&X-Amz-Expires=86400&X-Amz-Signature=1e3bfefc2f1ebeb97d02d279aac85e14e75e5abc243ee082b36acd5aaf31ac02&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22&x-id=GetObject)

Yukarıda bahsedilen protokolleri her katman için biraz daha detaylı inceleyelim.

###   Application Layer - Uygulama Katmanı
##### Name System
- **DNS - Domain Name System** 
	skorskyblog.me gibi alan adlarını IP adreslerine çevirir.
##### Host Config
- **DHCPv4 - Dynamic Host Configuration Protocol v4** 
 IPv4 için DHCPv4 sunucusu, başlangıçta DHCPv4 istemcilerine IPv4 adresleme bilgilerini dinamik olarak atar ve artık ihtiyaç duyulmadığında adreslerin yeniden kullanılmasına izin verir.
 
-  **DHCPv6 - Dynamic Host Configuration Protocol V6** 
IPv6 için DHCPv6, DHCPv4'e benzer. DHCPv6 sunucusu, başlangıçta DHCPv6 istemcilerine IPv6 adresleme bilgilerini dinamik olarak atar.

-   **SLAAC - StateLess Address Auto Configuration**  
Bir aygıtın DHCPv6 sunucusu kullanmadan IPv6 adresleme bilgilerini almasını sağlayan bir yöntem.

#####  E-mail
-   **SMTP - Simple Mail Transfer Protocol**
İstemcilerin bir posta sunucusuna e-posta göndermesini sağlar ve sunucuların diğer sunuculara e-posta göndermesini sağlar.
 
-   **POP3 - Post Office Protocol 3**
İstemcilerin bir posta sunucusundan e-posta almasını ve e-postayı istemcinin yerel posta uygulamasına indirmesini sağlar.

-   **IMAP - Internet Message Access Protocol**
İstemcilerin, bir posta sunucusunda depolanan e-postalara erişebilmesinin yanı sıra sunucuda e-postaları da korumasını sağlar.

#####  File Transfer

-   **FTP - File Transfer Protocol** 
Bir hosttaki kullanıcının başka bir hosttaki dosyalara ağ üzerinden erişmesini veya aktarıp almasını sağlayan kuralları belirler. FTP güvenilirdir, bağlantı odaklı ve onaylı bir dosya dağıtım protokolüdür.

-   **SFTP - Secure File Transfer Protocol**
Secure Shell (SSH) protokolünün bir uzantısı olarak SFTP, dosya aktarımının şifrelendiği güvenli bir dosya aktarım oturumu oluşturmak için kullanılabilir. SSH, genellikle bir cihazın komut satırına erişmek için kullanılan güvenli uzaktan oturum açma yöntemidir.

-   **TFTP - Trivial File Transfer Protocol**
En iyi çaba gerektiren, onaylı olmayan dosya teslimi ile basit, bağlantısız bir dosya aktarım protokolü. FTP'den daha az ek yük kullanır.
#####  Web and Web Service

-   **HTTP - Hyper-Text Transfer Protocol**
World Wide Web'de metin, grafik görüntü, ses, video ve diğer multimedya dosyalarını alıp vermek için bir dizi kural.

-   **HTTPS** - World Wide Web üzerinden değiştirilen verileri şifreleyen güvenli bir HTTP formu.

-   **REST - Representational State Transfer**
Web uygulamaları oluşturmak için uygulama programlama arayüzlerini (API'ler) ve HTTP isteklerini kullanan bir web hizmeti.

###   Transport Layer - Taşıma Katmanı

##### Connection Oriented - Bağlantı Odaklı
- **TCP - Transmission Control Protocol**
Ayrı ana bilgisayarlarda çalışan süreçler arasında güvenilir iletişimi sağlar ve başarılı teslimatı doğrulayan güvenilir, onaylı iletimler sağlar.
##### Connectionless - Bağlantısız
- **UDP - User Datagram Protocol**
Bir hostta çalışan bir işlemin, başka bir hostta çalışan bir işleme paket göndermesini sağlar. Ancak, UDP başarılı datagram iletimini doğrulamaz.
### Internet Layer
 
##### Internet Protocol

-   **IPv4**
Taşıma katmanından ileti kesimlerini alır, iletileri paketler ve ağ üzerinden uçtan uca teslim etmek için paketleri adresler. IPv4, 32 bit adres kullanır.

-   **IPv6**
IPv4'e benzerdir ancak 128-bit adres kullanır.

-   **NAT - Network Address Translation**
Özel bir ağdaki IPv4 adreslerini, genel olarak benzersiz genel IPv4 adreslerine çevirir.

##### Messagign

-   **ICMPv4**
Paket dağıtımındaki hatalar hakkında bir hedef hosttan kaynak hosta geri bildirim sağlar.

-   **ICMPv6**
ICMPv4 ile benzer işlevsellik sağlar, ancak IPv6 paketleri için kullanılır.

-   **ICMPv6 ND**
Adres çözümlemesi ve yinelenen adres algılaması için kullanılan dört protokol iletisi içerir.

##### Routing Protocols

-   **OSPF - Open Shortest Path First**
OSPF açık standart bir iç yönlendirme protokolüdür.

-   **EIGRP - Interior Gateway Routing Protocol**
Gelişmiş İç Ağ Geçidi Yönlendirme Protokolü. Bant genişliği, gecikme, yük ve güvenilirliğe dayalı kompozit metrik kullanan, Cisco tescilli bir yönlendirme protokolü.

-   **BGP - Border Gateway Protocol**
Sınır Geçidi Protokolü. Internet Servis Sağlayıcıları (ISS) arasında kullanılan açık standart dış ağ geçidi yönlendirme protokolü. BGP aynı zamanda ISS'ler ile büyük özel müşterileri arasında yönlendirme bilgileri alışverişinde bulunmak için yaygın olarak kullanılmaktadır.

### Network Access Layer - Ağ Erişim Katmanı
    
##### Adress Resolution - Adres Çözümleme
    
- **ARP**
Adres Çözümleme Protokolü. IPv4 adresi ile donanım adresi arasında dinamik adres eşlemesi sağlar.
    
##### Data Link Prtocols - Veri Bağlantısı Protokolleri
    
- **Ethernet**
 Ağ erişim katmanının kablolama ve sinyalizasyon standartlarını tanımlar.
 
- **WLAN - Wireless Local Area Network**
2,4 GHz ve 5 GHz radyo frekanslarında kablosuz sinyal verme kurallarını tanımlar.