#Day-1
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

#Day-2
İnner Join
https://medium.com/gokhanyavas/t-sql-join-i%CC%87%C5%9Flemleri-b2181ed3118b

#Day-3
SQL Distinct İfadesi

Bazen bir tablonun bazı kolonlarında tekrarlanan değerler (veriler) olabilir.
Ancak tekrarlanan verileri eleyerek her farklı veriden yalnız bir adet 
bulunmasını istiyorsak DISTINCT anahtar sözcüğünü kullanırız.

SELECT DISTINCT Şehir FROM Kişiler
SELECT DISTINCT cinsiyet FROM uyeler

#Day-4
SQL ORDER BY (Sıralama)

SELECT sorgusu ile çektiğimiz kayıtları (sonuç kümesini) 
sıralamak için ORDER BY anahtar kelimesini kullanırız. 
Bu sıralama belirtilen kolona göre yapılır. Ve varsayılan olarak artan
(küçükten büyüğe) sıradadır. 
ORDER BY için sözdizimi (syntax – sintaks) aşağıdaki gibidir:

SELECT kolon_adı(ları)
FROM tablo_adı
ORDER BY kolon_adı(ları) ASC|DESC

#Day-5
GROUP BY Kullanımı

GROUP BY ifadesi tabloyu veya birlikte sorgulanan tabloları
gruplara bölmek için kullanılır. Genel kullanımı aşağıdaki gibidir. 
GROUP BY ifadesi ORDER BY gibi sonuçları sıralamak için değil 
gruplara göre hesaplama yapılacağı zaman kullanılır.

Soru: Sınıflardaki öğrenci sayısını bulun.
SELECT sinif, count(*) from ogrenci group by sinif
