# toko_pasar_mobile

# Tugas 7
## Jelaskan apa yang dimaksud dengan stateless widget dan stateful widget, dan jelaskan perbedaan dari keduanya.
  **Stateless Widget:**
  
Widget yang tidak memiliki state atau keadaan yang berubah. Stateless widget hanya memiliki data yang bersifat statis dan tidak berubah setelah widget pertama kali dirender. Karena tidak memliki state, widget     ini tidak dapat merespons perubaha yang terjadi secara langsung pada UI.

**Stateful Widget:**

Merupakan widget yang memiliki state dan dapat mengalami perubahan selama aplikasi berjalan. Widget ini mampu merespons interaksi pengguna ataupun perubahan data yang menyebabkan tampilan UI-nya berubah. Stateful widget memiliki dua bagian utama yaitu widget itu sendiri dan objek state yang menampung data dan logika.

**Perbedaan:**

- Stateless widget bersifat statis sehingga tidak memiliki state internal yang berubah-ubah.
- Stateful widget bersifat dinamis dan dapat mengubah tampilannya sesuai dengan perubahan state yang terjadi.

  
## Sebutkan widget apa saja yang kamu gunakan pada proyek ini dan jelaskan fungsinya.
**1. MaterialApp**
   
Berfungsi sebagai root aplikasi, untuk mengatur judul aplikasi dan tema warna.

**2. Scaffold**

Struktur dasar halaman yang menyediakan AppBar dan body.

**3. AppBar**

Menampilkan judul aplikasi "Toko Pasar" di bagian atas.

**4. Padding**

Memberikan jarak di sekitar widget Column pada body agar konten tidak menempel pada bagian pinggir layar.

**5. Column**

Menyusun elemen UI secara vertikal, seperti Row, Text, dan GridView.

**6. Row**

Menyusun InfoCard secara horizontal di bagian atas halaman.

**7. InfoCard (Custom StatelessWidget)**

Menampilkan informasi dalam bentuk kartu, seperti NPM, Name, dan Class. Di dalamnya menggunakan:

- Card: Untuk membentuk kotak dengan bayangan di belakangnya.
- Text: Menampilkan teks judul dan konten pada kartu

**8. SizedBox**

Memberikan jarak vertikal antara Row (InfoCard) dan teks ‘Welcome to Toko Pasar!’.

**9. Center**

Menempatkan Column (yang berisi teks ’Welcome to Toko Pasar!’ dan grid item) di tengah halaman.

**10. Text**

Menampilkan teks ’Welcome to Toko Pasar!’ dengan gaya tertentu.

**11. GridView.Count**

Membuat grid dengan 3 kolom untuk menampilkan ItemCard.

**12. ItemCard (Custom StatelessWidget)**

Menampilkan setiap item toko (seperti "Lihat Daftar Produk", "Tambah Produk", dan "Logout") dalam bentuk kartu dengan ikon dan teks. Di dalamnya menggunakan:

- Material: Menyediakan latar belakang dengan warna dari item.
- InkWell: Memberikan efek ripple dan aksi ketika kartu ditekan.
- Container: Untuk padding dan layout internal.
- Icon: Menampilkan ikon pada setiap item kartu.
- Text: Menampilkan nama item di bawah ikon.
  
**13. ScaffoldMessenger dan SnackBar**

Menampilkan pesan sementara di bagian bawah layar saat kartu ditekan.


## Apa fungsi dari setState()? Jelaskan variabel apa saja yang dapat terdampak dengan fungsi tersebut.

setState() merupakan metode dalam StatefulWidget yang digunakan untuk memberitahukan framework bahwa ada perubahan state yang perlu di-render ulang di UI. Setiap kali setState() dipanggil, Flutter akan menjalankan ulang build method dari widget tersebut untuk menerapkan perubahan yang terjadi.

Variabel yang dapat terdampak dengan setState() adalah variabel-variabel state yang didefinisikan dalam objek state dari widget tersebut, biasanya berupa data yang memengaruhi tampilan UI.


## Jelaskan perbedaan antara const dengan final.
**const:** 

Digunakan untuk mendefinisikan nilai yang bersifat konstan dan sudah ditentukan saat kompilasi. Objek yang didefinisikan dengan const bersifat immutable (tidak dapat diubah) dan harus diketahui nilainya pada saat kompilasi. const biasanya digunakan pada widget atau variabel yang nilai dan propertinya tidak berubah selama aplikasi berjalan.

**final:** 

Digunakan untuk variabel yang nilainya akan diinisialisasi satu kali saja dan bersifat tetap setelah inisialisasi, tetapi nilai ini bisa ditentukan saat runtime (tidak perlu diketahui pada saat kompilasi).
 
 
## Jelaskan bagaimana cara kamu mengimplementasikan checklist-checklist di atas.

1. Membuat repository baru dengan nama toko-pasar-mobile.
2. Membuat direktori baru dengan nama toko_pasar_mobile dan melakukan generate proyek flutter melalui command prompt dengan path direktori tersebut.
3. Melakukan git init pada root folder dan add-commit-push pertama kalinya ke repositori yang telah dibuat diawal.
4. Membuat file baru yaitu menu.dart di direktori lib, lalu memindahkan kode class MyHomePage dan _MyHomePageState dari main.dart ke file baru tersebut.
5. Menambahkan import ‘package:toko_pasar_mobile/menu.dart’; agar MyHomePage tetap dikenali.
6. Mengubah warna tema aplikasi pada main.dart dengan colorScheme: ColorScheme.fromSwatch(primarySwatch: Colors.brown)
7. Menghapus const pada MyHomePage(title: 'Flutter Demo Home Page') sehingga menjadi MyHomePage(). 
8. Mengubah MyHomePage dari StatefulWidget ke StatelessWidget, dan menghapus state management yang tidak perlu.
9. Mendeklarasikan variabel npm, name, dan className dalam MyHomePage.
10. Membuat class ItemHomePage yang berisi atribut-atribut card yaitu name, icon, dan color.
11. Membuat list of ItemHomePage yang berisi tombol-tombol untuk ditambahkan pada class MyHomePage dan sesuaikan name, icon, serta color untuk setiap tombolnya.
12. Mengintegrasikan InfoCard dan ItemCard ke dalam Widget build() dalam MyHomePage agar tombol-tombolnya dapat ditampilkan.
13. Pada class ItemCard, onTap menggunakan item.name untuk menampilkan nama tombol yang ditekan di Snackbar. 
14. Melakukan add, commit, dan push ke repository.


