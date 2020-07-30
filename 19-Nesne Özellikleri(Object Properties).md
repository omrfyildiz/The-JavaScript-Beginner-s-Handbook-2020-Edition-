## Nesne Özellikleri(Object Properties)

Nesnelerin **özellikleri(properties)** vardır. Bunlar bir değerle ilişkilendirilmiş künyeden(label) meydana gelir.

Propertynin değeri herhangi bir türde olabilir: Dizi, fonksiyon ve hatta diğer nesneleri barındıran nesneler. 

Bu kullanım, önceki bölümde gördüğümüz nesne yazım sentaksı:

```js
const car = {

}
```

`color` diye bir property(özellik) tanımlıyoruz:

```js
const car = {
  color: 'blue'
}
```

Şimdi `color` özelliği ile adlandırılmış ve bu özelliği `blue` olarak değer alan `car` diye bir nesnemiz var.

Künyeler(labels) bir string olabilir, fakat özel karakterlere dikkat edin. Özelliğin adında değişken adı olarak geçerli olmayan bir karakter eklemek isteseydim, bunun etrafında tırnak işareti kullanmak zorunda kalırdım:

```js
const car = {
  color: 'blue',
  'the color': 'blue'
}
```

Geçerli olmayan değişken ismi karakterleri boşluklar, tire ve diğer özel karakterlerdir.

Gördüğünüz üzere, çoklu özellikler olduğunda her bir özelliği virgül işareti ile ayırıyoruz.

Propertynin(özelliğin) değerini iki farklı sentaks kullanımıyla alabiliriz.

İlk olarak **nokta notasyonu(dot notation)**:

```js
car.color //'blue'
```

İkincisi(geçerli olmayan isimli propertylerde(özelliklerde) kullanabileceğimiz tek yol) ise köşeli parantezlerdir:

```js
car['the color'] //'blue'
```

Var olmayan bir özelliğe erişirseniz `undefined` değerini alacaksınız:

```js
car.brand //undefined
```

Daha önce de bahsedildiği gibi nesneler başka nesnelerin içinde property(özellik) olarak bulunabilirler:

```js
const car = {
  brand: {
    name: 'Ford'
  },
  color: 'blue'
}
```

Bu örnekte brand name'e şöyle erişirsiniz:

```js
car.brand.name
```

ya da

```js
car['brand']['name']
```

Bir nesne tanımladığınız zaman özellik(property) değerini ayarlayabilirsiniz.

Fakat daha sonra bunu güncelleyebilirsiniz:

```js
const car = {
  color: 'blue'
}

car.color = 'yellow'
car['color'] = 'red'
```

Ve bir nesneye yeni özellikler ekleyebilirsiniz:

```js
car.model = 'Fiesta'

car.model //'Fiesta'
```

Verilen nesne

```js
const car = {
  color: 'blue',
  brand: 'Ford'
}
```

bundan bir özellik silebilmek için kullanmanız gereken

```js
delete car.brand
```