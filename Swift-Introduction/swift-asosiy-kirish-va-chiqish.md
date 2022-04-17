# Swift asosiy kirish va chiqish

Ushbu qo'llanmada biz Swift-da foydalanuvchilarga natijalarni ko'rsatish va foydalanuvchilardan ma'lumot olishning oddiy usullarini o'rganamiz.

### Tez chiqish <a href="#output" id="output"></a>

Swift-da biz shunchaki `print()`funksiyadan chiqishni chop etish uchun foydalanishimiz mumkin. Misol uchun,

```
print("Swift is powerful")

// Output: Swift is powerful
```

Bu erda `print()`funktsiya qo'sh tirnoq ichiga olingan qatorni ko'rsatadi.

**Print() sintaksisi**

Yuqoridagi kodda `print()`funksiya bitta parametrni oladi.

Biroq, chop etish funksiyasining haqiqiy sintaksisi **3 ta** parametrni qabul qiladi

```
print(items: separator: terminator:)
```

Bu yerda,

* **elementlar** - qo'sh tirnoq ichidagi qiymatlar
* **ajratuvchi** (ixtiyoriy) - ichkarida bir nechta **narsalarni** ajratish imkonini beradi `print()`.
* **terminator**`"\n"` (ixtiyoriy) - bizga yangi satr , yorliq kabi ma'lum qiymatlarni qo'shish imkonini beradi`"\t"`

{% hint style="info" %}
**Eslatma:** ajratuvchi va terminator ixtiyoriy. Agar biz ularni ga kiritmasak `print()`, ularning standart qiymatlari: `" "`ajratuvchi uchun bitta bo'sh joy va `"\n"`terminator uchun yangi qator ishlatiladi.
{% endhint %}

***

### 1-misol: Tez chop etish bayonoti <a href="#example1" id="example1"></a>

```
print("Good Morning!")
print("It's rainy today")
```

**Chiqish**

```
Xayrli tong!
Bugun yomg'irli
```

Yuqoridagi misolda `print()`bayonot faqat chop etiladigan **narsalarni o'z ichiga oladi.** Bu erda **terminator** qiymati ishlatilmaydi. Shunday qilib, u standart qiymatni oladi `"\n"`.

Shunday qilib, biz ikki xil satrda chiqishni olamiz.

***

### 2-misol: print() terminatori bilan

```
// print with terminator space
print("Good Morning!", terminator: " ")

print("It's rainy today")
```

**Chiqish**

```
Xayrli tong! Bugun yomg'irli
```

E'tibor bering, biz birinchi bayonotning `terminator: " "`oxiridan keyin qo'shdik.`print()`

Shunday qilib, biz bo'sh joy bilan ajratilgan bitta satrda chiqishni olamiz.

***

### 3-misol: print() ajratuvchi bilan <a href="#example2" id="example2"></a>

```
print("New Year", 2022, "See you soon!", separator: ". ")
```

**Chiqish**

```
Yangi yil. 2022. Tez orada ko'rishguncha!
```

Yuqoridagi misolda bayonot vergul bilan ajratilgan `print()`bir nechta **elementlarni o'z ichiga oladi.**

E'tibor bering, biz bayonot `separator: ". "`ichida ixtiyoriy parametrdan foydalanganmiz. `print()`Demak, chiqish `.`vergul bilan ajratilmagan elementlarni o'z ichiga oladi.

***

### Misol: O'zgaruvchilar va harflarni chop etish <a href="#example3" id="example3"></a>

[Funktsiyadan Swift o'zgaruvchilarini](swift-ozgaruvchilari-konstantalar-va-harflar.md)`print()` chop etish uchun ham foydalanishimiz mumkin . Misol uchun,

```
var number: Double = -10.6

var name: String = "Programiz"

// print literals     
print(5)

// print variables
print(number)
print(name)
```

**Chiqish**

```
5
-10.6
Dasturlash
```

***

### Misol: Birlashtirilgan satrlarni chop etish <a href="#example4" id="example4"></a>

`print()`Shuningdek, biz ikkita satrni bayonot ichida birlashtira olamiz . Misol uchun,

```
print("Programiz is " + "awesome.")
```

**Chiqish**

```
Dasturiz ajoyib.
```

Bu yerda,

* operator `+`ikkita satrni birlashtiradi `"Programiz is "`va`"awesome."`
* funksiya `print()`birlashtirilgan qatorni chop etadi

Satrlarni birlashtirish haqida ko'proq ma'lumot olish uchun [Swift Join String](swift-belgilar-va-satrlar.md) ga tashrif buyuring .

***

### O'zgaruvchilar va satrlarni birga chop eting <a href="#interpolation" id="interpolation"></a>

[Swift-da biz string interpolyatsiyasi](swift-malumotlar-turlari.md) yordamida satr va o'zgaruvchini birga chop etishimiz mumkin . Bu erda biz satr ichidagi o'zgaruvchilarni chop etish uchun teskari chiziq va qavsdan foydalanamiz. Misol uchun,

```
var year = 2014
print("Swift was introduced in \(year)")
```

**Chiqish**

```
Swift 2014 yilda taqdim etilgan
```

`print()`Yuqoridagi misolda, bayonot ichidagi satr o'z ichiga oladi

* **Matn** :`Swift was introduced in`
* **O'zgaruvchan** :/(yil)

Endi `print()`bayonot o'zgaruvchining qiymatini oladiyilva uni ip bilan birlashtiradi.

Shunday qilib, biz natijani olamiz:"Swift 2014 yilda taqdim etilgan".

***

### Swift Basic Input <a href="#input" id="input"></a>

Swift-da biz Xcode o'yin maydonchasidan to'g'ridan-to'g'ri ma'lumot ololmaydi.

Biroq, biz Xcode-da buyruq qatori vositasini yaratishimiz va foydalanuvchilardan ma'lumot olish uchun `readLine()`funksiyadan foydalanishimiz mumkin.

Misol uchun,

```
print("Enter your favorite programming language:")
let name = readLine()

print("Your favorite programming language is \(name!).")
```

**Chiqish**

```
Sevimli dasturlash tilingizni kiriting:
Tezkor
Sevimli dasturlash tilingiz Swift.
```

Yuqoridagi misolda biz foydalanuvchilardan qiymatlarni kiritishlarini so'raymiz. Kodga e'tibor bering,

```
let name = readLine()
```

Bu erda `readLine()`foydalanuvchidan ma'lumot oladi va uni nom o'zgaruvchisiga tayinlaydi.

Funktsiya `readLine()`oddiy qatorni qaytarmaydi. Buning o'rniga, u ixtiyoriy qatorni qaytaradi. Shuning uchun biz `name!`ismni majburan ochishga odatlanganmiz.

Majburiy emasligi haqida koʻproq maʼlumot olish uchun [Swift Options](swift-opsiyalari.md) ga tashrif buyuring .

{% hint style="info" %}
**Eslatma** : Yuqoridagi dastur faqat Xcode-da buyruq qatori vositasi yaratgan bo'lsangiz ishlaydi. Buyruqlar qatori vositalarini qanday yaratishni o'rganish uchun [macOS-da Buyruqlar](https://stackoverflow.com/questions/24004776/input-from-the-keyboard-in-command-line-application#answer-47880208) qatori vositasiga tashrif buyuring .
{% endhint %}
