## Döngüler(Loops)

Döngüler JavaScript'in ana kontrol yapılarından biridir.

Bir döngü ile birlikte bir kod blokunu, kaç kere çalıştırmak istiyorsak isteyelim, otomatize edebilir ve tekrarlatabiliriz.

JavaScript döngüler aracılığıyla yinelemenin birçok yoluna sahiptir.

Ben sadece üç tanesine odaklanacağım:

- while loops(while döngüleri)
- for loops(for döngüleri)
- for..of loops(for..of döngüleri)

### `while`

while döngüsü JavaScript'in bize sağladığı en basit döngü yapısıdır.

`while` anahtar kelimesinden sonra koşul ekleriz ve koşul `true` değer dönene kadar çalışacak bir kod bloku oluşturmuş oluruz.

Örnek:

```js
const list = ['a', 'b', 'c']
let i = 0
while (i < list.length) {
  console.log(list[i]) //value
  console.log(i) //index
  i = i + 1
}
```

`while` döngüsünü `break` anahtar kelimesi ile durdurabilirsiniz:

```js
while (true) {
  if (somethingIsTrue) break
}
```

ve eğer bir döngünün ortasında mevcut yinelemeyi es geçip bir diğer yinelemeye `continue` kullanarak atlayabilirsiniz:

```js
while (true) {
  if (somethingIsTrue) continue

  //do something else
}
```

`while` kullanımına çok benzeyen `do..while` döngüleri de vardır. Temel olarak `while` ile aynı olsa da koşul, kod bloku işlemini tamamladıktan *sonra* değerlendirilir.

Bu, şu anlama gelir: kod bloku her zaman *en azından bir kere* işleme alınır.

Example:

```js
const list = ['a', 'b', 'c']
let i = 0
do {
  console.log(list[i]) //value
  console.log(i) //index
  i = i + 1
} while (i < list.length)
```

### `for`

JavaScript'te ikinci en önemli döngü yapısı ise **for döngüsüdür**

`for` anahtar kelimesini kullanarak üçlü bir seti geçeriz: başlatma, koşul ve artış kısmı.

Örnek:

```js
const list = ['a', 'b', 'c']

for (let i = 0; i < list.length; i++) {
  console.log(list[i]) //value
  console.log(i) //index
}
```

Tıpkı `while` döngülerinde olduğu gibi, bir `for` döngüsünü de `break` kullanarak durdurabilirsiniz. Ve yine aynı şekilde bir diğer `for` döngüsü yinelemesine `continue` kullanarak hızlıca geçebilirsiniz.

### `for...of`

Bu döngü diğerlerine nazaran daha yeni sayılır(2015'te tanıtıldı) ve `for` döngüsünün basitleştirilmiş bir versiyonu sayılır:

```js
const list = ['a', 'b', 'c']

for (const value of list) {
  console.log(value) //value
}
```