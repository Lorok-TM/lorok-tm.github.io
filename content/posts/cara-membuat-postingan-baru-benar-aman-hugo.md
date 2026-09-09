+++
title = 'Cara Membuat Postingan Baru dengan Benar dan Aman di Hugo'
slug = 'cara-membuat-postingan-baru-benar-aman-hugo'
date = 2026-09-08T22:10:00+07:00
draft = false
description = 'Panduan lengkap cara membuat artikel baru di Hugo secara manual yang benar, ramah SEO, dan aman dari risiko error build.'
summary = 'Bagaimana cara membuat postingan baru di Hugo yang aman dan ramah SEO? Pelajari struktur Front Matter komplit dan aturan penggunaan Markdown vs HTML.'
categories = ['Tutorial', 'Web Development']
tags = ['Hugo', 'Front Matter', 'Markdown', 'Tips Keamanan']
author = 'Admin'
+++

Membuat postingan atau artikel baru di **Hugo Static Site Generator** sebenarnya sangat mudah. Namun, bagi pemula yang baru belajar, ada beberapa aturan main penting yang wajib dipahami agar artikel tidak hanya sukses muncul secara online, tetapi juga rapi secara struktur URL (SEO) dan aman dari celah keamanan.

Berikut adalah panduan lengkap langkah demi langkah cara membuat postingan baru di Hugo dengan metode yang benar dan aman.

---

## Langkah 1: Membuat File Artikel Baru (`.md`)

Setiap artikel di Hugo wajib disimpan dalam format file **`.md` (Markdown)**. Anda bisa membuatnya secara manual lewat VS Code atau langsung di repositori GitHub di dalam folder **`content/posts/`** (atau folder artikel sesuai tema Anda).

Berikan nama file menggunakan huruf kecil semua dan gunakan tanda hubung (`-`) sebagai pemisah kata, contohnya:  
`cara-membuat-postingan-baru-benar-aman-hugo.md`

---

## Langkah 2: Mengisi Struktur Front Matter yang Komplit

Front Matter adalah bagian paling atas dari artikel Anda yang diapit oleh tanda `+++` (format TOML). Bagian ini sangat penting karena berfungsi sebagai pengatur identitas artikel dan optimasi SEO. 

Berikut adalah contoh struktur Front Matter komplit yang sangat direkomendasikan untuk Anda gunakan di setiap artikel:

```toml
+++
title = 'Judul Artikel Anda yang Menarik'
slug = 'kustom-slug-url-pilihan-anda'
date = 2026-09-08T22:10:00+07:00
draft = false
description = 'Deskripsi pendek isi artikel untuk muncul di pencarian Google.'
summary = 'Ringkasan singkat artikel yang akan muncul di halaman utama blog.'
categories = ['Kategori']
tags = ['Tag1', 'Tag2']
author = 'Nama Penulis'
+++
```

### Catatan Penting Mengenai Pengaturan di Atas:
1. **Status Draft (`draft`):** Pastikan diubah menjadi `false`. Jika masih `true`, artikel Anda tidak akan pernah muncul di situs online.
2. **Pengaturan Tanggal (`date`):** Jika Anda ingin artikel langsung tayang saat itu juga tanpa masalah, pastikan tanggalnya diatur menggunakan tanggal hari ini atau **tanggal mundur (kemarin)**. Jika diisi tanggal masa depan (besok), Hugo akan menyembunyikan artikel tersebut sampai tanggal itu tiba.
3. **Kustom `slug`:** Gunakan parameter `slug` agar URL website Anda pendek, bersih, dan langsung menempel di belakang domain utama (pastikan Anda sudah mengaktifkan fitur permalinks di file `hugo.toml`).

---

## Langkah 3: Aturan Menulis Isi Konten (Pilih Format Anda)

Saat mulai menulis isi artikel di bawah tanda penutup `+++`, Anda dihadapkan pada dua pilihan gaya penulisan yang menentukan tingkat keamanan website Anda:

### Pilihan A: Menggunakan Markdown Murni (Sangat Aman & Direkomendasikan)
Gunakan simbol standar bawaan Hugo untuk menulis, seperti `##` untuk judul, `**teks**` untuk tebal, dan `[Nama Link](URL)` untuk tautan. 
* **Aturan Keamanan:** Jika Anda memilih cara ini, Anda **TIDAK PERLU** memasang kode gerbang `unsafe = true` di file `hugo.toml` Anda (buang atau hapus saja kode tersebut). Website Anda akan menjadi 100% aman dan kebal dari serangan injeksi skrip berbahaya.

### Pilihan B: Memaksa Menggunakan Tag HTML Mentah
Jika Anda terpaksa harus memasukkan kode HTML seperti `<div>`, `<p>`, atau tabel kustom di tengah artikel agar tampilannya lebih fleksibel:
* **Aturan Keamanan:** Anda **WAJIB MENYALAKAN SAKELAR** di file konfigurasi utama `hugo.toml` dengan menambahkan perintah:
  ```toml
  [markup.goldmark.renderer]
    unsafe = true
  ```
  *Peringatan:* Jika sakelar ini tidak dinyalakan (OFF), seluruh tag HTML mentah di dalam artikel Anda akan otomatis diblokir dan dihilangkan oleh Hugo.

---

## Kesimpulan

Kunci utama dalam membuat postingan baru di Hugo yang sukses adalah ketelitian dalam mengatur **Front Matter** (tanggal, status draft, dan slug) serta konsistensi dalam memilih **format penulisan**. Menulis dengan Markdown murni tanpa membuka sakelar `unsafe` adalah jalan ninja terbaik untuk menghasilkan website yang super cepat, bersih, dan aman dari peretasan. Selamat menulis!
