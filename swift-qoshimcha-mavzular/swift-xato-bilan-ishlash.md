# Swift xato bilan ishlash

Ushbu qo'llanmada biz misollar yordamida Swift xatolarini hal qilishni o'rganamiz.

Xato (istisno) - dasturni bajarish jarayonida yuzaga keladigan kutilmagan hodisa. Misol uchun,

```
var numerator = 10
var denominator = 0

// try to divide a number by 0
var result = numerator / denominator // error code
```

Bu erda biz raqamni ajratishga harakat qilamiz. Shunday qilib, bunday xatolik dasturning g'ayritabiiy tugatilishiga olib keladi.

***

### Swift-da xatolarni hal qilish uchun qadamlar <a href="#steps" id="steps"></a>

1. Xatolar turlarini ifodalovchi raqam yarating.
2. Kalit so‘z yordamida otish funksiyasini yarating `throws`.
3. Kalit so'z yordamida funktsiyani chaqiring `try`.
4. Kodni blokga o'rang va barcha xatolarni hal qilish uchun blokni `try`qo'shing `do {...}`.`catch {...}`

***

### 1. Xatolar sonini yarating <a href="#enum" id="enum"></a>

Swift-da biz dasturni yozishda duch kelishimiz mumkin bo'lgan xatolar turini ifodalovchi raqam yaratishimiz kerak.

Biz yaratgan enum `Error`protokolga mos kelishi kerak, shunda funksiya ichiga xato qiymatini chiqarishimiz mumkin.

Keling, bir misolni ko'rib chiqaylik,

```
enum DivisionError: Error {
  case dividedByZero
}
```

`DivisionError`Bu erda biz qiymat bilan nomli raqam yaratdik `dividedByZero`.

`DivisionError`Protokolga mos kelganligi sababli , `Error`biz endi enum xato qiymatini chiqarishimiz mumkin bo'ladi.

***

### 2. Otish funksiyasini yarating <a href="#throwing-function" id="throwing-function"></a>

Xatolarni tashlash uchun kalit so'z yordamida otish funksiyasini yaratishimiz kerak `throws`.

Keyin biz `throw`funktsiya ichidagi bayonotdan enum bilan ifodalangan ma'lum bir xatoni chiqarish uchun foydalanamiz. Misol uchun,

```
// create throwing function using throws keyword
func division(numerator: Int, denominator: Int) throws {

// throw error if divide by 0
  if denominator == 0 {
    throw DivisionError.dividedByZero
  }
  ...     
}
```

`division()`Bu erda biz kalit so'z yordamida nomlangan otish funktsiyasini yaratdik `throws`. Funktsiya enum if `dividedByZero`qiymatini chiqaradi`DivisionErrordenominator == 0`

Endi, funktsiya chaqiruvi vaqtida o'tkazilgan qiymatga asoslanib, agar xato sharti bajarilsa, funktsiya xatolik chiqaradi.

**Eslatma** : `throw`Kalit so'z kalit so'z bilan bir xil ta'sirga ega `return`. `return`funktsiyadan ba'zi qiymatlarni qaytaradi, funksiyadan esa `throw`xato qiymatini qaytaradi.

***

### 3. Sinab ko'ring kalit so'zdan foydalanib funksiya chaqiruvi <a href="#try" id="try"></a>

Swift-da biz `try`otish funksiyasini chaqirayotganda kalit so'zdan foydalanamiz. Bu funktsiya xatoga yo'l qo'yishi mumkinligini ko'rsatadi. Misol uchun,

```
// call throwing function using try keyword
try division(numerator: 10, denominator: 0)
```

Biroq, xatolarni qayta ishlash jarayoni hali ham to'liq emas. Agar dasturni hozir ishga tushirsak, xato xabarini olamiz:`An error was thrown and was not caught`

Shunday qilib, tashlangan xatoni ushlash uchun biz `do-catch`bayonotdan foydalanamiz.

***

### 4. Xatolarni do-catch bayonotidan foydalanish <a href="#do-catch" id="do-catch"></a>

Swift-da biz `try`kodni blokga o'ramiz va barcha xatolarni hal qilish uchun blokni `do`qo'shamiz . `catch`Misol uchun,

```
do {
  try division(numerator: 10, denominator: 0)
  ...
}

catch DivisionError.dividedByZero {
  // statement
}
```

Bu yerda biz blok `division()`ichidan otish funksiyasini chaqirdik va funksiya bitta tashlagan taqdirda xatolikni aniqlash uchun blokni `do`biriktirdik .`catch`

Yuqoridagi `catch`blok ning enum qiymati asosida bajariladi `DivisionError`.

Bu bizning dasturimizda yuzaga kelishi mumkin bo'lgan xatolarni hal qilishning oxirgi bosqichidir.

***

### Misol: Swift xatolik bilan ishlash <a href="#example" id="example"></a>

```
// create an enum with error values
enum DivisionError: Error {

  case dividedByZero
}

// create a throwing function using throws keyword
func division(numerator: Int, denominator: Int) throws {

  // throw error if divide by 0
  if denominator == 0 {
    throw DivisionError.dividedByZero
  }
    
  else {
    let result = numerator / denominator
    print(result)
  }
}

// call throwing function from do block
do {
  try division(numerator: 10, denominator: 0)
  print("Valid Division")
}

// catch error if function throws an error
catch DivisionError.dividedByZero {
  print("Error: Denominator cannot be 0")
}
```

**Chiqish**

```
Xato: maxraj 0 boʻlishi mumkin emas
```

Yuqoridagi misolda,

* `DivisionError`sanab hisoblanadi
* `division()`otish funksiyasi hisoblanadi
* `do-catch`bayonot xatoni hal qiladi

Biz `try`otish funksiyasiga qiymatlarni o'tkazish uchun foydalanganmiz

```
try division(numerator: 10, denominator: 0)
```

o'tkazilgan qiymatlar xato holatiga mos keladimi yoki yo'qligini tekshirish.

Agar xato holati bo'lsa

* **met** - otish funktsiyasi catch bloki tomonidan ushlangan xatoni chiqaradi.
* **bajarilmagan** - `else`otish funksiyasi ichidagi operator va blok `print`ichidagi bayonot `do`bajariladi.

***

### Xatolarni boshqarishni o'chirib qo'ying <a href="#disable" id="disable"></a>

Swift-da, ba'zida biz otish funktsiyasi ish vaqtida xatolikka yo'l qo'ymasligiga amin bo'lishimiz mumkin.

Bunday holda, biz `try!`funktsiyani chaqirish paytida xatolarni qayta ishlashni o'chirish uchun yozishimiz mumkin. Misol uchun,

```
enum DivisionError: Error {
  
  case dividedByZero
}

func division(numerator: Int, denominator: Int) throws {
  if denominator == 0 {
    throw DivisionError.dividedByZero
  }
    
  else {
    let result = numerator / denominator
    print("Result:", result)
  }
}

// disable error handling
try! division(numerator: 10, denominator: 5)
```

**Chiqish**

```
Natija: 2
```

Yuqoridagi misolda biz `try!`funktsiyani chaqirish paytida xatolarni qayta ishlashni o'chirish uchun foydalandik.

```
try! division(numerator: 10, denominator: 5)
```

Bu erda, chunki biz **5** qiymatini tayinladikmaxraj, dastur xatolikka yo'l qo'ymasligini bilamiz. Shunday qilib, biz xatolarni qayta ishlashni o'chirib qo'ydik.

Shuni ham yodda tutingki, biz dan foydalanganda , biz bayonotni `try!`ishlatishimiz shart emas .`do-catch`

**Eslatma** : Agar biz foydalansak `try!`va xatolik yuzaga kelsa, ilovamiz shunchaki ishdan chiqadi.

***

### Swift-da xatolik sabablari <a href="#causes" id="causes"></a>

Ko'p sabablarga ko'ra xatolik yuzaga kelishi mumkin. Ulardan ba'zilari:

* Foydalanuvchi kiritish noto‘g‘ri
* Qurilma xatosi
* Tarmoq ulanishining yo'qolishi
* Jismoniy cheklovlar (disk xotirasi yo'q)
* Kod xatolari
* Mavjud bo'lmagan fayl ochilmoqda

Xatolar dasturning bajarilishini g'ayritabiiy tarzda to'xtatganligi sababli, bunday xatolarni hal qilish muhimdir.
