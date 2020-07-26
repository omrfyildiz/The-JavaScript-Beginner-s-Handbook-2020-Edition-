## Diziler(Arrays)

Bir dizi birçok öğenin bir arada olmasını ifade eder.

JavaScript'teki diziler kendi başlarına bir *type(tür)* değildir.

Diziler **objects(nesne)**dir.

Boş bir diziyi iki farklı yolla başlatabiliriz:

```js
const a = []
const a = Array()
```

İlk kullanım **array literal syntax(dizi yazım sentaksı)**. İkinci kullanım ise 'Array built-in function(dahili fonksiyonlu dizi)'.

Bu sentaksı kullanarak diziyi önceden doldurabilirsiniz:

```js
const a = [1, 2, 3]
const a = Array.of(1, 2, 3)
```

Bir dizi farklı türlerde de olsa herhangi bir değeri bir arada tutabilir:

```js
const a = [1, 'Flavio', ['a', 'b']]
```

Bir dizinin içine birden fazla dizi eklenebildiğinden, çok kullanışlı uygulamaları olan çok boyutlu diziler yaratabiliyoruz (a matrix gibi):

```js
const matrix = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9]
]

matrix[0][0] //1
matrix[2][0] //7
```

Bir dizinin herhangi bir öğesine sıfırdan başlayan indeks numarasını referans vererek ulaşabilirsiniz:

```js
a[0] //1
a[1] //2
a[2] //3
```

İlk olarak 12 öğeden oluşan bir diziyi başlatan ve her öğeyi `0` sayısıyla dolduran bu sentaksı kullanarak bir değer setiyle yeni bir dizi başlatabilirsiniz:

```js
Array(12).fill(0)
```

Dizideki öğelerin adetini `length` özelliğini kullanarak edinebilirsiniz:

```js
const a = [1, 2, 3]
a.length //3
```

Dizinin uzunluğunu ayarlayabileceğinizi unutmayın. Dizinin boyutundan yüksek bir değer verdiğinizde ise bir şey değişmeyecektir. Daha küçük bir değer verdiğinizde, dizi, o sayıda duracaktır.

```js
const a = [1, 2, 3]
a //[ 1, 2, 3 ]
a.length = 2
a //[ 1, 2 ]
```

### Bir diziye öğe nasıl eklenir 

Dizinin sonuna `push()` metodu ile yeni öğe ekleyebiliriz:

```js
a.push(4)
```

Dizinin başlangıcına öğe ekleyebilmek için `unshift()` metodunu kullanırız:

```js
a.unshift(0)
a.unshift(-2, -1)
```

### Bir öğe diziden nasıl kaldırılır:

Bir dizinin sonundan öğe kaldırabilmek için `pop()` metodunu kullanırız:

```js
a.pop()
```

Bir dizinin başlangıcından öğe kaldırabilmek için `shift()` metodunu kullanırız:

```js
a.shift()
```

### İki ya da daha fazla diziyi birleştirme

Birden fazla diziyi `concat()` kullanarak birleştirebilriz:

```js
const a = [1, 2]
const b = [3, 4]
const c = a.concat(b) //[1,2,3,4]
a //[1,2]
b //[3,4]
```

**spread** işlemini (`...`) kullanarak da bu işlemi yapabilirsiniz:

```js
const a = [1, 2]
const b = [3, 4]
const c = [...a, ...b]
c //[1,2,3,4]
```

### Dizi içerisinde belirli bir öğeyi bulmak

`find()` metodunu kullanarak bir dizideki öğeyi bulabilirsiniz:

```js
a.find((element, index, array) => {
  //return true or false
})
```

True değerini döndüren ilk değer döner ve eğer öğe bulunmazsa `undefined` döner.

Genellikle kullanılan sentaks şudur: 

```js
a.find(x => x.id === my_id)
```

Yukarıdaki kod satırı, dizedeki `id === my_id` öğesine sahip olan ilk elementi döndürür.

`findIndex()` çalışma biçimi `find()` ile benzerdir, fakat true değer dönen ilk öğenin indeksini verir. Eğer bulunmazsa `undefined` olarak döner:

```js
a.findIndex((element, index, array) => {
  //return true or false
})
```

Bir diğer metod `includes()`:

```js
a.includes(value)
```

True değer döner eğer `a` bir `value(dğer)` içeriyorsa.

```js
a.includes(value, i)
```

True değer döner eğer `a` `i` konumundan sonra bir `value(değer)` içeriyorsa.