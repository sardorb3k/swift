# Swift enum

Ushbu qo'llanmada biz misollar yordamida Swift enum (sanoqlash) haqida bilib olamiz.

Swift-da enum (hisoblashning qisqartmasi) foydalanuvchi tomonidan belgilangan tegishli qiymatlar to'plamiga ega bo'lgan ma'lumotlar turidir.

`enum`Enum yaratish uchun kalit so'zdan foydalanamiz . Misol uchun,

```
enum Season {
  case spring, summer, autumn, winter
}
```

Bu yerda,

* `Season`- raqam nomi
* `spring/summer/autumn/winter`- enum ichida aniqlangan qiymatlar

**Eslatma** : Enum qiymatlari **enum holatlari** deb ham ataladi . Va biz `case`kalit so'zni enum ichidagi qiymatlarni e'lon qilish uchun ishlatamiz.

***

### Enum o'zgaruvchilarni yarating <a href="#access" id="access"></a>

Enum ma'lumotlar turi bo'lgani uchun biz enum tipidagi o'zgaruvchilarni yaratishimiz mumkin. Misol uchun,

```
var currentSeason: Season
```

Bu erda `currentSeason`o'zgaruvchining `Season`turi. U faqat enum ichida mavjud qiymatlarni ( `spring`, `summer`, `autumn`, ) saqlashi mumkin.`winter`

#### Enum o'zgaruvchilarga qiymatlarni belgilang

`.`Enum o'zgaruvchisiga qiymatlarni belgilash uchun enum nomi va belgidan foydalanamiz. Misol uchun,

```
// assign summer to currentSeason variable
var currentSeason = Season.summer
```

Bu erda biz a'zo qiymatini `summer`enum o'zgaruvchisiga tayinladik `currentSeason`.

***

#### Misol: Swift enumeration

```
// define enum 
enum Season {
  
  // define enum values
  case spring, summer, autumn, winter
}

// create enum variable
var currentSeason: Season

// assign value to enum variable
currentSeason = Season.summer

print("Current Season:", currentSeason)
```

**Chiqish**

```
Joriy mavsum: yoz
```

Yuqoridagi misolda,

* `Season`- **4 ta** qiymatli raqam : `spring`, `summer`, `autumn`,`winter`
* `currentSeason`- enum tipidagi o'zgaruvchi
* `currentSeason = Season.summer`- enum qiymatini tayinlaydi`currentSeason`

**Eslatma** : O'zgaruvchilarga o'xshab, biz ham raqam o'zgaruvchilarini yaratishimiz va bitta satrda qiymat belgilashimiz mumkin. Misol uchun,

```
var lastSeason = Season.spring
```

***

### Swift enum Switch bayonoti bilan <a href="#switch" id="switch"></a>

[Swift da switch iborasi](https://www.programiz.com/swift-programming/switch-statement) bilan enumdan ham foydalanishimiz mumkin . Misol uchun,

```
enum PizzaSize {
  case small, medium, large
}

var size = PizzaSize.medium

switch(size) {
  case .small:
    print("I ordered a small size pizza.")

  case .medium:
    print("I ordered a medium size pizza.")

   case .large:
     print("I ordered a large size pizza.");
}
```

**Chiqish**

```
Men o'rta kattalikdagi pitsa buyurtma qildim.
```

Yuqoridagi misolda biz quyidagi `PizzaSize`qiymatlar bilan nomlanuvchi raqam yaratdik: `small`, `medium`, `large`. Bayonotga e'tibor bering,

```
var size = PizzaSize.medium
```

Bu erda biz `medium`enum o'zgaruvchisiga qiymatni tayinlaymiz `size`.

Biz bayonot `size`ichida enum o'zgaruvchisidan foydalandik. Va qiymat har bir bayonotning `switch`qiymati bilan taqqoslanadi .`case`

Qiymat bilan mos `case .medium`kelganligi sababli, ish ichidagi operator bajariladi.

***

### Enum holatlarini takrorlash <a href="#iterate" id="iterate"></a>

Swift-da biz `CaseIterable`sanabni takrorlash uchun protokoldan foydalanamiz. Misol uchun,

```
enum Season: caseIterable {
  ...
}
```

Endi biz `allCases`sanamning har bir holatini aylantirish uchun xususiyatdan foydalanishimiz mumkin.

```
for currentSeason in Season.allCases {
   ...
}
```

***

#### Misol: Enum holatlarini takrorlash

```
// conform Languages to caseIterable 
enum Season: CaseIterable {
  case spring, summer, autumn, winter 
}

// for loop to iterate over all cases
for currentSeason in Season.allCases {
  print(currentSeason)
}
```

**Chiqish**

```
bahor
yoz
kuz
qish
```

Yuqoridagi misolda biz `CaseIterable`protokolni enum bilan moslashtirdik `Season`.

Keyin sanamning har bir holatini takrorlash [uchun for tsikli](https://www.programiz.com/swift-programming/for-in-loop)`allCases` bilan xususiyatdan foydalanamiz.

***

### rawValue bilan tezkor raqamlashlar <a href="#values" id="values"></a>

Swift-da biz har bir enum holatiga qiymatlarni belgilashimiz mumkin. Misol uchun,

```
enum Size : Int {
  case small = 10
  case medium = 12
  ...
}
```

Bu yerda biz sanab holatlarga mos ravishda **29** va **31** qiymatlarini tayinladik . Ushbu qiymatlar **xom qiymatlar** deb ataladi .`smallmedium`

E'tibor bering, biz `Int`raqamlash holatlari faqat butun son xom qiymatlarini o'z ichiga olishi mumkinligini aniqlash uchun enum nomidan foydalanganmiz.

**Enum xom qiymatlariga kirish**

Enumning xom qiymatiga kirish uchun biz `rawValue`xususiyatdan foydalanamiz. Misol uchun,

```
// access raw value 
Size.small.rawValue
```

Bu erda biz `medium`ishning qiymatiga erishdik.

***

#### Misol: xom qiymatlari bilan sanab o'tish

```
enum Size : Int {
  case small = 10
  case medium = 12
  case large = 14
}

// access raw value of python case
var result = Size.small.rawValue
print(result)
```

**Chiqish**

```
10
```

Yuqoridagi misolda biz turning `Size`xom qiymatiga ega bo'lgan nomli raqamni yaratdik `Int`.

Bu erda biz mulkdan `small`foydalangan holda ishning qiymatiga erishdik.`rawValue`

**Eslatma** : Xom qiymatlar qatorlar, belgilar, butun sonlar yoki suzuvchi nuqtali raqamlar turlaridan iborat bo'lishi mumkin.

***

### Swift enum bog'langan qiymatlar <a href="#associated" id="associated"></a>

Swift-da biz qo'shimcha ma'lumotni enum ishiga qo'shishimiz mumkin. Misol uchun,

```
enum Laptop {
  
  // associate value 
  case name(String)
  ...
}
```

Mana, uchunnomiholda, biz a biriktira olamizStringturi qiymati.

Endi biz ishga tegishli qiymatni belgilashimiz mumkin.

```
Laptop.name("Razer")
```

Bu erda `Razer`ishning tegishli qiymati `name`.

***

#### Misol: bog'langan qiymatlarni sanab bering

```
enum Laptop {

  // associate string value
  case name(String)

  // associate integer value  
  case price (Int)
}

// pass string value to name
var brand = Laptop.name("Razer")
print(brand)

// pass integer value to price
var offer = Laptop.price(1599)
print(offer)
```

**Chiqish**

```
nomi ("Razer")
Narxi(1599)
```

Yuqoridagi misolda bog'langan qiymat

* `Razor`ishga tayinlanadi `name`.
* **1599** ish uchun tayinlangan `price`.

Bog'langan qiymatlar haqida ko'proq bilish uchun _Swift enum Associated Value_ ga tashrif buyuring.\
