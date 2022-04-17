# Tez meros

Ushbu o'quv qo'llanmada biz misollar yordamida Swift merosi va uning turlari haqida bilib olamiz.

Boshqa OOP tillari singari, Swift ham sinf merosi tushunchasini qo'llab-quvvatlaydi.

Meros bizga mavjud sinfdan yangi sinf yaratish imkonini beradi.

Yaratilgan yangi sinf **pastki sinf** (bola yoki hosila sinf) deb nomlanadi va bolalar sinfi olingan mavjud sinf **yuqori** sinf (ota yoki asosiy sinf) deb nomlanadi.

**Swift meros sintaksisi**

Swift-da biz `:`boshqa sinfdan sinfni meros qilib olish uchun ikki nuqtadan foydalanamiz. Misol uchun,

```
// define a superclass
class Animal {
  // properties and methods definition
}

// inheritance
class Dog: Animal {

  // properties and methods of Animal
  // properties and methods of Dog
}
```

Bu erda biz `Dog`pastki `Animal`sinfni supersinfdan meros qilib olamiz.

***

#### Misol: Swift Meros <a href="#example" id="example"></a>

```
class Animal {

  // properties and method of the parent class
  var name: String = ""

  func eat() {
    print("I can eat")
  }
}

// inherit from Animal
class Dog: Animal {

  // new method in subclass
  func display() {

    // access name property of superclass
    print("My name is ", name);
  }
}

// create an object of the subclass
var labrador = Dog()

// access superclass property and method 
labrador.name = "Rohu"
labrador.eat()

// call subclass method 
labrador.display()
```

**Chiqish**

```
Men yeyishim mumkin
Mening ismim Rohu
```

Yuqoridagi misolda biz kichik sinfni oldikItsuper sinfdanHayvon. Bayonotlarga e'tibor bering,

```
labrador.name = "Rohu"

labrador.eat()
```

Mana, biz foydalanamizlabrador(ob'ekti `Dog`) kirish uchunnomiva `eat()`sinfdan `Animal`. Bu mumkin, chunki quyi sinf yuqori sinfning barcha xossalari va usullarini meros qilib oladi.

Bundan tashqari, biz kirishga erishdiknomi`Dog`sinf usuli ichidagi xususiyat .

***

### - munosabatdir <a href="#is-a-relation" id="is-a-relation"></a>

Sviftda meros - **bu** munosabatlardir. Ya'ni, biz merosdan faqat ikkita sinf o'rtasida is-a munosabatlari mavjud bo'lganda foydalanamiz. Misol uchun,

1. **Avtomobil** - bu **avtomobil**
2. **Olma** - bu **meva**
3. **Mushuk** - **Hayvon**

Bu yerda, **Avtomobil Avtomobildan** , **Apple Mevadan** meros bo'lishi mumkin va hokazo.

***

### Swift merosida usulni bekor qilish <a href="#method-override" id="method-override"></a>

Oldingi misolda biz quyi sinf ob'ekti supersinf usuliga kirishi mumkinligini ko'rib turibmiz.

**Ammo, agar bir xil usul supersinfda ham, kichik sinfda ham mavjud bo'lsa-chi?**

Bunday holda, kichik sinfdagi usul yuqori sinfdagi usulni bekor qiladi. Ushbu kontseptsiya Swift-da usulni bekor qilish sifatida tanilgan.

Biz `override`kompilyatorga metodni bekor qilayotganimizni aytish uchun kalit so'zdan foydalanamiz.

#### Misol: Usulni bekor qilish

```
class Animal {

 // method in the superclass
 func eat() {
   print("I can eat")
 }
}

// Dog inherits Animal
class Dog: Animal {

  // overriding the eat() method
  override func eat() {
    print("I eat dog food")
  }
}

// create an object of the subclass
var labrador =  Dog()

// call the eat() method
labrador.eat()
```

**Chiqish**

```
Men it ovqatini iste'mol qilaman
```

Yuqoridagi misolda bir xil usul sinfda `eat()`ham, `Dog`sinfda ham mavjud `Animal`.

Endi biz subklass `eat()`ob'ekti yordamida usulni chaqirganimizda, sinfning usuli chaqiriladi.`DogDog`

Buning sababi, `eat()`pastki `Dog`sinf usuli yuqori sinfning bir xil usulini bekor qiladi `Animal`. `override`Usul bekor qilinganligini belgilash uchun kalit so'zdan foydalandik .

```
override func eat() {
  print("I eat dog food")
}
```

***

### Swift merosida super kalit so'z <a href="#super" id="super"></a>

Ilgari biz pastki sinfdagi bir xil usul superklassdagi usulni bekor qilishini ko'rdik.

Biroq, agar biz pastki sinfdan superklass usuliga kirishimiz kerak bo'lsa, biz `super`kalit so'zdan foydalanamiz. Misol uchun,

```
class Animal {

  // create method in superclass
  func eat() {
    print("I can eat")
  }
}

// Dog inherits Animal
class Dog: Animal {

  // overriding the eat() method
  override func eat() {

  // call method of superclass
  super.eat()
  print("I eat dog food")
  }
}

// create an object of the subclass
var labrador =  Dog()

// call the eat() method
labrador.eat()
```

**Chiqish**

```
Men yeyishim mumkin
Men it ovqatini iste'mol qilaman
```

Yuqoridagi misolda kichik sinf `eat()`usuli yuqori sinfning `Dog`bir xil usulini bekor qiladi `Animal`.

IchkaridaItsinf, biz foydalanganmiz

```
// call method of superclass
super.eat()
```

`eat()`usulini chaqirishHayvondan superklassItkichik sinf.

Shunday qilib, biz ob'ekt `eat()`yordamida usulni chaqirganimizda`labrador`

```
// call the eat() method
labrador.eat()
```

Usulning bekor qilingan va superklass versiyasi `eat()`bajariladi.

***

### Nega meros? <a href="#why" id="why"></a>

Merosning afzalliklarini tushunish uchun keling, vaziyatni ko'rib chiqaylik.

Aytaylik, biz kvadrat, beshburchak va boshqalar kabi oddiy ko'pburchaklar bilan ishlaymiz. Va, biz kirish asosida bu ko'pburchaklarning perimetrini topishimiz kerak.

**1.** Perimetrni hisoblash formulasi barcha muntazam ko'pburchaklar uchun umumiy bo'lganligi sababli, perimetrni hisoblash uchun `Polygon`sinf va usulni yaratishimiz mumkin `calculatePerimeter()`.

```
class RegularPolygon {


  calculatePerimeter() {
    // code to compute perimeter
  }
}
```

**2.** Va sinfdan meros `Square`va `Pentagon`sinflar `RegularPolygon`. Ushbu sinflarning har biri tomonlarning uzunligi va sonini saqlash uchun xususiyatlarga ega bo'ladi, chunki ular barcha ko'pburchaklar uchun farq qiladi.

```
class Square: RegularPolygon {

  var length = 0
  var sides = 0
}
```

Perimetrni hisoblash uchun va `length`ning qiymatini beramiz .`sidescalculatePerimeter()`

Shunday qilib, meros bizning kodimizni qayta foydalanish mumkin va intuitiv qiladi.

***

#### Misol: Merosning afzalliklari

```
import Foundation
class RegularPolygon {

 func calculatePerimeter(length: Int, sides: Int) {
   var result = length * sides
   print("Perimeter:", result )
 }
}

// inherit Square from Polygon
class RegularSquare: RegularPolygon {
 var length = 0
 var sides = 0

 func calculateArea() {
   var area = length * length
   print("Regular Square Area:", area)
 }
}

// inherit Pentagon from Polygon
class RegularTriangle: RegularPolygon {
 var length = 0.0
 var sides = 0.0

 func calculateArea() {
   var area = (sqrt(3)/4) * (length * length)
   print("Regular Triangle Area:", area)
 }
}
var shape = RegularSquare()
shape.length = 4
shape.calculateArea()
shape.calculatePerimeter(length: 3,sides:4)

var shape2 = RegularTriangle()
shape2.length = 2
shape2.calculateArea()
shape2.calculatePerimeter(length: 2,sides:3)
```

**Chiqish**

```
Oddiy kvadrat maydoni: 16
Perimetri: 12
Oddiy uchburchak maydoni: 1,7320508075688772
Perimetri: 6
```

Yuqoridagi misolda biz `RegularPolygon`muntazam ko'pburchakning perimetrini hisoblaydigan sinf yaratdik.

Bu yerda `RegularSquare`va `RegularTriangle`dan meros oladi `RegularPolygon`.

Muntazam ko'pburchakning parametrini hisoblash formulasi hamma uchun umumiydir, shuning uchun biz `calculatePerimeter()`yuqori sinf usulini qayta ishlatdik.

Va maydonni hisoblash formulasi turli shakllar uchun har xil bo'lgani uchun, biz maydonni hisoblash uchun kichik sinf ichida alohida usul yaratdik.
