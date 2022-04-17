# Swift funktsiyasi parametrlari va qaytish qiymatlari

Ushbu qo'llanmada biz misollar yordamida Swift-da funktsiya parametrlari va qaytariladigan qiymatlar haqida bilib olamiz.

### Swift funktsiyasi parametrlari <a href="#arguments" id="arguments"></a>

Funksiya parametri funksiya tomonidan qabul qilinadigan qiymatdir.

[Funksiya parametrlari va qaytariladigan qiymatlar haqida bilishdan oldin, Swift funksiyalari](https://www.programiz.com/swift-programming/functions) haqida bilishingizga ishonch hosil qiling .

Keling, bir misolni ko'rib chiqaylik,

```
func addNumbers(a: Int, b: Int) {
  var sum = a + b
  print("Sum:", sum)
}

addNumbers(a: 2, b: 3)
```

**Chiqish**

```
Jami: 5
```

Yuqoridagi misolda funksiya `addNumbers()`ikkita parametrni oladi: `a`va `b`. Chiziqqa e'tibor bering,

```
addNumbers(a: 2, b: 3)
```

Bu erda `a: 2, b: 3`parametrlarni belgilaydi `a`va mos ravishda **2** va **3**`b` qiymatlarni oladi.

**Eslatma** : Funksiya chaqiruvi davomida berilgan **2** va **3** qiymatlari argumentlar deb ham ataladi.

***

### Standart qiymatlar bilan funksiya parametri <a href="#default" id="default"></a>

Swift-da biz funktsiya parametrlariga standart qiymatlarni berishimiz mumkin.

`=`Standart qiymatlarni berish uchun operatordan foydalanamiz . Misol uchun,

```
func addNumbers( a: Int = 7,  b: Int = 8) {
  var sum = a + b
  print("Sum:", sum)
}

// function call with two arguments
addNumbers(a: 2, b: 3)

// function call with one argument
addNumbers(a: 2)

// function call with no arguments
addNumbers()
```

**Chiqish**

```
Jami: 5
Jami: 10
Jami: 15
```

Yuqoridagi misolda funksiya ta'rifiga e'tibor bering

```
func addNumbers(a: Int = 7, b: Int = 8) {
  ...
}
```

Bu erda biz a va b parametrlari uchun mos ravishda **7** va **8 standart qiymatlarini taqdim etdik.** Mana bu dastur qanday ishlaydi

**1. Raqamlarni qo‘shish(a: 2, b: 3)**

Har ikkala qiymat ham funktsiya chaqiruvi vaqtida uzatiladi. Shunday qilib, bu qiymatlar standart qiymatlar o'rniga ishlatiladi.

**2. qo'shimcha raqamlar (a: 2)**

`a`Funktsiya chaqiruvi vaqtida parametr uchun faqat bitta qiymat o'tkaziladi. Shunday qilib, parametr uchun standart qiymat ishlatiladi `b`.

**3. addNumbers()**

Funktsiya chaqiruvi davomida hech qanday qiymat o'tkazilmaydi. Demak, standart qiymat ikkala parametr uchun ham `a`ishlatiladi `b`.

***

### Argument yorlig'i bilan funksiya <a href="#argument-label" id="argument-label"></a>

Swift-da biz funktsiyani ifodali va jumlaga o'xshash tarzda aniqlash uchun argument belgilaridan foydalanishimiz mumkin. Misol uchun,

```
func sum(of a: Int, and b: Int) {
  ...
}
```

Bu yerda `sum()`funksiya argument belgilariga ega: `of`va `and`.

Funktsiyani chaqirishda parametr nomlari o'rniga argument yorlig'idan foydalanishimiz mumkin. Misol uchun,

```
sum(of: 2, and: 3)
```

Bu erda biz argument belgilaridan foydalangan holda **2** va **3**`sum()` qiymatlari bilan chaqiramiz.

***

#### Misol: Argument yorlig'i bilan funksiya

```
func sum(of a: Int, and b: Int) {
  print("Sum:", a + b)
}

sum(of: 2, and: 3)
```

**Chiqish**

```
Jami: 5
```

**Eslatma**`sum(of: 2, and: 3)` : Funktsiyani o'rniga deb chaqirish mantiqiyroq bo'ladi `sum(a: 2, b: 3)`.

***

### Argument teglarini o'tkazib yuboring <a href="#omit-label" id="omit-label"></a>

`_`Parametr nomidan oldin a ni yozib, argument yorlig'ini ham o'tkazib yuborishimiz mumkin . Misol uchun,

```
func sum(_ a: Int, _ b: Int) {
  print("Sum:", a + b)
}

sum(2, 3)
```

**Chiqish**

```
Jami: 5
```

**Eslatma:** Agar `_`parametr nomidan oldin foydalansak, u holda funksiyani argument belgisi yoki parametr nomisiz chaqirishimiz mumkin.

***

### Variadik parametrlarga ega funksiya <a href="#variadic" id="variadic"></a>

Ba'zan biz funktsiyaga uzatiladigan argumentlar sonini oldindan bilmaymiz. Bunday vaziyatni hal qilish uchun biz Swift-da variadik parametrlardan foydalanishimiz mumkin.

Variadik parametrlar bizga funktsiya chaqiruvi paytida har xil miqdordagi qiymatlarni o'tkazishga imkon beradi.

`...`Variadik parametrlarni belgilash uchun parametr turidan keyingi belgidan foydalanamiz . Misol uchun,

```
// program to find sum of multiple numbers 

func sum( numbers: Int...) {

  var result = 0
  for num in numbers {
    result = result + num
  }
  
  print("Sum = \(result)")
}

// function call with 3 arguments
sum(numbers: 1, 2, 3)

// function call with 2 arguments
sum (numbers: 4, 9)
```

**Chiqish**

```
Yig'indi = 6
Yig'indi = 13
```

Yuqoridagi misolda biz `sum()`variadik parametrlarni qabul qiluvchi funksiyani yaratdik. Chiziqlarga e'tibor bering,

```
sum(numbers: 1, 2, 3)

sum(numbers: 4, 9)
```

Bu erda biz bir xil funktsiyani turli argumentlar bilan chaqira olamiz.

**Eslatma** : Bir nechta qiymatlarni olgandan so'ng, `numbers`biz `for`har bir qiymatga kirish uchun tsikldan foydalanishimiz uchun massiv sifatida harakat qiling.

***

### Kirish parametrlari bilan funksiya <a href="#inout" id="inout"></a>

Funktsiya parametrini aniqlaganimizda, funktsiya parametrini funktsiya tanasi ichida o'zgartirib bo'lmaydi. Misol uchun,

```
func changeName(name: String) {
  if name == ""{
    // Cause Error
    name = "Ross"
  }
}
```

Bu erda yuqoridagi kod xatolik hosil qiladi: `Error: cannot assign to value: 'name' is a 'let' constant`. Buning sababi, parametr doimiy qiymat sifatida ishlaydi.

Buni bartaraf etish uchun biz parametrni parametr sifatida belgilashimiz kerak `inout`. Misol uchun,

```
func changeName(name: inout String) {
  if name == "Ross" {
      name = "Joey"
  }
}

var userName = "Ross"
print("Before: ", userName)

changeName(name: &userName)

print("After: ", userName)
```

**Chiqish**

```
Oldin: Ross
Keyin: Joey
```

Yuqoridagi misolda biz parametrni `changeName()`qabul qiluvchi funktsiyani e'lon qildik .`inoutname`

Inout parametrli funktsiyani chaqirayotganda, biz `ampersand(&)`argument sifatida o'zgaruvchi nomidan oldin belgidan foydalanishimiz kerak.

```
changeName(name: &userName)
```

Sahna ortida, in-out parametri funktsiyaga o'tkaziladigan, funktsiya tomonidan o'zgartiriladigan va asl qiymatni almashtirish uchun funktsiyadan tashqariga qaytariladigan qiymatga ega. Shuning uchun funktsiya chaqiruvida berilgan qiymat o'zgaruvchi bo'lishi kerak.

***

### Swift funktsiyasini qaytarish qiymatlari <a href="#return" id="return"></a>

Funktsiya qiymatni qaytarishi yoki qaytarmasligi mumkin. Agar funktsiyamiz qandaydir qiymat qaytarishini istasak, biz **return iborasidan** va **return type** dan foydalanamiz . Misol uchun,

```
func addNumbers(a: Int, b: Int) -> Int {
  var sum = a + b
  return sum
}

let result = addNumbers(a: 2, b: 3)

print("Sum:", result)
```

**Chiqish**

```
Jami: 5
```

Yuqoridagi misolda biz nomli funksiya yaratdik `addNumbers()`. Funktsiya ikkita raqam qo'shadi va ni qaytaradi `sum`.

```
return sum
```

Qaytarilgan qiymat `result`o'zgaruvchida saqlanadi.

***

### Bir nechta qiymatlarni qaytarish funksiyasi <a href="#multiple" id="multiple"></a>

Funktsiya bir nechta qiymatlarni ham qaytarishi mumkin. Misol uchun,

```
func checkMarks() -> (String, Int) {
  ...
  return (message, marks)
}
```

Bu erda return iborasi ikkita qiymatni qaytaradi:xabarvabelgilar.

Shuningdek, qaytish turini va ni `-> (String, Int)`belgilaydi . Va tartib bir xil bo'lishi kerak. Ya'ni, birinchi qaytarilgan qiymat satr, ikkinchisi esa butun son bo'lishi kerak.`messagemarks`

***

#### Misol: Ko'p qaytariladigan qiymatlar

```
func compute(number: Int) -> (Int, Int, Int) {

  var square = number * number

  var cube = square * number
  
  return (number, square, cube)
}

var result = compute(number: 5)

print("Number:", result.0)
print("Square:", result.1)
print("Cube:", result.2)
```

**Chiqish**

```
Raqam: 5
Kvadrat: 25
Kub: 125
```

Yuqoridagi misolda `compute()`funksiya raqamni qabul qiladi va sonning kvadrati va kubini hisoblaydi. Chiziqqa e'tibor bering,

```
return (number, square, cube)
```

Bu erda funktsiya bir vaqtning o'zida raqamni, uning kvadratini va kub qiymatini qaytaradi.

Qaytarilgan qiymatlar ichida saqlanadinatija. Bu yerda,natijabir nechta qiymatlarni saqlaydigan kortejdir. Qo'shimcha ma'lumot olish uchun [Swift Tuple](https://www.programiz.com/swift-programming/tuples) -ga tashrif buyuring .

Kortejdan individual qiymatlarga kirish uchun biz indeks raqamidan foydalanamiz. Shuning uchun **5** ni `result.0`qaytaradi , **25** ni qaytaradi va **125** ni qaytaradi .`result.1`

`results.2`
