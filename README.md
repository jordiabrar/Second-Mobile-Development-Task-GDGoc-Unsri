# 📱Second Mobile Development Task

### Tujuan

Member mampu menerapkan konsep Flutter frontend secara nyata, meliputi:

- komposisi widget,
- penggunaan StatelessWidget dan StatefulWidget,
- layout dasar dan lanjutan,
- responsive design,
- navigasi antar halaman,
- state management sederhana dengan `setState`,
- validasi form,
- theme dan accessibility,
- optimasi performa dasar.

---

## Deliverables

Member melakukan fork pada repository ini dan push hal hal berikut ke repository fork anda :

1. **Source code Flutter**
2. **Readme baru** yang menjelaskan:
    - nama aplikasi,
    - fitur yang dibuat,
    - penjelasan singkat struktur halaman,
    - cara menjalankan project.
3. **Folder screenshot tampilan aplikasi**.

## Deadline

> Minggu, 26 April 2026. 23:59 WIB

---

## Deskripsi aplikasi

Buat aplikasi mobile Flutter bertema **katalog produk, event, kursus, atau artikel**. Tema boleh dipilih sendiri, tetapi struktur fiturnya wajib sama.

Aplikasi **harus berbasis data lokal** di dalam kode Dart, tanpa backend, tanpa API, dan tanpa database online. Ini supaya fokus penilaiannya ada pada frontend Flutter.

## Ketentuan umum

1. Aplikasi harus bisa dijalankan tanpa error.
2. Gunakan **MaterialApp** sebagai root aplikasi.
3. Semua tampilan harus dibuat dengan widget Flutter.
4. Data item boleh hardcoded dalam list Dart.
5. Aplikasi minimal punya **4 halaman**:
    - Home/Dashboard
    - Detail
    - Form Tambah/Edit
    - Settings/Info
6. Gunakan minimal **1 StatefulWidget** dan beberapa **StatelessWidget**.
7. Hindari overflow, unbounded constraints, dan layout error.

## Spesifikasi fitur wajib

### 1) Halaman Home/Dashboard

Halaman utama harus menampilkan:

- AppBar dengan judul aplikasi,
- ringkasan data,
- daftar item dalam bentuk **ListView** atau **GridView**,
- minimal satu elemen tata letak seperti `Stack`, `Wrap`, `Row`, `Column`, `Spacer`, atau `Card`,
- tombol atau ikon favorit yang mengubah state lokal.

Daftar item harus dapat dipilih untuk membuka halaman detail.

### 2) Halaman Detail

Halaman detail harus menampilkan:

- informasi lengkap dari item yang dipilih,
- judul, deskripsi, kategori, dan elemen visual,
- navigasi kembali ke halaman sebelumnya,
- minimal satu data dikirim dari halaman Home ke Detail menggunakan `Navigator.pushNamed` atau `Navigator.push` dengan arguments.

### 3) Halaman Form Tambah/Edit

Halaman ini harus berisi form input dengan minimal 3 field, misalnya:

- nama item,
- kategori,
- deskripsi,
- atau email jika temanya form registrasi.

Wajib memakai:

- `Form`,
- `TextFormField`,
- `validator`,
- tombol submit,
- validasi input minimal untuk field kosong dan minimal panjang karakter.  

### 4) Halaman Settings / Info

Halaman ini harus memuat:

- toggle tema terang/gelap atau mengikuti sistem,
- contoh widget adaptive seperti `Switch.adaptive`,
- minimal satu elemen accessibility, misalnya `Semantics` atau area sentuh yang layak.  

## Ketentuan responsive design

Aplikasi wajib responsif dan menyesuaikan ukuran layar.

### Minimum yang harus diterapkan

1. Gunakan `SafeArea`.
2. Gunakan `MediaQuery` untuk membaca ukuran layar atau orientasi.
3. Gunakan `LayoutBuilder` untuk mengubah layout berdasarkan lebar area yang tersedia.
4. Gunakan breakpoint berikut:
    - **Mobile**: kurang dari 600 px, tampilkan 1 kolom
    - **Tablet**: 600 px sampai 999 px, tampilkan 2 kolom
    - **Desktop/Layar lebar**: 1000 px ke atas, tampilkan 4 kolom.  
   
## Ketentuan state management

Gunakan state management sederhana berbasis `setState` untuk:

- toggle favorit,
- perubahan visibilitas,
- perubahan tema,
- atau perubahan isi form sementara.

Minimal ada **2 state dinamis** yang benar-benar mengubah tampilan. `setState` dipakai untuk UI lokal yang berubah, sedangkan state yang lebih kompleks bisa naik ke Provider atau Riverpod, tetapi untuk tugas ini cukup `setState` selama kebutuhan aplikasi masih sederhana.

## Ketentuan navigasi

Wajib ada:

- navigasi antar halaman memakai `Navigator`,
- minimal 1 penggunaan `push`,
- minimal 1 penggunaan `pop`,
- minimal 1 penggunaan named route atau passing arguments,
- penggunaan `PopScope` pada halaman form untuk mencegah keluar tanpa konfirmasi saat data belum tersimpan.  
    Materi membahas `Navigator.push`, `Navigator.pop`, named routes, `arguments`, dan `PopScope` sebagai pendekatan modern untuk kontrol back button.

## Ketentuan layout

Aplikasi harus menunjukkan minimal 5 dari elemen layout berikut:

- `Row`
- `Column`
- `Container`
- `Padding`
- `SizedBox`
- `Stack`
- `Positioned`
- `Expanded`
- `Flexible`
- `Spacer`
- `ListView`
- `GridView`
- `Wrap`
- `SingleChildScrollView`

Selain itu:

- gunakan `Expanded` atau `Flexible` di area yang rawan overflow,
- gunakan `SingleChildScrollView` bila konten lebih tinggi dari layar,
- gunakan `shrinkWrap: true` bila `ListView` atau `GridView` berada di dalam `Column`.  

## Ketentuan tema dan aksesibilitas

Wajib menerapkan:

1. `ThemeData` untuk tema utama aplikasi.
2. `ColorScheme.fromSeed` atau skema warna yang konsisten.
3. Dukungan dark mode.
4. Minimal satu `Semantics` untuk elemen penting.
5. Minimal satu tombol atau target sentuh dengan ukuran yang layak.
6. Teks dan ukuran komponen tidak boleh rusak saat ukuran layar berubah.

Warna dan gaya sebaiknya diambil dari tema, bukan hardcode satu per satu.

## Ketentuan performa dan kerapian kode

Wajib:

- memakai `const` untuk widget statis sebanyak mungkin,
- memecah widget besar menjadi widget kecil,
- tidak menaruh `setState` di area yang terlalu luas tanpa alasan,
- menghindari rebuild yang tidak perlu,
- memberi nama variabel, class, dan method dengan jelas.

## Hal yang tidak boleh

1. Tidak boleh memakai backend atau API online.
2. Tidak boleh memakai database online.
3. Tidak boleh menyalin full project dari internet tanpa modifikasi.
4. Tidak boleh ada error layout seperti overflow, unbounded height, atau unbounded width.
5. Tidak boleh semua tampilan dibuat dalam satu file besar tanpa struktur yang jelas.

---

# Grading Rubric Tugas Utama 0-100

## A. Struktur aplikasi dan komposisi widget: 10 poin

- 10: struktur rapi, widget dipisah dengan baik, penggunaan StatelessWidget dan StatefulWidget tepat.
- 5-9: aplikasi berjalan, tetapi struktur masih campur aduk.
- 0-4: struktur sangat buruk atau banyak bagian tidak berfungsi.

## B. Layout dan penggunaan widget dasar: 15 poin

- 13-15: pemakaian `Row`, `Column`, `Container`, `Padding`, `SizedBox`, `ListView` atau `GridView` tepat dan konsisten.
- 7-12: layout cukup jalan, tetapi kurang variatif atau kurang rapi.
- 0-6: layout bermasalah atau tidak sesuai materi.

## C. Responsive design: 15 poin

- 13-15: memakai `MediaQuery`, `LayoutBuilder`, `SafeArea`, dan breakpoint dengan benar.
- 7-12: responsive ada, tetapi belum konsisten di semua layar.
- 0-6: tampilan hanya cocok untuk satu ukuran layar.

## D. Navigation dan alur antar halaman: 15 poin

- 13-15: navigasi lengkap, ada push, pop, named route atau arguments, dan alur jelas.
- 7-12: navigasi ada, tetapi belum rapi atau belum lengkap.
- 0-6: navigasi rusak atau hanya satu halaman.

## E. State management lokal: 15 poin

- 13-15: `setState` digunakan dengan tepat untuk fitur interaktif yang benar-benar berubah.
- 7-12: state ada, tetapi implementasinya kurang bersih.
- 0-6: state tidak bekerja atau tidak relevan.

## F. Form dan validasi input: 10 poin

- 9-10: form berfungsi, validasi jelas, pesan error tepat.
- 5-8: form ada, tetapi validasi masih lemah.
- 0-4: form tidak valid atau tidak bisa dipakai.

## G. Theme dan accessibility: 10 poin

- 9-10: tema terang/gelap berjalan, `ThemeData` dipakai, ada `Semantics` atau aksesibilitas lain yang jelas.
- 5-8: tema ada, tetapi aksesibilitas masih minim.
- 0-4: tema hardcode dan aksesibilitas diabaikan.

## H. Performa dan kualitas kode: 10 poin

- 9-10: banyak `const`, rebuild terkontrol, kode bersih dan mudah dibaca.
- 5-8: cukup bersih, tetapi belum optimal.
- 0-4: banyak duplikasi, boros rebuild, atau rawan error.

**Total nilai utama: 100 poin**

---

# Bonus 0-10 poin

Bonus diberikan hanya untuk fitur tambahan yang benar-benar berjalan.

## Bonus yang dapat diambil

- **3 poin**: Hero animation antar halaman.
- **2 poin**: custom transition dengan `PageRouteBuilder`.
- **2 poin**: data tersimpan lokal, misalnya `SharedPreferences` atau restore state sederhana.
- **2 poin**: adaptive widget tambahan, misalnya beberapa komponen mengikuti platform Android/iOS.
- **1 poin**: peningkatan UX kecil yang rapi, misalnya loading state, empty state, atau micro interaction yang halus.

**Maksimum bonus: 10 poin**

Happy Coding Folks! 💜
