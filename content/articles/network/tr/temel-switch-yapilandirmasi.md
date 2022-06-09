---
tags:
  - "cisco"
  - "switch"
  - "switch-config"
description: "Temel switch yapılandırmalarını yapalım."
title: "Temel Switch Yapılandırması"
categories:
  - "network"
slug: "temel-switch-yapilandirmasi"
ID: "6849cc65-360b-46ca-afa0-006f3ee0dd81"
cover: "cover1.jpg"
date: "2022-06-09 12:00"
createdAt: 1654728343247
updatedAt: 1654728961997

---
## Switch Adını Değiştirelim

Bir switch yapılandırmaya başlarken ilk işimiz switch adını değiştirmek olmalıdır. Varsayılan olarak Cisco tarafından cihazlara <em>Switch</em> adı atanır. Sorun da tam olarak burada başlar. Bir ağda isim atanmamış tüm switchlerin adı aynı olduğunda uzaktan SSH ya da Telnet ile bağlanılan switchin hangi switch olduğunu anlamak karmaşık hale gelebilir.

Varsayılan isim, daha açıklayıcı bir isimle değiştirilmelidir. İsimler akıllıca seçildiğinde, ağ cihazlarını hatırlamak, belgelemek ve tanımlamak daha kolay olacaktır. Hostlar için bazı önemli isimlendirme yönergeleri şunlardır:

- Harf ile başlamalı
- Boşluk içermemeli
- Harf veya sayı ile bitmeli
- Sadece harf, sayı ve tireler kullanılmalı
- Uzunluğu 64 karakterden az olmalı

Aşağıda örnek bir switch adlandırması görmekteyiz. 

![örnek-switch-adlandırması](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/8bca2c1e-e069-4769-8f4c-9c513df32825/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220608%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220608T211755Z&X-Amz-Expires=86400&X-Amz-Signature=ae65ec7eb13e839b68921c2d02bc01810d9085d3deb45d78d8e8a93ad17e65ce&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22&x-id=GetObject)

İsimlendirmeler bu şekilde tanımlayıcı olduğu takdirde ilerleyen aşamalarda işimiz çok daha kolay hale gelecektir.

Bir switchin adını değiştirmek için global config modda iken <code>hostname</code> komutunun ardından verilmek istenen ismin girilmesi yeterlidir.

```
Switch# configure terminal
Switch(config)# hostname Sw-Floor-1
Sw-Floor-1(config)#
```

## Switch Modlarını Şifreleyelim
Bir cihaza ilk defa bağlandığımızda User EXEC modundayız demektir. Örnekte gösterildiği gibi <code>line console 0</code> komutunu kullanarak konsol yapılandırma moduna geçiş yapıyoruz. 0 olarak bahsettiğimiz ilk ve genelde tek olan cihaz üzerindeki konsol girişini ifade eder. 

Bu moda girdikten sonra <code>password</code> komutunu kullandıktan sonra vermek istediğimiz şifreyi girebiliriz. Son olarak <code>login</code> komutunu kullanarak User Exec modunu aktifleştirmemiz gerekiyor.

```
Sw-Floor-1# configure terminal
Sw-Floor-1(config)# line console 0
Sw-Floor-1(config-line)# password cisco
Sw-Floor-1(config-line)# login
Sw-Floor-1(config-line)# end
Sw-Floor-1#
```

Artık cihaz üzerinde bulunan konsol hattını şifreledik ancak cihaz üzerinde daha fazla yetkiye sahip olduğumuz Privileged modu da şifrelememiz güvenlik açısından elzem bir durumdur. Şimdi sıra privileged modda;

Privileged moda geçtikten sonra <code>enable secret</code> komutunun ardından istediğimiz şifreyi girebiliriz. 
```
Sw-Floor-1# configure terminal
Sw-Floor-1(config)# enable secret class
Sw-Floor-1(config)# exit
Sw-Floor-1#
```

Henüz işimiz bitmedi şimdi sıra Cisco Switchlerde bulunan SSH ve Telnet gibi uzaktan bağlantı yapmamıza olanak sunan sanal vty hatlarını şirelemekte. Çoğu Cisco cihazında 0-15 aralığında numaralandırılmış 16 adet sanal vty hattı yer alır.

Bu sanal hatları şifrelemek için global config modda iken <code>line vty 0 15</code> komutunu kullanarak vty config moda geçiş yapıyoruz. Daha sonra <code>password</code> komutunun ardından istediğimiz şifreyi verebiliriz. Hemen ardından <code>login</code>
komutunu kullanarak vty erişimini etkinleştiriyoruz.

```
Sw-Floor-1# configure terminal
Sw-Floor-1(config)# line vty 0 15
Sw-Floor-1(config-line)# password cisco 
Sw-Floor-1(config-line)# login 
Sw-Floor-1(config-line)# end
Sw-Floor-1#
```

Buraya kadar her şey çok güzel ancak cihaz üzerinde çalışan yapılandırma dosyasında varsayılan olarak verilen parolalar açık olarak yer almaktadır bu da üst düzey bir güvenlik açığı yaratmaktadır. Aşağıda encrypte edilmemiş yapılandırma dosyasını görmektesiniz. 
![şifresiz config](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/5cb85708-594f-480e-b6f8-7c4854476218/capture_20220609011538057.bmp?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220608%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220608T221616Z&X-Amz-Expires=86400&X-Amz-Signature=8cea65ba62d4a9a22415a954effbae7b13885ee52be28b118259b3874c9c0c8f&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22capture_20220609011538057.bmp%22&x-id=GetObject)

Görüldüğü üzere girilen tüm parolalar açıkça görülebilir halde şimdi bu parolaları encrypte edelim.

Global config moda girdikten sonra <code>service password-encryption</code> komutunu girdiğimiz zaman cihazda yer alan parolalar artık encrypte edilmiş hale gelir.

```
Sw-Floor-1# configure terminal
Sw-Floor-1(config)# service password-encryption
Sw-Floor-1(config)#
```

Cihazda çalışan yapılandırmayı görmek için <code>show running-config</code> ya da daha kısa hali olan <code>sh run</code> komutunu girdikten sonra enter tuşu ile biraz alt satırlara indiğimizde aşağıdaki gibi bir ekran ile karşılaşacağız. 
```
Sw-Floor-1(config)# end
Sw-Floor-1# show running-config
```
![encrypte password](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/d530255c-10cd-49e6-9371-1612dce60dd0/capture_20220609012157159.bmp?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220608%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220608T222232Z&X-Amz-Expires=86400&X-Amz-Signature=fae55173382260d8be969f313c2d0413e9c7f0d13b040feea6ed73d9450815f7&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22capture_20220609012157159.bmp%22&x-id=GetObject)

Artık şifrelerde encrypte olmuş halde. Durmak yok ilerlemeye devam. 

## Banner Mesajları Gösterelim
![banner](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/2cc48ce8-6fed-4517-867b-d905c7a9af8a/capture_20220609013000109.bmp?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220608%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220608T223112Z&X-Amz-Expires=86400&X-Amz-Signature=93f04bea494ea860d2ca6e0042d63b4126b95b5f487baa9be09a60d091187ea5&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22capture_20220609013000109.bmp%22&x-id=GetObject)

Cisco cihazına ilk eriştiğimizde yukarıdaki gibi bir banner mesajı verseydik güzel olmaz mıydı? Evet ben de aynı şekilde düşündüm. Hadi bir banner mesajı verelim.

Öncelikle global config moda geçtikten sonra <code>banner motd</code> komutundan sonra banner mesajı içerisinde yer almayacak özel bir karakteri ayraç olarak kullanarak mesajımızı giriyoruz. Daha anlaşılır olması için örnek verelim.
```
Sw-Floor-1# configure terminal
Sw-Floor-1(config)# banner motd !Authorized Access Only!
```

## Yapılandırmayı Kaydedelim
Switch üzerinde çeşitli değişiklikler yaptık çok güzel, fakat elektrik bağlantısı kesilirse ya da switch kapatılıp açılırsa ayarlar olduğu gibi korunacak mı? Hayır... Düzenlediğimiz ayarların geçici değil sürekli olmasını sağlamak için yapılandırma dosyasını Switch üzerinde bulunun NV-Ram'e kaydetmek gerekir. Hadi gelin bunu yapalım. 

Privileged moda geçtikten sonra <code>copy running-config startup-config</code> komutunu kullanırız. Burada geçen iki argümanı açıklamak gerekirse;

- running-config ⇒ Rastgele Erişimli Bellekte (RAM) saklanır. Geçerli yapılandırmayı yansıtır. Çalışan bir yapılandırma değiştirildiğinde Cisco cihazının çalışması derhal etkilenir. RAM uçucu hafızadır. Cihaz kapatıldığında veya yeniden başlatıldığında tüm içeriğini kaybeder. 
- startup-config . ⇒  NVRAM'de depolanan kaydedilmiş yapılandırma dosyasıdır. Cihazın açılışta veya yeniden başlatma sırasında kullanacağı tüm komutları içerir. Flash, cihaz kapatıldığında içeriğini kaybetmez.

```
Sw-Floor-1# show running-config
```
Son olarak başlangıç yapılandırmasına istenmeyen değişikler kaydedildiyse yine privileged moda geçerek <code>erase startup-config</code> komutunu kullanarak NV-Ram'de yer alan yapılandırma dosyasını silebiliriz. Cihaz yeniden başladığında varsayılan yapılandırma dosyası ile birlikte tekrar açılacaktır. 

Sonraki makalelerde görüşmek üzere hoşçakalın...
