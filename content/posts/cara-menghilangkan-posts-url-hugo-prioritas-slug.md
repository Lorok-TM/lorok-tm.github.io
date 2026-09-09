+++
title = 'Cara Menghilangkan /posts/ di URL Hugo dan Mengatur Prioritas Slug'
slug = 'cara-menghilangkan-posts-url-hugo-prioritas-slug'
date = 2026-09-08T14:30:00+07:00
draft = false
description = 'Panduan lengkap cara merapikan struktur URL di Hugo dengan menghapus folder /posts/ agar langsung menempel ke domain utama dan mengaturnya ramah SEO.'
summary = 'Ingin URL Hugo Anda lebih pendek dan estetik tanpa sub-folder /posts/? Pelajari trik konfigurasi permalinks di hugo.toml untuk memprioritaskan kustom slug.'
categories = ['Tutorial', 'Web Development']
tags = ['Hugo', 'Permalinks', 'SEO', 'Struktur URL']
author = 'Admin'
+++

Secara standar bawaan pabrik, Hugo akan membuat URL artikel Anda menjadi agak panjang karena menyertakan nama folder di dalam rumpunnya, misalnya: `domain ://anda.com`. Bagi sebagian orang, adanya sub-folder `/posts/` ini terasa mengganggu estetika dan kurang maksimal untuk optimasi SEO.

Kabar baiknya, kita bisa memotong jalur tersebut agar URL artikel langsung menempel di belakang domain utama, sekaligus mengatur sistem agar otomatis mendeteksi kustom `slug` terlebih dahulu sebelum terpaksa menggunakan `title` (judul).

Berikut adalah panduan lengkap cara mengatur rute permalinks di Hugo agar website Anda terlihat lebih profesional.

---

## Langkah 1: Mengubah Konfigurasi di `hugo.toml`

Kunci utama untuk mengatur rute URL di Hugo berada pada file konfigurasi pusat bernama **`hugo.toml`** (atau `hugo.yaml`). 

1. Buka folder proyek Hugo Anda menggunakan teks editor seperti **VS Code**.
2. Cari dan buka file **`hugo.toml`** yang terletak di folder paling luar (root).
3. Tambahkan atau ubah pengaturan `[permalinks]` Anda menjadi seperti kode di bawah ini:

```toml
[permalinks]
  posts = '/:slug/'
```

> **⚠️ CATATAN PENTING (PERINGATAN):** 
> Sebelum Anda menyimpan perubahan, pastikan untuk memeriksa baris kode di atasnya. Jika di dalam file `hugo.toml` Anda sudah ada perintah `posts = ...` bawaan dari tema, perintah lama tersebut **WAJIB DIHAPUS atau DIEDIT** disesuaikan seperti kode di atas. Di dalam file konfigurasi **hanya boleh ada satu perintah `posts`** di bawah blok `[permalinks]` supaya sistem tidak tabrakan dan tidak mbledos (error)!

4. Simpan perubahan file tersebut.

Dengan menghapus kata `posts` di dalam tanda petik dan hanya menyisakan `/:slug/`, Anda telah berhasil memerintahkan Hugo untuk langsung menempelkan URL artikel tepat di belakang domain utama Anda.

---

## Langkah 2: Memahami Cara Kerja Sistem Prioritas URL Hugo

Mengapa pengaturan di atas sangat ajaib dan aman? Karena secara otomatis, Hugo menerapkan sistem tingkatan prioritas (*fallback system*) saat membaca artikel Anda:

1. **Prioritas Utama (Kustom Slug):** Saat Hugo membangun website Anda, dia akan mengecek bagian Front Matter (bagian atas artikel). Jika Anda memasang parameter `slug = 'judul-kustom'`, maka Hugo akan **memprioritaskan** kata tersebut untuk dijadikan URL.
2. **Prioritas Kedua (Fallback Title):** Jika ternyata Anda lupa atau sengaja tidak mengisi parameter `slug` di bagian atas artikel, Hugo tidak akan error. Sistem akan otomatis beralih menggunakan komponen `title` (judul) artikel Anda untuk dicetak menjadi URL.

Sistem cerdas ini membuat website Anda tetap aman dari *broken link* meskipun Anda memiliki gaya penulisan Front Matter yang berbeda-beda di setiap artikel.

---

## Langkah 3: Melakukan Push ke GitHub

Setelah memastikan kodingan di `hugo.toml` lokal sudah benar, saatnya mengirimkan perubahan tersebut ke server agar langsung online:

1. Buka terminal komputer Anda.
2. Ketik perintah Git standar secara berurutan:
   ```bash
   git add .
   git commit -m "mengubah permalinks menjadi kustom slug tanpa posts"
   git push origin main
   ```
3. Tunggu proses build dari GitHub Actions selama 1-2 menit.

---

## Kesimpulan

Membuat URL website yang pendek dan langsung menempel pada domain utama sangatlah mudah di Hugo. Cukup dengan modal satu baris kode `posts = '/:slug/'`, Anda sudah mendapatkan struktur URL yang rapi, estetik, dan memiliki nilai tinggi di mata mesin pencari (SEO). Selamat mencoba!
