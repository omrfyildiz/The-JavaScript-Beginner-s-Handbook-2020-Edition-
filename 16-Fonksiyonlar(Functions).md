## Fonksiyonlar(Functions)

Az çok kompleks her JavaScript programında her şey fonksiyonlar içinde olup biter.

JavaScript'in temel parçası olarak fonksiyonlar bir çekirdektir.

Fonksiyon Nedir?

Bir fonksiyon müstakil bir kod blokudur.

İşte bir **fonksiyon deklarasyonu**:

```js
function getData() {
  // do something
}
```

Bir fonksiyonu çağırarak onu istediğiniz zaman çalıştırabilirsiniz. 
Şöyle:

```js
getData()
```

Bir fonksiyon bir ya da daha fazla argümana sahip olabilir:

```js
function getData() {
  //do something
}

function getData(color) {
  //do something
}

function getData(color, age) {
  //do something
}
```

Bir argümanı iletebildiğimizde, parametreleri iletilen fonksiyonu çağırırız:

```js
function getData(color, age) {
  //do something
}

getData('green', 24)
getData('black')
```

Unutmayın, ikinci çağrıda `black` string parametresini `color` argümanını `age` olmadan geçirdim. Dolayısıyla fonksiyondaki `age` ise `undefined` yani tanımlanmamış olur.

Şu koşulu kullanarak bir değerin undefined olup olmadığını kontrol edebiliriz:

```js
function getData(color, age) {
  //do something
  if (typeof age !== 'undefined') {
    //...
  }
}
```

`typeof` unary(tekli) bir işlemdir, değişkenin türünü kontrol etmemize olanak tanır.

Ayrıca şu şekilde de kontrol edebilirsiniz:

```js
function getData(color, age) {
  //do something
  if (age) {
    //...
  }
}
```

Eğer `age` `null`, `0` ya da boş bir string ise, koşul her halükarda true olacaktır.

Çağrılma durumları olmasa bile parametreler için varsayılan değerler(default values) verebilirsiniz:

```js
function getData(color = 'black', age = 25) {
  //do something
}
```

Parametre olarak herhangi bir değer çağırabilirsiniz: numbers(sayılar), stringler, boolean değerler, array(dizi), objects(nesneler) ve ayrıca fonksiyonlar.

Bir fonksiyon dönüş değerine(return value) sahiptir. Varsayılan olarak, bir değerle birlikte `return`  anahtar kelimesini kullanmadığınız sürece, bir fonksiyon `undefined` döner:

```js
function getData() {
  // do something
  return 'hi!'
}
```

Fonksiyonu çağırdığımızda, bu dönüş değerini bir değişkene atayabiliriz:

```js
function getData() {
  // do something
  return 'hi!'
}

let result = getData()
```

`result` artık `hi!` değerinde bir string tutmaktadır.

Yalnız bir tane değer döndürebilirsiniz.

Çoklu değer dönmesi için bir nesne ya da dizi döndürebilirsiniz. Şu şekilde:  

```js
function getData() {
  return ['Flavio', 37]
}

let [name, age] = getData()
```

Fonksiyonlar, başka fonksiyonlar içerisinde tanımlanabilir:

```js
const getData = () => {
  const dosomething = () => {}
  dosomething()
  return 'test'
}
```

İçerideki fonksiyon, dahil olduğu fonksiyonun dışından çağrılamaz.

Ayrıca bir fonksiyondan başka bir fonksiyon döndürebilirsiniz.