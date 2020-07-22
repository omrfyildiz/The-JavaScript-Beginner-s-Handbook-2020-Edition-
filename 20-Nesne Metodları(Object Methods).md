## Nesne Metodları(Object Methods)

Daha önceki bölümlerden birinde fonksiyonlardan bahsetmiştim.

Fonksiyonlar bir fonksiyon özelliğine(function property) atanabilir. Bu duruma **metod** denir.

Bu örnekte `start` özelliği atanmış bir fonksiyona sahiptir ve biz bunu özellikler için kullandığımız nokta sentaksını sonunda parantezlerle birlikte kullanarak çağırabiliriz:

```js
const car = {
  brand: 'Ford',
  model: 'Fiesta',
  start: function() {
    console.log('Started')
  }
}

car.start()
```

`function() {}` sentaksı kullanılarak tanımlanan bir metodun içinde `this` tarafından referans vererek nesnenin bir örneğine(instance) erişiriz.

Aşağıdaki örnekte `brand` ve `model` özelliklerinin değerlerine `this.brand` ve `this.model` kullanarak erişiriz:

```js
const car = {
  brand: 'Ford',
  model: 'Fiesta',
  start: function() {
    console.log(`Started 
      ${this.brand} ${this.model}`)
  }
}

car.start()
```

Normal fonksiyonlarla arrow fonksiyonlar arasındaki ayrımın akılda tutulması önemlidir: Arrow fonksiyon kullanıyorsak `this` erişimimiz olmaz:

```js
const car = {
  brand: 'Ford',
  model: 'Fiesta',
  start: () => {
    console.log(`Started 
      ${this.brand} ${this.model}`) //çalışmayacaktır
  }
}

car.start()
```

Bunun nedeni **arrow fonksiyonların objeye bağlı olmamasıdır**.

İşte bu yüzden normal fonksiyonlar sıklıkla kullanılan nesne metodlarıdır.

Metodlar, tıpkı fonksiyonlar gibi, parametre alabilirler:

```js
const car = {
  brand: 'Ford',
  model: 'Fiesta',
  goTo: function(destination) {
    console.log(`Going to ${destination}`)
  }
}

car.goTo('Rome')
```