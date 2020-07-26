## İşlemler(Operators)

İşlemler, sizin iki basit ifadeyi alıp daha kompleks bir formda bir araya getirmenizi sağlar.

İşlemleri operandlar(işlenenler) üzerine kurarız. Bazı işlemler(operatörler) tek bir işlenenle(operand) ile çalışırken çoğu iki tane ile çalışır. Üç tane ile çalışan sadece bir tane vardır.

İlkin işlemleri tanıtırken çoğunuzun aşina olanı ile başlayacağız: İki işlenenli işlemler.

Değişkenlerden(variables) bahsederken birine değindik zaten: Atama işlemi(assignment operator) `=`. Bunu bir değişkene değer atarken kullanırız:

```js
let b = 2
```

Şimdi de temel matematikten aşina olduğunuz diğer işlemlere bakalım:  

### Toplama Operatörü(The addition operator) (+)

```js
const three = 1 + 2
const four = three + 1
```

`+` işlemi aynı zamanda string kullanımında birleştirme işlemi görür. Örneğe dikkat edin:

```js
const three = 1 + 2
three + 1 // 4
'three' + 1 // three1
```

### Çıkarma İşlemi(The subtraction operator) (-)

```js
const two = 4 - 2
```

### Bölme İşlemi(The division operator) (/)

Birinci ve ikinci işlemlerden dönen bölümler:

```js
const result = 20 / 5 //result === 4
const result = 20 / 7 //result === 2.857142857142857
```

Sıfır(0) ile bölme yaptığınızda, JavaScript bir hata vermez, fakat `Infinity` value (ya da değer negatifse `-Infinity`) döndürür.

```js
1 / 0 //Infinity
-1 / 0 //-Infinity
```

### Yüzde İşlemi(The remainder operator) (%)

Yüzde işlemi birçok durum için oldukça kullanışlıdır:

```js
const result = 20 % 5 //result === 0
const result = 20 % 7 //result === 6
```
Bir değerin yüzde 0'ını işleme almaya çalıştığınızda her zaman `NaN` "Not a Number" özel değerini alırsınız:

```js
1 % 0 //NaN
-1 % 0 //NaN
```

### Çarpma İşlemi(The multiplication operator) (*)

İki sayının çarpımını verir:

```js
1 * 2 //2
-1 * 2 //-2
```

### Üs Alma İşlemi(The exponentiation operator) (**)

İlk değerin ikinci değer cinsinden üssünü verir:

```js
1 ** 2 //1
2 ** 1 //2
2 ** 2 //4
2 ** 8 //256
8 ** 2 //64
```