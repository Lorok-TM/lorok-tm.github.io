+++
title = 'Cara Cepat Membuat Situs Astro Gratis via GitHub dan Vercel (Langsung Online!)'
slug = 'cara-cepat-membuat-situs-astro-gratis'
date = 2026-09-08T02:24:18+07:00
draft = false
description = 'Panduan lengkap cara membuat website cepat dan gratis menggunakan framework Astro, GitHub, dan Vercel hanya dalam hitungan menit untuk pemula.'
summary = 'Membuat situs web yang cepat dan modern tidak harus mahal atau ribet. Pelajari cara otomatis deploy Astro ke Vercel lewat GitHub gratis.'
categories = ['Tutorial', 'Web Development']
tags = ['Astro', 'Vercel', 'GitHub', 'Website Gratis']
author = 'Admin'
+++

Membuat situs web yang cepat dan modern tidak harus mahal atau ribet. Dengan mengombinasikan **Astro** (framework web super cepat), **GitHub** (tempat menyimpan kode), dan **Vercel** (layanan hosting gratis), Anda bisa membuat situs web yang langsung online hanya dalam hitungan menit tanpa modal sepeser pun.

Tutorial ini cocok untuk pemula yang ingin memulai dari nol dengan metode otomatis yang paling cepat.

---

## Persiapan Awal
Sebelum mulai, pastikan Anda sudah memiliki dua akun gratis ini:
* Akun **GitHub** (untuk menyimpan proyek Anda secara online).
* Akun **Vercel** (bisa langsung daftar/login menggunakan akun GitHub Anda).

---

## Langkah 1: Membuat Proyek Astro Otomatis di GitHub
Cara tercepat tanpa perlu mengetik perintah di komputer adalah dengan memanfaatkan template resmi dari Astro yang bisa langsung disalin ke akun GitHub Anda.

1. Buka browser dan masuk ke halaman template resmi Astro di GitHub: **[astro.new](https://astro.new)**.
2. Pilih template **"Just the Basics"** atau template blog yang Anda sukai.
3. Klik tombol **"Open in GitHub"** (Anda akan diarahkan untuk membuat repositori baru berdasarkan template tersebut).
4. Beri nama repositori Anda (misalnya: `astroku`).
5. Setel visibilitasnya menjadi **Public** (agar nanti bisa dibaca oleh Vercel dan mesin pencari).
6. Klik **Create repository from template**. Sekarang, semua kode dasar Astro sudah aman berada di akun GitHub Anda.

## Langkah 2: Menghubungkan Proyek ke Vercel (Proses Deploy)
Setelah kodenya ada di GitHub, kita tinggal menyambungkannya ke Vercel agar situs web tersebut bisa diakses oleh semua orang di internet.

1. Buka dashboard **[Vercel](https://vercel.com)** dan login menggunakan akun GitHub Anda.
2. Klik tombol **"Add New..."** lalu pilih **"Project"**.
3. Di bagian *Import Git Repository*, Anda akan melihat daftar repositori GitHub Anda. Cari repositori `astroku` yang baru saja dibuat, lalu klik **"Import"**.
4. Pada halaman konfigurasi (*Configure Project*), Vercel secara otomatis akan mendeteksi bahwa proyek Anda menggunakan **Astro**. Jadi, Anda **tidak perlu mengubah pengaturan apapun** (biarkan *Build and Output Settings* dalam kondisi default).
5. Klik tombol **"Deploy"**.
6. Tunggu proses pembuatan (*building*) sekitar 1–2 menit. Jika sudah selesai, Anda akan melihat animasi kembang api dan tulisan **"Congratulations!"**.

Situs Astro Anda sekarang sudah online! Vercel akan memberikan domain gratis dengan format `nama-proyek.vercel.app` (contoh: `astroku.vercel.app`).

## Langkah 3: Cara Update Konten neng Komputer (Lokal)
Jika Anda ingin mengubah tampilan atau menambah artikel dari komputer sendiri:

1. *Clone* repositori GitHub tadi ke komputer Anda menggunakan perintah:
   ```bash
   git clone https://github.com
   ```
2. Buka folder tersebut menggunakan aplikasi teks editor seperti **VS Code**.
3. Lakukan perubahan kode atau tambah artikel baru di dalam folder `src/`.
4. Setelah selesai, simpan dan kirim kembali ke GitHub dengan perintah Git standar (`git add`, `git commit`, `git push`).
5. **Kelebihan Vercel:** Setiap kali Anda melakukan `git push` ke GitHub, Vercel akan otomatis memperbarui situs online Anda dalam beberapa detik secara otomatis!

---

## Kesimpulan
Membuat situs web modern yang ramah SEO sekarang sangat mudah berkat integrasi Astro, GitHub, dan Vercel. Anda tidak perlu pusing memikirkan biaya sewa hosting atau konfigurasi server yang rumit. Cukup fokus pada pengisian konten dan optimasi desain agar situs Anda semakin dilirik oleh pengunjung.

Selamat mencoba, dan semoga sukses membangun website impian Anda!
