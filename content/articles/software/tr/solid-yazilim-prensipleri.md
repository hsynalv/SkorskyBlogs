---
title: "SOLID Yazılım Prensipleri"
ID: "991bda4b-8705-4324-acad-a0595b0507e7"
description: "SOLID Yazılım Prensipleri"
tags:
  - "design-patterns"
  - "solid"
slug: "solid-yazilim-prensipleri"
categories:
  - "Software"
date: "2022-07-06 12:00"
cover: "solid.png"
createdAt: 1657068092424

---
## S.O.L.I.D Nedir?
S.O.L.I.D, yazılım geliştirirken sürdürülebilir kod yazmamızı sağlayan bir prensipler bütünüdür. Buradaki sürdürülebilirlikten kasıt; yazılım gereksinimleri değiştiğinde ya da mevcut yazılıma eklemeler yapıldığında sistemin buna direnç göstermemesi, en azından en az direnci göstermesi yani esnek olmasıdır. Bunların yanı sıra bakımının ve anlaşılmasının kolay olması gibi nedenler de sayılabilir.

SOLID içerisinde 5 ana başlığa ayrılır:

 1. **S**ingle Responsibility Principle (Tek Sorumluluk Prensibi)
 2. **O**pen/Closed Principle (Açık Kapalı Prensibi) 
 3. **L**iskov SubstitutionPrinciple (Liskov’un Yerine geçme Prensibi) 
 4. **I**nterface Segregation Principle (Arayüz Ayrımı Prensibi) 
 5. **D**ependency Inversion Principle(Bağımlılıkların Tersine Çevrilmesi Prensibi)

Şimdi bu prensipleri tek tek inceleyelim:

## Single Responsibility Principle (Tek Sorumluluk Prensibi)

> Her sınıf, metot, fonksiyon tek bir sorumluluğa sahip olmalıdır.

Şayet bu kurala uymazsak ilerleyen süreçte bir değişikliğe gidildiğinde bunun etkisini birçok yerde görmüş oluruz. Nedeni ise bir yapıya birden fazla sorumluluk yüklenmesinden dolayıdır. Eğer değişikliklerden etkilenen yerler arasında sistemin birçok yerinde kullanılan bir yapımız da varsa maliyet gittikçe artacaktır.
![single-1](https://skorskyfiles.blob.core.windows.net/$web/articles/SOLID/single-res-person.png)

``` Java
public class Person {
    public String firstName;

    public void sendPasswordResetLink() {
        ...
    }
}
```

Yukarıdaki diyagrama ve koda baktığımızda Person sınıfı içerisinde sendPasswordResetLink() diye bir metot bulunmaktadır. Bu sınıfın asıl amacı kişilere ait bilgileri tutmaktır, şifre sıfırlama bağlantısı göndermek değil. Birden fazla sorumluluk yüklendiği için olası bir mail gönderme değişikliğinde bu sınıf da etkilenecektir.

Yukarıdaki UML diyagramını biraz daha düzenlersek aşağıdaki gibi bir yapı elde edilir.

![single-res-2](https://skorskyfiles.blob.core.windows.net/$web/articles/SOLID/single-res-person-2.png)

```Java
class Person {
     public String firstName;
}

class EmailService {
    public void sendPasswordResetLink(Person person) {
        ...
    }
}
```

## Open/Closed Principle (Açık Kapalı Prensibi)

> Yapılarımız (sınıf, metot, fonksiyon) gelişime açık değişime kapalı olmalıdır.

Yazılımlar için zamanla değişim şüphesiz kaçınılmazdır; değişen iş kuralları, kullanılan harici kütüphaneler gibi başlıca nedenler örnek gösterilebilir. Bu prensibin anlatmak istediği şey yeni bir davranış ya da özellik eklemek istediğimiz durumda; yapmak istediğimiz değişikliği mevcut koda dokunmadan, değişimi sadece yeni kodlar üzerinden sağlamaktır.

![open-closed](https://skorskyfiles.blob.core.windows.net/$web/articles/SOLID/open-closed.png)

```Java
class Employee {
    ...
}

class EmployeeManager {
    public void addEmployee(Object database, Employee employee) {
        if (database instanceof OracleDatabase) {
            ((OracleDatabase) database).addDatabase(employee);
        }
    }
}

class OracleDatabase {
    public void addDatabase(Employee employee) {
        ...
    }
}
```

Yukarıdaki koda ve diyagrama baktığımız zaman EmployeeManager adında bir sınıfımız mevcut ve gelen Employee sınıfına ait nesneyi veri tabanına kayıt ediyor. Veri tabanına kayıt etmeden önce hangi veri tabanı örneği geldiğini de if-else durumlarında kotrol edip tip dönüşümü sağlamaktadır. Yukarıdaki kod örneği maalesef Open-Closed için uygun değildir. Nedeni ise yeni bir veri tabanı eklenmek istediğinde başka bir if-else durumu açılacaktır, yeni eklenen veri tabanı kontrolü sağlanacaktır ve sürekli mevcut koda bir müdahalede bulunulacaktır. Bunu çözmenin yolu ise genelde soyutlamadan geçmektedir.

Yukarıdaki UML diyagramını biraz daha düzenlersek aşağıdaki gibi bir yapı elde edilir. Yeni bir eklemede mevcut koda dokunmaya gerek kalmıyor bu sayede. Kayıt işlemlerini MySQL üzerinde yapmak istediğimiz zaman MySQLDatabase adında bir sınıf oluşturup IDatabase arayüzünü uygulamamız yeterlidir. 

![open-closed-2](https://skorskyfiles.blob.core.windows.net/$web/articles/SOLID/open-closed-2.png)

```Java	
class Employee { 
...
}

interface IDatabase {
    void addDatabase(Employee employee);
}

class EmployeeManager {
    public void addEmployee(IDatabase database, Employee employee) {
        database.addDatabase(employee);
    }
}

class OracleDatabase implements IDatabase {
    @Override
    public void addDatabase(Employee employee) {
       ...
    }
}
```

## Liskov Substitution Principle (Liskov’un Yerine geçme Prensibi)


> Alt sınıflardan oluşan nesnelerin, üst sınıfın nesneleri ile yer değiştirdiklerinde aynı davranışı sergilemesi gerekmektedir.

Alt sınıflar, üst sınıflardan türediği için onların davranışlarını devralırlar. Eğer üst sınflara ait davranışları gerçekleştirmiyorlarsa davranışı yapan metotu muhtemelen boş bırakır ya da bir hata fırlatırız fakat bu işlemler kod kirliliğine ve gereksiz kod kalabalığına neden olmaktadır. Bunların yanı sıra projeye daha sonradan dahil olacak geliştiriciler için de sorun oluşturmaktadır. Geliştirici, sistemin sağlıklı yürüdüğünü düşünerek gerçekleştirilmeyen bir davranışı kullanmaya çalışabilir.

![liskov-1](https://skorskyfiles.blob.core.windows.net/$web/articles/SOLID/liskov-1.png)

```Java
abstract class Logger {
    public abstract void openConnection();
    public abstract void closeConnection();
    public abstract void log();
}

class DatabaseLogger extends Logger {
    @Override
    public void openConnection() {
        ...
    }

    @Override
    public void closeConnection() {
        ...
    }

    @Override
    public void log() {
        openConnection();
        // LOG
        closeConnection();
    }
}
```
Yukarıdaki koda baktığımız zaman DatabaseLogger sınıfımız, Logger adlı sınıftan türemektedir. Başlangıç aşaması için bir problem görünmezken ilerleyen zamanlarda veri tabanı değil de bir dosyaya kayıt işlemi alınacağı zaman aşağıdaki gibi bir görünüm meydana gelecektir.

![liskov-2](https://skorskyfiles.blob.core.windows.net/$web/articles/SOLID/liskov-2.png)

```Java
class FileLogger extends Logger {
    @Override
    public void openConnection() {
        new Exception("Not implemented!");
    }

    @Override
    public void closeConnection() {
        new Exception("Not implemented!");
    }

    @Override
    public void log() {
        // LOG
    }
}
```

Bağlantı açma ve kapatma işlemleri veri tabanına aittir, bir dosyaya değil. Gereksiz hata fırlatmaları, kodun okunmasındaki zorluk, kod kalabalığı gibi birçok olaya neden olmaktadır. Burada bu işlemler bir ara sınıfa alınabilir.

![liskov-3](https://skorskyfiles.blob.core.windows.net/$web/articles/SOLID/liskov-3.png)

```Java
abstract class Logger {
    public abstract void log();
}

abstract class ConnectableLogger extends Logger {
    public abstract void openConnection();
    public abstract void closeConnection();
}

class FileLogger extends Logger {
    @Override
    public void log() {
        // LOG
    }
}

class DatabaseLogger extends ConnectableLogger {
    @Override
    public void openConnection() {
        ...
    }

    @Override
    public void closeConnection() {
        ...
    }

    @Override
    public void log() {
        openConnection();
        // LOG
        closeConnection();
    }
}
```

## Interface Segregation Principle (Arayüz Ayrımı Prensibi)


> Sınıflar, kullanmadığı metotları içeren arayüzleri uygulamaya zorlanmamalıdır.

Arayüzlerimizde genel olarak birçok operasyonel işlem barındırabiliriz fakat bu arayüzü uygulayan sınıfların, bazılarını kullanmama durumu olabilmektedir. Bir sınıf birden fazla arayüzü uygulaması özelliğiyle de birlikte bu prensip, bu tür durumlarda arayüzlerin ayrılmasını ve ihtiyaç halinde olanların kullanmasını söylemektedir.

![interface-segre](https://skorskyfiles.blob.core.windows.net/$web/articles/SOLID/interface-segre.png)

```Java
interface IWorker {
    void eat() throws Exception;

    void work();

    void pay() throws Exception;
}

class RobotWorker implements IWorker {

    @Override
    public void eat() throws Exception {
        throw new Exception();
    }

    @Override
    public void pay() throws Exception {
        throw new Exception();
    }

    @Override
    public void work() {
      ...
    }
}
```

Yukarıdaki diyagram incelendiğinde, şirket çalışanları IWorker arayüzünü uygulamaktadır; yemek yeme, ödeme alma, çalışma gibi davranışları gerçekleştirmektedir. Fakat daha sonradan bazı işler robotlar tarafından yapılmaya başlandı ya da dış kaynaktan birileri(outsource) de çalışmaya başladı. Bu durumda bazı davranışlar gerçekleşmeyecektir. Örneğin robotların yemek yeme ya da ödeme alma davranışını gerçekleştirememesi gibi ya da dış kaynaktan gelenlere verilmeyen yemek imkanı. Bu gerçekleşmeyen davranışların içlerini ya boş bırakma ya da hata fırlatma durumunda kalırız. Bu tür durumlarda bu prensip bizlere bu arayüzlerin ayrılmasını ve ihtiyaç halinde olanların kullanılmasını söylemektedir.

Yukarıdaki UML diyagramını biraz daha düzenlersek aşağıdaki gibi bir yapı elde edilir. work(), pay(), eat() davranışları başka arayüzlere aktarıldı ve ihtiyaç halinde olanlar uygulandı.

![interface-segre-2](https://skorskyfiles.blob.core.windows.net/$web/articles/SOLID/interface-segre-2.png)

```Java
interface IWorker {
    void work();
}


interface IEatableWorker {
    void eat();
}

interface IPayableWorker {
    void pay();
}

class Worker implements IWorker, IEatableWorker, IPayableWorker {

    @Override
    public void eat() {
        ...
    }

    @Override
    public void work() {
        ...
    }

    @Override
    public void pay() {
        ...
    }
}

class RobotWorker implements IWorker {
    @Override

    public void work() {
     ...
    }
}
```
## Dependency Inversion Principle (Bağımlılıkların Tersine Çevrilmesi Prensibi)
> Yüksek seviye sınıflar, düşük seviye sınıflara bağlı olmamalıdır. Her ikisi de soyutlamalara bağlı olmalıdır.
>Soyutlamalar, detaylara bağlı olmamalıdır. Detaylar, soyutlamalara bağlı olmalıdır.

![dependency-inv](https://skorskyfiles.blob.core.windows.net/$web/articles/SOLID/dependency-inv.png)

```Java
class ExceptionReporter {
    private OracleDatabase oracleDatabase;

    public ExceptionReporter() {
        oracleDatabase = new OracleDatabase();
    }

    public void reportException(Exception exception) {
        oracleDatabase.add(exception);
    }
}

class OracleDatabase {
    public void add(Object object) {
        System.out.println("added");
    }
}
```

Yukarıdaki diyagram ve kod incelendiğinde ExceptionReporter sınıfının (yüksek seviyeli sınıf), OracleDatabase sınıfına (düşük seviyeli sınıf) direkt olarak bağımlı olduğu görülmektedir. İleride veri tabanı olarak Oracle değil de MySQL kullanmak istersek maalesef bu sınıfa müdahale etmek zorunda kalacağız. Bu istenmeyen bir davranıştır. Bunun çözümünü ise buradaki bağımlılıkları soyutlayarak sağlayacağız.

Yukarıdaki UML diyagramını biraz daha düzenlersek aşağıdaki gibi bir yapı elde edilir.

![dependency-inv-2](https://skorskyfiles.blob.core.windows.net/$web/articles/SOLID/dependency-inv-2.png)

```Java
class ExceptionReporter {
    private IDatabase database;

    public ExceptionReporter(IDatabase database) {
        this.database = database;
    }

    public void reportException(Exception exception) {
        database.add(exception);
    }
}

interface IDatabase {
    void add(Object object);
}

class MySQLDatabase implements IDatabase {
    @Override
    public void add(Object object) {
        ...
    }
}

class OracleDatabase implements IDatabase {
    @Override

    public void add(Object object) {
        ...
    }
}
```






