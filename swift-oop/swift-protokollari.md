# Swift protokollari

Ushbu qo'llanmada biz misollar yordamida Swift protokollari haqida bilib olamiz.

Swift-da protokol keyinchalik sinflar (yoki boshqa turdagi) tomonidan qabul qilinishi mumkin bo'lgan usullar yoki xususiyatlarning rejasini belgilaydi.

`protocol`Protokolni aniqlash uchun kalit so'zdan foydalanamiz . Misol uchun,

```
protocol Greet {

  // blueprint of a property 
  var name: String { get }


  // blueprint of a method 
  func message() 
}    
```

Bu yerda,

* `Greet`- protokolning nomi
* nomi- olinadigan mulk
* `message()`- hech qanday amalga oshirilmasdan usulni aniqlash

**Eslatmalar** :

* Protokol faqat usul yoki xususiyatlar ta'rifini o'z ichiga oladi, ularning haqiqiy tanasi emas.
* Protokolda mulkni olish mumkin yoki olish mumkin va sozlanishi belgilanishi kerak.

***

### Sinfni Swift protokoliga moslashtirish <a href="#conform" id="conform"></a>

Swift-da protokoldan foydalanish uchun boshqa sinflar unga mos kelishi kerak. Sinfni protokolga moslashtirgandan so'ng, biz usulning amalda bajarilishini ta'minlashimiz kerak.

Bu erda sinfni protokolga qanday moslashtirish kerak,

```
// conform class to Greet protocol
class Employee: Greet {

  // implementation of property
  var name = "Perry"

  // implementation of method
  func message() {
    print("Good Morning!")
  }
}
```

Bu erda biz `Employee`sinfni `Greet`protokolga moslashtirdik. Shunday qilib, biz amalga oshirishni ta'minlashimiz keraknomixususiyat va `message()`usul.

***

#### 1-misol: Swift protokoli

```
protocol Greet {
  
  // blueprint of property
  var name: String { get }

  // blueprint of a method 
  func message() 
} 

// conform class to Greet protocol
class Employee: Greet {

  // implementation of property
  var name = "Perry"

  // implementation of method
  func message() {
    print("Good Morning", name)
  }
}

var employee1 = Employee()
employee1.message()
```

**Chiqish**

```
Xayrli tong Perri
```

Yuqoridagi misolda biz nomli protokol yaratdik `Greet`. Protokolda loyiha rejasi mavjudnomixususiyat va `message()`usul.

Bu erda `Employee`sinf mos keladi `Greet`va amalda bajarilishini ta'minlaydinomiva `message()`.

***

#### 2-misol: Hududni hisoblash uchun tezkor protokol

```
protocol Polygon {

  func getArea(length: Int, breadth: Int)
}

// conform the Polygon protocol
class Rectangle: Polygon {

  // implementation of method
  func getArea(length: Int, breadth: Int) {
    print("Area of the rectangle:", length * breadth)
  }
}

// create an object
var r1 = Rectangle()

r1.getArea(length:5, breadth: 6)
```

**Chiqish**

```
To'rtburchakning maydoni: 30
```

Yuqoridagi misolda biz nomli protokol yaratdik `Polygon`. Protokol `getArea()`ikkita parametrli usulning rejasini o'z ichiga oladi:uzunligivakenglik.

Bu erda `Rectangle`sinf usulga mos keladi `Polygon`va amalda amalga oshirilishini ta'minlaydi .`getArea()`

```
func getArea(length: Int, breadth: Int) {
  print("Area of the rectangle:", length * breadth)
}
```

***

### Bir nechta protokollarga muvofiqlik <a href="#multiple" id="multiple"></a>

Swift-da sinf bir nechta protokollarga ham mos kelishi mumkin. Misol uchun,

```
protocol Sum {
  ...
}

protocol Multiplication {
  ...
}

class Calculate: Sum, Multiplication {
  ...
}
```

Bu erda nomlangan sinf va protokollariga `Calculate`mos keladi .`SumMultiplication`

***

#### 3-misol: Bir nechta protokollarni moslashtirish

```
// create Sum protocol
protocol Sum {

  func addition()
}

// create Multiplication protocol
protocol Multiplication {

  func product()
}

// conform class to two protocols
class Calculate: Sum, Multiplication {

  var num1 = 0
  var num2 = 0

  func addition () {
    let result1 = num1 + num2
    print("Sum:", result1)
  }

  func product () {
    let result2 = num1 * num2
    print("Product:", result2)
  }
                   
}

// create an object
var calc1 = Calculate()

// assign values to properties
calc1.num1 = 5
calc1.num2 = 10

// access methods
calc1.addition()
calc1.product()
```

**Chiqish**

```
Jami: 15
Mahsulot: 50
```

&#x20;

Yuqoridagi misolda biz ikkita protokol yaratdik: `Sum`va `Multiplication`. Bundan tashqari, biz `Calculate`ushbu ikkita protokolga mos keladigan sinfni yaratdik.

Biz mos ravishda va protokollar ichida nomlangan `addition()`va `product()`ichida usullarning rejasini yaratdik.`SumMultiplication`

```
protocol Sum {

  func addition()
}

protocol Multiplication {

  func product()
}
```

va `Calculate`ga mos kelgani uchun biz sinf ichida va amalda bajarilishini taqdim etdik .`SumMultiplicationaddition()product()`

Nihoyat, biz ushbu usullardan foydalangan holda foydalandikcalc1sinf ob'ekti.

```
// access methods
calc1.addition()
calc1.product()
```

***

### Swift protokoli meros <a href="#inheritance" id="inheritance"></a>

Sinflarga o'xshab, protokollar boshqa protokollarni meros qilib olishi mumkin. Misol uchun,

```
protocol Car {
  ...
}

protocol Brand: Car {
  ...
}
```

Bu erda `Brand`protokol protokolni meros qilib oladi `Car`. Endi, agar biron bir sinf amalga oshirsa , u ikkala va `Brand`ning barcha xususiyatlari uchun ilovalarni taqdim etishi kerak .`CarBrand`

***

#### 4-misol: Swift protokoli merosi

```
protocol Car {
  var colorOptions: Int { get }
}

// inherit Car protocol
protocol Brand: Car {
  var name: String { get }
}

class Mercedes: Brand {

  // must implement properties of both protocols 
  var name: String = ""
  var colorOptions: Int = 0
}

var car1 = Mercedes()
car1.name = "Mercedes AMG"
car1.colorOptions = 4

print("Name:", car1.name)
print("Color Options:", car1.colorOptions)
```

**Chiqish**

```
Nomi: Mercedes AMG
Rang variantlari: 4
```

&#x20;

Yuqoridagi misolda `Brand`protokol protokolni meros qilib oladi `Car`.

Bu erda `Mercedes`sinf faqat ga mos keladi `Brand`. Ammo `Brand`meros bo'lgani uchun biz ikkala va `Car`ning barcha xususiyatlarini amalga oshirishimiz kerak .`CarBrand`

**Eslatma** : Protokol bir nechta protokollarni meros qilib olishi mumkin. Misol uchun,

```
protocol A {
  ...
}
protocol B {
  ... 
}

protocol C: A, B {
  ...
}
```

***

### Protokol kengaytmalari <a href="#extensions" id="extensions"></a>

Swift-da biz kalit so'z yordamida protokollarni kengaytirishimiz mumkin `extension`. Misol uchun,

```
// protocol definition
protocol Brake {
  func applyBrake()
}

// define class that conforms Brake
class Car: Brake {
  var speed: Int = 0

  func applyBrake() {
    print("Brake Applied")
  }
}

// extend protocol
extension Brake {
  func stop() {
    print("Engine Stopped")
  }
}

let car1 = Car()
car1.speed = 61
print("Speed:", car1.speed)

car1.applyBrake()

// access extended protocol
car1.stop()
```

**Chiqish**

```
Tezlik: 61
Tormoz qo'yilgan
Dvigatel to'xtadi
```

Yuqoridagi misolda biz `Brake`funktsiyani belgilaydigan protokolni yaratdik `applyBrake()`.

Biz `Brake`protokolni kengaytirdik va `stop()`uning ichidagi funksiyani aniqladik.

```
// extend protocol
extension Brake {
  func stop() {
    print("Engine Stopped")
  }
}
```

Biz kengaytirilgan protokolga kirishimiz mumkinavtomobil 1ob'ekt.

```
// access extended protocol
car1.stop()
```
