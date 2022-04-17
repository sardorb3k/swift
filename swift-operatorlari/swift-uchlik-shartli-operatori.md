# Swift uchlik shartli operatori

Ushbu maqolada siz dasturni boshqarish oqimini o'zgartirish uchun shartli yoki uchlik operatordan foydalanishni o'rganasiz.

`if...else`Muayyan stsenariylarda bayonotni almashtirish uchun uchlik operatoridan foydalanish mumkin .

Uchlik operatori haqida bilishdan oldin, [Swift if...else bayonoti](https://www.programiz.com/swift-programming/if-else-statement) haqida bilib oling .

***

### Swiftda uchlik operator <a href="#ternary" id="ternary"></a>

Uchlik operator shartni baholaydi va shart asosida kod blokini bajaradi. Uning sintaksisi

```
condition ? expression1 : expression2
```

Bu yerda uchlik operator `condition`va ni baholaydi

* agar **rost bo'lsa** , `condition`bajariladi .`expression1`
* agar `condition`noto'g'ri **bo'lsa** , `expression2`bajariladi.

Uchlik operator **3 ta operandni** ( `condition`, `expression1`, va `expression2`) oladi. Demak, **uchlik operator** nomi .

***

#### Misol: Swift uchlik operatori <a href="#example" id="example"></a>

```
// program to check pass or fail
let marks = 60

// use of ternary operator
let result = (marks >= 40) ? "pass" : "fail"

print("You " + result + " the exam")
```

**Chiqish**

```
Siz imtihondan o'tasiz.
```

Yuqoridagi misolda biz o'tish yoki muvaffaqiyatsizlikni tekshirish uchun uchlik operatoridan foydalanganmiz.

`let result = (marks >= 40) ? "pass" : "fail"`

Bu erda, agar **40**`marks` dan katta yoki teng bo'lsa , ga tayinlanadi . Aks holda, ga tayinlanadi .`passresultfailresult`

***

### if...else o'rniga uchlik operator <a href="#use" id="use"></a>

Uchlik operatori ma'lum turdagi `if...else`bayonotlarni almashtirish uchun ishlatilishi mumkin. Misol uchun,

Ushbu kodni almashtirishingiz mumkin

```
// check the number is positive or negative
let num = 15
var result = ""

if (num > 0) {
     result = "Positive Number"
}
else {
     result = "Negative Number"
}

print(result)
```

bilan

```
// ternary operator to check the number is positive or negative
let num = 15

let result = (num > 0) ? "Positive Number" : "Negative Number"
print(result)
```

**Chiqish**

```
Ijobiy raqam
```

Bu erda ikkala dastur ham bir xil natijani beradi. Biroq, uchlik operatoridan foydalanish bizning kodimizni yanada o'qilishi va toza qiladi.

***

### Ichki uchlik operatorlari <a href="#nested" id="nested"></a>

Biz bitta uchlik operatorni boshqa uchlik operator ichida ishlatishimiz mumkin. Bu Swiftda ichki uchlik operatori deb ataladi. Misol uchun,

```
// program to check if a number is positive, zero, or negative
let num = 7

let result = (num == 0) ? "Zero" : ((num > 0) ? "Positive" : "Negative")

print("The number is \(result).")
```

**Chiqish**

`The number is Positive.`

Yuqoridagi misolda, agar shart bo'lsa, biz ichki uchlik operatori `((num > 0) ? "Positive" : "Negative"`bajariladi .`num == 0false`

**Eslatma:** Ichki uchlik operatorlaridan foydalanmaslik tavsiya etiladi, chunki ular bizning kodimizni murakkablashtiradi.
