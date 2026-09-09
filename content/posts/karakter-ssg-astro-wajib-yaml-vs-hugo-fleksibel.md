+++
title = 'Karakter SSG: Astro Wajib Hubung (---) vs Hugo yang Sakti Fleksibel (+++)'
slug = 'karakter-ssg-astro-wajib-yaml-vs-hugo-fleksibel'
date = 2026-09-08T23:59:55+07:00
draft = false
description = 'Perbandingan karakter Front Matter antara Astro yang kaku wajib menggunakan format YAML dan Hugo yang fleksibel otomatis mendukung TOML maupun YAML.'
summary = 'Mengapa Astro sangat kaku dengan tanda --- sedangkan Hugo bisa melahap +++ dan --- sekaligus? Pelajari sistem prioritas Front Matter di kedua framework.'
categories = ['Tutorial', 'Web Development']
tags = ['Hugo', 'Astro', 'YAML', 'TOML', 'Front Matter']
author = 'Admin'
+++

Dalam dunia *Static Site Generator* (SSG) modern, kita mengenal dua raksasa framework yang super cepat, yaitu **Hugo** dan **Astro**. Meskipun keduanya sama-sama menggunakan file Markdown (`.md`) untuk menyusun artikel, ternyata keduanya memiliki karakter dan sifat yang bertolak belakang dalam membaca bagian **Front Matter** (identitas atas artikel).

Bagi Anda yang mengelola dua framework ini sekaligus, memahami sifat "Kaku" dari Astro dan sifat "Sakti Fleksibel" dari Hugo akan menyelamatkan website Anda dari risiko error mbledos saat proses deploy.

---

## 1. Karakter Astro: Disiplin Kaku & Wajib Hukumnya YAML (`---`)

Astro adalah framework modern yang sangat disiplin dan memiliki aturan main yang kaku. Dalam membaca Front Matter, Astro hanya mengenal satu bahasa, yaitu **YAML**.

* **Aturan Mutlak:** Anda **WAJIB HUKUMNYA** menggunakan tanda pembatas hubung tiga (**`---`**) di bagian atas artikel.
* **Konsekuensi:** Jika Anda nekat memasang tanda plus (**`+++`** atau format TOML) di dalam proyek Astro Anda, sistem detektor Astro tidak akan mengenalinya. Hasilnya, proses pembangunan (*build*) di server Vercel dijamin akan **langsung mbledos alias error total**.

---

## 2. Karakter Hugo: Sakti Gawan Bayi, Lahap (`+++`) Maupun (`---`)

Berbanding terbalik dengan Astro, Hugo adalah pendekar lama yang sudah dibekali dengan "tameng" fleksibilitas yang luar biasa tinggi sejak dari pabriknya. Tanpa perlu kode tambahan atau plugin apapun, Hugo bisa melahap dua format sekaligus.

Berikut adalah sistem prioritas dan cara kerja Hugo di balik layar saat membaca artikel Anda:

### Prioritas No. 1: Format TOML (`+++`)
Format ini menggunakan tanda pembatas plus (`+++`) dan tanda sama dengan (`=`) untuk mengisi data. Ini adalah **anak emas** atau format bawaan asli (*native*) Hugo karena bahasa dasarnya sangat sinkron dengan core sistem Hugo. Proses render format ini adalah yang paling cepat.

### Tameng Otomatis: Format YAML (`---`)
Meskipun bukan anak emas, Hugo **sudah siap menandingi dan menerima** format YAML (`---`) secara otomatis. Ketika Anda memasukkan artikel berpembatas `---`, detektor bawaan Hugo akan langsung membaca dan menyesuaikan diri tanpa memicu error sedikit pun.

---

## Tabel Perbandingan Karakter Front Matter

| Framework SSG | Format YAML (`---`) | Format TOML (`+++`) | Sifat Karakter |
| :--- | :--- | :--- | :--- |
| **Astro** 🚀 | **BISA (Wajib)** | **ORA BISA ❌ (Error)** | Kaku, Disiplin, Modern |
| **Hugo** 🐹 | **BISA** | **BISA (Prioritas 1)** | Fleksibel, Sakti Gawan Bayi |

---

## Kesimpulan & Jalan Ninja Terbaik

Melihat adanya perbedaan karakter ini, ada satu strategi cerdik atau **jalan ninja** paling aman bagi Anda yang mengelola situs Hugo dan Astro sekaligus agar tidak pusing:

> **Gunakan format YAML (`---`) untuk semua file konten Anda, baik di Hugo maupun di Astro.**

Dengan memilih format `---`, artikel Anda akan otomatis lolos aturan ketat di Astro, dan di saat yang sama, sifat fleksibel Hugo akan tetap melahap artikel tersebut dengan aman dan lancar tanpa butuh konfigurasi edit tambahan. Selamat mencoba strategi cerdik ini!
