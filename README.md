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

# Introduction

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
 document.getElementById("demo").innerHTML = "Paragraph changed.";
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
* HTML ve JS kodlarının birbirine karışmasını önler.
* Okunabilirliği arttırır.
* Script dosyalarını re-usable yani tekrar kullanılabilir hale getirir, böylelikle birbirini tekrar eden kodlar da ortadan kalkmış olur.

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
* `innerHTML` kullanarak HTML elementinin içine yazmak
* `document.write()` kullanarak HTML dökümanına yazmak
* `window.alert()` kullanarak mesaj kutusu göstermek
* `console.log()` kullanarak tarayıcının konsoluna yazmak