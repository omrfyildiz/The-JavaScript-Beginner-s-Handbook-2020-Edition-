## Arrow(Ok) Fonksiyonlar(Arrow functions)

Arrow fonksiyonlar JavaScript'e son dönemde girmiştir.

Bir önceki bölümde açıkladığım "normal" fonksiyonların yerine sıkça kullanılırlar. İki formatı da birçok yerde görecekiniz.

Görsel olarak daha kısa sentakslı fonksiyon yazmanıza izin verir. Şu formattan:

```js
function getData() {
  //...
}
```

...şu formata:

```js
() => {
  //...
}
```

Fakat dikkat edin, burada bir isim bulunmuyor.

Arrow fonksiyonlar anonimdirler. Onlara bir değişken atamamız gerekir.

Normal bir fonksiyona şu şekilde değişken atarız:

```js
let getData = function getData() {
  //...
}
```

Bunu yaparken fonksiyondan adı kaldırırız:

```js
let getData = function() {
  //...
}
```

ve değişkenin adını kullanarak fonksiyonu çağırırız:

```js
let getData = function() {
  //...
}
getData()
```

Arrow fonksiyonlarla yaptığımız şey de aynıdır:

```js
let getData = () => {
  //...
}
getData()
```

Eğer fonksiyon kalıbı sadece tekil bir statement içeriyorsa parantezleri yok sayabilir ve her şeyi tek bir satırda yazabilirsiniz:

```js
const getData = () => console.log('hi!')
```

Parametreler parantez içinde ifade edilir:

```js
const getData = (param1, param2) => 
  console.log(param1, param2)
```

Sadece bir parametreniz varsa parantezleri tamamen yok sayabilirsiniz:

```js
const getData = param => console.log(param)
```

Arrow fonksiyonlar size örtülü dönüş(implicit return) imkanı verir. Bu değerler `return` anahtar kelimesi kullanmaya gerek olmadan dönen değerlerdir.

Bu, fonksiyon kalıbında tek satırlı bir statement(ifade) olduğunda çalışır:

```js
const getData = () => 'test'

getData() //'test'
```

Normal fonksiyonlar gibi, çağrılmadıkları durumda, parametreler için varsayılan değerler alabiliriz:

```js
const getData = (color = 'black', 
                 age = 2) => {
  //do something
}
```
Ve normal fonksiyonlar gibi sadece bir değer döndürebiliriz.

Arrow fonksiyonlar ayrıca başka arrow fonksiyonlar içerebilir; hatta normal fonksiyonlar bile içerebilir.

İki tür fonksiyon da birbirine çok benzerler. O halde neden arrow fonksiyonlara ihtiyaç var diye sorabilirsiniz. Normal fonksiyonlarla arasındaki en önemli fark object(nesne) metod olarak kullanıldığında görülür. Bunun ne demek olduğunu ilerleyen bölümlerde göreceğiz.