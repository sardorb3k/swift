# Swift xususiyatlari

Ushbu qo'llanmada biz misollar yordamida Swift Property va uning turlari haqida bilib olamiz.

[Sinf yoki struktura ichida aniqlangan Swift o'zgaruvchisi yoki doimiysi](https://www.programiz.com/swift-programming/variables-constants-literals) xususiyatlar deyiladi. Misol uchun,

```
class Person {

  // define properties 
  var name: String = ""
  var age: Int = 0 

  ... 
}
```

Bu erda, `Person`sinf ichida biz ikkita xususiyatni aniqladik:

* nomi- `String`standart qiymatga ega turdagi`""`
* yoshi- `Int`standart qiymati **0 bo'lgan turdagi**

Xususiyatlar haqida bilishdan oldin , Swift-dagi [sinf](https://www.programiz.com/swift-programming/classes-objects) va [strukturaning](https://www.programiz.com/swift-programming/structs) ishlashini bilganingizga ishonch hosil qiling .

***

#### 1-misol: Swift xususiyatlari <a href="#example" id="example"></a>

```
class Person {

 // define two properties
 var name: String = ""
 var age: Int = 0
}

var person1 = Person()

// assign values to properties
person1.name = "Kevin"
person1.age = 42

// access properties
print("Name:", person1.name)
print("Age:", person1.age)
```

**Chiqish**

```
Ism: Kevin
Yosh: 42
```

Yuqoridagi misolda biz `Person`ikkita xususiyatga ega bo'lgan sinf yaratdik:nomivayoshi.

Bu erda biz ob'ektdan `person1`xususiyatlarga kirish uchun foydalandik:

* `person1.name`- kirishnomimulk
* `person1.age`- kirishyoshimulk

**Eslatma** : Yuqorida biz aniqlagan bu xususiyatlar, shuningdek, **saqlangan xususiyatlar**`Person` deb ataladi, chunki ular sinfning har bir namunasi uchun haqiqiy qiymatlarni saqlaydi .

***

### Tez hisoblangan mulk <a href="#computed" id="computed"></a>

Avvalroq biz har bir misol uchun qiymatni saqlaydigan saqlangan xususiyatlar haqida muhokama qildik. Misol uchun,

```
class Calculator {

  // define stored property
  var num1: Int = 0
  ... 
} 
```

Bu yerda,raqam 1saqlangan xususiyat bo'lib, u misol uchun ba'zi qiymatlarni saqlaydi `Calculator`.

**Biroq, hisoblangan xususiyatlar** deb ataladigan boshqa turdagi xususiyat mavjud . Saqlangan xususiyatdan farqli o'laroq, hisoblangan xususiyat qiymatni hisoblab chiqadi. Misol uchun,

```
class Calculator {
  ... 
   
  // define computed property
  var sum: Int {
    
    // calculate value
    num1 + num2
  }
}
```

Bu yerda,so'mqiymatni saqlamaydigan hisoblangan xususiyat bo'lib, u ikkita qiymat qo'shilishini hisoblaydi.

**Eslatma** : jingalak qavslar `{..}`hisoblangan xususiyatning tanasini bildiradi.

***

#### Misol: Swift Computed Property

```
class Calculator {

  // define two stored properties
  var num1: Int = 0
  var num2: Int = 0

  // define one computed property
  var sum: Int {

    // calculate value
    num1 + num2
  }
}

var obj = Calculator()
obj.num1 = 11
obj.num2 = 12

// read value of computed property 
print("Sum:", obj.sum)
```

**Chiqish**

```
Yig'indi: 23
```

Yuqoridagi misolda bizda bor

* Saqlangan xususiyatlar:raqam 1vasoni 2
* Hisoblangan mulk:so'm.

Bu erda hisoblangan xususiyatso'm`num1`va ning qo‘shilishini hisoblaydi`num2`

```
var sum: Int {

  // calculate value
  num1 + num2
}
```

Endi biz hisoblangan xususiyatga kirish orqali hisoblangan qiymatga kirishimiz mumkin

```
print("Sum:", obj.sum)
```

***

### Hisoblangan xususiyatlar uchun oluvchilar va sozlagichlar <a href="#getter-setter" id="getter-setter"></a>

Swift-da biz hisoblangan xususiyatga getter va setterni ham kiritishimiz mumkin.

* getter - hisoblangan qiymatni qaytaradi
* sozlagich - qiymatni o'zgartiradi

Keling, bir misolni ko'rib chiqaylik,

```
class Calculator {
  var num1: Int = 0
  var num2: Int = 0

  // create computed property
  var sum: Int {

    // retrieve value
    get {
      num1 + num2
    }
  
    // set new value to num1 and num2
    set(modify) {
      num1 = (modify + 10)
      num2 = (modify + 20)
    }
  }
}

var obj = Calculator()
obj.num1 = 20
obj.num2 = 50

// get value
print("Get value:", obj.sum)

// provide value to modify
obj.sum = 5

print("New num1 value:", obj.num1)
print("New num2 value:", obj.num2)

 
```

**Chiqish**

```
Qiymatni oling: 70
Yangi raqam 1 qiymati: 15
Yangi raqam 2 qiymati: 25
```

Yuqoridagi misolda biz nomli hisoblangan xususiyatni yaratdikso'm. Summa ichida bizda bor

**1. Getter** – yig‘indisini olmoqraqam 1vasoni 2

```
get {
  num1 + num2
}
```

**2. Sozlagich - num1 va num2 qiymatini o'zgartirish uchun**

```
set(modify) {
  num1 = (modify + 10)
  num2 = (modify + 20)
}
```

Bu erda sozlagich `modify`yangi qiymatlarni o'rnatish uchun ishlatilishi mumkin bo'lgan yangi qiymatga egaraqam 1vasoni 2.

Nihoyat, biz foydalandik,

* `obj.sum`- getterga kirish uchun
* `obj.sum = 5`- setterga kirish uchun

***

### Swift statik xususiyatlari <a href="#static" id="static"></a>

Oldingi misolda biz uning xususiyatlariga kirish uchun sinf ob'ektlaridan foydalanganmiz. Biroq, biz ob'ektlar yaratmasdan kirish va o'zgartirish mumkin bo'lgan xususiyatlarni ham yaratishimiz mumkin.

Ushbu turdagi xususiyatlar statik xususiyatlar deb ataladi. Swift-da biz `static`statik xususiyatni yaratish uchun kalit so'zdan foydalanamiz. Misol uchun,

```
class University {

  // static property 
  static var name: String = ""
  ...  
}
```

Bu yerda,nomistatik xususiyatdir. Endi statik xususiyatga kirish va uning qiymatini o'zgartirish uchun biz sinf nomidan foydalanamiz.

```
// modify value of the static property
University.name = "Kathmandu University"
```

***

#### Swift statik xususiyat <a href="#example-static" id="example-static"></a>

```
class University {

 // static property
 static var name: String = ""

 // non-static property
 var founded: Int = 0
}

// create an object of University class
var obj = University()

// assign value to static property
University.name = "Kathmandu University"
print(University.name)

// assign value to non-static property
obj.founded = 1991
print(obj.founded)
```

**Chiqish**

```
Katmandu universiteti
1991 yil
```

Yuqoridagi misolda bizda statik xususiyat mavjud:nomiva statik bo'lmagan xususiyat -asos solganBu yerda,

* `University.name`- sinf nomidan foydalanib statik xususiyatga kirish
* `obj.founded`- sinf ob'ekti yordamida statik bo'lmagan xususiyatga kirish

Statik xususiyat sinf turiga tegishli (ob'ekt bilan emas, balki sinf bilan bog'langan), shuning uchun biz ularga sinf nomlari yordamida kirishimiz mumkin.

**Eslatma** : Xuddi shunday, biz strukturada statik xususiyatlarni ham yaratishimiz mumkin. struktura ichidagi statik xususiyatlar struktura turiga ega, shuning uchun ularga kirish uchun struktura nomidan foydalanamiz.
