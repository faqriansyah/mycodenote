# mycodingnote
Ini adalah halaman github yang ditujukan untuk diri saya sendiri sebagai catatan belajar, yang didasarkan pada course-course berikut :
1. Programmer Zaman Now - TUTORIAL PHP OOP BAHASA INDONESIA : https://youtu.be/_P2t0lCzU-Q?si=iE2RYr11tIr7kBdq
2. Study.com - oop-object-oriented-programming-objects-classes-interfaces.html : https://study.com/academy/lesson/oop-object-oriented-programming-objects-classes-interfaces.html



# PHP OOP (DASAR)

## Silabus 
- Class
- Object
- Properties
- Function
- This
- Constant
- Self 
- Constructor & Destructor 
- Inheritance
- Namespace
- Import (namespace)
- Visibility


## Apa itu OOP?
- Pemrograman berbasis objek
- Objek adalah data yang berisi properties/attributes dan method/function/behavior
- Class adalah blueprint atau cetakan untuk membuat objek, berisi deklarasi semua properties dan function yang dimiliki object

## Class
Class bisa dibayangkan sebagai blueprint atau sebagai cetakan untuk membuat objek, karena memang objek itu adalah hasil instance dari sebuah Class

jika merujuk pada pengertian yang ada di Wikipedia yang sudah diterjemahkan, Class memiliki pengertian sebagai berikut :

Class adalah template kode program yang dapat diperluas untuk membuat objek, memberikan nilai awal untuk status (variabel anggota) dan implementasi perilaku (fungsi atau metode anggota).

Dari pengertian tersebut sudah dijelaskan bahwa Class memiliki nilai awal yang akan bisa dibuat variasinya saat objek dibuat dari sebuah Class.

tidak apa-apa kalau masih terkesan abstrak, yang penting terus belajar.


Untuk membuat class adalah dengan menggunakan keyword `class`.

```
Class Person {

}
```

dalam kode di atas adalah sintaks untuk membuat sebuah Class.

## Object
Class yang sudah dibuat tidak akan berguna jika tidak digunakan untuk membuat objek, maka dari itu kita harus membuat instance dari Class tersebut. 

Objek adalah hasil instance dari class, untuk menggunakan object, gunakan keyword `new` diikuti nama class dan ()

```
$person1 = new Person();
```

## Properties
di dalam sebuah kelas kita bisa membuat sebuah variabel lokal yang disebut properties.

Properties Adalah data (variabel) yanng disimpan di dalam object, untuk membuatnya dengan menggunakan keyword `var` lalu nama propertiesnya

```
Class Person {
  var $name = "Budi";
}
```

Untuk bisa mengakses value dari properties, gunakan `->`

```
$person1 = new Person();

echo $person1->name;
```

properti juga bisa dimodifikasi valuenya dengan menggunakan objek 

```
$person1 = new Person();
$person1->name = "Budi";
```

## Function
ketika objek dibuat kita menginginkan agar objek tersebut bisa melakukan sesuatu, maka Method pun berperan di sini

Method bisa didefinisikan sebagai "perilaku" suatu objek.

Function/method bisa dideklarasikan di dalam class dan diakses menggunakan `->`

```
Class Person {
  var $name = "Budi";

  function greeting($name) {  
    echo "Halo $name";
  }
}

$person1 = new Person();
$person1->greeting("Samsul");
```

## this
kita akan membutuhkan value dari sebuah properties atau method yang berada di dalam kelas, seprrti yang sudah dijelaskan sebelumnya untuk bisa mengakses value dari sebuah kelas kita bisa menggunakan tanda `->`.

Namun jika properties tersebut berada di dalam kelas yang sama maka kita bisa menggunakan kata kunci `this`

```
Class Person {
  var $name = "Budi";

  function greeting($name) {
    echo "Halo $name, nama saya $this->name";
  }
}

$person1 = new Person();
$person1->greeting("Samsul");
```

jika kita ingin mengakses sebuah method maka caranya adalah seperti ini 

```
Class Person {
  var $name = "Budi";

  function sayHi() {
    echo "Halo dari method!";
  }
  function greeting($name) {
    echo "Halo $name, nama saya $this->name";
    $this->sayHi();
  }
}

$person1 = new Person();
$person1->greeting("Samsul");
```

## constant
constant adalah data yang tidak bisa diubah, biasanya digunakan untuk menyimpan data permanen untuk sebuah Class. Misalnya untuk versi aplikasi.

Untuk membuatnya kita bisa menggunakan keyword `const` diikuti nama constantnya. Untuk bisa mengaksesnya gunakanlah `NamaClass::NamaConstant`

```
Class Person {
  const GENDER = "Pria";
}

echo Person::GENDER;
```

## self keyword 
`self` merupakan kata kunci yang digunakan untuk mengakses constant jika di dalam class yang sama, alih-alih menggunakan `NamaClass::NamaConstant`, kita bisa menggunakan `self::NamaConstant`

```
Class Person {
  const GENDER = "Pria";
  var $name = "Budi";

  function greeting($name) {
    echo "Halo $name, nama saya $this->name dan saya adalah seorang self::GENDER ";
  }
}

$person1 = new Person();
$person1->greeting("Samsul");
```

## constructor dan destructor 
Constructor berperan sebagai function yang akan pertama kali dipanggil saat instance dari sebuah kelas itu dibuat. 

Constructor bisa menerima parameter seperti halnya function pada umumnya. 

Untuk bisa membuat Constructor kita harus menggunakan nama constructor __construct()

```
Class Person {
  const GENDER = "Pria";
  var $name;

  function __construct($name) {
    $this->name = $name;
  }
  function greeting($name) {
    echo "Halo $name, nama saya $this->name dan saya adalah seorang self::GENDER ";
  }
}

$person1 = new Person("Budi");
$person1->greeting("Samsul");
```

sementara destructor adalah kebalikan dari constructor, akan dipanggil ketika program selesai. Tapi destructor tidak bisa menerima parameter. 

untuk membuatnya kita harus menggunakan nama __destruct()

```
Class Person {
  const GENDER = "Pria";
  var $name;

  function __construct($name) {
    $this->name = $name;
  }
  function greeting($name) {
    echo "Halo $name, nama saya $this->name dan saya adalah seorang self::GENDER ";
  }

  function __destruct() {
    echo "Program Selesai";
  }
}

$person1 = new Person("Budi");
$person1->greeting("Samsul");
```

## Inheritance (pewarisan)
dan hari thanks memungkinkan kita untuk bisa memiliki properti, perilaku, dan constant dari class lain (disebut parent) 

product.php
```
class Produk 
{
  var $name;
  var $price;
  function __construct($name, $price) 
  {
    $this->name = $name;
    $this->price = $price;
  }
}

class Toy extends Produk
{
  function showProduct() 
  {
  }
}
```

## Namespace 
Saat kita membuat sebuah aplikasi kita akan banyak membuat kelas, banyaknya kelas akan membuat pembuatan aplikasi semakin rumit, karena class-class yang ada tidak terorganisir dengan baik

Maka di sinilah peran Namespace bermain, Namespace digunakan untuk mengelompokkan class-class sesuai dengan fungsinya. 

contoh dari penggunaan Namespace adalah seperti ini

class.php
```
namespace foo\baa;

class Foo 
{
  function sayHi($name) 
  {
    echo "Hi $name";
  }
}
```

main.php 

```
require_once "class.php";

$foo1 = new foo\baa\Foo;
$foo1->sayHi("Udin");
```

Sekilas Namespace seperti folder yang menyimpan class-class. 

## import (use)
`use` digunakan untuk mengimpor namespace, traits, dan function.

contoh penggunaan use adalah sebagai berikut

class.php
```
namespace foo\baa;

class Foo {
  function sayHi($name) {
    echo "Hi $name";
  }
}
```

main.php 

```
require_once "class.php";

use foo\baa\Foo;

$foo1 = new Foo;
$foo1->sayHi("Udin");
```

namun perlu diingat bahwa jika nama class sama, maka akan terjadi error, walaupun nama namespacenya berbeda.

untuk mengatasi masalah itu, hp sudah menyediakan solusi dengan menyediakan fitur alias seperti ini

```
require_once "class.php";

use foo\baa\Foo as foo1;
use foo\baa2\Foo as foo2
```

# Akhir

Oke terima kasih sudah membaca, keep learning


















