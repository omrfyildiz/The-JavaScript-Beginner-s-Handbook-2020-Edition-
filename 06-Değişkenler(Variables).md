## Değişkenler

Değişken, bir tanımlayıcıya(identifier) atanmış değerdir(value). Yani referans edebilir ve daha sonra programda kullanabilirsiniz.

Bunun nedeni JavaScript'in **esnek yazım(loosely typed)** özelliğine sahip olmasıdır. Bunu ileride sıkça duyacaksınız.

Bir değişken(variable) kullanabilmeniz için önce onu belirtmeniz gerekir.

Değişkenleri belirtmenin iki esas yolu var. Birincisi `const` kullanmak.

```js
const a = 0
```

İkinci yolu ise `let`:

```js
let a = 0
```

Fark nedir?

`const` bir değeri referans alan sabiti(constant) tanımlar. Demek oluyor ki referans değiştirilemez. Buna yeni bir değer atayamazsınız.

`let` kullanımı sizin yeni bir değer atamanıza izin verir.

Örneğin şunu yapamazsınız:

```js
const a = 0
a = 1
```

Çünkü bunu yapmaya çalıştığınızda şu hatayı alacaksınız: `TypeError: Assignment to constant variable.`.

Öte yandan `let` kullanarak bunu yapabilirsiniz:

```js
let a = 0
a = 1
```

`const` C gibi diğer dillerdeki "sabit(constant)" anlamına gelmez. Değerin değiştirilemezliği anlamına gelmez, yeniden bir değer atanamayacağı anlamına gelir. Eğer değişken, bir nesneyi ya da diziyi gösteriyorsa, bu nesnenin ve dizinin içeriği dilediğiniz gibi değişebilir(Dizileri ve nesneleri ileride göreceğiz).

`const` değişkenleri atama yapıldığı anda bir değer edinmeli:

```js
const a = 0
```

fakat `let` değerleri sonra da edindirilebilir:

```js
let a
a = 0
```

Bir durumda(statement) aynı anda birden fazla değişken belirtilebilir: 

```js
const a = 1, b = 2
let c = 1, d = 2
```

Fakat aynı değişkeni birden fazla kez belirtemezsiniz:

```js
let a = 1
let a = 2
```

ya da "Birden fazla belirtim(duplicate declaration)" hatası alırsınız. 

Benim size tavsiyem her zaman `const` kullanmanız. `let` sadece bir değişkene yeniden değer atama ihtiyacınız olacağını bildiğiniz zaman kullanılmalı. Neden mi? Çünkü kodumuzun iktidarı ne kadar az olursa o kadar iyi. Bir değerin yeniden atanamadığını bilirsek buglar için de o kadar az kaynak anlamına gelir.

Şimdiye kadar `const` ve `let` ile nasıl çalışılacağını gördük. Sizlere `var` hakkında bir şeyler bahsetmek istiyorum.

2015'e kadar `var` JavaScript'te bir deişken tanımlamanın tek yoluydu. Bugün ise modern kod tabanları daha çok sadece `const` ve `let` kullanmaktalar. Şu [linkte]((https://flaviocopes.com/javascript-difference-let-var/)) bazı temel farklılıklarını anlattım ama yeni başlayanlardansanız bunu şimdilik çok dikkate almayabilirsiniz. Sadece `const` ve `let` kullanın.