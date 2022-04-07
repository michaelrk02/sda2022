# Analisis Kompleksitas

Pada semester pertama kita telah mempelajari bagaimana membuat algoritma untuk menyelesaikan suatu masalah. Namun, hal tersebut tidak sajalah cukup. Algoritma tidak saja harus benar (efektif), tetapi juga harus mangkus (efisien). Sehingga dapat dikatakan bahwa algoritma yang baik adalah algoritma yang mangkus. Kemangkusan suatu algoritma diukur dari sisi waktu (time) eksekusi serta penggunaan memori (space).

## 1 - Notasi Asimtotik

Terdapat beberapa jenis notasi asimtotik, tetapi kita hanya akan menggunakan dan membahas satu notasi saja, yaitu notasi Big-O. Big-O dipilih karena merupakan notasi yang paling populer dan paling banyak digunakan pada kalangan peneliti ilmu komputer. Notasi Big-O digunakan untuk mengkategorikan algoritma ke dalam fungsi yang menggambarkan batas atas (upper limit) dari pertumbuhan sebuah fungsi ketika masukan dari fungsi tersebut bertambah banyak.

| Fungsi Big-O | Nama       |
| ------------ | ---------- |
| O(1)         | Konstan    |
| O(log n)     | Logaritmik |
| O(n)         | Linear     |
| O(n log n)   | n log n    |
| O(n^2)       | Kuadratik  |
| O(n^m)       | Polinomial |
| O(n!)        | Faktorial  |

## 2 - Contoh Kriteria Kompleksitas

### O(1)

```cpp
// ...
int a = 0, b = 0;
for (i = 0; i < N; i++) {
	a = a + rand();
}
for (j = 0; j < M; j++) {
	b = b + rand();
}
// ...
```

Loop pertama adalah O(N) dan loop kedua adalah O(M). Karena kita tidak tahu mana yang lebih besar, kita katakan ini O(N + M). Ini juga dapat ditulis sebagai O(max(N, M)).
Karena tidak ada ruang tambahan yang digunakan, kompleksitas ruang adalah konstan / O(1)

### O(N^2)

```cpp
// ...
int a = 0;
for (i = 0; i < N; i++) {
	for (j = N; j > i; j--) {
		a = a + i + j;
	}
}
// ...
```

Kode di atas berjalan total tidak kali  
= N + (N – 1) + (N – 2) + … 1 + 0  
= N _ (N + 1) / 2  
= 1/2 _ N^2 + 1/2 \* N  
O(N^2) kali.

### O(n log n)

```cpp
// ...
int i, j, k = 0;
for (i = n / 2; i <= n; i++) {
	for (j = 2; j <= n; j = j * 2) {
		k = k + n / 2;
	}
}
// ...
```

Jika diperhatikan, j terus berlipat ganda hingga kurang dari atau sama dengan n. Beberapa kali, kita dapat menggandakan angka hingga kurang dari n akan menjadi log(n).  
Mari kita ambil contoh di sini.  
untuk n = 16, j = 2, 4, 8, 16  
untuk n = 32, j = 2, 4, 8, 16, 32  
Jadi, j akan dijalankan untuk langkah-langkah O(log n).  
saya berlari selama n/2 langkah.  
Jadi, langkah total = O(n/ 2 * log (n)) = O(n*logn)

### (log n)

```cpp
// ...
int a = 0, i = N;
while (i > 0) {
	a += i;
	i /= 2;
}
// ...
```

Kita harus mencari x terkecil sehingga N / 2^x N
x = log(N)

## 3 - Perbandingan Pertumbuhan Kompleksitas

![Gambar perbandingan kompleksitas](http://dev.bertzzie.com/knowledge/analisis-algoritma/_images/AllComplexityComparison.PNG)

Pengembangan algoritma idealnya diusahakan mendapatkan kompleksitas O(1) atau O(logn). Sayangnya pada kenyataannya kita tidak akan selalu mendapatkan kompleksitas terbaik dalam merancang algoritma. Jika tidak dapat mencapai kompleksitas maksimal, hal terbaik yang dapat kita lakukan ketika mengembangkan solusi dari masalah adalah melihat apakah masalah yang ada dapat diselesaikan dengan algoritma yang ada terlebih dahulu, sebelum mengembangkan algoritma baru. Hal ini memastikan kita mendapatkan kompleksitas yang paling efisien sampai saat pengembangan solusi.

## 4 - Kesimpulan

Pada bagian ini kita telah mempelajari bagaimana melakukan analisa efisiensi algoritma dengan menggunakan notasi Big-O. Kita juga melihat bagaimana algoritma yang paling efisien memiliki kompleksitas O(1), dengan kompleksitas O(n!) sebagai kelas kompleksitas yang paling tidak efisien. Dengan mengerti efisiensi algoritma, diharapkan pembaca dapat memilih dan merancang algoritma yang sesuai dengan kebutuhan untuk menyelesaikan masalah.
