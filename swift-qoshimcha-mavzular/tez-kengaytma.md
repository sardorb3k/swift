# Tez kengaytma

Ushbu qo'llanmada biz misollar yordamida Swift kengaytmalari haqida bilib olamiz.

Swift-da biz mavjud turlarga yangi funksiyalarni qo'shishimiz mumkin. **Bunga kengaytma** yordamida erishishimiz mumkin .

`extension`Kengaytmani e'lon qilish uchun kalit so'zdan foydalanamiz . Misol uchun,

```
// class definition 
class Temperature {
  ...
}

// extension of Temperature class
extension Temperature {

  // add new methods 
} 
```

Bu erda biz kalit so'z `Temperature`yordamida sinfning kengaytmasini yaratdik `extension`.

Endi kengaytma ichida biz ga yangi funksiya qo'shishimiz mumkin `Temperature`.

***

### Misol: Swift kengaytmasi <a href="#example" id="example"></a>

```
// class definition
class Temperature {
  var celsius: Double = 0

  func setTemperature(celsius: Double) {
    self.celsius = celsius
    print("Celsius:", celsius)
  }
}

// declare an extension
extension Temperature {

  // add a new method to Temperature class
  func convert() {
    var fahrenheit = (celsius * 1.8) + 32
    print("Fahrenheit:", fahrenheit)
  }
}

// class initialization
let temp1 = Temperature()
temp1.setTemperature(celsius: 16)

// access extension method using class object
temp1.convert()
```

**Chiqish**

```
Tselsiy: 16,0
Farengeyt: 60,8
```

Yuqoridagi misolda biz `Temperature`sinfning kengaytmasini yaratdik.

```
extension Temperature {

  // add a new method to Temperature class
  func convert() {
    var fahrenheit = (celsius * 1.8) + 32
    ...
  }
```

Ushbu kengaytma quyidagi xususiyatlarga qo'shiladi `Temperature`:

* `convert()`- oddiygina haroratni Selsiydan Farengeytga aylantiradigan usul.
* farengeyt`convert()`- konvertatsiya natijasini saqlaydigan ichida e'lon qilingan o'zgaruvchi .

Keyin nomli ob'ektni yaratdiktemp1ning `Temperature`, va uni ichida yaratilgan usulga kirish uchun ishlatgan `extension`.

```
// access extension method using class object
temp1.convert()
```

**Eslatma:** Sinf ichida aniqlangan xususiyatlar (masalanTselsiy bo'yicha) kengaytma ichida ham ishlatilishi mumkin.

***

### Kengaytmada hisoblangan mulk <a href="#computed-properties" id="computed-properties"></a>

**Swift-da biz saqlangan xususiyatlarni** kengaytmalarga qo'sha olmaymiz . Misol uchun,

```
extension Circle {
  // stored property
  var radius: Int // error code
}
```

Biroq, Swift bizga [hisoblangan xususiyatlarni](https://www.programiz.com/swift-programming/properties#computed) kengaytmaga qo'shish imkonini beradi. Misol uchun,

```
extension Circle {

  // computed property
  var area: Double {
    ...
  }
}
```

Bu yerda,hudud`extension`tanada aniqlangan hisoblangan xususiyatdir .

***

#### Misol: Kengaytmada hisoblangan mulk

```
class Circle {
  var radius: Double = 0
}

extension Circle {
  // define computed property 
  var area: Double {
    return 3.14 * radius * radius
  }
}

let circle1 = Circle()
circle1.radius = 5
print("Area:", circle1.area)
```

**Chiqish**

```
Maydoni: 78,5
```

&#x20;

Yuqoridagi misolda biz nomli hisoblangan xususiyatni aniqlagan sinfni `extension`yaratdik`Circle`hudud.

Bu xususiyat aylananing maydonini qiymatidan kelib chiqib hisoblab chiqadi `radius`.

```
var area: Double {
  return 3.14 * radius * radius
}
```

***

### Protokol kengaytmasi <a href="#protocol" id="protocol"></a>

_Swift-da biz protokollarni_ ham kengaytirishimiz mumkin . Misol uchun,

```
// protocol definition
protocol Brake {
  func applyBrake()
}

// extend protocol
extension Brake {
  func applyBrake() {
    print("Brake Applied")
  }
}

// define class that conforms Brake
class Car: Brake {
  var speed: Int = 0
}

let car1 = Car()
car1.speed = 61
print("Speed:", car1.speed)

// access extended protocol
car1.applyBrake()
```

**Chiqish**

```
Tezlik: 61
Tormoz qo'yilgan
```

Yuqoridagi misolda biz `Brake`funktsiyani belgilaydigan protokolni yaratdik `applyBrake()`.

Biz protokolni kengaytirdik va uning ichidagi funksiya `Brake`tanasini aniqladik .`applyBrake()`

```
// extend protocol
extension Brake {
  func applyBrake() {
    print("Brake Applied")
  }
}
```

Endi, chunki sinf protokolga `Car`mos keladi`Brake`

```
class Car: Brake {
  ...
}
```

yordamida kengaytirilgan protokolga kirishimiz mumkinavtomobil 1ob'ekt.

```
// access extended protocol
car1.applyBrake()
```
