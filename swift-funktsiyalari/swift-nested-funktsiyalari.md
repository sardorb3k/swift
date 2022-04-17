# Swift Nested funktsiyalari

Ushbu o'quv qo'llanmada biz misollar yordamida Swift-dagi ichki funksiyalar haqida bilib olamiz.

Swift-da funktsiya boshqa funktsiyaning tanasi ichida mavjud bo'lishi mumkin. Bu ichki funksiya deb ataladi.

Ichki funksiyalar haqida bilishdan oldin [Swift funksiyalari](https://www.programiz.com/swift-programming/functions) haqida bilib oling .

***

#### Ichki funksiya sintaksisi

Swift-da ichki o'rnatilgan funktsiyalarni qanday yaratamiz.

```
// outer function
func function1() {
  // code

  // inner function
  func function2() {
    // code
  }

}
```

Bu yerda funksiya `function2()`tashqi funksiya ichiga joylashtirilgan`function1()`

***

#### 1-misol: Swift Nested funksiyasi

```
// outer function
func greetMessage() {

  // inner function
  func displayName() {
    print("Good Morning Abraham!")
  }

  // calling inner function
  displayName()
}

// calling outer function
greetMessage()
```

**Chiqish**

```
Xayrli tong Ibrohim!
```

Yuqoridagi misolda biz ikkita funktsiyani yaratdik:

* `greetMessage()`- muntazam funktsiya
* `displayName()`- ichkariga joylashtirilgan ichki funksiya`greetMessage()`

`displayName()`Bu erda biz tashqi funktsiyadan ichki funktsiyani chaqiramiz .

**Eslatma** : Agar biz tashqi funktsiyadan tashqaridan ichki funktsiyani chaqirishga harakat qilsak, xato xabarini olamiz: `use of unresolved identifier`.

***

#### 2-misol: Parametrli ichki funksiya

```
// outer function
func addNumbers() {
  print("Addition")

  // inner function
  func display(num1: Int, num2: Int) {
      print("5 + 10 =", num1 + num2)
  }

  // calling inner function with two values
  display(num1: 5, num2: 10)
}

// calling outer function
addNumbers()
```

**Chiqish**

```
Qo'shish
5 + 10 = 15
```

Yuqoridagi misolda funksiya funktsiya `display()`ichiga joylashtirilgan `addNumbers()`. Ichki funktsiyaga e'tibor bering,

```
func display(num1: Int, num2: Int) {
  ...
}
```

Bu erda u ikkita parametrdan `num1`va dan iborat `num2`. Shunday qilib, biz uni chaqirayotganda **5** va **10**`display(num1: 5, num2: 10)` dan o'tdik ( )

***

#### 3-misol: Qaytish qiymatlari bilan ichki o'rnatilgan funksiya

```
func operate(symbol: String) -> (Int, Int) -> Int {

  // inner function to add two numbers 
  func add(num1:Int, num2:Int) -> Int {
    return num1 + num2
  }

  // inner function to subtract two numbers    
  func subtract(num1:Int, num2:Int) -> Int {
    return num1 - num2
  }

  let operation = (symbol == "+") ?  add : subtract
  return operation
}

let operation = operate(symbol: "+")
let result = operation(8, 3)
print("Result:", result)
```

**Chiqish**

```
Natija: 11
```

Yuqoridagi misolda va funksiyalari funksiya `add()`ichiga `subtract()`joylashtirilgan `operate()`. Tashqi funktsiya deklaratsiyasiga e'tibor bering

```
func operate(symbol: String) -> (Int, Int) -> Int {
  ...
}
```

Bu yerda qaytish turi `(Int, Int) -> Int`tashqi funksiya bilan funksiyani qaytarishini bildiradi

* turdagi ikkita parametr `Int`va
* turdagi qaytish qiymati `Int`.

Bu ichki funksiyalarning funksiya taʼrifiga mos kelganligi sababli, tashqi funksiya ichki funksiyalardan birini qaytaradi.

Shuning uchun biz ichki funktsiyani tashqi funktsiyadan tashqaridan ham chaqira olamiz

```
let result = operation(8, 3)
```

Bu yerda, yoki `operation(8, 3)`bilan almashtiriladi `add(8, 3)`yoki `subtract(8, 3)`qiymatiga asoslanadiramzi`operate()`funksiyasiga o‘tdi .
