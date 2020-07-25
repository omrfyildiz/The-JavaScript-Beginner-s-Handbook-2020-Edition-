## Promises

Promiseler asenkron kodla başa çıkabilmenin alternatif bir yoludur.

Bir önceki bölümde gördüğümüz gibi, callbacklerde(geri çağrımlarda) bir fonksiyonun işlenmesi bittiğinde çağrılacak olan başka bir fonksiyon call'a bir fonksiyon iletiyorduk. 

As we saw in the previous chapter, with callbacks we'd be passing a function to another function call that would be called when the function has finished processing.

Bunun gibi:

```js
doSomething(result => {
  console.log(result)
})
```
`doSomething()` kodu bittiğinde iletilen fonksiyonu bir parametre olarak çağırır:

```js
const doSomething = callback => {
  //do things
  //do things
  const result = /* .. */
  callback(result)
}
```
Bu yaklaşımdaki esas problem, eğer kodumuzun geri kalanında bu fonksiyonun result'ını kullanma ihtiyacımız olsaydı, bütün kodumuz callback'in içine yerleşmeliydi. Ve eğer iki-üç tane callback yapmak zorunda kalsaydık, genellikle "callback cehennemi" denen şeye, diğer fonksiyonlara girme eğilimi olan birçok fonksiyon katmanı ile birlikte girecektik:

```js
doSomething(result => {
  doSomethingElse(anotherResult => {
    doSomethingElseAgain(yetAnotherResult => {
      console.log(result)
    })
  }) 
})
```

Promiseler bu sorunla başa çıkmanın bir yoludur.

Şöyle yapmak yerine:

```js
doSomething(result => {
  console.log(result)
})
```

Promise temelli(promise-based) fonksiyonu bu yolla çağırırız:

```js
doSomething()
  .then(result => {
    console.log(result)
  })
```

Öncelikle fonksiyonu çağırdık, sonra fonksiyon bittiğinde bir `then()` metodu edindik.

Satır girintisi önemli olmasa da okunabilirlik için bu stili sıkça kullanacaksınız.

Hataları yakalamak için `catch()` metodu kullanılması bilinen bir şeydir:

```js
doSomething()
  .then(result => {
    console.log(result)
  })
  .catch(error => {
    console.log(error)
  })
```

Şimdi bu sentaksı kullanabilmek için `doSomething()` fonksiyonu implementasyonu(uygulaması) birazcık özel olmalı. Promises API'sini kullanmalı.

Normal bir fonksiyon olarak deklare etmek yerine:

```js
const doSomething = () => {
  
}
```

Bir promise nesnesi olarak deklare ederiz:

```js
const doSomething = new Promise()
```

ve Promise constructor'ında yeni bir fonksiyon olarak geçeriz:

```js
const doSomething = new Promise(() => {

})
```
Bu fonksiyon iki parametre alır. Birincisini promise'i resolve eden fonksiyon olarak adlandırırız, ikincisini ise reject eden promise olarak.

```js
const doSomething = new Promise(
  (resolve, reject) => {
    
})
```
Bir promise'i resolve etmek demek onu başarılı bir şekilde tamamlamak manasına gelir(Herhangi bir kullanımda `then()` metodu çağrısından gelen sonuçtur).

Bir promise'i reject etmek demek bir hatayla sonlanması anlamına gelir(Bahsedilen hata, herhangi bir kullanımda `catch()` metodu çağrısından gelen sonuçtur.)

Tam olarak şöyle:

```js
const doSomething = new Promise(
  (resolve, reject) => {
    //some code
    const success = /* ... */
    if (success) {
      resolve('ok')
    } else {
      reject('this error occurred')
    }
  }
)
```

resolve ve reject fonksiyonlara istediğimiz türde bir parametre geçebiliriz.