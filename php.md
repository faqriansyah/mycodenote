# mycodingnote
Ini adalah halaman github yang ditujukan untuk diri saya sendiri sebagai catatan belajar, yang didasarkan pada course-course berikut :
1. Programmer Zaman Now - TUTORIAL PHP OOP BAHASA INDONESIA : https://youtu.be/_P2t0lCzU-Q?si=iE2RYr11tIr7kBdq

# PHP OOP (DASAR)

## Apa itu OOP?
- Pemrograman berbasis objek
- Objek adalah data yang berisi properties/attributes dan method/function/behavior
- Class adalah blueprint atau cetakan untuk membuat objek, berisi deklarasi semua properties dan function yang dimiliki object

## Membuat Class
Untuk membuat class adalah dengan menggunakan keyword `class`

```
Class Person {

}
```

## Object
Objek adalah hasil instance dari class, untuk menggunakan object, gunakan keyword `new` diikuti nama class dan ()

```
$person1 = new Person();
```

## Properties
Adalah data (variabel) yanng disimpan di dalam object, untuk membuatnya dengan menggunakan keyword `var` lalu nama propertiesnya

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

## Function
function/method bisa dideklarasikan di dalam class dan diakses menggunakan `->`

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
`this` digunakan untuk mengakses properties dari dalam class yang sama

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

## constant
constant adalah data yang tidak bisa diubah, untuk membuatnya kita bisa menggunakan keyword `const` diikuti nama constantnya. Untuk bisa mengaksesnya gunakanlah `NamaClass::NamaConstant`

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

## constructor
constructor adalah function yang akan dipanggil saat pertama kali objek dibuat 

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
# Akhir

Oke terima kasih


















