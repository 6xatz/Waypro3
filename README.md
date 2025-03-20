## Mata Kuliah

Sebagai tugas praktikum: [1 - 3] Pemrograman Web II | Universitas Pelita Bangsa.

## 📖 Daftar Praktikum

1. [Praktikum 1: PHP Framework CodeIgniter 4](##praktikum-1-php-framework-codeigniter-4)
2. [Praktikum 2: Framework Lanjutan (CRUD)](##praktikum-2-framework-lanjutan-crud)
3. [Praktikum 3: View Layout dan View Cell](##praktikum-3-view-layout-dan-view-cell) - UNDERWORK!

---

## Praktikum 1: PHP Framework CodeIgniter 4

- Bagian 1:

  > File: `php.ini`

  <p align="left">
    <img src="/ss/php.jpg" width="500">
  </p>
  
Pada bagian extension, hilangkan tanda ; (titik koma) pada ekstensi yang akan diaktifkan. Kemudian simpan kembali filenya dan restart Apache web server.

- Bagian 2:

  > File: [Unduh CodeIgniter disini](https://codeigniter.com/download)

  <p align="left">
    <img src="/ss/ci4.jpg" width="500">
  </p>
  
Ekstrak ke `www/ci4/` lalu Buka pada browser: `localhost/ci4/Public/`.

- Bagian 3:

  > File: `spark` dan `mode development` pada `.env`.

  <p align="left">
    <img src="/ss/P1_01.jpg" width="500">
  </p>
  
CodeIgniter secara default menggunakan `mode production` sehingga error pada log disembunyikan.

**Memahami Konsep Framework: MVC atau Model-View-Controller**

  <p align="left">
    <img src="/ss/P1_02.jpg" width="500">
  </p>
  
1. `Model` - Bertanggung jawab atas pengelolaan data.
2. `View` - Menampilkan tampilan ke pengguna.
3. `Controller` - Menghubungkan Model dan View.

**Routing dan Controller**

  <p align="left">
    <img src="/ss/P1_03.jpg" width="500">
  </p>

Jalankan perintah: `php spark routes` untuk melihat daftar route.

## Pertanyaan dari Praktikum 1

1. Lengkapi kode program untuk menu lainnya yang ada pada Controller Page, sehingga semua
link pada navigasi header dapat menampilkan tampilan dengan layout yang sama:

 <p align="left">
    <img src="/ss/P1_04.jpg" width="500">
  </p>
  
---

## Praktikum 2: Framework Lanjutan (CRUD)

- Bagian 1:

  > Buat Database terlebih dahulu.
  
  <p align="left">
    <img src="/ss/P02_01.jpg" width="500">
  </p>
  
```sql
CREATE DATABASE lab_ci4;

CREATE TABLE artikel (
  id INT(11) AUTO_INCREMENT,
  title VARCHAR(200) NOT NULL,
  contain TEXT,
  image VARCHAR(200),
  status TINYINT(1) DEFAULT 0,
  slug VARCHAR(200),
  PRIMARY KEY(id)
);
```
  
Disini saya melakukan sedikit modifikasi pada bagian Database supaya menggunakan Bahasa Inggris.

- Bagian 2:

  > Konfigurasi Database melalui `app/config/database.php` dan beberapa file lainnya.

  <p align="left">
    <img src="/ss/P02_02.jpg" width="500">
  </p>
  <p align="left">
    <img src="/ss/P02_03.jpg" width="500">
  </p>
  
Kita akan menghubungkan Database.php, Routes.php, dan style.css, serta menambahkan ArticleModel.php sebagai ORM untuk memudahkan pengelolaan database di Controller serta Article.php sebagai Controller untuk menangani artikel.

- Bagian 3:

  > CLI: `php spark serve` terlebih dahulu agar MVC berfungsi dengan baik.

  <p align="left">
    <img src="/ss/P2_04.jpg" width="500">
  </p>
  
Selanjutnya, kita akan menambahkan Views untuk: index.php (halaman artikel), dan admin_index.php (halaman manajemen artikel) dan membuat Views untuk form_edit.php dan form_add.php, serta menambahkan fungsi delete pada Controller agar dapat dikelola melalui admin_index.php .

## Documentation

All associated resources. are licensed under the [MIT License](https://mit-license.org/).
