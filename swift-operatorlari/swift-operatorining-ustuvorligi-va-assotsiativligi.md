# Swift operatorining ustuvorligi va assotsiativligi

Ushbu maqolada siz operatorlar va operandlar bilan ifodani baholash uchun ishlatiladigan qoidalar haqida bilib olasiz.

Operatorning ustuvorligi - qaysi operator birinchi bo'lib bajarilishini belgilaydigan qoidalar to'plami.

[Operatorning ustuvorligi haqida bilishdan oldin, Swift operatorlari](https://www.programiz.com/swift-programming/operators) haqida bilishingizga ishonch hosil qiling .

***

Misol keltiramiz, deylik, ifodada bir nechta operator mavjud.

```
var num = 8 + 5 * 4 // 28
```

Bu yerda,

* birinchi bo'lib bajarilsa `+`, qiymati `num`bo'ladi`52`
* birinchi bo'lib bajarilsa `*`, qiymati `num`bo'ladi`28`

Bu holda operator ustuvorligi qaysi operator birinchi bo'lib bajarilishini aniqlash uchun ishlatiladi. ning operatori ustunligi `*`yuqori bo'lgani `+`uchun ko'paytirish birinchi bo'lib bajariladi.

***

### Operator ustunligi jadvali <a href="#table" id="table"></a>

Quyidagi jadvalda Swift operatorlarining ustuvorligi keltirilgan. Jadvalda qanchalik baland bo'lsa, uning ustunligi shunchalik yuqori bo'ladi.

| Operatorlar          | Misollar                                        |
| -------------------- | ----------------------------------------------- |
| Bit bo'yicha siljish | `>>` `<<`                                       |
| Multiplikativ        | `%` `*` `/`                                     |
| Qo'shimcha           | `\|` `-` `+` `-` `^`                            |
| Diapazon             | `..<` `...`                                     |
| Kasting              | `is as`                                         |
| Nil-birlashtirish    | `??`                                            |
| Taqqoslash           | `!=` `>` `<` `>=` `<=` `===` `==`               |
| Mantiqiy VA          | `&&`                                            |
| Mantiqiy OR          | `\|\|`                                          |
| Uchlik operator      | `? :`                                           |
| Topshiriq ustunligi  | `\|=` `%=` `/=` `*=` `>>=` `<<=` `^=` `+=` `-=` |

***

#### Misol: murakkab tayinlash operatori bilan operator ustunligi <a href="#example-precedence" id="example-precedence"></a>

```
var num = 15

num += 10 - 2 * 3
print(num)
```

**Chiqish**

```
19
```

Yuqoridagi misolda biz `num`qiymati bilan o'zgaruvchi yaratdik `15`. Bayonotga e'tibor bering

`num += 10 - 2 * 3`

Bu yerda yuqoridan pastga qarab ustunlik tartibi `*`, `-`va `+=`. Demak, bayonot sifatida bajariladi `num += 10 - (2 * 3)`.

***

### Swift Operator Assotsiativligi <a href="#associativity" id="associativity"></a>

Agar ifoda bir xil ustuvorlikka ega boʻlgan ikkita operatorga ega boʻlsa, ifoda uning assotsiativligiga (chapdan oʻngga yoki oʻngdan chapga) qarab baholanadi. Misol uchun,

```
print(6 * 4 / 3)     // 8 
```

Bu erda operatorlar `*`va `/`bir xil ustunlikka ega. Va ularning assotsiatsiyasi chapdan o'ngga. Shunday qilib, `6 * 4`birinchi navbatda amalga oshiriladi.

**Eslatma:** Agar biz birinchi bo'limni bajarmoqchi bo'lsak, biz qavslarni sifatida ishlatishimiz mumkin `print(6 * (4/3))`.

***

### Operatorlar assotsiativlik jadvali <a href="#associativity-table" id="associativity-table"></a>

Agar ifoda bir xil ustuvorlikka ega ikkita operatorga ega bo'lsa, ifoda uning assotsiativligiga qarab baholanadi.

* **Chap assotsiativlik** - operatorlar chapdan o'ngga qarab baholanadi
* **O'ng assotsiativlik -** operatorlar o'ngdan chapga baholanadi
* **Non-assotsiativlik** - operatorlar aniqlangan xatti-harakatlarga ega emas

Misol uchun,

```
print (6 * 4 / 3)
```

Bu erda operatorlar `*`va `/`bir xil ustunlikka ega. Biroq, ularning assotsiatsiyasi qolgan. Shunday qilib, `6 * 4`birinchi navbatda amalga oshiriladi.

Quyidagi jadvalda Swift operatorlarining assotsiatsiyasi ko'rsatilgan.

| Operatorlar                                          | Assotsiativlik |
| ---------------------------------------------------- | -------------- |
| **Bitwise Shift** :`>>` `<<`                         | yo'q           |
| **Multiplikativ** :`%` `*` `/`                       | chap           |
| **Qo'shimcha** :`\|` `+` `-` `^`                     | chap           |
| **Diapazon** :`..<` `...`                            | yo'q           |
| **Kasting** :`is as`                                 | yo'q           |
| **Nil-birlashma** :`??`                              | to'g'ri        |
| **Taqqoslash** :`!=` `>` `<` `>=` `<=` `===` `==`    | yo'q           |
| **Mantiqiy VA** :`&&`                                | chap           |
| **Mantiqiy OR** :`\|\|`                              | chap           |
| **Uchlik operator** :`? :`                           | to'g'ri        |
| **Topshiriq** :`\|=` `%=` `/=` `*=` `>>=` `<<=` `^=` | to'g'ri        |
