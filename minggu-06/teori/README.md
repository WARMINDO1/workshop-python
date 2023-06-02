# Ringkasan Minggu Ke-6
Nama : Muhammad Naufal Ramadhan

NIM : 205410138

Kelas : IF-3

## Bab 8 Error and Exceotions
Hingga saat ini pesan kesalahan hanya disebutkan tanpa lebih detail, tetapi jika Anda sudah mencoba contoh-contohnya, mungkin Anda sudah melihat beberapa pesan kesalahan. Terdapat (setidaknya) dua jenis kesalahan yang dapat dibedakan: kesalahan sintaksis dan pengecualian.

### 8.1. Syntax Errors

Parser mengulangi baris yang menyebabkan kesalahan dan menampilkan sebuah 'panah' kecil yang menunjuk ke titik awal pada baris di mana kesalahan terdeteksi. Kesalahan disebabkan oleh (atau setidaknya terdeteksi pada) token sebelum panah: dalam contoh ini, kesalahan terdeteksi pada fungsi print(), karena titik dua (':') hilang sebelumnya. Nama file dan nomor baris dicetak sehingga Anda tahu di mana mencari jika masukan berasal dari skrip.

### 8.2. Exceptions

Meskipun pernyataan atau ekspresi secara sintaksis benar, dapat menyebabkan kesalahan saat mencoba menjalankannya. Kesalahan yang terdeteksi saat eksekusi disebut pengecualian (exceptions) dan tidak selalu fatal secara mutlak
Pengecualian memiliki berbagai jenis, dan jenisnya dicetak sebagai bagian dari pesan: jenis-jenis yang ada dalam contoh ini adalah ZeroDivisionError, NameError, dan TypeError. String yang dicetak sebagai jenis pengecualian adalah nama pengecualian bawaan yang terjadi. Hal ini berlaku untuk semua pengecualian bawaan, tetapi tidak selalu berlaku untuk pengecualian yang ditentukan pengguna (meskipun itu adalah konvensi yang berguna). Nama-nama pengecualian standar adalah pengenal bawaan (bukan kata kunci yang dicadangkan).

Bagian sebelumnya dari pesan kesalahan menunjukkan konteks di mana pengecualian terjadi, dalam bentuk traceback tumpukan. Pada umumnya, itu berisi daftar traceback tumpukan yang mencantumkan baris kode sumber; namun, traceback tidak akan menampilkan baris yang dibaca dari input standar.

Built-in Exceptions (Pengecualian Bawaan) mencantumkan pengecualian bawaan dan maknanya.

### 8.3. Handling Exceptions

Dalam pemrograman, kita dapat menulis program yang menangani pengecualian tertentu.

Contoh berikut meminta pengguna untuk memasukkan input hingga angka bulat yang valid dimasukkan, tetapi memungkinkan pengguna untuk menghentikan program (menggunakan Control-C atau apa pun yang didukung sistem operasi). Pengecualian KeyboardInterrupt akan dipicu ketika pengguna menghentikan program.

Pernyataan try bekerja sebagai berikut:
   - Pertama, klausa try (pernyataan antara kata kunci try dan except) dieksekusi.
   - Jika tidak ada pengecualian terjadi, klausa except dilewati dan eksekusi pernyataan try selesai.
   - Jika terjadi pengecualian selama eksekusi klausa try, sisa klausa tersebut dilewati. Kemudian, jika jenis pengecualian tersebut cocok dengan pengecualian yang disebutkan setelah kata kunci except, klausa except dieksekusi, dan eksekusi dilanjutkan setelah blok try/except.
   - Jika terjadi pengecualian yang tidak cocok dengan pengecualian yang disebutkan dalam klausa except, pengecualian tersebut diteruskan ke pernyataan try luar; jika tidak ada penangan ditemukan, pengecualian tersebut tidak ditangani dan eksekusi dihentikan dengan pesan kesalahan.

Pernyataan try dapat memiliki lebih dari satu klausa except untuk menentukan penangan untuk pengecualian yang berbeda. Hanya satu penangan yang akan dieksekusi. Penangan hanya menangani pengecualian yang terjadi dalam klausa try yang sesuai, bukan dalam penangan lain dari pernyataan try yang sama. Klausa except dapat menamai beberapa pengecualian dalam bentuk tuple yang dikelilingi tanda kurung. Kelas dalam klausa except kompatibel dengan pengecualian jika kelas tersebut sama atau merupakan kelas dasarnya (namun tidak sebaliknya - klausa except yang mencantumkan kelas turunan tidak kompatibel dengan kelas dasar). Sebagai contoh, kode berikut akan mencetak B, C, D dalam urutan tersebut. Perlu dicatat bahwa jika klausa except dibalik (dengan except B pertama), akan mencetak B, B, B - klausa except yang pertama cocok akan dipicu. Keluaran __str__() pengecualian dicetak sebagai bagian terakhir ("detail") dari pesan untuk pengecualian yang tidak ditangani.

BaseException adalah kelas dasar umum dari semua pengecualian. Salah satu kelas turunannya, Exception, adalah kelas dasar dari semua pengecualian yang tidak fatal. Pengecualian yang bukan merupakan subkelas Exception biasanya tidak ditangani, karena digunakan untuk menunjukkan bahwa program harus dihentikan. Ini termasuk SystemExit yang dipicu oleh sys.exit() dan KeyboardInterrupt yang dipicu ketika pengguna ingin menghentikan program.

Exception dapat digunakan sebagai wildcard yang menangkap hampir semua pengecualian. Namun, praktik yang baik untuk menjadi sejelas mungkin dengan jenis pengecualian yang ingin kita tangani, dan membiarkan pengecualian yang tidak terduga menyebar.

Pola paling umum dalam menangani Exception adalah mencetak atau mencatat pengecualian dan kemudian memunculkannya kembali (memungkinkan pemanggil menangani pengecualian juga). Pernyataan try ... except memiliki klausa else opsional, yang jika ada, harus mengikuti semua klausa except. Ini berguna untuk kode yang harus dieksekusi jika klausa try tidak menimbulkan pengecualian. Penggunaan klausa else lebih baik daripada menambahkan kode tambahan ke dalam klausa try karena menghindari secara tidak sengaja menangkap pengecualian yang tidak dipicu oleh kode yang dilindungi oleh pernyataan try ... except.

Handler pengecualian tidak hanya menangani pengecualian yang terjadi langsung dalam klausa try, tetapi juga yang terjadi dalam fungsi yang dipanggil (bahkan secara tidak langsung) dalam klausa try tersebut.

### 8.4. Raising Exceptions

Pernyataan raise memungkinkan programmer untuk memaksa terjadinya pengecualian yang ditentukan.

Argumen tunggal pada raise menunjukkan pengecualian yang akan dipicu. Ini harus berupa instance pengecualian atau kelas pengecualian (kelas yang merupakan turunan dari BaseException, seperti Exception atau salah satu kelas turunannya). Jika kelas pengecualian dilewatkan, kelas tersebut akan secara implisit diinstansiasi dengan memanggil konstruktor tanpa argumen.

### 8.5. Exception Chaining

Jika sebuah pengecualian yang tidak ditangani terjadi di dalam bagian except, pengecualian yang sedang ditangani akan terlampir pada pengecualian tersebut dan disertakan dalam pesan kesalahan.
Untuk menunjukkan bahwa sebuah pengecualian adalah konsekuensi langsung dari pengecualian lainnya, pernyataan raise memungkinkan penggunaan klausa from yang bersifat opsional.

Hal ini dapat berguna saat Anda mengubah pengecualian.
Ini juga memungkinkan untuk menonaktifkan pencantuman pengecualian secara otomatis menggunakan idiom from None:
Untuk informasi lebih lanjut tentang mekanisme pencantian pengecualian, lihat Built-in Exceptions.

### 8.6. User-defined Exceptions

Program dapat memberi nama pengecualian mereka sendiri dengan membuat kelas pengecualian baru (lihat Kelas untuk informasi lebih lanjut tentang kelas Python). Pengecualian biasanya harus diturunkan dari kelas Exception, baik secara langsung maupun tidak langsung.

Kelas pengecualian dapat didefinisikan untuk melakukan apa pun yang bisa dilakukan oleh kelas lain, tetapi biasanya sederhana, sering hanya menawarkan sejumlah atribut yang memungkinkan informasi tentang kesalahan dapat diekstraksi oleh handler pengecualian.

Sebagian besar pengecualian didefinisikan dengan nama yang diakhiri dengan "Error", mirip dengan penamaan pengecualian standar.

Banyak modul standar mendefinisikan pengecualian mereka sendiri untuk melaporkan kesalahan yang mungkin terjadi dalam fungsi-fungsi yang mereka definisikan.

### 8.7. Defining Clean-up Actions

Pernyataan try memiliki klausa opsional lain yang ditujukan untuk mendefinisikan tindakan pembersihan yang harus dieksekusi dalam semua keadaan. Contohnya:
```python
try:
    # Kode yang mungkin menimbulkan pengecualian
except Exception:
    # Penanganan pengecualian
finally:
    # Tindakan pembersihan yang akan dieksekusi selalu
```
Jika klausa finally hadir, klausa finally akan dieksekusi sebagai tugas terakhir sebelum pernyataan try selesai. Klausa finally dijalankan baik pernyataan try menghasilkan pengecualian atau tidak. Berikut beberapa poin yang menjelaskan situasi yang lebih kompleks saat terjadi pengecualian:

- Jika terjadi pengecualian selama eksekusi klausa try, pengecualian tersebut dapat ditangani oleh klausa except. Jika pengecualian tidak ditangani oleh klausa except, pengecualian akan diangkat kembali setelah klausa finally dieksekusi.
- Pengecualian dapat terjadi selama eksekusi klausa except atau else. Sekali lagi, pengecualian akan diangkat kembali setelah klausa finally dieksekusi.
- Jika klausa finally menjalankan pernyataan break, continue, atau return, pengecualian tidak akan diangkat kembali.
- Jika pernyataan try mencapai pernyataan break, continue, atau return, klausa finally akan dieksekusi tepat sebelum eksekusi pernyataan break, continue, atau return.
- Jika klausa finally mencakup pernyataan return, nilai yang dikembalikan akan menjadi nilai dari pernyataan return pada klausa finally, bukan nilai dari pernyataan return pada klausa try.

Seperti yang dapat Anda lihat, klausa finally dieksekusi dalam semua keadaan. Pengecualian TypeError yang dihasilkan oleh pembagian dua string tidak ditangani oleh klausa except dan oleh karena itu diangkat kembali setelah klausa finally dieksekusi.

Dalam aplikasi dunia nyata, klausa finally berguna untuk melepaskan sumber daya eksternal (seperti file atau koneksi jaringan), terlepas dari keberhasilan penggunaan sumber daya tersebut.

### 8.8. Predefined Clean-up Actions

Beberapa objek mendefinisikan tindakan pembersihan standar yang dilakukan ketika objek tersebut tidak lagi diperlukan, terlepas dari berhasil atau gagalnya operasi yang menggunakan objek tersebut. Contoh berikut mencoba membuka sebuah file dan mencetak isinya ke layar.

Masalah dengan kode ini adalah bahwa file tetap terbuka untuk jangka waktu yang tidak dapat ditentukan setelah bagian kode ini selesai dieksekusi. Hal ini bukan masalah dalam skrip sederhana, tetapi dapat menjadi masalah dalam aplikasi yang lebih besar. Pernyataan "with" memungkinkan objek seperti file digunakan dengan cara yang memastikan mereka selalu dibersihkan dengan cepat dan dengan benar.

Setelah pernyataan dieksekusi, file "f" selalu ditutup, bahkan jika ada masalah saat memproses baris-baris tersebut. Objek yang, seperti file, menyediakan tindakan pembersihan yang telah ditentukan sebelumnya akan menunjukkan hal ini dalam dokumentasinya.

### 8.9. Raising and Handling Multiple Unrelated Exceptions

Ada situasi di mana penting untuk melaporkan beberapa exception yang terjadi. Ini sering terjadi dalam kerangka kerja konkurensi, ketika beberapa tugas mungkin gagal secara paralel, tetapi ada juga kasus penggunaan lain di mana lebih diinginkan untuk melanjutkan eksekusi dan mengumpulkan beberapa error daripada mengeluarkan exception pertama.

ExceptionGroup bawaan mengelompokkan daftar instance exception sehingga dapat diangkat bersama. Ini sendiri merupakan sebuah exception, sehingga dapat ditangkap seperti exception lainnya.

Dengan menggunakan except* daripada except, kita dapat menangani secara selektif hanya exception dalam grup yang cocok dengan jenis tertentu. Pada contoh berikut, yang menunjukkan grup exception yang bersarang, setiap klausa except* mengekstrak dari grup exception dengan jenis tertentu sementara membiarkan semua exception lainnya menyebar ke klausa lain dan pada akhirnya diangkat kembali.

Perhatikan bahwa exception yang bersarang dalam sebuah exception group harus berupa instance, bukan tipe. Hal ini karena dalam praktiknya, exception tersebut biasanya sudah pernah diangkat dan ditangkap oleh program.

### 8.10. Enriching Exceptions with Notes

Ketika sebuah exception dibuat untuk diangkat, biasanya diinisialisasi dengan informasi yang menjelaskan kesalahan yang terjadi. Ada kasus di mana berguna untuk menambahkan informasi setelah exception ditangkap. Untuk tujuan ini, exception memiliki metode add_note(note) yang menerima string dan menambahkannya ke daftar catatan exception. Rendering traceback standar mencakup semua catatan, sesuai urutan penambahan, setelah exception.

Misalnya, saat mengumpulkan exception ke dalam sebuah exception group, kita mungkin ingin menambahkan informasi konteks untuk setiap kesalahan individu. Pada contoh berikut, setiap exception dalam grup memiliki catatan yang menunjukkan kapan kesalahan ini terjadi.
