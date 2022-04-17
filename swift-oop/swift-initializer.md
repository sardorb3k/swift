# Swift Initializer

Ushbu o'quv qo'llanmada biz misollar yordamida Swift ishga tushirgich va uning turi haqida bilib olamiz.

Initsializer - bu sinf yoki strukturaning ob'ektini yaratish uchun ishlatiladigan maxsus turdagi funksiya.

Swift-da biz `init()`initsializator yaratish usulidan foydalanamiz. Misol uchun,

```
class Wall {
  ...

  // create an initializer 
  init() {
    // perform initialization
    ... 
  }
} 
```

Bu erda usul `init()`sinfning initsializatoridirDevor.

***

### Misol: Swift Initializer <a href="#example1" id="example1"></a>

```
// declare a class
class  Wall {
  var length: Double

  // initializer to initialize property
  init() {
    length = 5.5
    print("Creating a wall.")
    print("Length = ", length)
  }
}

// create an object
var wall1 = Wall()
```

**Chiqish**

```
Devor yaratish.
Uzunlik = 5,5
```

Yuqoridagi misolda biz nomli ishga tushirgich yaratdik `init()`. Initsializator ichida biz qiymatini ishga tushirdikuzunligimulk.

Quyidagi bayonotga e'tibor bering:

```
// create an object
var wall1 = Wall()
```

Mana, qachondevor 1obyekt yaratiladi, `init()`initsializator chaqiriladi. Va, qiymatiuzunligixususiyat **5,5** ga ishga tushiriladi .

***

### Parametrlangan boshlang'ich <a href="#parameterized" id="parameterized"></a>

Swift ishga tushirgichi bir yoki bir nechta parametrlarni ham qabul qilishi mumkin. Bunday initsializatorlar parametrli initsializatorlar (parametrli initsializatorlar) deb nomlanadi.

Keling, bir misolni ko'rib chiqaylik,

```
class Wall {
  
  var length: Double
  ...
  
  // initializer with parameter
  init(length: Double) {

    self.length = length
  } 
}

// create an object
var wall1 = Wall(length: 10.5)
```

Bu yerda,

* `init(length: Double)`- parametr bilan ishga tushirgichuzunligi
* `var wall1 = Wall(length: 10.5)`- parametrga **10,5 qiymatini o'tkazish**uzunligi
* `self.length = length`- qiymatini belgilaydiuzunligiparametr ( **10.5** ) gauzunligimulk
* `self.length`- belgilanguzunligixususiyat joriy ob'ekt bilan bog'langandevor 1

***

### Misol: Parametrlashtirilgan initializer <a href="#example2" id="example2"></a>

```
// declare a class
class Wall {
  var length: Double
  var height: Double

  // parameterized initializer to initialize properties
  init(length: Double, height: Double) {
    self.length = length
    self.height = height
  }

  func calculateArea() -> Double {
    return length * height
  }
}

// create object and initialize data members
var wall1 = Wall(length: 10.5, height: 8.6)
var wall2 = Wall(length: 8.5, height: 6.3)

print("Area of Wall 1: ", wall1.calculateArea())
print("Area of Wall 2: ", wall2.calculateArea())
```

**Chiqish**

```
1-devorning maydoni: 90,3
2-devorning maydoni: 53,55
```

Yuqoridagi misolda biz `init()`ikkita parametrli ishga tushirgich yaratdik:uzunligivabalandligi. Ifodalarga e'tibor bering,

```
var wall1 = Wall(length: 10.5, height: 8.6)
var wall2 = Wall(length: 8.5, height: 6.3)
```

Bu erda ob'ektni yaratishdaDevorsinf, biz a'zolar xususiyatlari uchun qiymatlarni argument sifatida o'tkazamiz.

A'zo o'zgaruvchilari shu tarzda ishga tushirilganda, endi `calculateArea()`usul bilan devor maydonini hisoblashimiz mumkin.

***

### Initializer haddan tashqari yuklanishi <a href="#init-overloading" id="init-overloading"></a>

[Swift Initializers funksiyani haddan tashqari yuklash](https://www.programiz.com/swift-programming/function-overloading) kabi haddan tashqari yuklanishi mumkin .

Initsializatorni haddan tashqari yuklashda ikki yoki undan ortiq initsializatorlar turli xil parametrlar yoki parametrlar soniga ega bo'lsa, bir xil nomga ega bo'lishi mumkin.

Va ob'ektni yaratishda o'tkazilgan argumentlarga asoslanib, mos keladigan ishga tushiruvchi chaqiriladi.

Keling, bir misolni ko'rib chiqaylik,

```
class Person {
  var age: Int

  // 1. initializer with no arguments
  init() {
    age = 20
  }

  // 2. initializer with an argument
  init(age: Int) {
    self.age = age
  }

  // method to return age
  func getAge() -> Int {
    return age
  }
}

var person1 = Person()
var person2 = Person(age: 23)

print("Person1 Age:", person1.getAge())
print("Person1 Age:", person2.getAge())
```

**Chiqish**

```
Odam 1 Yosh: 20
Odam 1 Yosh: 23
```

Yuqoridagi misolda biz sinf yaratdikShaxsbu yagona xususiyatga egayoshi.

Shuningdek, biz ikkita boshlang'ichni aniqladik: `init()`va `init(age: Int)`.

1. Biz hech qanday argument o'tkazmadikshaxs 1ob'ekt, shuning uchun birinchi initsializator chaqiriladi. Demak,yoshi**20** ga ishga tushiriladi .
2. Biz argument sifatida **23 dan o'tdik**shaxs2. Shunday qilib, ikkinchi ishga tushirgich va deb ataladiyoshi**23** ga ishga tushiriladi .

Usul `getAge()`qiymatini qaytaradiyoshi, va biz undan yoshni chop etish uchun foydalanamizshaxs 1vashaxs2.

***

### Swift qulaylik Initializer <a href="#convenience" id="convenience"></a>

Oldingi misollarda biz belgilagan initsializator sinfning asosiy initsializatorlari edi. Ushbu birlamchi ishga tushirgichlar, shuningdek, **belgilangan ishga tushirgichlar** deb ataladi .

**Biroq, biz qulaylik ishga tushiruvchisi** deb nomlangan sinf uchun ikkilamchi/qo'llab-quvvatlovchi ishga tushirgichni ham belgilashimiz mumkin .

Qulaylik ishga tushirgichni aniqlash uchun biz `convenience`initsializatordan oldin kalit so'zdan foydalanamiz. Misol uchun,

```
class University {
  
  var name : String
  var rank : String
  
  init(name : String, rank: String) {
    self.name = name
    self.rank = rank
  }

  // define convenience init  
  convenience init() {
    self.init(name: "Kathmandu University", rank: "1st")
  }
  
}

var university1 = University()
print(university1.name)
print("Rank:", university1.rank)
```

**Chiqish**

```
Katmandu universiteti
O'rin: 1
```

Yuqoridagi misolda biz belgilangan ishga tushirgichni yaratdik: `init()`va qulaylik ishga tushirgich: `convenience init()`.

Qulaylik initsializatori ichida biz belgilangan ishga tushirgichni chaqirdik va xususiyatlar uchun qiymatlarni tayinladik.

```
convenience init() {
  self.init(name: "Kathmandu University", rank: "1st")
}
```

Qachonuniversitet 1ob'ekt yaratiladi, qulaylik ishga tushirgichi chaqiriladi.

```
// using convenience initializer
var university1 = University() 
```

Bu bizning kodimizni belgilangan boshlang'ichni chaqirish bilan solishtirganda toza ko'rinishga olib keladi:

```
// call designated initializer
var university1 = University(name: "Kathmandu University", rank: "1st") 
```

**Eslatma** : Qulaylik Initializers saqlangan xususiyatlarga standart qiymatlarni belgilashda foydalidir.

***

### Initializer muvaffaqiyatsiz tugadi <a href="#failable" id="failable"></a>

Ba'zi hollarda initsializatorlar ishlamasligi yoki ishlamasligi mumkin, bu muvaffaqiyatsiz ishga tushirgich deb ataladi.

`(?)`Kalit so'zdan keyin savol belgisini qo'yib, muvaffaqiyatsiz ishga tushirgichni yozamiz `init`va `nil`agar biror narsa noto'g'ri bo'lsa, uni qaytaramiz. Misol uchun,

```
class File {

  var folder: String

  // failable initializer
  init?(folder: String) {

    // check if empty
    if folder.isEmpty {
      print("Folder Not Found") // 1st output
      return nil
    }
    self.folder = folder
  }
}

// create folder1 object
var file  = File(folder: "")
if (file != nil) {
  print("File Found Successfully")
}
else {
  print("Error Finding File") // 2nd output
}
```

**Chiqish**

```
Jild topilmadi
Faylni topishda xato
```

Yuqoridagi misolda biz `init?()`nomli parametr bilan muvaffaqiyatsiz ishga tushirgichni yaratdikpapka.

Va biz `if`bayonot va `isEmpty`mulkdan foydalandik

```
if (folder.isEmpty) { return nil }
```

mavjudligini tekshirish uchunpapka`nil`bo'sh va bo'sh bo'lsa qaytib keladi .

Uchunjild 1ob'ektni ishga tushirishda xatolikka olib keladigan bo'sh satrni o'tkazdik `""`, shuning uchun avval uning ichidagi bayonot bajariladi va keyin u qaytadi `nil`.

Va nihoyat, blok ichidagi bayonot `else`bajariladi

***

### Strukturalar uchun a'zolar bo'yicha initializer <a href="#memberwise" id="memberwise"></a>

Swift-da biz strukturalar bilan ishlashda initsializator yaratishimiz shart emas. Swift biz uchun avtomatik ravishda a'zo yaratadi. Misol uchun,

```
struct Person {
  
  var name: String
  var age: Int
}
```

Bu erda biz hech qanday boshlang'ich yaratmadikShaxstuzilishi. Biroq, Swift auto biz uchun a'zolar bo'yicha ishga tushirgichni yaratadi,

```
var person1 = Person(name: "Dwight", age: 43)
```

Bu erda qavs ichidagi qiymatlar strukturaning `()`mos keladigan xususiyatlariga avtomatik ravishda tayinlanadi. Bu a'zolar bo'yicha ishga tushiruvchi deb ataladi.

***

#### Misol: Memberwise Initializer

```
struct Person {

  // define two properties  
  var name: String
  var age: Int
}

// object of Person with memberwise initializer  
var person1 = Person(name: "Dwight", age: 43)

print("Name:", person1.name)
print("Age:", person1.age)
```

**Chiqish**

```
Ism: Duayt
Yosh: 43
```

Yuqoridagi misolda biz avtomatik ravishda yaratilgan a'zolar bo'yicha boshlang'ichdan foydalandik.Shaxstuzilishi.

```
var person1 = Person(name: "Dwight", age: 43)
```

Bu erda, qiymatinomiga o'rnatiladi `Dwight`vayoshi**43** ga o'rnatiladi .
