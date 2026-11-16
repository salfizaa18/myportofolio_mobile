# myportofolio_mobile

### Tugas 7

## 1. Jelaskan apa yang dimaksud dengan widget tree pada Flutter dan bagaimana hubungan induk-anak (parent-child) bekerja antar-widget!

Widget tree merupakan struktur yang menunjukkan susunan widget dalam aplikasi Flutter. Setiap widget bisa memiliki widget lain di dalamnya, sehingga terbentuk hubungan parent dan child. Widget parent berfungsi mengatur widget child, seperti posisi dan ukurannya. Pada proyek ini, susunan widget dimulai dari `MaterialApp`, kemudian `MyHomePage`, `Scaffold`, `Padding`, dan `Column`. Di dalamnya terdapat `Row` yang menampilkan tiga `InfoCard` serta `GridView` yang berisi beberapa `ItemCard`. Jika terjadi perubahan, Flutter akan membangun ulang bagian tampilan yang perlu diperbarui.

## 2. Sebutkan semua widget yang kamu gunakan dalam proyek ini dan jelaskan fungsinya masing-masing!

Dalam proyek ini, saya menggunakan beberapa widget bawaan Flutter, seperti `MaterialApp` untuk mengatur aplikasi, `Scaffold` sebagai kerangka halaman, dan `AppBar` untuk menampilkan judul di bagian atas. Ada juga `Padding`, `Column`, dan `Row` untuk mengatur jarak serta susunan widget. Untuk menampilkan informasi, saya menggunakan `Card`, `Container`, dan `Text`, sedangkan `Icon` digunakan untuk menampilkan ikon. Selain itu, `GridView.count` digunakan untuk menyusun tombol dalam tiga kolom. Pada bagian tombol, saya menggunakan `Material` dan `InkWell` agar kartu memiliki warna, sudut membulat, dan bisa merespons sentuhan. Ketika tombol ditekan, `SnackBar` akan muncul sebagai notifikasi. Saya juga membuat beberapa widget sendiri, yaitu `MyApp`, `MyHomePage`, `InfoCard`, dan `ItemCard`.

## 3. Apa fungsi dari widget MaterialApp? Jelaskan mengapa widget ini umumnya digunakan sebagai root widget pada aplikasi Flutter!

`MaterialApp` merupakan widget utama yang menjadi dasar dari sebuah aplikasi Flutter dengan tampilan Material Design. Widget ini digunakan untuk mengatur tema, halaman awal, judul aplikasi, serta navigasi antarhalaman. `MaterialApp` diletakkan di bagian paling atas karena widget lain di dalam aplikasi, seperti `Scaffold` dan `Theme.of(context)`, membutuhkan pengaturan yang disediakan olehnya. Dengan begitu, pengaturan dasar aplikasi cukup dilakukan di satu tempat.

## 4. Jelaskan perbedaan antara StatelessWidget dan StatefulWidget! Kapan kita sebaiknya memilih StatelessWidget dan kapan harus menggunakan StatefulWidget?

`StatelessWidget` digunakan untuk widget yang tidak memiliki data yang berubah selama aplikasi berjalan. Tampilan widget ini bergantung pada data yang diberikan dan akan dibangun ulang ketika diperlukan oleh parent-nya. Sementara itu, `StatefulWidget` digunakan ketika ada data atau kondisi yang bisa berubah dan memengaruhi tampilan. Contohnya adalah penghitung angka, form yang diisi pengguna, atau animasi. Pada proyek ini, `StatelessWidget` sudah cukup digunakan untuk `MyHomePage`, `InfoCard`, dan `ItemCard` karena tampilannya belum membutuhkan perubahan state secara langsung.

## 5. Apa itu BuildContext dan mengapa penting di Flutter? Bagaimana penggunaannya di dalam metode build?

`BuildContext` merupakan informasi yang menunjukkan posisi suatu widget di dalam widget tree. Dengan `context`, sebuah widget bisa mengakses informasi atau layanan dari widget lain yang berada di atasnya. Pada proyek ini, `context` digunakan dalam `Theme.of(context)` untuk mengambil warna dari tema aplikasi, `MediaQuery.of(context)` untuk mengetahui ukuran layar, dan `ScaffoldMessenger.of(context)` untuk menampilkan `SnackBar` ketika tombol ditekan.

## 6. Jelaskan konsep hot reload di Flutter dan apa perbedaannya dengan hot restart! Kapan kita tidak bisa hanya mengandalkan hot reload dan harus melakukan hot restart atau full restart?

Hot reload digunakan untuk menerapkan perubahan kode ke aplikasi tanpa harus memulai ulang aplikasi dari awal, sehingga state yang sedang berjalan tetap dipertahankan. Sementara itu, hot restart akan menjalankan ulang aplikasi dari fungsi `main()`, sehingga state kembali ke kondisi awal. Hot restart diperlukan ketika perubahan kode tidak bisa diterapkan hanya dengan hot reload, misalnya perubahan pada proses inisialisasi atau `initState`. Jika menambahkan dependensi atau plugin baru di `pubspec.yaml`, maupun mengubah kode native pada folder `android` dan `ios`, biasanya diperlukan full restart dengan menghentikan dan menjalankan aplikasi kembali.

### AI Disclosure
Pada tugas 7 ini saya menggunakan Claude untuk memabntu saya memahami dan menerapkan Flutter. Hal yang dibantu:
1. Penjelasan error yang saya temui, yaitu `dart` dan `flutter` tidak dikenali di terminal, `Repository not found` saat `git push`, serta log Gradle dan AppInspector di VS Code
2. Penulisan kode awal `main.dart` dan `menu.dart` (MyHomePage, InfoCard, ItemCard, dan ItemHomepage) mengikuti alur Tutorial 08
3. Penjelasan cara menambahkan atribut warna pada model `ItemHomepage` dan memakainya sebagai warna latar `ItemCard`

Dalam pengerjaannya saya tetap berusaha memahami dan mengerjakan secara mandiri sebelum mengimplementasikannya sesuai saran AI.