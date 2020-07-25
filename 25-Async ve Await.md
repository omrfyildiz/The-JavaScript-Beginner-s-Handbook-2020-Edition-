## Async and Await

Async(Asenkron) fonksiyonlar promiselerin "daha ileri seviye abstraction"ıdır

Bir async fonksiyon bir promise döner. Şu örnekteki gibi:

```js
const getData = () => {
  return new Promise((resolve, reject) => {
    setTimeout(() =>
      resolve('some data'), 2000)
  })
}
```

Bu fonksiyonu kullanmak isteyen herhangi bir kod fonksiyondan hemen önce `await` anahtar sözcüğünü kullanacaktır:

```js
const data = await getData()
```
ve böyle yaparak, promise tarafından döndürülen herhangi bir data(veri) `data` değişkenine atanacaktır.

Bizim örneğimizde data "some data" stringidir.

Bir uyarı: `await` anahtar sözcüğünü ne zaman kullanırsak kullanalım, bunu `async` olarak tanımlı bir fonksiyon içinde yapmalıyız.

Bunun gibi:

```js
const doSomething = async () => {
  const data = await getData()
  console.log(data)
}
```
async/await ikilisi daha temiz bir kod yazmamızı ve asenkron kodla çalışmak için basit bir mental model sağlar.

Yukarıdaki örnekte de görebileceğiniz gibi, kodumuz oldukça basit görünüyor. Bunu bir de promiselerin kullanımı veya callback fonksiyonların kullanımı ile karşılaştırın.

Ve bu çok basit bir örnek, esas faydalarını kodunuz daha kompleks hale gelmeye başlayınca göreceksiniz.

Bir örnek olarak, promiseleri kullanıp Fetch API kullanarak bir JSON kaynağını nasıl edinecektiniz ve bunu nasıl ayrıştıracaktınız:

```js
const getFirstUserData = () => {
  // get users list
  return fetch('/users.json') 
    // parse JSON
    .then(response => response.json()) 
    // pick first user
    .then(users => users[0]) 
    // get user data
    .then(user => 
      fetch(`/users/${user.name}`)) 
    // parse JSON
    .then(userResponse => response.json()) 
}

getFirstUserData()
```

Ve bu da await/async kullanarak sağlanan aynı işlevsellik:

```js
const getFirstUserData = async () => {
  // get users list
  const response = await fetch('/users.json') 
  // parse JSON
  const users = await response.json() 
  // pick first user
  const user = users[0] 
  // get user data
  const userResponse = 
    await fetch(`/users/${user.name}`)
  // parse JSON
  const userData = await user.json() 
  return userData
}

getFirstUserData()
```