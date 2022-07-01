---
title: "Ağ Tehditleri"
slug: "ag-tehditleri"
tags:
  - "network-threat"
description: "ag-tehditleri"
categories:
  - "Siber Güvenlik"
  - "Network"
ID: "f714df12-432e-42c9-be19-3b2ccf5b7e73"
cover: "ag-tehditleri.png"
date: "2022-07-02"
createdAt: 1656693993640
updatedAt: 1656695187441

---
Zararlı yazılımlar hakkındaki makalemizden sonra şimdi sıra ağ tehditlerine geldi. En çok bilinen ve kullanılan bazı ağ tehditlerini biraz inceleyelim.

## Denial of Service (DoS) 
DoS saldırıları internete bağlı bir bilgisayarın sunmuş olduğu hizmetleri aksatma ya da kaynaklarını tüketerek çalışmasını durdurmak için yapılan en popüler ve tehlikeli saldırı türlerinden biridir. Hizmet reddi saldırısı olarak adlandırılır.

Siber güvenliğin *Gizlilik, Bütünlük ve Erişilebilirlik* ilkelerinden erişilebilirlik durumunu hedef alır. Sadece web sayfalarına yönelik değildir. MAC Flooding, ICMP Smurf, TCP SYN Flood, DHCP Startvation, DNS Flood HTTP GET Flood, SlowHTTP ve Slowloris DoS Ataklarına örnek olabilir.

Hizmet reddi saldırıları tekil bir kaynaktan geldiği zaman DoS, çoklu kaynaktan geldiği zaman ise Distributed Denial of Service (DDoS) olarak adlandırılır.

## Distributed Denial of Service(DDoS)

Dağıtılmış DoS Saldırısı (DDoS), DoS saldırısına benzer, ancak birden çok, eşgüdümlü kaynaktan kaynaklanır. Örneğin, bir tehdit aktörü, zombiler olarak bilinen virüslü ana bilgisayarlardan oluşan bir ağ oluşturur. Tehdit aktörü, zombilere kontrol mesajları göndermek için bir komut ve kontrol (CnC) sistemi kullanır. Zombiler sürekli olarak daha fazla ana bilgisayarı bot kötü amaçlı yazılımlarıyla tarar ve enfekte eder. Bot kötü amaçlı yazılımı, bir ana bilgisayara virüs bulaştırmak için tasarlanmıştır ve bu da onu CnC sistemi ile iletişim kurabilen bir zombi haline getirir. Zombi koleksiyonuna botnet denir. Hazır olduğunda, tehdit aktörü CnC sistemine zombilerin botnet'inin DDoS saldırısı gerçekleştirmesini emreder.

Aşağıda basit ölçüde animasyonlanmış bir DDoS saldırısını görmekteyiz.

![ddos-gif](https://skorskyfiles.blob.core.windows.net/$web/articles/network-threats/ddos.gif)

DDoS saldırılarını daha detaylı anlamamız için saldırı bileşenlerine göz atmamız gerekebilir. tabloda her bir bileşen kısaca açıklanmıştır.
| Bileşen| İşlevi |
|--|--|
| Zombie | Bu bileşen güvenliği ihlal edilmiş bir grup ana bilgisayarı (yani aracıları) ifade eder. Bu ana bilgisayarlar, robotlar (yani botlar) olarak adlandırılan kötü amaçlı kodları çalıştırır. Zombi kötü amaçlı yazılım sürekli olarak bir solucan gibi kendi kendine yayılmaya çalışır. |
| Bot | Botlar, bir ana bilgisayara virüs bulaştırmak ve bir işleyici sistemiyle iletişim kurmak için tasarlanmış kötü amaçlı yazılımlardır. Botlar ayrıca tuş vuruşlarını kaydedebilir, şifreleri toplayabilir, paketleri yakalayabilir ve analiz edebilir ve daha fazlasını yapabilir. |
| Botnet | Bu bileşen kendi kendine yayılan kötü amaçlı yazılımlar (yani botlar) kullanılarak enfekte olmuş ve işleyiciler tarafından kontrol edilen bir grup zombiyi ifade eder. |
| Handlers - İşleyici |   Bu, zombi gruplarını  **kontrol eden birincil komuta ve kontrol (CnC** veya  **C2)**  sunucusunu ifade eder. Bir botnet'in yaratıcısı, zombileri uzaktan kontrol etmek için Internet Relay Chat'i (IRC) veya C2 sunucusundaki bir web sunucusunu kullanabilir. |
| Botmaster |   Bu, botnet'i ve işleyicileri kontrol eden tehdit aktörüdür. |

## Pivoting
Direkt olarak erişim sağlanamayan hostlara aynı ağda yer alan diğer host/makineler üzerinden dolaylı olarak erişim sağlanması_ olarak ifade edilebilir. Böylece direkt erişimin olmadığı makineler de istismara açık hale gelir.
![pivoting](https://skorskyfiles.blob.core.windows.net/$web/articles/network-threats/pivoting.png)

Yukarıdaki görselde yeşil kutu içerisindeki makineler **eth1** ile aynı ağ içerisindedir. Ele geçirilmiş olan makine aynı zamanda **eth0** ile başka bir ağ içerisindedir. Saldırgan kendi sistemi üzerinden direkt olarak **eth1** ağına erişim sağlayamadığı için **10.10.10.129** IP adresine sahip makineye direkt olarak erişemeyecektir. Fakat bu noktada saldırgan; önce ele geçirmiş olduğu **192.168.197.147** IP adresli makineye erişim sağlayıp, sonra buradan **10.10.10.129** IP adresli makineye geçiş yaparak hedefine erişim sağlayabilir, diğer bir deyişle _pivoting_ gerçekleştirebilir.

## BitSquatting ve CyberSquatting
BitSquatting var olan kurum domainlerinin farklı ama en yakın hallerinin kötü amaçla kullanılmasıdır.

CyberSquatting ise var olan kurum domain adlarının aynısı ancak TLD (Top Level Domain) lerine yakın hallerini alarak son kullanıcıları tuzağa düşürme tekniğidir.

Bu konunun biraz daha anlaşılır olması açısından bir örnek verelim. Varsayalım ki facebook.com'a girmek istiyoruz ancak tarayıcımızdaki adres satırında focebook.com yazmakta. Yani ilk hecedeki a harfi yerine o harfi kullanılmış. Bu domaindeki bir değişim olduğundan BitSquatting olarak adlandırılır. Bir diğer özellik olarak tekrar adres satırımıza baktığımızda facebook.cam yazmakta domain bildiğimiz üzere facebook ancak .com yerine .cam uzantısı alınmış bu da CyberSquatting olarak adlandırılmakta.

Bu tür saldırılar şirketlerin engelleme gayreti sonucunda son dönemde azalmakta ancak yine de her zaman girdiğimiz sitenin adres satırındaki domainine ve uzantısına dikkat etmemiz gerekebilir.

## Sniffing ve Spoofing

Türkçe karışıklarına bakarak çok bir şey anlayamayacağımız iki siber güvenlik terimi ile karşı karşıyayız. sniffing koklama, spoofing ise aldatma demektir. Siber güvenlikte ise sniffing veri yolunu kesmek anlamına gelirken spoofing ise bir saldırı türüdür.

### Sniffing

Bir network ağı üzerinde yer alan veri akışını dinleyerek çözümler ve veriyi ele geçirmeyi amaçlar. Veri trafiği içerisinde yer alan paketleri ele geçirebilmek için o veriyi dinler. Sniffing bu koklama işini gerçekleştirmek için kullanılır. Pasif Sniffing ve aktif Sniffing olmak üzere iki çeşidi yer alır.

Pasif Siniffing HUB cihazı olan network ağlarında kullanılır. Ağ ortamında yer alan veriler birden fazla bilgisayara transfer edilir. Bu aşamada veri paketlerini koklamak daha kolay olur.

Aktif Sniffing ise, switch cihazlarının kullanıldığı sistemlerde tercih edilir. Sadece belirli bir MAC adresine gönderilen verilerin saldırganlar tarafından MAC adresini istemci gibi gösterip Switch cihazının beynini karıştırır. Bu şekilde Switch cihazının HUB olarak çalışmasını sağlar ve tüm portlardan veri çıkar.

### Spoofing

Spoofing (Aldatma) saldırılarında, güvenli olarak görünen kaynaktan paket gönderilerek alıcıyı aldatmaktır. Hedefinde yer alan sistemlerde saldırı yapabilmek için çeşitli yazılımlar kullanır. Birçok spoofing saldırı türü vardır biz ise en çok kullanılan türlerine bakalım.


**E-Mail Spoofing** ⇒  SMTP açıklarından faydalanarak e mail başlıklarının değiştirilmesiyle yapılır


**ARP Spoofing** ⇒ ARP Spoofing saldırısı yapacak kişi yerel ağı sahte paketler ile doldurur. Bu aşamada veriler alıcıya ulaşmadan önce saldırgana ulaşır. Bu aşamada saldırgan isterse verileri de bozabilir ya da değiştirebilir. Cihazın sahip olduğu IP adresi saldırı düzenlenen kişinin IP adresine benzer şekilde ayarlanır.
 

**MAC Spoofing** ⇒ Switch’in MAC tablosunun manipüle edilmesidir . Saldırganın bağlı olduğu porta, hedefin MAC’ini bildirmesiyle yapılır

**DNS Spoofing** ⇒ DNS sunucusundaki önbelleğin manüpile edilmesidir . RR’ların değiştirilerek cevapların yanıltılması ve yönlendirmeyle sonuçlanır

**URL Spoofing** ⇒ Farklı bir url adresi gönderilerek gerçekleşir. Eski internet tarayıcılarında işe yarayan bu yöntem, yeni tarayıcılarda işe yaramıyor. Bir saldırgan hedefinde olduğu kişiye benzer bir url linki göndererek eylemini gerçekleştirir.

**IP Spoofing** ⇒ Saldırganların bilgisayara yetkisiz erişim elde etme amacı ile kullanılan bir saldırı yöntemidir. Burada siber saldırganlar kendini gizleyerek saldırıyı gerçekleştirir. Veri paketlerini gönderirken farklı bir IP adresi ile değiştirerek gönderir. Farklı bir bilgisayardan gönderilmiş gibi gözükmesini sağlar.
Saldırı yapılan bilgisayar gerçek kaynağı göremez. Bu IP Spoofing saldırıları tüm protokollerde gerçekleştirilebilir. Sadece TCP protokollerini kullanan uygulamalarda IP Spoofing saldırısı gerçekleştirilemez.
UDP protokolünü kullanan uygulamalarda rahat bir şekilde saldırı girişiminde bulunulabilir. Bunun nedeni ise, TCP protokolünde üçlü el sıkışmasının zorunlu hale gelmesidir.

## Session Hijacking

Session Hijacking (oturum ele geçirme), bir kullanıcı oturumunun bir saldırgan tarafından ele geçirildiği bir saldırı türüdür. Bir oturum, örneğin bir uygulama hizmetine oturum açıldığında başlar ve oturum kapatıldığında sona erer. Saldırganın oturum çereziniz hakkında bilgi sahibi olma durumuna göre, saldırı, aynı zamanda çerez kaçırma veya çerez yan saldırısı olarak da adlandırılır. Bazen herhangi bir bilgisayar oturumu ele geçirilmesine rağmen, Session Hijacking en yaygın olarak tarayıcı oturumları ve web uygulamaları için geçerlidir.

Session Hijacking, bir saldırganın çoğu web sitesinde bir oturumu sürdürmek için kullanılan HTTP çerezlerini çalarak tehlikeye atılmış bir etkin oturumdan yararlanmasıyla gerçekleşir. Başka bir yol ise saldırganın belirli bir kullanıcının kimlik bilgilerini kullandığından, uzak bir web sunucusundaki bilgilere yetkisiz erişim elde etmek için etkin bir oturumun tahmin etmesidir. Oturum belirteci veya HTTP başlığının güvenliği manipıle edilebilir ve bunlar oturum koklama (Session Sniffing) ve siteler arası komut dosyası çalıştırma (XSS) saldırılarını içerir.

> Son dönemde bazı youtuber hesaplarının çalınması bu yöntem ile gerçekleştirilmişitr.

## Sosyal Mühendislik


Sosyal mühendislik, hedeflenen bir kurbanı hassas bilgi ve verilerini vermesi için psikolojik olarak manipüle etmeyi amaçlayan siber suçlular tarafından gerçekleştirilen bir dizi kötü niyetli faaliyettir.

Sosyal mühendislik özellikle ağ sistemlerinde, yazılımlarda ve işletim sistemlerindeki güvenlik açıklarından ziyade insan hatasına dayanır. Meşru kullanıcılar tarafından yapılan hatalar daha az tahmin edilebilir olduğundan, bunları tespit etmek, kötü amaçlı yazılım tabanlı izinsiz girişleri tespit etmekten daha zordur. 

## OWASP TOP 10

Buraya kadar birçok saldırı türü saydık. Peki günüöüzde en çok kullanılan saldırı türleri nelerdir. Bunu incelemek için OWASP'ten yardım alalım. Peki nedir OWASP?

**OWASP** açılımı Open Web Application Security Project olarak tanımlanır. Web uygulamalarındaki güvenlik açıklarının kapatılması ve bu uygulamaların güvenli bir şekilde korunmasını sağlamak için çalışmalar yapan özgür bir topluluktur. OWASP topluluğunun her üç ya da dört senede bir yenilediği OWASP Top 10 ismiyle o yıla ait en riskli güvenlik zafiyetlerini listeledikleri Top 10 listesi hazırlamaktadır. Ayrıca risklerini, etkilerini ve karşı önlemlerini de gösterir. En son OWASP güvenlik açıkları listesi 2021'de yayınlandı. 

- A1 Broken Access Control
- A2 Cryptographic Failures
- A3 Injection
- A4 Insecure Design
- A5 Security Misconfiguration
- A6 Vulnerable and Outdated Components
- A7 Identification and Authentication Failures
- A8 Software and Data Integrity Failures
- A9 Security Logging and Monitoring Failures
- A10 Server-Side Request Forgery

Bu açıkların her birinin bir başka makalemizde detaylı şekilde inceleyene dek görüşmek üzere

