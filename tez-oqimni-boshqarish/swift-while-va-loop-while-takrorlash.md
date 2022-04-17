# Swift while va loop while takrorlash

Ushbu o'quv qo'llanmada siz misollar yordamida while tsikli va takrorlash...while sikli haqida bilib olasiz.

Dasturlashda tsikllar kod blokini takrorlash uchun ishlatiladi. Misol uchun, agar siz xabarni 100 marta ko'rsatmoqchi bo'lsangiz, unda siz pastadirdan foydalanishingiz mumkin. Bu oddiy misol, siz halqalar yordamida ko'proq narsaga erishishingiz mumkin.

[Oldingi qo'llanmada siz Swift for-in Loop](https://www.programiz.com/swift-programming/for-in-loop) haqida bilib oldingiz . Bu erda siz looplar haqida bilib olasiz `while`.`repeat...while`

***

### Swift while Loop <a href="#while" id="while"></a>

Swift `while`loop ma'lum bir shart bajarilmaguncha ma'lum bir kodni ishlatish uchun ishlatiladi.

`while`Loop sintaksisi :

```
while (condition){
  // body of loop
}
```

Bu yerda,

* Qavs ichida `while`halqa baholaydi .`condition()`
* `condition`ga baholansa `true`, sikl ichidagi kod `while`bajariladi.
* `condition`yana baholanadi.
* Bu jarayon bo'lguncha davom `condition`etadi `false`.
* `condition`ga baholanganda , `false`tsikl to'xtaydi.

***

### while Loop sxemasi <a href="#flowchart-while" id="flowchart-while"></a>

![Swift-da while sikli qanday ishlaydi](https://cdn.programiz.com/cdn/farfuture/0xHV\_5ctjEVbHWRySw6v6257B3JsOrICthRNMx14pBA/mtime:1620036799/sites/tutorial2program/files/swift-while-loop.png)

#### 1-misol: Swift while Loop <a href="#example-while" id="example-while"></a>

```
// program to display numbers from 1 to 5

// initialize the variable
var i = 1, n = 5

// while loop from i = 1 to 5
while (i <= n) {
  print(i)
   i = i + 1
}
```

**Chiqish**

```
1
2
3
4
5
```

Mana dastur qanday ishlaydi.

| O'zgaruvchan                                    | Holati:`i <= n` | Harakat                                      |
| ----------------------------------------------- | --------------- | -------------------------------------------- |
| <p><code>i = 1</code><br><code>n = 5</code></p> | `true`          | `1`chop etiladi. **2**`i` gacha oshiriladi . |
| <p><code>i = 2</code><br><code>n = 5</code></p> | `true`          | `2`chop etiladi. **3**`i` gacha oshiriladi . |
| <p><code>i = 3</code><br><code>n = 5</code></p> | `true`          | `3`chop etiladi. **4**`i` ga oshiriladi .    |
| <p><code>i = 4</code><br><code>n = 5</code></p> | `true`          | `4`chop etiladi. **5**`i` ga oshiriladi .    |
| <p><code>i = 5</code><br><code>n = 5</code></p> | `true`          | `5`chop etiladi. **6**`i` ga oshiriladi .    |
| <p><code>i = 6</code><br><code>n = 5</code></p> | `false`         | Loop tugadi.                                 |

#### 2-misol: o'yin darajasini ko'rsatish uchun while loop

```
var currentLevel:Int = 0, finalLevel:Int = 5
let gameCompleted = true
while (currentLevel <= finalLevel) {

  if gameCompleted {
    print("You have passed level \(currentLevel)")
      currentLevel += 1
  }
}
print("Level Ends")
```

**Chiqish**

```
Siz 0-darajadan o'tdingiz                                                                                                                 
Siz 1-darajadan o'tdingiz                                                                                                                 
Siz 2-darajadan o'tdingiz                                                                                                                 
Siz 3-darajadan o'tdingiz                                                                                                                 
Siz 4-darajadan o'tdingiz                                                                                                                 
Siz 5-darajadan o'tdingiz                                                                                                                 
Darajaning tugashi     
```

Yuqoridagi misolda biz `while`joriy darajani tekshirish va uni konsolda ko'rsatish uchun pastadirdan foydalandik.

***

### takrorlang... while Loop <a href="#repeat-while" id="repeat-while"></a>

Loop bitta asosiy farq bilan halqaga `repeat...while`o'xshaydi . Test ifodasi tekshirilgunga qadar tsiklning `while`tanasi bir marta bajariladi.`repeat...while`

`repeat..while`Loop sintaksisi :

```
repeat {
  // body of loop
} while (condition)
```

Bu yerda,

* Dastlab tsiklning tanasi bajariladi. Keyin `condition`baholanadi.
* `condition`ga baholansa `true`, operator ichidagi sikl tanasi `repeat`yana bajariladi.
* `condition`yana bir bor baholanadi.
* `condition`Bu jarayon baholanmaguncha davom etadi `false`. Keyin tsikl to'xtaydi.

***

### Takrorlash sxemasi...while Loop <a href="#flowchart-repeat-while" id="flowchart-repeat-while"></a>

![Qanday qilib takrorlash mumkin ... while loop ishlaydi](https://cdn.programiz.com/cdn/farfuture/XI3OTMw9kXmOKDx7SxmFnxaJnBJlxNbIbrOuvXs9\_Zo/mtime:1620036791/sites/tutorial2program/files/swift-repeat-while-loop.png)

#### 3-misol: takrorlang... while Loop <a href="#example-repeat-while" id="example-repeat-while"></a>

```
// program to display numbers

var i = 1, n = 5

// repeat...while loop from 1 to 5
repeat {
  
  print(i)

  i = i + 1

} while (i <= n)
```

Yuqoridagi misolda dastlab va `i = 1`qiymati `n = 5`. Birinchi marta tsikl ichidagi operator shartni tekshirmasdan bajariladi. Vaziyat birinchi takrorlash tugagandan so'ng tekshiriladi.

Mana bu dastur qanday ishlaydi,

| O'zgaruvchan                                        | Holati:`i <= n` | Harakat                                      |
| --------------------------------------------------- | --------------- | -------------------------------------------- |
| <p><code>i = 1</code><br><code>n = 5</code><br></p> | tekshirilmagan  | `1`chop etiladi. **2**`i` gacha oshiriladi . |
| <p><code>i = 2</code><br><code>n = 5</code></p>     | `true`          | `2`chop etiladi. **3**`i` gacha oshiriladi . |
| <p><code>i = 3</code><br><code>n = 5</code></p>     | `true`          | `3`chop etiladi. **4**`i` ga oshiriladi .    |
| <p><code>i = 4</code><br><code>n = 5</code></p>     | `true`          | `4`chop etiladi. **5**`i` ga oshiriladi .    |
| <p><code>i = 5</code><br><code>n = 5</code></p>     | `true`          | `5`chop etiladi. **6**`i` ga oshiriladi .    |
| <p><code>i = 6</code><br><code>n = 5</code></p>     | `false`         | Loop tugadi.                                 |

***

### Infinite while Loop <a href="#infinite" id="infinite"></a>

Agar tsiklning **sharti** har `while`doim `true`bo'lsa, tsikl cheksiz vaqt davomida ishlaydi (xotira to'lguncha). **Bu cheksiz** `while` tsikl deb ataladi . Misol uchun,

```
while (true) {
    print("Endless Loop")
}
```

**Chiqish**

```
Cheksiz tsikl
Cheksiz tsikl
.
.
.
```

Bu erda shart har doim `true`. Shunday qilib, `while`tsikl cheksiz vaqt davomida ishlaydi.

***

### for vs while tsikli <a href="#difference" id="difference"></a>

`for-in`Loop odatda takrorlashlar soni ma'lum bo'lganda ishlatiladi . Misol uchun,

```
// this loop is iterated 5 times
for number in 1...5 {
   // body of loop
}
```

Biroq, `while`odatda, takrorlashlar soni noma'lum bo'lsa, tsikl ishlatiladi. Misol uchun,

```
while (condition) {
    // body of loop
}
```

**Eslatma:** ning ishlashi bilan `repeat...while`bir xil `while`. Demak, u iteratsiyalar soni noma'lum bo'lganda ham qo'llaniladi.
