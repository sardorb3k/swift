# Swift-da ichki o'rnatilgan tsikllar

Ushbu o'quv qo'llanmada biz misollar yordamida Swift-da o'rnatilgan tsikllar haqida bilib olamiz.

Agar boshqa halqaning tanasi ichida halqa mavjud bo'lsa, u ichki halqa deyiladi. `for`Mana, o'rnatilgan halqa misoli .

```
// outer loop
for i in 1...5 {
  // codes

  // inner loop
  for j in 1...2 {
    //codes
  }
}
```

Bu erda ichki `for`pastadir `for j in 1...2`tashqi `for`halqa ichiga joylashtirilgan `for i in 1...5`.

***

### Loop uchun Swift Nested <a href="#nested-for" id="nested-for"></a>

Ichki halqa boshqa halqa ichidagi bir `for`halqani o'z ichiga oladi . Misol uchun,`forfor`

```
// Swift program to display 7 days of 2 weeks

// outer loop
for week in 1...2 {
  print("Week: \(week)")

// inner loop
    for day in 1...7 {
      print("  Day:  \(day)")
  
   }

// line break after iteration of outer loop
   print("")
}
```

**Chiqish**

```
Hafta: 1
  Kun: 1
  Kun: 2
...

Hafta: 2
  Kun: 1
  Kun: 2
...
```

Yuqoridagi misolda tashqi halqa **2** marta takrorlanadi va **2** hafta chop etadi: `Week: 1`va `Week: 2`.

Va, ichki pastadir **7** marta takrorlanadi va **7** kunni chop etadi: `Day: 1`, `Day: 2`, va hokazo.

**Eslatma:** Shunga o'xshab, biz ham o'rnatilgan [while va takrorlash...while davrlarini](https://www.programiz.com/swift-programming/repeat-while-loop) yaratishimiz mumkin . Misol uchun,

```
// outer while loop
while (condition) {
  ...

  // inner while loop
  while (condition2) {
    ...
  }
}
```

***

### Swift for Loop a while Loop ichida <a href="#for-while" id="for-while"></a>

Bundan tashqari, biz har xil turdagi ichki halqalarni yaratishimiz mumkin. Ya'ni, biz bir `for`pastadir ichiga `while`va aksincha qo'yishimiz mumkin. Misol uchun,

```
// program to display 7 days of 2 weeks
var weeks = 2
var i = 1

// outer while loop
while (i <= weeks){
  print("Week: \(i)")

  // inner for loop
  for day in 1...7{
      print("  Day:  \(day)")
    }

    i = i + 1
}
```

**Chiqish**

```
Hafta: 1
  Kun: 1
  Kun: 2
…

Hafta: 2
  Kun: 1
  Kun: 2
 ...
```

Bu erda biz `for`pastadir ichidagi `while`pastadirdan foydalandik.

**Eslatma:** Xuddi shunday, biz ham halqani yoki `repeat...while`pastadir ichiga joylashtirishimiz mumkin .`whilefor`

***

### uzing va Inside Nested Loop-ni davom ettiring

**1. Nested Loop ichida sindirish**

Biz ichki tsikl ichida [break iborasidan](https://www.programiz.com/swift-programming/break-statement) foydalansak , u ichki tsiklni tugatadi, lekin tashqi tsiklni emas. Misol uchun,

```
// outer loop
for week in 1...3 {
  print("Week: \(week)")

  // inner loop
  for day in 1...7 {


    if(week == 2) {
      // use of break statement
      break
      }

    print("  Day:  \(day)")
   }

  print("")
}
```

**Chiqish**

```
Hafta: 1
  Kun: 1
  Kun: 2
...

Hafta: 2

Hafta: 3
  Kun: 1
  Kun: 2
...
```

Yuqoridagi misolda biz `break`ichki `for`halqa ichidagi bayonotdan foydalanganmiz. Chiziqqa e'tibor bering,

```
if(week == 2) {
  break
}
```

`week`Bu yerda dastur siklni qachon tugatadi `2`.

Shuning uchun kunlar `week 2`chop etilmaydi. Biroq, haftani chop etadigan tashqi halqa ta'sir qilmaydi.

***

**2. Nested Loop ichida davom eting**

Xuddi shunday, biz ichki halqa ichida [davom](https://www.programiz.com/swift-programming/continue-statement) etish iborasidan foydalansak, u faqat ichki tsiklning joriy iteratsiyasini o'tkazib yuboradi. Misol uchun,

```
// outer loop
for week in 1...2 {
  print("Week: \(week)")

  // inner loop
  for day in 1...7 {

    // use of continue statement
    if(day % 2 != 0) {
      continue
      }

   print("  Day:  \(day)")
   }

  print("")
}
```

**Chiqish**

```
Hafta: 1
  Kun: 2
  Kun: 4
  Kun: 6

Hafta: 2
  Kun: 2
  Kun: 4
  Kun: 6
```

Yuqoridagi misolda biz `continue`ichki for tsikli ichidagi bayonotdan foydalanganmiz. Kodga e'tibor bering,

```
if(day % 2 != 0) {
  continue
}
```

Bu yerda ifoda qiymati toq `continue`bo‘lganda bajariladi . `day`Shunday qilib, dastur faqat teng bo'lgan kunlarni chop etadi.

Biz `continue`bayonot faqat ichki halqaga ta'sir qilganini ko'rishimiz mumkin. Tashqi halqa muammosiz ishlaydi.
