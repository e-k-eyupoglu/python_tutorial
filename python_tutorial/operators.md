﻿# İçindekiler
- [Operatörler (Operators)](#1)
    - [`,` Comma Operator](#1.1)
    - [Arithmetic Operators](#1.2)
        - [`+` Addition (Toplama) Operator](#1.2.1)
        - [`-` Subtraction (Çıkarma) Operator](#1.2.2)
        - [`*` Multiplication (Çarpma) Operator](#1.2.3)
        - [`/` Division (Bölme) Operator](#1.2.4)
        - [`**` Exponentiation (Üs Alma) Operator](#1.2.5)
        - [`//` Floor division (Taban Bölme)) Operator](#1.2.6)
        - [`%` Modulus (Modül) Operator](#1.2.7)
    - [Comparison Operators](#1.3)
        - [`==` Operator](#1.3.1)
        - [`!=` Operator](#1.3.2)
        - [`>` Operator](#1.3.3)
        - [`<` Operator](#1.3.4)
        - [`>=` Operator](#1.3.5)
        - [`<=` Operator](#1.3.6)
    - [Logical Operators](#1.4)
        - [`and` Operator](#1.4.1)
        - [`or` Operator](#1.4.2)
        - [`not` Operator](#1.4.3)
    - [Bitwise operators](#1.5)
        - [`&` Bitwise AND Operator](#1.5.1)
        - [`|` Bitwise OR Operator](#1.5.2)
        - [`^` Bitwise XOR Operator](#1.5.3)
        - [`~` Bitwise Complement Operator](#1.5.4)
        - [`<<` Binary Left Shift Operator](#1.5.5)
        - [`>>` Binary Right Shift Operator](#1.5.6)
    - [Assignment Operators](#1.6)
        - [`=` Assignment Operator](#1.6.1)
        - [`+=` Operator](#1.6.2)
        - [`-=` Operator](#1.6.3)
        - [`*=` Operator](#1.6.4)
        - [`/=` Operator](#1.6.5)
        - [`**=` Operator](#1.6.6)
        - [`//=` Operator](#1.6.7)
        - [`%=` Operator](#1.6.8)
        - [`&=` Operator](#1.6.9)
        - [`|=` Operator](#1.6.10)
        - [`^=` Operator](#1.6.11)
        - [`<<=` Operator](#1.6.12)
        - [`>>=` Operator](#1.6.13)
    - [`is` Identity Operator](#1.7)
    - [`in` Membership Operator](#1.8)
- [`:=` Assignment Expression](#2)
- [Boolean Type](#3)
- [Operator Önceliği](#4)

<h1 id="1">Operatörler (Operators)</h1>

Python'un yapı taşlarından birisidir. Variable'lar, value'lar veya objeler üzerinde işlemler yapmamızı sağlarlar. `2 + 2` işleminde `2`'ler **operand** (işlenen), `+` ise **operator**'dır (işleç/işlemci).

<h2 id="1.1"><code>,</code> Comma Operator</h2>

Tek başına spesifik bir kullanım alanı çok yoktur. Comma (virgül) operator'ı, birden fazla variable'a tek statement'da value atamak veya swap işlemi için kullanılabilir. Örnek:
```py
a, b = 1, 2 # a = 1 ; b = 2
print(a, b) # Output: 1 2

a, b = (1, 2) # <class 'tuple'>
print(a, b) # Output: 1 2

a, b = [1, 2] # <class 'list'>
print(a, b) # Output: 1 2

a, b = {1, 2} # <class 'set'>
print(a, b) # Output: 1 2

print(a, b) # Output: 1 2
a, b = b, a
print(a, b) # Output: 2 1
a,b,c = 1,2,3
print(a,b,c) # Output: 1 2 3
a,b,c = c,a,b
print(a,b,c) # Output: 3 1 2

a, b = 1
print(a, b) # TypeError: cannot unpack non-iterable int object
```
Bunlar dışında `list`, `tuple`, `set`, `dict` vs. gibi type'larda, sıralı elemanları ayırmak için kullanılır. Örnek:
```py
list_exp = [1, 2, 3]
tuple_exp = (1, 2, 3)
set_exp = {1, 2, 3}
dict_exp = {1:"bir", 2:"iki", 3:"üç"}
```
<h2 id="1.2">Arithmetic Operators</h2>

<h3 id="1.2.1"><code>+</code> Addition (Toplama) Operator</h3>

Addition operator'ı, iki operand'ı birbiriyle toplar / birbirine ekler. Örneğn numeric type'larda toplama işlemi, text type'larda ekleme işlemi yapar.
```py
print(5 + 10) # Output: 15

print("Python" + " " + "C++") # Output: Python C++
```
İki objeyi de birbirine ekleyebilir. Örnek:
```py
class Vektor:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def __str__(self):
        return 'Vektör ({}, {})'.format(self.x, self.y)

    def __add__(self,other):
        return Vektor(self.x + other.x, self.y + other.y)

v1 = Vektor(2,10)
v2 = Vektor(5,-2)
print(v1 + v2) # Output: Vektör (7, 8)
```
Yukarıdaki örnek class'larla ilgili bir konu olduğu için şimdilik anlamak zorunda değilsiniz.

<h3 id="1.2.2"><code>-</code> Subtraction (Çıkarma) Operator</h3>

Subtraction operator'ı, iki operandı birbirinden çıkarır. Örneğin numenic type'larda kullanılır. Örnek:
```py
print(10 - 2) # Output: 8
```

<h3 id="1.2.3"><code>*</code> Multiplication (Çarpma) Operator</h3>

Multiplication operator'ı, iki operandı birbiriyle çarpar. Örneğin numenic type'larda çarpma işlemi, text type'larda ise çoklu yazdırma işlemleri yapar. Örnek:
```py
print(5 * 10) # Output: 50
print("Beş " * 5) # Output: Beş Beş Beş Beş Beş 
```

<h3 id="1.2.4"><code>/</code> Division (Bölme) Operator</h3>

Division operator'ı, iki operandı birbirine böler. Örneğin numenic type'larda bölme işlemi yapar. Örnek:
```py
print(10 / 5) # Output: 2
```

<h3 id="1.2.5"><code>**</code> Exponentiation (Üs Alma) Operator</h3>
Exponentiation operator'ı, solundaki operand'ın, sağındaki operand'a göre üssünü alır. Örneğin numenic type'larda üst alma işlemi yapar. Örnek:
```py
print(2 ** 4) # Output: 8
```

<h3 id="1.2.6"><code>//</code> Floor division (Taban Bölme)) Operator</h3>

Floor division operator'ı, iki operandı birbirine kalansız böler. Örneğin numenic type'larda kalansız bölme işlemi yapar. Örnek:
```py
print(5 // 2) # Output: 2
```
`5`'in içinde iki tane `2` vardır. Burada sonucun `2.5` çıkmamasının sebebi budur. Normal division işleminden farkı budur. 

<h3 id="1.2.7"><code>%</code> Modulus (Modül) Operator</h3>

Modulus operator'ı, iki operandın birbirine bölünübden kalanı verir. Örneğin numenic type'larda modulus işlemi yapar. Örnek:
```py
print(5 % 2) # Output: 1
```
`5`'in içinde iki tane `2` olduğu için `1` kalır. Bu yüzden modulus işlemi `1` sonucunu verir.

<h2 id="1.3">Comparison Operators</h2>

<h3 id="1.3.1"><code>==</code> Operator</h3>

İki operand birbirine eşitse `True`, değilse `False` döndürür.
```py
print(1 == 1) # Output: True
print(1 == 2) # Output: False
```

<h3 id="1.3.2"><code>!=</code> Operator</h3>

İki operand birbirine eşitse `False`, değilse `True` döndürür. `==` operator'ının tam tersi işlevi yapar.
```py
print(1 != 2) # Output: True
print(1 != 1) # Output: False
```

<h3 id="1.3.3"><code>></code> Operator</h3>

Soldaki operand sağdaki operand'dan büyükse `True`, aksi durumlarda `False` döndürür.
```py
print(2 > 1) # Output: True
print(1 > 2) # Output: False
```

<h3 id="1.3.4"><code><</code> Operator</h3>

Sağdaki operand soldaki operand'dan büyükse `True`, aksi durumlarda `False` döndürür.
```py
print(1 < 2) # Output: True
print(2 < 1) # Output: False
```

<h3 id="1.3.5"><code>>=</code> Operator</h3>

Soldaki operand sağdaki operan'dan büyükse ya da eşitse `True`, aksi durumlarda `False` döndürür.
```py
print(2 >= 1) # Output: True
print(2 >= 2) # Output: True
print(1 >= 2) # Output: False
```

<h3 id="1.3.6"><code><=</code> Operator</h3>

Sağdaki operand soldaki operan'dan büyükse ya da eşitse `True`, aksi durumlarda `False` döndürür.
```py
print(1 <= 2) # Output: True
print(1 <= 1) # Output: True
print(2 <= 1) # Output: False
```

<h2 id="1.4">Logical Operators</h2>

<h3 id="1.4.1"><code>and</code> Operator</h3>

`and` logical operator'ı, bütün karşılaştırma işlemlerinin sonucunun `True` olmasına bakar. Bağlanan karşılaştırma işlemlerinin **hepsinin** kendi içinde sonucu `True` ise genel sonuç `True` , diğer durumlarda ise sonuç `False` çıkar. Örnek:
```py
print(1 == 1 and 2 == 2 and 3 == 3) # Output: True
print(1 == 1 and 2 == 2 and 3 != 3) # Output: False
```
Python bu işlemleri **soldan sağa** okumaya başlar. Bir tane bile `False`'a denk gelirse sonuç `False` olur.

<h3 id="1.4.2"><code>or</code> Operator</h3>

`or` logical operator'ı, en az bir karşılaştırma işlemlerinin sonucunun `True` olmasına bakar. Bağlanan karşılaştırma işlemlerinin **en az bir tanesinin** kendi içinde sonucu `True` ise genel sonuç `True` , bütün karşılaştırma işlemlerinin sonucu `False` ise genel sonuç `False` çıkar. Örnek:
```py
print(1 == 1 or 2 == 2 or 3 == 3) # Output: True
print(1 == 1 or 2 == 2 or 3 != 3) # Output: True
print(1 == 1 or 2 != 2 or 3 != 3) # Output: True
print(1 != 1 or 2 != 2 or 3 != 3) # Output: False
```

<h3 id="1.4.3"><code>not</code> Operator</h3>

`not` operator'ı logical operator değildir. Operator'ların döndürdüğü veya value'ların ifade ettiği boolean değerleri tersine çeviren bir oparetor'dır. Yani `True`'yu `False`, `False`'ı `True` yapar. Örnek:
```py
# Value'ların sahip olduğu boolean değerlere örnek
print(bool(1)) # Output: True
print(not bool(1)) # Output: False
print(bool(0)) # Output: False
print(not bool(0)) # Output: True

# Comparison Operator'ların sahip olduğu boolean değerlere örnek
print((1<2)) # Output: True
print(not (1<2)) # Output:False

# Logical Operator'ların sahip olduğu boolean değerlere örnek
print(1 == 1 and 2 == 2 and 3 != 3) # Output: False
print(not (1 == 1 and 2 == 2 and 3 != 3)) # Output: True
print(1 == 1 or 2 == 2 or 3 != 3) # Output: True
print(not (1 == 1 or 2 == 2 or 3 != 3)) # Output: False
```

<h2 id="1.5">Bitwise operators</h2>

<h3 id="1.5.1"><code>&</code> Bitwise AND Operator</h3>

Bitsel AND `&` operator'ı, her iki operand da `1` ise, `1` döndürür. Aksi halde `0` döndürür. Mantıktaki **"ve"** bağlacına benzer. Doğruluk tablosu:

| `A` | `B` | `A & B` |
| :--: | :--: | :--: |
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

Örnek:
```
12 = 00001100 (In Binary)
25 = 00011001 (In Binary)

00001100 & 00011001 = 00001000

8 = 00001000 (In Binary)
```
Yukarıdaki işlemin Python'da karşılığı:
```py
var1 = 12
var2 = 25
print(f"{var1} & {var2} = {var1 & var2}") # Output: 12 & 25 = 8
```

<h3 id="1.5.2"><code>|</code> Bitwise OR Operator</h3>

Bitsel OR `|` operator'ı, operand'lardan en az biri `1` ise, `1` döndürür. Aksi halde `0` döndürür. Mantıktaki **"veya"** bağlacına benzer. Doğruluk tablosu:

| `A` | `B` | `A \| B` |
| :--: | :--: | :--: |
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 1 |

Örnek:
```
12 = 00001100 (In Binary)
25 = 00011001 (In Binary)

00001100 | 00011001 = 00011101

29 = 00011101 (In Binary)
```
Yukarıdaki işlemin Python'da karşılığı:
```py
var1 = 12
var2 = 25 
print(f"{var1} | {var2} = {var1 | var2}") # Output: 12 | 25 = 29
```

<h3 id="1.5.3"><code>^</code> Bitwise XOR Operator</h3>

Bitsel XOR `^` operator'ı, operand'lar birbirinden farklıysa `1`, aynıysa `0` döndürür. Mantıktaki **"ya da"** bağlacına benzer. Doğruluk tablosu:

| `A` | `B` | `A \^ B` |
| :--: | :--: | :--: |
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

Örnek:
```
12 = 00001100 (In Binary)
25 = 00011001 (In Binary)

00001100 ^ 00011001 = 00010101

21 = 00010101 (In Binary)

12 = 0 0 0 0 1 1 0 0 (In Binary)
     + + + + + + + +
25 = 0 0 0 1 1 0 0 1 (In Binary)
     | | | | | | | |
     V V V V V V V V
21 = 0 0 0 1 0 1 0 1 (In Binary)
```
Yukarıdaki işlemin Python'da karşılığı:
```py
var1 = 12
var2 = 25
print(f"{var1} ^ {var2} = {var1 ^ var2}") # Output: 12 ^ 25 = 21
```

<h3 id="1.5.4"><code>~</code> Bitwise Complement Operator</h3>

Bitsel Complement `~` operator'ı, sadece bir operand'a etki eder. `1`'i `0`'a, `0`'ı `1`'e dönüştürür. Logical NOT operator'ına benzer çalışır. Bir `N` operand'ı düşünün. `N` operand'ı `~` operator'ından etkilenirse `-(N + 1)` değerine dönüşür. Doğruluk tablosu:

| `A` | `~ B` |
| :--: | :--: |
| 0 | 1 |
| 0 | 1 |
| 1 | 0 |
| 1 | 0 |

```
35 = 00100011 (In Binary)
~ 00100011 = 11011100
-36 = 11011100 (In Binary)

-36 = -(35+1)
```
Yukarıdaki işlemin Python'da karşılığı:
```py
var1 = 35
print(~ var1) # Output: -36
```

<h3 id="1.5.5"><code><<</code> Binary Left Shift Operator</h3>

Basitçe, bir binary sayıyı sola kaydırır. Kaydırma işlemi sırasında boşluklar `0` ile tamamlanır. Örnek:
```
22 = 00010110 (In Binary)

00010110 << 2 = 01011000

88 = 01011000 (In Binary)
```
Yukarıdaki işlemin Python'da karşılığı:
```py
var1 = 22
print(var1 << 2) # Output: 88
```
Teknik açıklamak gerekirse; 22 decimal sayısının binary versiyonu `00010110`, 88 decimal sayısının binary versiyonu `01011000`'dir. `22 << 2` işleminden sonra 22 (`N`),  88'e (`N * (2**2)`) dönüşür.

<h3 id="1.5.6"><code>>></code> Binary Right Shift Operator</h3>

Basitçe, bir binary sayıyı sağa kaydırır. Kaydırma işlemi sırasında boşluklar `0` ile tamamlanır. Örnek:
```
32 = 00100000 (In Binary)

00100000 >> 2 = 00001000

8 = 00001000 (In Binary)
```
Yukarıdaki işlemin Python'da karşılığı:
```py
var1 = 32
print(var1 >> 2) # Output: 8
```
Teknik açıklamak gerekirse; 32 decimal sayısının binary versiyonu `00100000`, 8 decimal sayısının binary versiyonu `00001000`'dir. `32 >> 2` işleminden sonra 32 (`N`),  8'e (`N / (2**2)`) dönüşür.

**Not:** Bir decimal sayı üzerinde binary shift operator kullanırsanız, işlemler binary form'da yapılsa bile output decimal formda verilir.

**Not:** C++ gibi low level dillerde shift operator'ları kullanırken negatif sayılarla ve data type'ın tutabileceği data boyutundan daha büyük sayılarla işlemler yapılması sıkıntıydı. Bu kısıtlama, gözlemlediğim kadarıyla Python'da yok.

<h2 id="1.6">Assignment Operators</h2>

<h3 id="1.6.1"><code>=</code> Assignment Operator</h3>

Sağdaki operand'ı soldaki opranda **atamak** (assignment) için kullanılır. Örneğin bir value'yu bir variable'a atamanızı sağlar. Örnek:
```py
a = 15
b = 30
# etc.
```

<h3 id="1.6.2"><code>+=</code> Operator</h3>

`a += 5` işlemi `a = a + 5` anlamına gelmektedir.
```py
a = 5
print(a) # Output: 5
a += 5
print(a) # Output: 10
```

<h3 id="1.6.3"><code>-=</code> Operator</h3>

`a -= 5` işlemi `a = a - 5` anlamına gelmektedir.
```py
a = 5
print(a) # Output: 5
a -= 5
print(a) # Output: 0
```

<h3 id="1.6.4"><code>*=</code> Operator</h3>

`a *= 5` işlemi `a = a * 5` anlamına gelmektedir.
```py
a = 5
print(a) # Output: 5
a *= 5
print(a) # Output: 25
```

<h3 id="1.6.5"><code>/=</code> Operator</h3>

`a /= 5` işlemi `a = a / 5` anlamına gelmektedir.
```py
a = 5
print(a) # Output: 5
a /= 5
print(a) # Output: 1
```

<h3 id="1.6.6"><code>**=</code> Operator</h3>

`a **= 5` işlemi `a = a ** 5` anlamına gelmektedir.
```py
a = 5
print(a) # Output: 5
a **= 5
print(a) # Output: 3125
```

<h3 id="1.6.7"><code>//=</code> Operator</h3>

`a //= 5` işlemi `a = a // 5` anlamına gelmektedir.
```py
a = 5
print(a) # Output: 5
a //= 2
print(a) # Output: 2
```

<h3 id="1.6.8"><code>%=</code> Operator</h3>

`a %= 5` işlemi `a = a % 5` anlamına gelmektedir.
```py
a = 5
print(a) # Output: 5
a %= 2
print(a) # Output: 1
```

<h3 id="1.6.9"><code>&=</code> Operator</h3>

`a &= 25` işlemi `a = a & 25` anlamına gelmektedir.
```py
a = 12
print(a) # Output: 12
a &= 25
print(a) # Output: 8
```

<h3 id="1.6.10"><code>|=</code> Operator</h3>

`a |= 5` işlemi `a = a | 25` anlamına gelmektedir.
```py
a = 12
print(a) # Output: 12
a |= 25
print(a) # Output: 29
```

<h3 id="1.6.11"><code>^=</code> Operator</h3>

`a ^= 5` işlemi `a = a ^ 25` anlamına gelmektedir.
```py
a = 12
print(a) # Output: 12
a ^= 25
print(a) # Output: 21
```

<h3 id="1.6.12"><code><<=</code> Operator</h3>

`a <<= 5` işlemi `a = a << 2` anlamına gelmektedir.
```py
a = 22
print(a) # Output: 22
a <<= 2
print(a) # Output: 88
```

<h3 id="1.6.13"><code>>>=</code> Operator</h3>

`a >>= 5` işlemi `a = a >> 2` anlamına gelmektedir.
```py
a = 32
print(a) # Output: 32
a >>= 2
print(a) # Output: 8
```

<h2 id="1.7"><code>is</code> Identity Operator</h2>

Python'da her objenin geçici bir **identity**'si (kimlik numarası) vardır. Identity'e kısaca **ID** denilir. Bir objenin ID'sini öğrenebilmek için `id()` build-in fonksiyonu kullanılır. Örnek:
```py
a = "Benim ID'm ne?"
print(id(a)) # Output: 2048499024880
```

**ID** ile **bellek adresi** kavramlarını açıklayalım.

Bellek adresi kavramını anlamak için **pointer** kavramını anlamak gerekiyor. Pointer kavramı, `C` dil ailesini alakadar eden bir kavram. Kısaca bellek adresi, bir variable veya objenin bellekte depolandığı alanın adresidir.

ID kavramı bellek adresinden farklı bir kavramdır. Bellek adresi fiziksel bir belleği işaret ettiği için eşsizdir. Ama ID eşsiz değildir. Farklı variable'lar aynı ID'ye sahip olabilirler çünkü Python'da aynı value ya da obje için farklı ID'ler oluşturulmaz, aynı value'yu barındıran variable'lar aynı ID'ye sahiptir. Örnek:
```py
b1 = 1000
b2 = 1000

print(id(b1))   # Output: 2254419109904
print(id(b2))   # Output: 2254419109904
print(id(1000)) # Output: 2254419109904
```
ID'yi, Python'un bir obje veya value'ya atıfta bulunmak (refers to) için oluşturduğu geçici kimlik gibi düşünebilirsiniz. Python, az yer kaplayan değerleri önbellekte saklarken, büyük çok yer kaplayan değerler için her defasında yeni bir depolama işlemi yapar. Örnek:
```py
a=10
b=9
b+=1
  
print(a,b, sep=", ") # Output: 10, 10
print(a is b) # Output: True
print(id(a)) # Output: 1491813100112
print(id(b)) # Output: 1491813100112
```
Gördüğünüz gibi ilk başta `a` ve `b` farklı value'lara sahip olsa bile son durumda sahip oldukları value'lar az yer kapladığı için aynı id'ye sahip oldu. Tam tersinin örneği:
```py
a=36893488147419103232
b=36893488147419103231
print(id(a)) # Output: 2236630293648
print(id(b)) # Output: 2236630294320

b+=1
print(a == b) # Output: True (value'lar birbirine eşit)
print(a is b) # Output: False (value'lar farklı alanlarda saklanıyor)
print(id(a)) # Output: 2236630293648
print(id(b)) # Output: 2236630294464
```

**`is` operator'ı**, kıyaslanan iki objenin id'lerinin aynı olma durumunu kontrol eder. **`is not` operator'ı** ise, kıyaslanan iki objenin id'lerinin aynı olmama durumunu kontrol eder. Örnek:
```py
a = "Örnek 1"
b = a
print(a is b) # Output: True
print(a is not b) # Output: False

b = "Örnek 2"
print(a is b) # Output: False
print(a is not b) # Output: True
```
`b = a` statement'ına `a`'nın değeri `b`'ye atandığı için, `a` ve `b` aynı id'ye sahip oluyor çünkü aynı bellek adresindeki objeye atıfta bulunuyorlar. Başka bir örnek:
```py
a="Python"
print(id(a)) # Output: a: 2941676186544
b="Pytho"
print(id(b)) # Output: b: 2941676183728
b+="n"
print(id(b)) # Output: b: 2941676564656

print(a,b, sep=" | ") # Output: Python | Python
print(a is b)         # Output: False
print(a is not b)     # Output: True
print(id(a))          # Output: 2941676186544
print(id(b))          # Output: 2941676564656
```
Buradaki olaya **String Concatenation** denir. Daha fazla bilgi için [bu sitedeki String Concatenation başlığına](https://medium.datadriveninvestor.com/how-does-memory-allocation-work-in-python-and-other-languages-d2d8a9398543 "https://medium.datadriveninvestor.com/how-does-memory-allocation-work-in-python-and-other-languages-d2d8a9398543") bakabilirsiniz.

`a` ve `b` son durumda `Python` string'ine sahip olmasına rağmen farklı ID'lere sahiptirler. Çünkü `a` ilk başta `Python`, `b` ilk başta `Pytho` stringine sahip olduğu ve bu iki string birbirinden farklı value'lar oldukları için ilk başta farklı bellek adreslerine atandılar. Bu yüzden aynı string olsalar bile farklı ID'lere sahiptirler.

**Not:** `is` operator'ı, iki operand'ın aynı obje olup olmadığını kontrol eder. `==` operator'ı, iki operand'ın value'larının aynı olup olmadığını kontrol eder. Örnek:
```py
a = "Python"
b = "ython"
b = "P" + b

print(a is b) # Output: False
print(a == b) # Output: True
```

<h2 id="1.8"><code>in</code> Membership Operator</h2>

Sağdaki operand, soldaki operand'ı içeriyorsa (yani soldaki operand, sağdaki operand'ın içinde varsa) `True`, aksi durumlarda `False` döndürür. `not in` kullanarak bunun tam tersi durumları sorgulayabilirsiniz. Örnek:
```py
isim="Python"
harf="P"

print(harf in isim) # Output: True
print(harf not in isim) # Output: False
```

<h1 id="2"><code>:=</code> Assignment Expression</h1>
Assignment expression, bir variable'a değer atama işlemini bir koşul durumunun içinde yapmamıza olanak sağlayarak fazladan bir statement kod yazmaktan bizi kurtarır.

**Assignment expression Kullanmadan:**
```py
giriş = len(input("Adın ne? "))
  
if giriş < 4:
	print("Adın kısaymış.")
elif giriş < 6:
	print("Adın biraz uzunmuş.")
else:
	print("Çok uzun bir adın var.")
```

**Assignment expression Kullanarak:**
```py
if ( giriş := len(input("Adın ne? ")) ) < 4:
	print("Adın kısaymış.")
elif giriş < 6:
	print("Adın biraz uzunmuş.")
else:
	print("Çok uzun bir adın var.")
```

**Not:**  `giriş := len(input("Adın ne? "))` kodunu parantez içinde (yani `(giriş := len(input("Adın ne? ")))` şeklinde) yazmazsanız, ya hata yükseltilecek ya da `if` istenilen şekilde çalışmayacak. Bu yüzden bu operator'ı kullanırken kodu parantez içine yazmalısın.

<h1 id="3">Boolean Type</h1>

Data type'ların duruma göre boolean değerleri `True` ya da `False` olabilir. Örnek:
```py
print(bool("")) # Output: False
print(bool(0)) # Output: False
print(bool(0.0)) # Output: False
print(bool(0 + 0j)) # Output: False
print(bool(False)) # Output: False
print(bool(None)) # Output: False

print(bool(" ")) # Output: True (Boşluk karakteri)
print(bool(1)) # Output: True
print(bool(1.1)) # Output: True
print(bool(1 + 1j)) # Output: True
print(bool(True)) # Output: True
```
**Not:** Boşluk karakteri de bir varlığı ifade eder. İlla bir şeyler yazmak zorunda değilsiniz.

**Not:** `None` değeri, "boş, yok" anlamlarına gelmektedir. Yani bir variable'a `None` atarsanız, Python bunu "Bu variable herhangi bir data içermiyor, boş bir variable." olarak yorumlar ama yine de bellekte o variable için **16 byte** boyutunda yer açar. Çünkü sonuç olarak bir variable bildirmiş (declaration) oluyorsunuz ve Python bu variable'ı daha sonra kullanma ihtimaliniz olduğu için bellekte bu variable'a 16 byte yer açar. `None`, genellikle bir variable'ın içeriğini daha sonra belirlemek istediğinizde kullanılır.

<h1 id="4">Operator Önceliği</h1>

Bir operator'ın önceliğini arttırmak için o operator'ın bulunduğu işlemi parantez `()` içine alabilirsiniz. Örneğin `2 + 2 * 2` işlemindeki `+` operator'ının önceliğini arttırmak için bu işlemi `(2 + 2) * 2` şeklinde yazabilirsiniz. Aşağıdaki operator'lar, en öncelikliden son öncelikliye doğru olmak üzere yukarıdan aşağıya sıralanmıştır.
| Operator | Description |
| :----------: |-------------|
| `()` | Parentheses |
| `**` | Exponent |
| `+x`, `-x`, `~x` | Unary plus, Unary minus, Bitwise NOT |
| `*`, `/`, `//`, `%` | Multiplication, Division, Floor division, Modulus |
| `+`, `-` | Addition, Subtraction |
| `<<`, `>>` | Bitwise shift operators |
| `&` | Bitwise AND |
| `\^` | Bitwise XOR |
| `\|` | Bitwise OR |
|  `==`, `!=`, `>`, `>=`, `<`, `<=`, `is`, `is not`, `in`, `not in` | Comparisons, Identity, Membership operators |
| `not` | Logical NOT |
| `and` | Logical AND |
| `or` | Logical OR |

Daha ayrıntılı bilgi için [tıklayınız](https://docs.python.org/3/reference/expressions.html#operator-precedence "https://docs.python.org/3/reference/expressions.html#operator-precedence").

**Not:** Yukarıdaki linkte ilk sırada olan Binding'in ne olduğunu öğrenmek için [tıklayınız](https://mathieularose.com/python-variables "https://mathieularose.com/python-variables").

[Sonraki Ders](https://github.com/e-k-eyupoglu/python_tutorial/blob/main/python_tutorial/statements/statements_and_keywords.md)
