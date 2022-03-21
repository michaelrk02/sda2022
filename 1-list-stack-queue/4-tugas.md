# Tugas Praktikum List, Stack, & Queue

NOTE

1. Gunakan bahasa **C++**
2. Kumpulkan semua source code pada assignment Google Classroom **(jangan di-ZIP)**, diberi format: **PSDA01_NIM_Nama Lengkap_Nomor Soal.cpp**, misal **PSDA01_M0520047_Michael Raditya Krisnadhi_1.cpp** apabila mengumpulkan nomor 1

## No. 1 - List

Ikuti langkah-langkah berikut **(bobot: 40%)**:

1. Buatlah list untuk menyimpan data berupa sekumpulan string: **Apple**, **Orange**, **Banana**, **Orange**, **Banana**, **Mango**
2. Hapus seluruh elemen yang memiliki nilai **Orange**
3. Setelah itu, tampilkan isi dari list tersebut

Anda boleh menggunakan array list (std::vector) ataupun linked list (std::list)

## No. 2 - Stack

Selesaikan permasalahan di bawah menggunakan stack **(bobot: 30%)**:

Pak Dengklek memiliki tumpukan buku sebagai berikut (urut dari posisi teratas):

- Fundamentals of Computer Graphics
- Linear Algebra and Its Applications
- Introduction to Machine Learning
- Computer Networking: A Top Down Approach
- Discrete Mathematics and Its Applications
- Numerical Analysis

Suatu saat Pak Dengklek ingin mengambil salah satu buku, namun cara mengambilnya yaitu Pak Dengklek mengeluarkan terlebih dahulu buku-buku yang berada di atasnya, lalu dimasukkan kembali sesuai posisi semula. Dengan demikian, apabila Pak Dengklek ingin mengambil buku **Introduction to Machine Learning**, maka berikut adalah langkah-langkah yang dilakukan oleh Pak Dengklek:

1. Mengeluarkan buku **Fundamentals of Computer Graphics**
2. Mengeluarkan buku **Linear Algebra and Its Applications**
3. Mengambil buku **Introduction to Machine Learning**
4. Meletakkan kembali buku **Linear Algebra and Its Applications**
5. Meletakkan kembali buku **Fundamentals of Computer Graphics**

Buatlah program yang mensimulasikan permasalahan tersebut menggunakan stack! Program tidak harus menampilkan isi stack ke layar ataupun menerima input. Asisten akan menilai ketepatan dari source code yang dibuat.

## No. 3 - Queue

Selesaikan permasalahan di bawah menggunakan queue (dan stack) **(bobot: 30%)**:

Komputer Pak Dengklek memiliki berbagai macam perintah:

|Perintah|Deskripsi|
|--|--|
|PUSH 0|Memasukkan angka 0 ke atas stack|
|PUSH 1|Memasukkan angka 1 ke atas stack|
|TOP|Menampilkan angka yang berada di atas stack|
|POP|Mengeluarkan angka yang berada di atas stack|

Komputer tersebut bekerja dengan cara menerima input kemudian memasukkannya ke dalam queue, lalu dieksekusi oleh mesin dengan cara membaca isi queue tersebut. Dengan demikian, apabila komputer pak dengklek menerima perintah (urut):

- PUSH 0
- PUSH 0
- TOP
- PUSH 1
- TOP
- POP
- POP
- TOP

Maka akan menampilkan output berupa:
```
010
```

Buatlah program yang mensimulasikan permasalahan tersebut menggunakan queue (dan stack)! Anda bebas memasukkan perintah apapun ke dalam queue dan melalui manapun (melalui source code atau user input atau file input).
