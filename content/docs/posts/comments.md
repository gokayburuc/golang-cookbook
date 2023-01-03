---
title: "5. Yorum İfadeleri - Comments"
weight: 5
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

# Yorum İfadeleri - Comments

Yorum ifadeleri, GO programlama dilinde iki farklı şekilde karşımıza çıkmaktadır. 

- Tek Satır Yorum İfadeleri (Line Comments)
- Çok Satır Yorum İfadeleri (Multiline Comments)


## Tek Satır Yorum İfadeleri 

Tek satır yorum ifadeleri, işleme dahil olmasını istemediğiniz ve koda ait tek satırlık yorumların olduğunu belirtmek için kullanılır. Satırın başına `//` iki adet eğik çizgi (double slash) ile belirtilir.

```go
// Tek satır yorum ifadesidir 
```


## Çok Satırlı Yorum İfadeleri

Çok satırlı yorum ifadeleri, geniş açıklama yapılmak istendiğinde ilk satıra `/*` ve son satırın bitirişine de `*/` eklemek suretiyle yazılan yorum ifadeleridir.

```go

/* Ilk satır yorum
ikinci satır yorum 
son satır yorum */

```

## Yorum İfadelerinin Konumları 

Yorum ifadeleri işleme dahil etmek istediğimiz kodun üstünde, altında, ve sağ yanında yer alabilir. 


Bir örnek vermek gerekirse hepsinin bir arada kullanıldığı örneğimiz aşağıda yer almaktadır.

```go
package main 
import "fmt"

func main(){
    EkranaYazdir()
}

func EkranaYazdir(){
    /* Ekrana yazdır programımız,
    Yorum ifadeleri haricinde 
    işleme dahil olan herşeyi 
    ekrana yazdıracaktır.*/


    //isim ve soyisim degiskenleri tanımladık.
    var name string = "Gokay" // ad degiskeni
    var surname string = "BURUC"// soyad degiskeni
    
    // ekrana isim ve soyisim degiskenlerini yazdırıyoruz
    fmt.Println("ISIM:", name , "SOYISIM:",surname)
    // islem bitisinde terminal üzerinden go run dosyaAdi yazarak calistiriyoruz.
}
```

Kodumuzu çalıştırdığımızda aşağıdaki ekran çıktısını alacağız. 

```bash
ISIM: Gokay SOYISIM: BURUC
```

Görüldüğü üzere yorum satırlarının hiçbir işlemimize dahil olmamıştır. Ne çalıştırılan kodun üstünde yer alan satırlar ne yanındakiler ne de altındakiler hiçbir şekilde işlemde yer almamaktadır.
