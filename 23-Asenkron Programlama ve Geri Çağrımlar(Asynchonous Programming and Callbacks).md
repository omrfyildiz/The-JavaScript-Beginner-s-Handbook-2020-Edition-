## Asenkron Programlama ve Geri Çağrımlar(Asynchonous Programming and Callbacks)

Çoğu zaman JavaScript kodu senkron olarak çalışır.

Bunun anlamı, bir kod satırı çalıştırılır, sonra bir sonraki satırdaki çalışır ve böyle devam eder.

Her şey sizin de beklediğiniz gibidir ve birçok programlama dilinde nasıl çalışıyorsa o şekildedir.

Yine de bazı zamanlar vardır ki sadece bir kod satırının çalışması için bekleyemezsiniz.

Büyük bir dosyanın yüklenmesi için iki saniye bekleyemezsiniz ve programı tamamen durduramazsınız.

Başka bir şey yapmadan önce bir ağ(network) kaynağının indirilmesini öylece bekleyemezsiniz.

JavaScript bu problemi **callbacks** kullanarak çözer.

callbacklerin nasıl kullanılacağının en basit yollarından biri timerlardır(zamanlayıcılar). Timerlar JavaScript'in bir parçası değildir ama tarayıcı ve Node.js tarafından sağlanırlar. Size timerlardan biri olan `setTimeout` hakkında biraz bahsedeyim.

`setTimeout` fonksiyonu iki argüman alır: bir fonksiyon ve bir sayı. Sayı, fonksiyon çalıştırılmadan önce geçmesi gereken milisaniyedir.

Örnek:

```js
setTimeout(() => {
  // runs after 2 seconds(iki saniye sonra çalışır)
  console.log('inside the function')
}, 2000)
```

`console.log('inside the function')` dizesini içeren fonksiyon iki saniye sonra çalışır.

Fonksiyona öncül olarak `console.log('before')` ve sonuna `console.log('after')` eklerseniz:

```js
console.log('before')
setTimeout(() => {
  // runs after 2 seconds(iki saniye sonra çalışır)
  console.log('inside the function')
}, 2000)
console.log('after')
```
Konsolda şunun olduğunu göreceksiniz:

```js
before
after
inside the function
```
Callback fonksiyon asenkron olarak çalışacaktır.

Dosya sistemleri, network, eventler ya da tarayıcıdaki DOM ile çalışırken bu çok yaygın bir desendir.

Tüm bu bahsettiklerim JavaScript "temeli" olan şeyler değildir. Yani bu kitapta hepsi açıklanmadı, fakat birçok örneğini diğer handbooklarımda bulabilirsiniz [https://flaviocopes.com](https://flaviocopes.com/).

Kodun içinde callbackleri nasıl uyguladığımızı görelim.

Bir fonksiyon olan `callback` parametresini alacak olan fonksiyonu tanımlayalım.

Kodumuz callback'i tetiklemeye hazır olduğunda, kendisini result geçirerek tetikleriz:

```js
const doSomething = callback => {
  //do things
  //do things
  const result = /* .. */
  callback(result)
}
```

Bu fonksiyonu kullanan kod şu şekilde kullanılacaktır:

```js
doSomething(result => {
  console.log(result)
})
```