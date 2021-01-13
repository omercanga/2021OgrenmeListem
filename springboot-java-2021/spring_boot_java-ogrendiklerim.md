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
10 Tips to Handle Null Effectively
https://dzone.com/articles/10-tips-to-handle-null-effectively

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