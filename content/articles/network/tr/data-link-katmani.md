---
categories:
  - "network"
title: "Data Link Katmanı"
tags:
  - "osi"
  - "data-link-layer"
slug: "data-link-katmani"
description: "data link katmanını inceliyoruz."
ID: "0fc4ee6c-0c02-4817-870c-3c571bd9652c"
cover: "Data-Link-Layer.jpg"
date: "2022-06-12 12:00"
createdAt: 1654983046596
updatedAt: 1654983415568

---

## Data Link Katmanının Amacı
OSI modeline göre Data Link Layer (2. katman) ağ verilerini fiziksel ağ için hazırlar. data link katmanı, ağ arayüz kartından (NIC) ağ arayüz kartına iletişiminden sorumludur. data linkkatmanı aşağıdakileri yapar:

-   Üst katmanların medyaya erişmesini sağlar . Üst katman protokolleri cihazların hangi fiziksel bağlantı yoluyla bağlandığını bilmez, bu nedenle bağlantı medyasına göre hareket eden katman data link katmanıdır.
-   Verilere  genellikle 3.Katman paketlerini (örn. IPv4 veya IPv6) ekler ve bunları 2.Katman frame'lerine kapsüller.
-   Verilerin medyaya nasıl yerleştirildiğini ve alındığını kontrol eder.
-   Ağ medyası üzerinden, uç noktalar arasında frame'leri değiş tokuş eder.
-   Kapsüllenmiş verileri içerisine genellikle 3.Katman paketlerini alır ve bunları uygun olan üst katman protokolüne yönlendirir.
-   Hata algılaması gerçekleştirir ve bozuk frame'leri reddeder.
- Kısaca gelen verileri fiziksel katman için hazırlar. Giden verileri ise üst katmanlar için hazırlar.

Bilgisayar ağlarında düğüm, bir iletişim yolu boyunca veri alabilen, oluşturabilen, depolayabilen veya iletebilen bir aygıttır. Düğüm, dizüstü bilgisayar veya cep telefonu gibi bir uç aygıtı veya Ethernet switchi gibi bir aracı aygıt olabilir.

Data link katmanı olmadan, IP gibi ağ katmanı protokolleri, bir teslimat yolu boyunca var olabilecek her tür medyaya bağlanmak için hazırlık yapmak zorundadır. Ayrıca, her yeni bir ağ teknolojisi veya medyası geliştirildiğinde, IP'nin buna uyum sağlaması gerekir.

Aşağıdaki şekilde 3. katman olan ağ katmanından gelen veri paketine 2. katman başlığını(Ethernet hedefi ve kaynak NIC bilgisi) eklemesini görmekteyiz. Bu işlemden sonra fiziksel katman tarafından desteklenen bir biçime dönüştürerek fiziksel katmana iletir.

![data-link-layer](https://skorskyfiles.blob.core.windows.net/$web/articles/data-link-layer/data-link.png)

## EEE 802 LAN/MAN Data Link Alt Katmanları

IEEE 802 LAN/MAN standartları Ethernet LAN'larına, kablosuz LAN'lara (WLAN), kablosuz kişisel alan ağlarına (WPAN) ve diğer yerel ve metropol alan ağlarına özgüdür. IEEE 802 LAN/MAN data link katmanı aşağıdaki iki alt katmandan oluşur:

-   **Mantıksal Bağlantı Kontrolü (LLC)** 
 Bu IEEE 802.2 alt katmanı üst katmanlardaki ağ yazılımı ile alt katmanlardaki aygıt donanımı arasında iletişim kurar. Frame için hangi ağ katmanı protokolünün kullanıldığını tanımlayan bilgileri frame'e yerleştirir. Bu bilgiler, IPv4 ve IPv6 gibi birden çok 3. Katman protokolünün aynı ağ arayüzünü ve medyasını kullanmasını sağlar.
 
-   **Media Access Controller Address (MAC)** 
 Bu katman bizim mac adresi diye bildiğimiz alt katmandır ve donanıma uygulanır. Encapsulation' dan sorumludur. Data link katmanı için adresleme sağlar ve bazı fiziksel katman teknolojileri ile birlikte hareket eder.

MAC alt katmanı encapsulation işlemini şu şekilde yapar:

-   **Frame sınırlama**  ⇒ Bir frame içindeki alanları tanımlamak için önemli sınırlayıcılar sağlar. Bu sınırlayıcı bitler, verici ve alıcı düğümler arasında senkronizasyon sağlar.
-   **Adresleme**  ⇒ 2.Katman frame'inin aynı paylaşılan medyadaki aygıtlar arasında taşınması için kaynak ve hedef adresleme sağlar.
-   **Hata algılama**  ⇒ İletim hatalarını algılamak için kullanılan bir artbilgi içerir.

MAC alt katmanı, birden fazla cihazın paylaşılan (yarı çift yönlü) bir medya üzerinden iletişim kurmasına izin vererek medya erişim kontrolü de sağlar. Tam çift yönlü iletişim erişim kontrolü gerektirmez.

## Frame
Data link katmanı, kapsüllenmiş verileri (genellikle bir IPv4 veya IPv6 paketi), başlık ve artbilgiyle birlikte frame oluşturacak şekilde kapsülleyerek, yerel medya üzerinden aktarım için hazırlar.

data link protokolü, aynı ağ içindeki NIC-NIC iletişimlerinden sorumludur.data link katmanı frame'lerini tanımlayan birçok farklı data link katmanı protokolü bulunmasına rağmen, her frame türü üç temel parçaya sahiptir:

-   Başlık
-   Veri
-   Artbilgi

Diğer kapsülleme protokollerinden farklı olarak, data link katmanı frame'inin sonuna artbilgi şeklinde bir bilgi ekler.
## Frame Alanları
Encapsulation, kontrol bilgilerini başlık ve artbilgiye farklı alanlardaki değerler olarak yerleştirerek kesintisiz yayını çözülebilir gruplara ayırır. Bu format, fiziksel sinyallere düğümler tarafından tanınan ve hedefte paketler halinde kodu çözülen bir yapı verir.

Genel frame alanları şekilde gösterilmiştir. Tüm protokoller bu alanların tümünü içermez. Belirli bir data link protokolüne yönelik standartlar gerçek frame biçimini belirler.
![frame-alanlari](https://skorskyfiles.blob.core.windows.net/$web/articles/data-link-layer/frame-alanlari.png)

-   **Frame start and stop indicator flags**  ⇒ Frame'in başlangıç ve bitiş sınırlarını tanımlamak için kullanılır.
-   **Addressing** ⇒ Medyadaki kaynak ve hedef düğümleri gösterir.
-   **Type**  ⇒ Veri alanındaki 3.Katman protokolünü tanımlar.
-   **Control**  ⇒ Hizmet kalitesi gibi (QoS) özel akış kontrolü hizmetlerini tanımlar. QoS, belirli ileti türlerine iletme önceliği verir. Örneğin, IP üzerinden ses (VoIP) çerçevleri normalde egecikmeye duyarlı oldukları için öncelik alır.
-   **Data**  ⇒ Frame yükünü (yani paket başlığı, segment başlığı ve veri) içerir.
-   **Error Detection**  ⇒ Artbilgi oluşturmak için verilerden sonra dahil edilir.

### Özetle

Data link katmanı protokolleri her frame'in sonuna artbilgi ekler. Hata algılama adı verilen işlemde artbilgi, frame'in hatasız olup olmadığını belirler. Frame'i oluşturan bitlerin mantıksal veya matematiksel bir özetinin Frame'e yerleştirilmesiyle gerçekleştirilir. Medyadaki sinyaller temsil ettikleri bit değerlerini önemli ölçüde değiştirecek parazit, bozulma ve kayıplara maruz kalabileceği için, data link katmanı hata algılamayı ekler.

İletimde bir düğüm, döngüsel yedekleme kontrolü (CRC) değeri olarak bilinen frame içeriğinin mantıksal özetini oluşturur. Bu değer, frame içeriğini temsil etmek için frame kontrol sırası (FCS) alanına yerleştirilir. Ethernet artbilgisinde, FCS, frame'in iletim hatalarıyla karşılaşıp karşılaşmadığını belirlemek için alıcı düğüm için bir yöntem sağlar.

## 2. Katman Adresleri
Data link katmanı, bir frame'i paylaşılan bir yerel medyaya taşımak için kullanılan adreslemeyi sağlar. Bu katmandaki cihaz adresleri fiziksel adres olarak anılır. Data link katmanı adreslemesi frame başlığında bulunur ve yerel ağdaki frame hedef düğümünü belirtir. Genellikle frame'in başlangıcıdır, bu nedenle NIC, frame'in geri kalanını kabul etmeden önce kendi 2.Katman adresiyle eşleşip eşleşmediğini hızlıca belirleyebilir. Frame başlığı frame'in kaynak adresini de içerebilir.

Fiziksel adresler, hiyerarşik olan 3.Katman mantıksal adreslerinden farklı olarak cihazın hangi ağda bulunduğunu göstermez. Aksine, fiziksel adres belirli cihaza özeldir. Bir aygıt, başka bir ağa veya alt ağa taşınsa bile, aynı 2.Katman fiziksel adresiyle çalışmaya devam eder. Bu nedenle, 2.Katman adresleri yalnızca aynı paylaşılan medya içindeki aygıtları aynı IP ağına bağlamak için kullanılır.

IP paketi hosttan routera, routerdan routera ve son olarak routerdan hosta geçerken, IP paketinin yeni bir data link frame'inde kapsüllenir. Her data link frame'i, o frame'i gönderen NIC'nin kaynak data link adresini ve frame'i alan NIC'nin hedef data link adresini içerir.

- **Host - Router**
Kaynak host 3.Katman IP paketini 2.Katman frame'inde kapsüller. Frame başlığında, host 2.Katman adresini kaynak olarak ve R1 için 2.Katman adresini hedef olarak ekler.
![host-router](https://skorskyfiles.blob.core.windows.net/$web/articles/data-link-layer/host-router.png)
- **Router- Router**
R1, 3.Katman IP paketini yeni bir 2.Katman çerçevesinde kapsüller. Çerçeve başlığında R1, 2.Katman adresini kaynak olarak ve R2 için 2.Katman adresini hedef olarak ekler.
![router-router](https://skorskyfiles.blob.core.windows.net/$web/articles/data-link-layer/router-router.png)
-  **Router- Host**
R2, 3.Katman IP paketini yeni bir 2.Katman çerçevesinde kapsüller. Çerçeve başlığında R2, 2.Katman adresini kaynak olarak ve sunucu için 2.Katman adresini hedef olarak ekler.
![router-host](https://skorskyfiles.blob.core.windows.net/$web/articles/data-link-layer/router-host.png)

Veri bağlantısı katmanı adresi yalnızca LAN içinde geçerlidir. Bu katmandaki adreslerin LAN dışında bir anlamı yoktur. Verilerin başka bir ağ segmentine geçmesi gerekiyorsa, router gibi bir aracı gerekir. Router, fiziksel adrese göre frame'i kabul etmeli ve IP adresi olan hiyerarşik adresi incelemek için frame kapsülünü açmalıdır. IP adresini kullanarak router, hedef cihazın ağ konumunu ve bu adrese ulaşmak için en iyi yolu belirleyebilir. Paketin nereye iletileceğini bildiğinde, router paket için yeni bir frame oluşturur ve yeni frame son hedefine doğru bir sonraki ağ segmentine gönderilir.

Artık Data link katmanı hakkında çok daha fazla bilgi edindik. Network katmanına geçmek için sonraki makalelerde geçebiliriz ama önce network topolojilerini daha detaylı inceleyeceğiz. Bir sonraki makalede görüşmek üzere....