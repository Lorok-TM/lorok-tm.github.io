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

Setelah sebelumnya kita membahas cara membuat postingan baru di Hugo, sekarang saatnya kita berkenalan dengan saudara lakonnya, yaitu **Astro**. Sebagai framework web modern yang super cepat, Astro memiliki pendekatan yang sedikit berbeda namun sangat aman dalam mengelola artikel, yaitu menggunakan fitur **Content Collections**.

Dengan metode yang benar, artikel Anda tidak hanya rapi secara struktur kode dan ramah SEO, tetapi juga terhindar dari risiko error saat proses pembangunan (*build*) di Vercel.

Berikut adalah panduan lengkap cara membuat postingan baru di Astro dari nol dengan benar dan aman.

---

## Langkah 1: Memahami Struktur Folder Artikel di Astro

Jika di Hugo artikel disimpan di folder `content/posts/`, maka di dalam proyek Astro (`astroku`), artikel masa kini idealnya disimpan di dalam folder **Content Collections**. 

Struktur foldernya di komputer lokal Anda akan terlihat seperti ini:
```text
astroku/
├── src/
│   ├── content/
│   │   └── blog/  <-- Tempat Anda menaruh file artikel
│   │       ├── artikel-pertama.md
│   │       └── tutorial-kedua.mdx
```
> **Catatan:** Anda bebas menamai folder di dalam `src/content/` tersebut (misalnya `blog`, `posts`, atau `artikel`), namun pastikan nama folder tersebut sudah didaftarkan di file konfigurasi `src/content/config.ts`.

---

## Langkah 2: Membuat File Konten (`.md` atau `.mdx`)

Di dalam folder koleksi tersebut (misalnya folder `blog`), buat file baru dengan huruf kecil semua dan gunakan tanda hubung (`-`) sebagai pemisah, contohnya:  
`cara-membuat-postingan-baru-benar-aman-astro.md`

Astro secara bawaan mendukung dua format:
* Gunakan **`.md`** jika artikel Anda hanya berisi tulisan tutorial dan gambar pasif (sangat direkomendasikan karena ringan).
* Gunakan **`.mdx`** jika di tengah-tengah artikel Anda ingin menyisipkan komponen interaktif buatan sendiri (seperti tombol interaktif atau kalkulator).

---

## Langkah 3: Mengisi Front Matter di Bagian Atas

Berbeda dengan Hugo yang super fleksibel, di dalam proyek Astro Anda **WAJIB HUKUMNYA** menggunakan Front Matter yang diapit oleh tanda hubung tiga (`---`) atau format YAML. Ingat, Astro sama sekali tidak mendukung format tanda plus (`+++` atau TOML) untuk file kontennya. Jika Anda nekat menggunakan `+++`, proses build di Vercel dijamin akan langsung mbledos (error).

Berikut adalah contoh struktur Front Matter standar Astro yang komplit, aman, dan sudah lolos validasi skema SEO:

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

### Aturan Ketat Front Matter Astro:
1. **Validasi Skema (Schema):** Astro akan memverifikasi apakah data yang Anda masukkan (seperti `title` atau `pubDate`) sudah sesuai dengan aturan yang didaftarkan pada file `src/content/config.ts`. Salah mengetik format atau tipe data akan membuat web gagal di-deploy.
2. **Kustom `slug`:** Secara default, Astro mencetak URL berdasarkan nama file `.md` Anda. Dengan memasang kustom `slug: '...'` di atas, Anda bisa memotong URL agar langsung nempel rapi di belakang domain utama Vercel Anda tanpa embel-embel nama folder yang panjang.

---

## Langkah 4: Menulis Isi Konten dan Proses Deploy

Tulis isi artikel Anda tepat di bawah baris penutup Front Matter menggunakan simbol Markdown murni. Berbeda dengan Hugo, Astro **secara bawaan sudah aman** dalam merender konten teks, jadi Anda tidak perlu pusing memikirkan sakelar keamanan seperti *unsafe HTML*.

Setelah selesai menulis di komputer lokal:
1. Simpan file Anda.
2. Lakukan perintah Git standar di terminal:
   ```bash
   git add .
   git commit -m "menambah artikel tutorial astro"
   git push origin main
   ```
3. **Kelebihan Vercel:** Begitu Anda melakukan `git push`, server Vercel akan otomatis mendeteksi, membaca koleksi konten Astro Anda, mendeteksi kustom slug, dan memperbarui situs online Anda (`astroku.vercel.app`) dalam hitungan detik!

---

## Kesimpulan

Membuat postingan baru di Astro memberikan rasa aman ekstra berkat fitur **Content Collections** yang menjaga agar struktur data artikel tidak berantakan. Cukup pastikan penempatan file berada di folder `src/content/`, isi Front Matter dengan teliti, dan biarkan Vercel bekerja otomatis menyebarkan tulisan bermanfaat Anda ke internet. Selamat mencoba!
