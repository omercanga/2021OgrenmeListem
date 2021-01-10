# Day-1
Javascript notification api kullanımı
https://www.muratoner.net/javascript/javascript-notification-api-kullanimi

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

# Day-2
JavaScript Window - The Browser Object Model
https://www.w3schools.com/js/js_window.asp

window.document.getElementById("header");
document.getElementById("header");


# Day-3
log'a yazdırma
javascript-debugging-tips
https://raygun.com/learn/javascript-debugging-tips
console.log()

# Day-4
Komut satırı ile Git-Readme dosyası oluşturma
echo "#dosyaismi" >>README.md
git repoya push yapma
git remote add origin https://githubblabla...
git push -u origin master

hem commit hem mesaj aynı anda yapmak için
git commit -am "mesajlı komit yapıldı."

projeyi klonlamak
git clone https://githubblabla...

orjin dosyayı görmek için
git remote -v

# Day-5
remote tarafta ki dosyaları önce kopyalar sonra merge geçer
git fetch 
git merge :wq

git pull =git fetch + git merge
 
# Day-6 
git checkout -b branchismi

git push origin branchismi

--master'a geçiyor
git checkout master 

# Day-7
--branch silme
git branch -d branchismi

--github 
Spoon Knife ornek repo test için

--githubda statik site yayınlama
repository name=>> omercanga.github.io


# Day-8
AJAX: Asynchronous JavaScript and XML, tüm sayfayı kullanıcıya tekrar yükletmeden ekrana getiren veya servera gönderen bir çok programlama dili ile uyumlu çalışan bir tekniktir.
jQuery: HTML dokümanların yönetiminde, animasyonların oluşturulmasında, etkileşimli Web sayfaların hazırlanmasında kullanılan Javascript kütüphanesidir.
Angular JS: Front-end gelirştirmede kullanılan bir Javascript kütüphanesidir.
Backbone: Front-end gelirştirmede kullanılan bir Javascript kütüphanesidir.
Node JS:  Javascript motoru üzerinde çalışan, Event-driven, nonblocking I/O modeli kullanan, ölçeklenebilir uygulamalar geliştirmek için dizayn edilmiş bir platformdur.
Knockout: Front-end gelirştirmede kullanılan bir Javascript kütüphanesidir.
Ember JS: Front-end gelirştirmede kullanılan bir Javascript kütüphanesidir.

# Day-9
https://www.freecodecamp.org/news/javascript-foreach-how-to-loop-through-an-array-in-js/
const numbers = [1, 2, 3, 4, 5];
//for ornek
for (i = 0; i < numbers.length; i++) {
  console.log(numbers[i]);
} 
//foreach ornek
numbers.forEach(function(number) {
    console.log(number);
});

# Day-10
js cookie example
```
function setCookie(cname, cvalue, exdays) {
  var d = new Date();
  d.setTime(d.getTime() + (exdays*24*60*60*1000));
  var expires = "expires="+ d.toUTCString();
  document.cookie = cname + "=" + cvalue + ";" + expires + ";path=/";
}
```
add cookie time expires dates
```
document.cookie = "name=value; expires=date; path=path;domain=domain; secure";
document.cookie = "someCookieName=true; expires=Fri, 31 Dec 9999 23:59:59 GMT";
```