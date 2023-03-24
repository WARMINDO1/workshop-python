# Ringkasan Minggu Ke-2
Nama : Muhammad Naufal Ramadhan

NIM : 205410138

Kelas : IF-3

## Bab 4 Pengendali Aliran Program
Selain whilepernyataan yang baru saja diperkenalkan, Python menggunakan pernyataan kontrol aliran biasa yang dikenal dari bahasa lain, dengan beberapa perubahan.

### if Statement
Pengambilan keputusan (kondisi if) digunakan untuk mengantisipasi kondisi yang terjadi saat jalanya program dan menentukan tindakan apa yang akan diambil sesuai dengan kondisi.
Pada python ada beberapa statement/kondisi diantaranya adalah if, else dan elif Kondisi if digunakan untuk mengeksekusi kode jika kondisi bernilai benar True. Jika kondisi bernilai salah False maka statement/kondisi if tidak akan di-eksekusi.

### for Statement
For statement adalah perintah yang digunakan untuk melakukan perulangan atau iterasi. For pada python memiliki perilaku yang berbeda dengan for pada kebanyakan bahasa pemrograman yang lain, karena pada python ia sangat berkaitan dengan data sequence atau data kolektif. Mungkin kalau dibandingkan dengan bahasa lain, for pada python lebih dikenal sebagai foreach.
Fungsi range() merupakan fungsi yang menghasilkan list. Fungsi ini akan menciptakan sebuah list baru dengan rentang nilai tertentu. Jika memerlukan perulangan urutan angka maka fungsi range() akan berguna. Ini menghasilkan proses aritmatika.

Dalam banyak hal objek yang dikembalikan oleh range()berperilaku seolah-olah itu adalah daftar, tetapi sebenarnya bukan. Ini adalah objek yang mengembalikan item berturut-turut dari urutan yang diinginkan saat Anda mengulanginya, tetapi tidak benar-benar membuat daftar, sehingga menghemat ruang.

objek seperti itu dapat dirubah , yaitu cocok sebagai target untuk fungsi dan konstruksi yang mengharapkan sesuatu dari mana mereka dapat memperoleh item berturut-turut hingga persediaan habis.

### Break dan Continue Statement, dan Klause else pada Perulangan 
Statement break pada Python sama seperti di C, keluar dari perulangan for atau perulangan while
Kalau sebelumnya ada break yang berfungsi untuk keluar dari loop, sekarang ada continue yang fungsinya adalah untuk lompat ke iterasi selanjutnya tanpa harus mengeksekusi sisa kode yang ada di bawahnya.

Perbedaan utama dari break dan continue adalah jika break akan menghentikan perulangan secara total, sedangkan continue hanya akan lompat ke iterasi selanjutnya. Ketika dipanggil, keduanya sama-sama akan mengabaikan semua perintah yang ada di bawahnya.

### Pass Statement
Statement Pass adalah sebuah statemen pada python yang tidak memiliki tugas apa pun. Tidak menginstruksi sistem untuk melakukan satu hal pun. Ia ada, tapi keberadaannya seolah tidak ada.

Fungsinya, berguna sebagai placeholder untuk suatu fungsi atau suatu class yang belum kita implementasikan secara nyata.

### Match Statement
Pernyataan matchmengambil ekspresi dan membandingkan nilainya dengan pola berurutan yang diberikan sebagai satu atau lebih blok kasus. Ini mirip dengan pernyataan switch di C, Java atau JavaScript (dan banyak bahasa lainnya), tetapi lebih mirip dengan pencocokan pola dalam bahasa seperti Rust atau Haskell. Hanya pola pertama yang cocok yang akan dieksekusi dan juga dapat mengekstrak komponen (elemen urutan atau atribut objek) dari nilai menjadi variabel.
Jika menggunakan kelas untuk menyusun data, maka dapat menggunakan nama kelas diikuti dengan daftar argumen yang menyerupai konstruktor

### Mendefinisikan Fungsi 
Fungsi dalam python merupakan kumpulan perintah yang dikelompokkan menjadi satu. Fungsi yang telah dibuat  ini nantinya akan bisa dipanggil serta digunakan berulang kali. Dengan menggunakan fungsi, programmer dapat mengefisienkan penulisan program, terutama program besar. Program yang awalnya besar dapat dipecah menjadi beberapa bagian serta fungsinya dipanggil sewaktu-waktu ketika dibutuhkan. Dengan kata lain, penggunaan fungsi ini membuat program lebih terstruktur. 

Kata kunci def, sebagai tanda bahwa blok kode program tersebut merupakan fungsi

Pernyataan pertama dari badan fungsi secara opsional dapat berupa string literal; literal string ini adalah string dokumentasi fungsi, atau docstring. Ada alat yang menggunakan docstring untuk menghasilkan dokumentasi online atau cetak secara otomatis, atau untuk membiarkan pengguna menelusuri kode secara interaktif; merupakan praktik yang baik untuk menyertakan dokumen dalam kode yang Anda tulis, jadi biasakanlah.

Eksekusi suatu fungsi memperkenalkan tabel simbol baru yang digunakan untuk variabel lokal dari fungsi tersebut . Lebih tepatnya, semua penugasan variabel dalam suatu fungsi menyimpan nilai dalam tabel simbol lokal; sedangkan referensi variabel pertama-tama terlihat di tabel simbol lokal, lalu di tabel simbol lokal fungsi terlampir, lalu di tabel simbol global, dan terakhir di tabel nama bawaan.
Parameter aktual (argumen) untuk pemanggilan fungsi diperkenalkan di tabel simbol lokal dari fungsi yang dipanggil saat dipanggil; dengan demikian, argumen diteruskan menggunakan call by value (di mana nilainya selalu merupakan referensi objek , bukan nilai objek).

Definisi fungsi mengaitkan nama fungsi dengan objek fungsi dalam tabel simbol saat ini. Penerjemah mengenali objek yang ditunjuk oleh nama itu sebagai fungsi yang ditentukan pengguna.

### Mendefinisikan Fungsi Lebih Dalam
**Nilai Argumen Default**

Bentuk yang paling berguna adalah menentukan nilai default untuk satu atau beberapa argumen. Ini menciptakan fungsi yang dapat dipanggil dengan lebih sedikit argumen daripada yang diizinkan.

Fungsi ini dapat dipanggil dengan beberapa cara:
- hanya memberikan argumen wajib
- memberikan salah satu argumen opsional
- atau bahkan memberikan semua argumen

**Note :**

Nilai default hanya dievaluasi sekali. Ini membuat perbedaan ketika defaultnya adalah objek yang dapat diubah seperti daftar, kamus, atau instance dari sebagian besar kelas.

**Argumen Kata Kunci**

Fungsi juga bisa dipanggil menggunakan argumen kata kunci dari form kwarg=value. Menerima satu argumen wajib ( voltage) dan tiga argumen opsional ( state, action, dan type).

Dalam pemanggilan fungsi, argumen kata kunci harus mengikuti argumen posisi. Semua argumen kata kunci yang diteruskan harus cocok dengan salah satu argumen yang diterima oleh fungsi (misalnya actorbukan argumen yang valid untuk parrotfungsi tersebut), dan urutannya tidak penting. Tidak ada argumen yang boleh menerima nilai lebih dari satu kali.

**Parameter Khusus**

Secara default, argumen dapat diteruskan ke fungsi Python baik dengan posisi atau secara eksplisit dengan kata kunci. Untuk keterbacaan dan kinerja, masuk akal untuk membatasi cara argumen dapat diteruskan sehingga pengembang hanya perlu melihat definisi fungsi untuk menentukan apakah item diteruskan oleh posisi, posisi atau kata kunci, atau kata kunci.

Definisi fungsi mungkin terlihat dimana /dan *adalah opsional. Jika digunakan, simbol ini menunjukkan jenis parameter dengan cara argumen dapat diteruskan ke fungsi: hanya posisi, posisi atau kata kunci, dan kata kunci saja. Parameter kata kunci juga disebut sebagai parameter bernama.

**Argumen Posisional atau Kata Kunci**

Jika /dan *tidak ada dalam definisi fungsi, argumen dapat diteruskan ke fungsi berdasarkan posisi atau kata kunci.

**Positional-Only Parameters**
Melihat ini sedikit lebih detail, dimungkinkan untuk menandai parameter tertentu sebagai positional-only . Jika positional-only , urutan parameter penting, dan parameter tidak dapat diteruskan dengan kata kunci. Parameter khusus posisi ditempatkan sebelum /(garis miring). The /digunakan untuk secara logis memisahkan parameter hanya posisional dari parameter lainnya. Jika tidak ada /dalam definisi fungsi, tidak ada parameter hanya posisi.
Parameter yang mengikuti /mungkin berupa posisi-atau-kata kunci atau kata kunci saja .

**Keyword-Only Arguments**
Untuk menandai parameter sebagai hanya kata kunci , yang menunjukkan bahwa parameter harus diteruskan oleh argumen kata kunci, tempatkan an *di daftar argumen tepat sebelum parameter khusus kata kunci pertama .

**Contoh Fungsi**

Definisi fungsi pertama, standard_arg, bentuk yang paling umum, tidak membatasi konvensi pemanggilan dan argumen dapat diteruskan oleh posisi atau kata kunci

Fungsi kedua pos_only_argdibatasi untuk hanya menggunakan parameter posisi seperti yang ada /dalam definisi fungsi

Fungsi ketiga kwd_only_argshanya mengizinkan argumen kata kunci seperti yang ditunjukkan oleh a *dalam definisi fungsi

Dan yang terakhir menggunakan ketiga konvensi pemanggilan dalam definisi fungsi yang sama

Akhirnya, pertimbangkan definisi fungsi ini yang memiliki potensi benturan antara argumen posisi name dan **kwdsyang memiliki namekunci. Tidak ada kemungkinan panggilan yang membuatnya kembali Truekarena kata kunci 'name' akan selalu mengikat ke parameter pertama.

Tetapi menggunakan /(argumen hanya posisi), itu dimungkinkan karena memungkinkan namesebagai argumen posisi dan 'name'sebagai kunci dalam argumen kata kunci:

**Rekap**

Kasus penggunaan akan menentukan parameter mana yang akan digunakan dalam definisi fungsi

Sebagai panduan:
- Gunakan hanya posisi jika Anda ingin nama parameter tidak tersedia untuk pengguna. Ini berguna ketika nama parameter tidak memiliki arti sebenarnya, jika Anda ingin menerapkan urutan argumen saat fungsi dipanggil atau jika Anda perlu mengambil beberapa parameter posisi dan kata kunci arbitrer.
- Gunakan hanya kata kunci jika nama memiliki arti dan definisi fungsi lebih mudah dipahami dengan nama yang eksplisit atau Anda ingin mencegah pengguna mengandalkan posisi argumen yang diteruskan.
- Untuk API, gunakan positional-only untuk mencegah perubahan API yang rusak jika nama parameter diubah di masa mendatang.

**Arbitrary Argument Lists**

menentukan bahwa suatu fungsi dapat dipanggil dengan jumlah argumen yang berubah-ubah. Argumen ini akan dibungkus dalam sebuah tuple. Sebelum jumlah argumen variabel, nol atau lebih argumen normal dapat terjadi.

Biasanya, argumen variadik ini akan menjadi yang terakhir dalam daftar parameter formal, karena mereka meraup semua argumen masukan yang tersisa yang diteruskan ke fungsi. Parameter formal apa pun yang muncul setelah *args parameter adalah argumen 'kata kunci saja', yang berarti bahwa parameter tersebut hanya dapat digunakan sebagai kata kunci daripada argumen posisional.

**Unpacking Argument Lists**

Situasi sebaliknya terjadi ketika argumen sudah ada dalam daftar atau tupel tetapi perlu dibongkar untuk pemanggilan fungsi yang memerlukan argumen posisi terpisah. Misalnya, fungsi bawaan range()mengharapkan argumen start dan stop yang terpisah. Jika tidak tersedia secara terpisah, tulis pemanggilan fungsi dengan -operator *untuk membongkar argumen dari daftar atau tupel:

Dengan cara yang sama, kamus dapat mengirimkan argumen kata kunci dengan -operator **

**Ekspresi Lambda**

Fungsi anonim kecil dapat dibuat dengan lambdakata kunci. Fungsi ini mengembalikan jumlah dari dua argumennya. Fungsi Lambda dapat digunakan di mana pun objek fungsi diperlukan. Mereka secara sintaksis dibatasi untuk satu ekspresi. fungsi lambda dapat mereferensikan variabel dari cakupan yang memuat:lambda a, b: a+b

**Dokumentasi string**

Parser Python tidak menghapus indentasi dari literal string multi-baris di Python, jadi alat yang memproses dokumentasi harus menghapus indentasi jika diinginkan. Ini dilakukan dengan menggunakan konvensi berikut. Baris tidak kosong pertama setelah baris pertama string menentukan jumlah lekukan untuk seluruh string dokumentasi. (Kita tidak dapat menggunakan baris pertama karena biasanya bersebelahan dengan tanda kutip pembuka string sehingga indentasinya tidak terlihat dalam literal string.) Spasi "setara" dengan indentasi ini kemudian dihapus dari awal semua baris string . Garis yang indentasinya lebih kecil tidak boleh muncul, tetapi jika muncul, semua spasi putih di depannya harus dihilangkan. Kesetaraan spasi harus diuji setelah penambahan tab (biasanya menjadi 8 spasi).

**Anotasi Fungsi**

Anotasi fungsi adalah informasi metadata yang sepenuhnya opsional tentang jenis yang digunakan oleh fungsi yang ditentukan pengguna. 

Anotasi disimpan dalam__annotations__ atribut fungsi sebagai kamus dan tidak berpengaruh pada bagian lain dari fungsi tersebut. Anotasi parameter ditentukan oleh tanda titik dua setelah nama parameter, diikuti dengan ekspresi yang mengevaluasi nilai anotasi. Anotasi pengembalian ditentukan oleh literal->, diikuti oleh ekspresi, antara daftar parameter dan titik dua yang menunjukkan akhir pernyataandef.
