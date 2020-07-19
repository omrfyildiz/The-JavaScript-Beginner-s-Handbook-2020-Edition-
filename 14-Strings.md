## Strings

bir string karakterlerden meydana gelir.

Bunu tek tırnak işareti ya da çift tırnak işareti içine alınmış string literal(string yazımı) olarak da adlandırabiliriz:

```js
'Bir string'
"Başka bir string"
```

Ben kişisel olarak tek tırnak işareti kullanıyorum her zaman. Çift tırnak işaretini sadece HTML'de attributeları tanımlarken kullanıyorum.

Bir değişkene şu şekilde değer atarsınız:

```js
const name = 'Flavio'
```

`length` property kullanarak bir stringin uzunluğunu elde edebilirsiniz:

```js
'Flavio'.length //6
const name = 'Flavio'
name.length //6
```

Boş bir string şöyledir: `''`. Boş stringin length'i 0'dır:

```js
''.length //0
```

İki string `+` işlemi ile birleştirilebilir:

```js
"A " + "string"
```

Ayrıca `+` işlemini değişkenleri *interpolate(bir araya getirmek)* için kullanabilirsiniz:

```js
const name = 'Flavio'
"My name is " + name //My name is Flavio
```

String tanımlamanın bir diğer yolu da backticks(``) içinde yazılan template literals(şablon yazım)'dir. Çoklu satır stringlerin yazımında kullanılması özellikle işi oldukça kolaylaştırır. Tek ya da çift tırnak işaretiyle kolayca çoklu satırdan oluşan stringleri kolayca tanımlayamazsınız.

Backtick ile bir template literal açtığınız zaman, sadece enter'a basarak(herhangi özel bir karakter olmadan) yeni bir satır oluşturursunuz. Ve olduğu gibi elde edilir:

```js
const string = `Hey
this

string
is awesome!`
```

Template literal çok işe yarar çünkü değişkenleri(variables) ve ifadeleri(expression) stringde kolayca bir araya getirme(interpolate) imkanını sağlar.

`${...}` sentaksını kullanarak da bunu yapabilirsiniz:

```js
const var = 'test'
const string = `something ${var}` 
//something test
```

`${}` içine istediğinizi ekleyebilirsiniz, expressionları bile:

```js
const string = `something ${1 + 2 + 3}`
const string2 = `something 
  ${foo() ? 'x' : 'y'}`
```