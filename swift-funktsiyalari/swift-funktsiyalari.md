# Swift funktsiyalari

Ushbu qo'llanmada biz misollar yordamida Swift funktsiyasi va funksiya ifodalari bilan tanishamiz.

Funksiya ma'lum bir vazifani bajaradigan kod blokidir.

Aylana hosil qilish va uni ranglash uchun dastur yaratishimiz kerak deylik. Bunday holda biz ikkita funktsiyani yaratishimiz mumkin:

1. aylana chizish funksiyasi
2. doirani rang berish funktsiyasi

Shunday qilib, funktsiya kodimizni qayta foydalanish va tushunish oson qilish uchun dasturimizni kichikroq qismlarga ajratishga yordam beradi.

Swift-da funksiyaning ikki turi mavjud:

* **Foydalanuvchi tomonidan belgilangan funktsiya** - Biz o'z talablarimiz asosida o'z funktsiyalarimizni yaratishimiz mumkin.
* **Standart kutubxona funktsiyalari** - Bu Swift-da foydalanish mumkin bo'lgan o'rnatilgan funktsiyalardir.

Keling, avvalo foydalanuvchi tomonidan belgilangan funksiyalar haqida bilib olaylik.

***

### Swift funktsiyasi deklaratsiyasi <a href="#declaration" id="declaration"></a>

Funktsiyani e'lon qilish sintaksisi:

```
func functionName(parameters)-> returnType {
  // function body 
}
```

Bu yerda,

* **func** - funktsiyani e'lon qilish uchun ishlatiladigan kalit so'z
* **functionName** - funktsiyaga berilgan har qanday nom
* **parametrlar** - funktsiyaga berilgan har qanday qiymat
* **returnType** - funksiya tomonidan qaytarilgan qiymat turini belgilaydi

Keling, bir misolni ko'rib chiqaylik,

```
func greet() {
print("Hello World!")
}
```

Bu erda biz nomli funktsiyani yaratdik `greet()`. Bu shunchaki matnni chop etadi `Hello World!`.

Bu funksiya hech qanday parametr va qaytish turiga ega emas. Qaytish turi va parametrlari haqida keyinroq ushbu qo'llanmada bilib olamiz.

***

### Swift-da funktsiyani chaqirish <a href="#calling" id="calling"></a>

Yuqoridagi misolda biz nomli funktsiyani e'lon qildik `greet()`.

```
func greet() {
  print("Hello World!")
}
```

Endi ushbu funktsiyadan foydalanish uchun biz uni chaqirishimiz kerak.

`greet()`Funktsiyani Swift -da qanday chaqirishimiz mumkin .

```
// call the function
greet()
```

***

### Misol: Swift funktsiyasi

```
// declare a function
func greet() {
  print("Hello World!")
}

// call the function
greet()

print("Outside function")
```

**Chiqish**

```
Salom Dunyo!
Tashqi funktsiya
```

Yuqoridagi misolda biz nomli funksiya yaratdik `greet()`. Dastur qanday ishlaydi:

![Swift funktsiyasi](https://cdn.programiz.com/cdn/farfuture/tz2qUGiqAjzBFfyGQ6qXBvJwAYUqFKBJPc6SdGBZr-4/mtime:1622110248/sites/tutorial2program/files/swift-function-example1.png)Swift-da funksiyalarning ishlashi

Bu yerda,

1. Funktsiya chaqirilganda, dasturni boshqarish funktsiya ta'rifiga o'tadi.
2. Funktsiya ichidagi barcha kodlar bajariladi.
3. Dasturni boshqarish funktsiya chaqiruvidan keyin keyingi gapga o'tadi.

***

### Funktsiya parametrlari <a href="#parameter" id="parameter"></a>

Yuqorida aytib o'tilganidek, funktsiya parametrlarga ham ega bo'lishi mumkin. Parametr - bu funktsiya tomonidan qabul qilingan qiymat. Misol uchun,

```
// function with two parameters
func addNumbers(num1: Int, num2: Int) {
  var sum = num1 + num2
  print("Sum: ",sum)
}

// function with no parameter
func addNumbers() {
  // code
}
```

Parametrlar bilan funksiya yaratadigan bo'lsak, ularni chaqirishda mos keladigan qiymatlarni o'tkazishimiz kerak. Misol uchun,

```
// function call with two values
addNumbers(num1: 3, num2: 4)

// function call with no value
addNumbers()
```

Bu yerda,1 raqami: 3, son2: 4parametrlarini belgilaydiraqam 1vasoni 2**mos ravishda 3** va **4** qiymatlarini oladi.

**Eslatma** : Funktsiya parametrlari haqida ko'proq ma'lumot olish uchun [Swift Function Parameters](https://www.programiz.com/swift-programming/function-parameter-return-values) ga tashrif buyuring .

***

### Misol: Funksiya parametrlari

```
// function that adds two numbers
func addNumbers(num1: Int, num2: Int) {
  var sum = num1 + num2
  print("Sum: ", sum)
}

// calling function with two values
addNumbers(num1: 3, num2: 4)
```

**Chiqish**

```
Jami: 7
```

Yuqoridagi dasturda biz parametrlar bilan nomlangan funksiya yaratdik `addNumbers()`:raqam 1vasoni 2.

![Funktsiya parametrlari](https://cdn.programiz.com/cdn/farfuture/h2Z5dWlk45MLX9C53ZNNG5NU6JxZmpbkI\_uhvvM-y0o/mtime:1622110254/sites/tutorial2program/files/swift-function-parameter.png)Funksiyaning parametrlar bilan ishlashi

**Eslatma:** Funktsiya parametrining ma'lumotlar turi har doim funktsiya chaqiruvi paytida uzatilgan ma'lumotlarga mos kelishi kerak. `num1`Bu erda va ma'lumotlar turi `num2`, `Int`shuning uchun biz funktsiya chaqiruvi paytida **3** va **4 butun son qiymatlarini o'tkazdik.**

***

### Swift funktsiyasini qaytarish turi <a href="#return" id="return"></a>

Swift funktsiyasi qiymatni qaytarishi yoki qaytarmasligi mumkin. Agar funktsiyamiz qandaydir qiymat qaytarishini istasak, biz **return iborasidan** foydalanishimiz mumkin . Misol uchun,

```
func addNumbers() -> Int {
  ...
  return sum
}
```

Bu erda biz o'zgaruvchini qaytaramizso'm. Funktsiya `-> Int`ta'rifidagi funktsiyaning qaytish turi butun son ekanligini bildiradi.

Agar funktsiya har qanday qiymatni qaytarsa, qiymatning qaytish turi funktsiya ta'rifida ko'rsatilishi kerak ( **-> returnType** ). Aks holda, xatolik yuzaga keladi.

***

### Misol: Funktsiyani qaytarish turi

```
// function definition
func findSquare (num: Int) -> Int {
  var result = num * num
  return result
}

// function call
var square = findSquare(num: 3)

print("Square:",square)
```

**Chiqish**

```
Kvadrat: 9
```

Yuqoridagi misolda biz nomli funksiya yaratdik `findSquare()`. Funktsiya raqamni qabul qiladi va raqamning kvadratini qaytaradi.

![Qaytish qiymatlari bilan funksiya](https://cdn.programiz.com/cdn/farfuture/IYonY4e32JqYtKjU8d8\_dEq8xVhofBHItS8x99x0YTY/mtime:1622110258/sites/tutorial2program/files/swift-function-return.png)Swift funksiyasining qaytish qiymatlari bilan ishlashi

***

### Misol: Ikki raqam qo'shing

```
// function that adds two numbers
func addNumbers(num1: Int, num2: Int) -> Int {
  var sum = num1 + num2
  return sum
}

// calling function with two values
var result = addNumbers(num1: 3, num2: 4)

print("Sum: ", result)
```

**Chiqish**

```
Yig'indi = 7
```

***

### Swift Library funktsiyalari <a href="#library" id="library"></a>

Swift-da standart kutubxona funktsiyalari to'g'ridan-to'g'ri dasturimizda ishlatilishi mumkin bo'lgan o'rnatilgan funktsiyalardir. Misol uchun,

* `print()`- qo'shtirnoq ichidagi satrni chop etadi
* `sqrt()`- sonning kvadrat ildizini qaytaradi
* `pow()`- raqamning kuchini qaytaradi

Ushbu kutubxona funktsiyalari ramka ichida aniqlanadi. Va ulardan foydalanish uchun biz dasturimizga ramkani kiritishimiz kerak.

Masalan, `sqrt()`va ramka `pow()`ichida aniqlanadi .`Foundation`

***

### Misol: Swift Library funksiyasi

```
import Foundation

// sqrt computes the square root
var squareRoot = sqrt(25)

print("Square Root of 25 is",squareRoot)

// pow() comptes the power
var power = pow(2, 3)

print("2 to the power 3 is",power)
```

**Chiqish**

```
25 ning kvadrat ildizi 5,0 ga teng
2 ning kuchi 3 ga teng 8 ga teng
```

Yuqoridagi misolda biz foydalandik

* `sqrt(25)`**- 25** ning kvadrat ildizini hisoblash
* `pow(2, 3)`- sonning kuchini, ya'ni **2 3 ni hisoblaydi**

Mana, bayonotga e'tibor bering,

```
import Foundation
```

`sqrt()`Kutubxona ichida va `pow()`ular aniqlanganligi sababli , `Foundation`biz uni dasturimizga kiritishimiz kerak.

***

### Funksiyalardan foydalanishning afzalliklari <a href="#benefits" id="benefits"></a>

**1. Kodni qayta** ishlatish mumkin - biz dasturimizda bir xil funktsiyadan bir necha marta foydalanishimiz mumkin, bu bizning kodimizni qayta ishlatishga imkon beradi. Misol uchun,

```
// function definition
 func getSquare(num: Int) -> Int{
   return num * num
 }

for i in 1...3{

  // function call
  var result = getSquare(num: i)
  print("Square of \(i) =",result)
}
```

**Chiqish**

```
1 ning kvadrati = 1
2 ning kvadrati = 4
Kvadrat 3 = 9
```

Yuqoridagi dasturda `getSquare()`sonning kvadratini hisoblash uchun nomli funksiya yaratdik. **Bu erda funktsiya 1** dan **3** gacha bo'lgan raqamlarning kvadratini hisoblash uchun ishlatiladi .

Shunday qilib, bir xil usul qayta-qayta qo'llaniladi.

**2. Kodni** o'qish imkoniyati - Funktsiyalar dasturimizni o'qilishi va tushunarli qilish uchun kodimizni bo'laklarga bo'lishimizga yordam beradi.
