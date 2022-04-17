# Swift break bayonoti

Ushbu qo'llanmada siz misollar yordamida tanaffus bayonoti bilan tanishasiz.

Ko'rsatma `break`siklni duch kelganda darhol tugatish uchun ishlatiladi.

Bayonotning sintaksisi `break`:

```
break
```

Bayonot haqida bilishdan oldin, `break`quyidagilarni bilganingizga ishonch hosil qiling:

* [Swift for loop](https://www.programiz.com/swift-programming/for-in-loop)
* [Swift if... else bayonoti](https://www.programiz.com/swift-programming/if-else-statement)
* [Swift while tsikli](https://www.programiz.com/swift-programming/repeat-while-loop)

***

### Swift break bayonotining ishlashi <a href="#working" id="working"></a>

![Swift-da break iborasi qanday ishlaydi](https://cdn.programiz.com/cdn/farfuture/ZOIZEfp0V6CTrRuBNum2Q0A6EZzYGJeoEmmGNHHyfRo/mtime:1620036782/sites/tutorial2program/files/swift-break-statement.png)

### Swift break bayonoti for tsikli bilan <a href="#for" id="for"></a>

Muayyan shart bajarilganda siklni tugatish uchun sikl `break`bilan ifodadan foydalanishimiz mumkin . `for`Misol uchun,

```
for i in 1...5 {
  
  if i == 3 {
    break
  }
 
print(i)
}
```

**Chiqish**

```
1
2
```

Yuqoridagi misolda biz `for`ning qiymatini chop etish uchun tsikldan foydalanganmiz `i`. `break`Bayonotdan foydalanishga e'tibor bering ,

```
if i == 3 {
  break
}
```

Bu erda, **3**`i` ga teng bo'lganda , bayonot tsiklni tugatadi. **Shunday qilib, chiqish 2** dan keyingi qiymatlarni o'z ichiga olmaydi .`break`

**Eslatma:** Bayonot `break`deyarli har doim qaror qabul qilish bayonotlari bilan ishlatiladi.

***

### while Loop bilan uzing <a href="#while" id="while"></a>

Bundan tashqari, `while`operator yordamida tsiklni tugatishimiz mumkin `break`. Misol uchun,

```
// program to find first 5 multiples of 6

var i = 1

while (i<=10) {
  print("6 * \(i) =",6 * i)

    if i >= 5 {
      break
   }
 
  i = i + 1
}
```

**Chiqish**

```
6 * 1 = 6
6 * 2 = 12
6 * 3 = 18
6 * 4 = 24
6 * 5 = 30
```

Yuqoridagi misolda biz `while`6 ning birinchi 5 ta karrasini topish uchun tsikldan foydalandik. Bu erda chiziqqa e'tibor bering,

```
if i >= 5 {
  break
}
```

Bu `i`5 dan katta yoki unga teng bo'lsa, `while`tsikl tugatiladi.

***

### O'rnatilgan tsikllar bilan tezkor uzilish bayonoti <a href="#nested-loops" id="nested-loops"></a>

Biz `break`iborani ichki tsikllar bilan ishlatganimizda, u ichki tsiklni tugatadi. Misol uchun,

```
// outer for loop
for i in 1...3 {

  // inner for loop
  for j in 1...3 {

    if i == 2 {
      break
    }

    print("i = \(i), j = \(j)")
  }
}
```

**Chiqish**

```
i = 1, j = 1                                                                                                                            
i = 1, j = 2                                                                                                                            
i = 1, j = 3                                                                                                                            
i = 3, j = 1                                                                                                                            
i = 3, j = 2                                                                                                                            
i = 3, j = 3
```

Yuqoridagi misolda biz `break`ichki `for`halqa ichidagi bayonotdan foydalanganmiz.

```
if i == 2 {
  break
}
```

Bu erda agar qiymat bo'lsa `i`, operator `2`bajariladi `break`. U ichki tsiklni tugatadi va dasturning boshqaruv oqimi tashqi tsiklga o'tadi.

Shunday qilib, qiymati `i = 2`hech qachon chiqishda ko'rsatilmaydi.

***

### Swift Belgilangan tanaffus <a href="#labeled" id="labeled"></a>

Hozirgacha biz etiketlanmagan `break`bayonotdan foydalanganmiz. Biroq, Swift-da **belgilangan break**`break` deb nomlanuvchi bayonotning yana bir shakli mavjud .

Ichki tsikllardan foydalanganda, biz tashqi tsiklni **belgilangan break bayonoti** bilan tugatishimiz mumkin .

![Belgilangan tanaffus qanday ishlaydi](https://cdn.programiz.com/cdn/farfuture/MGFqnrYS6F8xJ0Bz-2fZLdgRz7ml3zUZSPqLb2bggMo/mtime:1620036776/sites/tutorial2program/files/swift-labeled-break-statement.png)

Yuqoridagi rasmda ko'rib turganingizdek, biz `outerloop`tashqi tsiklni belgilash uchun identifikatordan foydalanganmiz. Endi `break`ibora qanday ishlatilishiga e'tibor bering ( `break outerloop`).

Bu erda `break`bayonot belgilangan bayonotni (ya'ni tashqi tsikl) tugatadi. Shundan so'ng, dasturni boshqarish belgilangan bayonotdan keyingi bayonotga o'tadi.

#### Misol: tanaffus bilan belgilangan bayonot <a href="#example-labeled" id="example-labeled"></a>

```
outerloop: for i in 1...3{

  innerloop: for j in 1...3 {

    if j == 3 {
      break outerloop
    }

      print("i = \(i), j = \(j)")
  }
}
```

**Chiqish**

```
i = 1, j = 1
i = 1, j = 2
```

Yuqoridagi misolda biz halqalarimizni quyidagicha belgiladik:

```
outerloop: for i in 1...3 {...}
innerloop: for j in 1...3 {...}
```

Bu looplarni aniqlashga yordam beradi. Belgilangan `break`bayonotdan foydalanishga e'tibor bering.

```
if j == 3 {
  break outerloop
}
```

Bu erda `break`bayonot endi bilan belgilangan tashqi tsiklni tugatadi `outerloop`.
