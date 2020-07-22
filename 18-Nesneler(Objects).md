## Nesneler(Objects)

Primitif tür(primitive type) (string, number, boolean, symbol, null, undefined) olmayan herhangi bir değer **object** olarak geçer.

Bir object(nesne) nasıl tanımlanır bakalım:

```js
const car = {

}
```

Buna **object literal(nesne yazım)** sentaksı denir. JavaScript'teki en hoş şeylerden biridir.

Ayrıca `new Object` sentaksını da kullanabilirsiniz:

```js
const car = new Object()
```

Bir diğer kullanım sentaksı ise `Object.Create()`: 

```js
const car = Object.create()
```

Bir nesneyi büyük harfle başlayan bir fonksiyondan önce `new` anahtar sözcüğü kullanarak da başlatabilirsiniz. Bu fonksiyon, nesne için constructor olarak hizmet edecektir. Bu yolla, nesnenin başlangıç durumunu ayarlamak için parametre olarak aldığımız argümanları başlatabiliriz:    

```js
function Car(brand, model) {
  this.brand = brand
  this.model = model
}
```

Yeni bir nesneyi şunları kullanarak başlatırız:

```js
const myCar = new Car('Ford', 'Fiesta')
myCar.brand //'Ford'
myCar.model //'Fiesta'
```

Nesneler **her zaman referans olarak iletilir.**

Bir değişkeni aynı değerde bir başkasına atarsanız, number veya string gibi primitif türse(primitive type), değere göre iletilir:

Şu örneğe bakın:

```js
let age = 36
let myAge = age
myAge = 37
age //36
const car = {
  color: 'blue'
}
const anotherCar = car
anotherCar.color = 'yellow'
car.color //'yellow'
```

Diziler ve fonksiyonlar bile şapka altında nesnedirler. O halde nasıl çalıştıklarını anlamak çok önemli.