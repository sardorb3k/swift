# Swift Overriding usullari va xususiyatlari

Ushbu qo'llanmada biz misollar yordamida Swift-da xususiyat va usullarni bekor qilish haqida bilib olamiz.

[Swift Inheritance](https://www.programiz.com/swift-programming/inheritance) - da pastki sinf yuqori sinfning usullari va xususiyatlarini meros qilib oladi. Bu pastki sinflarga superklass a'zolariga bevosita kirish imkonini beradi.

Endi, agar yuqori sinfda ham, kichik sinfda ham bir xil usul aniqlangan bo'lsa, u holda kichik sinfning usuli yuqori sinf usulini bekor qiladi. Bu bekor qilish deb nomlanadi.

Usulning bekor qilinishini e'lon qilish uchun `override`kalit so'zdan foydalanamiz. Misol uchun,

```
class Vehicle {
  
  func displayInfo(){
    ... 
  }
}

class Car: Vehicle {
  
  // override method
  override func displayInfo() {
    ... 
  }   
} 
```

Bu erda, `displayInfo()`usuliAvtomobilpastki sinf ning bir xil usulini bekor qiladiTransport vositasisupersinf.

***

### Misol: Swift usulini bekor qilish <a href="#method-overriding" id="method-overriding"></a>

```
class Vehicle {

  // method in the superclass
  func displayInfo() {
    print("Four Wheeler or Two Wheeler")
  }
}

// Car inherits Vehicle
class Car: Vehicle {

  // overriding the displayInfo() method
  override func displayInfo() {
    print("Four Wheeler")
  }
}

// create an object of the subclass
var car1 =  Car()

// call the displayInfo() method
car1.displayInfo()
```

**Chiqish**

```
To'rt g'ildirakli
```

Yuqoridagi misolda biz `displayInfo()`yuqori sinf usulini bekor qilamizTransport vositasipastki sinf ichidaAvtomobil.

```
// inside the Car class 
override func displayInfo() {
  print("Four Wheeler")
}
```

Bu erda biz `override`bekor qilingan usulni belgilash uchun kalit so'zdan foydalandik.

`displayInfo()`Endi ob'ekt yordamida usulni chaqirganimizdaavtomobil 1ningAvtomobil,

```
car1.displayInfo()
```

kichik sinf ichidagi usul deyiladi.

![Swift usulini bekor qilish](https://cdn.programiz.com/cdn/farfuture/ykHrcDlMcBnJy7T5lzKEjotMST\_\_8RmJS3wVvRgkIGQ/mtime:1626423162/sites/tutorial2program/files/swift-method-overriding.png)Usulni bekor qilishning ishlashi

Buning sababi, `displayInfo()`usuliAvtomobilpastki sinf ning bir xil usulini bekor qiladiTransport vositasisupersinf.

***

### Swift-da bekor qilingan usulga kirish <a href="#access-overridden" id="access-overridden"></a>

Subklassdan supersinf usuliga kirish uchun biz `super`kalit so'zdan foydalanamiz. Misol uchun,

```
class Vehicle {

  // method in the superclass
  func displayInfo() {
    print("Vehicle: Four Wheeler or Two Wheeler")
  }
}

// Car inherits Vehicle
class Car: Vehicle {

  // overriding the displayInfo() method
  override func displayInfo() {

    // access displayInfo() of superclass
    super.displayInfo()
    print("Car: Four Wheeler")
  }
}

// create an object of the subclass
var car1 =  Car()

// call the displayInfo() method
car1.displayInfo()
```

**Chiqish**

```
Avtomobil: to'rt g'ildirakli yoki ikki g'ildirakli
Avtomobil: to'rt g'ildirakli
```

Yuqoridagi misolda, `displayInfo()`usuliAvtomobilpastki sinf ning bir xil usulini bekor qiladiTransport vositasisupersinf.

`displayInfo()`-ning ichidaAvtomobil, biz foydalanganmiz

```
// call method of superclass
super.displayInfo()
```

`displayInfo()`usulini chaqirishTransport vositasi

`displayInfo()`Shunday qilib, biz yordamida usulni chaqirganimizdaavtomobil 1ob'ekt

```
// call the displayInfo() method
car1.displayInfo()
```

usullarning bekor qilingan va superklass versiyasi `displayInfo()`bajariladi.

***

### Usulni bekor qilishni oldini olish <a href="#prevent" id="prevent"></a>

Swift-da biz usulni bekor qilishning oldini olishimiz mumkin.

Usulni bekor qilib bo'lmaydigan qilish uchun biz `final`superklassdagi usulni e'lon qilishda kalit so'zdan foydalanamiz. Misol uchun,

```
class Vehicle {

  // prevent overriding
  final func displayInfo() {
    print("Four Wheeler or Two Wheeler")
  }
}

// Car inherits Vehicle
class Car: Vehicle {

  // attempt to override
  override func displayInfo() {
    print("Four Wheeler")
  }
}

// create an object of the subclass
var car1 =  Car()

// call the displayInfo() method
car1.displayInfo()
```

Yuqoridagi misolda biz `displayInfo()`superklassdagi usulni sifatida belgilab oldik `final`.

Usul deb e'lon qilingandan so'ng `final`, biz uni bekor qila olmaymiz. Yakuniy usulni bekor qilishga harakat qilganimizda,

```
override func displayInfo() {
  print("Four Wheeler")
```

biz xato xabarini olamiz: `error: instance method overrides a 'final' instance method`.

***

### Swift xususiyatlarini bekor qilish <a href="#property" id="property"></a>

[Swift-da biz hisoblangan xususiyatlarni](https://www.programiz.com/swift-programming/properties#computed) bekor qilishimiz mumkin . Misol uchun,

```
class University {

  // computed property
  var cost: Int {
  return 5000
 }
}

class Fee: University {
 // override computed property
 override var cost: Int {
 return 10000
 }
}

var amount = Fee()

// access fee property
print("New Fee:", amount.cost)
```

**Chiqish**

```
Yangi to'lov: 10000
```

Yuqoridagi misolda biz superklass ichida hisoblangan xususiyatni yaratdikUniversitet. Subklass ichidagi kodga e'tibor beringHaq,

```
override var cost: Int {
  return 10000 
} 
```

Biz hisoblangan xususiyatni bekor qilamizxarajat. Endi, biz kirganimizdaxarajatob'ektdan foydalanadigan xususiyatmiqdoriningHaq,

```
// access fee property
amount.cost
```

kichik sinf ichidagi xususiyat deyiladi.

**Eslatma** : Swift-da saqlangan xususiyatlarni bekor qila olmaymiz. Misol uchun,

```
class A {
  // stored property
  var num = 0
}

class B: A {
  // overriding stored property 
  override var num = 2    // Error Code
}
```
