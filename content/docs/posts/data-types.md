---
title: "Veri Tipleri (Data Types) "
weight: 1
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

# GO Dilinde Veri Tipleri (Data Types in GO)

GO programlama dilinde veri tipleri varsayılan olarak mevcuttur. Ayrıca kullanıcılar tarafından da tanımlanabilirler.

{{<hint info>}}
- **Varsayılan veri tipleri**  program kurulduğu an itibariyle tanımlı olan veri tipleridir. 
{{</hint>}}

{{<hint info>}}
- **Kullanıcı tanımlı veri tipleri** ise kullanıcı tarafından sisteme tanıtılan ve kullanılan veri tipleridir.

{{</hint>}}


## Veri Tiplerinin Gruplanması

Genel olarak veri tipleri dört ana başlık altında toplanabilir

![data-types](/img/datatypes.png)


1. **Basic type (Temel Veri Tipi ) :** Sayılar, metin ve bool ifadeler bu kategoriye girer. *int, float, string, bool, complex*
2. **Aggregate type (Toplanmış Veri Tipi):**  Dizi ve yapılar bu kategoriye girer. *array, struct*
3. **Reference type (Referans Veri Tipi):** İşaretçiler, dilimler, haritalar, işlevler ve kanallar bu kategoriye girer.  *pointer, slice, map, function, channel*
4. **Interface Type (Arayüz Veri Tipi) :** Arayüzler bu veri tipinde yer alır.  *interface*

-----------------------------

## 1. Temel Veri Tipleri (Basic Types)

1. String (*string*)
2. Int (*int8, int16*, *int32, int64*)
3. Float  ( *float32, float64*)
4. Boolean (*bool*)
5. Complex(complex)


### Int (Integer-Tamsayı)

Tam sayı değerlerlerinin program hafızasında tutulduğu veri tipidir.


`int` tanımlaması aşağıdaki şekilde yapılır.

```go
var degiskenAdi int = 32
```

İkinci bir tanımlama yöntemi ise aşağıdaki şekildedir.

```go 
degiskenAdi := 35 
``` 

Peki bu sayı tipleri GO programlama tipinde nasıl tanımlanır? Bir örnek ile konuyu açıklamaya çalışalım. 


```go
package main 
import ("fmt")

func main(){

	var matematikNotu int8 = 85
	var edebiyatNotu int8 = 92
	fizikNotu = 65

	fmt.Println(matematikNotu, edebiyatNotu, fizikNotu)
	// ortalama 
	fmt.Println((matematikNotu + edebiyatNotu + fizikNotu)/3)
}
```

Yukarıda tanımlandığı gibi sisteme `int` ifadesi ile bir değişken tanımladığımızda bu değişken sistem hafızasında `integer` olarak tutulur ve bu şekilde işlemlere dahil edilir. 

Yukarıdaki örnek incelendiğinde `matematikNotu` isimli bir `int` ifadesi tanımladık. Bu değerler 1 ile 100 arasında olacağından dolayı veri tipi olarak `int8` seçtik. Bu seçim sayılarımızın -127 ve 128 arasında olacağından dolayıdır. Aynı şekilde `edebiyatNotu` isimli bir `int8` ifade tanımladık. 


#### Int Veri Tipinin Hafızada Kapladığı Yer

Tanımladığımız verileriin hafızada kapladığı yer, programcıların en çok kafasını kurcalayan sorulardan biridir. Yazdığınız programın performansını etkiler ve bu sebeple bu temelin ne olduğu ile ilgili bir ön bilgi edinilmesi önemlidir.

Hafızada kapladığı yere ve oluşturulma usullerine göre `int` veri tipleri aşağıda yer almaktadır.

| Veri Tipi   | Açıklama                                                                                                                            | Veri Aralığı                                                                          |
| ----------- | ----------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| **int8**    | 8-bit signed integer                                                                                                                | -127 ve 128 değerleri arasında yer alır ( signed integer)                             |
| **int16**   | 16-bit signed integer                                                                                                               | -32,768 ve +32,767 değerleri arasında yer alır                                        |
| **int32**   | 32-bit signed integer                                                                                                               | -2147483648 to 2147483647 değerleri arasında yer alır                                 |
| **int64**   | 64-bit signed integer                                                                                                               | -9,223,372,036,854,775,808 ve  9,223,372,036,854,775,807 değerleri arasında yer alır. |
| **uint8**   | 8-bit unsigned integer                                                                                                              | 0 ve 255 değerleri arasında yer alır                                                  |
| **uint16**  | 16-bit unsigned integer                                                                                                             | 0 ve 65535	değerleri arasında yer alır                                                |
| **uint32**  | 32-bit unsigned integer                                                                                                             | 0 ve 4294967295 değerleri arasında yer alır                                           |
| **uint64**  | 64-bit unsigned integer                                                                                                             | 0 ve (2^64) değerleri arasında yer alır                                               |
| **int**     | Hem int hem de uint, 32 veya 64 bit olmak üzere aynı boyutu içerir.                                                                 |                                                                                       |
| **uint**    | Hem int hem de uint, 32 veya 64 bit olmak üzere aynı boyutu içerir.                                                                 |                                                                                       |
| **rune**    | İnt32 ile eşanlamlıdır ve ayrıca Unicode kod noktalarını temsil eder.                                                               |                                                                                       |
| **byte**    | uint8 ile eşanlamlıdır.                                                                                                             |                                                                                       |
| **uintptr** | İşaretsiz bir tamsayı (unsigned integer) türüdür. Genişliği tanımlanmamıştır, ancak bir işaretçi değerinin tüm bitlerini tutabilir. |
|             |

{{<hint info>}}
 32 bit , 64 bit veri tiplerinin mevcut olmasının temel sebebi tutulacak verinin sistemde kaplayacağı yeri düzenlemek içindir.
{{</hint>}}

**Birden çok veri tipinin olması sistem hafızasında kaplanacak yer sorunu ile ilgilidir.** Milyonlarca sayıdan oluşan bir veri setinin olduğunu düşünelim. Bu sayıların ise 1 ile 1000 arasında yer aldığını düşünelim. Eğer sisteme int16 ( 16 bit tamsayı ) veri tipinde veri girileceğini belirtmez isek sistem bu veri tipleri için int64 (64 bit tamsayı ) imiş gibi muamele edip her bir sayı için 2^64 'lük bir yer ayıracaktır. Böylece yapılan işlemler için ayrılan hafıza muazzam boyutlarda artacaktır. 


### Float (Ondalık) 

Virgül ya da nokta ile ayrılmış ondalıklı değerleri ifade eder. 
`int` ifadelerinde olduğu gibi `float` ifadelerde de hafızada kapladığı yere bakılarak bir seçim yapılır. 


```go
var sicaklik float32 = 33.25
```

Diğer bir tanımlama ise şu şekilde yapılabilir. 


```go
sicaklik := 33.25 
```


Veri tipi tanımlaması aşağıdaki tabloya göre belirlenir.

| Veri Tipi | Açıklama                              | Değer Aralığı                                                                                                                                                                                            |
| --------- | ------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| float32   | 32-bit IEEE 754 floating-point number | İşaretli bir 32 bit tamsayı değişkeni maksimum 231 − 1 = 2,147,483,647 değerine sahipken, bir IEEE 754 32 bitlik taban-2 kayan noktalı değişkenin maksimum değeri (2 − 2−23) × 2127 ≈ 3.4028235 × 1038 . |  |
| float64   | 64-bit IEEE 754 floating-point number |                                                                                                                                                                                                          |  |


Float ifadelere ait bir örnek aşağıda yer almaktadır.

```go
package main
import "fmt"

func main() {
	//float verilerin tanımlanması
	a := 20.45
	b := 34.89
	//Cikartma islemi
	c := b-a
	// Sonuc Görüntülemesi
	fmt.Printf("Result is: %f", c)
	// Vier türünün görüntülenmesi 
	fmt.Printf("\nThe type of c is : %T", c)
}
```

Örneğimizde `a` ve `b` olmak üzere iki adet `float` değişken tanımlanmıştır. İki değere de `float64` atanmıştır.


{{<hint warning>}}
**HATIRLATMA:**
Eğer float ifade tanımlanırken bir veri tipi seçilmeden tanımlama yapılırsa GO otomatik olarak float64 seçimi yapar. 
{{</hint>}}

-------------------------------

###  String (Metin)

String veri türü metin verilerinin bir dize olarak tutulduğu veri tipidir. Bu veriler baytlardan oluşur.


`string` ifadeler aşağıdaki şekilde tanımlanır. 

```go 
var degiskenAdi string = "metin ifadesi"
```

ikinci bir tanımlama yöntemi ise aşağıdaki şekildedir.

```go 
degiskenAdi := "metin ifadesi"
```

Şimdi bir uygulama örneği ile devam edelim.

```go

package main

import "fmt"

func main() {

stringIfadesi := "GOKAYBURUC.DEV"
	
// String ifadesinin uzunluğunun görüntülenmesi
fmt.Printf("Length of the string is:%d",
								len(stringIfadesi))
	
// String ifadesinin görüntülenmesi
fmt.Printf("\nString is: %s", stringIfadesi)
	
// String ifadesinin veri türünün görüntülenmesi 
fmt.Printf("\nType of str is: %T", stringIfadesi)
}

```


### Boolean (Mantıksal) 

Bir veri tipinin mantıksal değerler olan `true` ya da `false` döndürdüğü ifadelerdir.  Bir koşullu işlemin sonucu bilgisayar tarafından geçerli olduğu noktada `true` geçersiz olduğu noktada ise `false` değerini döndürür. 

| Veri Tipi | Açıklama                                            |
| --------- | --------------------------------------------------- |
| `true`    | koşul sınamasının olumlu olması sonucu dönen değer  |
| `false`   | koşul sınamasının olumsuz olması sonucu dönen değer |

----------------------------------------------------

#### Boolean Uygulaması
```go
package main 

import "fmt"

func main(){

	var a = 25
	var b = 45

	a=25
	b=45

	//mantıksal sorgu 
	sorguBir := (a > b) 
	sorguİki := (a < b) 
	sorguUc := (a == b) 
	sorguDort := (a != b)

	fmt.Println(sorguBir)
	fmt.Println(sorguİki)
	fmt.Println(sorguUc)
	fmt.Println(sorguDort)


	// Deger ataması
	var ehliyet bool = true
	var ruhsat bool = false

	fmt.Printf("Ehliyet : %v\nRuhsat : %v \n", ehliyet,ruhsat)
}

```


### Complex ( Karmaşık ) 

Matematik gösterimi i ve j ye bağlı olan ve iki boyutlu bir analitik düzlem üstünde gösterilen sayılar için sistem hafızasında tutulan veri tipidir. 

Komplek Sayi  `j + Xi`  seklinde yazılır. Yani sayının bir imajiner bir de reel kısmı mevcuttur. Sonuçlarımız da bu şekilde döndürülecektir.


Yazım şekili

```go 
var degiskenAdi complex64 = complex(2,15)
```

ikinci yazım şekli 

```go
var degiskenAdi := complex(2,15)
```

Komplex sayı veri tipine ait tablo aşağıda yer almaktadır.

| Veri Tipi  | Açıklama                                                            |
| ---------- | ------------------------------------------------------------------- |
| complex64  | `float32` değerini reel (`j`) ve imajiner (`i`) kısımda tutan deger |
| complex128 | `float64` değerini reel (`j`) ve imajiner(`i`) kısımda tutan değer  |


Aşağıda açıklama örneğimiz yer almaktadır.

```go
// Go program to illustrate
// the use of complex numbers
package main

import "fmt"
 
func main() {
     
   var a complex128 = complex(6, 2)
   var b complex64 = complex(9, 2)

	//
   fmt.Println(a)
   fmt.Println(b)
    
   // Display the type
  fmt.Printf("The type of a is %T and "+
            "the type of b is %T", a, b)
}

```


## Kaynakça 
1.  [https://www.geeksforgeeks.org/data-types-in-go/](https://www.geeksforgeeks.org/data-types-in-go/)
2. [https://go.dev/tour/basics/11](https://go.dev/tour/basics/11)
3. [https://www.programiz.com/golang/data-types](https://www.programiz.com/golang/data-types)