# Tezkor usullar

Ushbu o'quv qo'llanmada biz misollar yordamida Swift usuli va uning turlari haqida bilib olamiz.

Sinf ichida aniqlangan [Swift funksiyasi metod deyiladi. ](https://www.programiz.com/swift-programming/functions)Misol uchun,

```
class Person {
  . . .    
 
  // define methods
  func greet() {
  // method body    
  }
}
```

Bu erda, sinf `greet()`ichida aniqlangan usul . Usullar haqida bilishdan oldin , Swift -da [sinf](https://www.programiz.com/swift-programming/classes-objects) va [strukturaning](https://www.programiz.com/swift-programming/structs)`Person` ishlashini bilganingizga ishonch hosil qiling .

***

#### 1-misol: Tezkor usullar <a href="#example" id="example"></a>

```
class Person {
  
  // define a method
  func greet() {
    print("Hey there!")
  }
}

var nick = Person()

// call method
nick.greet()
```

**Chiqish**

```
Salom!
```

Yuqoridagi misolda biz sinf `greet()`ichida nomli usul yaratdik. `Person`Bu erda biz `nick`metodni chaqirish uchun sinf ob'ektidan foydalandik.

```
// call method
nick.greet()
```

Usul `greet()`shunchaki uning ichidagi satrni chop etadi `"Hey there!"`.

***

#### 2-misol: Swift usullari yordamida maydon va hajmni hisoblang

```
// create a class
class Hall {

  var length = 0.0
  var breadth = 0.0
  var height = 0.0

  // method to calculate area
  func calculateArea() {
    print("Area of Hall =", length * breadth)
  }

  // method to calculate volume
  func calculateVolume() {
    print("Volume of Hall =", length * breadth * height)
  }
}

// create object of Hall class
var hall1 = Hall()

hall1.length = 42.5
hall1.breadth = 30.8
hall1.height = 45.2

// call calculateArea() method
hall1.calculateArea()

// call calculateVolume() method
hall1.calculateVolume()
```

**Chiqish**

```
Xona maydoni = 1309,0
Xonaning hajmi = 59166,8
```

`Hall`Yuqoridagi misolda biz ikkita usul bilan nomlangan sinf yaratdik :

* `calculateArea()`- zalning maydonini hisoblash
* `calulateVolume()`- zalning hajmini hisoblash

Ushbu usullar sinf ichida e'lon qilinganligi sababli, biz `hall1`ularni chaqirish uchun sinf ob'ektidan foydalandik.

```
hall1.calculateArea()

hall1.calculateVolume()
```

***

### Swift statik usullar <a href="#static" id="static"></a>

Oldingi misolda biz uning usullariga kirish uchun sinf ob'ektlaridan foydalanganmiz. Biroq, biz ob'ektlar yaratmasdan kirish mumkin bo'lgan usullarni ham yaratishimiz mumkin.

Ushbu turdagi usullar statik usullar deb ataladi. Swift-da biz `static`statik usul yaratish uchun kalit so'zdan foydalanamiz. Misol uchun,

```
class Calculator {

  // static method 
  static func add() {
  ...  
  }
}
```

Bu erda `add()`statik usul.

Statik usulga kirish uchun biz sinf nomidan foydalanamiz. Misol uchun,

```
// access static method
Calculator.add()
```

***

#### Misol: Swift statik usullar <a href="#static-method" id="static-method"></a>

```
class Calculator {

  // non-static method
  func multiply(num1: Int, num2: Int) -> Int {
    return num1 * num2
  }

  // static method
  static func add(num1: Int, num2: Int) -> Int {
    return num1 + num2
   }
}

// create an instance of the Calculator class
var obj = Calculator()

// call static method
var result2 =  Calculator.add(num1: 2, num2: 3)
print("2 + 3 =", result2)

// call non-static method
var result1 = obj.multiply(num1:2,num2:2)
print("2 * 2 =", result1)
```

**Chiqish**

```
2 * 2 = 4
2 + 3 = 5
```

Yuqoridagi misolda biz nomli sinf yaratdik `Calculator`. Sinfda statik usul mavjud: `add()`va statik bo'lmagan usul -`multiply()`

Bu yerda,

* `Calculator.add()`- sinf nomidan foydalangan holda statik usulni chaqiradi
* `obj.multiply()`- sinf ob'ekti yordamida statik bo'lmagan usulni chaqiradi.

Statik usul sinf turiga (ob'ekt emas, balki sinf bilan bog'langan), shuning uchun biz ularga sinf nomlari yordamida kirishimiz mumkin.

**Eslatma** : Xuddi shunday, biz strukturada statik usullarni ham yaratishimiz mumkin. Struktura ichidagi statik usullar struktura tipiga ega, shuning uchun biz ularga kirish uchun struktura nomidan foydalanamiz.

***

### Metodlarda Swift shaxsiy mulki <a href="#self" id="self"></a>

Ba'zan xususiyat nomi va usul parametrining nomi bir xil bo'lishi mumkin. Misol uchun,

```
var physics = 0

func checkEligibility(physics: Int) {
... 
}
```

Bu yerda xususiyat ham, usul parametri ham bir xil nomga egafizika.

Bunday hollarda ismlar o'rtasida noaniqlik bo'lishi mumkin. Shunday qilib, ularni farqlash uchun biz `self`mulkdan foydalanamiz. Xususiyat `self`usulning joriy ob'ektiga ishora qiladi.

***

#### Misol: Swift shaxsiy mulki

```
class Marks {

  var physics = 0

  func checkEligibility(physics: Int) {

    // using self property
    if (self.physics < physics) {
      print("Not Eligible for admission")
    }

    else {
      print("Eligible for admission")
    }
  }
}

var student1 = Marks()
student1.physics = 28
student1.checkEligibility(physics: 50)
```

**Chiqish**

```
Qabul qilish huquqiga ega emas
```

Yuqoridagi misolda biz xossa va usul parametrlari uchun fizikaning bir xil nomidan foydalanganmiz.

Ularni farqlash uchun biz `checkEligibility()`usul ichida o'z-o'zini mulkidan foydalanganmiz

```
if (self.physics < physics) {
  ...
}
```

Bu yerda,

* o'z-o'zini.fizika`student1`- qiymati **28** bo'lgan ob'ektning xususiyatiga ishora qiladi .
* fizika**- qiymati 50** bo'lgan usul parametriga ishora qiladi .

Shart ( **28** < **50** ) bo'lganligi `true`sababli, ichidagi `if`operator bajariladi.

***

### Tez mutatsiyaga uchragan usullar <a href="#mutating" id="mutating"></a>

Swift-da, agar biz sinf yoki struktura ichida xususiyatlarni e'lon qilsak, ularni usullar ichida o'zgartira olmaymiz. Misol uchun,

```
struct Employee {

  var salary = 0.0
  ...
  func salaryIncrement() {
    // Error Code
    salary = salary * 1.5
  }
```

Bu erda, chunki `struct`qiymat turi, agar biz qiymatini o'zgartirishga harakat qilsakish haqi, biz xato xabarini olamiz.

Ammo, agar biz usulning ichidan qiymat turining xususiyatlarini o'zgartirmoqchi bo'lsak, `mutating`usulni e'lon qilishda kalit so'zdan foydalanishimiz kerak.

***

#### Misol: Usuldan qiymat turlarini o'zgartirish

```
struct Employee {
  var salary = 0
  
  // define mutating function
  mutating func salaryIncrement(increase: Int) {

  // modify salary property  
  salary = salary + increase
  print("Increased Salary:",salary)
  }
}

var employee1 = Employee()
employee1.salary = 20000
employee1.salaryIncrement(increase: 5000)
```

**Chiqish**

```
Oshgan maosh: 25000
```

Yuqoridagi misolda biz nomli strukturani yaratdik `Employee`. Diqqat,

```
mutating func salaryIncrement(increase: Int) {

  // modify salary property  
  salary = salary + increase
  ...
}
```

Bu erda `mutating`usul bizga qiymatini o'zgartirish imkonini beradiish haqiusul ichida.
