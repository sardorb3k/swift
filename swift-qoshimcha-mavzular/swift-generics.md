# Swift Generics

Ushbu qo‘llanmada biz Swift Generics, umumiy funksiyalar va turlarini qanday yaratish va uning afzalliklarini misollar yordamida bilib olamiz.

Swift Generics bizga turli xil ma'lumotlar turlari bilan ishlatilishi mumkin bo'lgan yagona funktsiya va sinfni (yoki boshqa turdagi) yaratishga imkon beradi.

Bu bizga kodimizni qayta ishlatishga yordam beradi.

***

### Swift umumiy funksiyasi <a href="#function" id="function"></a>

Swift-da biz har qanday turdagi ma'lumotlar bilan ishlatilishi mumkin bo'lgan funktsiyani yaratishimiz mumkin. Bunday funktsiya umumiy funktsiya deb nomlanadi.

Swift-da umumiy funktsiyani qanday yaratishimiz mumkin:

```
// create a generic function
func displayData<T>(data: T){
  ...
}
```

Bu yerda,

* nomli umumiy funksiya yaratdik `displayData()`.
* `T`burchak qavs ichida ishlatiladi **turi parametri**`<>` deyiladi .

Va funktsiyaga berilgan qiymat turiga qarab, `T`o'sha ma'lumotlar turiga ( `Int`, `String`, va hokazo) almashtiriladi.

**Eslatma** : Biz turi parametriga istalgan nom berishimiz mumkin: `<S>`, `<Element>`, va hokazo. Lekin, odatda, biz dan foydalanamiz `T`.

***

### Misol: Swift umumiy funksiyasi <a href="#example" id="example"></a>

```
  // create a generic function
func displayData<T>(data: T) {
  print("Generic Function:")
  print("Data Passed:", data)
}

// generic function working with String
displayData(data: "Swift")

// generic function working with Int
displayData(data: 5)
```

**Chiqish**

```
Umumiy funktsiya:
O'tkazilgan ma'lumotlar: Swift
Umumiy funktsiya:
O'tkazilgan ma'lumotlar: 5
```

`displayData()`Yuqoridagi misolda biz type parametri bilan nomlangan umumiy funksiya yaratdik `<T>`.

Endi biz umumiy funktsiyani chaqirganimizda

```
displayData(data: "Swift")
```

biz satr qiymatidan o'tdik, shuning uchun to'ldiruvchi parametr `T`avtomatik ravishda bilan almashtiriladi `String`.

Xuddi shunday, biz `Int`umumiy funktsiyaga o'tganimizda

```
displayData(data: 5)
```

joy egallovchi bilan almashtiriladi `Int`.

***

### Swift umumiy sinf <a href="#class" id="class"></a>

Umumiy funktsiyaga o'xshab, biz ham har qanday turdagi ma'lumotlar bilan ishlatilishi mumkin bo'lgan sinfni yaratishimiz mumkin. **Bunday sinf umumiy sinf** sifatida tanilgan .

Keling, bir misolni ko'rib chiqaylik,

```
// create a generic class
class Information<T> {

  // property of T type
  var data: T

  init (data: T) {
    self.data = data
  }

  // method that return T type variable
  func getData() -> T {
    return self.data
  }
}

// initialize generic class with Int data
var intObj = Information<Int>(data: 6)
print("Generic Class returns:", intObj.getData())

// initialize generic class with String data
var strObj = Information<String>(data: "Swift")
print("Generic Class returns:", strObj.getData())
```

**Chiqish**

```
Umumiy sinf qaytaradi: 6
Umumiy sinf qaytaradi: Swift
```

Yuqoridagi misolda biz nomli umumiy sinf yaratdikMa \`lumot. Bu sinf har qanday turdagi ma'lumotlar bilan ishlash uchun ishlatilishi mumkin.

```
class Information<T> {...}
```

Biz ikkita ob'ektni yaratdikMa \`lumot

```
var intObj = Information<Int>(data: 6)

var strObj = Information<String>(data: "Swift")
```

Bu yerda,

1. intObj- tip parametri `T`bilan almashtiriladi `Int`. Endi `Information`butun sonli ma'lumotlar bilan ishlaydi.
2. stringObj- tip parametri `T`bilan almashtiriladi `String`. Endi, `Information`string ma'lumotlar bilan ishlaydi.

***

### Swift Generics-da turdagi cheklovlar <a href="#type-constraints" id="type-constraints"></a>

Umuman olganda, **tip parametri** har qanday ma'lumotlar turini ( `Int`, `String`, `Double`, ...) qabul qilishi mumkin.

Biroq, agar biz faqat ba'zi bir maxsus turlar uchun (masalan, raqam turlarining ma'lumotlarini qabul qilish) generiklardan foydalanmoqchi bo'lsak, u holda biz tur cheklovlaridan foydalanishimiz mumkin.

Turi cheklovlarini qanday yaratamiz:

```
func addition<T: Numeric>(num1: T, num2: T) {
  ...
}
```

Bu erda `<T: Numeric>`tur parametriga cheklovlar qo'shiladi. Bu protokolga `T`mos kelishi kerakligini belgilaydi.`Numeric`

**Eslatma** : va `Numeric`kabi raqamli qiymatlar uchun o'rnatilgan protokol .`IntDouble`

***

#### Misol: Tur cheklovlari

```
//create a generic function with type constraint
func addition<T: Numeric>(num1: T, num2: T) {

  print("Sum:", num1 + num2)
}

// pass Int value
addition(num1: 5, num2: 10)

// pass Double value
addition(num1: 5.5, num2: 10.8)
```

**Chiqish**

```
Jami: 15
Yig'indi: 16.3
```

Yuqoridagi misolda biz nomli umumiy funksiya yaratdik `addition()`. ifodaga e'tibor bering,

```
<T: Numeric>
```

Bu yerda umumiy funksiya tur cheklovlari bilan yaratilgan. Bu `addition()`faqat Raqamli protokolga ( `Int`, `Double`, va hokazo) mos keladigan ma'lumotlar turlari bilan ishlashi mumkin.

**Eslatma** : Agar biz boshqa turlarni o'tkazishga harakat qilsak, deylik `String`, xatoga duch kelamiz: `argument type 'String' does not conform to the expected type 'Numeric'`.

***

### Swift Generics-ning afzalliklari <a href="#advantages" id="advantages"></a>

#### 1. Kodni qayta ishlatish imkoniyati

Swift-dagi generiklar yordamida biz har xil turdagi ma'lumotlar bilan ishlaydigan kod yozishimiz mumkin. Misol uchun,

```
func genericFunction<T>(data: T) {...}
```

Bu erda biz umumiy funktsiyani yaratdik. Xuddi shu funktsiya butun sonli ma'lumotlar, satr ma'lumotlari va boshqalar bilan operatsiyalarni bajarish uchun ishlatilishi mumkin.

#### 2. Collections bilan ishlatiladi

Swift qatori generiklar tushunchasidan foydalanadi. Misol uchun,

```
// creating a integer type array
var list1: Array<Int> = []

// creating a string type array
var list2: Array<String> = []
```

Bu yerda,ro'yxat 1`Int`va qiymatlarini saqlaydigan massivro'yxat 2`String`qiymatlarni saqlaydigan massiv .

Massivlar singari, lug'atlar ham Swiftda umumiydir.
