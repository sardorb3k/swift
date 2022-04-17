# Swift o'zgaruvchilari, konstantalar va harflar

Ushbu qo'llanmada siz Swift-dagi o'zgaruvchilar, konstantalar va literallar haqida bilib olasiz.

### 1. Swift o'zgaruvchilari <a href="#variables" id="variables"></a>

Dasturlashda o'zgaruvchi ma'lumotlarni saqlash uchun konteyner (saqlash maydoni) hisoblanadi. Misol uchun,

```
var num = 10 
```

Bu erda `num`10 qiymatini saqlaydigan o'zgaruvchi mavjud.

***

### Swift-da o'zgaruvchilarni e'lon qilish <a href="#declare-variable" id="declare-variable"></a>

Swift-da biz `var`o'zgaruvchilarni e'lon qilish uchun kalit so'zdan foydalanamiz. Misol uchun,

```
var siteName:String
var id: Int
```

Bu yerda,

* sayt nomitipdagi o‘zgaruvchidirString. Ya'ni, u faqat matn qiymatlarini saqlashi mumkin.
* id`Int`tipdagi o‘zgaruvchidir . Ya'ni, u faqat butun son qiymatlarini saqlashi mumkin.

{% hint style="info" %}
**Eslatma:** Swift-da biz e'lon qilingan o'zgaruvchining turini o'zgartira olmaymiz.
{% endhint %}

***

### O'zgaruvchilarga qiymatlarni belgilash <a href="#assign-variable" id="assign-variable"></a>

`=`Siz operator yordamida o'zgaruvchilarga qiymatlarni belgilashingiz mumkin .

```
var siteName: String
siteName = "swift.satif.uz"

print(siteName) 
```

**Chiqish**

```
swift.satif.uz
```

Shuningdek, siz o'zgaruvchini to'g'ridan-to'g'ri turdagi izohsiz belgilashingiz mumkin:

```
var siteName = "swift.satif.uz"
print(siteName) // swift.satif.uz
```

Bu erda kompilyator buni avtomatik ravishda aniqlaydisayt nomi`String`tipdagi o‘zgaruvchidir .

***

### O'zgaruvchining qiymatini o'zgartirish <a href="#change-variable" id="change-variable"></a>

Mavjud o'zgaruvchining qiymatini o'zgartirishingiz mumkin. Demak, **o'zgaruvchining** nomi . Misol uchun,

```
var siteName = "swift.satif.uz"
 
// siteName ga yangi qiymat belgilash
siteName = "apple.com"
print(siteName)
```

**Chiqish**

```
apple.com
```

Bu erda, qiymatisayt nomidan o'zgartiriladi "swift.satif.uz" uchun "apple.com".

***

### Swift o'zgaruvchilarni nomlash qoidalari <a href="#rules" id="rules"></a>

O'zgaruvchilarni nomlash qoidalari:

1.  O'zgaruvchilar nomlari harf, pastki chiziq `_`yoki dollar belgisi bilan boshlanishi kerak `$`. Misol uchun,

    ```
    // valid
    var a = "hello"
    var _a = "hello"
    var $a = "hello"
    ```
2.  O'zgaruvchilar nomlari raqamlar bilan boshlanmaydi. Misol uchun,

    ```
    // invalid
    var 1a = "hello" // throws error
    ```
3.  Swift katta-kichik harflarga sezgir. Shunday qilibAvaaturli oʻzgaruvchilardir. Misol uchun,

    ```
    var A = 5 
    var a = 55
    print(A) // 5
    print(a) // 55
    ```
4. , , , va hokazo kabi _Swift kalit so'zlarini_ o'zgaruvchilar nomi sifatida ishlatishdan saqlaning .`varStringclass`

**Eslatmalar** :

* Ta'riflovchi o'zgaruvchiga nom berish yaxshi amaliyotdir. Misol uchun,olma sonidan yaxshiroq o'zgaruvchan noma,olma, yokin.
* Swift-da, o'zgaruvchilar nomlari, agar ularda bir nechta so'z bo'lsa, odatda camelCase-da yoziladi. Misol uchun,myVariable,addTwoNums, va boshqalar.

***

### 2. Tezkor konstantalar <a href="#constants" id="constants"></a>

Konstanta - qiymatini o'zgartirib bo'lmaydigan o'zgaruvchilarning maxsus turi. Misol uchun,

```
let a = 5
```

Mana, keyina5 ga ishga tushirilgan bo'lsa, biz uning qiymatini o'zgartira olmaymiz.

***

### Swiftda doimiylarni e'lon qilish <a href="#declare-constant" id="declare-constant"></a>

Swift-da biz `let`doimiylarni e'lon qilish uchun kalit so'zdan foydalanamiz. Konstantaning qiymatini o'zgartirib bo'lmaydi. Misol uchun,

```
let x = 5
x = 10      // Error
print(x)
```

**Chiqish**

```
main.swift:4:1: xato: qiymatni belgilash mumkin emas: 'x' - 'kel' doimiysi
```

Bundan tashqari, siz doimiyni ishga tushirmasdan e'lon qila olmaysiz. Misol uchun,

```
let siteName: String
print(siteName)
```

**Chiqish**

```
main.swift:4:7: xato: ishga tushirishdan oldin doimiy "siteName" ishlatilgan
```

**Eslatmalar:**

* Agar o'zgaruvchining qiymati dastur davomida o'zgarmasligiga ishonchingiz komil bo'lsa, undan foydalanish tavsiya etiladi `let`.
* O'zgaruvchilarni nomlash qoidalari doimiylarga ham tegishli.

***

### 3. Swift Literals <a href="#literals" id="literals"></a>

Literallar dasturdagi oʻzgarmas qiymatlarning koʻrinishidir. Ular raqamlar, belgilar yoki satrlar va boshqalar bo'lishi mumkin. Masalan,"Salom Dunyo!",12,23.0,"C", va boshqalar.

Literallar ko'pincha o'zgaruvchilar yoki konstantalarga qiymat berish uchun ishlatiladi.

**Misol uchun:**

```
let siteName = "Apple.com"
```

Yuqoridagi ifodada,sayt nomio‘zgaruvchi bo‘lib, `"Apple.com"`literaldir.

***

### Butun sonli harflar <a href="#integer-literals" id="integer-literals"></a>

Butun sonli harflar kasr yoki eksponensial qismga ega bo'lmaganlardir.

Swift-da butun sonli harflarning to'rt turi mavjud:

| Turi        | Misol       | Izohlar           |
| ----------- | ----------- | ----------------- |
| O'nlik      | 5, 10, -68  | Oddiy raqamlar.   |
| Ikkilik     | 0b101, 0b11 | bilan boshlang0b. |
| Sakkizlik   | 0o13        | bilan boshlang0o. |
| O'n oltilik | 0x13        | bilan boshlang0x. |

***

### Suzuvchi nuqtali harflar <a href="#float-literal" id="float-literal"></a>

Suzuvchi nuqtali harflar suzuvchi kasrli sonli harflardir. Misol uchun,

```
let piValue: Float = 3.14
```

Bu yerda,3.14ga tayinlangan suzuvchi nuqtali harfdirpiValuedoimiy.

***

### Mantiqiy harflar <a href="#bool-literals" id="bool-literals"></a>

Ikkita mantiqiy harflar mavjud: `true`va `false`.

Misol uchun,

```
let pass: Bool = true  
```

Bu erda `true`mantiqiy literal tayinlangano'tish.

***

### String va belgilar harflari <a href="#string-char-literals" id="string-char-literals"></a>

Belgilar harflari ikki tirnoq ichiga olingan Unicode belgilaridir. Misol uchun,

```
let someCharacter: Character = "S"
```

Bu yerda, `S`belgi literal tayinlanganba'zi belgilar.

Xuddi shunday, String literallari juft tirnoq ichiga olingan belgilar ketma-ketligidir `"`.

Misol uchun,

```
let someString: String = "Swift is fun" 
```

Bu yerda,"Swift qiziqarli"ga tayinlangan satr harfidirsomeString.
