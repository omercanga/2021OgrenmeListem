# Day-1
Calling REST Services with WebClient
https://docs.spring.io/spring-boot/docs/2.0.3.RELEASE/reference/html/boot-features-webclient.html

# Day-2
//Converting String into int using Integer.parseInt()  
int i=Integer.parseInt(s);  

int i=10;  
String s=String.valueOf(i);//Now it will return "10"  

// char to String         
char ch1 = 'A';    
char ch2 = 'B';  
String s1 = String.valueOf(ch1);    
String s2 = String.valueOf(ch2); 

# Day-3
Nulls and the dreaded NPE can be awful, but by maintaining encapsulation, keeping your code simple, and using nulls only in certain situations, you can come out on top.
10 Tips to Handle Null Effectively
https://dzone.com/articles/10-tips-to-handle-null-effectively

````java
if(degisken != Null) //istenen kontrol erme yöntemi
````

# Day-4
debugging tricks
https://stackify.com/java-debugging-tips/

# Day-5
SOAP servis ile REST servis
Nedir? Benzerlik ve farklılıkları nelerdir?

SOAP (Simple Object Access Protocol) yani Basit Nesne Erişim Protokolü,
internet üzerinden küçük miktarda bilgileri yada mesajları aktarma protokoludur. 
SOAP mesajları XML formatındadırlar ve  genellikle HTTP protokolu bazende TCP/IP 
kullanılarak gönderilirler. SOAP bizi XML tabanlı kullanıma mecbur bırakır. 
Bu konuda esnek değildir. SOAP üzerinde güvenlik sağlamak daha kolaydır. 
SOAP için geliştirici araçları daha iyidir. Kullanmak için yardımcı olacak 
daha çok kaynak bulunabilir.

REST (REpresentational State Transfer) yani Temsili Durum Transferi, 
istemci ve sunucu arasında veri alışverişinin basit bir yoludur. 
REST mimarisi standart bir tanımlamaya ihtiyaç duymaz. REST ile veri 
alışverişini JSON, XML hatta Text formatında bile yapabilirsiniz. 
Esnek bir yapıya sahiptir. REST mimarisinde de HTTP metodlarından yararlanılır. 
Uygulamanın daha hızlı çalışmasını sağlar.

# Day-6
https://logging.apache.org/log4j/2.x/manual/configuration.html

log4j kullanım
```
import com.foo.Bar;
 
// Import log4j classes.
import org.apache.logging.log4j.Logger;
import org.apache.logging.log4j.LogManager;
 
public class MyApp {
 
    // Define a static logger variable so that it references the
    // Logger instance named "MyApp".
    private static final Logger logger = LogManager.getLogger(MyApp.class);
 
    public static void main(final String... args) {
 
        // Set up a simple configuration that logs on the console.
 
        logger.trace("Entering application.");
        Bar bar = new Bar();
        if (!bar.doIt()) {
            logger.error("Didn't do it.");
        }
        logger.trace("Exiting application.");
    }
}
```

# Day-7
double dan long a cevirim
```
  double val = 3.5;
		long intPartVal= (long) val;
		double fracPartVal = val - intPartVal;
		System.out.println(fracPartVal);
```
sdouble ondalık kısımı alma
```
		double d1 = 67.22;
		double d2 = d1%1;
		System.out.println(d2);
		System.out.println("*******");
```
https://stackoverflow.com/questions/7124448/how-does-java-math-roundingmode-work

The problem you have is that double is not a precise representation and you are round based on this imprecise number.

```
BigDecimal bd = new BigDecimal(1.555d);
System.out.println("bd=" + bd);
bd = bd.setScale(2, RoundingMode.HALF_UP);
System.out.println("after rounding bd=" + bd);
double d = bd.doubleValue();
System.out.println("after rounding d=" + d);
```
prints

```
bd=1.5549999999999999378275106209912337362766265869140625
after rounding bd=1.55
after rounding d=1.55
```
however
```
BigDecimal bd = BigDecimal.valueOf(1.555d);
System.out.println("bd=" + bd);
bd = bd.setScale(2, RoundingMode.HALF_UP);
System.out.println("after rounding bd=" + bd);
double d = bd.doubleValue();
System.out.println("after rounding d=" + d);
```
prints
```
bd=1.555
after rounding bd=1.56
after rounding d=1.56
This works because BigDecimal.valueOf does some extra rounding based on how double would appear if you printed it.
```
However I wouldn't use BigDecimal unless performance/simplicity is not an issue.

```
double d = 1.555d;
System.out.println("d=" + d);
d = roundToTwoPlaces(d);
System.out.println("after rounding d=" + d);

public static double roundToTwoPlaces(double d) {
    return ((long) (d < 0 ? d * 100 - 0.5 : d * 100 + 0.5)) / 100.0;
}
prints

d=1.555
after rounding d=1.56
```		
# Day-8
Servlet nedir ?
Web sunucusu üzerinde çalışır ve gönderilen veriye göre sonuç üreten java sınıflardıdır.Kullanıcı ulaşmak istediği sayfayı belirtip bilgiyi sonucuya gönderir.Web sunucu gelen bu isteği(request) alıp bu isteğe uygun olan servete ait nesne varsa istek servete gönderilir.Eğer istenilen(gönderilen bilgiyle uyuşan) nesne bellekte yoksa üretilip istek ve bilgi servete gönderilir.Servlet kendisine gelen bu istek doğrultusunda bir sonuç üretip(örn:html sayfası formatında) web sunucusuna gönderir.Web suncuda servletten gelen bu değeri isteği yapan kullanıcıya gönderir.Fakrlı sonuçlar için farklı servlet sınıfları üretilmeli(örn:HttpServlet).Servlet makinesi web sunucuda servlet ve javanın nasıl kullanıldığını bilir ve sunucuda bulunmalıdır.Bu makine servletleri JVM(Java virtual machine) ile çalıştırılabilir ve sonuçları kullanıcıya gönderilebilir.Web suncusu ve servlet makinesi içeren bir çok  sunucu vardır.En çok bilinen Apache Tomcat, Macromedya Jrun,Oracle. Aynı servete birden fazla istek aynı anda gelince suncu bu servlet sınıfndan tek bir nesne üreterip bu nesneyi iş parçacığı(multi thread) ile tüm isteklere cevap verebilir.Bu arada javada çoklu süreç(multi process) yok.Çünkü JRE bir süreçtir ve aynı anda birden fazla süreç çalıştırılamaz.Bunun için tek süreç ile çoklu iş parçacığı ile bir çok işlem aynı anda gerçekleştirilebiliyor.[34] http://www.ethemsulan.com/2010/02/java-servlet-nedir-ve-nasl-calsr.html

# Day-9
JPA / Hibernate arasındaki fark nedir ?
JPA (Java Persistence API) veritabanından bağımsız kodlama yapabilmenizi ve sorgular hazırlayabilmenizi olanaklı kılar. Java geliştiricilerine veritabanı tabloları ile sınıflar arasında mapping imkanı sunarak, ilişkisel veritabanlarının nesne tabanlı bir geliştirme iskeleti ile kolaylıkla yönetilmesini sağlar. The Java Persistence API, Java Persistence Query Language ve nesne/tablo ilişkisini gösteren mapping metadataları gibi üç kola ayrılmış bir geliştirim mantığı vardır. JPQL (Java Persistence Query Language) ile yazacağınız sorgular, veritabanınızdaki ilişkisel yapıya göre hazırladığınız, birbiriyle ilişkili POJO(plain old java object) nesnelerini kullandığınız sorgular olacaktır. JPA 'nın sunduğu imkanlar ile çoğu basit işlemi (kayıt silme, ekleme ve birleştirme) de, JPQL kullanmadan, kolaylıkla halledebilme olanağı bulunmaktadır.
Hibernate, JPA’ nın özelliklerini taşımakla birlikte kendine ait yararlı ek özellikleri de bulunmaktadır. JPA bir standart olduğu için bu döküman JPA ‘ya ağırlık verilmektedir. [12] https://blog.kodcu.com/minikitap/Java.pdf

# Day-10
Java’da length, length() ve size() farkı
Java’da bir şeyin boyutunu, uzunluğunu öğrenmek için dizilerde(array) .length değişkenini, String’lerde(bir dizi olduğu için) .length() ve listelerde ise .size() fonksiyonlarını kullanıyoruz. 

# Day-11
Spring Boot’un özellikleri 
- Web Geliştirme (Web Development)
- Spring Uygualamaları (SpringApplication)
- Uygulama Etkinlikleri ve Dinleyicileri (Application events and listeners)
- Admin Özellikleri (Admin features)
- Özellik/Nitelik Dosyaları(Properties Files)
- Loglama (Logging)
- Güvenlik (Security)

# Day-12
Spring Boot Notasyonları 
@RestController bir stereotype notasyondur. 
Sınıfa @Controller ve @ResponseBody notasyanları ekler.
Uygulamak için, dosyanızdaki pakete org.springframework.web.bind.annotation belirtmeye ihtiyacınız vardır.
[Kaynak](https://www.kampuskod.com/yazilim/java/spring-boot-mulakat-sorulari-1/ )

# Day-13
Spring Boot otomatik olarak bağımlılıkları (dependencies) ve yapılandırmaları (configuration) yönetir.
Bu bağımlılıkların herhangi biri için bir sürüm belirtmeniz gerekmez. 
Spring Boot versiyonu yükselttiğinizde, Spring Boot tüm bağımlılıkları otomatik olarak yükseltir.
[Kaynak](https://www.kampuskod.com/yazilim/java/spring-boot-mulakat-sorulari-1/ )

# Day-14
Spring Boot Özellikleri (Properties):
Spring Boot, projemizin application.properties dosyasında belirtilebilecek çeşitli özellikler sunar. 
Bu özellikler varsayılan değerdedir ve özellik dosyası içinde ayarlayabilirsiniz. 
Özellikler, değerleri ayarlamak için kullanılır. 
Örneğin; server-port numarası (number), veritabanı bağlantı ayarları (database connection configuration) vb.
[Kaynak](https://www.kampuskod.com/yazilim/java/spring-boot-mulakat-sorulari-1/ )

# Day-15
## DTO, DAO, POJO/Bean ve JavaBean Nedir Nerelerde Kullanılır?

## DAO(Data Access Object):
Genellikle veri tabanı üzerinde yapılacak işlemleri yüklenen sınıflardır. DAO içine database işlemlerimizi yazıp programda karışıklık ve tekrar tekrar kullanmanın(code reuse) önünü açarız.

## DTO(Data Transfer Object):
Adından anlaşılacağı üzere bu objeler katmanlar, birimler arasında sadece veri aktarımı için kullanılırlar. (DB ve JVM arasında örneğin , JVM-JVM arasında)
- Depolama dışında herhangi bir yükümlülükleri yoktur.
- Setter/getter kullanmına gerek yoktur. Tüm veriler public olarak tutulabilir.

## JavaBean:
JavaBean dediğimiz objeler veri tutma amaçlı kullanılırlar. Bir objenin JavaBean olarak sayılabilmesi için 3 şartı sağlaması gereklidir.
- Serializable olmalı.
- Parametresi yapıcı metodu olmalı.(No parameter constructor)
- Public setter/getter metodlarına sahip olmalı

## POJO/Bean(Plain Old Java Object):
Bu obje de veri depolamak için kullanılırlar. JavaBean den farklı herhangi bir zorlamaya sahip değildir. Örneğin kullanıcı bilgilerini tutacağımız bir objeye UserBean diyebiliriz.
[Kaynak](https://hasanmen.blogspot.com/2016/08/dto-dao-pojobean-ve-javabean-nedir.html )

# Day-16
Hibernate, veritabanı ile etkileşim kurmak için Java uygulama geliştirmelerini kolaylaştıran bir Java Frameworku’dur. 
Hibernate açık kaynak kodlu, hafif, ORM (Nesne İlişkisel Haritalama/Eşleme (Object Relational Mapping) ) aracıdır. 
Hibernate, veri sürekliliği için JPA’nın tanımlamalarını uygular.

ORM Tool Nedir?
ORM tool (aracı), veri oluşturma, veri değiştirme ve veri erişimini basitleştirir. 
Veritabanı üzerinde saklanan verilere nesne eşleyen bir programlama tekniğidir.

ORM tool, veritabanıyla etkileşim kurmak için JDBC API kullanır.

JPA Nedir?
Java Persistence API (JPA), ORM araçlarına (tools) belirli fonksiyonellik ve standart sağlayan bir Java spesifikasyonudur. 
javax.persistence paketi, JPA sınıfları ve arayüzlerini içerir.

Hibernate Framework Avantajları
Açık Kaynak Kodlu ve Hafif (Open Source and Lightweight)
Hibernate framework’u LGPL lisansı altında açık kaynak kodludur ve hafiftir.

- Hızlı Performans (Fast Performance)
Hibernate Framework’nun performansı hızlıdır çünkü cache (önbellek) kullanılır. 
Hibernate Framework’te iki tür cache vardır: 
    -İlk Seviye Cache ve İkinci Seviye Cache. İlk Seviye Cache varsayılan olarak gelmektedir.

- Veritabanı Bağımsız Sorgu (Database Independent Query)
HQL (Hibernate Query Language (Hibernate Sorgu Dili)) SQL’in nesne yönelimli bir versiyonudur. Veritabanından bağımsız sorgular üretir. Böylece, veritabanına özgü sorgular yazmanıza gerek yoktur. 

Hibernate’den önce, proje için veritabanı değiştirilirse, bakım problemlerine yol açan SQL sorgusunu da değiştirmemiz gerekir.
- Otomatik Tablo Oluşturma (Automatic Table Creation)

Hibernate Framework, veritabanı tablolarını otomatik olarak oluşturmak için kolaylık sağlar. Bu yüzden, veritabanındaki tabloları manuel olarak eklenmesine gerek yoktur.
- Karmaşık Birleşmeyi Basitleştirir (Simplifies Complex Join)

Hibernate Framework’te birçok tablodan veri çekmek, kolaydır.
- Sorgu İstatistikleri ve Veritabanı Durumunu Sağlar (Provides Query Statistics and Database Status)
Hibernate, sorgu önbelleğini (cache) destekler ve sorgu ve veritabanı durumu hakkında istatistikler sağlar.

[Kaynak](https://www.kampuskod.com/yazilim/java/hibernate-nedir-hibernate-framework-avantajlari-java-dersleri/ )


# Day-17
Equals() ve == arasında temek fark, birinin metot diğerinin operator olmasıdır.
== operatörünü referans karşılaştırması (reference) (address comparison) için ve equals() metotunu içerik karşılaştırması için kullanırız. 
Basitçe söylemek gerekirse, == her iki nesnenin aynı bellek konumuna işaret edip etmediğini denetlerken, .equals() nesnelerdeki değerlerin karşılaştırılmasını değerlendirir.
```java

public class KampusKod {
    
    public static void main(String[] args) {
        String s1 = "KAMPUSKOD";
        String s2 = "KAMPUSKOD";
        String s3 = new String("KAMPUSKOD");
        String s4 = new String("KAMPUSKOD");
        
        System.out.println(s1 == s2);
        System.out.println(s1.equals(s2));
        System.out.println(s3 == s4);
        System.out.println(s3.equals(s4));
    }

}
```
Kod Çıktısı:
```
true
true
false
true
```
[https://www.kampuskod.com/yazilim/java/javada-ve-equals-farki-java-dersleri/ ]

# Day-18
Given String s, is there a good way of testing whether VALUES contains
Arrays.asList(yourArray).contains(yourValue)

```java
String[] fieldsToInclude = { "id", "name", "location" };

if ( ArrayUtils.contains( fieldsToInclude, "id" ) ) {
    // Do some stuff.
}
```
Başka bir örnek
```java
String testValue="test";
String newValueNotInList="newValue";
String[] valueArray = { "this", "is", "java" , "test" };
Arrays.asList(valueArray).contains(testValue); // returns true
Arrays.asList(valueArray).contains(newValueNotInList); // returns false
```
# Day-19
-Tasarım Desenleri (Design Patterns) kullanmak gerekli midir, neden? 
Tasarım desenleri temel olarak, tasarım prensiplerinin bir amaç için sınıf seviyesinde birlikte kullanılmasıdır. Desenler, yazılım geliştiricilerin zaman içersinde deneme/yanılma, iyi/kötü tecrübelerinin sonucunda ortaya çıkmış yazılım geliştirme teknikleridir.
-Tasarım desenleri iki esasa bağlıdırlar. Tekrar kullanılabilirlik ve esneklik. Yazılan kodlar bu esasa göre yazılmışsa iyi bir yazılım geliştirilmiş denilebilir. Tasarım Desenleri; Creational, Structural ve Behavioral olmak üzere 3 başlığa ayrılır.
- Creational Patterns (Yaratımsal)
Factory Method
Abstact Factory
Builder
Singleton
Prototype
- Structural Patterns (Yapısal)
Adapter
Facade Method
Decorator
Bridge
Composite
Proxy
Flyweight
- Behavioral Patterns (Davranışsal)
Command
Strategy
Observer
State
Template
Iterator
Interpreter
Memento
Chain of Responsibility
Mediator
Visitor
[https://medium.com/gokhanyavas/tasar%C4%B1m-desenleri-gof-design-patterns-16e93e54a92d]
# Day-20
--OOP prensipleri nelerdir?  Abstraction, Sarmalama(encapsulation), polimorfizm, kalıtım(inheritence) ve herbiri nedir acıkla?
İyi bir kod tasarımı için uyulması gereken bazı prensipler vardır. Prensipler zorunlu değildir fakat uyulduğunda hem dünya çapında standart bir kod yazmış oluruz hem de sürdürülebilirliği yüksek bir iş ortaya çıkar. 
1-Abstraction(Soyutlama):
2-İnheritance(Kalıtım):
3-Encapsulation(Kapsülleme):
4-Polymorphism(Çok Biçimlilik):
[https://medium.com/@kamer.dev/oopnin-4-ana-prensibi-encapsulation-inheritence-abstraction-polymorphism-712ed2fbac7e]
[https://medium.com/@sumeyyeturkmen/4-temel-oop-prensibi-9bd4a36d35a1]

# Day-21 
1-Abstraction(Soyutlama):
Detayların, karmaşıklığın azaltılması anlamına gelmektedir.Bir nesnenin neleri içermesi gerektiğine odaklanmayı ve önemli bilgileri gösterirken istenmeyen ayrıntıları gizlemeyi amaçlar. Büyük projelerde yapılan çalışmaların hepsini bilmek gereksizdir.Projelerin detaylarında kaybolmak yerine işlevleri göstermeye odaklanmak projeyi daha iyi anlamamızı sağlar.

# Day-22
2-İnheritance(Kalıtım):
Türkçe karşılığı ‘miras alma, kalıtım’dır. Inheritance; bir nesnenin özelliklerinin başka nesneler tarafından kullanılabilmesine olanak sağlar. Sınıflar arasında hiyearşik bir yapı kurabilmek için kullanılır. Inheritance bir sınıfın kendi özellikleri ve metotları yanı sıra kalıtım aldığım base(taban) sınıfın özellikleri ve metotlarına da sahip olabilmesidir.Ancak kalıtım alan sınıf herhangi bir özellik veya metoda sahip olmasa da olur.
# Day-23
3-Encapsulation(Kapsülleme):
Bir varlığı bütün olarak ele almak ve varlığın yapısını dışarıyla oluşabilecek sonuçlara karşı korumayı amaçlar.Bu mekanizma hakkında genel fikir basittir. Bir nesnede dışarıdan görünmeyen bir özelliğiniz varsa ve erişimi sağlayan yöntemlerle bir araya getirirseniz, belirli bilgileri gizleyebilir ve nesnenin iç durumuna erişimi kontrol edebilirsiniz.
# Day-24
4-Polymorphism(Çok Biçimlilik):
Genel olarak, birçok biçimde görünme yeteneği.OOP(Nesneye yönelik programlama)’da, polimorfizm, bir programlama dilinin veri türüne veya sınıfına bağlı olarak nesneleri farklı şekilde işleme yeteneğini ifade eder.Daha spesifik olarak, türetilmiş sınıflar için yöntemleri yeniden tanımlama yeteneğidir. OOP’de polimorfizmin en yaygın kullanımı, bir alt sınıf nesnesini belirtmek için bir üst sınıf referansı kullanıldığında ortaya çıkar.
[https://medium.com/@kamer.dev/oopnin-4-ana-prensibi-encapsulation-inheritence-abstraction-polymorphism-712ed2fbac7e]
[https://medium.com/@sumeyyeturkmen/4-temel-oop-prensibi-9bd4a36d35a1]
# Day-25
dizilerin dezavantajları
- dizilere tek tip veri eklenebilmesi
- oluşturken boyutlarının belirlenmesi
- key value ilişkisi kurulamaması

# Day-26
arraylist listin özel bir türüdürür.
````java

List<String> listOrnegi=new ArrayList<String>();

````
# Day-27
diziyi sıralamak için `sort` kullanılır ve search(arama) yapmak için mutlaka sıralı bir liste kullanılması gerekmektedir.
````java
Collections.sort(dizi) 
````
dizi içeriside değer arayıp index bulma
````java
int indexDegeri=Collections.binarySearch(liste,"arananDeger")
````

--Web Service nedir? Ne işe yarar?
--Servlet nedir?
--XML nedir, XSD nedir ?
--Yazılım yaşam döngüsü adımları nelerdir ?
--hibernate ne işe yarar? faydası nedir?
--maven nedir? ne işe yarar?
--Javada değişken tanımlanırken hangisi kullanılabilir
  a) # b)@ c)$ d)* e)^