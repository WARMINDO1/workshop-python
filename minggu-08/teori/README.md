# Ringkasan Minggu Ke-8
Nama : Muhammad Naufal Ramadhan

NIM : 205410138

Kelas : IF-3

## Bab 10. Brief Tour of the Standard Library

### 10.1. Operating System Interface

Modul os menyediakan fungsi-fungsi untuk berinteraksi dengan sistem operasi:

 ```python
import os
os.getcwd()                       # Mengembalikan direktori kerja saat ini
os.chdir('/server/accesslogs')    # Mengubah direktori kerja saat ini
os.system('mkdir today')          # Menjalankan perintah mkdir di shell sistem
```
Penting untuk menggunakan gaya import os daripada from os import *. Ini mencegah os.open() menggantikan fungsi bawaan open() yang beroperasi secara berbeda.

Untuk bantuan interaktif dalam bekerja dengan modul besar seperti os, gunakan fungsi bawaan dir() dan help()

Untuk tugas-tugas pengelolaan file dan direktori sehari-hari, modul shutil menyediakan antarmuka tingkat yang lebih tinggi

### 10.2. File Wildcards

Modul glob menyediakan fungsi untuk membuat daftar file dari pencarian dengan wildcard di direktori.

### 10.3. Command Line Arguments

Skrip utilitas umum sering memproses argumen baris perintah yang disimpan dalam atribut argv modul sys sebagai sebuah daftar. Modul argparse menyediakan mekanisme yang lebih canggih untuk memproses argumen baris perintah.

### 10.4. Error Output Redirection and Program Termination

Modul sys juga memiliki atribut untuk stdin, stdout, dan stderr. stderr berguna untuk mengeluarkan peringatan dan pesan kesalahan agar terlihat bahkan ketika stdout telah dialihkan

Modul sys juga memiliki atribut untuk stdin, stdout, dan stderr. stderr berguna untuk mengeluarkan peringatan dan pesan kesalahan agar terlihat bahkan ketika stdout telah dialihkan

Cara paling langsung untuk menghentikan sebuah skrip adalah dengan menggunakan sys.exit().

### 10.5. String Pattern Matching

Modul re menyediakan alat-alat ekspresi reguler untuk pemrosesan string yang lebih canggih. Untuk pencocokan dan manipulasi yang kompleks, ekspresi reguler menawarkan solusi yang ringkas dan dioptimalkan

Ketika hanya kemampuan sederhana yang diperlukan, metode-metode string lebih disukai karena lebih mudah dibaca dan didebug

### 10.6. Mathematics

Modul math memberikan akses ke fungsi-fungsi pustaka C yang mendasari untuk perhitungan matematika titik mengambang

Modul random menyediakan alat-alat untuk melakukan pemilihan acak

Modul statistics menghitung properti statistik dasar (rerata, median, varians, dll.) dari data numerik

Proyek SciPy https://scipy.org memiliki banyak modul lain untuk komputasi numerik.

### 10.7. Internet Access

Terdapat beberapa modul untuk mengakses internet dan memproses protokol internet. Dua yang paling sederhana adalah urllib.request untuk mengambil data dari URL dan smtplib untuk mengirim email

### 10.8. Dates and Times

Modul datetime menyediakan kelas-kelas untuk memanipulasi tanggal dan waktu dengan cara yang sederhana maupun kompleks. Meskipun aritmetika tanggal dan waktu didukung, fokus implementasinya adalah pada ekstraksi anggota yang efisien untuk pemformatan output dan manipulasi. Modul ini juga mendukung objek yang memiliki kesadaran zona waktu.

### 10.9. Data Compression

Format-format umum untuk mengarsipkan dan mengompresi data didukung secara langsung oleh beberapa modul, antara lain: zlib, gzip, bz2, lzma, zipfile, dan tarfile.

### 10.10. Performance Measurement

Beberapa pengguna Python tertarik untuk mengetahui performa relatif dari pendekatan yang berbeda terhadap masalah yang sama. Python menyediakan alat pengukuran yang dapat menjawab pertanyaan tersebut dengan cepat.

Berbeda dengan tingkat granularitas yang baik dari timeit, modul profile dan pstats menyediakan alat-alat untuk mengidentifikasi bagian-bagian yang kritis dalam waktu pada blok kode yang lebih besar.

### 10.11. Quality Control

Salah satu pendekatan dalam pengembangan perangkat lunak berkualitas tinggi adalah dengan menulis pengujian (test) untuk setiap fungsi saat pengembangan dan menjalankan pengujian tersebut secara sering selama proses pengembangan.

Modul doctest menyediakan alat untuk memindai modul dan memvalidasi pengujian yang tertanam dalam docstring program. Konstruksi pengujian semudah menyalin dan memasukkan pemanggilan fungsi beserta hasilnya ke dalam docstring.

doctest.testmod()   # secara otomatis memvalidasi pengujian yang tertanam

Modul unittest memungkinkan pengujian yang lebih komprehensif tetapi tidak semudah modul doctest.

### 10.12. Batteries Included

Python memiliki "filosofi baterai terlampir" yang terlihat melalui paket-paket besar dengan kemampuan canggih, antara lain:

- xmlrpc.client dan xmlrpc.server: Implementasi panggilan prosedur jarak jauh tanpa perlu pengetahuan XML langsung.
- email: Perpustakaan untuk mengelola pesan email, termasuk MIME dan dokumen pesan berbasis RFC 2822.
- json: Dukungan kuat untuk memparsing format pertukaran data JSON.
- csv: Modul untuk membaca dan menulis file dalam format Comma-Separated Value (CSV).
- xml.etree.ElementTree, xml.dom, dan xml.sax: Modul-modul untuk memproses XML.
- sqlite3: Modul wrapper untuk database SQLite.
- Internationalisasi didukung oleh modul-modul seperti gettext, locale, dan codecs.


## Bab 11. Brief Tour of the Standard Library — Part II

Tur kedua ini mencakup modul-modul yang lebih canggih yang mendukung kebutuhan pemrograman profesional. Modul-modul ini jarang digunakan dalam skrip-skrip kecil.

### 11.1. Output Formatting

Modul reprlib: reprlib.repr(obj) memberikan tampilan singkat objek dengan kontainer besar atau bersarang.

Modul pprint: pprint.pprint(obj, width=30) mencetak objek dengan format yang lebih terbaca, termasuk objek yang kompleks, dengan pemisah baris dan indentasi.

Modul textwrap: textwrap.fill(text, width=40) memformat teks menjadi paragraf dengan lebar yang ditentukan.

Modul locale: locale.format() digunakan untuk memformat angka dengan pemisah grup berdasarkan pengaturan lokal yang diberikan.

### 11.2. Templating

Format tersebut menggunakan nama placeholder yang terbentuk oleh $ dengan identifikasi Python yang valid (karakter alfanumerik dan garis bawah). Mengelilingi placeholder dengan kurung kurawal memungkinkan diikuti dengan huruf alfanumerik lebih lanjut tanpa spasi di antaranya.

Metode substitute() akan menghasilkan KeyError jika sebuah placeholder tidak tersedia dalam kamus atau argumen kata kunci. Dalam aplikasi seperti mail-merge, data yang diberikan pengguna mungkin tidak lengkap, dan metode safe_substitute() dapat lebih sesuai metode ini akan mempertahankan placeholder jika data tidak ada.

### 11.3. Working with Binary Data Record Layouts

Modul struct menyediakan fungsi pack() dan unpack() untuk bekerja dengan format rekaman biner variabel. Contoh berikut menunjukkan bagaimana melalui informasi header dalam file ZIP tanpa menggunakan modul zipfile. Kode pack "H" dan "I" mewakili angka tak bertanda dua dan empat byte secara berturut-turut. Tanda "<" menunjukkan bahwa mereka berukuran standar dan berurutan byte little-endian.

### 11.4. Multi-threading

Threading adalah teknik untuk memisahkan tugas-tugas yang tidak saling bergantung secara sekuensial. Thread dapat digunakan untuk meningkatkan responsivitas aplikasi yang menerima input pengguna sementara tugas lain berjalan di latar belakang. Penggunaan yang terkait adalah menjalankan I/O secara paralel dengan komputasi dalam thread lain.

Koordinasi tugas dalam aplikasi multi-threaded dapat dilakukan dengan menggunakan modul threading untuk mengatur sinkronisasi antar thread. Dalam hal ini, modul queue digunakan sebagai alat komunikasi antar thread yang mempermudah desain, meningkatkan keterbacaan, dan keandalan aplikasi.

### 11.5. Logging

Modul logging menyediakan sistem logging yang lengkap dan fleksibel. Secara default, pesan informasi dan debugging ditampilkan dan keluarannya dikirim ke standar error. Opsi keluaran lainnya termasuk pengiriman pesan melalui email, datagram, socket, atau ke server HTTP. Filter baru dapat dipakai untuk memilih rute yang berbeda berdasarkan prioritas pesan: DEBUG, INFO, WARNING, ERROR, dan CRITICAL.

Sistem logging dapat dikonfigurasi langsung dari Python atau dapat dimuat dari file konfigurasi yang dapat diubah oleh pengguna untuk logging yang disesuaikan tanpa mengubah aplikasi.

### 11.6. Weak References

Python menggunakan manajemen memori otomatis dengan penghitungan referensi dan pengumpulan sampah. Modul weakref menyediakan alat untuk melacak objek tanpa membuat referensi permanen. Ini berguna untuk aplikasi seperti caching objek yang mahal.

### 11.7. Tools for Working with Lists

Modul array menyediakan objek array() untuk menyimpan data homogen secara lebih kompak. Modul collections menyediakan objek deque() untuk operasi cepat append dan pop dari sisi kiri.

### 11.8. Decimal Floating Point Arithmetic

Modul decimal menyediakan tipe data Decimal untuk aritmetika titik desimal. Dibandingkan dengan implementasi float bawaan yang menggunakan titik mengambang biner, kelas ini sangat berguna untuk : 

- aplikasi keuangan dan penggunaan lain yang memerlukan representasi desimal yang akurat,
- kontrol atas presisi,
- kontrol atas pembulatan untuk memenuhi persyaratan hukum atau regulasi,
- pelacakan tempat desimal yang signifikan, atau
- aplikasi di mana pengguna mengharapkan hasilnya sesuai dengan perhitungan yang dilakukan secara manual.
