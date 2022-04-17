# Swift switch bayonoti

Ushbu maqolada siz o'z dasturingizning bajarilishini boshqarish uchun switch boshqaruvi bayonotlaridan foydalanishni o'rganasiz.

Bayonot `switch`bizga ko'plab alternativalar orasida kod blokini bajarishga imkon beradi.

`switch`Swift -dagi bayonotning sintaksisi :

```
switch (expression)  {
  case value1:
    // statements 

  case value2:
    // statements 

  ...
  ...
        
  default:
    // statements
}
```

Bayonot `switch`qavslar ichidagi ifodani baholaydi `()`.

1. Ifodaning natijasi ga teng bo'lsa `value1`, ning `case value1:`operatorlari bajariladi.
2. Ifodaning natijasi ga teng bo'lsa `value2`, ning `case value2:`operatorlari bajariladi.
3. Agar mos kelmasa, **standart holatning** bayonotlari bajariladi.

**Eslatma:** [if...else...if](https://www.programiz.com/swift-programming/if-else-statement#if-else-if) narvon bilan ham xuddi shunday qilishimiz mumkin . Biroq, `switch`bayonotning sintaksisi yanada toza va o'qish va yozishni ancha osonlashtiradi.

***

### Switch bayonoti sxemasi <a href="#undefined" id="undefined"></a>

![Switch bayonoti bizga ko'plab alternativalardan ma'lum kod bloklarini bajarishga imkon beradi.](https://cdn.programiz.com/cdn/farfuture/xLoJgDQVxTGY721Bcn5p4geinUUk6r4d0WGDYOLeaeg/mtime:1619594067/sites/tutorial2program/files/swift-switch-statement.png)

#### 1-misol: Switch bayonotidan foydalangan holda oddiy dastur <a href="#simple" id="simple"></a>

```
// program to find the day of the week 

let dayOfWeek = 4

switch dayOfWeek {
  case 1:
    print("Sunday")
	    
  case 2:
    print("Monday")
	    
  case 3:
    print("Tuesday")
	    
  case 4:
    print("Wednesday")
	    
  case 5:
    print("Thursday")
	    
  case 6:
    print("Friday")
	    
  case 7:
    print("Saturday")
	    
  default:
    print("Invalid day")
}
```

**Chiqish**

```
chorshanba
```

Yuqoridagi misolda biz o'zgaruvchini `4`tayinladik . `dayOfWeek`Endi o'zgaruvchi har bir case bayonotining qiymati bilan taqqoslanadi.

Qiymat bilan mos kelganligi sababli `case 4`, `print("Wednesday")`ish ichidagi operator bajariladi va dastur tugatiladi.

***

### Bayonotni pasayish bilan almashtiring <a href="#fallthrough" id="fallthrough"></a>

Agar `fallthrough`kalit so'zni case operatori ichida ishlatsak, case qiymati switch ifodasiga mos kelmasa ham boshqaruv keyingi holatga o'tadi. Misol uchun,

```
// program to find the day of the week 

let dayOfWeek = 4

switch dayOfWeek {
  case 1:
    print("Sunday")
	    
  case 2:
    print("Monday")
	    
  case 3:
    print("Tuesday")
	    
  case 4:
    print("Wednesday")
    fallthrough
	    
  case 5:
    print("Thursday")
	    
  case 6:
    print("Friday")
	    
  case 7:
    print("Saturday")
	    
  default:
    print("Invalid day")
}
```

**Chiqish**

```
chorshanba
Payshanba
```

Yuqoridagi misolda qiymat bilan mos kelganligi sababli `case 4`, `print("Wednesday")`ish ichidagi operator bajariladi

Biz kalit so'zdan ham foydalanganmiz `fallthrough`. Demak, `print("Thursday")`ichidagi `case 5`gap ish bayoniga mos kelmasa ham bajariladi.

***

#### 2-misol: Diapazon bilan almashtirish bayonoti <a href="#range" id="range"></a>

```
let ageGroup = 33

switch ageGroup {
  case 0...16:
    print("Child")

  case 17...30:
    print("Young Adults")

  case 31...45:
    print("Middle-aged Adults")

  default:
    print("Old-aged Adults")
}
```

**Chiqish**

```
O'rta yoshli kattalar
```

Yuqoridagi misolda bitta qiymat o'rniga biz har bir holat uchun raqamli diapazonlardan foydalandik: `case 0...16`, `case 17...30`, va `case 31...45`.

Bu erda ning qiymati `ageGroup`diapazon `33`ostiga tushadi `32...45`. Shunday qilib, bayonot `print("Middle-aged Adults")`bajariladi.

***

### Switch bayonotidagi kortej <a href="#tuple" id="tuple"></a>

Swift-da biz switch iboralarida [kortejlardan ham foydalanishimiz mumkin. ](https://www.programiz.com/swift-programming/tuples)Misol uchun,

```
let info = ("Dwight", 38)

// match complete tuple values
switch info {
  case ("Dwight", 38): 
    print("Dwight is 38 years old")

  case ("Micheal", 46): 
    print("Micheal is 46 years old")

  default:
    print("Not known")
}
```

**Chiqish**

```
Duayt 38 yoshda
```

`info`Yuqoridagi misolda biz qiymatlar bilan nomlangan kortej yaratdik : `"Dwight"`va `38`.

Bu erda bitta qiymat o'rniga har bir case operatori kortejlarni ham o'z ichiga oladi: `case ("Dwight", 38)`va `case ("Micheal", 46)`.

Endi ning qiymati `info`har bir holat bayonoti bilan taqqoslanadi. Qiymat bilan mos kelganligi sababli `case ("Dwight", 38)`, bayonot `print("Dwight is 38 years old")`bajariladi.

Kortejlar haqida ko'proq ma'lumot olish uchun [Swift Tuple](https://www.programiz.com/swift-programming/tuples) -ga tashrif buyuring .
