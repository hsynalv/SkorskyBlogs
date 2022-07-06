---
ID: "ad28943f-266d-44ca-ad76-09319cf63b36"
title: "Design Patterns"
slug: "design-patterns"
tags: []
categories: []
description: "design-patterns"
date: "2022-07-07 12:00"
cover: "design-patterns.jpg"
createdAt: 1657143878432

---
## Design Patterns (Tasarım Kalıpları) Nedir?

Tasarım Desenleri (veya bir diğer kullanımla tasarım kalıpları) yazılımda sık karşılaşılan problemler için oluşturulmuş çözümlerdir. Kodunuz içerisinde sıklıkla karşılaşılan sorunları çözmek için özelleştirerek kullanabileceğiniz önceden hazırlanmış planlar olarak düşünebilirsiniz. Tasarım kalıpları bir fonksiyon, ya da sınıf gibi hazır olarak bulup kodunuza ekleyebileceğiniz parçalar değil, prorblem çözümü için kullanılan genel konseptlerdir.

Tasarım kalıpları gibi algoritmalar da problemleri çözmek için üretilmiş tipik çözümler olduğundan tasarım desenleri genelde algoritmalarla karıştırılır. Algoritmalar bir hedefe ulaşabilecek net bir eylemler kümesi tanımlarken, tasarım desenleri bir çözümün daha üst düzey bir tanımıdır. Aynı desenin iki farklı programa uygulanan kodu farklı olabilir.

Bir algoritmayı yemek tarifine benzetebiliriz. Kullanılacak malzemeler ve takip edilecek adımlar net olarak bellidir. Öte yandan bir tasarım kalıbı daha çok bir plan gibidir, sonuçta bekleneni ve özellikleri görürsünüz ama uygulama sırası ve şekli biraz daha size bağlıdır.


## Design Pattern Ne Değildir?
Nesneler arası ilişkiler genellikle UML diyagramları ile gösterilir, bu sayede yazılımcılar arasında ortak bir iletişim dili oluşmuş olur.

Design patterns, doğrudan koda dönüştürülebilen bitmiş bir tasarım değildir. Birçok farklı durumda kullanılabilecek bir sorunun nasıl çözüleceğine ilişkin bir açıklama veya şablondur.

## Design Pattern'e Neden İhtiyaç Duyarız?
- Design Patterns, test edilmiş, kanıtlanmış geliştirme paradigmaları sağlayarak geliştirme sürecini hızlandırabilir.
- Kodunuzu, daha basit tutmak gerektiğinde kodu daha anlamlı ve daha az karmaşık hale getirmeye yardımcı olurlar. 
- Büyük sorunlara neden olabilecek ince sorunları önlemeye yardımcı olur ve ayrıca kod okunabilirliğini artırır.
- Ortak bir programlama sorununa karşı standart bir çözüm işlemi, yazılımın büyük ölçekte yeniden kullanılmasını sağlar.

## Design Pattern Kategorileri
Yazılım tasarım kalıpları genel olarak 3 ana başlıkta incelenir. Bunlar şunlardır:

1. Creational Patterns (Yaratımsal Kalıplar): Nesnelerin oluşturulmasında ve yönetilmesinde kullanılan bir desendir. Bu program akışında hangi nesneye ihtiyaç varsa onu oluşturmada esneklik ve kolaylık sağlar.
2. Structural Patterns (Yapısal Kalıplar): Birden fazla sınıfın bir işi yerine getirirken nasıl davranacağını belirlemek için kullanılan desenlerdir. 
3. Behavioral Patterns (Davranışsal Kalıplar): Nesnelerin birbirleri ile ilişkisini düzenleyen desendir.


### Creational Patterns (Yaratımsal Kalıplar)
- Singleton Pattern
- Factory Pattern
- Abstract Factory Pattern
- Builder Pattern
- Prototype Pattern


### Structural Patterns (Yapısal Kalıplar)
- Adapter Pattern
- Bridge Pattern
- Filter Pattern
- Composite Pattern
- Decorator Pattern
- Facade Pattern
- Flyweight Pattern
- Proxy Pattern

### Behavioral Patterns (Davranışsal Kalıplar)
- Command Pattern
- Interpreter Pattern
- Iterator Pattern
- Mediator Pattern
- Memento Pattern
- Observer Pattern
- Null Object Pattern
- Strategy Pattern
- State Pattern
- Visitor Pattern

> Bu tasarım kalıplarının bazılarını sonraki makalelerimizde inceleyeceğiz.

## Anti Pattern Nedir?
Anti patternler de bir patterndir ama yazılımsal olarak bir problemi kabul edilmiş bir pattern olarak kullanmak yerine sorunları özgün bir yöntem ile çözmek demektir. Yani tasarım kalıplarının tam zıttıdır diyebiliriz.

Probleminizde bir anti pattern kullanmak ileride ciddi sorunlara yol açabilir. Ayrıca o problem için anti pattern olarak sayılan bir tasarım başka bir problem için uygun bir çözüm olabilir bunu unutmamak gerek. Bu anti patternler belgelenmiştir.

Anti patternlerin belgelenmesinin avantajı programcının bu yöntemlerden mümkün olduğunca uzak durabilmesini sağlamak karşılaştırma yapabileceği bir kaynak sunmaktır.

Bazı anti patternler şunlardır:

- Magic Push Button
- Spagetti Coding
- Functional Decomposition
- Error Hidding
- Swiss Army Knife
- Cricular Dependency
- God Object
- Cargo Cult Programming
- Golden Hammer
- Boat Anchor
- Copy Paste Programming




