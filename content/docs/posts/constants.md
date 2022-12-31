---
title: "Sabitler (Constants)"
weight: 3
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

# Sabitler (Constants)



Constant ifadeler sabitler olarak bilinirler.  **Değişken ifadelerinden farklı olarak, bir defa değer atandığı an itibariyle sistemde sabit kalırlar.**  İşleme tabi tutulsalar dahi, işlem bitişinde yine değerleri sabit olmaktadır.


## Yazım Biçimi - Snytax 

```go 
const ifade = deger
```


{{<hint warning>}}
HATIRLATMA: 
 `const` ifadeleri `scope` içinde ve dışında tanımlanabilir. 
{{</hint>}}


## const İfadelerin Veri Türleri 

`const` ifadeler aşağıda yer alan tüm veri tiplerinde veri taşıyabilirler.

- Integer - int 
- Float - float32, float64 vs.
- String - string 
- Boolean - bool 
- Character - tek bir karakter 

### const İfadelerin Kullanımı

[GeeksForGeeks](https://www.geeksforgeeks.org/constants-go-language/) web sitesinden alınan örnek ifade aşağıda verilmiştir.

```go
package main

import "fmt"

const PI = 3.14

func main()
{
	const GFG = "GeeksforGeeks"
	fmt.Println("Hello", GFG)

	fmt.Println("Happy", PI, "Day")

	const Correct= true
	fmt.Println("Go rules?", Correct)
}

```


ifadede görüldüğü üzere `PI` isimli `float` bir sabit değer tanımlanmıştır. Burada dikkat etmemiz gereken nokta `const` ifadelerinin `scope` (fonksiyon tanımlanan aralık) dışında da tanımlanabildiğidir. 

#### Yazılmamış (Untyped) ve Yazılı (Typed) Sayısal Sabitler:  
Yazılan sabitler (*typed constants*), sabitlenmiş değişkenler gibi çalışır, yalnızca aynı türle birlikte çalışabilir ve tür bilgisi yazılmamış sabitler (*untyped constants*), değişmezler gibi çalışır, benzer türlerle birlikte çalışabilir. 

> Sabitler (constants), Go'da bir türle veya türsüz olarak bildirilebilir. 

Aşağıda, hem `typed` hem de `untyped` biçimde belirtilmiş ifadeler örneklenmiştir.


```go

//veri tipi belirtilmemiş
const untypedInteger             = 123
const untypedFloating            = 123.12

//veri tipi belirtilmiş
const typedInteger  int             = 123
const typedFloatingPoint   float64  = 123.12
```


## Yazılı ve Yazılı Olmayan Sabitlere Ait Örnek Uygulama

Aşağıda belirli sabitler tanımlanmıştır ve bu sabitlerle rastgele işlemler yapılmıştır.


```go
package main

import "fmt"


const Pi = 3.14 // untyped 
const Euro float32 = 18.78 // typed 
const yil = 2022 // untyped 
const kurulus int = 1923 //typed

func main() {

test := Euro * yil // tanımli sabit Euro ile tanımsiz sabit yil carpiliyor
test2 := Pi * Euro // tanımli sabit Euro ile tanımsız sabit Pi carpiliyor
test3 := Pi * yil // tanımsız sabit pi ile tanımsız sabit yil carpiliyor


/* a
test3 := kurulus * Euro
yukarıdaki ifade hata verecektir
cünkü kurulus tanımlı sabit Euro da tanımlı sabittir 
ve veri tipleri farklıdır. tip dönüşümü gerekmektedir.
kurulus int degerini float32 'ye cevirerek isleme sokabiliriz.*/ 

test4 := float32(kurulus) * Euro

fmt.Println(test)
fmt.Println(test2)
fmt.Println(test3)
fmt.Println(test4)

}
```

## Tip Dönüşümü 

İfademizde notları incelediyseniz tanımlama sırasında bir noktada tip dönüşümü yaptık. Bunun sebebi ise bu değerin tip tanımlı bir sabit olmasıdır. Bu sebepten dolayı GO otomatik olarak uygun değere çeviremez ve yeniden tip elle tip tanımlaması yapmamız gerekir. 

```go 
// tip dönüşümü
test4 := float32(kurulus) * Euro //int veri tipini float32 veri tipine cevirdik
``` 


## Sabit Türleri

GOLANG içerisinde sabit türleri çeşitli olmakla birlikte temel başlıklar altında toplanabilir.

1. Metin Sabitleri  -  String Literals
2. Sayısal Sabitler - (Integer, Float , Complex )
3. Boolean Sabitleri 

### Metin Sabitleri 

- Go, iki tür değişmez `string`yi destekler, yani ” ” (çift tırnak stili) ve ' '(geri alıntı).  
- `string` ifadeler + ve += operatörleriyle birleştirilebilir.  
- Bir `string`, karakter değişmezlerine benzer karakterler içerir: düz karakterler (plain characters), kaçış dizileri (escape sequences ) ve evrensel karakterler (universal characters). Ve bu, yazılmamış karakterlerdendir.  
- `string` türlerinin sıfır değerleri, değişmez olarak ” ” veya ” ile gösterilebilen boş `string`lerdir.  
- `string` türlerinin tümü, == (equal) , != (not equal) ve (aynı türlerin karşılaştırılması için) gibi operatörler kullanılarak karşılaştırılabilir.


```go

package main

import "fmt"

func main()

{
	const A = "GOKAYBURUC.DEV"
	var B = "Medium Blog Page"
	
	// Concat strings. - String ifadelerin birleştirilmesi 
	var karsilama = A+ " " + B
	karsilama += "!"
	fmt.Println(karsilama)
	
	// Compare strings. - String ifadelerin karşılaştırılması
	fmt.Println(A == "GOKAYBURUC")
	fmt.Println(B < A)
}

```


### Boolean Sabitleri 

`true` ve `false` değeri alan sabitlerdir. 

```go

package main

import "fmt"

const Pi = 3.14

func main()
{
	// degeri true olan bir const tanımladık
	const trueConst = true
	
	// Type definition using type keyword - Veri Tipi Tanımlama
	type myBool bool

	// const ifadeyi bir değişkene atadık
	var defaultBool = trueConst // izin verilir
	var customBool myBool = trueConst // izin verilir
	
	// defaultBool = customBool //  izin verilmez
	fmt.Println(defaultBool)
	fmt.Println(customBool)
}

```


### Tamsayı (Integer) Sabitleri 

Tamsayı integer sabitleri çeşitli değişkenlik göstermektedir. 

Burada sayı yazılımları :
- Decimal : Ondalık ( 10 luk sayı sistemi ) 
- Octal  : Sekizlik ( 8 'lik sayı sistemi )
- Hexadecimal : On altılık (16'lık sayı sistemi)
- Int : Tamsayı
- Unsigned Int :  İmzasız integer
- Long : Uzun veri tipi  - C Kökenli bir veri tipidir. ( 2^64 ifadesini getirir)


```go
85         /* decimal */
0213       /* octal */
0x4b       /* hexadecimal */
30         /* int */
30u        /* unsigned int */
30l        /* long */
30ul       /* unsigned long */
212         /* Legal */
215u        /* Legal */
0xFeeL      /* Legal */
078         /* Illegal: 8 is not an octal digit */
032UU       /* Illegal: cannot repeat a suffix */
```

Örnek ifademizi tanımlayalım.

```go 
package main
import "fmt"

const ekmek int = 5
func main() {

//const ekmek = 5

var sepet int = 30
yarimSepet := sepet / 2
yarimEkmek := ekmek / 2
fmt.Println(yarimEkmek)
fmt.Println(yarimSepet * ekmek)

// bu ifade hata verecektir. sabit bir deger ikinci bir atama kabul etmez
ekmek = ekmek / 2
fmt.Println(ekmek)

}
```


### Ondalık (Float) Sabitleri 

Ondalık sabitler olarak tanımlanır.

```go
3.14159       /* Legal */
314159E-5L    /* Legal */
510E          /* Illegal: incomplete exponent */
210f          /* Illegal: no decimal or exponent */
.e55          /* Illegal: missing integer or fraction */
```


### Kompleks Sayı (Complex) Sabitleri 

2 değerle tanımlanan komplex sayılar için kullanılır. Aşağıdaki iki tanımlama da geçerli bir tanımlamadır.

```go
const ilk = (0.0, 0.0) 
const sinirlar = (-123.456E+30, 987.654E-29)
```


## Tip Tanımlama - Type Definition
Type Definition (Tip Tanımlama): GOLANG içinde eğer yeni bir tip tanımlamak istiyorsanız 
```go
//type tipAdı veriTürü
type benimVeriTipim string
```
sentaks değerini izlersiniz.




### Kaynakça 

1.  [https://go.dev/tour/basics/15](https://go.dev/tour/basics/15)
2.  [https://www.geeksforgeeks.org/constants-go-language/](https://www.geeksforgeeks.org/constants-go-language/)
