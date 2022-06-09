---
title: "OSI Referans Modeli"
description: "Daha önceki makalemde anlattığım üzere protokoller bilgisayarların iletişimi için olmazsa olmazdır. Şimdi OSI Referans Modelini daha detaylı şekilde inceleyelim."
categories: []
slug: "osi-referans-modeli"
tags: []
ID: "fc5ebf74-0a07-4426-90f6-efd2ef75d9ac"
cover: "osi-model.png"
date: "2022-06-10 12:00"
createdAt: 1654814286182

---
Daha önceki makalemde anlattığım üzere protokoller bilgisayarların iletişimi için olmazsa olmazdır. Şimdi OSI Referans Modelini daha detaylı şekilde inceleyelim.

OSI'den önce firmalar kendilerine özel ağ sistemleri geliştirip bunları bir paket halinde müşteriye sunuyorlardı. Fakat bu çok pahalıydı ve dışarıya kapalı bir sistem oluşturmaktaydı. Aslında kendi içlerinde çok sağlıklı çalışabilmelerine karşın kendi dışındaki ağlarla iletişim kurmaları çok zor ya da imkânsızdı. Örneğin IBM işletim sistemleri, IBM network aygıtları kullanarak kendi aralarında iletişim kurabiliyorlardı.

Ağ sistemlerinde arzın talebi karşılayamaması ve ağ piyasasında donanım üreticilerinin baskısı sonucunda, ağ sistemlerinin işlevleri için standart bir modelin oluşturulması gerektiği anlaşıldı. Bu nedenle ISO (International Organization for Standardization) tarafından 1978 yılında bilgisayar ağları standardı olan OSI referans modeli ortaya konmuştur. İlk olarak 1978 yılında ortaya çıkarılan bu standart 1984 yılında yeniden düzenlenerek OSI (Open System Interconnection) referans modeli olarak yayınlanmıştır. Model yaygın olarak kabul görmüş ve network işlemi için bir kılavuz olmuştur. OSI Modeli sadece bir standarttır. Eskiden olduğu gibi isteyen kendi başına bir ağ iletişim modeli geliştirebilir. Ancak OSI modeli referans alınmadıysa diğer ağlarla iletişimi zor olacak değişik üreticiler bu ağ sistemi için donanım ve yazılım üretemeyecekler demektir. OSI referans modeli bilgisayar ağlarında iletişim ortamından (kablolu, kablosuz) kullanıcıya kadar olan işlemleri 7 katmana ayırmıştır.

Bu katmanlar sırasıyla;
1.  Physical (Fiziksel Katman)
2.  Data Link (Veri Bağlantı Katmanı)
3.  Network (Ağ Katmanı)
4.  Transport (Taşıma Katmanı)
5.  Session (Oturum Katmanı)
6.  Presentation (Sunu Katmanı)
7.  Application (Uygulama Katmanı)

![osi-reference-model](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/2f2e2410-4970-40a4-b800-45bc4441b78f/osi-referans_1.jpg?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45/20220609/us-west-2/s3/aws4_request&X-Amz-Date=20220609T220420Z&X-Amz-Expires=86400&X-Amz-Signature=3c6d2e25c22c52cf39a37d773348dbfa4f462f196bd599054fcd72a764355d0e&X-Amz-SignedHeaders=host&response-content-disposition=filename%20=%22osi-referans_1.jpg%22&x-id=GetObject)

OSI modeline göre veri uç cihazdan çıkarak her bir katmana uğrar ve fiziksel kablo aracılığı ile aynı katmanlardan yeniden geçerek server-host cihaza ulaşır.

Şimdi bu katmanlara biraz göz atalım. 

## 1-Physical layer (Fiziksel Katman)

Bilgisayar için her şey 1 ve 0'dır. Gönderilecek veri de 1 ve 0 lar olarak iletilir. Alıcı tarafta okunan sinyaller 1 ve 0 a dönüştürülürken; gönderici taraf 1 ve 0'ları elektrik sinyallerine çevirip kabloya yerleştirir.

Gönderim işleminden önce ortamın özelliklerine karar verilmelidir ki işte bu işlemi gerçekleştiren katman fiziksel katmandır. Kablolu bağlantı için kablo türü, kablosuz bağlantı için iletim kanalı seçimi vb. kararlar bu katmanda verilir. Bitler, elektrik, radyo sinyalleri, ışık gibi pek çok yolla gönderilebilir. İletimin gerçekleşmesi açısından önemli unsur ise taşıma ortamıdır. Taşıma ortamı hem alıcı hem gönderici için aynı olmalıdır. Elektriksel yolla iletilen veri radyo sinyalleri olarak alınırsa iletim düzgün şekilde gerçekleşemez. Taşıma ortamı iletim için tek unsur, tek şart değildir. Voltaj değeri veri iletim hızı gibi değerlerin de uygun şekilde tanımlanması gerekir.

> RS232, ATM, FDDI, gibi protokoller bu katmanda çalışır.
> Repeater cihazları, hub, kablolar, ethernet bu katman üzerinde çalışır

## 2-Data Link layer (Veri Bağlantı Katmanı)

-   Veri bağlantı katmanı fiziksel katmana erişmek ve kullanmak ile ilgili kuralları belirler.
-   Bu katmanda Ethernet ya da Token Ring olarak bilinen erişim yöntemleri çalışır ve bu erişim yöntemleri, verileri kendi protokollerine uygun olarak işleyerek iletebilirler.
-   Veriler ağ katmanından fiziksel katmana gönderilir. Bu aşamada veriler belli parçalara bölünür bu parçalarada frame diyoruz. Frame yani türkçesi ile çerçeve verilerin belli bir kontrol içinde göndermeyi sağlayan paketlerdir.
-   Veri bağlantı katmanının büyük bir bölümü network kartı içinde gerçekleşir.
-   Veri bağlantı katmanı ağ üzerindeki diğer bilgisayarları tanımlama, kablonun o anda kimin tarafından kullanıldığının tespiti ve fiziksel katmandan gelen verinin hatalara karşı kontrolü görevini yerine getirir.
-   Veri bağlantısı katmanı iki alt bölüme ayrılır:

Media Access Control (MAC) and Logical Link Control (LLC)

MAC alt katmanı veriyi hata kontrol kodu(CRC), alıcı ve gönderenin MAC adresleri ile beraber paketler ve fiziksel katmana aktarır. Alıcı tarafta da bu işlemleri tersine yapıp veriyi veri bağlantısı içindeki ikinci alt katman olan LLC’ye aktarmak görevi yine MAC alt katmanına aittir. LLC alt katmanı bir üst katman olan ağ katmanı için geçiş görevi görür. Protokole özel mantıksal portlar oluşturur (Service Access Points, SAPs gibi). Böylece kaynak makinada ve hedef makinada aynı protokoller iletişime geçebilir (örneğin TCP/IP←>TCP/IP). LLC ayrıca veri paketlerinden bozuk gidenlerin tekrar gönderilmesinden sorumludur. Flow Control yani alıcının işleyebileğinden fazla veri paketi gönderilerek boğulmasının engellenmesi de LLC’nin görevidir.

Ayrıca switch  2.katmanda çalışan bir cihazdır. Çünkü 2. katmanda tanımlı MAC adreslerini algılayabilirler ve bir porttan gelen veri paketini (yine elektrik sinyalleri halinde) sadece gerekli olan porta yönlendirirler. 

## 3-Network Layer (Ağ Katmanı)

Ağ katmanı veri paketine farklı bir ağa gönderilmesi gerektiğinde yönlendiricilerin yani routerların kullanacağı bilginin eklendiği katmandır. Bu katmanda veriler paket olarak taşınır.

-   Bu katman sayesinde veri router aracılığıyla yönlendirmesi sağlanır.
-   Switching and routing teknolojisi bu katmanda çalışır.
-   Veri paketini hedefe yönlendirilmesi ve iletilmesini sağlar.
-   Internetworking, error handling (hata işleme), congestion control ve packet sequencing (paket sıralama) bu katmanda çalışır.
>  TCP/IP, IPX, AppleTalk gibi farklı ağ protokolleri bu katmanda çalışır.

## 4-Transport Layer (Taşıma Katmanı)

Taşıma katmanı üst katmanlardan gelen veriyi ağ paketi boyutunda parçalara böler.

-   Taşıma katmanı alt katmanlar (Transport Set) ve üst katmanlar (Application Set) arasında geçit görevini üstlenir.
-   Bu katmanda veriler segment halinde taşınır.
-   Üst katmanlara taşıma servisi sağlamasınını yanında ayrıca ağın servis kalitesini (Quality pf Service) artırır.
-   Alt ve üst katmanların eş zamanlı ve stabil çalışabilmesini sağlar bu işleme _**multiplexing**_ denir
- En önemli görevi verinin uçtan uca iletimini ve zamanında ulaşıp ulaşmadığının kontrolünü sağlar
> TCP, UDP gibi protokoller bu katmadan çalışır.
# 5-**Session Layer (Oturum Katmanı)**

Oturum katmanı bir bilgisayar birden fazla bilgisayarla aynı anda iletişim içinde olduğunda, genelde böyle olur, oturum bilgilerini tutar ve doğru bilgisayar ile iletişim kurmamızı sağlar. Sunum katmanına yollanacak veriler farklı oturumlarla birbirinden ayrılarak yapılır.

Örneğin A bilgisayarı B üzerideki yazıcıya yazdırıken, C bilgisayarı B üzerindeki diske erişiyorsa, B hem A ile olan, hem de C ile olan iletişimini aynı anda sürdürmek zorundadır.

-   Oturum ve bağlantı koordinasyonu ile ilgilenir.
-   Uygulamalar arasındaki bağlantıların kurulması, yönetimi ve sonlandırılmasından sorumludur.
-   NetBIOS ve Sockets gibi protokoller farklı bilgisayarlarla aynı anda olan bağlantıları yönetme imkanı sağlarlar.
-   İletişimde problem olması halinde verinin baştan gönderilmemesi için veriye checkpoint’ler ekler. Aksaklık halinde ne kadarı gönderilmediği tespit edilerek sadece o kısım gönderilir.
- 
## 6-Presentation Layer (Sunum Katmanı)

Bu katmanın en önemli görevi gönderilecek olan verinin diğer bilgisayara anlaşılacak şekilde çevrilmesidir.

-   Sizin ekranınıza gelecek olan veriden sorumludur.
-   Datayı Encryption and decryption edilmesi bu katmadan gerçekleşir.
>  GIF, JPEG, TIFF, EBCDIC, ASCII vb. bu katmanda çalışır.

Bu katmanın görevi çoğunlukla network ile ilgili değildir. Bu katmanı aslen aynı dosyayı okuyabilen programlar kullanmaktır.

## 7-Application Layer (Uygulama Katmanı)

Uygulama katmanı, kullanıcıya en yakın olan katmandır. Bizler bu katmanda çeşitli programları kullanarak (Chrome, Firefox, Skype vb.) bu katman içerisinde veri oluşturabiliyoruz. 

-   Son kullanıcı ile uygulamalar arasındaki süreçleri destekler diyebiliriz.
-   Dosya aktarımları, mail ve diğer network yazılımı hizmetleri için uygulama hizmetinden sorumludur.
- Kullanıcın Google.com’u çağırdığını Presentation Layer’e bildirir.(Diğer katmanlarla tek ilişkisi budur)
>  FTP, HTTP, Telnet gibi protokoller burada çalışır.

## Kısaca

OSI kavramsal bir modeldir ne OSI yazılımı nede OSI donanımı diye birşey göremezsiniz. Ancak yazılım ve donanım üreticileri bu modelin tanımlandığı kurallar çevresinde üretim yaparlar ve bu sayede ürünler birbiri ile uyumlu olur.
