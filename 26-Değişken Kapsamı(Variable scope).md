## Değişken Kapsamı(Variable scope)

Değişkenlerden(variables) ilk defa bahsederken `const`, `let` ve `var` kullanımları hakkında konuşmuştum.

Scope(kapsam) programın bir kısmı için görünür olan değişkenler setidir.

JavaScript'te global scope, block scope ve function scope vardır.

Bir değişken fonksiyon ya da blok dışında tanımlanırsa, bu, global object(nesne)'e eklenir ve global scope'a sahip olur. Bunun manası da programın her kısmında erişilebilir demektir.

`var`, `let` ve `const` deklarasyonları arasında çok önemli bir fark vardır.

Bir değişken, fonksiyonun içinde `var` olarak tanımlandığında, bir fonksiyonun argümanlarına benzer şekilde, sadece fonksiyonun içinde görünebilir demektir.

Öte yandan bir değişken `const` ya da `let` olarak tanımlandığında sadece tanımlandığı **blok** içinde görünebilir.

Blok bir çift süslü parantez içinde gruplandırılmış talimatlar setidir. Tıpkı bir `if` statement'ı, bir `for` döngüsü ya da bir fonksiyon gibi.

Anlamamız gereken şey bir blok `var` için yeni bir scope tanımlamaz, fakat `let` ve `const` için tanımlar.

Bu birçok pratik uygulamaya sahiptir.

Bir fonksiyonda `if` koşulu içinde `var` değişkeni tanımladığınızı varsayın

```js
function getData() {
  if (true) {
    var data = 'some data'
    console.log(data) 
  }
}
```

Bu fonksiyonu çağırdığınızda, konsolda `some data` yazıldığını göreceksiniz.

`if`'ten sonra console.log(data)'yı kaldırmaya denerseniz, halen çalıştığını göreceksiniz:

```js
function getData() {
  if (true) {
    var data = 'some data'
  }
  console.log(data) 
}
```

Fakat `var data`'yı `let data`'yla değiştirirseniz:

```js
function getData() {
  if (true) {
    let data = 'some data'
  }
  console.log(data) 
}
```

Bir hata alacaksınız: `ReferenceError: data is not defined`.

Bunun nedeni `var`'ın fonskyon scoped olması ve burada meydana gelen hoisting(yukarı çekme) diye adlandırılan özel bir şey olması. Kısaca, `var` deklasrasyonu, JavaScript tarafından kodu çalıştırmadan önce en yakın fonksiyonun üstüne taşınır. Bu, az ya da çok, özünde JavaScript'te fonksiyonun neye benzediğidir:

```js
function getData() {
  var data
  if (true) {
    data = 'some data'
  }
  console.log(data) 
}
```

İşte bu yüzden `console.log(data)` 'yı fonksiyonun en üst kısmında, hatta deklare edilmeden önce bile bulundurabilirsiniz ve bu değişken için değer olarak `undefined` alacaksınızdır.

```js
function getData() {
  console.log(data) 
  if (true) {
    var data = 'some data'
  }
}
```

fakat `let`'e geçiş yaparsanız `ReferenceError: data is not defined` hatası alacaksınız, çünkü hoisting(yukarı çekme) `let` deklarasyonlarında meydana gelmez.  

`const` da `let` gibi aynı kurala tabidir: Blok scoped değildir.

İlk başlarda biraz kafa karıştırıcı gelebilir ama bir kere bu farkı anlarsanız, neden bugünlerde `var`'ın `let`'e nazaran bad practice(kötü uygulama) olarak kabul edildiğini göreceksiniz. Daha az hareketli parçaya sahiptirler ve scopeları(kapsamları) blokla sınırlıdır, bu da onları döngü değişkenleri olarak çok iyi yapar, çünkü bir döngü sona erdikten sonra varlıklarını sürdürmezler:

```js
function doLoop() {
  for (var i = 0; i < 10; i++) {
    console.log(i)
  }
  console.log(i)
}

doLoop()
```

Döngüden çıktığınız zaman, `i`, 10 değeriyle birlikte geçerli bir değişken olacaktır.

`let`'e geçiş yaparsanız, `console.log(i)` denemeye çalıştığınızda `ReferenceError: i is not defined` diye bir hata sonucu verecektir.