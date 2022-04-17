# Tez davom etish bayonoti

Ushbu o'quv qo'llanmada biz misollar yordamida davom iborasi bilan tanishamiz.

Ushbu `continue`bayonot tsiklning joriy iteratsiyasini o'tkazib yuborish uchun ishlatiladi va dasturning boshqaruv oqimi keyingi iteratsiyaga o'tadi.

Bayonotning sintaksisi `continue`:

```
continue
```

Bayonot haqida bilishdan oldin, `continue`quyidagilarni bilganingizga ishonch hosil qiling:

* [Swift for loop](https://www.programiz.com/swift-programming/for-in-loop)
* [Swift if... else bayonoti](https://www.programiz.com/swift-programming/if-else-statement)
* [Swift while tsikli](https://www.programiz.com/swift-programming/repeat-while-loop)

***

### Swiftning ishini davom ettirish bayonoti <a href="#working" id="working"></a>

![Swift-da davom etish bayonoti qanday ishlaydi](https://cdn.programiz.com/cdn/farfuture/-U-RGApp19146iA7zZ3rDulN0lNqhqnbK-hpazbBynI/mtime:1620036763/sites/tutorial2program/files/swift-continue-statement.png)Swiftning ishini davom ettirish bayonoti

***

### Swift continue bayonoti bilan for Loop <a href="#for" id="for"></a>

Biz tsiklning joriy iteratsiyasini o'tkazib yuborish uchun tsikl `continue`bilan bog'liq bayonotdan foydalanishimiz mumkin. `for`Keyin dasturni boshqarish keyingi iteratsiyaga o'tadi. Misol uchun,

```
for i in 1...5 {
  
  if i == 3 {
    continue
  }
 
print(i)
}
```

**Chiqish**

```
1
2
4
5
```

Yuqoridagi misolda biz `for`ning qiymatini chop etish uchun tsikldan foydalanganmiz `i`. `continue`Bayonotdan foydalanishga e'tibor bering ,

```
if i == 3 {
  continue
}
```

Bu erda `i`ga teng bo'lsa `3`, `continue`operator bajariladi. Shunday qilib, qiymat `3`chiqishda chop etilmaydi.

**Eslatma:** Bayonot `continue`deyarli har doim qaror qabul qilish bayonotlari bilan ishlatiladi.

***

### while tsikli bilan davom eting <a href="#while" id="while"></a>

Bundan tashqari , bayonot `while`yordamida tsiklning joriy iteratsiyasini o'tkazib yuborishimiz mumkin. `continue`Misol uchun,

```
// program to print odd numbers from 1 to 10

var num = 0

while num <= 10{
  num += 1

  if (num % 2) == 0 {
    continue
}

print("\(num)")
}
```

**Chiqish**

```
1
3
5
7
9
```

Yuqoridagi misolda biz **1** dan **10**`while` gacha bo'lgan toq raqamlarni chop etish uchun tsikldan foydalanganmiz . Chiziqqa e'tibor bering,

```
if (num % 2) == 0 {
  continue
}
```

Bu erda raqam juft bo'lganda, `continue`bayonot joriy iteratsiyani o'tkazib yuboradi va keyingi iteratsiyani boshlaydi.

***

### Yuvalangan halqalar bilan Swift continue bayonoti <a href="#nested-loops" id="nested-loops"></a>

Biz `continue`iborani ichkariga qo'yilgan halqalar bilan ishlatganimizda, u ichki tsiklning joriy iteratsiyasini o'tkazib yuboradi. Misol uchun,

```
for i in 1...3 {
  for j in 1...3 {
    
    if j == 2 {
      continue
    }
    
    print("i = \(i), j = \(j)")
  }
}
```

```
```

**Chiqish**

```
i = 1, j = 1
i = 1, j = 3
i = 2, j = 1
i = 2, j = 3
i = 3, j = 1
i = 3, j = 3
```

Yuqoridagi misolda biz `continue`ichki `for`halqa ichidagi bayonotdan foydalanganmiz.

```
if j == 2 {
  continue
}
```

Bu erda ning qiymati `j`2 ga teng bo'lsa `continue`, operator bajariladi. Shunday qilib, qiymati `j = 2`hech qachon chiqishda ko'rsatilmaydi.

***

### Swift Labeled davom etadi <a href="#labeled" id="labeled"></a>

Hozirgacha biz etiketlanmagan `continue`bayonotdan foydalanganmiz. Biroq, Swift-da **davom**`continue` etuvchi deb nomlanuvchi bayonotning yana bir shakli mavjud .

Ichki tsikllardan foydalanilganda, biz **davom** etish yorlig'i bilan tashqi tsiklning joriy iteratsiyasini o'tkazib yuborishimiz mumkin .

![Davom etish belgisi qanday ishlaydi](https://cdn.programiz.com/cdn/farfuture/S3msnhLSFsTAWMH\_SL923RKC1yylWLUZoEjt-HL7D38/mtime:1620036769/sites/tutorial2program/files/swift-labeled-continue-statement.png)Swift Labeled ishini davom ettirish bayonoti

Yuqoridagi rasmda ko'rib turganimizdek, biz `outerloop`tashqi tsiklni belgilash uchun identifikatordan foydalanganmiz. Endi davom iborasi qanday ishlatilishiga e'tibor bering ( `continue outerloop`)

Bu erda `continue`bayonot belgilangan bayonotning joriy iteratsiyasini o'tkazib yuboradi (ya'ni tashqi tsikl). Keyin, dastur boshqaruvi belgilangan bayonotning keyingi iteratsiyasiga o'tadi.

#### Misol: davomi bilan belgilangan bayonot

```
outerloop: for i in 1...3{
  
  innerloop: for j in 1...3 {
    
    if j == 3 {
      continue outerloop
    }
    
    print("i = \(i), j = \(j)")
  }
}
```

**Chiqish**

```
i = 1, j = 1                                                                                                                            
i = 2, j = 1                                                                                                                            
i = 3, j = 1                                                                                                                                         
```

Yuqoridagi misolda biz halqalarimizni quyidagicha belgiladik:

`outerloop: for i in 1...3 {...}`

`innerloop: for j in 1...3 {...}`

Bu looplarni aniqlashga yordam beradi. Belgilangan `continue`bayonotdan foydalanishga e'tibor bering.

```
if j == 3 {
  continue outerloop
}
```

Bu erda ifoda qiymati ga teng bo'lganda `continue`bilan belgilangan tashqi tsiklning iteratsiyasini o'tkazib yuboradi .`outerloopj3`

**Eslatma** : **Davom etish belgisidan** foydalanish odatda tavsiya etilmaydi, chunki bu kodingizni tushunishni qiyinlashtiradi.
