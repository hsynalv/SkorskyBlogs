---
tags:
  - "cisco"
  - "switch"
  - "switch-config"
description: "Temel switch yapılandırmalarını yapalım."
title: "Temel Switch Yapılandırması"
categories:
  - "Switch & Router"
  - "Cisco CCNA-1"
slug: "temel-switch-yapilandirmasi"
ID: "6849cc65-360b-46ca-afa0-006f3ee0dd81"
cover: "cover1.jpg"
date: "2022-06-09 12:00"
createdAt: 1654728343247
updatedAt: 1654900801500

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

![örnek-switch-adlandırması](https://skorskyfiles.blob.core.windows.net/$web/articles/temel-switch-yapilandirmasi/ornek-adlandirma.png)

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
Sw-Floor-1(config-line)# password skorskyblog
Sw-Floor-1(config-line)# login
Sw-Floor-1(config-line)# end
Sw-Floor-1#
```

Artık cihaz üzerinde bulunan konsol hattını şifreledik ancak cihaz üzerinde daha fazla yetkiye sahip olduğumuz Privileged modu da şifrelememiz güvenlik açısından elzem bir durumdur. Şimdi sıra privileged modda;

Privileged moda geçtikten sonra <code>enable secret</code> komutunun ardından istediğimiz şifreyi girebiliriz. 
```
Sw-Floor-1# configure terminal
Sw-Floor-1(config)# enable secret skorsky
Sw-Floor-1(config)# exit
Sw-Floor-1#
```

Henüz işimiz bitmedi şimdi sıra Cisco Switchlerde bulunan SSH ve Telnet gibi uzaktan bağlantı yapmamıza olanak sunan sanal vty hatlarını şirelemekte. Çoğu Cisco cihazında 0-15 aralığında numaralandırılmış 16 adet sanal vty hattı yer alır.

Bu sanal hatları şifrelemek için global config modda iken <code>line vty 0 15</code> komutunu kullanarak vty config moda geçiş yapıyoruz. Daha sonra <code>password</code> komutunun ardından istediğimiz şifreyi verebiliriz. Hemen ardından <code>login</code>
komutunu kullanarak vty erişimini etkinleştiriyoruz.

```
Sw-Floor-1# configure terminal
Sw-Floor-1(config)# line vty 0 15
Sw-Floor-1(config-line)# password skorsky-line
Sw-Floor-1(config-line)# login 
Sw-Floor-1(config-line)# end
Sw-Floor-1#
```

Buraya kadar her şey çok güzel ancak cihaz üzerinde çalışan yapılandırma dosyasında varsayılan olarak verilen parolalar açık olarak yer almaktadır bu da üst düzey bir güvenlik açığı yaratmaktadır. Aşağıda encrypte edilmemiş yapılandırma dosyasını görmektesiniz. 
![şifresiz config](https://skorskyfiles.blob.core.windows.net/$web/articles/temel-switch-yapilandirmasi/sifresiz-config.png)

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
![encrypte password](https://skorskyfiles.blob.core.windows.net/$web/articles/temel-switch-yapilandirmasi/sifreli-config.png)

Artık şifrelerde encrypte olmuş halde. Durmak yok ilerlemeye devam. 

## Banner Mesajları Gösterelim
![banner](https://skorskyfiles.blob.core.windows.net/$web/articles/temel-switch-yapilandirmasi/banner.png)

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
