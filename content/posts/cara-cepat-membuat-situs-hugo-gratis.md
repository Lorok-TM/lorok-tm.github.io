+++
title = 'Cara Cepat Membuat Situs Hugo Gratis via GitHub Pages (Langsung Online!)'
slug = 'cara-cepat-membuat-situs-hugo-gratis'
date = 2026-09-08T23:59:00+07:00
draft = false
description = 'Panduan lengkap cara membuat website atau blog gratis menggunakan Hugo Static Site Generator dan dideploy otomatis ke GitHub Pages untuk pemula.'
summary = 'Membuat blog yang super cepat dan gratis tidaklah sulit. Pelajari cara otomatis membuat situs Hugo langsung online menggunakan GitHub Pages dari nol.'
categories = ['Tutorial', 'Web Development']
tags = ['Hugo', 'GitHub Pages', 'Website Gratis', 'Blog Pemula']
author = 'Admin'
+++

Setelah sebelumnya kita membahas cara membuat website menggunakan Astro, kali ini kita akan membedah framework alternatif yang tidak kalah populer dan super cepat, yaitu **Hugo**. 

Dengan mengombinasikan Hugo (Static Site Generator berbasis bahasa Go) dan **GitHub Pages** (layanan hosting gratis milik GitHub), Anda bisa memiliki situs dokumentasi, portfolio, atau blog pribadi yang langsung online 100% gratis tanpa biaya sewa server sepeser pun.

Berikut adalah panduan langkah demi langkah membuat situs Hugo dari nol lewat metode otomatis yang paling cepat dan aman.

---

## Persiapan Awal
Sebelum memulai, pastikan Anda sudah memiliki satu akun gratis ini:
* Akun **GitHub** aktif (tempat menyimpan kode sekaligus sebagai server hosting gratisan Anda).

---

## Langkah 1: Membuat Repositori dari Template Resmi Hugo
Cara tercepat tanpa perlu menginstal aplikasi Hugo di komputer sejak awal adalah dengan memanfaatkan template siap pakai yang disediakan oleh komunitas GitHub.

1. Buka browser dan masuk ke akun GitHub Anda.
2. Cari atau gunakan template blog Hugo resmi (salah satu yang paling populer dan mudah digunakan adalah template dengan tema **Ananke**).
3. Klik tombol **"Use this template"** lalu pilih **"Create a new repository"**.
4. **Aturan Penting Penamaan Repo:** Agar situs Anda bisa diakses langsung sebagai domain utama gratis dari GitHub, beri nama repositori Anda dengan format:  
   `username-githubmu.github.io` (contoh: `lorok-tm.github.io`).
5. Setel visibilitas repositori menjadi **Public**.
6. Klik tombol **"Create repository"**. Sekarang, semua pondasi kode situs Hugo Anda sudah aman berada di akun GitHub.

---

## Langkah 2: Mengonfigurasi File `hugo.toml`
Setelah repositori berhasil disalin, kita perlu mengubah alamat URL utamanya agar sesuai dengan nama domain GitHub Pages Anda.

1. Di dalam repositori GitHub Anda, cari file bernama **`hugo.toml`** (atau `hugo.yaml`), lalu klik ikon pensil untuk mengeditnya secara online.
2. Pada baris paling atas, ubah nilai `baseURL` menjadi alamat domain GitHub Pages Anda.  
   Contoh: `baseURL = 'https://github.io'`
3. Klik **"Commit changes..."** di pojok kanan atas untuk menyimpan perubahan tersebut.

---

## Langkah 3: Mengaktifkan Fitur Otomatis GitHub Actions (Deploy)
Langkah terakhir adalah memerintahkan GitHub agar otomatis membangun (*build*) file Hugo Anda menjadi situs web yang siap diakses publik setiap kali ada pembaruan konten.

1. Masuk ke tab **"Settings"** pada repositori Anda.
2. Di menu sebelah kiri, cari bagian *Code and automation*, lalu klik **"Pages"**.
3. Pada bagian *Build and deployment* -> *Source*, ubah pilihannya dari *Deploy from a branch* menjadi **"GitHub Actions"**.
4. GitHub akan otomatis mendeteksi konfigurasi Hugo Anda dan menjalankan alur kerja (*workflow*) pembuatan situs di balik layar.
5. Tunggu proses pembuatan sekitar 1–2 menit. Anda bisa memantau perkembangannya di tab **"Actions"**.

Jika sudah muncul tanda centang hijau, selamat! Situs Hugo Anda kini telah resmi *live* dan bisa diakses oleh semua orang di internet melalui alamat `https://github.io`.

---

## Langkah 4: Cara Mengisi Konten dari Komputer Lokal
Jika situs online sudah jadi, Anda tinggal mengunduhnya ke komputer Anda untuk mulai menulis artikel secara nyaman:

1. Buka terminal komputer Anda, lalu lakukan *clone* repositori:
   ```bash
   git clone https://github.com
   ```
2. Buka folder tersebut menggunakan aplikasi **VS Code**.
3. Buat file artikel baru berformat **`.md`** di dalam folder `content/posts/` (pastikan status `draft = false` dan gunakan tanggal hari ini atau tanggal kemarin agar langsung muncul).
4. Jika sudah selesai menulis, simpan dan jalankan perintah Git:
   ```bash
   git add .
   git commit -m "menambah artikel pertama"
   git push origin main
   ```
5. GitHub Actions akan otomatis memperbarui situs web online Anda dalam hitungan detik!

---

## Kesimpulan
Membuat website dengan Hugo dan GitHub Pages adalah kombinasi terbaik bagi Anda yang menginginkan situs yang super cepat, andal, gratis, dan memiliki keamanan tingkat tinggi. Anda tidak perlu pusing memikirkan biaya perpanjangan hosting bulanan, cukup fokus memproduksi konten tutorial yang bermanfaat bagi pembaca. Selamat mencoba!
