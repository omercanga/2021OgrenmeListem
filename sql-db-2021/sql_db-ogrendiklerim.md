# Day-1
with ur?
“with ur” in a query tells DB2 that you want to use the Uncommitted Read isolation level.
The WITH clause specifies the isolation level at which the statement is executed. 
(Isolation level does not apply to declared temporary tables because no locks are acquired.)
```
U can use the following combination in WITH clause...
-CS Cursor stability
-UR Uncommitted read
-RR Repeatable read
-RR KEEP UPDATE LOCKS
Repeatable read keep update locks
-RS Read stability
-RS KEEP UPDATE LOCKS
Read stability keep update locks
```

# Day-2
İnner Join
https://medium.com/gokhanyavas/t-sql-join-i%CC%87%C5%9Flemleri-b2181ed3118b

# Day-3
SQL Distinct İfadesi

Bazen bir tablonun bazı kolonlarında tekrarlanan değerler (veriler) olabilir.
Ancak tekrarlanan verileri eleyerek her farklı veriden yalnız bir adet 
bulunmasını istiyorsak DISTINCT anahtar sözcüğünü kullanırız.

SELECT DISTINCT Şehir FROM Kişiler
SELECT DISTINCT cinsiyet FROM uyeler

# Day-4
SQL ORDER BY (Sıralama)

SELECT sorgusu ile çektiğimiz kayıtları (sonuç kümesini) 
sıralamak için ORDER BY anahtar kelimesini kullanırız. 
Bu sıralama belirtilen kolona göre yapılır. Ve varsayılan olarak artan
(küçükten büyüğe) sıradadır. 
ORDER BY için sözdizimi (syntax – sintaks) aşağıdaki gibidir:
``` sql
SELECT kolon_adı(ları)
FROM tablo_adı
ORDER BY kolon_adı(ları) ASC|DESC
```
# Day-5
GROUP BY Kullanımı

GROUP BY ifadesi tabloyu veya birlikte sorgulanan tabloları
gruplara bölmek için kullanılır. Genel kullanımı aşağıdaki gibidir. 
GROUP BY ifadesi ORDER BY gibi sonuçları sıralamak için değil 
gruplara göre hesaplama yapılacağı zaman kullanılır.

Soru: Sınıflardaki öğrenci sayısını bulun.
SELECT sinif, count(*) from ogrenci group by sinif

# Day-6
DDL, DML, DCL, TCL Nedir?
DDL (Data Definition Language) Nedir?
Veri Tanımlama Dili (DDL) deyimleri tabloları, veritabanı yapısı veya şema tanımlamak için kullanılır.

Bunlardan bazıları;
CREATE – Veritabanındaki nesneleri oluşturmak için kullanılır.
ALTER – Veritabanı nesnelerinin yapısını değiştirmek için kullanılır.
DROP – Veritabanındaki nesneleri silmek ya da başka bir ifadeyle ilgili nesneleri bütünüyle kaldırmak için kullanılır.
TRUNCATE – Kayıtlar için ayrılan tüm boşluklar dahil, bir tablodaki tüm kayıtları kaldırılır
COMMENT – Veri sözlüğüne yorum eklemek için kullanılır.
RENAME – Bir nesneyi yeniden adlandırmak için kullanılır.

**DML (Data Manipulation Language)** Nedir?
Veri İşleme Dili (DML) deyimleri tablo ya da şema nesneleri içindeki verileri yönetmek için kullanılır.

Bunlardan bazıları;
```
SELECT – Veritabanından kayıt çekmek için kullanılır.
INSERT – Tabloya kayıt ya da kayıtları eklemek için kullanılır.
UPDATE – Tablodaki kayıt ya da kayıtları güncellemek için kullanılır.
DELETE – Tablodan kayıt ya da kayıtları silmek için kullanılır (Veriler silinse de ancak kapladığı alan kalır)
MERGE – UPSERT işlemi (ekleme veya güncelleme), başka bir ifadeyle birleştirme yapar.
CALL – PL/SQL veya Java alt programını çalıştırır.
EXPLAIN PLAN – Verilere erişim yolunun detaylarını açıklamak için kullanılır.
LOCK TABLE – Kontrolü eş zamanlılığı sağlamak için kullanılır.
```
**DCL (Data Control Language)** Nedir?
Veri Kontrol Dili (DCL) deyimleri yetkilendirme ya da ayrıcalıkları belirlemek için kullanılır.

Bunlardan bazıları;
GRANT – Belirli bir kullanıcı ya da gruba veritabanının belirtilen nesnelerine erişim ayrıcalıklarını verir.
REVOKE – GRANT komutu ile verilen ayrıcalıkların bir kısmını ya da tümünü geri almak için kullanılır.

TCL (Transaction Control) Nedir?
İşlem Kontrol (TCL) deyimleri DML ifadeleri tarafından yapılan değişiklikleri yönetmek için kullanılır.

Bunlardan bazıları;
COMMIT – Yapılanları kalıcı hale getirir. İşin tamamlanmasını sağlar.
SAVEPOINT – Daha sonra geri dönülecek bir dönüş noktası belirler.
ROLLBACK – Son COMMIT’e kadar olan yeri geri alır.

# Day-7
UNION operatörü ile farklı tablolardaki seçeceğimiz alanları birleştirerek tek bir tabloymuş gibi gösterebiliriz. Kriterlere uygun olan kayıtları bir kez dikkate alır, tekrarlı kayıtları ekrana getirmez.

Tekrarlı kayıtların da ekrana gelmesini istiyorsak  UNUON ALL kullanırız.

Kullanım Şekli:
```
Select alan_ad(ları)_1   from tabloadı_1
```
**UNION ALL**
```
Select alan_ad(ları)_2   from tabloadı_2
```
Select ifadesinden sonra gelen alan sayısı her iki tabloda da aynı olmalıdır. Alan adları farklı olabilir.

# Day-8 
SQL Always On: Uygulamaların yüksek erişilebilir olması ve sistemde oluşacak bir hata sonucu sistemin çalışmasının minimum seviyede aksamasının sağlayan bir SQL teknolojisidir.

SQL Replication: Kaynak veri tabanının aynısı, sürekli yenilerek, başka bilgisayarlarda da tutulma teknolojisidir.

Performance Tuning: SQL performans yönetimi teknolojisidir.

# Day-9
QueryStore: SQL Server‘de plan değişikliklerinden dolayı yaşanılan performans problemleri için geliştirilmiş bir teknolojidir.

# Day-10
HAVING ve  WHERE Arasında ki farklar
the difference between the having and where clause in SQL is that the where clause cannot be used with aggregates, but the having clause can.
The where clause works on row’s data, not on aggregated data. 

# Day-11
Like operator for integer
SELECT * FROM WHERE CAST(phone AS VARCHAR(9)) LIKE '%0203'

# Day-12
 “Delete” ve “truncate” komutları arasındaki farklar; Ana fark delete komutu tablodan tek sıra silerken truncate hepsini siler.
Diğer bir önemli fark delete kullanıldıktan sonra bir sorun çıktığı zaman geri almak için kullanılmasıdır.
truncate komutu kullanıldığında böyle bir şey gerçekleştirilemez. Ayrıca truncate oldukça hızlıdır.

# Day-13
“table” ve “field” ;Table sıralara ve sütunlara dönüştürülmüş organize verilerdir.
Field ise bir table’daki sütunların sayısıdır.

# Day-14
“join” nedir?
join komutu farklı table’lardan sıraları birleştirir. Bu sıraların birleşme şekli onlarla birlikte olan sütunlara göre değişir.
Bu komut sayesinde iki table’ı bir bütün haline getirebilir veya bir table’dan diğerine veri aktarabilirsiniz.
Toplamda dört farklı join türü vardır: inner, full, left ve right.

# Day-14
“view” nedir?
view, table’ın sanal temsilidir. View’lar bir table’dan fazla veriyi yansıtabilir ve birleştirilebilir. Oldukça durum ve ilişki bağımlıdır.

# Day-15
constraint’ler, bir table’da kullanılan belli bir veri türünün sayısının belirtmek için kullanılan komutlardır.

# Day-16
SQL query’leri içerisinde şu anki saati ve tarihi günü gösteren GetDate() komutu mevcuttur.

# Day-17
Denormalization, veri tabanına üst formlardan alt formlara doğru eriştiğiniz işlemdir.

# Day-18
Unique :Her bir verinin birbirinden farklı olmasın sağlanmasıdır.
````sql
CREATE TABLE kisiler (
  kisi_sira INT UNIQUE,
  kisi_adi VARCHAR(20),
  kisi_soyadi VARCHAR(30),
  kisi_eposta VARCHAR(50)
);
````
[https://www.yusufsezer.com.tr/sql-foreign-key/]

# Day-19
primary key kavramı Unique kısıtlamasına benzer bir kullanımı olmasına rağmen farkı değer olarak NULL içermemesi ve her tabloya sadece bir tane eklenebilmesidir. Özetle primary keyin kullanım amacı her bir satırın farklı olmasını garantilemektir.
````sql
CREATE TABLE kisiler (
  kisi_sira INT,
  kisi_adi VARCHAR(20),
  kisi_soyadi VARCHAR(20),
  kisi_eposta VARCHAR(50),
  CONSTRAINT PK_sira_eposta PRIMARY KEY(kisi_sira, kisi_eposta)
);
````
[https://www.yusufsezer.com.tr/sql-foreign-key/]
# Day-20
Foreign key :SQL Primary Key  veya SQL Unique  ile birlikte iki tabloyu ilişkilendirmek için kullanılan bir kısıtlamadır. 
Kısıtlamasının kullanım amacı veri bütünlüğünü sağlamaktır
````sql
CREATE TABLE tablo_adi (
  sutun_adi veritipi kısıtlama,
  ...
  ...
  CONSTRAINT FK_adi FOREIGN KEY (sutun_adi) REFERENCES diger_tablo_adi(diger_sutun_adi)
    ON UPDATE <EYLEM>
    ON DELETE <EYLEM>
);
````
[https://www.yusufsezer.com.tr/sql-foreign-key/]

# Day-21
Foreign key eylemleri
Foreign key kısıtlamasına ait eylemler kullanılan VTYS göre değişmektedir.
- CASCADE
- NO ACTION
- SET NULL
- NOT: 
- RESTIRCT

# Day-22
### CASCADE:
REFERENCES: ile belirtilen sütunda bir eylem (UPDATE, DELETE) olduğunda Foreign key ile belirtilen ilişkili sütunda benzer eylemi yapar.
### NO ACTION: 
Foreign key sütunu ve REFERENCES ile belirtilen sütunda bir ilişki varsa, REFERENCES ile belirtilen sütunda bir eyleme (UPDATE, DELETE) izin vermez.
### SET NULL: 
REFERENCES ile belirtilen sütunda bir eylem (UPDATE, DELETE) olduğunda Foreign key ile belirtilen ilişkili sütunu NULL yapar.
### NOT:
Foreign key sütununda NOT NULL kısıtlaması varsa hata verir.
### RESTIRCT:
MySQL VTYS içerisinde bulunan bu eylem NO ACTION: ile aynı işleve sahiptir.
