# Refleksi 1

## Prinsip Clean Code dan Secure Coding yang Diterapkan

### 1. Penamaan yang bermakna (Meaningful Names)
Saya berusaha menerapkan prinsip **Meaningful Names** dari *Clean Code*. Saya memsastikan bahwa nama variabel yang saya gunakan deskriptif dan mengungkapkan maksud pengguna secara jelas. Saya berusaha ikuti standar penamaan Java (CamelCase) 
- **Contoh:** saya memakai nama yang spesifik seperti `productName` dan `productQuantity` daripada `pname` atau `pquant`. kode menjadi lebih mudah dibaca tanpa perlu komentar .

### 2. Secure Coding & Identitas Objek 
Dalam mengimplementasikan fitur **Edit**, saya rasa identifikasi unik untuk setiap produk di dalam repository `ArrayList` penting sekali. Mengandalkan input manual dari user untuk ID berisiko dan rentan error.
- **Perbaikan:** Saya mengubah strategi penanganan `productId`. Saya tidak menggunakan String sederhana yang diinput user, tapi mengimplementasikan pembuatan **UUID** secara otomatis.
- **Manfaat:** Langkah ini menjamin bahwa setiap produk yang dibuat memiliki pengenal yang unik sebagai primary key dan aman dari duplikasi (collision). 

## Akan di improve nanti

### 1. Validasi Input & Penanganan Error
Saya menemukan potensi masalah terkait **Validasi Data Input**.
- **Masalah:** Kalau membiarkan kolom "Quantity" kosong saat pembuatan atau pengeditan produk, web akan *error* dan return halaman kesalahan default ("Whitelabel Error Page"). Hal ini terjadi karena aplikasi mencoba mengonversi string kosong menjadi integer.
- **Rencana:** Saat ini dibiarkan dulu seperti ini untuk tutorial sekarang. Akan dieprbaiki di modul-modul mendatang dengan menerapkan validasi yang tepat di sisi klien (*client-side*) maupun sisi server (*server-side*), serta membuat halaman error message.