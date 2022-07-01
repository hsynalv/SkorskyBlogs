---
tags:
  - "cisco"
  - "first-step-to-switch"
description: "Cisco switch cihazlarına yapılandırmaya başlamak için switch ve IOS'u tanıyalım."
title: "Cisco Switch'e ilk Adım"
categories:
  - "Switch & Router"
  - "CCNA-1"
slug: "cisco-switch-e-ilk-adım"
ID: "1c86164b-7c68-4f8c-a9ab-c95ce427086b"
cover: "cover2.jpg"
date: "2022-06-08 12:00"
createdAt: 1654719373157
updatedAt: 1654728512525

---
Tüm ağ cihazlarının her birinde birer işletim sistemi olmak zorundadır. Cisco Switch cihazlarında ise IOS işletim sistemi vardır. (Apple IOS ile karıştırmayın :-))

Bu makalemizde ise bu temel kullanım için bu IOS işletim sistemini nasıl configüre edebiliriz onu anlatacağım.

Öncelikle Cisco Swicth cihazlarında herhangi bir GUI yok bu nedenle çoğu kişinin sevmediği ama biz network ve siber güvenlik ile uğraşan kişilerin sevdiği ve çokça aşina olduğu CLI ekranını kullanacağız 

## IOS CLI'a İlk Adımlar

Cisco IOS yazılımı bir güvenlik özelliği olarak, yönetim erişimini aşağıdaki gibi iki komut moduna ayırır:

<span style="color:green">User EXEC Mode (Kullanıcı EXEC Modu)</span>

- Bu mod sadece kısıtlı sayıda temel monitoring (izleme) komutlarına izin verir.
- Genellikle <em>yalnızca görüntüleme modu</em veya <em>enable mode</em> olarak adlandırılır.
- Cihaz yapılandırmasına herhangi bir değişiklik yapılmasına izil verilmez.
- CLI'da <code>SwitchAdı></code> ile gösterilir. 


<span style="color:green">Privileged EXEC Mode (Ayrıcalıklı Exec Modu)</span>

- Bu modda iken kullanıcı herhangi bir izleme komutunu kullanabilir, cihaza ait yapılandırma ve yönetim komutlarını yürütebilir.
- Global Config modu gibi daha yüksek yapılandırma modlarına sadece bu moddan giriş yapılabilir.
- CLI'da <code>SwitchAdı#</code> ile gösterilir. 

## Global Yapılandırma Modu ve Alt Yapılandırma Modları

Cisco switchlerini yapılandırmak için kullanıcının global yapılandırma modu olarak adlandırılan, global config moduna girmesi gerekir.

Global yapılandırma modunda, cihazın bir bütün olarak çalışmasını etkileyen CLI yapılandırma değişiklikleri yapılır. Global yapılandırma modu, <code>Switch(config)#</code> gibi cihaz adından sonra biten bir <em>(config)#</em> istemiyle tanımlanır.

Global Config moduna, diğer belirli yapılandırma modlarından önce erişilir. Kullanıcı global Config modundan farklı alt yapılandırma modlarına girebilir. Bu modların her biri, switchin belirli bir bölümünün veya işlevinin yapılandırılması için kullanılır. Alt yapılandırma modlarına iki örnek aşağıdaki gibidir.

- **Line Config Mode** ⇒ Konsol, SSH, Telnet veya AUX erişimini yapılandırmak için kullanılır.
- **Interface Config Mode** ⇒ Switch portunu veya Router ağ arayüzünü yapılandırmak için kullanılır.

CLI kullanırken hangi modda olduğumuzu o moda ait komut istemi aracılığı ile öğreniriz. Varsayılan olarak her komut istemi cihazın adı ile başlar, daha sonra ise hangi modda olduğunu belirten ifade yer alır. Örneğin;

- Global Config Mode ⇒ <code>SwitchAdı(config)#</code>
- Line Config Mode ⇒ <code>SwitchAdı(config-line)#</code>
- Interface Config Mode ⇒ <code>SwitchAdı(config-if)#</code>

## Switch Modları Arasında Gezinelim

Swicth modlarına girip çıkmak için özel komutlar kullanılır. User EXEC modundan Privileged EXEC moduna geçmek için <code>enable</code>komutu kullanılır. Kullanıcı EXEC moduna geri dönmek için ise Privileged EXEC modundayken <code>disable</code> komutunu kullanılır.

Global Config moduna girmek için Privileged EXEC modundayken <code>configure terminal</code> modunu kullanılır. Global Config moddan Privileged EXEC moduna geri dönmek için ie <code>exit</code> komutu kullanılır.

Birçok farklı alt yapılandırma modu vardır. Örneğin, Line Config moduna girmek için <code>line</code> komutu ve ardından erişmek istediğiniz yönetim line türünü ve numarasını kullanılır. Alt yapılandırma modundan çıkmak ve global yapılandırma moduna dönmek için exit komutu kullanılır.

```
Switch(config)# line console 0
Switch(config-line)# exit
Switch(config)#
```

Herhangi bir alt yapılandırma modundan, modlar hiyerarşisine göre bi üst moda geçmek için <code>exit</code> komutu dışında <code>end</code> komutu ve Ctrl+Z tuş kombinasyonu kullanılabilir.

Ayrıca bir alt yapılandırma modundan diğerine doğrudan da geçebiliriz. Bir arayüzü seçtikten sonra komut isteminin değiştiğine dikkat edelim

```
Switch(config-line)# interface FastEthernet 0/1
Switch(config-if)#
```

### Swicth modlarını daha hızlı değiştirelim

Sürekli configüre terminal gibi uzun mod değiştirme komutlarını kullanmak bazen can sıkıcı olabilir. Aşağıda sık kullanılan mod değiştirme komutlarının kısaltılmış verisyonlarını görebilirsiniz.
|Komut|Kısa hali
|-|-|
|enable|en|
|configure terminal|conf t|
|interface FastEthernet 0/1| int fa0/1|
|...|...|
İlerleyen makalelerde daha fazla komut göreceğiz merak etmeyin :)


