# Swift funksiyasini haddan tashqari yuklash

Ushbu qo'llanmada biz misollar bilan Swift-da funksiyani haddan tashqari yuklash haqida bilib olamiz.

Swift-da ikkita yoki undan ko'p [funktsiyalar](https://www.programiz.com/swift-programming/functions) parametrlari bo'yicha farq qilsa (har xil miqdordagi parametrlar, har xil turdagi parametrlar yoki ikkalasi) bir xil nomga ega bo'lishi mumkin.

Bu funksiyalar haddan tashqari yuklangan funksiyalar va bu funksiya funksiyaning haddan tashqari yuklanishi deb ataladi. Misol uchun:

```
// same function name different arguments
func test() { ... }
func test(value: Int) -> Int{ ... }
func test(value: String) -> String{ ... }
func test(value1: Int, value2: Double) -> Double{ ... }
```

Bu erda `test()`funksiya haddan tashqari yuklangan. Bu funksiyalar bir xil nomga ega, lekin turli argumentlarni qabul qiladi.

**Eslatma** : Yuqoridagi funksiyalarning qaytish turlari bir xil emas. Buning sababi, funktsiyani haddan tashqari yuklash qaytish turlari bilan bog'liq emas. Haddan tashqari yuklangan funktsiyalar bir xil yoki turli xil qaytish turlariga ega bo'lishi mumkin, ammo ular parametrlarda farq qilishi kerak.

***

### 1-misol: Har xil parametr turlari bilan ortiqcha yuklash

```
// function with Int type parameter
func displayValue(value: Int) {
    print("Integer value:", value)
}

// function with String type parameter
func displayValue(value: String) {
    print("String value:", value)
}

// function call with String type parameter
displayValue(value: "Swift")

// function call with Int type parameter
displayValue(value: 2)
```

**Chiqish**

```
String qiymati: Swift 
Integer qiymati: 2
```

Yuqoridagi misolda biz `displayValue()`funktsiyani haddan tashqari yukladik:

* bitta funktsiya `Int`tip parametriga ega
* boshqasi `String`turi parametriga ega

Funksiyani chaqirish paytida uzatilgan argument turiga qarab, mos keladigan funktsiya chaqiriladi.

![DisplayValue() funksiyasi uchun Swift funksiyasining haddan tashqari yuklanishi](https://cdn.programiz.com/cdn/farfuture/gZjsxKzg\_OMqny2j3qWLc3nsrfp90IyVp-LQSCz874c/mtime:1622802548/sites/tutorial2program/files/swift-function-overload.png)DisplayValue() funksiyasi uchun Swift funksiyasining haddan tashqari yuklanishi

***

### 2-misol: Turli sonli parametrlar bilan ortiqcha yuklash

```
// function with two parameters
func display(number1: Int, number2: Int) {
   print("1st Integer: \(number1) and 2nd Integer: \(number2)")
}

// function with a single parameter
func display(number: Int) {
   print("Integer number: \(number)")
}


// function call with single parameter
display(number: 5)

// function call with two parameters
display(number1: 6, number2: 8)
```

**Chiqish**

```
Butun son: 5
1-butun: 6 va 2-butun: 8
```

Bu erda biz `display()`funktsiyani turli xil parametrlar bilan ortiqcha yukladik.

Funksiyani chaqirish paytida o'tkazilgan argumentlar soniga asoslanib, mos keladigan funktsiya chaqiriladi.

![Displey() funksiyasi uchun Swift funksiyasining haddan tashqari yuklanishi](https://cdn.programiz.com/cdn/farfuture/UA0wEXsAiAJ84NyeR4hyhjP-UwM5xRttWpweE5OKiTI/mtime:1622802554/sites/tutorial2program/files/swift-function-overload2.png)Displey() funksiyasi uchun Swift funksiyasining haddan tashqari yuklanishi

***

### 3-misol: Argument yorlig'i bilan funktsiyani ortiqcha yuklash

```
func display(person1 age:Int) {
    print("Person1 Age:", age)
}

func display(person2 age:Int) {
    print("Person2 Age:", age)
}

display(person1: 25)

display(person2: 38)
```

**Chiqish**

```
Odam 1 Yosh: 25
Odam 2 Yosh: 38
```

Yuqoridagi misolda bir xil nomdagi ikkita funksiya bir `display()`xil raqam va bir xil turdagi parametrlarga ega. Biroq, biz hali ham funktsiyani ortiqcha yuklay olamiz.

Buning sababi, Swift-da biz argument belgilaridan foydalanib, funktsiyani ortiqcha yuklashimiz mumkin.

Bu erda ikkita funktsiya turli xil [argument belgilariga](https://www.programiz.com/swift-programming/function-parameter-return-values#argument-label) ega . Va funktsiyani chaqirish paytida ishlatiladigan argument yorlig'iga asoslanib, mos keladigan funktsiya chaqiriladi.
