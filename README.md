# Giriş

Javascript HTML'in ve Web platformunun programlama dilidir. Öğrenmesi oldukça kolaydır. Bu dökümantasyon size JS hakkında size temel bilgi sağlayacak.

## Neden Javascript Öğrenelim?

Javascript tüm web geliştiricilerinin bilmesi gereken üç dilden bir tanesidir.

1. **HTML:** Web sayfalarının içeriğini oluşturur.
1. **CSS:** Sayfaların görüntü bakımından düzen ve yerleşimini sağlar.
1. **JS:** Web sayfalarının nasıl davranacağını programlar.

Javascript'in kullanıldığı tek alan elbette sadece web siteleri değil. Çokça masaüstü ve ve server taraflı programlar Javascript'i kullanmaktadırlar. Bunların arasından Node.JS gayet popüler olmakla beraber ayrıca MongoDB , CouchDB gibi bazı veri tabanlarıda programlama dili olarak Javascript kullanıyorlar.

## Biiiyor muydunuz?

Javascript ve Java gerek konsept gerekse tasarım bakımından birbirlerinden tamamen farklı dillerdir.

Javascript ilk olarak Brendan Eich tarafından 1995'te ortaya atıldı ve 1997'de ECMA standartı haline geldi. Standartın resmi adı ECMA-262 idi. ECMAScript dilin, resmiyetteki adıdır.

# Başlayalım

## Javascript HTML elementlerinin içeriğini değiştirebilir.

`getElementById()` çokça Javascript metotlarından yalnızca bir tanesidir.

Bu metotu örneğimizde ID'si demo olan bir HTML elementini bulmak ve onun üzerinde işlemler yapmak, mesela içeriğini (`innerHTML`) değiştirmek için kullanacağız.

```javascript
document.getElementById('demo').innerHTML = 'Merhaba JavaScript';
```

> Javascript dilinde tek tırnak da çift tırnak da geçerlidir.

```javascript
document.getElementById('demo').innerHTML = 'Merhaba JavaScript';
```

## JavaScript HTML Elementlerinin Özelliklerini Değiştirebilir

Bu örnekte Javascript ile `img` etiketinin `src` özelliğini değiştireceğiz.

[Örnek](https://www.w3schools.com/js/tryit.asp?filename=tryjs_intro_lightbulb)

## JavaScript HTML Elementlerinin Stillerini (CSS) Değiştirebilir

JavaScript ile bir elementin stilini değiştirmek, elementin özelliğini değiştirmenin başka bir türüdür.

```javascript
document.getElementById('demo').style.fontSize = '35px';
```

## JavaScript HTML Elementlerini Gizleyebilir/Gösterebilir

HTML elementleri gizlemek, elementin `display` stil özelliğini değiştirerek mümkün. Aynısı gizli olan bir elementi göstermek için de geçerli.

```javascript
document.getElementById('demo').style.display = 'none';
```

```javascript
document.getElementById('demo').style.display = 'block';
```

# JavaScript Nereye?

## \<script> etiketleri

HTML'de, JavaScript kodları mutlaka script etiketi içerisine gömülü olmalıdır.

```javascript
<script>
document.getElementById("demo").innerHTML = "My First JavaScript";<
</script>
```

> Eski JavaScript örnekleri script etiketleri içerisinde type="text/javascript" değerini içerebilir.<br>Bu özellik zorunlu değildir. HTML'in varsayılan script dili zaten JavaScript'tir.

## JavaScript Fonksiyon ve Eventları

Yazılımcı tarafından belirlenen yerde çağrılıp kullanılabilecek JavaScript kodlarından oluşan bloklara JavaScript fonksiyonu diyebiliriz. Mesela bir event tetiklendiğinde spesifik örnek vermek gerekirse kullanıcı bir butona tıkladığı zaman çağırabileceğimiz kod blokları.

> İlerleyen bölümlerde fonksiyonlar ve eventlar hakkında daha fazla bilgi yer almaktadır.

## \<head> veya \<body> etiketlerinde JavaScript

Bir HTML dökümanına istediğimiz sayıda script eklememiz mümkün.
Bu scriptler HTML dökümanın \<head> veya \<body> kısmında yer alabilirler.

## \<head> kısmında JavaScript

Bu örnekte bir JavaScript fonksiyonu dökümanın \<head> kısmında yerleştirilmiş olacak. Bu fonksiyon butona tıklandığı zaman tetiklenecek.

```html
<!DOCTYPE html>
<html>
	<head>
		<script>
			function myFunction() {
				document.getElementById('demo').innerHTML = 'Paragraph changed.';
			}
		</script>
	</head>
	<body>
		<h1>A Web Page</h1>
		<p id="demo">A Paragraph</p>
		<button type="button" onclick="myFunction()">Try it</button>
	</body>
</html>
```

## \<body> kısmında JavaScript

Aynen yukarda olduğu gibi bu örnekte de fonksiyon dökümanın \<body> kısmında yer alacak ve işlevi aynı olacak.

```html
<!DOCTYPE html>
<html>
	<body>
		<h1>A Web Page</h1>
		<p id="demo">A Paragraph</p>
		<button type="button" onclick="myFunction()">Try it</button>

		<script>
			function myFunction() {
				document.getElementById('demo').innerHTML = 'Paragraph changed.';
			}
		</script>
	</body>
</html>
```

> Scriptleri \<body> elementinin içinde en aşağı kısımlara yerleştirmek hız açısından avantajlı olacaktır. Zira o script içeriğinin yorumlanması yavaşlık doğurabileceğinden dolayı tüm HTML elementlerinin altına yerleştirildiği zaman çok fazla yansımayacak ve hissedilmeyecektir.

## External JavaScript

Scriptler ayrıca tamamen harici dosyalardan da dahil edilebilir. Mesela scriptDosyam isminde bir JS dosyası oluşturalım ve içeriğini örnekteki hale getirelim.

```js
function myFunction() {
	document.getElementById('demo').innerHTML = 'Paragraph changed.';
}
```

Farklı sayfalarda da kullanabileceğimiz scriptleri böyle dosya haline getirip kod fazlalığını önlememiz mümkün. Javascript dosyalarının uzantısı `.js` olmalıdır. Şimdi bu dosyayı HTML dökümanımıza gömmek için script etiketlerini açacağız ve src özelliğine bu dosyayı belirteceğiz:

```html
<script src="myScript.js"></script>
```

Bu script etiketlerini de yukarıda değindiğimiz üzere \<head> veya \<body> elementleri içerisinde kullanabiliriz.

> Harici script dosyaları \<script> tagları içermez.

## External JavaScript Avantajları

JavaScript kodlarını harici dosyalara taşımanın bazı avantajları mevcut:

-   HTML ve JS kodlarının birbirine karışmasını önler.
-   Okunabilirliği arttırır.
-   Script dosyalarını re-usable yani tekrar kullanılabilir hale getirir, böylelikle birbirini tekrar eden kodlar da ortadan kalkmış olur.

Bir kaç tane script dosyasını HTML dökümanına gömmek için bir kaç tane \<script> etiketi kullanabiliriz.

```html
<script src="myScript.js"></script>
<script src="myScript2.js"></script>
```

## External Referansları

Harici script dosyaları URL ile veya ilişkili bir dosya yolu ile belirtilebilir.

Aşağıdaki örnek tam bir URL adresi kullanmaktadır.

```html
<script src="https://www.w3schools.com/js/myScript1.js"></script>
```

Aşağıdaki örnek aynı web sitesinin farklı bir klasörünün altındaki dosyayı kullanmaktadır.

```html
<script src="/js/myScript1.js"></script>
```

Aşağıdaki örnek aynı web sitesinin aynı klasöründeki dosyayı kullanmaktadır.

```html
<script src="/js/myScript1.js"></script>
```

# JavaScript Çıktıları

## JavaScript'in Çıktı Alternatifleri

Javascript farklı yollardan verileri gösterebilir:

-   `innerHTML` kullanarak HTML elementinin içine yazmak
-   `document.write()` kullanarak HTML dökümanına yazmak
-   `window.alert()` kullanarak mesaj kutusu göstermek
-   `console.log()` kullanarak tarayıcının konsoluna yazmak

### innerHTML

JavaScript bir HTML elementine erişmek için `document.getElementById(id)` metodunu kullanır.

id özelliği HTML elementini temsil eder. innerHTML özelliği ise HTML elementinin içeriğini temsil eder.

```html
<!DOCTYPE html>
<html>
	<body>
		<h1>My First Web Page</h1>
		<p>My First Paragraph</p>

		<p id="demo"></p>

		<script>
			document.getElementById('demo').innerHTML = 5 + 6;
		</script>
	</body>
</html>
```

> Bir bilgiyi HTML'de göstermek için innerHTML özelliğini değiştirmek yaygın olarak kullanılan yöntemdir.

### document.write()

Test amacıyla kullanımı uygundur.

```html
<!DOCTYPE html>
<html>
	<body>
		<h1>My First Web Page</h1>
		<p>My first paragraph.</p>

		<script>
			document.write(5 + 6);
		</script>
	</body>
</html>
```

> Bir HTML dökümanı yüklendikten sonra `document.write()` methodunu kullanmak bütün HTML'i silecektir. Aşağıdaki örnekte bu durum mevcuttur.

```html
<!DOCTYPE html>
<html>
	<body>
		<h1>My First Web Page</h1>
		<p>My first paragraph.</p>

		<button type="button" onclick="document.write(5 + 6)">Try it</button>
	</body>
</html>
```

> Bu metot yalnızca test için kullanılıyor olmalıdır.

### window.alert()

Bilgiyi göstermek için mesaj kutusu kullanılması da mümkün.

````html
<!DOCTYPE html>
<html>
	<body>
		<h1>My First Web Page</h1>
		<p>My first paragraph.</p>

		<script>
			window.alert(5 + 6);
		</script>
	</body>
</html>
```
````

### console.log()

Alınacak çıktıları test etmek için ve debugging aşamasında sıkça kullanılan yöntem olarak tarayıcının konsoluna da bilgiyi yazdırabiliriz.

> İlerleyen kısımlarda debugging hakkında daha fazla bilgi sahibi olacağız.

```html
<!DOCTYPE html>
<html>
	<body>
		<script>
			console.log(5 + 6);
		</script>
	</body>
</html>
```

# JavaScript Statements

Statements örnekleri:

```javascript
var x, y, z; // Statement 1
x = 5; // Statement 2
y = 6; // Statement 3
z = x + y; // Statement 4
```

## JavaScript Programları

Aslında bir bilgisayar programı, bilgisayar tarafından çalıştırılacak talimatlar listesidir. Bir programlama dilinde bu programlama talimatları **statements** olarak ifade edilir.

> HTML'de JavaScript programları web tarayıcıları tarafından çalıştırılır.

## JavaScript Statements

JavaScript statementları şunlardan oluşur:
Değerler, operatörler, ifadeler, keywordler ve yorumlar.

Örnekteki statement tarayıcıya, id'si 'demo' değerine eşit olan HTML elementinin içine 'Merhaba' yazmasını söyler.

```js
document.getElementById('demo').innerHTML = 'Merhaba';
```

Çoğu JavaScript programı çokça JavaScript statementı içerir.
Statementlar da yazıldıkları sıra doğrultusunda tek tek, satır satır çalıştırılır.

## Noktalı Virgüller ;

Noktalı virgüller JavaScript statementlarını ayırır.

Her çalıştırılabilir statementın sonuna noktalı virgül ekleyebiliriz.

```js
var a, b, c; // 3 değişken oluştur
a = 5; // 5 değerini a değişkenine ata
b = 6; // 6 değerini b değişkenine ata
c = a + b; // a ve b değişkenlerinin toplamını c değişkenine ata
```

Ayrıca birden fazla statementta eğer noktalı virgüllerle ayrılırsa tek satırda bulunmaları mümkün.

```js
a = 5;b = 6;c = a + b;
```

> Araştırma yaparken bazı projelerde noktalı virgül kullanılmadığını görebilirsiniz. JavaScript dilinde noktalı virgül kullanımı zorunlu değil fakat herhangi sorun yaşanmaması için oldukça tavsiye edilmektedir.

## JavaScript Beyaz Alan (White-Space)

JavaScript birden fazla boşluğu (space karakterini) yok sayar. Scriptinize okunabilirliğini arttırmak için beyaz alanlar ekleyebilirsiniz. Aşağıda örnekteki iki satır da birbirine denktir.

```js
var person='Hege';
var person = 'Hege';
```
Operatörlerin arasına boşluklar eklemek de iyi olacaktır.
```js
var x = y + z; 
```
## JavaScript Satır Uzunlukları ve Satır Bitimleri
Okunabilirlik için programcılar çoğunlukla 80 karakterden uzun kod satırları yazmayı tercih etmezler.

Eğer bir JavaScript statementı tek satıra sığmıyor veya okunabilirliği bozuyor ise o satırı bir operatörden sonra bitirip yenisine geçebiliriz.
```js
document.getElementById("demo").innerHTML =
"Hello!"; 
```
## JavaScript Kod Blokları
JavaScript statementları kod bloklarında süslü parantezler { . . . } içerisinde birbirleriyle grup haline gelebilirler.

Kod bloklarının amacı birlikte çalışacak statementları gruplamaktır. Bu durumu fonksiyonlarda görebiliriz.
```js
function myFunction() {
  document.getElementById("demo1").innerHTML = "Hello!";
  document.getElementById("demo2").innerHTML = "How are you?";
}
```
> İlerleyen kısımlarda fonksiyonlar hakkında daha fazla bilgi sahibi olacağız.
## JavaScript Anahtar Kelimeler (Keywords)
JavaScript statementları yapılacak işin belirtilmesi için genellikle bir **keyword** ile başlar.

JavaScript'te tüm rezerve edilmiş keywordleri görüntülemek için [tıklayınız](https://www.w3schools.com/js/js_reserved.asp)
>JavaScript keywordleri rezerve edilmiş anahtar kelimelerdir. Bunlar değişken, fonksiyon vb. tanımlanırken kullanılamaz.
# JavaScript Sözdizimi (Syntax)
JavaScript syntaxı aslında kurallar dizisidir. JavaScript programlarının yapılandırılmasına dair tariftir de diyebiliriz.
```js
var x, y, z;       // Değişken nasıl tanımlanır
x = 5; y = 6;      // Değer nasıl atanır
z = x + y;         // Hesaplama nasıl yapılır
```
## JavaScript Değişkenleri (Variables)
Bir programlama dilinde değişken kavramı aslında içinde veri bulunan bir kutu gibidir.

JavaScript değişken tanımlamalarında `var` anahtar kelimesini kullanır.

`=` operatörü ile de tanımlanan değişkenlere, değer ataması yapılabilir.

Bu örnekte 'x' bir değişken olarak tanımlanmış ve içerisine 6 değeri atanmıştır.
```js
var x;
x = 6; 
```
## JavaScript Operatörleri
JavaScript hesaplama işlemleri için **aritmetik operatörleri ( +, -, \*, / )** kullanır.
```js
(5 + 6) * 10
```
JavaScript değer atama işlemleri için **atama operatörünü ( = )** kullanır.
```js
var x, y;
x = 5;
y = 6; 
```
## JavaScript Yorumları
Bütün JavaScript statementları çalıştırılabilir değildir.

// ifadelerinden sonrasına veya /* ve */ ifadeleri arasına yazılacak içerikler yorum satırı olacaktır.

Yorum satırları da yok sayılacak, çalıştırılmayacaktır.
```js
var x = 5; // Çalıştırılacak
// var x = 6; Çalıştırılmayacak
```
## JavaScript Tanımlayıcılar (Identifiers)
Tanımlıyıcılar aslında isimlerdir.

JavaScript'te tanımlayıcılar değişkenleri (ve anahtar kelimeleri, fonksiyonları) adlandırmak için kullanılır.

Geçerli isimlendirme için kurallar genelde çoğu programlama dilinde aynıdır.

JavaScript isimlendirmesinde ilk karakter muhakkak bir harf veya bir alt tire (_) veya bir dolar simgesi ($) olmalıdır. Sonraki karakterler yine harf, alt tire, dolar işareti ve rakamlardan oluşabilir.
>İlk karakter olarak rakam verilemez.
## JavaScript Küçük-Büyük Harf Duyarlıdır
Tüm JavaScript tanımlayıcıları küçük-büyük harflere duyarlıdır. Mesela `soyad` ve `soyAd` değişkenleri, birbirinden bağımsız iki değişkendir.
```js
var soyad, soyAd;
soyad = "John";
soyAd = "Doe";
```
Bir diğer örnek olarak JavaScript `var` anahtar kelimesini `Var`, `VAR` gibi şekillerde yazıldığı zaman anlayamaz ve yorumlayamaz.
## JavaScript Karakter Seti
JavaScript **Unicode** karakter setini kullanır.

**Unicode** global olarak tüm karakterleri, sembolleri ve noktalama işaretlerini barındırır. Detaylı bilgi için [göz atabilirsiniz](https://www.w3schools.com/charsets/ref_html_utf8.asp).
# JavaScript Yorumları
JavaScript yorumları JavaScript kodunu açıklamak ve okunur kılmak maksadıyla kullanılır.

Ayrıca sık olarak da mevcut kod satırlarının çalışmasını (test maksadıyla) engellemek için kullanılır.

## Tek Satır Yorumlar
Tek satır yorumlar `//` ile başlar.

`//` işaretleri ile bu işaretlerin konulduğu satırın sonuna kadar yazılacak şeyler JavaScript tarafından yok sayılır yani çalıştırılmaz.

Aşağıda her kod satırından önce kullanılarak örneklenmiştir.
```js
// baslik ID'sine sahip nesnenin içeriğini değiştirir:
document.getElementById("baslik").innerHTML = "Benim İlk Sayfam!";

// paragraf ID'sine sahip nesnenin içeriğini değiştirir:
document.getElementById("paragraf").innerHTML = "Benim ilk paragrafım.";
```
Aşağıdaki örneğimizde ise kod satırlarının bitiminde satıra dahil olarak kullanmıştır.
```js
var x = 5;      // x isminde değişken tanımla ve 5 değerini ata
var y = x + 2;  // y isminde değişken tanımla ve x değişkenini 2 ile toplayarak ortaya çıkan sonucu ata
```
## Çok Satır Yorumlar
Birden fazla satırda yorumlar için `/*` işaretleriyle başlanır ve `*/` işaretleri ile bitirilir. Bu iki işaretleme arasında bulunacak tüm yazılar yorum satırı olacaktır. Aşağıda örnek verilmiştir.
```js
/*
Aşağıdaki kod
ID'si baslik ve paragraf olan 
HTML elementlerinin içeriğini
benim web sayfamda değiştirecektir.
*/
document.getElementById("baslik").innerHTML = "Benim İlk Sayfam!";
document.getElementById("paragraf").innerHTML = "Benim ilk paragrafım.";
```
>Tek satır yorumlar sıkça kullanılmakla beraber çok satır yorumlara ise genelde resmi dökümantasyonlarda yer verilmektedir.
## Kodların Çalışmasını Önlemek İçin Yorumları Kullanmak
Bir ürünü veya programı henüz geliştirme aşamasındayken test maksatlı bazı kodları çalıştırmamız veya çalışmasını önlememiz gerekebilir. Eğer yorum satırları olmasaydı çalışmasını önlemek için tabii ki kodu silmemiz gerekecekti. Fakat çalışmasını istemediğimiz kodu test ve geliştirme aşamasındayken yorum satırı haline çevirirsek JavaScript onu yok sayacak ve çalıştırmayacaktır.

```js
//document.getElementById("baslik").innerHTML = "Benim İlk Sayfam!";
document.getElementById("paragraf").innerHTML = "Benim ilk paragrafım.";
```
Ayrıca çoklu yorum satırları ile de çokça kod bloğunun çalışmasını engellememiz mümkün.
```js
/*
document.getElementById("baslik").innerHTML = "Benim İlk Sayfam!";
document.getElementById("paragraf").innerHTML = "Benim ilk paragrafım.";
*/
```
# JavaScript Değişkenler (Variables)
Değişkenler aslında verileri barındıran, saklayan kutucuklardır.

Bu örneğimizde `x`, `y` ve `z` değişkendirler.
```js
var x = 5;
var y = 6;
var z = x + y;
```
Yukarıdaki örnekten şu yorumlar çıkartılabilir:
* x, 5 değerini barındırır.
* y, 6 değerini barındırır.
* z, 11 değerini barındırır.
## Adeta Cebir Gibi
Yine bu örnekte de `fiyat1`, `fiyat2` ve `toplam` değişkendirler.
```js
var fiyat1 = 5;
var fiyat2 = 6;
var toplam = fiyat1 + fiyat2;
```
Aynen cebirde olduğu gibi programlamada da değerleri ifade etmek için değişkenler (mesela fiyat1) kullanıyoruz.

Aynı şekilde bu değerler ile işlemler yaparak sonuçlara ulaşabiliyoruz

Yukarıdaki örnekten elde bulunan değişkenlerle hesaplama yaparak 11 sonucuna ulaşıldığı görülüyor.
## JavaScript Tanımlayıcılar (Identifiers)
Bütün JavaScript değişkenleri tekil isimlerle tanımlanmış olmalılardır.

Bu tekil isimler __tanımlayıcılar__ olarak isimlendirilir.

Tanımlayıcılar x, y gibi kısa isimler olabilmekle beraber yaş, toplam gibi açıklayıcı da olabilir.

Değişkenler (tekil tanımlayıcılar) için genel kurallar:
* İsim harfler, rakamlar, alt tireler ve dolar sembolleri içerebilir.
* İsim bir harfle başlamalıdır. Ayrıca dolar sembolü veya alt tire ile de başlayabilir (fakat bu dökümantasyonda bu şekilde kullanım yapılmayacaktır.)
* İsimler büyük-küçük harf duyarlıdır. (y ve Y farklı değişkenlerdir)
* Rezerve edilmiş kelimeler, anahtar kelimeler isim olarak kullanılamaz.

## JavaScript Veri Tipleri
JavaScript değişkenleri sayıları tutabileceği gibi metinleri de tutabilir.

JavaScript çokça tip veriyi tutabilir fakat şuan için sadece sayılar ve metinleri düşünelim.

Metinler tek tırnak veya çift tırnak içerisine yazılabilir. Sayılar ise herhangi bir tırnak içerisinde olmaksızın doğrudan yazılırlar. Eğer sayıları da tırnak içinde yazarsanız metin olarak kabul edileceklerdir.
```js
var pi = 3.14;
var person = "John Doe";
var answer = 'Yes I am!';
```

## JavaScript Değişkeni Oluşturma
`var` anahtar kelimesi ile JavaScript'te değişken tanımlamamız mümkün.
```js
var arabaAdi;
```
Bu şekilde tanımladıktan sonra değişken herhangi bir değere sahip olmayacaktır (teknik olarak `undefined` değerine sahip olacaktır.).

Tanımlanan değişkene değer atamak için eşittir (`=`) sembolünü kullanabiliriz.
```js
arabaAdi = "Volvo";
```
Aynı zamanda değişkeni tanımlama esnasında da değer atamamız mümkün:
```js
var arabaAdi = "Volvo";
```
Aşağıdaki örnekte `arabaAdi` ismiyle bir değişken oluşturduk ve içerisine "Volvo" değerini atadık.

Sonrasında bu değişkenin değerini çıktı almak için ID'si 'demo' olan bir HTML paragrafının içerisine yazdırdık.
```html
<p id="demo"></p>

<script>
var arabaAdi = "Volvo";
document.getElementById("demo").innerHTML = arabaAdi;
</script> 
```
## Bir Statement, Çokça Değişken
Bir statementta birden fazla değişken tanımlayabiliriz.

Statementa `var` ile başlayalım ve değişkenleri virgül ile ayıralım.
```js
 var person = "John Doe", carName = "Volvo", price = 200; 
```
Bu işlemi birden fazla satıra da ayırabiliriz.
```js
var person = "John Doe",
carName = "Volvo",
price = 200;
```
## Değişkenleri Tekrar Tanımlama
Eğer bir JavaScript değişkenini tekrar tanımlarsanız önceki değerini kaybetmeyecektir.

Aşağıdaki örnekte `arabaAdi` isimli değişken yine de "Volvo" değerine sahip olacaktır.
```js
var carName = "Volvo";
var carName;
```

## JavaScript Aritmetik
Cebirde olduğu gibi JavaScript'te de `=`, `+` gibi operatörlerle aritmetik işlemler yapabilirsiniz:
```js
var x = 5 + 2 + 3;
```
Ayrıca stringlere de uygulamamız mümkün. Bu durumda stringler birleşeceklerdir.
```js
var x = "John" + " " + "Doe"; 
```
Lütfen şunu da deneyin:
```js
var x = "5" + 2 + 3;
```
> Eğer tırnak içerisine sayı yerleştirirseniz metin gibi davranacaklar ve geri kalan değerlerle birleşeceklerdir.
Şimdi de şunu deneyin:
```js
var x = 2 + 3 + "5";
```