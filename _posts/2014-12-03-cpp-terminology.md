---
layout: post
title: Terminologi dasar pada pemrograman dengan C/C++
comments: true
---

Pemahaman yang benar terkait [terminologi](http://kbbi.web.id/terminologi) yang digunakan pada suatu bahasa pemrograman sangat diperlukan untuk mempelajari dan memahami bahasa pemrograman tersebut. Pada tulisan kali ini, akan dipaparkan beberapa istilah dasar yang digunakan pada pemrograman secara umum maupun pada bahasa C/C++. Agar mudah dipahami, disertakan juga contoh-contoh yang tekait.  

### IDE (*Integrated Development Environment*)

IDE merupakan perangkat lunak terintegrasi yang digunakan untuk membuat aplikasi. IDE umumnya terdiri dari *editor*, *compiler*, *linker*, *debugger* beserta program-program tambahan seperti *resource compiler*, DLL (*dynamic link library*) *import* dan lain sebagainya. Berikut beberapa contoh IDE yang mendukung pemrograman dengan C/C++ (Daftar IDE lebih lengkap dapat dilihat [disini](http://en.wikipedia.org/wiki/Comparison_of_integrated_development_environments#C.2FC.2B.2B)). 

1. Microsoft Visual Studio. [http://www.visualstudio.com/](http://www.visualstudio.com/)
2. Code::Blocks. [http://www.codeblocks.org/](http://www.codeblocks.org/)
3. Dev-C++. [http://www.bloodshed.net/devcpp.html](http://www.bloodshed.net/devcpp.html)
4. NetBeans. [https://netbeans.org/](https://netbeans.org/)
5. Eclipse CDT. [https://eclipse.org/cdt/](https://eclipse.org/cdt/)
6. Qt Creator. [http://qt-project.org/wiki/Category:Tools::QtCreator](http://qt-project.org/wiki/Category:Tools::QtCreator)
7. Anjuta Studio. [http://anjuta.org/](http://anjuta.org/)
8. Code Lite. [http://codelite.org/](http://codelite.org/)

Penggunaan IDE sangat disarankan karena IDE tersebut akan memudahkan dalam pembuatan, manajemen, perbaikan serta pemahaman alur program yang dibuat melalui proses *debugging*. Akan tetapi karena kemudahannya serta sifat IDE yang umumnya *menyembunyikan* tahapan detil untuk mengubah kode sumber (*source code*) menjadi aplikasi, seorang pemula sering kali tidak bisa membedakan antara kompiler dengan IDE. 

### Text Editor

*Text editor* merupakan aplikasi yang digunakan untuk mengolah (membuat, memodifikasi, menyimpan) file dalam bentuk text. Aplikasi ini digunakan untuk menulis *source code*. *Text editor* yang bagus dilengkapi dengan penomeran baris serta *syntax highlighter* untuk memudahkan dalam penulisan *source code*. Beberapa *text editor* juga dilengkapi dengan kemampuan untuk memanggil aplikasi lain (seperti *compiler*), sehingga memudahkan proses pembuatan program. *Text editor* masih banyak digunakan oleh programmer karena aplikasi ini memerlukan memori yang lebih sedikit dibandingkan IDE sehingga terasa lebih ringan. Selain itu programer memiliki kebebasan dan kontrol penuh untuk mengorganisir bagaimana susunan *folder*, *source code* serta bagian-bagian lain dari aplikasi yang dibuat. Berikut beberapa contoh *text editor* yang dapat digunakan pada pemrograman dengan bahasa C/C++ (Daftar *text editor* lengkap dapat dilihat [disini](http://en.wikipedia.org/wiki/Comparison_of_text_editors)).

1. Notepad++. [http://notepad-plus-plus.org/](http://notepad-plus-plus.org/)
2. Sublime Text. [http://www.sublimetext.com/](http://www.sublimetext.com/)
3. Emacs. [http://www.gnu.org/software/emacs/](http://www.gnu.org/software/emacs/)
4. Vim. [http://www.vim.org/](http://www.vim.org/)
5. Gedit / pluma di MATE. [https://wiki.gnome.org/Apps/Gedit](https://wiki.gnome.org/Apps/Gedit)
6. SciTE. [http://www.scintilla.org/SciTE.html](http://www.scintilla.org/SciTE.html)

### Source code (kode sumber)

*Source code* merupakan perintah-perintah yang ditulis oleh programer untuk dijalankan oleh komputer. Agar bisa dipahami dan dijalankan oleh komputer, *source code* tersebut perlu diterjemahkan oleh program lain (*compiler*, *assembler*, *linker*, *interpreter*) menjadi bahasa mesin. *Source code* disimpan dalam file (*source file*) dalam format text. Dalam bahasa C/C++, file *source code* dibagi menjadi bagian implementasi (umumnya mempunyai ekstensi .c .cc .cpp .cxx) dan *header file* (dengan ekstensi .h .hpp .hxx atau tanpa ekstensi seperti pada **iostream** dsb). Jika aplikasi yang dibuat sudah kompleks, untuk memudahkan dalam mengorganisir, sebaiknya *source code* dibagi dalam beberapa file. Berikut contoh *source code* C++.

{% highlight cpp linenos %}
#include <iostream>
#include "hello.h"

void say_hello()
{
    std::cout << "Halo dari C/C++." << std::endl;
}

void say(const char * name)
{
    std::cout << "Halo " << name 
        << ", semoga harimu menyenangkan." << std::endl;
}
{% endhighlight %}

### Header file  

*Header file* berisi deklarasi yang dapat digunakan pada lebih dari satu kode sumber. *Header file* umumnya berisi deklarasi fungsi, *class*, fungsi *inline*, konstanta, enumerasi maupun *template*. Oleh karena itu, *header file* bertindak sebagai penghubung antar beberapa kode sumber. *Header file* dapat dikelompokkan menjadi tiga macam yaitu:

1. *Header file* standar, merupakan *header file* yang pasti ada pada setiap kompiler C/C++. Contohnya **stdio.h**, **iostream**, **string**, **vector** dan lain sebagainya.
2. *Header file* dari vendor, yaitu *header file* yang disediakan oleh pihak ketiga bersamaan dengan *library* untuk memudahkan programer dalam membangun aplikasi. Contohnya **windows.h** (fungsi-fungsi spesifik pada OS Windows), **QtWidgets** (salah satu *header* untuk pemrograman GUI berbasis Qt), **mysql.h** (akses database MySQL) dan lain sebagainya.
3. *Header file* yang dibuat oleh programer. Penamaan *header file* ini bebas tergantung dari selera programer, tapi disarankan untuk menggunakan nama yang dapat mencerminkan isi dari *header file* tersebut. Berikut contoh header file yang penulis buat (**hello.h**).

{% highlight cpp linenos %}
#ifndef __hello_h__
#define __hello_h__

extern void say_hello();
extern void say(const char * name);

#endif
{% endhighlight %}

### Syntax

*Syntax* merupakan seperangkat aturan yang ditetapkan dalam suatu bahasa pemrograman. Pemahaman *syntax* mutlak diperlukan agar *source code* yang ditulis dapat dipahami dan diterjemahkan oleh *compiler*. Mempelajari bahasa pemrograman mirip dengan mempelajari bahasa komunikasi seperti bahasa Indonesia, bahasa Inggris, dll dimana untuk memahami bahasa tersebut serta dapat berkomunikasi dengan baik, perlu pemahaman terhadap aturan-aturan seperti struktur penulisan kalimat, tanda baca, penulisan paragraf dan sebagainya. Dengan mematuhi *syntax* yang ditetapkan maka *compiler* dapat menterjemahkan *source code* menjadi bahasa mesin.  

### Compiler (Kompiler)

*Compiler* adalah program yang digunakan untuk menterjemahkan *source code* menjadi format lain seperti *assembly* atau *object code*. Berikut adalah beberapa *compiler* yang dapat digunakan pada pemrograman dengan bahasa C/C++ (Daftar lebih lenkap bisa dilihat [disini](http://en.wikipedia.org/wiki/List_of_compilers#C.2B.2B_compilers).

1. GNU Compiler Collection. [https://gcc.gnu.org/](https://gcc.gnu.org/). 
2. Visual C++ Compiler. [http://www.visualstudio.com/](http://www.visualstudio.com/)
3. Clang. [http://clang.llvm.org/](http://clang.llvm.org/)

### Assembler

*Assembler* merupakan program yang berfungsi untuk mengubah *source code* dalam bahasa assembly menjadi *object code*. *Assembler* sangat spesifik pada arsitektur procesor yang didukung, misalnya *assembler* untuk x86 berbeda dengan *assembler* untu ARM. Berikut adalah beberapa contoh assembler (Contoh lainnya ada [disini](http://en.wikipedia.org/wiki/Comparison_of_assemblers).

1. NASM. [http://www.nasm.us/](http://www.nasm.us/)
2. GNU Assembler. [https://www.gnu.org/software/binutils/](https://www.gnu.org/software/binutils/)

### Linker

*Linker* berfungsi untuk menggabungkan beberapa *object code* hasil dari *compiler* atau *assembler* dengan *library* yang tersedia menjadi satu format lain dalam bentuk bahasa mesin seperti *executable*/EXE atau pustaka (*dynamic linking library*/DLL). Berikut adalah contoh-contoh *linker*.

1. Microsoft linker. [http://msdn.microsoft.com/en-us/library/y0zzbyt4.aspx](http://msdn.microsoft.com/en-us/library/y0zzbyt4.aspx)
2. GNU Linker. [https://www.gnu.org/software/binutils/](https://www.gnu.org/software/binutils/)

Umumnya pada *build tools* modern seperti GNU C++ compiler, Microsoft Visual C++ Compiler dan lain sebagainya, saat proses kompilasi, jika diperlukan *compiler* langsung memanggil *assembler* maupun *linker*, sehingga hasil akhir dari proses kompilasi adalah program jadi dalam bentuk EXE atau DLL. 

Berikut adalah *screenshot* yang berisi daftar *source file* (hello.cpp, main.cpp), hasil *assembler* (hello.s, main.s), *object code* (hello.o, main.o) dan hasil akhir dalam bentuk executable (**hello**). 

![Contoh source file, hasil assembler, object code dan hasil akhir dalam bentuk executable](/public/img/2014-12-03/cpp_src-asm-obj.png)

### Error

Istilah *error* disini mengacu pada kesalahan dalam pemrograman. Tipe *error* dapat dikelompokkan sebagai berikut.

- **Syntax error**. Tipe kesalahan karena *syntax* tidak dipatuhi oleh programer. *Error* tipe ini dapat dengan mudah dideteksi oleh *compiler*.
{% highlight cpp linenos %}
int perkalian(int a, int b)
{
	return a * b    //tidak ada semikolon
}
{% endhighlight %}

- **Semantic error**. Kesalahan yang disebabkan oleh penggunaan pernyataan yang tidak tepat, contohnya:
{% highlight cpp linenos %}
int x;	//Nilai x belum di inisialisasi.
std::cout << "Nilai x adalah << x << std::endl;

int array[] = {1, 2, 3, 4};
std::cout << "Elemen ke-10 adalah " << array[9] << std::endl;
//Indeks 9 tidak valid karena hanya ada 4 elemen.
{% endhighlight %}

- **Logical error**. Kesalahan karena spesifikasi yang ditetapkan tidak dipatuhi, misalnya:
{% highlight cpp linenos %}
//Fungsi untuk menghitung hasil perkalian dua bilangan
double perkalian(double a, double b)
{
	return a + b;
}
{% endhighlight %}

Sedangkan, jika ditinjau berdasarkan pada kapan sebuah *error* terdeteksi, tipe *error* ada dua yaitu:

- **Compile time error**. Kesalahan jenis ini terdeteksi pada saat proses kompilasi. **Syntax error** dan sebagian **semantic error** terdeteksi oleh kompiler pada saat proses kompilasi. Kompiler akan melaporkan pada baris keberapa *error* tersebut terjadi. 

  > *Error* biasanya ada pada baris atau sebelum baris yang dilaporkan oleh kompiler. Jika ada lebih dari satu *error*, telusuri dan perbaikilah mulai dari *error* yang muncul paling pertama. Bisa saja jumlah kesalahan yang dibuat oleh programer, riilnya lebih sedikit dari yang dilaporkan oleh kompiler. Dengan memperbaiki kesalahan yang terjadi diawal, seringkali jumlah *error* akan berkurang secara signifikan.

- **Runtime error**. *Error* tipe ini tidak dapat dideteksi oleh kompiler pada saat proses kompilasi, dan baru muncul apabila program dijalankan. Berikut contoh kode program yang dapat menimbulkan *runtime error*.
{% highlight cpp linenos %}
#include <iostream>
using namespace std;

int main()
{
    int array[5];
    int indek, nilai;

    cout << "Elemen ke?"; cin >> indek;
    cout << "Nilainya?";  cin >> nilai;

    array[indek] = nilai; 	

    return 0;
}
{% endhighlight %} 
Pada potongan kode diatas, jika pada saat program dijalankan user memasukkan nilai indek yang lebih besar dari 4, maka akan terjadi *error* karena kapasitas variabel **array** hanya 5.

### Debug

[*Debug*](http://dictionary.reference.com/browse/debug) berasal dari kata *de* (menghilangkan) dan *bug* (serangga). Dalam pemrograman, istilah *debug* mengacu pada proses menghilangkan kesalahan (*runtime error*) yang ada dalam program. Untuk melakukan *debug* diperlukan aplikasi yang disebut *debugger*. Umumnya kompiler modern seperti GCC, Microsoft Visual C++ Compiler sudah disertai dengan aplikasi *debugger*. Aplikasi ini akan sangat berguna dan lebih mudah digunakan jika digabungkan dengan IDE. Berikut contoh proses *debug* dengan menggunakan IDE QtCreator dan [GDB](http://www.gnu.org/s/gdb/).

![QtCreator dan GDB](/public/img/2014-12-03/qtcreator-debug.png)

Pada *screenshot* diatas ditampilkan bagaimana programer dapat menghentikan eksekusi program melalui *breakpoint* pada baris tertentu (**baris ke-12**), kemudian programmer juga dapat mengamati nilai dari variabel (x, y dan z) sampai pada baris tersebut. Selain itu, masih banyak lagi yang dapat diamati melalui *debugger*, misalnya urutan pemanggilan fungsi (*call stack*), isi memory (*memory dump*), dll. Disamping itu, sebenarnya melalui *debugger* programer dapat menelusuri bagaimana program yang ia buat dijalankan *step-by-step*, dan pemahaman ini sangat membantu untuk meningkatkan kemampuan koding.  

### Entry point

*Entry point* adalah posisi kode yang pertama kali dieksekusi oleh *Operating System* saat program dijalankan. Pada bahasa pemrograman C/C++, program pertama kali dieksekusi mulai dari fungsi **main**. Berikut adalah beberapa cara mendeklarasikan fungsi **main** yang benar.
{% highlight cpp linenos %}
int main(void);
int main();
 
int main(int argc, char **argv);
int main(int argc, char *argv[]);
{% endhighlight %}

### bit dan byte

*bit* adalah singkatan dari [*binary digit*](http://dictionary.reference.com/browse/binary%20digit) (nilainya 0 atau 1 pada sistem bilangan biner). Selanjutnya, *byte* merupakan istilah untuk besaran 8-bit. Satuan *bit* ditulis dengan **b** (misalnya pada satuan kecepatan internet dalam kbps, Mbps, dan lain-lain), sedangkan *byte* ditulis dengan huruf kapital **B** (contoh pada kapasitas memori MB, GB). Beberapa besaran terkait

- 1 **kilobyte** (KB) sama dengan 2<sup>10</sup> bytes = 1024 bytes.
- 1 **megabyte** (MB) sama dengan 2<sup>20</sup> bytes = 1024 KB.
- 1 **gigabyte** (GB) sama dengan 2<sup>30</sup> bytes = 1024 MB.
- 1 **terabyte** (TB) sama dengan 2<sup>40</sup> bytes = 1024 GB.
- 1 **petabyte** (PB) sama dengan 2<sup>50</sup> bytes = 1024 TB.
- 1 **exabyte** (EB) sama dengan 2<sup>60</sup> bytes = 1024 PB.

## Referensi

1. C++ Programming Terminology. [http://www.flashcardmachine.com/c-programming-terminology.html](http://www.flashcardmachine.com/c-programming-terminology.html)
2. Terms used in C++. [http://www.sstutor.com/cpp/terms.htm](http://www.sstutor.com/cpp/terms.htm)
3. C++ Glossary. [http://www.glenmccl.com/glos.htm](http://www.glenmccl.com/glos.htm)
4. Bjarne Stroustrup's C++ Glossary. [http://www.stroustrup.com/glossary.html](http://www.stroustrup.com/glossary.html)
5. Basic Terminology for Programming in C++. [http://www.cs.ucla.edu/classes/winter05/cs31/lectures/defs.html](http://www.cs.ucla.edu/classes/winter05/cs31/lectures/defs.html)
6. Program errors and exception handling. [http://www.inf.unibz.it/~calvanese/teaching/05-06-ip/lecture-notes/uni10/uni10-main.html](http://www.inf.unibz.it/~calvanese/teaching/05-06-ip/lecture-notes/uni10/uni10-main.html)

(/ips)
