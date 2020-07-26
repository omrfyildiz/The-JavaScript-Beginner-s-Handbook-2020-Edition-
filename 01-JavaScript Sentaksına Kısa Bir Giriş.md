## JavaScript sentaksına(söz dizimine) kısa bir giriş

Bu kısacık girişte sizlere beş konu hakkında bir şeyler söyleyeceğim:

* Boşluk(White space)

* Büyük-küçük harf ayrımı

* Yazım(Literals)

* Tanımlayıcılar(identifiers)

* Yorum
  
## ----------

### Boşluk (White Space)

 JavaScript bırakılan boşluğu anlamlandırmaz. Boşluklar ve satır geçişleri, teoride, istediğiniz tarzda eklenebilir.

Pratikte, büyük ihtimalle iyi derlenmiş bir stil tutturacaksınız ve insanlar çoğunlukla ne kullanıyorsa ona bağlı olacaksınız. Bu kullanım sizi Prettier gibi bir stil aracı kullanımına sizi itecektir.

## ----------

### Büyük-küçük harf ayrımı
 JavaScript büyük-küçük harf ayrımına duyarlıdır. `something` diye yazacağınız şey `Something` 'den farklı olacaktır.

 Aynısı herhangi bir tanımlayıcı(identifier) için de geçerlidir.

## ----------

## Yazım(Literals)

Yazımı, kaynak kodda yazılmış bir değer olarak tanımlarız. Örneğin bir sayı(number), string, boolean ya da Nesne yazımı(Object literals) veya Dizi yazımı(Array literals) gibi daha ileri constructlar(yapılar).

```javascript
5
'Test'
true
['a', 'b']
{color: 'red'; shape:'Rectangle'}

```

## ----------

### Tanımlayıcılar(Identifiers)
Tanımlayıcı(identifier) bir değişkeni, bir fonksiyonu ya da bir objeyi tanımlamak için kullanılan karakter aralığı olarak adlandırılabilir. Bir harfle, dolar($) işaretiyle, alt çizgi(_) de başlayabilir ya da basamaklar(digits) içerebilir. Unicode(Evrensel kod) kullanarak bir harf, izin verilen herhangi bir karakter olabilir, mesela bir emoji(😄).

```javascript
Test
test
TEST
_test
Test1
$test

```

Dolar işareti DOM(Data Object Model) elementlerine referans için kullanılır.

Bazı adlar JavaScript dahili kullanımı için rezerve edilmiştir; bunları tanımlayıcı olarak kullanamayız.

## ----------

### Yorumlar
Yorumlar bir programın ya da programlama dilinin en önemli parçalarıdır. Önemli olmalarının sebebi kodu okurken kendimiz için ya da okuyacak başka birisi için kod hakkında detaylı açıklamalar yapmamızı ve önemli bilgileri eklememizi sağlamasıdır.

JavaScript'te tek satırlık yorumları `//` ile yaparız. Bu aralıkta yazılanlar kod olarak değerlendirilmez.

```javascript
// Bir Yorum
true //Başka bir yorum

```

Bir diğer yorum ise çoklu satırlardaki yorumdur. `/*` ile başlar ve `*/` ile biter.

Bu aralıktakiler kod olarak değerlendirilmez.

```javascript
/* some kind
of
comment

*/
```