# Bog'langan qiymatlar bilan Swift enum

Ushbu qo'llanmada biz misollar yordamida Swift enumlarida bog'langan qiymatlar haqida bilib olamiz.

[Swift enum](https://www.programiz.com/swift-programming/enum) - da biz o'rnatilgan tegishli qiymatlar to'plamiga ega bo'lgan ma'lumotlar turini qanday aniqlashni o'rgandik.

Biroq, ba'zida biz raqam qiymatlariga qo'shimcha ma'lumot qo'shishni xohlashimiz mumkin. Enum qiymatlariga biriktirilgan ushbu qo'shimcha ma'lumotlar bog'langan qiymatlar deb **ataladi** .

Keling, bir misolni ko'rib chiqaylik,

```
enum Distance {
  
  // associate value 
  case km(String)
  ...
}
```

Bu erda `(String)`qiymatga qo'shimcha ma'lumot biriktirilgan `km`. ning qiymati `km`faqat a bo'lishi mumkinligini bildiradi `String`.

Endi biz bog'langan qiymatni enum qiymatiga qanday belgilashimiz mumkin.

```
Distance.km("Metric System")
```

Bu erda, `"Metric System"`qiymat bilan bog'liq `km`qiymat.

***

### Misol: Bog'langan qiymatlar bilan Swift enum <a href="#example" id="example"></a>

```
enum Distance {
  
  // associate value
  case km(String)
  case miles(String)
}

// pass string value to km
var dist1 = Distance.km("Metric System")
print(dist1)

// pass string value to miles
var dist2 = Distance.miles("Imperial System")
print(dist2)
```

**Chiqish**

```
km("Metrik tizim")
mil (“Imperatorlik tizimi”)
```

Yuqoridagi misolda biz nomli raqam yaratdikMasofaquyidagi bog'langan qiymatlar bilan:

* `"Metric System"km`qiymatga tayinlanadi .
* `"Imperial System"miles`qiymatga tayinlanadi .

***

### Bir nechta qiymatlarni bog'lash <a href="#multiple-values" id="multiple-values"></a>

Swift-da biz bir nechta qiymatlarni bitta enum qiymatiga bog'lashimiz mumkin. Misol uchun,

```
enum Marks {

 // associate multiple Double values
case gpa(Double, Double, Double)

// associate multiple String values
case grade(String, String, String)
}

// pass three Double values to gpa
var marks1 = Marks.gpa(3.6, 2.9, 3.8)
print(marks1)

// pass three string values to grade
var marks2 = Marks.grade("A", "B", "C")
print(marks2)
```

**Chiqish**

```
gpa(3,6, 2,9, 3,8)
daraja ("A", "B", "C")
```

Bu erda biz ikkita qiymatga ega bo'lgan raqam yaratdik: `gpa`va `grade`. Enum qiymatlariga e'tibor bering,

```
// associate multiple Double values
case gpa(Double, Double, Double)

// associate multiple String values
case grade(String, String, String)
```

Bu biz uchta `Double`va `String`qiymatlarni mos ravishda `gpa`va bilan bog'lashimiz kerakligini ko'rsatadi `grade`. Ushbu bog'langan qiymatlar [kortejlar](https://www.programiz.com/swift-programming/tuples) deb ham ataladi .

Shunday qilib, biz **3.6** , **2.9** , **3.8** ni biriktirdik `gpa`.

```
// pass three integer values to gpa
var marks1 = Marks.gpa(3.5, 2.9, 3.8)
```

Va, biz , `"A"`, `"B"`ga `"C"`biriktirdik `grade`.

```
// pass three string values to grade
var marks2 = Marks.grade("A", "B", "C")
```

***

### Nomlangan bog'liq qiymatlar <a href="#named" id="named"></a>

Swift-da biz kodimizni yanada o'qilishi uchun tegishli qiymatga nom berishimiz mumkin. Misol uchun,

```
enum Pizza {

  case small(inches: Int)
}
```

Bu erda biz nom berdikdyuymbog'langan qiymatga.

Buning o'rniga nomlangan bog'langan qiymatni o'qish mantiqiyroq bo'ladi

```
case small(Int)
```

***

#### Misol: Nomlangan bog'langan qiymatlar

```
enum Pizza {

  // named associated value
  case small (inches: Int)
  case medium (inches: Int)
  case large (inches: Int)
}

// pass value using provided names
var pizza1 = Pizza.medium(inches: 12)
print(pizza1)
```

**Chiqish**

```
o'rtacha (dyuym: 12)
```

Yuqoridagi misolda biz nom berdikdyuymbog'langan qiymatga.

Ishga bog'langan qiymatni o'tkazishda biz berilgan nomdan foydalandik,

```
Pizza.medium(inches: 12)
```

***

### enum Associated Values ​​va Switch bayonoti <a href="#switch" id="switch"></a>

Enum bilan bog'liq qiymatlarga mos kelish uchun biz [Swift switch bayonotidan foydalanishimiz mumkin. ](https://www.programiz.com/swift-programming/switch-statement)Misol uchun,

```
enum Mercedes {

 case sedan(height: Double)
 case suv(height: Double)
 case roadster(height: Double)
}

var choice = Mercedes.suv(height: 5.4)

switch(choice) {
 case let .sedan(height):
   print("Height:", height)

 case let .suv(height):
   print("Height:", height)

 case let .roadster(height):
   print("Height:", height)
}
```

**Chiqish**

```
Balandligi: 5.4
```

Yuqoridagi misolda biz `switch`enum bilan bog'liq qiymatlarga mos keladigan bayonotdan foydalanganmiz. Bayonotga e'tibor bering,

```
var choice = Mercedes.suv(height: 5.4)
```

Bu erda biz **5.4** ni biriktirdik `suv`va uni enum o'zgaruvchisiga tayinladiktanlash.

Keyin, biz foydalandiktanlash`switch`enum holatini har bir bayonotning qiymati bilan solishtirish uchun bayonot ichida `case`. Switch case bayonotiga e'tibor bering,

```
case let .suv(height):
```

Bu erda `let`bog'langan qiymatni bog'laydibalandligining tanasida foydalanishimiz mumkin bo'lgan o'zgaruvchi `case`.

Qiymat bilan mos kelganligi sababli `case let .suv`, ichidagi `case`operator bajariladi.

***

### Xom qiymatlar va bog'liq qiymatlar <a href="#raw-vs-associated" id="raw-vs-associated"></a>

Swift-da **xom qiymatlar** har bir enum qiymatiga taqdim etilgan oldindan belgilangan doimiy qiymatlardir. Misol uchun,

```
enum Vehicle: String {

  case car = "Four Wheeler"
  case bike = "Two Wheeler"
}
```

Bu erda biz xom qiymatlarni taqdim etdik: `"Four Wheeler"`va `"Two Wheeler"`to `car`va `bike`mos ravishda.

Biroq, **bog'langan qiymatlar** ko'proq enum qiymatlari bilan bog'langan o'zgaruvchilarga o'xshaydi. Misol uchun,

```
enum Marks {
  
  case grade(String)
  case gpa(Double)
}
```

Bu yerda `grade`va mos ravishda va turi `gpa`bilan bog'langan qiymatga ega bo'ling.`StringDouble`

Va biz o'zgaruvchini yaratishda bog'langan qiymatni enum qiymatiga belgilaymiz.

```
var marks = Marks.grade("A")
```

**Eslatmalar** :

1. Enum bir vaqtning o'zida ham xom qiymatlarga, ham tegishli qiymatlarga ega bo'lishi mumkin emas.
2. Enumning xom qiymatlari bir xil turdagi ma'lumotlarga ega bo'lishi kerak. Lekin bog'langan qiymatlar har qanday turdagi bo'lishi mumkin.
