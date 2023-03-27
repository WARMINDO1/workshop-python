# Ringkasan Minggu Ke-3
Nama : Muhammad Naufal Ramadhan

NIM : 205410138

Kelas : IF-3

## Bab 5 Struktur Data
Bab ini menjelaskan beberapa hal yang telah di pelajari secara lebih mendetail, dan menambahkan beberapa hal baru juga.

### More on List
Tipe data list memiliki beberapa metode lagi. Berikut ini semua metode objek daftar:

Dalam bahasa pemrograman Python, struktur data yang paling dasar adalah urutan atau lists. Setiap elemen-elemen berurutan akan diberi nomor posisi atau indeksnya. Indeks pertama dalam list adalah nol, indeks kedua adalah satu dan seterusnya.
List adalah tipe data yang paling serbaguna yang tersedia dalam bahasa Python, yang dapat ditulis sebagai daftar nilai yang dipisahkan koma (item) antara tanda kurung siku. Hal penting tentang daftar adalah item dalam list tidak boleh sama jenisnya.

Ciri-ciri utama dari tipe data list ini adalah memiliki urutan atau list yang ada di dalam datanya. Nanti dalam elemennya akan diberikan nomor-nomor posisi. 
Tipe data list ini memiliki banyak fitur yang bisa di manfaatkan. Ketika ingin memanggil salah satu kelompok data dalam suatu list, maka kita bisa memakai fitur di dalamnya yaitu fitur call dengan memanggil urutan angka atau nomor indeksnya.

### 5.1.1 Using List as Stacks
 
Metode list membuatnya sangat mudah untuk menggunakan list sebagai tumpukan, di mana elemen terakhir yang ditambahkan adalah elemen pertama yang diambil (“last-in, first-out”). Untuk menambahkan item ke atas tumpukan, gunakan append(). Untuk mengambil item dari atas tumpukan, gunakan pop()tanpa indeks eksplisit

Stack adalah struktur data yang dapat ditunjukkan oleh tempat penyisipan dan penghapusan elemen terjadi hanya pada satu tempat yang disebut puncak tumpukan. Cara dasar untuk mengakses data di stack adalah dengan metode Last In First Out (LIFO). Untuk memahami struktur stack, bayangkan setumpuk buku. Seseorang hanya bisa menggunakan ujung atas tumpukan untuk menambahkan atau mengeluarkan buku dari tumpukan. Juga, nomor indeks tidak bisa digunakan ke elemen dalam tumpukan, oleh karena itu, elemen di tengah tumpukan tidak dapat diakses secara langsung. Dalam Python kita bisa menggunakan list sebagai stack, lebih lanjut mengenai List Di Python.

### 5.1.2. Using List as Queues

Queue adalah struktur data yang bisa diwakili oleh antrian (urutan). Dengan kata lain memiliki depan dan belakang.
Antrian struktur data ini mengikuti prinsip First In First Out (FIFO). Penambahan elemen disebut “Enqueue” dan Penghapusan elemen disebut “Dequeue”. Enqueue berlangsung di bagian belakang, sementara Dequeue terjadi di depan. Untuk menggunakan list sebagai queue dalam Python, kita menggunakan collections.deque.

Dimungkinkan juga untuk menggunakan daftar sebagai antrian, di mana elemen pertama yang ditambahkan adalah elemen pertama yang diambil (“first-in, first-out”); namun, daftar tidak efisien untuk tujuan ini. Sementara menambahkan dan muncul dari akhir daftar cepat, melakukan sisipan atau muncul dari awal daftar lambat (karena semua elemen lain harus digeser satu).

### 5.1.3. List Comprehensions

List Comprehensions menyediakan cara ringkas untuk membuat list. Aplikasi umum adalah membuat daftar baru di mana setiap elemen adalah hasil dari beberapa operasi yang diterapkan ke setiap anggota urutan lain atau iterable, atau untuk membuat urutan elemen yang memenuhi kondisi tertentu.
Seperti yang sudah disebutkan sebelumnya, list comprehension merupakan ternary operator pada Python yang berfungsi untuk mempersingkat proses inisialisasi variable list.

Akan tetapi list comprehension biasanya digunakan hanya untuk membuat program-program yang simple. 

Keuntungan menggunakan daftar komprehensi. Berikut ini adalah keuntungannya:
- Penggunaan daftar komprehensi lebih hemat waktu dan hemat ruang daripada loop.
- Anda hanya memerlukan lebih sedikit baris kode.
- Anda dapat mengubah pernyataan iteratif menjadi rumus.

### 5.1.4. Nested List Comprehensions

Nested list comprehension adalah list comprehension yang mengandung satu atau lebih ekspresi for yang tertulis secara bertingkat, sehingga dapat memproses elemen dari dua atau lebih list secara bersamaan.

Nested list comprehension mungkin terdengar mirip dengan list comprehension dengan nested loop, tapi sebenarnya sangat bebeda. Ekspresi awal dalam pemahaman daftar dapat berupa sembarang ekspresi, termasuk list comprehension lainnya.

### 5.2 The del statement

Cara untuk menghapus item dari daftar yang diberikan indeksnya alih-alih nilainya: pernyataan del. Ini berbeda dari pop()metode yang mengembalikan nilai. Pernyataan itu deljuga dapat digunakan untuk menghapus irisan dari daftar atau menghapus seluruh daftar (yang kita lakukan sebelumnya dengan menugaskan daftar kosong ke irisan).

Perintah del berguna untuk menghemat ruang memori dan membersihkan sumber daya yang tidak digunakan. Namun, perlu diingat bahwa penggunaan perintah del dengan sembarangan dapat menyebabkan kehilangan data yang tidak diinginkan atau menghasilkan kesalahan runtime jika objek yang dihapus masih digunakan oleh kode lain. Oleh karena itu, perlu mempertimbangkan secara cermat sebelum menggunakan perintah del.

### 5.3 Tuples and Sequences

Tipe data sequence digunakan untuk kumpulan tipe data yang terorganisir. Tipe data yang masuk kebagian ini adallah list dan tuple.

Tuple dalam Python adalah stuktur data yang digunakan untuk menyimpan sekumpulan data. Tupe bersifat immutable, artinya isi tuple tidak bisa kita ubah dan hapus. Namun, dapat kita isi dengan berbagai macam nilai dan objek.

Mengakses data pada tuple tidak jauh berbeda dengan cara mengakses data pada list, bahkan bisa kita bilang sama persis dalam keumumannya.
Kita bisa mengakses nilai pada tuple dengan langsung mendefinisikan indeks-nya. Kita juga bisa mengakses nilai pada tuple dengan negatif indeks 

### 5.4. Sets

Tipe data set adalah koleksi tak terurut tanpa elemen duplikat. Penggunaan dasar termasuk pengujian keanggotaan dan menghilangkan entri duplikat. Set objek juga mendukung operasi matematika seperti penyatuan, persimpangan, perbedaan, dan perbedaan simetris.

Tipe data set ini sangat mirip dengan tipe sequence tetapi set itu memiliki data yang tidak berurutan dan tidak terindeks. Set berada diantara tanda kurung kurawal buka dan penutup ({ dan }) dan setiap item dipisahkan tanda koma (,).

Set ini tidak boleh ada data yang duplikat, tidak dapat diubah lagi setelah menentukan nilainya, serta tidak memiliki rujukan seperti indeks dan key.

Set memiliki panjang yang dapat dicek dengan len() serta set dapat menyimpan tipe data yang berbeda-beda dan gunakan method set() untuk jadikan ke tipe set.

### 5.5. Dictionaries

Dictionary merupakan tipe data pada Python yang berfungsi untuk menyimpan kumpulan data atau nilai, yang setiap urutanya berisi key dan value. Jika biasanya kita ingin mengakses nilai pada list menggunakan indeks, di dictionary ini kita perlu kata kunci (key) untuk mengakses nilainya.

Dictionary terkadang ditemukan dalam bahasa lain sebagai "memori asosiatif" atau "array asosiatif". Tidak seperti urutan, yang diindeks oleh rentang angka, kamus diindeks oleh key , yang dapat berupa tipe apa pun yang tidak dapat diubah; string dan angka selalu bisa menjadi kunci. Tupel dapat digunakan sebagai kunci jika hanya berisi string, angka, atau tupel; jika tuple berisi objek yang dapat diubah baik secara langsung maupun tidak langsung, itu tidak dapat digunakan sebagai kunci. Anda tidak dapat menggunakan daftar sebagai kunci, karena daftar dapat dimodifikasi menggunakan penetapan indeks, penetapan irisan, atau metode seperti append()dan extend().

Operasi utama pada kamus adalah menyimpan nilai dengan beberapa kunci dan mengekstraksi nilai yang diberikan kunci tersebut. Dimungkinkan juga untuk menghapus key:value pair dengan del. Jika Anda menyimpan menggunakan kunci yang sudah digunakan, nilai lama yang terkait dengan kunci tersebut akan dilupakan. Merupakan kesalahan untuk mengekstrak nilai menggunakan kunci yang tidak ada.

Melakukan list(d)di kamus mengembalikan daftar semua kunci yang digunakan dalam kamus, dalam urutan penyisipan (jika Anda ingin diurutkan, gunakan saja sorted(d)). Untuk memeriksa apakah satu kunci ada di kamus, gunakan inkata kunci.

### 5.6. Looping Techniques

Saat menggunakan looping pada dictionaries ada beberapa teknik yang digunakan dalam Python

Fungsi enumerate() adalah fungsi yang digunakan untuk mengembalikan panjang iterable dan mengulang itemnya secara bersamaan. Jadi, saat kita mencetak setiap item dalam tipe data yang dapat diubah, secara bersamaan output akan mengeluarkan indeksnya.

zip() function adalah fungsi di Python yang menerima objek iterable sebagai argumen dan mengembalikan iterator. Iterator ini menghasilkan rangkaian tuple yang berisi item dari setiap iterable, dimana item pertama di setiap iterable dipasangkan bersama, begitu juga untuk urutan item lainnya. Jika iterable memiliki panjang yang berbeda, maka panjang iterator baru yang terbentuk ditentukan berdasarkan panjang iterable yang terpendek.

reversed() function berfungsi untuk memutarbalikkan atau membalikkan urutan posisi elemen pada tipe data gabungan seperti tipe data list

sorted() berfungsi untuk mengulang urutan dalam urutan terurut dengan fungsi yang mengembalikan daftar terurut baru sambil membiarkan sumbernya tidak berubah.

Menggunakan set()urutan menghilangkan elemen duplikat. Penggunaan sorted()dalam kombinasi dengan set()urutan adalah cara idiomatis untuk mengulang elemen unik dari urutan dalam urutan yang diurutkan.

### 5.7. More on Conditions

Kondisi yang digunakan dalam whiledan ifpernyataan dapat berisi operator apa pun, bukan hanya perbandingan.

Operator pembanding indan adalah pengujian keanggotaan yang menentukan apakah suatu nilai ada di dalam (atau tidak di dalam) wadah. Operator dan membandingkan apakah dua objek benar-benar objek yang sama. Semua operator pembanding memiliki prioritas yang sama, yang lebih rendah dari semua operator numerik.not inisis not

Perbandingan dapat dirantai. Misalnya, menguji apakah kurang dari dan terlebih lagi sama dengan .a < b == cabbc

Perbandingan dapat digabungkan menggunakan operator Boolean anddan or, dan hasil perbandingan (atau ekspresi Boolean lainnya) dapat ditiadakan dengan not. Ini memiliki prioritas lebih rendah daripada operator pembanding; di antara mereka, notmemiliki prioritas tertinggi dan orterendah, sehingga setara dengan . Seperti biasa, tanda kurung dapat digunakan untuk menyatakan komposisi yang diinginkan.A and not B or C(A and (not B)) or C
Operator Boolean anddan ordisebut operator hubung singkat : argumen mereka dievaluasi dari kiri ke kanan, dan evaluasi berhenti segera setelah hasilnya ditentukan.

### 5.8. Comparing Sequences and Other Types

Objek urutan biasanya dapat dibandingkan dengan objek lain dengan tipe urutan yang sama. Perbandingannya menggunakan leksikografispengurutan: pertama dua item pertama dibandingkan, dan jika berbeda, ini menentukan hasil perbandingan; jika sama, dua item berikutnya dibandingkan, dan seterusnya, sampai salah satu urutannya habis. Jika dua item yang akan dibandingkan itu sendiri adalah urutan dari jenis yang sama, perbandingan leksikografis dilakukan secara rekursif. Jika semua item dari dua urutan sebanding, urutannya dianggap sama. Jika satu urutan adalah sub-urutan awal dari yang lain, urutan yang lebih pendek adalah yang lebih kecil (lebih kecil). Pengurutan leksikografis untuk string menggunakan nomor poin kode Unicode untuk mengurutkan karakter individual.

Perhatikan bahwa membandingkan objek dari jenis yang berbeda dengan <atau >legal asalkan objek tersebut memiliki metode perbandingan yang sesuai. Misalnya, tipe numerik campuran dibandingkan berdasarkan nilai numeriknya, jadi 0 sama dengan 0,0, dll. Jika tidak, alih-alih memberikan pengurutan arbitrer, penafsir akan memunculkan pengecualian TypeError.
