# Ionic Login App

Aplikasi ini adalah contoh implementasi fitur login menggunakan **Ionic** sebagai front-end dan **PHP** dengan **MySQL** sebagai back-end.

## Cara Kerja Login

1. **Input Data Pengguna**: Pengguna memasukkan **username** dan **password** di form login.
2. **Hash Password**: Jika password di database menggunakan hashing (contoh: MD5), aplikasi akan meng-hash password sebelum mengirimkannya ke server untuk verifikasi.
3. **Kirim Data ke Server**: Data dikirim ke endpoint API login (`login.php`) menggunakan metode POST.
4. **Verifikasi di Server**: Server mengecek apakah **username** dan **password** cocok dengan data yang ada di database.
5. **Pemberian Notifikasi**:
   - Jika berhasil, pengguna akan diarahkan ke halaman utama atau halaman selanjutnya.
   - Jika gagal, muncul pesan "Username atau Password Salah".
6. **Penyimpanan Token (Jika Diperlukan)**: Jika server mengembalikan token sebagai bukti autentikasi, token disimpan di **local storage** untuk menjaga sesi tetap aktif hingga logout.

## Screenshot

Berikut adalah contoh tampilan aplikasi saat proses login:

![Login Screen](screenshot/login_screen.png)
*Gambar 1: Form Login pada aplikasi Ionic.*

![Error Notification](screenshot/error_notification.png)
*Gambar 2: Notifikasi jika login gagal.*

## Langkah 1

1. Database API: Buat tabel `user` di database dengan kolom `username` dan `password`.
2. File Koneksi: Buat file `koneksi.php` untuk menghubungkan aplikasi dengan database.
3. Endpoint Login: Buat file `login.php` yang menerima request dan melakukan validasi username dan password.
4. Letakkan folder proyek di direktori server, seperti `www/` pada Laragon atau `htdocs/` pada XAMPP.

## Langkah 2

1. Buat Project Ionic dengan nama cobalogin, Pilih Angular sebagai framework, blank sebagai template, dan aktifkan modul NgModules
2. Install Modul npm i @capacitor/preferences
3. Gunakan perintah ionic generate [schematic] [name] untuk membuat berbagai fitur aplikasi, seperti page, component, dan service
4. Selanjutnya, tambah kode program pada modul praktikum
5. Jalankan aplikasi Ionic dengan perintah berikut di terminal:
   ```bash
   ionic serve
    
   
## Proses Login
1. Tampilan Halaman Login: melihat halaman login dengan dua input: username dan password, serta tombol Login.
2. Menekan Tombol Login: Saat tombol ditekan, aplikasi memeriksa apakah username dan password telah diisi.
3. Kirim Permintaan Login: Jika input valid, aplikasi mengirim permintaan ke server dengan username dan password.
4. Tanggapan dari Server: Login Berhasil: Jika server mengonfirmasi bahwa - - login sukses, aplikasi menyimpan token dan username pengguna untuk sesi 
tersebut, lalu mengarahkan pengguna ke halaman utama.
respon : (res.status_login == "berhasil")
- Login Gagal: Jika login gagal (misalnya, username atau password salah), aplikasi menampilkan pesan notifikasi bahwa login tidak berhasil.
respon : (res.status_login == "gagal")
5.Status Pengguna: Aplikasi menggunakan mekanisme untuk menyimpan status login (terautentikasi atau tidak) menggunakan BehaviorSubject, yang memungkinkan bagian lain aplikasi mengetahui apakah pengguna sudah masuk.
5. Logout:
Jika pengguna memilih untuk keluar, aplikasi akan menghapus data login dan mengarahkan kembali ke halaman login.

## Alur Login
Pengguna -> Masukkan Username dan Password -> Tekan Login
     |
     v
Validasi Input -> Jika Kosong -> Notifikasi
     |
     v
Permintaan ke Server -> Jika Berhasil -> Simpan Token dan Username
     |                                   |
     v                                   v
Arahkan ke Home                   Notifikasi Gagal

