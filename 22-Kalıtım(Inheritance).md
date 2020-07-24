## Kalıtım(Inheritance)

Bir sınıf başka bir sınıfı **genişletebilir(extend)** ve bu sınıf kullanılarak başlatılan nesneler her iki sınıfın tüm metodlarını devralır.

`Person` adlı bir sınıfımız olduğunu varsayalım:

```js
class Person {
  hello() {
    return 'Hello, I am a Person'
  }
}
```

`Person` sınıfını genişleten(extend eden) `Programmer` diye yeni bir sınıf tanımlayalım:

```js
class Programmer extends Person {

}
```

Şimdi ``Programmer` sınıfından yeni bir nesne türetirsek `hello()` metoduna erişimi olacaktır:

```js
const flavio = new Programmer()
flavio.hello() //'Hello, I am a Person'
```

Child class(alt sınıf)'ın içinde `super()` öğesi ile çağırarak parent class(üst sınıf)'a referans verebilirsiniz:

```js
class Programmer extends Person {
  hello() {
    return super.hello() + 
      '. I am also a programmer.'
  }
}

const flavio = new Programmer()
flavio.hello()
```

Yukarıdaki program *Hello, I am a Person. I am also a programmer.* şeklinde çıktı verecektir.