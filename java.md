# mycodingnote
Ini adalah halaman github yang ditujukan untuk diri saya sendiri sebagai catatan belajar, yang didasarkan pada course-course berikut :
1. Programmer Zaman Now - Tutorial Java Dasar 

# Java Dasar 

## Java
Java adalah masa pemrograman yang dibuat berdasarkan Object Oriented Progamming.

Untuk bisa menjalankan Java kita harus menginstal Java terlebih dahulu, bisa mengunjungi website resminya, atau jika tidak mau repot maka kita bisa menggunakan IDE seperti Eclipse, Intelij, dan lain-lain.

## Hello World!
Untuk bisa membuat program hello world, sintaks dasarnya adalah seperti ini, tulis di sebuah file dengan nama `Main.java`

```
public class Main {
	public static void main(String[] args) {
		System.out.println("Hello World")
	}
}
```

penjelasan :
1. Pertama ada class Main, ya itu merupakan kelas utama dari program Java ini sendiri. Penamaan kelas utama harus sama dengan nama file javanya
2. Setiap kelas utama harus memiliki main function di dalamnya, di sini main function adalah main() yang berisi sintaks untuk mengeluarkan Hello World

## Kompilasi Java
proses kompilasi Java menggunakan JVM(Java Virtual Machine), JVM adalah engine yang menjalankan Java. 

JVM tidak menjalankan kode Java yang kita buat secara langsung, melainkan kode Java yang kita buat harus dikompilasi terlebih dahulu menjadi binary, lalu bisa dipahami oleh JVM dan kode pun berhasil berjalan. 

untuk lebih jelasnya coba jalankan perintah 

```
javac Main.java 
```

maka kita akan melihat sebuah file baru yang muncul dengan nama Main.class, ini adalah file binary yang akan diproses oleh JVM. 

jalankan perintah ini

```
java main
```

maka kita akan melihat output hello world yang sudah kita program tadi
