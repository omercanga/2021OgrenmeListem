# Day-1
flask rest api create
https://realpython.com/flask-by-example-part-1-project-setup/

# Day-2
Zeep: Python SOAP client
https://docs.python-zeep.org/en/master/

# Day-3
Python Cheat Sheet
https://www.pythoncheatsheet.org/#JSON,-YAML-and-configuration-files

# Day-4
creating-apis-with-python-and-flask
https://programminghistorian.org/en/lessons/creating-apis-with-python-and-flask

# Day-5
How to Run a Python Script using Docker?
https://www.geeksforgeeks.org/how-to-run-a-python-script-using-docker/

# Day-6
docker komutlar
**çalışan servisleri listeler :**docker service ls
**nginx procesisi ile ilgili bilgi verir :**docker service ps nginx  
**servis oluşturuyor :**docker service create --name=nginx -p 80:80 nginx:latest

# Day-7
docker makinelerin ip bilgilerini verir
docker-machines ls
network oluşturma
docker network create -d=overlay odevler
busybox oluşturma
docker service  create -d --name box1 -t --network=odevler busybox:latest
workere bağlanma
docker-machine ssh worker1

# Day-8
**Docker Commands**

```
docker run – Runs a command in a new container.
docker start – Starts one or more stopped containers
docker stop – Stops one or more running containers
docker build – Builds an image form a Docker file
docker pull – Pulls an image or a repository from a registry
docker push – Pushes an image or a repository to a registry
docker export – Exports a container’s filesystem as a tar archive
docker exec – Runs a command in a run-time container
docker search – Searches the Docker Hub for images
docker attach – Attaches to a running container
docker commit – Creates a new image from a container’s changes

```
# Day-9
[https://medium.com/javascript-in-plain-english/7-basic-docker-commands-38d1a29ee9d3 ]


# Day-10

docker hubde container image indirme
docker image pull omercanga/app1

çekilen imajın çalıştırılması
docker container  run --name ilkcontainer omercanga/app1

indirilen container ikinci kez çalıştırıldı.
docker container  run --name ikincicontainer omercanga/app1

liberty server pull etmek yani indirmek
docker pull websphere-liberty

# Day-11
Django: Python Programlama diliyle yazılmış MTV mimari deseni kullanılan, yüksek seviyeli web kütüphanesidir.

# Day-12
Flask: Güçlü ve kolay öğrenilebilen bir kütüphanedir. Hafif uygulamalar ve projeler için uygundur.

# Day-13
CherryPy: Nesne Yönelimli Programlama’ya dayalı web geliştirme ortamıdır.
Web2Py: Web uygulamaları geliştirmek için kullanılan tüm web kütüphanelerinin en basitidir.

# Day-14
Özel Nesnelerin inşasında ve başlatılmasında kullanılan Python'un 3 sihirli yöntemi
__init()__
__new()__
__del()__

# Day-15
Run Jenkins on Docker
First, clone the project:
git clone https://github.com/fabianenardon/jenkins-docker-demo
docker-compose up
[https://github.com/docker/labs/blob/master/developer-tools/java/chapters/ch09-cicd.adoc]

# Day-16
python init kullanım
```python
class Dog:

    def __init__(self, name, age):  
        self.name = name
        self.age = age

    def bark(self):
        print("bark bark!")

    def doginfo(self):
        print(self.name + " is " + str(self.age) + " year(s) old.")

    def birthday(self):
        self.age +=1
```
# Day-17
Python Tuple is used to store the sequence of immutable Python objects. 
The tuple is similar to lists since the value of the items stored in the list can be changed, whereas the tuple is immutable, and the value of the items stored in the tuple cannot be changed.

Creating a tuple
A tuple can be written as the collection of comma-separated (,) values enclosed with the small () brackets. The parentheses are optional but it is good practice to use. A tuple can be defined as follows.

T1 = (101, "Peter", 22)    
T2 = ("Apple", "Banana", "Orange")     
T3 = 10,20,30,40,50  
  
print(type(T1))  
print(type(T2))  
print(type(T3))  

# Day-18
Python Tuple Negative Indexing
The tuple element can also access by using negative indexing. The index of -1 denotes the rightmost element and -2 to the second last item and so on.

The elements from left to right are traversed using the negative indexing. Consider the following example:
```python
tuple1 = (1, 2, 3, 4, 5)    
print(tuple1[-1])    
print(tuple1[-4])    
print(tuple1[-3:-1])  
print(tuple1[:-1])  
print(tuple1[-2:])  
```
Output:
```
5
2
(3, 4)
(1, 2, 3, 4)
(4, 5)
```

Deleting Tuple
Unlike lists, the tuple items cannot be deleted by using the del keyword as tuples are immutable. To delete an entire tuple, we can use the del keyword with the tuple name.
Consider the following example.
```python
tuple1 = (1, 2, 3, 4, 5, 6)    
print(tuple1)    
del tuple1[0]    
print(tuple1)    
del tuple1    
print(tuple1)    
```
Output:
```
(1, 2, 3, 4, 5, 6)
Traceback (most recent call last):
  File "tuple.py", line 4, in <module>
    print(tuple1)
NameError: name 'tuple1' is not defined
```
# Day-19
linux dizin yapısı
/bin
Sistemin açılışı ve kontrolü için gerekli komutlar. Hem kullanıcıların, hem de sistem görevlisinin kullanabileceği dosyalar (kök dizinde ise fazla şişmemesi koşuluyla) buraya atılabilir. Sadece root kullanıcının ihtiyaç duyacağı init, getty, updatedb gibi programlar /sbin veya /usr/sbin'de durabilir. Bu dizinde bulunan dosyalara örnek olarak cat, chgrp, chown, date, dd, df, ln, mkdir, mount, ps, rm, sh, su, sync ve umount verilebilir.
/dev
G/Ç dosyaları. Linux çekirdeğinde desteklenen her aygıta ait dosya /dev dizini altında bulunur. Kurulum anında bu dosyalar yerine yerleştirilir, bu dosyaların silinmesi durumunda /dev/MAKEDEV ile tekrar yaratılabilirler.
/etc
Sistem yapılandırma dosyaları. Bu dizinde çalıştırılabilir dosyalar bulunmamalıdır.
[http://www.belgeler.org/lis/archive-tlkg-lis-5.11.html]
[https://www.yusufsezer.com.tr/linux-dizin-yapisi/]

# Day-20

/home
Kullanıcılara ayrılmış dizin. Başka şekilde ayarlanmamış ise, açılan her hesaba ait kullanıcı, burayı kullanır. Büyük sistemlerde, bu kısım alt parçalara ayrılabilir (/home/ftpadm , /home/ogrenci gibi)
/lib
Kütüphane dosyaları.
/mnt
Geçici mount edilen dosya sistemleri. Sadece bu iş için kullanıldığından sistem görevlisine zaman kazandırır.
/proc
Süreç kontrollerini ve diğer sistem bilgilerini tutan dosya sistemi. Bu dosya sistemi aslında disk üzerinde yer kaplamaz, tüm dosyalar çekirdeğin bir uzantısı sayılabilir.
[http://www.belgeler.org/lis/archive-tlkg-lis-5.11.html]
[https://www.yusufsezer.com.tr/linux-dizin-yapisi/]

# Day-21

/root
Sistem görevlisinin ev dizini. Mümkünse bu dizini sistemdeki diğer kullanıcıların görmeyeceği şekilde ayarlayın.
/sbin
Hayati sistem komutları. Bir zamanlar bu dosyalar /etc dizini altında yeralıyorlardı. Sadece sistem görevlisinin ihtiyacı olan komutlar, /sbin veya /usr/sbin içinde bulunur.
/tmp
Geçici dosyaların koyulduğu dizin. Belirli zaman aralıklarında temizlenmelidir.
/usr
Diğer önemli sistem dosyalarını tutar. Bu bölüm genelde en kalabalık dizindir, zira yeni kurulan tüm programlar buraya konulur.
[http://www.belgeler.org/lis/archive-tlkg-lis-5.11.html]
[https://www.yusufsezer.com.tr/linux-dizin-yapisi/]

# Day-22

/var
Sürekli değişen sistem bilgileri burada tutulur. İstisnalar dışında diğer makinalarla paylaştırılmaz.
adm
Sistem yönetimini ilgilendiren kayıtlar
preserve
Sistemin göçmesinden sonra zarar görmesi mümkün dosyaların kaydedildiği yer.
spool
Sonra işlenecek olan veriler buraya atılır (e-posta gibi)
[http://www.belgeler.org/lis/archive-tlkg-lis-5.11.html 
[https://www.yusufsezer.com.tr/linux-dizin-yapisi/ ]

# Day-23
linux kısayol tuşları
- <CTRL> <Alt> <BackSpace>  – Grafik arayüzünü sonlandırır.
- <Ctrl><Alt><Del>
Sistemi yeniden başlatmak için kullanılır. Konsoldaki shutdown -r now veya reboot komutu gibi davranır. Makinanın üzerindeki sıfırlama (Reset) tuşuna basmayıp bunu tercih etmeniz gerekir, aksi takdirde ext2 gibi bazı dosya sistemleri sorun çıkarabilir.
- <Tab>
Bir uçbirimde yazmakta olduğunuz komutu tamamlar. Mesela README dosyasını okutmak için more RE yazıp TAB'a basarsanız o anda bulunduğunu dizindeki RE ile başlayan dosyaların listesini görürsünüz, eğer tek dosya varsa satır tamamlanır. Aynı şey komut isimleri için de geçerlidir, bas yazıp TAB'a bastığınızda hemen basename diye komutun tamamlandığını görürsünüz. (Bu işlem çok sayıda komutla eşleşme durumunda bazı uçbirimlerde iki defa TAB tuşuna basmayı gerektirebilir.)
[http://www.belgeler.org/lis/archive-tlkg-lis-5.11.html ]

# Day-24
##Temel Linux Komutları
### Sistem Komutları
- uname -u : Sistem bilgisi(çekirdek sürümü, tarihi ve mimarisi)
- uname -r : Çekirdek sürümü bilgisi
- uptime : Sistemin ne kadar zamandır açık olduğunu ve yükü gösterir
- hostname : Sistem adı
- last reboot : Son kapanma listesi çalışma düzey değişikliği dahil
- date : tarih hakkında bilgi verir
- cal : takvim
- w : hangi kullanıcı o anda hangi komutu çalıştırdığını görürüz.
- whoami : o anki kullanılan kullanıcı adını verir
- finger yakup : Kullanıcı hakkında bilgi verir
- echo “user:passwd” | chpasswd : Tek satırda parola yenilemek
 [https://yakupseker.medium.com/her-linux-kullan%C4%B1c%C4%B1s%C4%B1n%C4%B1n-bilmesi-gereken-temel-komutlar-ve-tu%C5%9F-k%C4%B1sayollar%C4%B1-125-komut-1552423cf7db ]

# Day-25
##Temel Linux Komutları
### Donanım Komutları
- dmesq : Kernel mesajlarını verir
- cat /proc/cpuinfo : İşlemci hakkında bilgi verir
- cat /proc/meminfo : Bellek(RAM) hakkında bilgi verir
- cat /proc interrupts : CPU Çekirdek sistem kesme listesi
- lshw : Sistemin donanım konfigurasyon bilgileri
- lsblk : Disk Bölümleme tablosu
- free -m : Sistemde kullanılan ram bilgisi
- lspci -tv : PCI cihazlarını listeler
- lsusb -tv : USB cihazlarını listeler
- dmidecode : BIOS donanım bilgisi
- hdparm -i /dev/sda : Disk hakkında bilgi verir
- hdparm -tT /dev/sda : Kullanılan disk için okuma hız testi
- badblocks -s /dev/sda : Ulaşılamayan block tespiti
 [https://yakupseker.medium.com/her-linux-kullan%C4%B1c%C4%B1s%C4%B1n%C4%B1n-bilmesi-gereken-temel-komutlar-ve-tu%C5%9F-k%C4%B1sayollar%C4%B1-125-komut-1552423cf7db ]

# Day-26
##Temel Linux Komutları
### Kullanıcılar
- cat /etc/passwd : Tüm kullanıcıları listeler
- id : Kullanıcı id bilgisi
- last : Sisteme en son giriş yapmış kullanıcıların bugünden geriye doğru listesi
- who : Sisteme kayıtlı kullanıcılar
- groupadd : Sistemde yeni bir grup oluşturur
- useradd yakup : Sisteme yakup isimli bir kullanıcı ekler
- userdel yakup : Sistemden yakup isimli kulllanıcıyı siler
- usermod : Kullanıcı izinlerini değiştirme
 [https://yakupseker.medium.com/her-linux-kullan%C4%B1c%C4%B1s%C4%B1n%C4%B1n-bilmesi-gereken-temel-komutlar-ve-tu%C5%9F-k%C4%B1sayollar%C4%B1-125-komut-1552423cf7db ]

# Day-27
##Temel Linux Komutları
### Dosya Komutları
- ls -la : Dosyaları listeler (a gizli olanlar, l detaylı)
- pwd : Mevcut dizin gösterir
- mkdir : Dizin oluşturur
- rm : Dosya silme
- rm -r : Dizin sil(alt dizinlerde dahil)
- rm -f : Sormadan siler
- rm -rf : Dizini ve alt dizinleri sormadan siler
- cp : Dosyayı kopyala
- cp -r home1 home2 : home1 isimli dizini home2 ye taşı yoksa kapyala
- mv : Dosyaları taşıma
- ln -s “/home/yakup/bgpdump” /usr/local/bin : bin klasörüne bgpdump uygulaması için kısayol oluşturur
- touch : Dosya oluştur
- cat : Dosya içeriğinin tümünü oku
- more : Dosyanın içeriğini sayfalayarak göster
- head : Dosya içeriğinin ilk 10 satırını göster
- tail : Dosya içeriğinin son 10 satırını göster
- tail -f : Dosyanın içeriğinin son 10 satırını anlık gösterir
 [https://yakupseker.medium.com/her-linux-kullan%C4%B1c%C4%B1s%C4%B1n%C4%B1n-bilmesi-gereken-temel-komutlar-ve-tu%C5%9F-k%C4%B1sayollar%C4%B1-125-komut-1552423cf7db ]

# Day-28
##Temel Linux Komutları
### İşlem Komutları
- ps : Çalışan süreçler
- ps aux | grep uygulama adı : Adı verilen uygulamanın çalışan süreçleri
- pmap -x PID : İşlemin bellek haritası
- kill : İşlemi bitir
- killall : Bütün işlemleri bitir
- pkill -f telnet : İşlemi bitir
- bg : Durdurulmuş işleme arkaplanda devam et
- fg : Arkaplanda yapılan işlemi ön plana getir
 [https://yakupseker.medium.com/her-linux-kullan%C4%B1c%C4%B1s%C4%B1n%C4%B1n-bilmesi-gereken-temel-komutlar-ve-tu%C5%9F-k%C4%B1sayollar%C4%B1-125-komut-1552423cf7db ]

# Day-29
##Temel Linux Komutları
###