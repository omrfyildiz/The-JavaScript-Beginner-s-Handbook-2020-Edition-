## Öncelik Kuralları(Precedence rules)

Her aynı satırdaki birden fazla işlem, öncelik problemleri ile karşılaşmamıza neden olur. 

Şu örneğe bakalım:

```js
let a = 1 * 2 + 5 / 2 % 2
```

Sonuç 2.5, peki neden?

İlk işleme alınması gerekenler nedir ve hangisi neden beklemek durumundadır?

Bazı işlemler diğerlerine göre önceliğe sahiptir. Öncelik kuralları şu tabloda sıralanmıştır:

| OPERATOR    | DESCRIPTION             |
| :---------- | :---------------------- |
| `*` `/` `%` | multiplication/division |
| `+` `-`     | addition/subtraction    |
| `=`         | assignment              |

Aynı düzeydeki işlemler(`+` ve `-` gibi) olduğu gibi işleme konur, soldan sağa.

Bu kuralları takip ederek yukarıdaki örneği şu şekilde çözeriz:

```js
let a = 1 * 2 + 5 / 2 % 2
let a = 2 + 5 / 2 % 2
let a = 2 + 2.5 % 2
let a = 2 + 0.5
let a = 2.5
```