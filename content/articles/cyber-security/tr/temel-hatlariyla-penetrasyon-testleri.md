---
tags:
  - "penetrasyon-testing"
categories:
  - "Siber Güvenlik"
description: "Temel Hatlarıyla Penetrasyon Testleri"
ID: "b9e98045-2b55-4146-9428-5d05f6f19882"
slug: "temel-hatlariyla-penetrasyon-testleri"
title: "Temel Hatlarıyla Penetrasyon Testleri"
cover: "penetrasyon-testi.png"
date: "2022-07-03"
createdAt: 1656781357808
updatedAt: 1656781718369

---
## Penetrasyon - Sızma Testi Nedir?

**Penetrasyon testi - Pentest**  şirketin güvenlik becerilerini üst düzeyde tutmak, Dışarıdan gelebilecek saldırıları görüp önlem almak, Sistemlerinize yapılan yatırımı güvende tutmak ve en önemlisi de güvenlik açıkları nedeniyle oluşabilecek bilgi kayıplarına engel olabilmek için  **pentest - penetrasyon testi**  yapılmalıdır. Penetrasyon testlerini yapan kişiye ise **Pentester** denir.

Penetrasyon testleri üç farklı şekilde yapılır.
### Blackbox Pentest

Pentester, test yapılacak sisteme dair hiçbir bilgi sahibi olmadan saldırıyı gerçekleştirerek sisteme dahil olmaya çalışır. Pentester yabancı biri davranarak herhangi bir hackerın uygulayacağı senaryoları sistem üzerinde dener.

### Greybox Pentest

İç networkte bulunan yetkisiz bir personelin veya misafir ağına bağlanmış bir müşterinin sisteme verebileceği zararın analiz edilmesini sağlar. Veri çalınması, yetki yükseltme ve network paket kaydedicilerine karşı zayıflıklar denetlenir. Sistem hakkında en minimum düzeyde bilgi sahibi olunarak test edilir ve en önemli sızma testi türüdür.

### Whitebox Pentest

Networkteki tüm sistemler hakkında bilgi sahibi olunarak yapılan sızma testi türüdür. Çalışanlardan birisinin içeriden networke girip zarar vermeye çalışmasının simüle edilmiş halidir.

## Penetrasyon Testi ve Modelleri

Sızma testleri yapılırken bazı modeller izlenerek testin karmaşıklaşması önlenmeye çalışılır. İzlenilen birçok model vardır ancak biz iki tanesine değinelim. 

![penetrasyon-model-1](https://skorskyfiles.blob.core.windows.net/$web/articles/penetrasyon-testleri/penetrasyon1.png)

İlk modelimiz yukarıdaki şekilde şematize edilmiştir.

 1. **Information Gathering** ⇒ İlk aşama, hedef hakkında pasiften (hedef ile etkileşim olmadan) aktife (etkileşimli) bilgi toplamadır.
 2. **Threat Modeling** ⇒ Toplanan bilgiler doğrultusunda kullanılacak olan tehditler planlanır. Buna tehdit modelleme denir
 3. **Vulnerability Analysis** ⇒ Planlanan tehditler sonrası güvenlik açığı arama ve analiz etme aşamasıdır. Sistem içerisindeki en zayıf halka aranır.
 4. **Exploitation** ⇒ Bulunan güvenlik açıklarının sömürülmesi denenir. Başarılı olunursa sisteme giriş de sağlanmış olur.
 5. **Post Ecploitation** ⇒ Sömürünün sürdürülebilirliği için diğer sistemlerde de kalıcılığı amaçlanır. Bu sebeple sistem içerisinde yayılmaya çalışılır.
 6. **Repoting** ⇒ Hedefin tüm aşamalardaki güçlü ve zayıf yönlerinin ayrıntılı olarak raporlanmasıdır

İlk modelimiz bu şekildeydi, şimdi diğer bir modelimize bakalım.

![penetrasyo2](https://skorskyfiles.blob.core.windows.net/$web/articles/penetrasyon-testleri/penetrasyon2.png)

1. **Reconnaissance** ⇒ İlk aşama hedef hakkında pasiften aktife doğru bilgi toplama aşamasıdır.
2. **Scanning** ⇒ Toplanan bilgiler doğrultusunda kullanılacak tehditler planlanır ve en zayıf halka aranır
3. **Exploitation/Gaining Access** ⇒ Bulunan güvenlik açıklarının sömürülmesi denenir. Başarılı olunursa  isteme giriş de sağlanmış olur
4. **Maintaining Access** ⇒ Sömürünün sürdürülebilirliği için diğer sistemlerde de kalıcılık amaçlanır . Bu sebeple yayılmak da hedeflenir
5. **CoveringTracks** ⇒Hack işleminin izlerini yok etme aşamasıdır . Delil yok etmek ve temizlik amaçlanır

Görüldüğü üzere modellerde her ne kadar benzerlik olsa da bazı alanlar farklılık göstermekte ve pentesterler hangi modeli seçeceğine bireysel veya kurumsal düzeyde karar verebilirler.

## Cyber Kill Chain - Bir Saldırının Yaşam Döngüsü

Siber saldırıları analiz edebilmek amacıyla çeşitli modellerden birisi olan  cyber kill chain keşif aşamasından saldırı aşamasına kadar tanımlayan ve bu saldırıyı gerçekleştirmek veya önlemek amacıyla oluşturulan 7 aşamalı bir modeldir.

Askeri terminolojideki Ölüm Zinciri ’nden esinlenerek Lockheed Martin tarafından geliştirilmiştir Aşağıdaki aşamalardan oluşur.
![cyber-kill-chain](https://skorskyfiles.blob.core.windows.net/$web/articles/penetrasyon-testleri/cyber-kill-chain.png)

1. **Reconnaissance**

Saldırı gerçekleşmeden veya bir istismar yaratılmadan önce keşif ve bilgi toplama aşamasıdır. Saldıran taraf; hedef sistem veya sistemler üzerinde çeşitli taramalar gerçekleştirerek zafiyetleri tespit etmeye çalışır ayrıca çalışanların isimleri, görevleri, e-mail adresleri, ip adresleri, ağ haritası çıkarma gibi eylemleri aktif ve pasif bilgi toplama araçlarıyla yapabildiği gibi, iş ilanları , linkedln , twitter , facebook , instagram gibi sosyal medya aracılığıyla hedef hakkında sosyal mühendislik yöntemleri ile bilgiler toplayabilir.

**Pasif Bilgi Toplama:** Hedef ile direkt olarak temasa geçilmeden bilgi toplama çeşitidir. (Shodan vb)

**Aktif Bilgi Toplama:** Hedef ile direkt olarak temasa geçilen bilgi toplama çeşitidir. (Port scan vb.)

2. **Weaponization**

Keşif sırasında bulunan zafiyetlerin sömürülmesi için kullanılacak yöntemlerin belirlenmesi ve uygun araçları hazırlama olarak tanımlanan aşamadır. Bu aşamada zafiyete uygun exploitler, zafiyetin istismar edilmesi için kullanılabilecek payloadlar olabileceği gibi zararlı dosyalar ve dokümanlar, oltalama saldırısında kullanılabilecek sahte epostalar gibi birçok yöntem kullanılarak sızma işlemi gerçekleştirilebilir.

3.  **Delivery**

Hazırlanan zararlının ve belirlenen yöntemle hedefe iletilmesi bu aşamadadır. Çeşitli açık kaynak kodlu yazılımlar, phishing, sosyal networkler veya tünellemeler gibi yöntemler kullanılabileceği gibi, güvenlik olarak çalışanların sosyal mühendisliklere veya phishing saldırılarına karşı farkındalıkları, çalışanların hangi donanımların kurum ağına bağlanabildiği veya bağlanamadığı konusunda bilgilendirmesi, bilinen zararlı veya şüpheli web sitelerinin erişim bloklarının kontrol edilmesi bu aşamayı önleyebilir.

4.  **Exploitation**

Oluşturulan zararlı ve belirlenen atak vektörünü kullanarak hedefin zafiyetinin sömürüldüğü aşamadır. Exploit hazırlanıp hedefe iletildikten sonra bu aşamada zararlı kod çalıştırılır. Bunu önlemek amacıyla yazılımlar ne sıklıkla güncellendiği , sistemdeki zafiyetlerin tespit edilmesi için güvenlik denetimleri yapılıp yapılmadığı kontrol edilebilir.

5.  **Installation**

Hedefin sömürülmesi ardından, kalıcı bir tehdit haline gelmek, güvenlik sisteminin ötesinde sistem başarılı bir şekilde kontrol edilebilmesi için hedefe asıl zararlı yazılımın indirilmesi, zararlı yazılımın sistemde kalacağı süreyi mümkün olduğunca arttırmayı hedefleyen aşamadır. Sistemde çalışan bilgisayarlarla yüklenen yazılımların denetlenmesi, kullanıcıların istedikleri yazılımları bilgisayarlara yükleyebilirlikleri, whitelisting ve blacklisting oluşturma bu aşamayı önleyebilir.

6. **Command and Control, c&c**

Sisteme yerleşmiş olan zararlının çalışması uzaktan kontrol edilebildiği ve sistemin ele geçirildiği aşamadır. Bu aşama için saldırıyı engelelyebilircek firewall ve ips‘in devrede olup olmadığı iyi konfigüre edilip edilmediği ve güvenlik cihazlarının monitör edilebiliriliği bu aşamayı aksatmak için önemli unsur taşımakta.

7. **Actions on objectives**

Bütün aşamaları gerçekleştiren saldırgan kuruma erişim sağlamıştır ve bu aşamada, veri çalma, veri değiştirme , veri silme , veri şifreleme, sisteme zarar verme gibi eylemleri gerçekleştirebilir. Önlem olarak iç ağdan dışarı yapılan veri akışı sınırlandırılması, sadece bilinen sunuculara veri akışını sağlama ( whitelisting ) oluşturulduğunda saldırı engellenebilir. Bu süreçte tehdit altındaki verilerin yedeklerinin önceden alınması, bir sistem devre dışı kaldığında hizmet verebilecek yedek sistemin olması bu saldırının etkilerini azaltabilir.