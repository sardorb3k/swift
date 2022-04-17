# Swift massivlari

Ushbu qo'llanmada siz misollar yordamida Swift massivlari haqida bilib olasiz.

Massiv - bu o'xshash turdagi ma'lumotlar to'plami. Misol uchun,

**Aytaylik, biz 5** o'quvchining yoshini qayd etishimiz kerak . **5 ta** alohida oʻzgaruvchini yaratish oʻrniga oddiygina massiv yaratishimiz mumkin:

![Yosh qatori](https://cdn.programiz.com/cdn/farfuture/M3wP6yfUwR2XybIMy1UnJOzv2TnSpIDBBAhFzPfjilo/mtime:1620632548/sites/tutorial2program/files/swift-array-intro.png)Massivning elementlari

***

### Swift massivi yarating <a href="#create" id="create"></a>

Swift-da massivni qanday yaratamiz.

```
// an array of integer type
var numbers : [Int] = [2, 4, 6, 8]

print("Array: \(numbers)")  
```

**Chiqish**

```
Massiv: [2, 4, 6, 8]
```

Yuqoridagi misolda biz nomli massiv yaratdik `numbers`. Bu yerda `[Int]`massiv faqat butun sonli ma’lumotlarni saqlashi mumkinligini bildiradi.

Swift - bu turdagi xulosalar tili bo'lib, u avtomatik ravishda massivning ma'lumotlar turini uning qiymatlari asosida aniqlay oladi. Shunday qilib, biz ma'lumotlar turini ko'rsatmasdan massivlarni yaratishimiz mumkin. Misol uchun,

```
var numbers = [2, 4, 6, 8]
print("Array: \(numbers)")   // [2, 4, 6, 8]
```

**Bo'sh massiv yarating**

Swift-da biz bo'sh massiv ham yaratishimiz mumkin. Misol uchun,

```
var value = [Int]()
print(value)
```

**Chiqish**

```
[ ]
```

Yuqoridagi misolda `value`hech qanday element bo'lmagan bo'sh massiv mavjud.

Shuni ta'kidlash kerakki, bo'sh massivni yaratishda biz kvadrat qavs ichida ma'lumotlar turini, `[]`so'ngra initsializator sintaksisini ko'rsatishimiz kerak `()`. Bu erda `[Int]()`bo'sh massiv faqat butun son ma'lumotlar elementlarini saqlashi mumkinligini bildiradi.

**Eslatma**`Int` : Swift-da biz , `String`va hokazo kabi har qanday turdagi ma'lumotlar massivlarini yaratishimiz mumkin .

***

### Massiv elementlariga kirish <a href="#access" id="access"></a>

Swift-da massivdagi har bir element raqam bilan bog'langan. Raqam massiv indeksi sifatida tanilgan.

**Indeks raqami (0, 1, 2 ...)** yordamida massiv elementlariga kirishimiz mumkin . Misol uchun,

```
var languages = ["Swift", "Java", "C++"]

// access element at index 0
print(languages[0])   // Swift

// access element at index 2
print(languages[2])   // C++
```

Yuqoridagi misolda biz nomli massiv yaratdik `languages`.

![Massiv indeksi qanday ishlaydi](https://cdn.programiz.com/cdn/farfuture/rqVibTPf0OmBvWkiTE92v9mV1UrgNfWaWleGaJ9s0cg/mtime:1620632558/sites/tutorial2program/files/swift-array-index.png)Swift-da massivlarni indekslash

Bu erda biz har bir massiv elementi indeks raqami bilan bog'langanligini ko'rishimiz mumkin. Va biz elementlarga kirish uchun indeks raqamidan foydalandik.

**Eslatma** : massiv indeksi har doim **0** bilan boshlanadi . **Demak, massivning birinchi elementi 1** emas, balki **0** indeksida mavjud .

***

### Massivga elementlar qo'shish <a href="#add" id="add"></a>

Swift Array massivga elementlar qo'shishning turli usullarini taqdim etadi.

**1. append() dan foydalanish**

Usul `append()`massivning oxiriga element qo'shadi. Misol uchun,

```
var numbers = [21, 34, 54, 12]

print("Before Append: \(numbers)")

// using append method
numbers.append(32)

print("After Append: \(numbers)")
```

**Chiqish**

```
Ilovadan oldin: [21, 34, 54, 12]
Ilovadan keyin: [21, 43, 54, 12, 32]
```

Yuqoridagi misolda biz nomli massiv yaratdikraqamlar. Chiziqqa e'tibor bering,

```
numbers.append(32)
```

Bu erda massivning oxiriga **32**`append()` qo'shiladi .

`append()`Usuldan bir massivning barcha elementlarini boshqasiga qo'shish uchun ham foydalanishimiz mumkin . Misol uchun,

```
var primeNumbers = [2, 3, 5]
print("Array1: \(primeNumbers)")

var evenNumbers = [4, 6, 8]
print("Array2: \(evenNumbers)")

// join two arrays
primeNumbers.append(contentsOf: evenNumbers)

print("Array after append: \(primeNumbers)")
```

**Chiqish**

```
1-massiv: [2, 3, 5]
2-massiv: [4, 6, 8]
Qo‘shimchadan keyingi massiv: [2, 3, 5, 4, 6, 8]
```

Yuqoridagi misolda bizda ikkita massiv nomlari borasosiy raqamlarvajuft raqamlar. Bayonotga e'tibor bering,

```
primeNumbers.append(contentsOf: evenNumbers)
```

Bu erda biz barcha elementlarni qo'shamizjuft raqamlaruchunasosiy raqamlar.

**Eslatma:** Agar biz barcha elementlarni bir massivdan boshqasiga qo'shishni xohlasak, `contentOf`bilan foydalanishimiz kerak .`append()`

**2. insert() dan foydalanish**

Usul `insert()`massivning belgilangan pozitsiyasiga elementlarni qo'shish uchun ishlatiladi. Misol uchun,

```
var numbers = [21, 34, 54, 12]

print("Before Insert: \(numbers)")

numbers.insert(32, at: 1)

print("After insert: \(numbers)")
```

**Chiqish**

```
Qo‘shishdan oldin: [21, 34, 54, 12]
Kiritilgandan keyin: [21, 32, 34, 54, 12]
```

Bu erda 1 **indeksiga 32**`numbers.insert(32, at:1)` qo'shiladi .

***

### Massiv elementlarini o'zgartirish <a href="#modify" id="modify"></a>

Massiv elementini o'zgartirish uchun massiv indeksidan foydalanishimiz mumkin. Misol uchun,

```
var dailyActivities = ["Eat","Repeat"]
print("Initial Array: \(dailyActivities)")

// change element at index 1
dailyActivities[1] = "Sleep"

print("Updated Array:  \(dailyActivities)")  
 
```

**Chiqish**

```
Boshlang'ich massiv: ["Ovqat", "takrorlash"]
Yangilangan massiv: ["Ovqat", "Uyqu"]
```

Bu erda dastlab **indeks 1** qiymati `Repeat`. Keyin qiymatni `Sleep`foydalanishga o'zgartirdik

```
dailyActivities[1] = "Sleep"
```

***

### Massivdan elementni olib tashlang <a href="#remove" id="remove"></a>

Biz `remove()`massivdan oxirgi elementni olib tashlash uchun usuldan foydalanishimiz mumkin. Misol uchun,

```
var languages = ["Swift","Java","Python"]

print("Initial Array: \(languages)")

// remove element at index 1
let removedValue = languages.remove(at: 1)

print("Updated Array: \(languages)")
print("Removed value: \(removedValue)")
```

**Chiqish**

```
Boshlang'ich massiv: ["Swift", "Java", "Python"]
Yangilangan massiv: ["Swift", "Python"]
O'chirilgan qiymat: Java
```

Xuddi shunday, biz ham foydalanishimiz mumkin

* `removeFirst()`- birinchi elementni olib tashlash uchun
* `removeLast()`- oxirgi elementni olib tashlash uchun
* `removeAll()`- massivning barcha elementlarini olib tashlash uchun

***

### Boshqa massiv usullari <a href="#other" id="other"></a>

| Usul         | Tavsif                                        |
| ------------ | --------------------------------------------- |
| `sort()`     | massiv elementlarini tartiblaydi              |
| `shuffle()`  | massiv elementlarining tartibini o'zgartiradi |
| `forEach()`  | har bir element uchun funktsiyani chaqiradi   |
| `contains()` | massivdagi elementni qidiradi                 |
| `swapAt()`   | massiv elementlarining o'rnini almashtiradi   |
| `reverse()`  | massiv elementlarining tartibini o'zgartiradi |

***

### Massiv orqali aylanish <a href="#loop" id="loop"></a>

Massiv elementlarini takrorlash [uchun for tsiklidan](https://www.programiz.com/swift-programming/for-in-loop) foydalanishimiz mumkin . Misol uchun,

```
// an array of fruits
let fruits = ["Apple", "Peach", "Mango"]

// for loop to iterate over array
for fruit in fruits {
  print(fruit)
}
```

**Chiqish**

```
olma
Shaftoli
Mango
```

***

### Massiv elementlari sonini toping <a href="#count" id="count"></a>

Biz `count`massivda mavjud elementlar sonini topish uchun xususiyatdan foydalanishimiz mumkin. Misol uchun,

```
let evenNumbers = [2,4,6,8]
print("Array: \(evenNumbers)")

// find number of elements
print("Total Elements: \(evenNumbers.count)")
```

**Chiqish**

```
Massiv: [2, 4, 6, 8]
Jami elementlar: 4
```

***

### Massiv bo'sh yoki yo'qligini tekshiring <a href="#empty" id="empty"></a>

Xususiyat `isEmpty`massiv bo'sh yoki yo'qligini tekshirish uchun ishlatiladi. Misol uchun,

```
// array with elements
let numbers = [21, 33, 59, 17]
print("Numbers: \(numbers)")

// check if numbers is empty
var  result = numbers.isEmpty
print("Is numbers empty? : \(result)")

// array without elements
let evenNumbers = [Int]()
print("Even Numbers: \(evenNumbers)")

// check if evenNumbers is empty
result = evenNumbers.isEmpty
print("Is evenNumbers empty? : \(result)")
```

**Chiqish**

```
Raqamlar: [21, 33, 59, 17]
Raqamlar bo'shmi? : yolg'on
Juft raqamlar: []
Juft raqamlar bo'shmi? : rost
```

Yuqoridagi misolda biz `isEmpty`massivlarni tekshirish uchun xususiyatdan foydalanganmizraqamlarvajuft raqamlarbo'sh. Mana, `isEmpty`qaytib keladi

* `true`- agar massiv bo'sh bo'lsa
* `false`- agar massiv bo'sh bo'lmasa

***

### Aralash ma'lumotlar turlariga ega massiv <a href="#mixed" id="mixed"></a>

Hozirgacha biz bitta turdagi ma'lumotlar elementlarini o'z ichiga olgan massivlardan foydalandik.

Biroq, Swift-da biz bir nechta ma'lumotlar turlarining elementlarini saqlay oladigan massivlarni ham yaratishimiz mumkin. Misol uchun,

```
// array with String and integer data
var address: [Any] = ["Scranton", 570]
 
print(address)
```

**Chiqish**

```
["Scranton", 570]
```

Yuqoridagi misolda biz nomli massiv yaratdikmanzil.

```
var address: [Any] = ["Scranton", 570]
```

Bu erda, `[Any]`buni aniqlaydimanzilhar qanday turdagi ma'lumotlar elementlarini o'z ichiga olishi mumkin. Bunday holda, u ikkalasini ham `String`, `Integer`ma'lumotlarni ham saqlaydi.
