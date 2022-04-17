# Tez yopilishlar

Ushbu qo'llanmada siz misollar yordamida Swift yopilishi haqida bilib olasiz.

Swiftda yopish funksiya nomisiz funksiyaning maxsus turi hisoblanadi. Misol uchun,

```
{
  print("Hello World")
}
```

Bu erda biz chop etadigan yopishni yaratdikSalom Dunyo.

Yopishlar haqida bilishdan oldin, [Swift funktsiyalari](https://www.programiz.com/swift-programming/functions) haqida bilib oling .

***

### Tez yopilish deklaratsiyasi <a href="#syntax" id="syntax"></a>

Biz `func`yopishni yaratish uchun kalit so'zdan foydalanmaymiz. Mana yopilishni e'lon qilish sintaksisi:

```
{ (parameters) -> returnType in
   // statements
}
```

Bu yerda,

1. **parametrlar** - yopilishga o'tgan har qanday qiymat
2. **returnType** - yopilish bilan qaytarilgan qiymat turini belgilaydi
3. **in** (ixtiyoriy) - **parametrlarni** / **returnType** ni yopish tanasidan ajratish uchun ishlatiladi

Keling, bir misolni ko'rib chiqaylik,

```
var greet = {
  print("Hello, World!")
}
```

Bu erda biz yopishni aniqladik va uni nomlangan o'zgaruvchiga tayinladik `greet`. Ichkariga ilova qilingan bayonot `{}`yopilish tanasidir.

Ushbu yopilishni amalga oshirish uchun biz uni chaqirishimiz kerak. Mana, biz yopilishni qanday chaqirishimiz mumkin

```
// call the closure
greet()
```

Yopish shunchaki matnni chop etadi `Hello World`.

**Eslatma** : Bu yopish parametrlari va qaytish turiga ega emas.

***

#### Misol: Tez yopilish

```
// declare a closure
var greet = {
  print("Hello, World!")
}

// call the closure
greet()
```

**Chiqish**

```
Salom Dunyo!
```

Yuqoridagi misolda biz yopishni aniqladik va uni nomlangan o'zgaruvchiga tayinladiksalomlashish.

Yopishni chaqirganimizda, yopilish `print()`ichidagi bayonot bajariladi.

***

### Yopish parametrlari <a href="#parameter" id="parameter"></a>

Funktsiyalarga o'xshab, yopilish ham parametrlarni qabul qilishi mumkin. Misol uchun,

```
// closure that accepts one parameter
let greetUser = { (name: String)  in
    print("Hey there, \(name).")
}

// closure call
greetUser("Delilah")
```

**Chiqish**

```
Salom, Delila.
```

`greetUser`Yuqoridagi misolda biz o'zgaruvchiga yopishni tayinladik .

Yopishning ichida, yopilish nomidagi turdagi parametrni `(name: String)`qabul qilishini bildiradi . `String`E'tibor bering, biz `in`yopish parametrini tana bilan ajratish uchun foydalanganmiz.

Shuningdek, yopilish chaqirig'iga e'tibor bering

```
greetUser("Delilah")
```

`"Delilah"`Bu erda biz yopilish uchun satr qiymatini o'tkazdik .

Va nihoyat, yopilish ichidagi bayonot bajariladi.

**Eslatma** : Funktsiyadan farqli o'laroq, biz parametr nomini eslatmasdan yopishni chaqiramiz.

***

### Qiymatni qaytaruvchi yopilish <a href="#return" id="return"></a>

Swift yopilishi qiymatni qaytarishi yoki qaytarmasligi mumkin. Agar biz yopilishimiz qandaydir qiymatni qaytarishini istasak, uning **qaytish turini** eslatib o'tishimiz va **return iborasidan** foydalanishimiz kerak . Misol uchun,

```
// closure definition
var findSquare = { (num: Int) -> (Int) in
  var square = num * num
  return square
}

// closure call
var result = findSquare(3)

print("Square:",result)
```

**Chiqish**

```
Kvadrat: 9
```

Yuqoridagi misolda biz raqamning kvadratini qaytaradigan yopishni aniqladik. Yopish ta'rifiga e'tibor bering,

```
var findSquare = { (num: Int) -> (Int) in
  ... 
  return square
}
```

Bu erda, `(num: Int) -> (Int)`yopilishini ko'rsatadi

* `(num: Int)`- butun son tipidagi parametrni bildiradi
* `-> (Int)`- Int tipidagi yopilish qaytish qiymatini ifodalaydi
* `return square`- yopilish ichidagi qaytarish bayonoti

Qaytarilgan qiymat `result`o'zgaruvchida saqlanadi.

***

### Funktsiya parametri sifatida yopilishlar <a href="#function-parameter" id="function-parameter"></a>

Swift-da biz yopishni parametr sifatida qabul qiladigan funksiya yaratishimiz mumkin.

```
// define a function
func grabLunch(search: () -> ()) {
  …
  // closure call
  search()  
}
```

Bu yerda,

* `search`- funksiya parametri
* `() -> ()`- yopilish turini ifodalaydi
* `search()`- funksiyaning ichki qismidan chaqiruvni yopish.

Endi ushbu funktsiyani chaqirish uchun biz uning argumenti sifatida yopishni o'tkazishimiz kerak

```
// function call
grabLunch(search: {
  print("Alfredo's Pizza: 2 miles away")
})
```

***

#### Misol: Funktsiya parametri sifatida yopish

```
// define a function and pass closure
func grabLunch(search: ()->()) {
  print("Let's go out for lunch")

  // closure call
  search()
}

// pass closure as a parameter
grabLunch(search: {
   print("Alfredo's Pizza: 2 miles away")
})
```

**Chiqish**

```
Ovqatlanish uchun tashqariga chiqaylik
Alfredo's Pizza: 2 mil uzoqlikda
```

***

### Yopish <a href="#trailing" id="trailing"></a>

Keyingi yopilishda, agar funktsiya yopishni oxirgi parametr sifatida qabul qilsa,

```
// function definition
func grabLunch(message: String, search: ()->()) {
  ...
}
```

Parametr nomini aytmasdan, funksiya tanasi sifatida yopishni o'tkazish orqali funktsiyani chaqirishimiz mumkin. Misol uchun,

```
// calling the function
grabLunch(message:"Let's go out for lunch")  {
  // closure body
}
```

Bu erda ichidagi hamma narsa `{...}`yopiq tanadir.

***

#### Misol: Yopish

```
func grabLunch(message: String, search: ()->()) {
   print(message)
   search()
}

// use of trailing closure
grabLunch(message:"Let's go out for lunch")  {
  print("Alfredo's Pizza: 2 miles away")
}
```

**Chiqish**

```
Keling, tushlikka chiqaylik
Alfredo's Pizza: 2 mil uzoqlikda
```

Yuqoridagi misolda `grabLunch()`funksiya yopishni qabul qiladi `search: () -> ()`. Bu erda yopish funksiyaning oxirgi parametridir.

Demak, biz yopilish argumentini funksiya taʼrifi sifatida berib, funksiyani chaqirdik.

```
grabLunch(message:"Let's go out for lunch")  {
  print("Alfredo's Pizza: 2 miles away")
}
```

***

### Avtomatik yopish <a href="#autoclosure" id="autoclosure"></a>

Funksiyani chaqirayotganda biz qavslardan foydalanmasdan ham yopishni o'tkazishimiz mumkin. `{}`Masalan,

```
// using {}
display(greet:{
  print("Hello World!")
}

// without using {}
display(greet: print("Hello World!"))
```

Yopish argumentini qavslarsiz o'tkazish uchun biz `@autoclosure`funktsiya ta'rifida kalit so'zdan foydalanishimiz kerak. Misol uchun,

```
func display(greet: @autoclosure () -> ()) {
 ...
}
```

Bu erda `@autoclosure`avtomatik ravishda jingalak qavslar qo'shiladi.

***

#### Misol: Avtomatik yopish

```
// define a function with automatic closure
func display(greet: @autoclosure () -> ()) {
 greet()
}

// pass closure without {}
display(greet: print("Hello World!"))
```

**Chiqish**

```
Salom Dunyo!
```

**Eslatma** : Biz argumentlarni avtoyopishga o'tkaza olmaymiz. Agar shunday qilishga harakat qilsak, xato xabarini olamiz: `argument type of @autoclosure parameter must be '()'`.
