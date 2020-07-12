## Karşılaştırma İşlemleri(Comparison operators)

Atama ve matematik işlemlerinden sonra, üçüncü işlemler seti olarak size karşılaştırma operatörlerini tanıtmak istiyorum.

Şimdi göreceğimiz işlemleri iki sayıyı ya da stringi karşılaştırırken kullanabilirsiniz.

Karşılaştırma işlemleri her zaman `true` ya da `false` bir boolean döndürür.

Şunlar **eşitsizlik karşılaştırma işlemleri**:

- `<` "küçüktür" anlamına gelir
- `<=` "küçük eşittir" anlamına gelir
- `>` "büyüktür" anlamına gelir
- `>=` "büyük eşittir" anlamına gelir

Örnek:

```js
let a = 2
a >= 1 //true
```

Bunlara ek olarak, dört tane **eşitlik işlemi** vardır. İki değer alır ve boolean döner:

- `===` eşitlik durumunu kontrol eder
- `!==` eşitsizlik durumunu kontrol eder

Unutmayın ki JavaScript'te bir de `==` ve `!=` vardır. Fakat benim size önerim sadece `===` ve `!==` kullanmanız, çünkü bu sayede bazı küçük problemlerin önüne geçebilirsiniz.