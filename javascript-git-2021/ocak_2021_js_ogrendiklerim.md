# Day-1
Javascript notification api kullanımı
```js
var notification = new Notification('Başlık', { 
    body: 'Mesaj gövdenizi buraya yazın',
    icon: '/simle_yolunuz/icon.png' // opsiyonel
});
 
notification.onclose = function(){
    console.info("kapatıldı")
}
 
notification.onshow = function(){
    console.info("gösterildi")
}
 
notification.onclick = function(){
    console.info("tıklandı")
}
```
- [Kaynak](https://www.muratoner.net/javascript/javascript-notification-api-kullanimi)

# Day-2
JavaScript Window - The Browser Object Model

```
window.document.getElementById("header");
document.getElementById("header");
```
- [Kaynak](https://www.w3schools.com/js/js_window.asp)

# Day-3
log'a yazdırma
javascript-debugging-tips
console.log()

- [Kaynak](https://raygun.com/learn/javascript-debugging-tips)

# Day-4
Komut satırı ile Git-Readme dosyası oluşturma
```git
echo "#dosyaismi" >>README.md
```
git repoya push yapma
```git
git remote add origin https://githubblabla...
git push -u origin master
```
hem commit hem mesaj aynı anda yapmak için
```
git commit -am "mesajlı komit yapıldı."
```
projeyi klonlamak
```
git clone https://githubblabla...
```
orjin dosyayı görmek için
```
git remote -v
```

# Day-5
remote tarafta ki dosyaları önce kopyalar sonra merge geçer
```
git fetch 
git merge :wq
```
**git pull** =git fetch + git merge
 
# Day-6 
git checkout -b branchismi
git push origin branchismi

master'a geçiyor
```
git checkout master 
```
# Day-7
branch silme
```
git branch -d branchismi
```
github 
Spoon Knife ornek repo test için

githubda statik site yayınlama
```
repository name=>> omercanga.github.io
```

# Day-8
AJAX: Asynchronous JavaScript and XML, tüm sayfayı kullanıcıya tekrar yükletmeden ekrana getiren veya servera gönderen bir çok programlama dili ile uyumlu çalışan bir tekniktir.
jQuery: HTML dokümanların yönetiminde, animasyonların oluşturulmasında, etkileşimli Web sayfaların hazırlanmasında kullanılan Javascript kütüphanesidir.
Angular JS: Front-end gelirştirmede kullanılan bir Javascript kütüphanesidir.
Backbone: Front-end gelirştirmede kullanılan bir Javascript kütüphanesidir.
Node JS:  Javascript motoru üzerinde çalışan, Event-driven, nonblocking I/O modeli kullanan, ölçeklenebilir uygulamalar geliştirmek için dizayn edilmiş bir platformdur.
Knockout: Front-end gelirştirmede kullanılan bir Javascript kütüphanesidir.
Ember JS: Front-end gelirştirmede kullanılan bir Javascript kütüphanesidir.

# Day-9
js for ve foreach ornek
```js
const numbers = [1, 2, 3, 4, 5];
//for ornek
for (i = 0; i < numbers.length; i++) {
  console.log(numbers[i]);
} 
//foreach ornek
numbers.forEach(function(number) {
    console.log(number);
});
```
- [Kaynak](https://www.freecodecamp.org/news/javascript-foreach-how-to-loop-through-an-array-in-js/)
# Day-10
js cookie example
```js
function setCookie(cname, cvalue, exdays) {
  var d = new Date();
  d.setTime(d.getTime() + (exdays*24*60*60*1000));
  var expires = "expires="+ d.toUTCString();
  document.cookie = cname + "=" + cvalue + ";" + expires + ";path=/";
}
```
add cookie time expires dates
```js
document.cookie = "name=value; expires=date; path=path;domain=domain; secure";
document.cookie = "someCookieName=true; expires=Fri, 31 Dec 9999 23:59:59 GMT";
```
# Day-11
js excell export alma
```html
<meta http-equiv="content-type" content="text/plain; charset=UTF-8"/>
```
js kısmı
```js
<script type="text/javascript">
var tableToExcel = (function() {
  var uri = 'data:application/vnd.ms-excel;base64,'
    , template = '<html xmlns:o="urn:schemas-microsoft-com:office:office" xmlns:x="urn:schemas-microsoft-com:office:excel" xmlns="http://www.w3.org/TR/REC-html40"><head><!--[if gte mso 9]><xml><x:ExcelWorkbook><x:ExcelWorksheets><x:ExcelWorksheet><x:Name>{worksheet}</x:Name><x:WorksheetOptions><x:DisplayGridlines/></x:WorksheetOptions></x:ExcelWorksheet></x:ExcelWorksheets></x:ExcelWorkbook></xml><![endif]--><meta http-equiv="content-type" content="text/plain; charset=UTF-8"/></head><body><table>{table}</table></body></html>'
    , base64 = function(s) { return window.btoa(unescape(encodeURIComponent(s))) }
    , format = function(s, c) { return s.replace(/{(\w+)}/g, function(m, p) { return c[p]; }) }
  return function(table, name) {
    if (!table.nodeType) table = document.getElementById(table)
    var ctx = {worksheet: name || 'Worksheet', table: table.innerHTML}
    window.location.href = uri + base64(format(template, ctx))
  }
})()
</script>
```

# Day-12
yeni bir branch oluşturma
```git
git branch new-branch
```
branchleri listeleme
```git
git branch 
```
çıktı daki * şuanki varsayılan branch'ı gösterir
```
* master
```

# Day-13
başka bir branchı master' merge etme
```git
# ...develop some code...
$ git add –A
$ git commit –m "Some commit message"
$ git checkout master
Switched to branch 'master'
$ git merge new-branch
```
- [Kaynak](https://stackabuse.com/git-merge-branch-into-master/) 

git rabase ornek

```
git checkout master
git pull
git checkout test
git pull
git rebase -i master
git checkout master
git merge test
```
- [Kaynak](https://stackoverflow.com/questions/5601931/what-is-the-best-and-safest-way-to-merge-a-git-branch-into-master)

# Day-14
Node JS , back-end geliştirme ve uygulama işlemlerini gerçekleştirmek için tasarlanmış JavaScript tabanlı bir araçtır. 

# Day-15
Node JS kullanmak için bir kaç sebep;Hızlı, asenkron, tek bir genelleştirilmiş programlama dili ve veri türü vb...
Genel olarak, Node JS JavaScript tabanlı sunucu tarafı geliştirme söz konusu olduğunda mevcut piyasadaki en iyi araçlardan biridir. 

# Day-16
 “Real DOM”u ve “Virtual DOM”:
DOM, Document Object Model’in (Belge Nesne Modeli) kısaltmasıdır. DOM’lar bazı özel metinleri anlamak için kullanılır. 
Örneğin web ve uygulama geliştirmede DOM, HTML metinlerini temsil etmek için kullanılır.
React JS virtual DOM’dan faydalanır. Temel olarak React’ın HTML metinlerinin basitleştirilmiş bir kopyasıdır.
React’ın “virtual DOM” kullanması bu JavaScript kütüphanesi hakkında konuşulurken sık sık ele alınan iyi yönlerden biridir. 
React JS sorunuza gelince, bu sorudan sonra “virtual DOM”un “real DOM”dan neden üstün olduğu sorulabilir. 
Cevap oldukça basit; virtual DOM real olandan çok daha hızlı ve ucuzdur.

# Day-17
```js
Compare two strings in the current locale:
var str1 = "cd";
var str2 = "ab";
var n = str1.localeCompare(str2);
```
# Day-18
JavaScript Date Reference
```js
var d = new Date();
var d = new Date(milliseconds);
var d = new Date(dateString);
var d = new Date(year, month, day, hours, minutes, seconds, milliseconds);
```
# Day-19
typeof= değişken veri türünü öğrenmek için  typeof operatorü kullanılır.
```js
<script>
  alert(typeof "Yusuf");                  // "string"
  alert(typeof 3.14);                     // "number"
  alert(typeof NaN);                      // "number"
  alert(typeof false);                    // "boolean"
  alert(typeof [1,2,3,4]);                // "object"
  alert(typeof {name:'Yusuf', kilo:78});  // "object"
  alert(typeof new Date());               // "object"
  alert(typeof function () {});           // "function"
  alert(typeof xSayisi);                  // "undefined"
  alert(typeof null);                     // "object"
</script>
```
[https://www.yusufsezer.com.tr/javascript-tip-donusumleri/]
# Day-20
java scriptte değer içermeyen 2 değişken türü vardır. 
- null 
- undefined
[https://www.yusufsezer.com.tr/javascript-tip-donusumleri/]

# Day-21
java scirptte  3 farklı nesne türü vardır.
Object
Date
Array
[https://www.yusufsezer.com.tr/javascript-tip-donusumleri/]

# Day-22
java scirptte  değer saklanabilen 5 değişken türü vardır.
- string 
- number 
- boolean
- object
- function
[https://www.yusufsezer.com.tr/javascript-tip-donusumleri/]

# Day-23
js-Ekrana yazdırma işlemi;
- HTML nesnelerine yazdırma – innerHTML,
- HTML sayfasına yazdırma – document.write(),
- Uyarı pencersine yazdırma – alert(),
- Tarayıcı konsoluna yazdırma – console.log()

# Day-24
 Uzun JavaScript komutları sayfa açılışını yavaşlatabilir. Bu yüzden Sayfa içinde yer alan veya harici JavaScript dosyalarında 
 yer alan kodlar <body> etiketi sonuna eklenirse sayfa daha hızlı açılacaktır.
 
# Day-25
JavaScript kodları sayfaya aşşagıdaki şekillerde eklenebilir;
1. 
```javascript
<script> </ script> etiketleri arasına yazılabilir.,

<script>
  alert("Merhaba JavaScript");
</script>
````

2. HTML elemanına tıklandığını ifade eden ``onclick`` HTML elemanının üzerine gelindiğini ifade eden ``onmouseover``  gibi HTML özelliklerine yazılabilir.

``<button onclick="alert('Merhaba JavaScript')">Tıkla</button>``
3. JavaScript kodları harici  ``.js`` uzantılı dosyaya yazıldıktan sonra ``<script>`` etiketi ``src`` özelliğine dosya adını belirterek yazılabilir.

- JavaScript kodları (ornek.js)

```javascript
alert("Merhaba JavaScript");
```

HTML kodları

```html
<script src="ornek.js"></script>
```

# Day-26
java script fonksiyon yazma
```javascript
<script>
  function Topla(sayi1, sayi2) {
    return sayi1 + sayi2;         // sayi1 ve sayi2 toplamını döndürür
  }
  alert(Topla(10, 5));
</script>

```

# Day-27
java script fonksiyon çağırma
html nesnesine tıklandığında
```javascript
<button onclick="alert('Merhaba JavaScript');">Merhaba</button>
```
fonksiyon çağırma yapıldığında
```javascript
<script>
function uyari(mesaj) {
  alert(mesaj);
}
uyari("Merhaba JavaScript");
</script>
```

# Day-28


 
