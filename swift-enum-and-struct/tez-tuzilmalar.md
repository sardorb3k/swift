# Tez tuzilmalar

Ushbu o'quv qo'llanmada siz Swift strukturasi haqida bilib olasiz va misollar yordamida struktura misollarini yaratishni ham o'rganasiz.

Swift-da struktura har xil turdagi ma'lumotlarning o'zgaruvchilarini saqlash uchun ishlatiladi. Misol uchun,

Aytaylik, biz odamning ismi va yoshini saqlamoqchimiz. Biz ikkita o'zgaruvchini yaratishimiz mumkin: ism va yosh va saqlash qiymati.

Biroq, biz bir nechta odamlarning bir xil ma'lumotlarini saqlamoqchimiz deylik.

Bunday holda, individual shaxs uchun o'zgaruvchilar yaratish zerikarli vazifa bo'lishi mumkin. Buni yengish uchun biz ism va yoshni saqlaydigan strukturani yaratishimiz mumkin. Endi bu tuzilma har bir kishi uchun ishlatilishi mumkin.

***

### Swift strukturasini aniqlang <a href="#define" id="define"></a>

Swift-da strukturani aniqlash uchun sintaksis:

```
struct StructureName {
  // structure definition 
}
```

Bu yerda,

* `struct`- strukturani aniqlash uchun ishlatiladigan kalit so'z
* `StructName`- strukturaning nomi

Keling, bir misolni ko'rib chiqaylik,

```
struct Person {

  var name = ""
  var age = 0
}
```

Bu erda biz nomli strukturani aniqladik `Person`. Jingalak qavslar ichida `{}`struktura ikkita o'zgaruvchini o'z ichiga oladinomivayoshiqiymatlari `""`va mos ravishda **0** bilan.

**Eslatma** : Struktura ichidagi o'zgaruvchilar va konstantalar xususiyatlar deyiladi.

***

### Struktura misollari <a href="#instance" id="instance"></a>

Struktura ta'rifi shunchaki rejadir. Strukturadan foydalanish uchun biz uning namunasini yaratishimiz kerak. Misol uchun,

```
struct Person {

  var name = " "
  var age = 0
}

// create instance of struct
var person1 = Person()
```

`Person`Bu erda biz strukturaning nomini va undan keyin standart ishga tushirgichni yozish orqali misol yaratdik`()`

Endi biz `person1`struktura xususiyatlariga kirish va o'zgartirish uchun misoldan foydalanishimiz mumkin. Misol uchun,

```
// modify the name property
person1.name = "Swift"

// access the age property
person1.age
```

Bu erda biz `.`struktura xususiyatlariga kirish uchun nuqta belgisidan foydalandik.

***

### Misol: Swift Access Struct Properties

```
// define a structure 
struct Person {

// define two properties
 var name = ""
 var age = 0
}

// create instance of Person
var person1 = Person()

// access properties and assign new values
person1.age = 21
person1.name = "Rick"

print("Name: \(person1.name) and Age: \( person1.age) ")
```

**Chiqish**

```
Ism: Rik va Yoshi: 21
```

Yuqoridagi misolda biz `Person`ikkita xususiyat bilan nomlangan strukturani aniqladik:nomivayoshi.

`person1`Shuningdek, biz strukturaning namunasini yaratdik `Person`.

Nihoyat, biz `.`notation yordamida misolning xususiyatlariga kirdik va o'zgartirdik.

***

### Misol: Structning bir nechta nusxalarini yarating

```
// define a structure
struct Student {

// define a property
var studentID = 0
}

// instance of Person
var student1 = Student()

// access properties and assign new values
student1.studentID = 101

print("Student ID: \(student1.studentID)")

// another instance of Person
var student2 = Student()

// access properties and assign new values
student2.studentID = 102

print("Student ID: \(student2.studentID)")
```

**Chiqish**

```
Talaba ID raqami: 101
Talaba ID raqami: 102
```

Yuqoridagi misolda biz ikkita misol `student1`va `student2`strukturani `Student`yaratdik

**Eslatma:** Biz xohlagancha strukturaning ko'plab nusxalarini yaratishimiz mumkin.

***

### Swift Memberwise Initializer <a href="#initializer" id="initializer"></a>

Ilgari biz struktura xususiyatiga standart qiymatni tayinlagan edik.

```
struct Person {
  
  var name = ""
}
```

Biz standart ishga tushirgich yordamida namuna yaratdik.

```
var person1 = Person()
```

Biroq, agar biz struct xususiyatiga standart qiymat bermasak.

```
struct Person {
  
  var name: String
}
```

Biz misol yaratishda qiymatni o'tkazamiz

```
var person1 = Person(name: "Kyle")
```

Bu erda qavs ichidagi qiymatlar strukturaning `()`mos keladigan xususiyatlariga avtomatik ravishda tayinlanadi. Bu a'zolar bo'yicha ishga tushiruvchi deb ataladi.

**Eslatma** : Struktura xususiyatiga standart qiymat tayinlagan bo'lsak ham, biz a'zolar bo'yicha ishga tushirgichdan ham foydalanishimiz mumkin.

***

#### Misol: Memberwise Initializer

```
struct Person {

// properties with no default values
var name: String
var age: Int
}

// instance of Person with memberwise initializer  
var person1 = Person(name: "Kyle", age: 19)

print("Name: \(person1.name) and Age: \( person1.age)")
```

**Chiqish**

```
Ismi: Kayl va yoshi: 19
```

Yuqoridagi misolda biz strukturaning namunasini `person1`yaratdik `Person`.

Xususiyatlarga standart qiymatlarni belgilamaganimiz sababli, qiymatlarni belgilash uchun a'zolar bo'yicha ishga tushirgichdan foydalanamiz.

***

### Swift Struct ichidagi funksiya <a href="#function" id="function"></a>

Swift strukturasida funksiyani ham belgilashimiz mumkin. Struktura ichida aniqlangan funksiya metod deyiladi.

Keling, bir misolni ko'rib chiqaylik,

```
struct Car {

  var gear = 0

  // method inside struct
  func applyBrake(){
  print("Applying Hydraulic Brakes")
  }
}

// create an instance 
var car1 = Car()

car1.gear = 5

print("Gear Number: \(car1.gear)")
// access method
car1.applyBrake()
```

**Chiqish**

```
Gidravlik tormozlarni qo'llash
```

Yuqoridagi misolda biz strukturaning `applyBraking()`ichida nomlangan usulni aniqladik `Car`. Usulga kirishga e'tibor bering,

```
car1.applyBrake()
```

Bu erda biz `.`strukturaning ichida belgilangan usulga kirish uchun notatsiyadan foydalandik. Nihoyat, usul ichidagi bayonot bajariladi.
