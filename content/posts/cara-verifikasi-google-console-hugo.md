+++
title = 'Cara Verifikasi Google Search Console di Situs Hugo + GitHub Pages'
slug = 'cara-verifikasi-google-console-hugo'
date = 2026-09-09T20:12:00+07:00
draft = false
description = 'Panduan lengkap dan terstruktur untuk melakukan verifikasi kepemilikan Google Search Console pada website berbasis Hugo dan GitHub Pages.'
summary = 'Ingin website Hugo Anda terindeks di Google? Simak panduan lengkap verifikasi Google Search Console menggunakan metode yang paling praktis.'
categories = ['Tutorial', 'Web Development']
tags = ['Hugo', 'GitHub Pages', 'SEO', 'Google Search Console']
author = 'Admin'
+++

Menghubungkan website berbasis **Hugo dan GitHub Pages** ke **Google Search Console (GSC)** merupakan langkah krusial agar seluruh konten Anda dapat diindeks oleh mesin pencari Google. Dengan demikian, website Anda dapat muncul pada halaman hasil pencarian.

Berikut adalah panduan lengkap dan terstruktur untuk melakukan verifikasi kepemilikan tanpa harus memodifikasi file eksternal atau tema yang rumit.

---

## Langkah 1: Mendapatkan Kode Verifikasi dari Google Search Console

1. Buka halaman resmi [Google Search Console](https://google.com).
2. Masuk menggunakan akun Google Anda.
3. Jika ini adalah pertama kali, pilih tipe properti **Awalan URL (URL prefix)** di bagian kanan.
4. Masukkan URL website Anda secara lengkap (Contoh: `https://github.io`).
5. Klik **Teruskan / Continue**.
6. Pada opsi metode verifikasi yang muncul, gulir ke bawah ke bagian **Metode verifikasi lainnya**.
7. Pilih metode **Tag HTML** (berupa baris kode yang diawali dengan `<meta name="google-site-verification" ... />`).
8. Salin (*copy*) kode tersebut dan simpan untuk sementara waktu.

---

## Langkah 2: Memasang Kode Verifikasi di Situs Hugo (Pilih Salah Satu)

Terdapat dua metode yang paling efisien untuk menerapkan kode verifikasi ini pada platform Hugo. Anda cukup memilih salah satu metode di bawah ini:

### Metode A: Menempelkan Langsung pada File `.md` (Melalui Konten)
Anda dapat menyisipkan kode `meta tag` tersebut langsung di dalam dokumen artikel atau halaman utama berformat `.md`. 

Agar kode HTML tersebut dapat dieksekusi dengan baik oleh Hugo, gunakan fitur *shortcode* bawaan seperti berikut:

```html
{{< raw >}}
<meta name="google-site-verification" content="KODE_VERIFIKASI_ANDA" />
{{< /raw >}}
```
*Ganti `KODE_VERIFIKASI_ANDA` dengan kode unik yang telah Anda salin dari Google Search Console sebelumnya.*

### Metode B: Menggunakan File HTML di Folder `static` (Sangat Direkomendasikan)
Metode ini jauh lebih bersih karena tidak mencampur kode verifikasi dengan konten artikel.

1. Pada halaman Google Search Console, pilih metode **File HTML** (bukan Tag HTML).
2. Unduh (*download*) file HTML yang disediakan oleh Google (biasanya bernama seperti `google456xyz.html`).
3. Buka direktori proyek Hugo Anda, lalu cari folder bernama **`static`**.
4. Tempatkan file HTML yang telah diunduh tersebut langsung ke dalam folder `static` (Struktur path: `proyek-hugo/static/google456xyz.html`).
5. Lakukan proses *commit* dan *push* repositori Anda ke GitHub.

---

## Langkah 3: Melakukan Konfirmasi Verifikasi

1. Setelah menerapkan Metode A atau Metode B, pastikan Anda telah melakukan **Git Commit** dan **Git Push** ke repositori GitHub Pages Anda.
2. Tunggu sekitar 1 hingga 2 menit agar proses *GitHub Actions* selesai membangun (*build*) ulang website Anda.
3. Kembali ke tab browser **Google Search Console**.
4. Klik tombol **Verifikasi / Verify**.
5. Sistem akan menampilkan notifikasi berwarna hijau yang menyatakan bahwa **Kepemilikan telah diverifikasi**.

---

## Kesimpulan

Website Hugo Anda kini telah resmi terhubung dengan Google Search Console. Langkah selanjutnya yang sangat disarankan adalah mendaftarkan **Sitemap** Anda (pada Hugo biasanya terletak di `https://github.iositemap.xml`) melalui menu *Sitemaps* di Google Search Console untuk mempercepat indeksasi artikel-artikel baru ke depannya.
