##Cara Kerja Login

#Input Data: Pengguna memasukkan username dan password.
#Hash Password: Jika password di database menggunakan hash (contoh: MD5), aplikasi meng-hash password sebelum mengirimnya ke server.
#Kirim ke Server: Data dikirim ke API login (login.php) menggunakan metode POST.
#Verifikasi di Server: Server memeriksa apakah username dan password cocok dengan data di database.
#Notifikasi Hasil:
Jika berhasil, pengguna diarahkan ke halaman utama.
Jika gagal, muncul pesan "Username atau Password Salah".
Penyimpanan Token: Jika server mengembalikan token, token disimpan di local storage untuk autentikasi sesi.
Persiapan

#Database: Tabel user dengan kolom username dan password.
#File Koneksi: koneksi.php untuk menghubungkan ke database.
Jalankan Aplikasi
Letakkan folder proyek di www/ (Laragon) atau htdocs/ (XAMPP).
Jalankan aplikasi dengan:
html
''
bash
ionic serve
''
