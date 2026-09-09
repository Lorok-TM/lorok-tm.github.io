+++
title = 'Perbandingan Tag HTML vs Markdown Murni di Hugo: Kapan Harus Pakai?'
slug = 'perbandingan-tag-html-vs-markdown-murni-hugo'
date = 2026-09-08T17:00:00+07:00
draft = false
description = 'Ketahui perbedaan mendasar antara menulis artikel menggunakan tag HTML mentah vs Markdown murni di Hugo beserta solusi mengatasi error unsafe render.'
summary = 'Mana yang lebih baik untuk menulis artikel di Hugo, HTML atau Markdown? Pelajari kelebihan masing-masing dan cara mengaktifkan fitur unsafe HTML.'
categories = ['Tutorial', 'Web Development']
tags = ['Hugo', 'Markdown', 'HTML', 'Tips Website']
author = 'Admin'
+++

Bagi pemula yang baru bermigrasi dari platform seperti WordPress atau Blogger ke **Hugo Static Site Generator**, format penulisan artikel sering kali menjadi bahan pertanyaan. Apakah sebaiknya kita menulis artikel menggunakan **tag HTML mentah** (seperti `<div>`, `<h2>`, `<p>`) atau menggunakan **Markdown murni** (seperti `#`, `##`, `**`)?

Secara teknis, Hugo mendukung kedua format tersebut. Namun, masing-masing memiliki karakteristik, kelebihan, serta aturan keamanan khusus yang wajib Anda ketahui agar tampilan situs tidak rusak.

Berikut adalah perbandingan mendalam antara Tag HTML vs Markdown Murni di Hugo.

---

## 1. Menulis dengan Markdown Murni (Sangat Direkomendasikan)

Markdown adalah bahasa marka bawaan yang paling disukai oleh Hugo. Formatnya sangat ringkas karena hanya menggunakan simbol-simbol sederhana untuk mengatur struktur tulisan.

* **Kelebihan:**
  * **Sangat Bersih:** Kode di dalam teks editor (VS Code) sangat rapi dan mudah dibaca tanpa terganggu barisan tag penutup.
  * **Langsung Jalan:** Tanpa perlu mengubah konfigurasi apapun, Hugo akan langsung merender tulisan Anda menjadi halaman web yang sempurna.
  * **Cepat Di-ketik:** Menulis tebal cukup dengan `**teks**`, membuat judul cukup dengan `## Judul`.
* **Kekurangan:** Terbatas pada format standar. Anda tidak bisa menambahkan kelas CSS khusus (`class="..."`) pada elemen tertentu secara langsung di tengah paragraf.

---

## 2. Menulis dengan Tag HTML Mentah

Beberapa orang lebih nyaman menyalin kode HTML langsung dari dokumen lain atau sengaja menggunakan HTML untuk membuat tata letak (*layout*) artikel yang lebih kompleks.

* **Kelebihan:** Sangat fleksibel. Anda bisa menyisipkan tag `<div>`, memberikan gaya warna langsung via komponen `style="..."`, atau menyematkan kelas CSS untuk kustomisasi tampilan yang rumit.
* **Kekurangan (Masalah Keamanan):** Secara standar, parser Markdown milik Hugo (bernama Goldmark) akan **memblokir dan menyembunyikan** semua tag HTML mentah yang Anda tempel di dalam file `.md`. Hal ini dilakukan demi keamanan (*security*) untuk mencegah injeksi skrip berbahaya.

---

## Solusi: Cara Mengaktifkan Fitur HTML Mentah di Hugo

Jika Anda terpaksa harus menggunakan tag HTML mentah di dalam artikel agar tampilannya sesuai keinginan, Anda harus memberikan izin khusus pada konfigurasi Hugo.

Caranya, buka file **`hugo.toml`** Anda, lalu tambahkan baris kode di bawah ini di bagian paling bawah:

```toml
[markup]
  [markup.goldmark]
    [markup.goldmark.renderer]
      unsafe = true
```

Dengan menyetel `unsafe = true`, Anda memerintahkan Hugo untuk tidak memblokir tag HTML mentah lagi, sehingga semua kode HTML yang Anda tempel di dalam artikel akan langsung aktif dan muncul di website.

---

## Kesimpulan: Kapan Harus Memilih?

* Gunakan **Markdown Murni** untuk penulisan artikel tutorial, blog harian, atau berita biasa. Format ini jauh lebih cepat, aman, dan meminimalkan risiko error saat proses *deploy*.
* Gunakan **Tag HTML Mentah** (ditambah setelan `unsafe = true`) hanya jika Anda membutuhkan struktur halaman khusus yang interaktif, tabel super rumit, atau kustomisasi desain yang tidak bisa diakomodasi oleh Markdown standar.
