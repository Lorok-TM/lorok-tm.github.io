+++
title = 'Cara Membuat Postingan Baru dengan Benar dan Aman di Astro'
slug = 'cara-membuat-postingan-baru-benar-aman-astro'
date = 2026-09-08T23:59:45+07:00
draft = false
description = 'Panduan lengkap cara membuat artikel atau postingan baru di framework Astro menggunakan Content Collections yang aman, rapi, dan ramah SEO.'
summary = 'Bagaimana cara menambahkan artikel baru di Astro? Pelajari struktur folder src/content, aturan Front Matter, dan cara menulis menggunakan Markdown atau MDX.'
categories = ['Tutorial', 'Web Development']
tags = ['Astro', 'Content Collections', 'Markdown', 'MDX']
author = 'Admin'
+++

... *(Langkah 1 & 2 panggah padha)* ...

## Langkah 3: Mengisi Front Matter di Bagian Atas

Sama seperti Hugo, Astro menggunakan Front Matter di bagian paling atas. Namun, di dalam proyek Astro, Anda **wajib menggunakan tanda hubung tiga (`---`)** sebagai pembatasnya karena Astro menggunakan format standar YAML.

Berikut adalah contoh Front Matter standar Astro yang komplit dan aman untuk SEO:

```yaml
---
title: 'Judul Artikel Astro Anda yang Menarik'
slug: 'kustom-slug-pilihan-anda'
pubDate: 2026-09-08
draft: false
description: 'Deskripsi pendek isi artikel untuk kebutuhan pencarian Google.'
tags: ['Astro', 'Tutorial']
author: 'Admin'
---
```

### Aturan Keamanan Front Matter Astro:
1. **Validasi Skema (Schema):** Astro akan mengecek apakah data yang Anda masukkan sudah sesuai tipe datanya dengan yang diatur di `src/content/config.ts`. Jika Anda salah memasukkan format tanggal, Astro akan langsung memberikan peringatan error saat di-build.
2. **Kustom `slug`:** Secara bawaan, Astro akan membuat URL berdasarkan nama file. Namun, dengan memasang parameter `slug: '...'` di atas, Anda bisa memotong URL agar lebih ringkas dan nempel langsung di domain utama Vercel Anda.

... *(Seteruse panggah padha)* ...
