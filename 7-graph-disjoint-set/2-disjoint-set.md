# 2 - Disjoint Set

## Konsep Disjoint Set

Disjoint Set adalah suatu struktur data yang dapat mengelompokkan beberapa data berdasarkan suatu kesamaan. Salah satu contoh penerapan sederhana dari struktur data ini adalah jejaring pertemanan di media sosial. Perhatikan ilustrasi berikut:

- Terdapat 5 orang yaitu: Andi, Budi, Caca, Deni, dan Edo
- Andi berteman dengan Budi
- Budi berteman dengan Caca
- Deni berteman dengan Edo
- Dengan demikian, Caca berada dalam satu jaringan pertemanan dengan Andi (meskipun melalui perantara yaitu Budi)
- Namun Caca tidak berada dalam satu jaringan pertemanan dengan Edo (karena jaringan pertemanan Edo adalah hanya dengan Deni)

## Implementasi Disjoint Set

Disjoint Set dapat dinyatakan sebagai array (atau map) yang memetakan suatu data ke data yang bertipe sama yang merupakan perwakilan dari data tersebut.

Untuk memastikan bahwa suatu data memiliki kesamaan kelompok dengan data lain, disjoint set akan melacak perwakilan dari semua data tersebut sampai akarnya. Apabila perwakilan sama, maka kedua data tersebut berada dalam kelompok yang sama, begitu juga sebaliknya.

Untuk mendukung prosesnya, disjoint set menggunakan suatu algoritma yaitu **union-find** yang akan kita pelajari berikutnya.

Berikut adalah contoh definisi struktur data untuk kasus jejaring pertemanan:

```
std::map<std::string, std::string> perwakilan;

// mulanya seluruh orang hanya diwakili oleh dirinya sendiri
// sehingga Andi berada dalam satu kelompok dengan dirinya sendiri, begitu juga Budi, dan seterusnya
perwakilan["Andi"] = "Andi";
perwakilan["Budi"] = "Budi";
perwakilan["Caca"] = "Caca";
perwakilan["Deni"] = "Deni";
perwakilan["Edo"] = "Edo";
```

Kemudian untuk menjalin pertemanan, berikut adalah contohnya:

```
// fungsi untuk menemukan perwakilan kelompok pertemanan
// merupakan bagian "find" dalam algoritma "union-find"
std::string find(std::string X) {
    if (perwakilan[X] == X) {
        return X;
    }
    return find(perwakilan[X]);
}

// fungsi untuk menjalin pertemanan A dengan B
// merupakan bagian "union" dalam algoritma "union-find"
void union(std::string A, std::string B) {
    std::string wakilA = find(A);
    std::string wakilB = find(B);

    perwakilan[wakilA] = wakilB;

    // analisis:
    // contoh kasus pertemanan, apabila grup Deni-Edo bergabung dengan Andi-Budi-Caca,
    // maka kedua perwakilan kelompok digabung.
    // misal mulanya masing-masing diwakili oleh Deni dan Andi, maka setelah penggabungan,
    // kedua grup Deni-Edo dan Andi-Budi-Caca semuanya diwakili oleh Andi
    // dengan demikian, Deni (diwakili Andi) sudah berada dalam kelompok yang sama dengan Budi (diwakili Andi juga)
}
```

Untuk mengecek apakah kedua orang berada dalam jaringan pertemanan yang sama, maka cukup melakukan:

```
if (find("Andi") == find("Deni")) {
    std::cout << "Andi dan Deni berada dalam satu jaringan yang sama" << std::endl;
}
```

## Selengkapnya

- [Disjoint Set (e-Book Pemrograman Kompetitif Dasar)](https://ksn.toki.id/data/pemrograman-kompetitif-dasar.pdf)

