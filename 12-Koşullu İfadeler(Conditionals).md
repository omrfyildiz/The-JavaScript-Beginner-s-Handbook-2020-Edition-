## Koşullu İfadeler(Conditionals)

Karşılaştırma operatörlerinden bahsederken koşullu ifadelere de değinebiliriz.

Bir `if` ifadesi, programı, bir ifade derlemesinin sonucuna bağlı olan döngü olarak yaratmak için kullanılır.

Her zaman gerçekleşebilecek basit bir örnek:

```js
if (true) {
  //do something
}
```

Yukarıdaki örneğin aksine, şu örnek hiç gerçekleşmez:

```js
if (false) {
  //do something (? never ?)
}
```


Koşullu ifade, kendisine ilettiğiniz ifadeyi doğru(true) veya yanlış(false) bir değer açısından kontrol eder. Bir sayı iletirseniz, bu 0 olmadığı sürece her zaman true olarak değerlendirilir. Bir string iletirseniz, boş bir dize olmadığı sürece her zaman true olarak değerlendirilir. Bunlar, bir boolean'in davranış türünün genel kurallarıdır.

Süslü parantezleri(curly braces) fark ettiniz mi? Bu **block** olarak adlandırılır ve farklı farklı statementlar(kod satırı) listesini gruplamak için kullanılır.

Tekil bir statement olan her yerde blok kullanılabilir. Bir koşuldan sonra çalışmasını istediğiniz bir tekil statement varsa bloktan kurtulup sadece statement'i yazılabilir. 

```js
if (true) doSomething()
```

Fakat ben her zaman daha açık olması için süslü parantezleri tercih ediyorum.

`if` statement'ına ikinci olarak `else` ekleyebilirsiniz:

`if` koşulu false(yanlış) olursa çalışacak statement `else` olur.

```js
if (true) {
  //do something
} else {
  //do something else
}
```

`else` bir statement kabul ettiğinden, içine başka bir if/else statement'ı yerleştirebilirsiniz:

```js
if (a === true) {
  //do something
} else if (b === true) {
  //do something else
} else {
  //fallback
}
```