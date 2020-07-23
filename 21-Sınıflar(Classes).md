## Sınıflar(Classes)

JavaScript'in en ilgi çekici kısımlarından biri olan nesneler hakkında konuştuk.

Bu bölümde sınıfları bir adım ileri giderek göreceğiz.

Sınıflar nedir? Birden çok nesne için ortak bir desen(pattern) tanımlamanın bir yoludur.

Bir şahıs nesnesini ele alalım:

```js
const person = {
  name: 'Flavio'
}
```

`name` özelliği olan `Person` isimli bir sınıf(Büyük harf `P` sınıfları kullanmanın geleneksel yoludur) yaratabiliriz:

```js
class Person {
  name
}
```

Şimdi bu sınıftan `flavio` nesnesi türetebiliriz:

```js
const flavio = new Person()
```

`flavio` Person sınıfının *örneği(instance)* olarak adlandırılır.

`name` özelliğinin(property) değerini set edebiliriz

```js
flavio.name = 'Flavio'
```

ve şöyle kullanarak buna ulaşabilirsiniz

```js
flavio.name
```

tıpkı diğer nesne özellikleri için yaptığımız gibi.

Sınıflar `name` gibi özellikler ve ayrıca metodlar tutabilir.

Metodlar şu yolla tanımlanır:

```js
class Person {
  hello() {
    return 'Hello, I am Flavio'
  }
}
```

ve metodları bir sınıfın örneği üzerinden çağırabiliriz:  
and we can invoke methods on an instance of the class:

```js
class Person {
  hello() {
    return 'Hello, I am Flavio'
  }
}
const flavio = new Person()
flavio.hello()
```

Yeni bir nesne örneği yarattığımız zaman sınıf özelliklerini tetiklemek için kullanabileceğimiz özel bir metod olarak adlandırılan `constructor()` diye bir metod vardır.

Şu şekilde çalışır:

```js
class Person {
  constructor(name) {
    this.name = name
  }

  hello() {
    return 'Hello, I am ' + this.name + '.'
  }
}
```

Nesne örneğine(object instance) erişmek için `this`'i nasıl kullandığımızı not edin.

Şimdi bir string içinde yer vererek sınıftan yeni bir nesne örneklendirebiliriz(instantiate). Ve `hello` diye çağırdığımızda kişiselleştirilmiş bir mesaj alacağız:

```js
const flavio = new Person('flavio')
flavio.hello() //'Hello, I am flavio.'
```

Nesne tetiklendiği zaman `constructor` metod, yer verilen parametrelerle çağrılır.

Normalde metodlar, sınıflarda değil; nesne örneğinde(object instance) tanımlanırlar.

Bunun yerine sınıfta yürütülmesine izin vermek için bir metodu `statik` olarak tanımlayabilirsiniz:

```js
class Person {
  static genericHello() {
    return 'Hello'
  }
}

Person.genericHello() //Hello
```

Zaman zaman çok yararlıdır bu yol.