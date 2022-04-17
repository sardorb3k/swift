# Swift sinflari va ob'ektlari

Ushbu qo'llanmada biz Swift sinflari haqida bilib olamiz, shuningdek, misollar yordamida ob'ektlar yaratishni o'rganamiz.

Swift ham ob'ektga yo'naltirilgan dasturlash tilidir. Va, boshqa oop tillari kabi, u ham ob'ektlar va sinflar tushunchasini qo'llab-quvvatlaydi.

Ob'ekt shunchaki ma'lumotlar (o'zgaruvchilar) va usullar (funktsiyalar) to'plamidir. Xuddi shunday, sinf bu ob'ekt uchun rejadir.

Ob'ektlar haqida bilishdan oldin, Swift-dagi sinflar haqida bilib olaylik.

***

### Tezkor sinflar

Sinf ob'ektlarning rejasi sifatida qaraladi. Biz sinfni uyning eskizi (prototipi) sifatida tasavvur qilishimiz mumkin. Unda pollar, eshiklar, derazalar va boshqalar haqida barcha ma'lumotlar mavjud. Ushbu tavsiflarga asoslanib, biz uy quramiz. Uy - ob'ekt.

Xuddi shu tavsifdan ko'plab uylar yasalishi mumkinligi sababli, biz sinfdan ko'plab ob'ektlarni yaratishimiz mumkin.

***

### Swift sinfini aniqlang <a href="#define" id="define"></a>

Swift-da sinf yaratish uchun biz class kalit so'zidan foydalanamiz. Misol uchun,

```
class ClassName {
  // class definition 
}
```

Bu yerda biz ClassName nomli sinf yaratdik.

Keling, bir misolni ko'rib chiqaylik,

```
class Bike {

  var name = ""
  var gear = 0
}
```

Bu yerda,

* `Bike`- sinf nomi
* `name/gear`- sinf ichidagi o'zgaruvchilar standart qiymatlari `""`va mos ravishda **0** .

**Eslatma** : Sinf ichidagi o'zgaruvchilar va doimiylar xususiyatlar deyiladi.

***

### Tezkor ob'ektlar <a href="#objects" id="objects"></a>

Ob'ekt sinfning namunasi deb ataladi. Misol uchun, sinf bo'lsa, biz sinfdan , va hokazo `Bike`kabi ob'ektlarni yaratishimiz mumkin .`bike1bike2`

Bu yerda ob'ekt yaratish sintaksisi.

```
var objectName = ClassName()
```

Keling, bir misolni ko'rib chiqaylik,

```
// create class
class Bike {

  var name = ""
  var gears = 0
}

// create object of class
var bike1 = Bike()
```

Bu erda `bike1`sinfning ob'ekti. Endi biz ushbu ob'ektdan sinf xususiyatlariga kirish uchun foydalanishimiz mumkin.

***

### Ob'ektlar yordamida Class xususiyatiga kiring <a href="#access" id="access"></a>

Biz `.`sinfning xususiyatlariga kirish uchun belgidan foydalanamiz. Misol uchun,

```
// modify the name property
bike1.name = "Mountain Bike"

// access the gear property
bike1.gears
```

Bu erda biz mos ravishda `bike1.name`va mulk `bike.gears`qiymatini o'zgartirish va kirish uchun va foydalandik `name`.`gears`

***

### Misol: Swift sinfi va ob'ektlari <a href="#example" id="example"></a>

```
// define a class
class Bicycle {

// define two properties
var name = ""
var gears = 0
}

// create instance of Person
var bike1 = Bicycle()

// access properties and assign new values
bike1.gears = 11
bike1.name = "Mountain Bike"

print("Name: \(bike1.name), Gears: \( bike1.gears) ")
```

**Chiqish**

```
Nomi: Tog'li velosiped, viteslar: 11
```

Yuqoridagi misolda biz `Bike`ikkita xususiyat bilan nomlangan sinfni aniqladik:nomivaviteslar.

Biz `bike1`sinfning ob'ektini ham yaratdik `Bike`.

Nihoyat, biz ob'ektning belgilaridan foydalanib, ob'ektning xususiyatlariga kirdik va o'zgartirdik `.`.

***

### Sinfning bir nechta ob'ektlarini yaratish <a href="#multiple" id="multiple"></a>

Bundan tashqari, bitta sinfdan bir nechta ob'ektlarni yaratishimiz mumkin. Misol uchun,

```
// define a class
class Employee {

// define a property
var employeeID = 0
}

// create two objects of the Employee class
var employee1 = Employee()
var employee2 = Employee()

// access property using employee1
employee1.employeeID = 1001
print("Employee ID: \(employee1.employeeID)")

// access properties using employee2
employee2.employeeID = 1002
print("Employee ID: \(employee2.employeeID)")
```

**Chiqish**

```
Xodim identifikatori: 1001
Xodim identifikatori: 1002
```

Yuqoridagi misolda biz ikkita ob'ektni va `employee1`sinfni yaratdik`employee2Employee`

**Eslatma:** Biz xohlagancha strukturaning ko'plab nusxalarini yaratishimiz mumkin.

***

### Swift sinfidagi funksiya <a href="#function" id="function"></a>

Biz Swift klassi ichidagi funksiyani ham belgilashimiz mumkin. Sinf ichida aniqlangan [Swift funksiyasi metod deyiladi.](https://www.programiz.com/swift-programming/functions)

Keling, bir misolni ko'rib chiqaylik,

```
// create a class
class Room {

  var length = 0.0
  var breadth = 0.0

  // method to calculate area
  func calculateArea() {
    print("Area of Room =", length * breadth)
  }
}

  // create object of Room class
  var studyRoom = Room()

  // assign values to all the properties 
  studyRoom.length = 42.5
  studyRoom.breadth = 30.8

  // access method inside class
  studyRoom.calculateArea()
```

**Chiqish**

```
Xona maydoni = 1309,0
```

Yuqoridagi misolda biz quyidagi nomli sinf yaratdik `Room`:

* **Xususiyatlari** :uzunligivakenglik
* **Usul** :`calculateArea()`

Bu erda biz sinf `studyRoom`nomidan ob'ekt yaratdik . `Room`Keyin biz ob'ektni xususiyatlarga qiymat berish uchun ishlatdik:uzunligivakenglik.

E'tibor bering, biz ob'ektdan sinf ichidagi usulni chaqirish uchun ham foydalanganmiz

```
room1.calculateArea()
```

Bu erda biz `.`usulni chaqirish uchun belgidan foydalandik. Nihoyat, usul ichidagi bayonot bajariladi.

***

### Swift Initializer <a href="#custom-initializer" id="custom-initializer"></a>

Ilgari biz sinf xususiyatiga standart qiymat tayinlagan edik.

```
class Bike {
  
  var name = ""
}
...

// create object
var bike = Bike()
```

Biroq, biz boshlang'ich yordamida qiymatlarni ishga tushirishimiz ham mumkin. Misol uchun,

```
class Bike {
  
  var name: String

  init(name: String){
  self.name = name
  }
}
```

Bu erda `init()`ning qiymatini belgilash uchun ishlatiladigan initsializatornomio'zgaruvchan. Biz ob'ektning xususiyatiga `self.name`murojaat qilish uchun foydalandik.`namebike1`

Agar biz sinf ichidagi qiymatlarni ishga tushirish uchun initsializatordan foydalansak, sinf ob'ektini yaratish jarayonida mos keladigan qiymatni o'tkazishimiz kerak.

```
var bike1 = Bike(name: "Mountain Bike")
```

Bu yerda,

* `"Mountain Bike"`ga uzatiladinomiparametriinit()
* `selfbike1`obyektni ifodalaydi
* `self.name`Mountain Velosipediga teng

***

#### Misol: Swift Initializer <a href="#example" id="example"></a>

```
class Bike {

  // properties with no default values
  var name: String
  var gear: Int

  // assign value using initializer
  init(name: String, gear: Int){
    self.name = name
    self.gear = gear
  }
}

// object of Person with custom initializer 
var bike1 = Bike(name: "BMX Bike", gear: 2)

print("Name: \(bike1.name) and Gear: \(bike1.gear)")
```

**Chiqish**

```
Nomi: BMX Bike and Gear: 2
```

Yuqoridagi misolda biz `Bike`ikkita xususiyatga ega `name`va nomli sinfni yaratdik `gear`.

Biz sinf xususiyatlariga qiymatlarni belgilash uchun moslashtirilgan ishga tushirgichdan foydalandik.

Nihoyat, sinf ob'ektini yaratishda `Bike`biz argument sifatida qiymatlarni `"BMX Bike"`va **2 ni o'tkazdik.**

***

### Swift-da Struct Vs Class

Struktura va sinfning ishlashi bir-biriga o'xshash bo'lsa ham, ular o'rtasida ba'zi katta farqlar mavjud.

1\. Sinf - ob'ektga yo'naltirilgan dasturlash tushunchasi. Shunday qilib, u mavjud sinfdan yangi sinfni olishimiz mumkin bo'lgan Meros kabi ba'zi OOP xususiyatlarini taqdim etadi.

Biroq, tuzilmalarni meros qilib olish mumkin emas.

Meros haqida ko'proq ma'lumot olish uchun [Swift Inheritance](https://www.programiz.com/swift-programming/inheritance) -ga tashrif buyuring .

2\. Sinflar mos yozuvlar turiga kiradi. Bu shuni anglatadiki, sinfning har bir nusxasi ma'lumotlarning bir xil nusxasini baham ko'radi. Misol uchun,

```
class Bike {
  var color: String

  init(color:String) {
    self.color = color
  }
}

var bike1 = Bike(color: "Blue")

var bike2 = bike1

bike1.color = "Red"
print(bike2.color)  // prints Red
```

Ko'rib turganingizdek, biz `bike1`ob'ektning rangini o'zgartirmoqdamiz. Biroq, rang `bike2`ob'ekt uchun ham o'zgartiriladi.

Boshqa tomondan, strukturalar qiymat turiga kiradi. Bu shuni anglatadiki, strukturaning har bir nusxasi ma'lumotlarning mustaqil nusxasiga ega bo'ladi. Misol uchun,

```
struct Bike {
  var color: String

  init(color:String) {
    self.color = color
  }
}

var bike1 = Bike(color: "Blue")

var bike2 = bike1

bike1.color = "Red"
print(bike2.color)  // prints blue
```

Ko'rib turganingizdek, biz `bike1`ob'ektning rangini o'zgartirmoqdamiz. Biroq, `bike2`ob'ektning rangi o'zgarmasdir.
