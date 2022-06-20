---
title: "Ağ Katmanı"
categories:
  - "network"
description: "Ağ Katmanı"
slug: "ag-katmtmani"
tags:
  - "osi"
  - "network-layer"
ID: "9835da93-deb7-4a31-b02e-7248355ec6ac"
cover: "cover1.jpg"
date: "2022-06-20 12:00"
createdAt: 1655739041908

---
## Ağ Katmanı Özellikleri
Ağ katmanı veya OSI 'nin 3.Katmanı, uç cihazların ağlar arasında veri alışverişini sağlayan hizmetler sunar. Ağ katmanı temel protokollerini IP versiyon 4 (IPv4) ve IP versiyon 6 (IPv6) oluşturmaktadır.  Diğer ağ katmanı protokolleri arasında Open Shortest Path First (OSPF) gibi yönlendirme protokolleri ve Internet Control Message Protocol (ICMP) gibi ileti protokolleri bulunur.
![ag-katmani](https://skorskyfiles.blob.core.windows.net/$web/articles/ag-katmani/ag-katmani.jpg)
Ağ sınırları boyunca uçtan uca iletişimi gerçekleştirmek için ağ katmanı protokolleri dört temel işlem gerçekleştirir:

-   **Uç cihazların adreslenmesi** ⇒ Uç aygıtlar, ağda yer edinebilmek için benzersiz bir IP adresiyle yapılandırılmalıdır.

-   **Kapsülleme-** ⇒ Ağ katmanı, taşıma katmanının protokol veri birimini (PDU) bir pakete kapsüller. Kapsülleme işlemi, kaynak (gönderen) ve hedef (alıcı) hostların IP adresleri gibi bilgileri IP başlığına ekler. Kapsülleme işlemi IP paketinin kaynağı tarafından gerçekleştirilir.
-   **Yönlendirme** ⇒ Ağ katmanı, paketleri başka bir ağdaki bir hedef hosta yönlendirmek için hizmetler sunar. Paket, başka ağlara ulaşabilmek için router tarafından işlenmelidir. Routerların rolü, yönlendirme (routing) olarak bilinen bir işlemle en iyi yolu seçmek ve paketleri hedef hosta yönlendirmektir. Bir paket, hedef hosta ulaşmadan önce birçok routerdan geçebilir. Hedef hosta ulaşmak için bir paketin geçtiği her routera, atlama (sekme) adı verilir.

-   **Kapsül açma**  ⇒Paket hedef hostun ağ katmanına vardığında, host paketin IP başlığını kontrol eder. Başlık içindeki hedef IP adresi hostun IP adresiyle eşleşiyorsa, IP başlığı paketten kaldırılır. Ağ katmanı tarafından paketin kapsülü açıldıktan sonra, ortaya çıkan 4.Katman PDU'su taşıma katmanındaki uygun hizmete aktarılır. Kaspül açma işlemi, IP paketinin hedefi olan host tarafından gerçekleştirilir.

Her bir host üzerinde çalışan işlemler arasındaki veri taşımasını yöneten taşıma katmanının (OSI 4.Katman) aksine, ağ katmanı iletişim protokolleri (örn., IPv4 ve IPv6) veriyi bir hosttan diğerine taşımak için kullanılan paket yapısını ve işlemleri belirler. Her bir pakette taşınan veriyi dikkate almadan çalışma, ağ katmanına birden çok host arasındaki birden çok türde iletişim için paket taşıma olanağı sağlar.
![ip-gif](https://skorskyfiles.blob.core.windows.net/$web/articles/ag-katmani/The-Network-Layer.gif)

## IP Kapsülleme
IP, bir IP başlığı ekleyerek taşıma katmanını segmentini veya diğer verileri kapsüller. IP başlığı, paketi hedef hosta teslim etmek için kullanılır.
![ip-kapsullleme](https://skorskyfiles.blob.core.windows.net/$web/articles/ag-katmani/ip-kapsulleme.jpg)
Veri katmanını katman katman kapsülleme işlemi, farklı katmanlardaki hizmetlerin diğer katmanları etkilemeden geliştirilmesini ve ölçeklenmesini sağlar. Bu, taşıma katmanı segmentlerinin IPv4 , IPv6 veya gelecekte geliştirilebilecek herhangi bir yeni protokol ile kolayca paketlenebileceği anlamına gelir.

IP başlığı, bir ağ üzerinden hedefine doğru ilerledikçe 3.Katman aygıtları (yani Routerlar ve 3.Katman switchler) tarafından incelenir. IP adresleme bilgisinin, IPv4 için Ağ Adresi Çevirisi (NAT) gerçekleştiren cihaz tarafından çevrilmesi haricinde, paketin kaynak hosttan ayrıldığı andan hedef hosta ulaşana kadar aynı kaldığını unutmamak önemlidir.

Routerlar, paketleri ağlar arasında yönlendirmek için yönlendirme protokollerini uygular. Bu aracı aygıtlar tarafından gerçekleştirilen yönlendirme, paket başlığındaki ağ katmanı adreslemesini inceler. Her durumda, paketin veri bölümü, yani kapsüllenmiş taşıma katmanı PDU'su veya diğer veriler, ağ katmanı işlemleri sırasında değişmeden kalır.

## Uç Cihazların Paketleri Yönlendirmesi
Hem IPv4 hem de IPv6 ile paketler her zaman kaynak hostta oluşturulur. Kaynak hostun, paketi hedef hosta yönlendirebilmesi gerekir. Bunu yapmak için, host uç aygıtları kendi yönlendirme tablosunu oluşturur. Bu konuda, uç aygıtların yönlendirme tablolarını nasıl kullandığı anlatılmaktadır.

Ağ katmanının diğer bir rolü, paketleri hostlar arasında yönlendirmektir. Host aşağıdakilere bir paket gönderebilir:

-   **Kendisi**  ⇒ Bir host, 127.0.0.1 özel IPv4 adresine ya da ::1 IPv6 kendisine ping atabilir :( loopback arayüzü olarak adlandırılır.) Loopback arayüzü pinglendiğinde hosttaki TCP / IP protokol yığını test edilir.
-   **Yerel host**  ⇒ Gönderen hostla aynı yerel ağdaki kaynak hosttur. Kaynak ve hedef host aynı ağ adresini paylaşır.
-   **Uzak host**  ⇒  Bu, uzak ağdaki bir hedef hosttur. Kaynak ve hedef host aynı ağ adresini paylaşmazlar.
![yonlendirme](https://skorskyfiles.blob.core.windows.net/$web/articles/ag-katmani/yonlendirme.jpg)
Bir paketin yerel bir hosta mı yoksa uzak bir hosta mı gönderileceği, kaynak uç cihaz tarafından belirlenir. Kaynak uç cihaz, hedef IP adresinin kendisi ile aynı ağda olup olmadığını belirler. Belirleme yöntemi IP sürümüne göre değişir:

-   **IPv4'te**  ⇒ Kaynak aygıt, bunu belirlemek için kendi IPv4 adresi ve hedef IPv4 adresi ile birlikte kendi alt ağ maskesini kullanır.
-   **IPv6'da**  ⇒ Yerel router, yerel ağ adresini (önek) ağdaki tüm cihazlara bildirir.

Bir ev veya iş ağında, LAN switchi veya kablosuz erişim noktası (WAP) gibi bir aracı kullanarak birbirine bağlı birkaç kablolu ve kablosuz cihazınız olabilir. Bu ara cihaz yerel ağdaki yerel hostlar arasında ara bağlantı sağlar. Yerel ana hostlar, herhangi bir ek cihaza ihtiyaç duymadan birbirlerine ulaşabilir ve bilgi paylaşabilir. Host, kendisiyle aynı IP ağı ile yapılandırılmış bir cihaza paket gönderiyorsa, paket basitçe host arayüzünden dışarı gönderilerek, ara cihaz üzerinden ve doğrudan hedef aygıta iletilir.

Elbette, çoğu durumda cihazlarımızın, diğer evler, işletmeler ve internet gibi yerel ağ segmentinin ötesine bağlanmasını isteriz. Yerel ağ segmentinin ötesindeki cihazlar uzak hostlar olarak bilinir. Bir kaynak cihaz, uzak bir hedef cihaza bir paket gönderdiğinde, routerların ve yönlendirmenin yardımına ihtiyaç duyulur. Yönlendirme, hedefe giden en iyi yolu belirleme işlemidir. Yerel ağ segmentine bağlı router, varsayılan ağ geçidi olarak anılır.

Bir sonraki makalemizde burada sıkça bahsettiğimiz IPv4 ve IPv6 neymiş daha detaylı inceleyebiliriz. Görüşmek üzere...