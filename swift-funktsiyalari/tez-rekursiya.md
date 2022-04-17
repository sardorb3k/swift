# Tez rekursiya

Ushbu qo'llanmada biz Swift-dagi rekursiv funksiya va uning ishlashini misollar yordamida bilib olamiz.

O'zini chaqiradigan [funktsiya](https://www.programiz.com/swift-programming/functions) rekursiv funktsiya deb nomlanadi. Va bu texnika rekursiya sifatida tanilgan.

Jismoniy dunyo misoli ikkita parallel oynani bir-biriga qaratib qo'yishdir. Ularning orasidagi har qanday ob'ekt rekursiv tarzda aks ettiriladi.

***

### Swiftda rekursiyaning ishlashi <a href="#working" id="working"></a>

```
func recurse() {
  ... ...  
  recurse()
  ...  ...     
}

recurse()
```

Bu erda `recurse()`funktsiya o'zini qayta-qayta chaqiradi. Quyidagi rasmda rekursiya qanday ishlashi ko'rsatilgan.

![Tez rekursiya](https://cdn.programiz.com/cdn/farfuture/XAoZyQnKV7TXpegz5z3SEgw\_2hDTXk2sebkB6C23q2U/mtime:1622635027/sites/tutorial2program/files/swift-recursion.png)****

**Rekursiyani to'xtatish sharti**

Agar biz rekursiv chaqiruvni buzish uchun biron bir shartni eslatmasak, funktsiya o'zini cheksiz chaqirishda davom etadi.

Rekursiyani buzish uchun [if...else](https://www.programiz.com/swift-programming/if-else-statement) (yoki shunga o'xshash yondashuv) dan foydalanamiz.

Odatda, rekursiv funktsiya ikkita filialga ega:

* Rekursiv qo'ng'iroqlar uchun.
* Muayyan sharoitlarda qo'ng'iroqni buzish uchun boshqa.

Misol uchun,

```
func recurse() {

  if(condition) {
    // break recursive call
    recurse()
  }

  else {
    // recursive call
    recurse()
  }
}

// function call 
recurse()
```

***

#### 1-misol: Swift funksiyasining rekursiyasi

```
// program to count down number to 0

func countDown(number: Int) {

  // display the number
  print(number)

  // condition to break recursion
  if number == 0 {
  print("Countdown Stops")
  }

  // condition for recursion call
  else {
  
    // decrease the number value
    countDown(number: number - 1)
  }
}


print("Countdown:")
countDown(number:3)
```

**Chiqish**

```
Ortga hisoblash:
3
2
1
0
Ortga hisoblash to'xtaydi
```

Yuqoridagi misolda biz nomli rekursiv funksiya yaratdik `countDown()`. **Bu yerda funksiya unga berilgan raqam 0** ga aylanmaguncha o‘zini chaqiradi .

Qachonraqam**0** ga teng , `if`shart rekursiv chaqiruvni buzadi.

```
if number == 0 {
print(Countdown Stops)
}
```

**Dasturning ishlashi**

| Takrorlash | Funktsiya chaqiruvi | Chop etish | raqam == 0?                           |
| ---------- | ------------------- | ---------- | ------------------------------------- |
| 1          | `countDown(3)`      | **3**      | `false`                               |
| 2          | `countDown(2)`      | **2**      | `false`                               |
| 3          | `countDown(1)`      | **1**      | `false`                               |
| 4          | `countDown(0)`      | **0**      | `true`(funktsiya chaqiruvi to'xtaydi) |

***

### Misol: Sonning faktorialini toping <a href="#factorial" id="factorial"></a>

```
func factorial(num: Int) -> Int {

  // condition to break recursion
  if num == 0 {
    return 1
  } 

  // condition for recursive call
  else {
    return num * factorial(num: num - 1)
  }

}

var number = 3

// function call
var result = factorial(num: number)
print("The factorial of 3 is", result)
```

**Chiqish**

```
3 ning faktoriali 6 ga teng
```

Yuqoridagi misolda bizda ismli rekursiv funksiya mavjud `factorial()`. Bayonotga e'tibor bering

```
return num * factorial(num: num - 1)
```

Bu erda biz `factorial()`ning qiymatini kamaytirish orqali rekursiv chaqiramizsonparametr.

* Dastlab, qiymatisonichida **3** bo'ladi `factorial()`.
* Keyingi rekursiv qo'ng'iroqda,son**2** ga aylanadi .
* Xuddi shunday, jarayon qadar davom etadison0 ga aylanadi.
* Qachonson**0** ga teng , `if`shart rekursiv chaqiruvni buzadi.

**Dasturning ishlashi**

![Rekursiya yordamida faktorial hisoblash](https://cdn.programiz.com/cdn/farfuture/N1Hp\_f0\_AJyNoTZtMGsUudzziej2RFF6SfJVVxHumNA/mtime:1622635023/sites/tutorial2program/files/swift-factorial-working.png)

### Funksiya rekursiyasining afzalliklari va kamchiliklari

Quyida Swift dasturlashda rekursiyadan foydalanishning afzalliklari va kamchiliklari keltirilgan.

**1. Afzalliklar**

* Bu bizning kodimizni qisqartiradi va tozalaydi.
* Rekursiya ma'lumotlar tuzilmalari va ilg'or algoritmlar bilan bog'liq muammolarni hal qilishda talab qilinadi, masalan, Grafik va Tree Traversal.

**2. Kamchiliklari**

* Iterativ dastur bilan solishtirganda bu juda ko'p joy oladi.
* Bu ko'proq protsessor vaqtini sarflaydi.
* Ekvivalent iterativ dasturga nisbatan disk raskadrovka qilish qiyinroq bo'lishi mumkin.
