+++
title = 'Cara Verifikasi Google Search Console di Situs Hugo + GitHub Pages'
slug = 'cara-verifikasi-google-console-hugo-github'
date = 2026-09-09T00:01:00Z
draft = false
description = 'Panduan lengkap dan terstruktur untuk melakukan verifikasi kepemilikan Google Search Console pada website berbasis Hugo dan GitHub Pages.'
summary = 'Ingin website Hugo Anda terindeks di Google? Simak panduan lengkap verifikasi Google Search Console menggunakan metode yang paling praktis.'
categories = ['Tutorial', 'Web Development']
tags = ['Hugo', 'GitHub Pages', 'SEO', 'Google Search Console']
author = 'Admin'
+++

Menghubungkan website berbasis **Hugo dan GitHub Pages** ke **Google Search Console (GSC)** merupakan langkah krusial agar seluruh konten Anda dapat diindeks oleh mesin pencari Google. Dengan demikian, website Anda dapat muncul pada halaman hasil pencarian.

Berikut adalah panduan lengkap dan terstruktur untuk melakukan verifikasi kepemilikan menggunakan metode yang paling aman dan bersih tanpa memicu eror pada sistem *build* Hugo.

---

## Langkah 1: Mendapatkan File Verifikasi dari Google Search Console

1. Buka halaman resmi [Google Search Console](https://search.google.com/search-console/).
2. Masuk menggunakan akun Google Anda.
3. Pilih tipe properti **Awalan URL (URL prefix)** di bagian kanan.
4. Masukkan URL website Anda secara lengkap (Contoh: `https://situsku.github.io`).
5. Klik **Teruskan / Continue**.
6. Pada opsi metode verifikasi yang muncul, pilih metode **File HTML** (Sangat Direkomendasikan).
7. Unduh (*download*) file HTML resmi yang disediakan oleh Google (biasanya file tersebut bernama unik seperti `google456xyz.html`).
8. Simpan file tersebut di komputer Anda.

---

## Langkah 2: Memasang File HTML di Folder Static Hugo

Karena beberapa tema Hugo tidak mendukung pemrosesan kode HTML mentah (shortcode) langsung di dalam file Markdown, metode pemindahan file ke folder `static` adalah solusi terbaik dan paling bersih.

1. Buka direktori atau folder utama proyek Hugo Anda.
2. Cari folder bernama **`static`** (folder ini sejajar dengan folder `content`, `themes`, dan `config`).
3. Pindahkan atau *paste* file HTML verifikasi dari Google yang sudah Anda unduh tadi ke dalam folder **`static`** tersebut.
   * *Struktur jalurnya akan menjadi seperti ini: `proyek-hugo/static/google456xyz.html`*
4. Simpan perubahan, lalu lakukan proses **Git Commit** dan **Git Push** repositori Anda ke GitHub.

> **Catatan Penting Pengalaman Penulis (Tips Mengatasi Folder `static` yang Hilang):**
> Saat pertama kali memeriksa repositori di GitHub, Anda mungkin akan menyadari bahwa folder `static` (yang berada di luar folder `themes`) **tidak muncul atau tidak kelihatan sama sekali**. 
> 
> Jangan panik, hal ini terjadi karena sistem Git secara otomatis akan mengabaikan (*ignore*) folder yang kosong tanpa isi file sama sekali. 
> 
> **Solusinya:** Anda hanya perlu membuat folder baru bernama `static` secara manual di dalam direktori utama proyek Hugo Anda (sejajar dengan folder `content`). Setelah folder dibuat, langsung masukkan file verifikasi HTML dari Google tersebut ke dalamnya (Struktur: `static/google12345.html`), ganti kodenya google12345.html menggunakan milik Anda. Begitu folder `static` sudah berisi file, sistem Git akan langsung mendeteksinya dan folder tersebut akan muncul di GitHub setelah Anda melakukan *push*.

---

## Langkah 3: Melakukan Konfirmasi Verifikasi

1. Setelah file HTML berada di folder `static` dan Anda telah melakukan *push* ke GitHub, tunggu sekitar 1 hingga 2 menit.
2. Pastikan proses *GitHub Actions* selesai membangun (*build*) ulang website Anda dengan status sukses (centang hijau).
3. Kembali ke tab browser **Google Search Console**.
4. Klik tombol **Verifikasi / Verify**.
5. Sistem akan langsung menampilkan notifikasi berwarna hijau yang menyatakan bahwa **Kepemilikan telah diverifikasi**.

---

## Kesimpulan

Website Hugo Anda kini telah resmi terhubung dengan Google Search Console. Langkah selanjutnya yang sangat disarankan adalah mendaftarkan **Sitemap** Anda (pada Hugo biasanya terletak di `https://github.iositemap.xml`) melalui menu *Sitemaps* di Google Search Console untuk mempercepat indeksasi artikel-artikel baru ke depannya.
