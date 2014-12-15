---
layout: post
title: Dasar-dasar pemrograman
comments: true
---

Tidak ada seorangpun didunia ini langsung menjadi seorang ahli tanpa melalui tahapan pemula, tak terkecuali di bidang pemrograman. Untuk menjadi seorang ahli (*expert*) khususnya pada bidang pemrograman, haruslah menjalani tahapan pemula tersebut dengan benar yaitu melalui pemahaman terhadap konsep-konsep dasar dengan benar, **rajin membaca**, belajar dan berlatih dengan sabar ([[1]](http://norvig.com/21-days.html)/[[2]](http://djitz.com/djitzlosophy/belajar-programming-sendiri-dalam-sepuluh-tahun/)), serta melatih kreativitas dengan cara pengembangan lebih lanjut (walaupun pengembangannya hanya sedikit) terhadap solusi dari soal-soal/permasalahan sederhana yang telah berhasil dipecahkan.  

Seringkali, pada tahapan pemula, seseorang tergesa-gesa ingin membuat suatu aplikasi yang "keren", padahal konsep dasar dari pemrograman belum dikuasai dengan benar. Hal ini saya rasakan setelah mengamati berbagai posting di milis/forum/group *facebook* yang terkait dengan pemrograman, dimana seringkali muncul pertanyaan-pertanyaan (oleh pemula yang baru memulai pemrograman) seperti "*ajarin dong cara memprogram GUI di bahasa C++*, *bagaimana membuat program yang terkoneksi dengan database di bahasa ...*" dan lain sebagainya. Saya katakan tergesa-gesa karena misalnya untuk memprogram GUI di C++ harus paham dulu konsep-konsep mengenai *library*/pustaka (karena C++ tidak punya pustaka standar untuk GUI), *event*, *event handler*, jenis-jenis *control*, API (*application programming interface*) dari pustaka yang digunakan, dan masih banyak lagi konsep lainnya, dan hal-hal tersebut tidak bisa dijelaskan dan dipahami hanya dengan beberapa kalimat/paragraf. 

Pada tulisan kali ini, akan coba dipaparkan mengenai konsep-konsep paling mendasar pada bahasa pemrograman khususnya bahasa pemrograman tingkat tinggi. Tulisan ini terinspirasi dan banyak mengutip artikel [[3]](http://www.gamedev.net/page/resources/_/technical/general-programming/the-programming-primer-r3090). 

## Apa itu pemrograman?

Banyak orang pasti tahu bahwa *pemrograman* merupakan aktifitas untuk membuat aplikasi seperti game, kalkulator, pengolah gambar, web, dan sebagainya (secara umum kita sebut program), dan orang yang melakukan pemrograman disebut programer. Seorang programer seharusnya bukan hanya seseorang yang mampu mengetikkan perintah-perintah (terlebih lagi hanya *copy-paste*) dengan bahasa pemrograman tertentu, akan tetapi dituntut untuk mampu menganalisis dan menyodorkan solusi terhadap suatu permasalahan (*problem solving*). 

Bagian *problem solving* ini merupakan bagian tersulit, memerlukan pengalaman dan tidak ada seorangpun yang tahu semua solusi terhadap suatu permasalahan serta seringkali untuk suatu permasalahan ada banyak cara untuk memecahkannya. Tidak memahami dan hafal semua solusi merupakan hal yang wajar, akan tetapi memahami konsep dasar pemrograman, menerapkan konsep tersebut pada suatu permasalahan, mampu mencari dan mempelajari solusi terbaik dari permasalahan tersebut merupakan kunci sukses menjadi seorang programer. Seorang programer harus mampu menghadapi tantangan yang ada didepannya, memecah-mecah tantangan tersebut menjadi komponen-komponen dasar serta merangkaikan komponen-kompnen tersebut menjadi suatu solusi yang efisien. Janganlah mudah menyerah jika belum tahu bagaimana menyelesaiakannya, jangan patah arang jika program yang dibuat tidak jalan sesuai dengan keinginan, melainkan berusahalah untuk mencari tahu kenapa hal tersebut tidak berjalan serta berusahalah untuk terus mencari solusi yang lebih baik.      

## Komponen dasar pemrograman

Pada hakekatnya, sebuah program itu memerlukan masukan berupa **data** (baik secara langsung maupun tidak langsung), memproses **data** tersebut menjadi bentuk lain, serta menyajikannya sebagai suatu keluaran (*output*). Singkatnya, dalam setiap program pasti ada **data** dan **proses** pengolahan data. Oleh karena itu, konsep dasar yang paling pertama dan merupakan bagian terpenting adalah bagaimana menangani/mengingat/menyimpan **data** tersebut dalam program yang dibuat.

---

### Variabel

Variabel merupakan komponen yang pasti ada pada setiap bahasa pemrograman. Variabel umumnya menunjuk pada lokasi memori tertentu di komputer yang digunakan untuk menyimpan **data** (masukan, hasil pengolahan, keluaran, dll). Tergantung dari bahasa pemrograman yang digunakan, sebuah variabel biasanya diberi *identitas* melalui nama tertentu, serta mampu menyimpan suatu nilai yang mempunyai *tipe data* tertentu. Variabel akan valid (bisa digunakan) setelah dideklarasikan terlebih dahulu (pada beberapa bahasa pemrograman, deklarasi dilakukan secara implisit) serta berlaku dalam suatu skope tertentu (maksimum selama program dijalankan). Setelah dideklarasikan, sebuah variabel bisa diberi nilai misalnya "*hasil ujian*" = "*95*". Jumlah **byte** memori yang diperlukan oleh suatu variabel tergantung pada *tipe data* dari nilai yang disimpan oleh variabel tersebut. Berikut contoh deklarasi serta penggunaan variabel pada bahasa C/C++. 

{% highlight cpp linenos %}
int nilaiUjian;
char grade;

nilaiUjian = 95;
if (nilaiUjian >= 80)
    grade = 'A';

{% endhighlight %}

Pada baris ke-1 dan ke-2 dalam contoh diatas, variabel **nilaiUjian** dan **grade** dideklarasikan masing-masing dengan tipe data *int* serta  *char* (lebih detil mengenai tipe data, akan dibahas selanjutnya). Maknanya adalah dalam program yang dibuat, programer mendefinisikan variabel untuk menyimpan data dengan tipe bilangan bulat (tipe data *integer*) serta huruf (*char*) untuk menyimpan nilai ujian serta nilai grade (A,B,...,E) yang sepadan dengan nilai ujian tersebut. Terlihat sederhana, tapi variabel selalu ada dalam program, jadi harus diingat dan dipahami dengan benar.

### Tipe data

Tipe data merupakan terminologi yang digunakan untuk mendefinisikan jenis variabel beserta jumlah memori yang diperlukan. Pada bahasa pemrograman tertentu (seperti JavaScript), jenis variabel ditentukan secara otomatis berdasarkan data yang diberikan pada variabel tersebut, tapi pada bahasa pemrograman lain yang dikenal dengan istilah *strongly typed languages*, programer dituntut untuk mendeklarasikan tipe data dari sebuah variabel secara spesifik dan ekplisit. Dalam kedua kasus tersebut, seorang programer harus paham apa yang dimaksud dengan tipe data, untuk menghindari perilaku yang tidak diinginkan dalam program yang dibuat. Secara garis besar, ada tiga macam tipe data yaitu angka (*number*), huruf (*letter*) serta boolean (true/false). 

#### Angka (*number*)

Angka digunakan pada berbagai program untuk mengekpresikan besaran yang digunakan pada program tersebut seperti harga, potongan, nilai ujian, jarak, dan masih banyak lagi. Tipe data angka dibagi lagi berdasarkan jumlah **byte** memori yang diperlukan serta tipe bilangan (bulat dan desimal). Komputer yang ada saat ini umumnya mempunyai kapasitas memori yang cukup besar sehingga programer hampir tidak perlu memikirkan berapa banyak memori yang diperlukan untuk sebuah variabel, kecuali variabel tersebut menyimpan data dengan kapasitas yang sangat besar seperti pada pemrosesan citra atau video. Berikut beberapa jenis tipe data angka.

##### int 

Tipe data *int* digunakan untuk mendefiniskan angka dalam bilangan bulat baik "*signed*" (angka bisa negatif) maupun "*unsigned*" (angka positif). Berdasarkan kapasitasnya, *int* dikelompokkan lagi menjadi *short* (umumnya 16-bit) dan *long* (umumnya 64-bit).

##### float
*float* mengacu pada tipe data angka *floating point* yaitu tipe angka desimal. Umumnya pada berbagai bahasa pemrograman, pada saat memberikan nilai ke variabel tipe *float*, programer perlu secara ekplisit menuliskannya dengan huruf 'f' seperti dibawah ini.

{% highlight cpp linenos %}

float pi = 3.14f;

{% endhighlight %}

##### double

*double* merupakan tipe data untuk *double precision floating point*, yaitu angka desimal dengan ketelitian dua kali lipat dari *float* (umumnya *float* sampai 7 digit dibelakang koma, sedangkan *double* 14-15 digit dibelakang koma). Jika nilai yang diberikan pada variabel tanpa diakhiri dengan huruf 'f', maka akan dianggap sebagai tipe data *double*.


#### Huruf (*letter*)

*Character* atau dikenal dengan *char* merupakan tipe data untuk menyimpan huruf. Variabel tipe *char* umumnya berukuran 1 atau 2 byte yang digunakan untuk menyimpan data berupa huruf. Pada hakekatnya huruf merupakan angka dengan nilai kode tertentu (ASCII, Unicode, dll) dimana masing-masing huruf diberikan kode standar (contohnya huruf 'a' kodenya 97). Sekumpulan huruf (misalnya sebuah kata) biasanya disebut dengan *string*. Pada bahasa pemrograman tertentu, umumnya digunakan penanda khusus untuk membedakan angka, huruf maupun string. 

{% highlight cpp linenos %}

int x = 9;              //tipe data angka, nilainya 9
char c = '9';           //tipe data huruf dengan kode ASCII 57
char * kata = "Hai";    //tipe data string berisi 3 huruf

{% endhighlight %}

#### Boolean

Boolean atau *bool* merupakan tipe data paling primitif yang hanya menyimpan nilai biner 0 (false) atau 1 (true). Nilai biner merupakan nilai dasar yang membangun seluruh komputer yang ada dewasa ini. Bagian komputer berupa *processor*, *memory* dan lain sebagainya, pada level terendah merupakan suatu perangkat yang tersusun dari kombinasi *transistor* (dalam jumlah besar), dimana *transistor-transistor* tersebut dapat dimatikan (*off* nilai 0) dan dihidupkan (*on* nilai 1). Dalam pemrograman dengan level yang lebih tinggi, nilai *bool* biasanya digunakan sebagai *flag* untuk menandai suatu kondisi misalnya *isPositive*, *isFinished*, dan sejenisnya.

---

### Struktur dasar program

Pada penjelasan diatas, difokuskan pada bagaimana mengekpresikan/menangani **data** dalam pemrograman. Selanjutnya, pada bagian ini akan dijelaskan mengenai struktur dasar dari program, dimana struktur ini berkaitan dengan **proses** yang akan dilakukan dalam program tersebut. Program merupakan kumpulan dari perintah-perintah yang harus dijalankan oleh komputer, dimana dalam *source code* yang disusun oleh programer sebuah perintah disebut dengan pernyataan/*statement*. Pernyataan dapat dibagi menjadi tiga macam yaitu:

#### **Pernyataan sekuensial (*Sequence*)**

*Sequence* merupakan sekumpulan pernyataan yang akan dieksekusi satu persatu secara berurutan oleh komputer. Sekumpulan pernyataan dapat ditandai dengan penanda blok (begin/end pada Pascal/VB, {} pada C/C++/C#/Java dll). Berikut adalah contoh pernyataan sekuensial pada C++.

{% highlight cpp linenos %}

int panjang = 10;  //variabel 'panjang' dengan nilai 10
int lebar = 5;     //variabel 'lebar' dengan nilai 5
int luas;

//variabel 'luas' dengan nilai panjang x lebar
luas = panjang * lebar;

//cetak nilai luas
std::cout << "Luas " << luas << std::endl;

{% endhighlight %}

Pada contoh diatas, **semua** pernyataan yang tertulis akan dieksekusi satu persatu, secara berurutan.

#### **Percabangan (*Branching*)**

Percabangan atau *branching* digunakan untuk mengatur alur eksekusi pernyataan berdasarkan kondisi tertentu. Karena sifat komputer yang menggunakan nilai biner, maka percabangan paling dasar terdiri dari dua cabang, satu untuk kumpulan pernyataan yang akan dieksekusi jika kondisi benar/*true*, lainnya untuk kondisi jika salah/*false*. Berikut adalah contoh percabangan sederhana dalam bahasa C.

{% highlight cpp linenos %}

int x = 10;

if (x < 0)
    printf("Nilai x negatif\n");
else
    printf("Nilai x positif\n");

{% endhighlight %}

Pada contoh diatas, **tidak semua** pernyataan akan dieksekusi oleh komputer, dimana pernyataan yang dieksekusi bergantung pada kondisi (nilai variabel **x**). Jika kondisi yang diuji lebih dari satu, maka digunakan kombinasi dari dua percabangan diatas, misalnya:

{% highlight cpp linenos %}

double score = 90.0;

if (score >= 80)
    printf("Nilai A\n");
else {
    if (score >= 70)
        printf("Nilai B\n");
    else {
        if (score >= 60)
            printf("Nilai C\n");
        else {
            if (score >= 50)
                printf("Nilai D\n");
            else
                printf("Nilai E\n");
        }
    }
}

{% endhighlight %}

Pada contoh diatas, jika *score* < 80, maka pernyataan yang dieksekusi adalah pernyataan antara baris ke-6 s.d. baris ke-18. Oleh karena dalam kumpulan pernyataan ini terdapat percabangan maka dipilih lagi pernyataan mana yang akan dieksekusi berdasarkan kondisinya, misal jika *score* >= 70 (dan *score* < 80) maka yang dieksekusi adalah pernyataan pada baris ke-7, sedangkan jika score < 70, maka pernyataan yang dieksekusi adalah pernyataan antara baris ke-9 s.d. baris ke-16, begitu seterusnya. Untuk menuliskan percabangan yang kompleks seperti diatas, tiap bahasa pemrograman umumnya menawarkan cara penulisan yang lebih sederhana seperti dibawah ini (maknanya persis sama):

{% highlight cpp linenos %}

double score = 90.0;

if (score >= 80)
    printf("Nilai A\n");
else if (score >= 70)
    printf("Nilai B\n");
else if (score >= 60)
    printf("Nilai C\n");
else if (score >= 50)
    printf("Nilai D\n");
else
    printf("Nilai E\n");

{% endhighlight %}

#### **Pengulangan (*loop*)**

Struktur yang terakhir adalah pengulangan (*loop*), dimana pada struktur ini, sekumpulan pernyataan akan dieksekusi **secara berulang selama suatu kondisi terpenuhi**. Biasanya, struktur pengulangan terdiri dari empat bagian yaitu:

- Inisialisasi kondisi
- Pengecekan kondisi
- Pernyataan yang dieksekusi
- Update kondisi

Dalam berbagai bahasa pemrograman, umumnya ada beberapa cara untuk menuliskan pengulangan, dimana masing-masing memiliki karakteristiknya sendiri-sendiri. Berikut cara penulisan pengulangan pada bahasa C/C++.

{% highlight cpp linenos %}

//Pengulangan dengan 'while'
int x = 0; //inisialisasi
while (x < 10) {    //pengecekan kondisi
    printf("X = %d\n", x);  //pernyataan yang dieksekusi
    x++;                    //pernyataan dan update kondisi   
}

//Pengulangan dengan for
//Inisialisasi, pengecekan dan update kondisi
for(int i = 0; i < 10; i++) {
    printf("i = %d\n", i);  //pernyataan yang dieksekusi
}

//Pengulangan do-while
int y = 0;
do {
    printf("y = %d\n", y);  //pernyataan yang dieksekusi
    y++;                    //pernyataan dan update kondisi
} while (y < 10);           //pengecekan kondisi

{% endhighlight %}

---

### Fungsi

Uraian diatas terkait dengan variabel, tipe data dan struktur program. Dengan pengetahuan ini sebenarnya program yang komplek sudah bisa ditulis, karena pada dasarnya sekomplek apapun program, pasti tersusun dari komponen-komponen dasar tersebut. Selanjutnya, pada bagian ini akan dijelaskan satu lagi konsep penting yaitu fungsi. 

Dalam proses penyusunan program, sering ditemui sebuah kasus dimana **cara penyelesaiannya mirip** dan hanya berbeda pada **data** atau nilai yang digunakan/diperlukan. Sebagai contoh sederhana, pada program untuk menentukan grade nilai ujian mahasiswa berdasarkan nilai ujian, formula yang digunakan sama, hanya berbeda pada nilai ujian yang perlu dikonversikan. Jika ada 40 orang mahasiswa, kemungkinan besar ada 40 nilai ujian yang berbeda dan tentu tidak akan praktis menulis 40 macam program konversi berdasarkan nilai ujian yang diperoleh. Disinilah peran *fungsi*. 

**Fungsi** adalah sekumpulan pernyataan yang memiliki identitas dan berfungsi untuk melakukan operasi tertentu serta dapat dipanggil seperlunya. Artinya, walaupun pernyataan-pernyataannya ditulis di *source code* tidak serta merta akan dieksekusi oleh komputer apabila tidak dipanggil. Berikut contoh fungsi dalam bahasa C/C++.

{% highlight cpp linenos %}

#include <stdio.h>

char hitungCetakGrade(float nilai)
{
    char grade;
    if (nilai >= 80)
        grade = 'A';
    else if (nilai >= 70)
        grade = 'B';
    else if (nilai >= 60)
        grade = 'C';
    else if (nilai >= 50)
        grade = 'D'
    else
        grade = 'E';
    printf("Grade untuk nilai %.1f = %c\n", nilai, grade);

    return grade;
}

int main()
{
    printf("----- Konversi nilai -----\n");
    hitungCetakGrade(90);
    hitungCetakGrade(80);
    hitungCetakGrade(55);

    return 0;
}

{% endhighlight %} 

Pada contoh diatas, terdapat 2 fungsi yaitu **hitungCetakGrade** (baris ke-3 s.d. 19) dan **main** (baris ke-21 s.d. 19). Fungsi pertama dipanggil oleh fungsi **main** dengan parameter yang berbeda-beda sehingga grade yang dicetak akan berubah berdasarkan parameter tersebut. Coba bayangkan apabila seorang programer tidak menggunakan fungsi dan harus menulis pernyataan pada fungsi **hitungCetakGrade** sebanyak jumlah nilai yang mau dikonversi (pada contoh ini ada 3), tentu *source code* dari program tersebut akan menjadi besar padahal prosesnya sama. Inilah salah satu kegunaan fungsi yaitu dapat mempersingkat kode program sehingga lebih mudah dipahami.

Sebuah fungsi boleh mempunyai nilai kembalian (*return value*, pada contoh ini mengembalikan grade hasil konversi dengan tipe *char*), serta dapat juga mendefinisikan parameter/*argument* yang diperlukan untuk perhitungan (pada contoh ini **nilai**). Pada bahasa pemrograman tertentu, fungsi yang tidak mengembalikan nilai disebut **prosedur** (misalnya pada Pascal atau VB).

## Penutup

Pada tulisan ini, disajikan komponen dasar dari pemrograman yang umum terdapat diberbagai bahasa pemrograman. Contoh-contoh yang disajikan disini dalam bahasa C/C++, semata-mata hanya untuk memberikan gambaran konkrit terhadap konsep-konsep yang dijelaskan. Tidak perlu memahamai secara detil mengenai sintak dari contoh-contoh yang disajikan, dan cukup dipahami konsep dasar yang ada pada setiap pembahasan. 

Tulisan ini tidak bermaksud membahas keseluruhan aspek dari bahasa pemrograman baik untuk C/C++, maupun bahasa pemrogaman lainnya, hanya menyajikan konsep-konsep paling dasar yang ada didalamnya. Diharapkan dengan membaca tulisan ini, diperoleh gambaran mengenai ide-ide dasar pada bahasa pemrograman, dimana selanjutnya pembaca dituntut untuk menggali lebih detil dan lebih spesifik pada bahasa pemrograman yang ingin digunakan.

## Referensi
1. [Teach Yourself Programming in Ten Years](http://norvig.com/21-days.html)
2. [Terjemahan: Belajar Programming Sendiri Dalam Sepuluh Tahun](http://djitz.com/djitzlosophy/belajar-programming-sendiri-dalam-sepuluh-tahun/)
3. [The Programming Primer](http://www.gamedev.net/page/resources/_/technical/general-programming/the-programming-primer-r3090)

(/ips)