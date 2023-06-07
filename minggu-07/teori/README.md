# Ringkasan Minggu Ke-7
Nama : Muhammad Naufal Ramadhan

NIM : 205410138

Kelas : IF-3

## Bab 9 Classes
Kelas dalam Python menggabungkan data dan fungsi bersama-sama. Dengan membuat kelas baru, kita bisa menciptakan objek baru dengan tipe yang berbeda. Setiap objek kelas memiliki atribut untuk menyimpan keadaannya dan metode untuk memodifikasinya. 

Python's class mechanism sederhana dengan sintaksis dan semantik minimal, menggabungkan fitur-fitur standar Pemrograman Berorientasi Objek. Kelas-kelas Python bersifat dinamis, bisa dibuat dan dimodifikasi saat program berjalan. Dalam Python, kita dapat menggunakan tipe bawaan sebagai kelas dasar dan mendefinisikan ulang operator bawaan untuk objek kelas.

### 9.1. A Word About Names and Objects

Objek memiliki individualitas dan dapat memiliki beberapa nama yang terikat padanya (aliasing). Aliasing ini tidak perlu dikhawatirkan ketika menggunakan tipe data dasar yang tidak dapat diubah. Namun, pada objek yang dapat diubah seperti daftar atau kamus, aliasing dapat memiliki efek yang mengejutkan. Aliasing ini sering digunakan dengan manfaat, karena alias berperilaku seperti pointer. Misalnya, melewatkan objek pada fungsi hanya membutuhkan pengiriman pointer, sehingga lebih efisien. Jika fungsi memodifikasi objek yang dilewatkan sebagai argumen, perubahan tersebut akan terlihat oleh pemanggil. Ini menghilangkan kebutuhan untuk mekanisme pengiriman argumen yang berbeda seperti pada bahasa Pascal.

### 9.2. Python Scopes and Namespaces

Namespace adalah pemetaan dari nama ke objek. Terdapat beberapa jenis namespace dalam Python, seperti namespace bawaan (berisi fungsi dan pengecualian bawaan), namespace global dalam modul, dan namespace lokal dalam fungsi.

Atribut adalah nama yang mengikuti tanda titik setelah sebuah objek. Dalam modul, atribut merujuk pada namespace global. Atribut bisa hanya-baca atau dapat ditulisi, dan dapat dihapus dengan pernyataan del.

Cakupan (scope) adalah wilayah teks dalam program Python di mana sebuah namespace dapat diakses secara langsung. Ada beberapa cakupan yang saling tertaut dalam eksekusi:

- Cakupan terdalam berisi nama-nama lokal dalam fungsi.
- Cakupan fungsi yang mengelilingi, berisi nama-nama non-lokal dan non-global.
- Cakupan sebelumnya berisi nama-nama global modul saat ini.
- Cakupan terluar adalah namespace yang berisi nama-nama bawaan.

Jika suatu nama dideklarasikan sebagai global, maka referensi dan penugasan akan langsung mengarah ke cakupan sebelumnya yang berisi nama-nama global modul. Untuk mengubah variabel di luar cakupan terdalam, dapat digunakan pernyataan nonlocal.

Penting untuk menyadari bahwa cakupan ditentukan secara statis, tetapi digunakan secara dinamis. Saat menjalankan program, terdapat 3 atau 4 cakupan bertingkat yang dapat diakses secara langsung. Namun, pencarian nama dilakukan secara dinamis saat runtime.

Di Python, penugasan nama selalu masuk ke cakupan terdalam jika tidak ada pernyataan global atau nonlocal yang berlaku. Penugasan tidak mengkopi data, tetapi hanya mengikat nama ke objek. Hal yang sama berlaku untuk penghapusan: pernyataan del menghapus ikatan nama dari namespace lokal.

Pernyataan global digunakan untuk menunjukkan bahwa variabel tertentu berada dalam cakupan global dan harus diikat di sana, sementara pernyataan nonlocal menunjukkan bahwa variabel tertentu berada dalam cakupan yang mengelilingi dan harus diikat di sana.

#### 9.2.1. Python Scopes and Namespaces

 Berikut ini contoh penggunaan yang menunjukkan perbedaan cakupan dan namespace, serta pengaruh global dan nonlocal pada pengikatan variabel:

 ```python
    def scope_test():
    def do_local():
        spam = "local spam"

    def do_nonlocal():
        nonlocal spam
        spam = "nonlocal spam"

    def do_global():
        global spam
        spam = "global spam"

    spam = "test spam"
    do_local()
    print("Setelah assignment lokal:", spam)
    do_nonlocal()
    print("Setelah assignment nonlocal:", spam)
    do_global()
    print("Setelah assignment global:", spam)

    scope_test()
    print("Di dalam cakupan global:", spam)
```

Output:

Setelah assignment lokal: test spam
Setelah assignment nonlocal: nonlocal spam
Setelah assignment global: nonlocal spam
Di dalam cakupan global: global spam

Perhatikan bahwa assignment lokal tidak mengubah pengikatan spam dalam scope_test. Assignment nonlocal mengubah pengikatan spam dalam scope_test, dan assignment global mengubah pengikatan level modul. Sebelum assignment global, tidak ada pengikatan sebelumnya untuk spam.

### 9.3 A First Look at Classes

Kelas memperkenalkan sedikit sintaks baru, tiga tipe objek baru, dan beberapa semantik baru.

#### 9.3.1. Class Definition Syntax

Definisi kelas harus dieksekusi sebelum memiliki efek. Bisa ditempatkan di dalam percabangan if atau fungsi.

Definisi kelas umumnya berisi definisi fungsi, tetapi juga dapat berisi pernyataan lain yang berguna. Definisi fungsi dalam kelas memiliki format argumen yang khusus sesuai konvensi pemanggilan metode.

Saat memasuki definisi kelas, namespace baru dibuat sebagai cakupan lokal. Semua assignment ke variabel lokal dilakukan dalam namespace baru ini. Definisi fungsi mengikat nama fungsi baru di dalam namespace tersebut.

Setelah definisi kelas selesai (dalam blok akhirnya), sebuah objek kelas dibuat. Objek ini adalah pembungkus yang berisi konten dari namespace yang dibuat oleh definisi kelas. Di cakupan lokal asli sebelumnya (sebelum masuk ke definisi kelas), objek kelas diikat dengan nama kelas yang diberikan dalam header definisi kelas (ClassName dalam contoh tersebut).

#### 9.3.2. Class Objects

Objek kelas mendukung dua jenis operasi: referensi atribut dan instansiasi.

- Referensi atribut menggunakan sintaks standar obj.nama, di mana nama atribut valid adalah semua nama yang ada dalam namespace kelas saat objek kelas dibuat. Misalnya, MyClass.i dan MyClass.f mengembalikan nilai integer dan objek fungsi, masing-masing.
- Instansiasi kelas menggunakan notasi fungsi. Misalkan kita memiliki kelas MyClass, kita dapat membuat instansi baru dengan memanggilnya seperti fungsi tanpa parameter: x = MyClass(). Ini akan menciptakan objek instansi baru dari kelas tersebut dan menugaskannya ke variabel lokal x.
- Pada saat instansiasi kelas, jika kelas mendefinisikan metode init(), metode tersebut akan secara otomatis dipanggil untuk objek instansi yang baru dibuat. Metode init() ini dapat memiliki argumen untuk menginisialisasi objek dengan keadaan awal tertentu.
- Selain itu, metode init() juga dapat menerima argumen saat instansiasi kelas, yang akan diteruskan ke metode init(). Misalnya, dalam kelas Complex, argumen realpart dan imagpart akan digunakan untuk menginisialisasi atribut self.r dan self.i.

#### 9.3.3. Instance Objects

Instance objects hanya dapat melakukan operasi referensi atribut. Ada dua jenis atribut yang valid: atribut data dan metode.

Atribut data adalah variabel yang terkait dengan objek instansi. Mereka muncul saat pertama kali diberikan nilai dan tidak perlu dideklarasikan.

Metode adalah fungsi yang "dimiliki oleh" objek. Nama metode yang valid untuk objek instansi tergantung pada kelasnya. 

#### 9.3.4. Method Objects

Biasanya, metode dipanggil segera setelah diikat dengan menggunakan sintaksis objek_metode(). Namun, metode juga dapat disimpan untuk dipanggil nanti. Ketika sebuah metode dipanggil, objek instansi secara otomatis diteruskan sebagai argumen pertama kepada fungsi metode.

Dalam implementasinya, saat sebuah atribut non-data dari objek instansi dirujuk, kelas objek tersebut akan dicari. Jika atribut tersebut adalah objek fungsi yang valid dalam kelas, maka objek metode akan dibuat dengan menggabungkan objek instansi dan objek fungsi dalam sebuah objek abstrak. Ketika metode dipanggil dengan argumen, sebuah daftar argumen baru akan dibuat dengan menyisipkan objek instansi sebagai argumen pertama, kemudian fungsi metode akan dipanggil dengan daftar argumen baru ini.

#### 9.3.5. Class and Instance Variables

Secara umum, variabel instansi digunakan untuk data yang unik untuk setiap objek instansi, sedangkan variabel kelas digunakan untuk atribut dan metode yang dibagikan oleh semua objek instansi dalam kelas:

Namun, perlu diingat bahwa penggunaan data yang dibagikan dapat memiliki efek yang tidak terduga dengan objek yang dapat diubah, seperti list atau dictionary. Jadi, sebaiknya hindari menggunakan variabel kelas untuk objek mutable tersebut.

### 9.4. Random Remarks

Jika nama atribut yang sama muncul baik pada objek instansi maupun pada kelas, maka pencarian atribut memberikan prioritas pada objek instansi.

Atribut data dapat diakses oleh metode maupun oleh pengguna biasa. Python tidak memberikan mekanisme untuk mengimplementasikan data hiding secara ketat, namun hal ini berdasarkan konvensi.

Penggunaan atribut data perlu diperhatikan agar tidak merusak invarian yang dijaga oleh metode. Klien dapat menambahkan atribut data mereka sendiri pada objek instansi tanpa mempengaruhi validitas metode, selama tidak ada konflik nama.

Tidak ada singkatan khusus untuk merujuk pada atribut data (atau metode lainnya) dari dalam metode. Hal ini meningkatkan keterbacaan metode dan menghindari kebingungan antara variabel lokal dan variabel instansi.

Biasanya, argumen pertama dari sebuah metode dinamakan self, namun ini hanyalah sebuah konvensi dan tidak memiliki makna khusus bagi Python.

Fungsi yang didefinisikan sebagai atribut kelas berfungsi sebagai metode untuk objek instansi dari kelas tersebut. Fungsi tersebut tidak harus didefinisikan di dalam definisi kelas, namun dapat diatributkan ke variabel lokal dalam kelas.

Metode dapat memanggil metode lainnya dengan menggunakan atribut metode dari argumen self.

Metode dapat merujuk pada nama-nama global seperti halnya fungsi biasa. Ruang lingkup global yang terkait dengan sebuah metode adalah modul yang berisi definisinya.

Setiap nilai adalah objek dan memiliki sebuah kelas (tipe). Kelas objek dapat diakses melalui object.class.

### 9.5. Inheritance

Pewarisan (inheritance) didukung dalam Python melalui penggunaan kelas turunan (derived classes). Sintaks untuk mendefinisikan kelas turunan adalah sebagai berikut:

 ```python
class DerivedClassName(NamaKelasInduk):
    <pernyataan>
```

NamaKelasInduk harus didefinisikan dalam cakupan yang berisi definisi kelas turunan. Ekspresi lain juga diperbolehkan sebagai nama kelas induk.

Kelas turunan dapat menggantikan (override) metode-metode dari kelas induknya. Ketika atribut tidak ditemukan dalam kelas turunan, pencarian dilanjutkan ke kelas induk. Proses ini bersifat rekursif jika kelas induk itu sendiri merupakan turunan dari kelas lain.

Referensi metode diresolusikan dengan mencari atribut kelas yang sesuai, dengan turun ke kelas-kelas induk jika diperlukan.

Untuk memanggil metode dari kelas induk secara langsung, gunakan sintaks NamaKelasInduk.namametode(self, argumen). Hal ini dapat berguna untuk memperluas (extend) metode kelas induk dalam kelas turunan.

Python menyediakan fungsi isinstance() untuk memeriksa tipe suatu instansi dan fungsi issubclass() untuk memeriksa pewarisan kelas.

#### 9.5.1. Multiple Inheritance

Pewarisan ganda (multiple inheritance) didukung dalam Python. Sebuah kelas dapat memiliki beberapa kelas induk yang didefinisikan sebagai berikut:

 ```python
class DerivedClassName(Induk1, Induk2, Induk3):
    <pernyataan>
 ```
 
Pencarian atribut yang diwarisi mengikuti urutan secara vertikal ke bawah, dari kiri ke kanan, menghindari pencarian ganda dalam kelas yang sama.

Urutan resolusi metode berubah secara dinamis untuk mendukung pemanggilan kooperatif ke super(), memungkinkan pembuatan kelas yang dapat diandalkan dan diperluas dengan pewarisan ganda.

Perubahan urutan dinamis diperlukan untuk menangani kasus di mana terdapat hubungan diamond dalam hierarki pewarisan, memastikan setiap kelas induk hanya dipanggil satu kali dan mempertahankan urutan kiri ke kanan.

### 9.6. Private Variables

Python tidak memiliki variabel instance "private" yang tidak dapat diakses kecuali dari dalam objek. Namun, ada konvensi yang diikuti oleh sebagian besar kode Python: nama yang diawali dengan garis bawah (misalnya _spam) dianggap sebagai bagian non-publik dari API dan dapat berubah tanpa pemberitahuan.

Ada juga dukungan terbatas untuk anggota kelas "private" dengan mekanisme yang disebut name mangling. Identifier dengan format __spam (minimal dua garis bawah di awal, maksimal satu garis bawah di akhir) digantikan dengan _namakelas__spam. Name mangling ini berguna untuk menghindari konflik nama dengan kelas turunan.

Name mangling berguna untuk memungkinkan subclass mengganti metode tanpa mengganggu pemanggilan metode dalam kelas yang sama.

Perlu diperhatikan bahwa aturan mangling dirancang terutama untuk menghindari kecelakaan; masih memungkinkan untuk mengakses atau mengubah variabel yang dianggap sebagai private. Hal ini bahkan bisa berguna dalam situasi khusus, seperti dalam debugger.

Perlu diperhatikan bahwa kode yang dilewatkan ke exec() atau eval() tidak mempertimbangkan nama kelas dari kelas yang memanggil sebagai kelas saat ini; ini mirip dengan efek dari pernyataan global, yang juga dibatasi hanya untuk kode yang dikompilasi menjadi byte bersama-sama. Batasan yang sama berlaku untuk getattr(), setattr(), dan delattr(), serta saat merujuk langsung ke dict.

### 9.7. Odds and Ends

Kadang-kadang berguna memiliki tipe data yang mirip dengan "record" dalam Pascal atau "struct" dalam C, yang menggabungkan beberapa item data bernama.

Kode Python yang membutuhkan tipe data abstrak tertentu seringkali dapat menerima kelas yang meniru metode dari tipe data tersebut sebagai gantinya. Misalnya, jika Anda memiliki sebuah fungsi yang memformat data dari objek file, Anda dapat mendefinisikan sebuah kelas dengan metode read() dan readline() yang mengambil data dari buffer string, dan mengirimkannya sebagai argumen.

Objek metode instan juga memiliki atribut: m.self adalah objek instan dengan metode m(), dan m.func adalah objek fungsi yang sesuai dengan metode tersebut.

### 9.8. Iterators

Dalam Python, Anda dapat menggunakan pernyataan for untuk mengulang elemen-elemen dalam objek kontainer. Ini dimungkinkan karena di balik layar, for statement memanggil fungsi iter() pada objek kontainer untuk mendapatkan iterator. Iterator ini memiliki metode next() yang mengakses elemen-elemen satu per satu. Ketika tidak ada elemen lagi, StopIteration exception dipicu untuk mengakhiri perulangan.

Untuk membuat kelas Anda dapat diulang dengan menggunakan iterator, Anda perlu mendefinisikan metode iter() yang mengembalikan objek dengan metode next().

### 9.9. Generators

Generator adalah alat sederhana dan kuat untuk membuat iterator. Mereka ditulis seperti fungsi reguler, tetapi menggunakan pernyataan yield ketika ingin mengembalikan data. Setiap kali next() dipanggil, generator melanjutkan dari titik terakhir (mengingat nilai data dan pernyataan terakhir yang dieksekusi).

Yang membuat generator kompak adalah bahwa metode iter() dan next() dibuat secara otomatis. Selain itu, variabel lokal dan status eksekusi disimpan secara otomatis antara pemanggilan. Ini membuat fungsi lebih mudah ditulis dan lebih jelas daripada menggunakan variabel instansiasi seperti self.index dan self.data. Selain itu, ketika generator berakhir, mereka secara otomatis memunculkan StopIteration. Dalam kombinasi, fitur-fitur ini memudahkan pembuatan iterator tanpa usaha lebih banyak dibandingkan menulis fungsi reguler.

### 9.10. Generator Expressions

Generator expressions adalah ekspresi yang digunakan untuk membuat generator dengan cara yang ringkas. Mereka menggunakan sintaks yang mirip dengan list comprehensions, tetapi dengan tanda kurung () daripada tanda kurung siku []. Generator expressions dirancang untuk situasi di mana generator digunakan langsung oleh fungsi yang mengelilinginya. Mereka lebih ringkas tetapi kurang serbaguna daripada definisi generator lengkap, dan cenderung lebih ramah terhadap penggunaan memori daripada list comprehensions yang setara.
