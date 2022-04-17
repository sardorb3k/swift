# Swift belgilar va satrlar

Ushbu qo'llanmada siz Swift belgilar va satrlari haqida bilib olasiz. Shuningdek, siz satrlar va belgilar ustida bajarilishi mumkin bo'lgan turli operatsiyalarni o'rganasiz.

### Tezkor xarakter <a href="#character" id="character"></a>

Belgilar - bu bitta belgili satrni ( , , , va hokazo) ifodalovchi [ma'lumotlar turi .](swift-malumotlar-turlari.md)`"a""@""5"`

Biz `Character`kalit so'zdan Swift-da belgilar tipidagi o'zgaruvchilarni yaratish uchun foydalanamiz. Misol uchun,

```
var letter: Character
```

Bu erda `letter`o'zgaruvchi faqat bitta belgili ma'lumotlarni saqlashi mumkin.

***

### Belgilar misoli <a href="#example" id="example"></a>

```
// create character variable
var letter: Character = "H"
print(letter)  // H

var symbol: Character = "@"
print(symbol)  // @ 
```

Yuqoridagi misolda biz ikkita belgi o'zgaruvchisini yaratdik: `letter`va `symbol`. Bu erda biz `"H"`ga `letter`va `"@"`ga tayinladik `symbol`.

**Eslatma:**`Character` Agar o'zgaruvchiga bir nechta belgilarni belgilashga harakat qilsak, xatoga yo'l qo'yamiz.

```
// create character variable
let test: Character = "H@" 

print(test)

// Error:
// cannot convert value of type 'String' to specified type Character
```

***

### Swift String <a href="#string" id="string"></a>

Swift-da matnli ma'lumotlarni saqlash uchun satr ishlatiladi ( `"Hey There!"`, `"Swift is awesome."`, va hokazo).

Biz `String`kalit so'zdan string tipidagi o'zgaruvchilar yaratish uchun foydalanamiz. Misol uchun,

```
let name: String
```

Mana,nomio'zgaruvchi faqat matnli ma'lumotlarni saqlashi mumkin.

**Eslatma:** Satr bir nechta belgilarni o'z ichiga olganligi sababli, u belgilar ketma-ketligi deyiladi.

***

### String misoli <a href="#example" id="example"></a>

```
// create string type variables

let name: String = "Swift"
print(name)

let message = "I love Swift."
print(message) 
```

**Chiqish**

```
Tezkor
Men Swiftni yaxshi ko'raman.
```

Yuqoridagi misolda biz string tipidagi o'zgaruvchilarni yaratdik:nomivaxabarqadriyatlar bilan `"Swift"`va `"I love Swift"`mos ravishda.

Bayonotga e'tibor bering,

```
let message = "I love Swift."
```

**Bu erda** biz `String`o'zgaruvchini yaratishda kalit so'zdan foydalanmadik . Buning sababi, Swift qiymat asosida turni aniqlashga qodir.

**Eslatma:** Swift-da biz satrlar va belgilarni ifodalash uchun qo'sh tirnoqlardan foydalanamiz.

***

### String operatsiyalari <a href="#operations-string" id="operations-string"></a>

Swift- dagi `String`sinf bizga satrlarda turli xil operatsiyalarni bajarishga imkon beradigan turli xil o'rnatilgan funktsiyalarni taqdim etadi.

#### 1. Ikki qatorni solishtiring <a href="#compare" id="compare"></a>

`==`Ikki qatorni solishtirish uchun operatordan foydalanamiz . Agar ikkita satr teng bo'lsa, operator ni qaytaradi `true`. Aks holda, u qaytadi `false`. Misol uchun,

```
let str1 = "Hello, world!"
let str2 = "I love Swift."
let str3 = "Hello, world!"

// compare str1 and str2
print(str1 == str2)

// compare str1 and str3
print(str1 == str3)
```

**Chiqish**

```
yolg'on
rost
```

Yuqoridagi misolda,

* `str1`va `str2`teng emas. Demak, natijayolg'on.
* `str1`va `str3`tengdir. Demak, natijarost.

***

#### 2. Ikki qatorni birlashtiring <a href="#concatenate" id="concatenate"></a>

Biz `append()`Swift-da ikkita qatorni birlashtirish uchun funktsiyadan foydalanamiz. Misol uchun,

```
var greet = "Hello "
var name = "Jack"

// using the append() method
greet.append(name)
print(greet)
```

**Chiqish**

```
Salom!
```

Yuqoridagi misolda biz `append()`qo'shilish usulidan foydalanganmiznomivasalomlashish.

**+ va += yordamida birlashtiring**

Ikki qatorni birlashtirish uchun `+`va operatorlaridan ham foydalanishimiz mumkin .`+=`

```
var greet = "Hello, "
let name = "Jack"

// using + operator
var result = greet + name
print(result)

//using =+ operator
greet +=  name
print(greet)
```

**Chiqish**

```
Salom, Jek
Salom, Jek
```

Yuqoridagi misolda biz ikkita qatorni birlashtirish uchun `+`va `+=`operatorlaridan foydalanganmiz: `greet`va `name`.

**Eslatma:**`greet` yordamida yarata olmaymiz `let`. Buning sababi, `+=`operator ikkita satrni birlashtiradi va yangi qiymatni ga belgilaydi `greet`.

***

#### 3. Satrning uzunligini toping <a href="#count" id="count"></a>

Biz `count`satr uzunligini topish uchun xususiyatdan foydalanamiz. Misol uchun,

```
let message = "Hello, World!"

// count length of a string
print(message.count) // 13
```

**Eslatma:** Bu `count`xususiyat qatordagi belgilarning umumiy sonini, shu jumladan bo'shliqlarni hisoblaydi.

***

#### Boshqa o'rnatilgan funktsiyalar

| O'rnatilgan funksiya | Tavsif                                                                 |
| -------------------- | ---------------------------------------------------------------------- |
| `isEmpty`            | satr bo'sh yoki yo'qligini aniqlaydi                                   |
| `capitalized`        | satrdagi har bir so'zning birinchi harfini bosh harf bilan yozadi      |
| `uppercased()`       | satrni bosh harfga aylantiradi                                         |
| `lowercase()`        | satrni kichik harfga aylantiradi                                       |
| `hasPrefix()`        | satr ma'lum belgilar bilan boshlanishi yoki boshlanmasligini aniqlaydi |
| `hasSuffix()`        | satr ma'lum belgilar bilan tugaydimi yoki yo'qligini aniqlaydi         |

***

### Qochish ketma-ketligi <a href="#escape-sequences" id="escape-sequences"></a>

Escape ketma-ketligi satr ichida mavjud bo'lgan ba'zi belgilardan qochish uchun ishlatiladi.

Aytaylik, biz satr ichiga qo'sh tirnoq qo'shishimiz kerak.

```
// include double quote
var example = "This is "String" class"

print(example) // throws error
```

**Satrlar qo'sh tirnoq** bilan ifodalanganligi sababli , kompilyator `"This is "`satr sifatida ishlaydi. Shunday qilib, yuqoridagi kod xatolikka olib keladi.

Ushbu muammoni hal qilish uchun biz `\`Swift-da qochish belgisidan foydalanamiz.

```
// use the escape character
var example = "This is \"String\" class"

print(example)

// Output: This is "String" class
```

Endi dastur hech qanday xatosiz ishlaydi. Bu erda qochish belgisi kompilyatorga dan keyin belgini e'tiborsiz qoldirishni aytadi `\`.

Bu erda Swift tomonidan qo'llab-quvvatlanadigan barcha qochish ketma-ketliklari ro'yxati.

| Qochish ketma-ketligi | Xarakter             |
| --------------------- | -------------------- |
| `\0`                  | null                 |
| `\\`                  | oddiy teskari chiziq |
|                       | gorizontal yorliq    |
|                       | qator tasmasi        |
| `\"`                  | qo'sh tirnoq         |

***

### String interpolyatsiyasi <a href="#string-interpolation" id="string-interpolation"></a>

`\`Shuningdek , satr ichidagi o'zgaruvchilar va doimiylardan foydalanish uchun teskari chiziq belgisidan foydalanishimiz mumkin. Misol uchun,

```
let name = "Swift"

var message = "This is \(name) programming."
print(message)
```

**Chiqish**

```
Bu Swift dasturlash.
```

Yuqoridagi misolda chiziqqa e'tibor bering

```
var message = "This is \(name) programming."
```

Bu erda biz `name`string ichidagi o'zgaruvchidan foydalanamiz `message`. Bu jarayon Swift-da **String Interpolation** deb ataladi .

***

### Swift multiline string <a href="#multiline-string" id="multiline-string"></a>

Shuningdek, biz Swift-da ko'p qatorli qator yaratishimiz mumkin. Buning uchun biz uch qo'sh tirnoqdan foydalanamiz `"""`. Misol uchun,

```
// multiline string 
var str: String = """
Swift is awesome
I love Swift
"""

print(str)
```

**Chiqish**

```
Swift ajoyib
Men Swiftni yaxshi ko'raman
```

Yuqoridagi misolda, **uch qo'shtirnoq** ichidagi har qanday narsa bitta ko'p qatorli qatordir.

**Eslatma:** Ko'p qatorli satrlar har doim yangi satrdan boshlanishi kerak. Aks holda, xatolik yuzaga keladi.

```
// error code
var str = """Swift 
I love Swift
"""
```

***

#### String Instance yaratish <a href="#string-instance" id="string-instance"></a>

**Biz, shuningdek, boshlang'ich sintaksisi** yordamida satr yaratishimiz mumkin . Misol uchun,

```
var str = String()
```

Bu erda initsializator sintaksisi `String()`bo'sh qatorni yaratadi.
