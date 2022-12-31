---
title: "Anahtar Durum İfadeleri (Switch Case )"
weight: 4
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

# Anahtar Durum İfadeleri (Switch Case)

Switch  ifadesi, çok yollu bir dal ifadesidir. İfadenin değerine dayalı olarak yürütmeyi bir kodun farklı bölümlerine aktarmak için etkili bir yol sağlar. Basit bir ifade ile demiryolu makası gibi düşünülebilir.


Go dili, iki tür anahtar deyimini destekler:

1.  **İfade Switch**
2.  **Tip Switch**

#### İfade Switch

İfade switch, **C**, **C++**, **Java** dilindeki switch ifadesine benzer. İfadenin değerine bağlı olarak yürütmeyi kodun farklı bölümlerine göndermenin kolay bir yolunu sağlar.

**Syntax:**

```go
switch optstatement; optexpression{
case expression1: Statement..
case expression2: Statement..
...
default: Statement..
}
```


Önemli Noktalar:**

- `switch` ifadesi sonrasında yazılan `optexpression` ve `optstatement` opsiyonel ifadelerdir. 
- Eğer hem `optexpression` hem de  `optstatement` ifadede mevcut ise ikisinin arasına noktalı virgül `;` işareti koymak gereklidir. 
- Eğer `switch` herhangi bir ifade içermiyorsa, derleyici ifadenin `true` olduğunu varsayar. 
-  `optstatement` değişken tanımlamaları, artış ya da atama durumları, fonksiyon çağrıları vb. gibi basit durumları içerir.
- Eğer değişken `optstatement` içerisinde görüntülenirse, değişkenin aralığı switch ifadesi ile sınırlıdır.
- `switch` ve `case` ifadeleri dahili olarak `break` ile durdurulmaz. Fakat şart sağlandığında otomatik olarak anahtar değeri değişir ve bir sonraki aşamaya geçilir. 
-   `default` ifadesi `switch` ifadesinde isteğe bağlı olarak kullanılır.
-   `case` ifadesi birden fazla değişken içerirse bu ifadeler **virgül (,)** ile ayrılırlar.
-  Eğer `case` ifadesi herhangi bir ifade içermiyorsa, sistem bu ifadenin değerinin `true` kabul eder.



**Example 1:**

```go
package main

import "fmt"

func main(){ 

    switch day:=4; day {
    case 1:
        fmt.Println("Pazartesi")
    case 2:
        fmt.Println("Salı")
    case 3:
        fmt.Println("Çarşamba")
    case 4:
        fmt.Println("Perşembe")
    case 5:
        fmt.Println("Cuma")
    case 6:
        fmt.Println("Cumartesi")
    case 7:
        fmt.Println("Pazar")
    default:
        fmt.Println("Geçerli Bir gün Girmediniz!")
        return
    }
}
```

**Çıktı:**

```go
Perşembe
```

**Example 2:**

```go
package main 

import (
	"fmt"
)

func main(){

	var secim int = 3 

	switch secim {
	case 1:
		fmt.Println("Cemil")
	case 2:
		fmt.Println("Numan")
	case 3: 
		fmt.Println("Şaban")
	case 4:
		fmt.Println("Haydar")
	default:
		fmt.Println("Afrikalı Nuri")
		return
	}
}
```

**Output:**

```go 
Şaban
```

**Example 3:**

`

```go
package main

import "fmt"

func main() {

	var secim string = "Huseyin"

	switch secim{
	case "Ahmet","Mehmet":
		// "Ahmet" ya da "Mehmet" verilirse bu uyarı gelir
		fmt.Println("Değil")
	case "Cemil", "Huseyin","Numan":
		// eğer verilen 3 degerden biri secimde tanımlanırsa bu uyarı gelir
		fmt.Println("Alakası Yok!")
	case "Gokay":
		fmt.Println("Aradığınız adamı buldunuz!")
	default:
		fmt.Println("Bir adam ismi girin!")
		return
	}
}
```

**Output:**

```go
Alakası Yok!
```

#### Tip Switch (Type Switch)

Tip switch anahtarı, türleri karşılaştırmak istediğinizde kullanılır. Bu anahtarda, durum, anahtar ifadesinde bulunan tür ile karşılaştırılacak olan türü içerir.

**Syntax:**

```go 
switch optstatement; typeswitchexpression{
case typelist 1: Statement..
case typelist 2: Statement..
...
default: Statement..
}
```


**Önemli noktalar:**

- Opsiyonel ifade, yani optstatement, switch ifadesindeki ile benzerdir.
- Bir `optstatement` birden fazla değer içeriyorsa ve bu değerler virgül(,) ile ayrılırlar.
- `switch` deyimi türünde, case ve default deyimi herhangi bir break deyimi içermez. Ancak, programınız gerekliyse, `break` ve `fallthrough` ifadesini kullanmanıza izin verilir.
- `typeswitchexpression`' de  `default`  isteğe bağlıdır.
- `typeswitchexpression`, sonucu bir tür olan bir ifadedir.
- `typeswitchexpression` içinde `:=` operatörü kullanılarak bir ifade atanırsa, bu değişkenin türü, case yan tümcesinde bulunan türe bağlıdır. `case` yan tümcesi iki veya daha fazla tür içeriyorsa, değişkenin türü, `typeswitchexpression` içinde oluşturulduğu türdür.

**Example:**

```go 

package main

import "fmt"

func main() {
	var value interface{}
	switch q:= value.(type) {
	case bool:
	fmt.Println("value is of boolean type")
	case float64:
	fmt.Println("value is of float64 type")
	case int:
	fmt.Println("value is of int type")
	default:
	fmt.Printf("value is of type: %T", q)
	}
}

```

**Output:**

```go
value is of type: <nil>[Finished in 634ms]
```

KAYNAKÇA: 

1.[https://www.geeksforgeeks.org/type-switches-in-golang/](https://www.geeksforgeeks.org/type-switches-in-golang/)
2.[https://www.geeksforgeeks.org/switch-statement-in-go/](https://www.geeksforgeeks.org/switch-statement-in-go/)


```go 
package main 
import "fmt"
```