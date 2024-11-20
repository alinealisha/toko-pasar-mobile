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


# Tugas 8
## Apa kegunaan const di Flutter? Jelaskan apa keuntungan ketika menggunakan const pada kode Flutter. Kapan sebaiknya kita menggunakan const, dan kapan sebaiknya tidak digunakan?

Const digunakan untuk mendefinisikan nilai konstan dan immutable yaitu tidak dapat diubah setelah didefinisikan. Keuntungan dari menggunakan const pada kode Flutter adalah sebagai berikut:

- Penghematan memori:
  Objek yang didefinisikan sebagai const hanya didefinisikan sekali dalam memori dan tidak dibuat ulang, sehingga membantu mengurangi penggunaan memori.

- Optimasi Performansi:
  Flutter melakukan optimasi pada widget yang bersifat immutable atau konstan. Karena, ketika UI di rebuild, widget const tidak perlu dibuat ulang lagi, mereka selalu
  memiliki nilai yang sama.

- Code Clarity:
  Const membantu mengidentifikasi bagian-bagian dari kode yang tidak akan berubah sehingga cukup membantu untuk memudahkan pemahaman kode.

Penggunaan `const` baik digunakan untuk widget atau nilai yang diyakini tetap konstan selama aplikasi berjalan, sehingga Flutter dapat mengoptimalkan performa. Selain itu, `const` berguna untuk mendefinisikan parameter default yang tidak akan berubah. Pada elemen layout statis seperti padding, margin, atau teks yang tidak berubah, `const` juga menjadi pilihan yang baik untuk menjaga efisiensi. 

Namun, penggunaan `const` sebaiknya tidak digunakan jika nilai atau widget tersebut bersifat dinamis dan dapat berubah saat aplikasi berjalan, karena hal ini dapat memicu error. Begitu juga, `const` sebaiknya tidak diterapkan pada nilai yang bergantung pada data atau operasi yang dinamis, seperti hasil dari API atau perubahan state widget.

## Jelaskan dan bandingkan penggunaan Column dan Row pada Flutter. Berikan contoh implementasi dari masing-masing layout widget ini!

**Column** digunakan untuk menampilkan widget dalam satu kolom, dari atas ke bawah. Beberapa properti utama pada Column adalah mainAxisAlignment, yang mengatur posisi widget sepanjang sumbu utama (vertikal), dan crossAxisAlignment, yang mengatur posisi widget sepanjang sumbu sekunder (horizontal).

Contoh implementasi widget Column:

```dart
child: Column(
  crossAxisAlignment: CrossAxisAlignment.center,
  children: [
    // Row widget untuk menampilkan InfoCard secara horizontal
    Row(
      mainAxisAlignment: MainAxisAlignment.spaceEvenly,
      children: [
        InfoCard(title: 'NPM', content: npm),
        InfoCard(title: 'Name', content: name),
        InfoCard(title: 'Class', content: className),
      ],
    ),
    const SizedBox(height: 16.0),
    Center(
      child: Column(
        children: [
          // Teks sambutan
          const Padding(
            padding: EdgeInsets.only(top: 16.0),
            child: Text(
              'Welcome to Toko Pasar!',
              style: TextStyle(
                fontWeight: FontWeight.bold,
                fontSize: 18.0,
              ),
            ),
          ),
          // Grid item
          GridView.count(
            primary: true,
            padding: const EdgeInsets.all(20),
            crossAxisSpacing: 10,
            mainAxisSpacing: 10,
            crossAxisCount: 3,
            shrinkWrap: true,
            children: items.map((ItemHomepage item) {
              return ItemCard(item: item);
            }).toList(),
          ),
        ],
      ),
    ),
  ],
),
```


**Row** digunakan untuk menyusun widget dalam satu baris, dari kiri ke kanan, menjadikannya ideal untuk layout yang memerlukan penyusunan elemen secara horizontal, seperti ikon dan teks yang diletakkan bersebelahan atau beberapa tombol yang berbaris. Row juga memiliki mainAxisAlignment dan crossAxisAlignment yang berfungsi mengatur penempatan widget di sepanjang sumbu utama (horizontal) dan sumbu sekunder (vertikal).

Contoh implementasi widget Row:
```dart
Row(
  mainAxisAlignment: MainAxisAlignment.spaceEvenly,
  children: [
    InfoCard(title: 'NPM', content: npm),
    InfoCard(title: 'Name', content: name),
    InfoCard(title: 'Class', content: className),
  ],
),
```

## Sebutkan apa saja elemen input yang kamu gunakan pada halaman form yang kamu buat pada tugas kali ini. Apakah terdapat elemen input Flutter lain yang tidak kamu gunakan pada tugas ini? Jelaskan!

Pada halaman form Toko Pasar digunakan elemen input **TextFormField** untuk input teks ataupun angka seperti Product Name, Amount, Description, Price, dan Rating.

Elemen input lain yang tidak digunakan:
- Checkbox: untuk memilih satu atau lebih opsi dalam bentuk kotak centang.
- Switch: elemen input yang sering digunakan untuk pilihan ON/OFF.
- RadioButton: untuk memilih satu opsi dari beberapa pilihan.
- DatePicker dan TimePicker: untuk memilih tanggal dan waktu tertentu.
- Slider: untuk memilih nilai dalam rentang tertentu.

## Bagaimana cara kamu mengatur tema (theme) dalam aplikasi Flutter agar aplikasi yang dibuat konsisten? Apakah kamu mengimplementasikan tema pada aplikasi yang kamu buat?

Ya, aplikasi Toko Pasar sudah mengimplementasikan tema.

Tema diatur dengan menentukan ColorScheme.fromSwatch, yang menciptakan skema warna berdasarkan primarySwatch yang disetting menjadi warna Colors.brown. Nantinya, tema ini akan diterapkan secara otomatis ke seluruh aplikasi, sehingga setiap widget yang mendukung tema, seperti AppBar, FloatingActionButton, atau Button, akan menggunakan warna dan gaya yang sama tanpa harus diatur ulang secara manual di setiap halaman.


## Bagaimana cara kamu menangani navigasi dalam aplikasi dengan banyak halaman pada Flutter?

**Navigasi menggunakan Navigator.push() dan Navigator.pop().**
   
Metode **Navigator.push()** digunakan untuk menambahkan halaman baru ke stack navigasi dan berpindah ke halaman tersebut. Halaman baru akan "terlihat" di atas halaman sebelumnya.

Sementara itu, ketika halaman baru ditampilkan, pengguna bisa kembali ke halaman sebelumnya menggunakan tombol "back" atau **Navigator.pop()**.

   Contoh implementasi Navigator.push():
   ```dart
   Navigator.push(
                  context,
                  MaterialPageRoute(
                    builder: (context) => MyHomePage(),
                  ));
   ```

   Contoh implementasi Navigator.pop():
   ```dart
   Navigator.pop(context);
   ```

# Tugas 9
## Jelaskan mengapa kita perlu membuat model untuk melakukan pengambilan ataupun pengiriman data JSON? Apakah akan terjadi error jika kita tidak membuat model terlebih dahulu?

Membuat model untuk data JSON dapat membantu dalam mempermudah manipulasi, validasi, dan pengelolaan data yang diterima atau dikirimkan. Model juga memastikan data sesuai dengan struktur yang diharapkan sehingga mengurangi risiko error akibat format data yang tidak sesuai. Jika model tidak dibuat, memang tidak secara langsung akan terjadi error, tetapi pengelolaan data menjadi lebih rawan error dan sulit untuk di-debug karena data akan dikelola secara manual tanpa validasi atau struktur yang jelas.

## Jelaskan fungsi dari library http yang sudah kamu implementasikan pada tugas ini

 Library http digunakan untuk melakukan komunikasi dengan server melalui protokol HTTP. Fungsi utamanya meliputi pengambilan data (GET), pengiriman data (POST), serta pengelolaan respons dari server. Library ini mempermudah integrasi antara Flutter dan backend seperti Django dalam pertukaran data.

## Jelaskan fungsi dari CookieRequest dan jelaskan mengapa instance CookieRequest perlu untuk dibagikan ke semua komponen di aplikasi Flutter.

CookieRequest digunakan untuk mengelola sesi autentikasi antara klien dan server dengan cara menyimpan dan mengelola cookie. Instance CookieRequest perlu dibagikan ke semua komponen Flutter untuk memastikan sesi tetap konsisten di seluruh aplikasi, yang memungkinkan komponen lain mengakses data sesi, seperti token autentikasi, tanpa perlu login ulang.

## Jelaskan mekanisme pengiriman data mulai dari input hingga dapat ditampilkan pada Flutter.

1. Input

   Data dimasukkan melalui form atau widget input pada Flutter.

2. Pengiriman

   Data tersebut dikirimkan menggunakan metode POST melalui library http   atau CookieRequest ke endpoint Django.

3. Proses Server

   Django memproses data, menyimpannya dalam database, lalu memberikan  respons JSON.

4. Penerimaan Data

   Flutter menerima respons JSON, memetakan data tersebut ke dalam model, dan menampilkan data pada UI menggunakan widget seperti ListView atau GridView.
   
## Jelaskan mekanisme autentikasi dari login, register, hingga logout. Mulai dari input data akun pada Flutter ke Django hingga selesainya proses autentikasi oleh Django dan tampilnya menu pada Flutter.

1. Login
   
   - Data akun (email/username dan password) dimasukkan melalui Flutter.
   - Flutter mengirim data ke endpoint Django menggunakan metode POST.
   - Django memverifikasi kredensial terhadap database dan, jika valid, mengembalikan token atau cookie sesi.
   - Flutter menyimpan token/cookie dan menampilkan menu atau halaman utama.

3. Register
   
   - Data pendaftaran dimasukkan di Flutter dan dikirimkan ke endpoint Django.
   - Django menyimpan data pengguna baru ke database, lalu mengembalikan respons sukses.

4. Logout
   
   - Flutter mengirim permintaan logout ke endpoint Django.
   - Django menghapus sesi atau token yang terkait, lalu mengembalikan respons sukses.
   - Flutter menghapus token/cookie lokal dan mengarahkan pengguna kembali ke halaman login


## Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step! (bukan hanya sekadar mengikuti tutorial).

1. Buat aplikasi Django dengan nama `authentication` dan tambahkan ke bagian `INSTALLED_APPS` yang ada di settings.py proyek utama Toko Pasar.
2. Install Library `django-cors-headers`, lalu tambahkan juga ke bagian `INSTALLED_APPS` dan middleware di `MIDDLEWARE` dalam file settings.py.
3. Tambahkan pengaturan CORS di `settings.py` untuk mendukung session lintas platform.
4. Tambahkan `10.0.2.2` ke bagian `ALLOWED_HOSTS` untuk mengakses emulator Android.
5. Tambahkan fungsi login di dalam `views.py` pada aplikasi `authentication`.
6. Tambahkan fungsi register di dalam `views.py` pada aplikasi `authentication` untuk pendaftaran pengguna baru.
7. Buat file `urls.py` di dalam folder `authentication` dan tambahkan routing untuk `/login` dan `/register`.
8. Hubungkan `/auth` di `urls.py` proyek utama untuk menyambungkan endpoint.
9.  Instal library `provider` dan `pbp_django_auth` untuk menangani autentikasi.
10.  Tambahkan `CookieRequest` sebagai provider di root widget (`main.dart`).  
11. Buat halaman login dengan form untuk username dan password, kirim data ke endpoint login menggunakan `CookieRequest`.
12. Buat halaman register dengan form untuk username, password, dan konfirmasi password, kirim data ke endpoint register menggunakan `CookieRequest`.
13. Salin data JSON dari endpoint Django ke situs Quicktype dan atur bahasa ke Dart.
14. Buat folder `models/` di direktori `lib/` Flutter dan tambahkan file `product_entry.dart`.  
15. Tempelkan kode model Dart dari Quicktype ke dalam file tersebut.
16. Install package `http` dengan perintah `flutter pub add http`.
17. Tambahkan izin akses internet di file `AndroidManifest.xml`.
18. Buat halaman baru `list_productentry.dart` untuk menampilkan daftar produk.
19. Gunakan `FutureBuilder` untuk mengambil data dari endpoint Django menggunakan metode GET.
20. Tambahkan navigasi ke halaman daftar produk pada menu dengan `ListTile`.
21. Hubungkan tombol "Lihat Produk" ke halaman daftar produk di aplikasi Flutter.
22. Tambahkan fungsi `create_product_flutter` di `main/views.py` untuk menerima data POST dari Flutter dan menyimpan data di database.
23. Tambahkan routing untuk endpoint baru `create-flutter/` di `main/urls.py`.
24. Integrasikan `CookieRequest` ke file `productentry_form.dart`.
25. Modifikasi tombol submit untuk mengirim data JSON ke endpoint Django menggunakan metode POST.
26. Jalankan ulang aplikasi Flutter dan periksa apakah data berhasil ditambahkan ke database Django.
27. Tambahkan fungsi logout di `authentication/views.py` untuk menghapus session pengguna.
28. Tambahkan routing untuk endpoint logout di `authentication/urls.py`.
29. Lakukan add-commit-push ke Github. 













