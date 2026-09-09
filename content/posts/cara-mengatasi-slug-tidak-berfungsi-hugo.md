+++
title = 'Cara Mengatasi Slug Front Matter Tidak Berfungsi di Hugo'
slug = 'cara-mengatasi-slug-tidak-berfungsi-hugo'
date = 2026-09-08T11:00:00+07:00
draft = false
description = 'Panduan mengatasi masalah kustom slug di Front Matter Hugo yang tidak terbaca dan selalu mengikuti judul (title) bawaan tema.'
summary = 'Mengapa kustom slug di Hugo tidak berfungsi? Pelajari cara mengaktifkan konfigurasi permalinks di hugo.toml agar URL website sesuai keinginan Anda.'
categories = ['Tutorial', 'Web Development']
tags = ['Hugo', 'Slug', 'SEO', 'Troubleshooting']
author = 'Admin'
+++

Saat membuat postingan baru di Hugo, kita sering kali menambahkan parameter `slug` di bagean Front Matter (atas) agar URL artikel lebih ringkas dan ramah SEO. Namun, terkadang kustom `slug` tersebut **tidak dianggap oleh tema** dan Hugo tetap mencetak URL berdasarkan `title` (judul) artikel.

Jika Anda mengalami masalah ini pada situs Hugo Anda, jangan panik. Masalah ini terjadi karena tema yang Anda gunakan belum dikonfigurasi untuk membaca kustom slug secara otomatis.

Berikut adalah cara mudah untuk mengatasinya tanpa perlu membongkar kode tema.

---

## Solusi: Menambahkan Pengaturan Permalinks di `hugo.toml`

Cara paling ampuh dan permanen untuk memaksa Hugo membaca kustom `slug` adalah dengan menambah sedikit konfigurasi pada file pengaturan utama Anda, yaitu **`hugo.toml`** (atau `hugo.yaml`).

1. Buka proyek Hugo Anda menggunakan **VS Code**.
2. Cari dan buka file bernama **`hugo.toml`** yang ada di folder paling luar (root).
3. Salin dan tempel kode berikut di bagian paling bawah file tersebut:

```toml
[permalinks]
  posts = '/posts/:slug/'
```

> **Catatan:** Jika folder tempat Anda menyimpan artikel bukan bernama `posts` (misalnya bernama `blog` atau `artikel`), silakan ganti tulisan `posts` di atas sesuai dengan nama folder Anda (contoh: `blog = '/blog/:slug/'`).

---

## Bagaimana Cara Kerja Pengaturan Ini?

Secara standar, Hugo akan membaca struktur URL sebagai `/:section/:title/` (mengikuti judul). 

Dengan menambahkan baris `posts = '/posts/:slug/'`, kita memberikan instruksi tegas kepada Hugo:
* Jika artikel memiliki parameter `slug` di Front Matter-nya, maka **gunakan isi slug tersebut** sebagai URL.
* Jika artikel tidak memiliki parameter `slug`, Hugo akan otomatis jatuh kembali (*fallback*) menggunakan judul sebagai URL-nya.

---

## Langkah Terakhir: Simpan dan Deploy

Setelah mengubah file `hugo.toml`:
1. Simpan perubahan file tersebut.
2. Jalankan perintah `hugo server` di terminal komputer untuk memastikan URL di lokal sudah berubah sesuai kustom slug Anda.
3. Jika sudah beres, lakukan `git add`, `git commit`, dan `git push` ke GitHub Anda.

Tunggu beberapa saat sampai GitHub Pages selesai memperbarui situs Anda. Sekarang, URL postingan Anda dijamin akan langsung berubah rapi mengikuti kustom `slug` tanpa mbulet lagi!
