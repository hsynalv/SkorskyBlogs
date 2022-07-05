---
slug: "vpn-ve-proxy-kavramlari"
categories:
  - "Siber Güvenlik"
  - "Network"
description: "vpn-ve-proxy-kavramlari"
ID: "2d388dec-28cb-488e-ba0d-c061510902a7"
title: "VPN ve Proxy Kavramları"
tags:
  - "VPN"
  - "Proxy"
cover: "vpn-proxy.png"
date: "2022-07-05 12:00"
createdAt: 1657048473930

---
## Proxy Nedir?
Proxy kavramını Türkçe'ye çevirmek istersek karşımıza *"Vekil Sunucu"* kavramı çıkacaktır. Türkçe anlamındaki gibi bizim yerimize vekil olarak çalışır yani bizi temsil eder. Son kullanıcı ile çevrimiçi bir kaynak arasında bir bağlantı kurarak bizi temsil eder, aracılık görevi görür. 

![proxy](https://skorskyfiles.blob.core.windows.net/$web/articles/proxy-vpn/VPN.png)

Doğrudan bir web sitesini ziyaret ettiğimiz zaman  kendimizle ilgili bazı bilgileri (kullandığımız bilgisayar, konum, IP adresi) içeren bir web isteği göndeririz. Buna karşılık olarak ise web kaynağı bize talep ettiğimiz içeriği sağlamakla yükümlüdür.

Proxy tabanlı bir bağlantı, gönderdiğiniz web talepleri ve web sitesinden geri alacağınız veriler için bir tür ağ geçidi sağlar. Proxy'ler web isteklerinizi gizleyebilir veya web sitesindeki içeriği filtreleyebilir. 

Proxy ile sağlanan bağlantılarda veri iletişimi **şifresiz** olarak gerçekleşir. **anonim olarak internette surf yapamazsınız** (bu vpn ile de tamamen mümkün değildir) Kullandığınız proxy sunucuları gizlilik taahhüt etse bile proxy sunucuna giderken gerçekleşen ağ trafiği ISP veya üçüncü bir kişi tarafından okunulabilir.

### Proxy Sunucu Nasıl Çalışır?

Bilgisayarınızın adresi İnternet Protokolü veya IP adresi olarak bilinir. Bu adres bilgisayarınıza özgüdür ve internetin hangi bilgisayara doğru verileri göndereceğini belirleme yöntemidir.

Proxy sunucuları, yalnızca bilgisayarınız tarafından bilinen kendi benzersiz IP adreslerine sahiptir. İnternet üzerinden bir istek gönderdiğinizde (bir web sayfasını açmak gibi), istek önce  proxy sunucusuna* gider. Proxy sunucusu daha sonra bu talebi internet üzerinden gönderir, yanıtı toplar ve verileri size iletir.

### Proxy Türleri Nelerdir?

Proxy sunucuları çevrimiçi gizliliğinizi sağlama türlerine göre üçe ayrılır:

1.  **Saydam (Transparent) Proxy Sunucuları:**  En çok tercih edilen ve ücretsiz olan proxy sunucular bu sınıftadır. En büyük handikabı ise IP gizleme işini tam anlamı ile gerçekleştirmemeleridir. İstenilmesi halinde, vekil sunucuya bağlandığınız IP adresi elde edilebilir. Ayrıca veri trafiği için herhangi bir şifreleme yoktur.
2.  **Anonim Proxy Sunucuları:**  IP adresinizi gizlemek amacı ile kullanılırlar. Bu konuda da yüksek oranda başarılıdırlar. Ayrıca hız bakımından da kullanıcıyı tatmin ederler. Fakat veri trafiğini şifreleme konusunda aynı başarıyı göstermiyor olmaları dezavantajlarından biridir. Ücretli, ücretsiz ve trafik kotalı seçenekleri bulunmaktadır.
3.  **Elit Proxy Sunucuları:**  Hem web trafiğinizi tamamen şifreleme, hem de IP adresinizi tamamen gizleme konusunda oldukça başarılı bir proxy sunucusu türüdür. Sınıfının en hızlı bağlantısını sağlar. Deneme süreleri hariç ücretsiz kullanmak mümkün değildir.

Bağlantı türüne göre de iki farklı proxy sunucusu bulunmaktadır:

1.  **HTTP (Web) Proxy Sunucuları:**  Genelde daha hızlı internet erişimi ve IP adresi gizleme amacı ile kullanılmaktadır. Sadece web sitelerini ziyaret etmek için kullanılır. HTTP protokolü dışında kalan (örneğin  [FTP](https://www.niobehosting.com/blog/ftp/)  protokolü gibi) hiçbir protokole bağlanmayı desteklemez. Yasaklı sitelere bağlanmak için en çok tercih edilen proxy sunucusu türüdür. Transparent, anonim ya da elit versiyonları kullanılabilir.
2.  **SOCKS Proxy Sunucuları:** FTP, SMTP gibi protokolleri destekler. HTTP proxy sunucularına göre daha yavaş çalışmaktadır. Bu sebeple çevrimiçi gerçek zamanlı oyun oynamak için uygun değildir. SMTP desteği olmasına rağmen, e-posta trafiğinde kullanmak için tavsiye edilmez.

### **Proxy Gizlilik Sağlar Mı?**

Proxy üzerinden bağlantılarımız o an gizlenmektedir ancak Proxy Server’larında sizin giriş talepleriniz ve ziyaretleriniz kayıt altına alınmaktadır. Herhangi kanunsuz bir işlem sonucunda kanun koyucular tarafından istenecek ziyaretçi bilgileri Proxy hizmeti verenler tarafından paylaşılabilir. Bu sebeple bu ziyaretler sizi kanuni açıdan yükümlülüklerden kurtarmayabilir.

Sadece kısıtlı sitelere ziyaret için kullanıyorsanız o kadar endişelenmeye gerek yok. Kanun koyucular, mahkeme kararı nedeniyle ziyaretçi bilgisi talepleri hariç, bu bilgileri istemeyecektir.

Kullanacağınız Proxy sitesinin  **SSL (Secure Socket Layer)**  yani güvenli giriş katmanı  sertifikası kullanıp kullanmadığına dikkat etmenizde fayda var, dikkat etmezseniz kişisel bilgileriniz kullanıcı adı ve şifre gibi bilgilerinizin çalınması ihtimali vardır. O yüzden internette ilk bulduğunuz ücretsiz Proxy bağlantısına tıklamayın, biraz araştırın. Link paylaşmak istemiyorum, çünkü güncellik konusunda sıkıntılar olabiliyor.

## VPN Nedir?

 Virtual Private Network olarak açılan VPN kavramının Türkçe karşılığı *Sanal Özel Ağ*'dır. En temel anlamıyla internete gerçek IP adresiniz gizlenip, farklı bir IP adresi üzerinden bağlanmanızı sağlayan hizmettir. VPN, bağlantınızı güvenli hale getirir ve herhangi bir ağa bağlanırken bağlantınızı şifreleyerek kimliğinizin tespit edilememesini de sağlar. Aradaki iletişim kriptolu olduğu ve sörf yaparken nereye gittiğinizin çözülememesi sebebiyle ülkenizdeki yasaklı, kısıtlanmış sitelere veya IP’lere yine VPN tünelleri üzerinden erişim sağlayabilirsiniz. VPN tüneli gönderdiğiniz, aldığınız tüm verileri kendisi şifrelediğinden 3. şahısların ne yaptığınızı görmesine izin vermeyen bir güvenlik sistemi olarak da kullanılabilir.

![vpn](https://skorskyfiles.blob.core.windows.net/$web/articles/proxy-vpn/VPN.png)

VPN, birçok farklı protokol ve teknolojiyi bir arada kullanmaktadır. Bir bilgisayardan karşı taraftaki diğer bilgisayar arasındaki iletişim kriptolama yapılarak güvenli bir tünel kurulması sağlanır.

Bu tünel içerisinden geçen veri şifrelendiği için araya giren veya girmeye çalışan kişiler yalnızca kriptolu veriyi görebileceği için güvenliğiniz sağlanmıştır. Bu kriptolama seviyesi ne kadar iyiyse gizliliğiniz de o kadar güvenli olur. Aynı zamanda tüm veri akışınızı (DNS istekleriniz de dahil olmak üzere) bu tünel içerisine aldığınız takdirde tam bir koruma sağlamış olursunuz.

Ancak değinmemiz gereken bir nokta var ki VPN trafiği VPN sunucusuna kadar okunulabilir değildir. Biraz daha açmak gerekirse VPN kullanarak internete çıktığınızı düşünecek olursak iki uç arasında şifrelenmiş bir tünelde veri trafiği sağlanır. Bu veri trafiği kullandığınız VPN sunucusu üzerinden geçerek ilerler. Sıkıntı da tam olarak burada başlayabilir. Sunucu verileri şifreleyebildiği gibi şifrelenmiş veriyi çözerek okuyabilir hatta loglama ile kayıt altına alabilir. Bu nedenle kullandığınız VPN sunucusuna dikkat etmekte yarar olacaktır.

### VPN nasıl çalışır?

VPN, IP adresinizi VPN ana bilgisayarı tarafından yönetilen özel olarak yapılandırılmış bir uzak sunucu üzerinden yeniden yönlendirerek maskeler. Yani siz internette VPN ile gezinirken VPN sunucusu verilerinizin kaynağı olur. Bu, İnternet Servis Sağlayıcınızın (ISP) ve üçüncü kişilerin ziyaret ettiğiniz web sitelerini veya gönderdiğiniz ve aldığınız verileri göremediği anlamına gelir. VPN, bütün verilerinizi "anlaşılamaz" hâle getiren bir filtreymiş gibi çalışır. Herhangi biri bu verileri ele geçirse bile kullanamaz.

### VPN Türleri Nelerdir?

1. **Uzaktan Erişim VPN**

Uzaktan erişim VPN, bir kullanıcının özel bir ağa bağlanmasına, hizmetlerine ve kaynaklarına uzaktan erişmesine izin verir. Kullanıcı ile özel ağ arasındaki bağlantı internet üzerinden gerçekleşir ve bağlantı tamamen güvenlidir.

Uzaktan Erişim VPN’ler çalışanlar ve evde VPN kullananlar için oldukça uygundur.

Bir şirket çalışanı seyahat ederken, şirketinin özel ağına bağlanmak ve özel ağdaki dosyalara ve kaynaklara uzaktan erişmek için VPN kullanır.

Ev kullanıcıları veya özel VPN kullanıcıları, internetteki bölgesel kısıtlamaları aşmak ve engellenen web sitelerine erişmek için öncelikle VPN hizmetine ihtiyaç duyar. İnternet güvenliği konusunda bilinçli kullanıcılar, internet güvenliğini ve gizliliklerini geliştirmek için VPN hizmetlerini de kullanır.

2. **Siteden Siteye VPN**

Siteden Siteye VPN, Yönlendiriciden Yönlendiriciye VPN olarak da adlandırılır ve daha çok şirketlerde kullanılır.

Farklı coğrafi konumlarda ofisleri olan şirketler, bir ofis konumunun ağını başka bir ofis konumundaki ağa bağlamak için Siteden siteye VPN kullanır. Aynı şirketin birden fazla ofisi Site-to-Site VPN türü kullanılarak bağlandığında buna Intranet tabanlı VPN denir.

Şirketler, başka bir şirketin ofisine bağlanmak için Siteden siteye VPN türünü kullandıklarında, buna Extranet tabanlı VPN denir. Temel olarak, Siteden siteye VPN, coğrafi olarak uzak ofislerdeki ağlar arasında sanal bir köprü oluşturur ve bunları İnternet aracılığıyla birbirine bağlar ve ağlar arasında güvenli ve özel iletişimi sağlar.

Siteden siteye VPN yönlendiriciden yönlendiriciye iletişimi temel aldığından, bu VPN türünde bir yönlendirici VPN İstemcisi, diğer yönlendirici ise VPN Sunucusu olarak işlev görür. İki yönlendirici arasındaki iletişim, yalnızca ikisi arasında kimlik doğrulama sağlandıktan sonra başlar.

## Proxy vs VPN

![proxy-vs-vpn](https://skorskyfiles.blob.core.windows.net/$web/articles/proxy-vpn/vpn-vs-proxy.bmp)

VPN ile Proxy arasındaki en temel fark yukarıdaki şekilde belirtilmiştir. Yine de biz biraz daha detaylı inceleyelim

VPN tüm web etkinliğini yeniden yönlendirir, ancak proxy’ler yeniden yönlendirmez. Proxy yalnızca proxy için yapılandırılmış olan cihazda çalışır ve VPN, tüm cihazlarda / uygulamalarda çalışan tüm cihazların güvenli olmasını sağlamak için uygulamaya sahip olur. Proxy’lerin çoğu, müşterinin gizliliğinin daha az korunacağı ve bilgilerin sızdırılabileceği anlamına gelen temel şifrelemeyi desteklemez. VPN’ler şifreleme sağlar ve istemcinin gizliliğini korumak için özel olarak tasarlanmıştır.

Kullanıcı yalnızca kısa bir süre için olan ve web sitesiyle herhangi bir bilgi paylaşmayı gerektirmeyen bir web sitesine erişmek istiyorsa, proxy en iyi seçim olacaktır. Kullanıcının güvenlik konusunda endişe duymadığı küçük görevler için proxy kullanmak en iyisidir. Çünkü VPN’lerin fiyatları yüksek ve bu dijital aracı bir kez kullanmak isteyen bir kullanıcı bunun için ödeme yapmamalı. Proxy’lerin çoğu güvensizdir, ancak ücretsizdir ve VPN’lerin çoğu tamamen güvenlidir, ancak bir bedeli vardır. Ücretsiz olanlara ise hiç değinmiyorum unutmayın bir hizmet beleşse ürün sizsinizdir :)

VPN’in güçlü şifrelemesinin kullanılması nedeniyle bağlantı hızı biraz düşebilir, ancak yine de çoğu proxy’den daha hızlı olacaktır. Proxy veya VPN seçmek söz konusu olduğunda, çok sayıda  şüpheli proxy ve VPN var, bu yüzden kullanıcı için iyi bir program seçmek gerekecektir.






