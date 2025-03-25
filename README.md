## Mata Kuliah

Sebagai tugas praktikum: [1 - 3] Pemrograman Web II | Universitas Pelita Bangsa.

## 📖 Daftar Praktikum

1. [Praktikum 1: PHP Framework CodeIgniter 4](#praktikum-1-php-framework-codeigniter-4)
2. [Praktikum 2: Framework Lanjutan (CRUD)](#praktikum-2-framework-lanjutan-crud)
3. [Praktikum 3: View Layout dan View Cell](#praktikum-3-view-layout-dan-view-cell) - UNDERWORK!

---

## Praktikum 1: PHP Framework CodeIgniter 4

- Bagian 1:

  > File: `php.ini`

  <p align="left">
    <img src="/ss/php.jpg" width="200">
  </p>
  
Pada bagian extension, hilangkan tanda ; (titik koma) pada ekstensi yang akan diaktifkan. Kemudian simpan kembali filenya dan restart Apache web server.

- Bagian 2:

  > File: [Unduh CodeIgniter disini](https://codeigniter.com/download)

  <p align="left">
    <img src="/ss/ci4.jpg" width="600">
  </p>
  
Ekstrak ke `www/ci4/` lalu Buka pada browser: `localhost/ci4/Public/`.

- Bagian 3:

  > File: `spark` dan `mode development` pada `.env`.

  <p align="left">
    <img src="/ss/P1_01.jpg" width="700">
  </p>
  
CodeIgniter secara default menggunakan `mode production` sehingga error pada log disembunyikan.

**Memahami Konsep Framework: MVC atau Model-View-Controller**

  <p align="left">
    <img src="/ss/P1_02.jpg" width="700">
  </p>
  
1. `Model` - Bertanggung jawab atas pengelolaan data.
2. `View` - Menampilkan tampilan ke pengguna.
3. `Controller` - Menghubungkan Model dan View.

**Routing dan Controller**

  <p align="left">
    <img src="/ss/P1_03.jpg" width="700">
  </p>

Jalankan perintah: `php spark routes` untuk melihat daftar route.

## Pertanyaan dari Praktikum 1

1. Lengkapi kode program untuk menu lainnya yang ada pada Controller Page, sehingga semua
link pada navigasi header dapat menampilkan tampilan dengan layout yang sama:

 <p align="left">
    <img src="/ss/P1_04.jpg" width="700">
  </p>
  
---

## Praktikum 2: Framework Lanjutan (CRUD)

- Bagian 1:

  > Buat Database terlebih dahulu.
  
  <p align="left">
    <img src="/ss/P2_01.jpg" width="600">
  </p>
  
```sql
CREATE DATABASE 6xatz;

CREATE TABLE article (
    id INT AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(200) NOT NULL,
    content TEXT,
    image VARCHAR(200),
    status TINYINT(1) DEFAULT 0,
    slug VARCHAR(200) UNIQUE,
);
```
  
Disini saya melakukan sedikit modifikasi pada bagian Database supaya menggunakan Bahasa Inggris.

- Bagian 2:

  > Konfigurasi Database melalui `app/config/database.php` dan beberapa file lainnya.

  <p align="left">
    <img src="/ss/P2_02.jpg" width="700">
  </p>
  <p align="left">
    <img src="/ss/P2_03.jpg" width="700">
  </p>
  
Kita akan menghubungkan Database.php, Routes.php, dan style.css, serta menambahkan ArticleModel.php sebagai ORM untuk memudahkan pengelolaan database di Controller serta Article.php sebagai Controller untuk menangani artikel.

- Bagian 3:

  > CLI: `php spark serve` terlebih dahulu agar MVC berfungsi dengan baik.

  <p align="left">
    <img src="/ss/P2_04.jpg" width="700">
  </p>
  
Selanjutnya, kita akan menambahkan Views untuk: index.php (halaman artikel), dan admin_index.php (halaman manajemen artikel) dan membuat Views untuk form_edit.php dan form_add.php, serta menambahkan fungsi delete pada Controller agar dapat dikelola melalui admin_index.php .

---

## Praktikum 3: View Layout dan View Cell

- Bagian 1:

  > Penyesuaian pada Database.
  
  <p align="left">
    <img src="/ss/P3_01.jpg" width="600">
  </p>
  
```sql
ALTER TABLE Article
ADD COLUMN category VARCHAR(100),
ADD COLUMN created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
ADD COLUMN updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP;
```
  
Lakukan modifikasi pada Database sehingga nanti bisa menggunakan 'Kategori' untuk sortir.

- Bagian 2:

  > Sesuaikan kembali file `header.php, footer.php, ArticleModel.php` dan tambahkan beberapa file baru untuk Components.

  <p align="left">
    <img src="/ss/P3_02.jpg" width="700">
  </p>
  
Pada `app/views/components/latest_article.php` kamu bisa melakukan perubahan mulai dari sortir berdasarkan Tanggal maupun Kategori.

- Bagian 3:

  > CLI: `php spark serve` terlebih dahulu agar MVC berfungsi dengan baik.

  <p align="left">
    <img src="/ss/P3_03.jpg" width="700">
  </p>
  
Jadi ini adalah Hasil dan Tampilan akhir dari Praktikum 1 hingga 3 pada Pemrograman Web II.

## Pertanyaan dari Praktikum 3

1. Apa manfaat utama dari penggunaan View Layout dalam pengembangan aplikasi?

| Manfaat                       | Deskripsi                                                               |
| ----------------------------- | ------------------------------------------------------------------------|
| Menyusun Template Konsisten   | Menggunakan satu layout untuk banyak halaman, memudahkan pemeliharaan   |
| Meningkatkan Efisiensi Koding | Menghindari pengulangan kode dengan menyusun header, footer, dan sidebar|
| Mempermudah Perubahan Tampilan| Cukup ubah satu layout untuk memperbarui tampilan seluruh aplikasi      |
| Memisahkan Logika dan Tampilan| Mempermudah pengembangan dan debugging dengan struktur kode yang rapi   |

2. Jelaskan perbedaan antara View Cell dan View biasa:

| Fitur             | View Layout                                             | View Cell                                                   |
| ----------------- | ------------------------------------------------------- | ----------------------------------------------------------- |
| Fungsi            | Template utama yang mengatur struktur tampilan          | Komponen modular untuk bagian kecil seperti sidebar/widget  |
| Fleksibilitas     | Digunakan untuk halaman penuh                           | Digunakan untuk bagian tertentu dalam tampilan              |
| Pemakaian         | `extend()` dan `renderSection()`                        | `view_cell()`                                               |
| Contoh Penggunaan | Layout dengan header, footer, sidebar                   | Daftar artikel terbaru, widget pencarian, dll               |

## Documentation

All associated resources. are licensed under the [MIT License](https://mit-license.org/).
