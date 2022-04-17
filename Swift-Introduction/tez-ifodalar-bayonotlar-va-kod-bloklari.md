# Tez ifodalar, bayonotlar va kod bloklari

Ushbu maqolada siz Swift ifodalari, bayonotlari va bloklari haqida bilib olasiz.

### Tez ifodalar <a href="#expressions" id="expressions"></a>

[Ifoda o'zgaruvchilar](https://www.programiz.com/swift-programming/variables-constants-literals) , [operatorlar](https://www.programiz.com/swift-programming/operators) , [harflar](https://www.programiz.com/swift-programming/variables-constants-literals) va [funksiyalarning](https://www.programiz.com/swift-programming/functions) birikmasidir . Misol uchun,

```
// assign value to marks
var marks = 80

// compare num1 and num2
var result = (num1 == num2)
```

Bu erda ifodalar:

* `var marks = 80`- biz **80** ga belgilaganimizni bildiradi`marks`
* `num1 == num2`- solishtiradi `num1`va`num2`

***

### Tez bayonotlar <a href="#statements" id="statements"></a>

Bayonotlar muayyan vazifani bajarish uchun ko'rsatmalardir. Misol uchun,

```
print("Hello World")
```

Bu erda biz kompyuterga matnni ko'rsatishni buyurish uchun **chop etish bayonotidan**`"Hello World"` foydalandik .

Swift-da uchta bayonot turi mavjud:

#### 1. Oddiy bayonotlar

Oddiy bayonot ifoda yoki bayonotdan iborat. Misol uchun,

```
var score = 9 * 5
```

Bu erda, o'zgaruvchiga natijasini `var score = 9 * 5`tayinlaydigan bayonot .`9 * 5score`

Oddiy iboralar Swift-dagi eng keng tarqalgan bayonot turlaridir. Biz ilgari ishlatgan **bosma gap ham oddiy gaplarga misoldir.**

***

#### 2. Shartli gaplar

Shartli bayonot faqat ma'lum shartlar bajarilganda ma'lum bir kod blokini bajarishga imkon beradi. Misol uchun,

```
var age = 25

if (age > 18) {
  print("Can Vote")
}
```

Yuqoridagi misolda **shartli**`if (age > 18)` bayonot **mavjud** . Bu yerda, agar shart bo'lsa , chop etish operatori bajariladi . `age > 18true`

Shartli gaplarning ikki turi mavjud:

* [agar ... boshqacha bayonot](https://www.programiz.com/swift-programming/if-else-statement)
* [almashtirish bayonoti](https://www.programiz.com/swift-programming/switch-statement)

***

#### 3. Loop bayonotlari

Loop bayonotlari bizga kod blokini qayta-qayta bajarishga imkon beradi. Misol uchun,

```
// create a loop statement
for i in 1...3 {
    print("Hello, World!")
}
```

**Chiqish**

```
Salom Dunyo!
Salom Dunyo!
Salom Dunyo!
```

Yuqoridagi misolda biz **for loop iborasidan foydalanganmiz:** `for i in 1...3` . **U chop etish bayonotini 3** marta bajaradi .

Swift-da uch turdagi aylanma bayonotlar mavjud.

* [for-in tsikli](https://www.programiz.com/swift-programming/for-in-loop)
* [while tsikli](https://www.programiz.com/swift-programming/repeat-while-loop)
* [while tsiklini takrorlang](https://www.programiz.com/swift-programming/repeat-while-loop#repeat-while)

**Eslatma:** `1...3` Swift-dagi diapazonni ifodalaydi. [Batafsil ma’lumot olish uchun Swift Ranges](https://www.programiz.com/swift-programming/ranges) -ga tashrif buyuring .

***

### Swift kod bloklari <a href="#blocks" id="blocks"></a>

Kod bloki - bu jingalak qavslar ichiga olingan bayonotlar guruhi (nol yoki undan ko'p) `{ }`. Misol uchun,

```
if true { // start of block
	
let sum = 2+3
print("Result is \(sum)")

} // end of block
```

Bu erda kod bloki ikkita bayonotdan iborat:

* `let sum = 2+3`
* `print("Result is \(sum)")`
