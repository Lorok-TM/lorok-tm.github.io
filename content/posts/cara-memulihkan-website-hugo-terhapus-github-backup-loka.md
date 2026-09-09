+++
title = 'Cara Memulihkan Website Hugo yang Terhapus di GitHub Menggunakan Backup Lokal'
slug = 'cara-memulihkan-website-hugo-terhapus-github-backup-lokal'
date = 2026-09-08T23:59:59+07:00
draft = false
description = 'Panduan darurat cara mengembalikan website Hugo yang tidak sengaja terhapus di GitHub secara utuh menggunakan file backup .zip dari komputer lokal.'
summary = 'Bagaimana jika repositori GitHub Anda terhapus? Jangan panik, pelajari cara mudah restore website Hugo Anda secara instan menggunakan backup lokal.'
categories = ['Tutorial', 'Web Development']
tags = ['Git', 'GitHub', 'Backup', 'Restore Website']
author = 'Admin'
+++

Dalam dunia pengelolaan website berbasis *Static Site Generator* (SSG), skenario terburuk seperti akun GitHub diretas atau repositori utama terhapus secara tidak sengaja adalah ancaman yang nyata. Bagi pemula, kejadian ini pasti akan memicu kepanikan luar biasa.

Namun, jika Anda adalah seorang developer yang cerdas dan sudah memiliki file cadangan (.zip) dari folder lokal komputer yang berisi folder rahasia `.git`, Anda sebenarnya memegang kendali penuh. Anda bisa menghidupkan kembali website Anda secara instan tanpa perlu melakukan konfigurasi dari nol lagi.

Berikut adalah panduan langkah demi langkah cara melakukan *restore* website Hugo yang terhapus di GitHub menggunakan *Ultimate Backup* lokal Anda.

---

## Syarat Utama Sebelum Memulai

Sebelum melakukan pemulihan, pastikan file cadangan `.zip` yang Anda miliki diambil langsung dari folder komputer lokal dengan kondisi fitur *Show Hidden Files* aktif. Artinya, folder rahasia bernama **`.git`** wajib terbungkus di dalam file `.zip` tersebut karena folder itulah yang menyimpan "nyawa" koneksi ke server.

---

## Langkah 1: Membuat Repositori Kosong Baru di GitHub

1. Masuk ke akun GitHub Anda.
2. Buat repositori baru (*New Repository*).
3. **Aturan Mutlak:** Beri nama repositori tersebut dengan **nama yang sama persis** seperti repositori Anda yang terhapus (contoh: `username-githubmu.github.io`).
4. Setel visibilitas menjadi **Public**, jangan centang opsi *Add a README file* atau *Add .gitignore* (biarkan repositori bener-bener kosong melompong bernilai 0).
5. Klik **Create repository**.

---

## Langkah 2: Membuka Folder Backup di VS Code

1. Ekstrak file `.zip` cadangan lokal Anda ke dalam komputer.
2. Buka folder hasil ekstrak tersebut menggunakan aplikasi **VS Code**.
3. Buka **Terminal** di dalam VS Code (gunakan menu *Terminal -> New Terminal*).

Karena folder rahasia `.git` Anda masih utuh di dalam folder tersebut, sistem Git lokal sebenarnya sudah otomatis mengenali alamat rute GitHub Anda yang lama.

---

## Langkah 3: Mengirim Pasukan Kode Menggunakan Perintah Paksaan (`--force`)

Untuk memaksa server GitHub yang baru dan kosong agar mau menerima seluruh barisan kode lama Anda, jalankan tiga perintah Git berikut secara berurutan di terminal VS Code:

```bash
git add .
git commit -m "membangun ulang situs total dari backup lokal"
git push origin main --force
```

> **Mengapa Harus Menggunakan `--force`?** Perintah `--force` adalah instruksi tegas untuk memberi tahu GitHub bahwa kita sengaja menimpa repositori kosong yang baru dengan seluruh sejarah kodingan lama kita tanpa perlu melakukan proses sinkronisasi ulang.

---

## Langkah 4: Aktifkan GitHub Actions Kembali

Setelah proses push sukses, langkah terakhir Anda tinggal masuk ke menu **Settings** -> **Pages** di halaman repositori GitHub baru Anda, lalu ubah opsi *Source* menjadi **GitHub Actions**.

Tunggu proses *building* selama 1-2 menit. Begitu selesai, website Anda dijamin akan langsung **ONLINE KEMBALI** secara utuh, lengkap dengan seluruh artikel tutorial Anda tanpa ada satu pun data yang hilang!

---

## Kesimpulan

Menjaga file backup lokal yang komplit beserta folder `.git` adalah investasi keamanan terbaik bagi seorang pemilik website. Melalui kombinasi perintah Git yang tepat, skenario kiamat seperti hilangnya repositori di GitHub bisa diatasi hanya dalam hitungan menit. Selalu amankan data Anda dan salam anti-mbledos!
