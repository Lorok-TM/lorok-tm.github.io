+++
title = 'Cheat Sheet: Tabel Lengkap Markdown Murni vs Tag HTML di Hugo'
slug = 'tabel-lengkap-markdown-murni-vs-html-hugo'
date = 2026-09-08T23:55:00+07:00
draft = false
description = 'Daftar tabel referensi lengkap sintaks Markdown murni konversi ke tag HTML biasa di Hugo untuk penulisan artikel yang cepat, rapi, dan aman.'
summary = 'Butuh contekan Markdown untuk Hugo? Ini tabel perbandingan super lengkap sintaks Markdown murni vs tag HTML umum, dari teks dasar hingga tingkat lanjut.'
categories = ['Tutorial', 'Web Development']
tags = ['Hugo', 'Markdown', 'HTML', 'Cheat Sheet']
author = 'Admin'
+++

Saat kita memutuskan untuk menutup gerbang keamanan Hugo dengan menghapus kode `unsafe = true`, maka kita wajib menulis isi artikel menggunakan **Markdown Murni**. Bagi yang terbiasa menggunakan tag HTML, mungkin akan sedikit bingung untuk mencari padanan simbolnya di Markdown.

Jangan khawatir! Artikel ini adalah **Cheat Sheet (contekan resmi)** super lengkap yang menyajikan tabel perbandingan antara sintaks Markdown murni dengan tag HTML umum. 

Silakan simpan (*bookmark*) halaman ini agar Anda bisa menyalinnya kapan saja saat menulis postingan baru di Hugo!

---

## 1. Format Teks Dasar & Struktur Paragraf

Bagian ini berisi format dasar yang paling sering digunakan untuk menyusun anatomi teks di dalam artikel.

| Fungsi Teks | Sintaks Markdown Murni | Padanan Tag HTML | Hasil Tampilan |
| :--- | :--- | :--- | :--- |
| **Judul Utama (H1)** | `# Judul Utama` | `<h1>Judul Utama</h1>` | Huruf paling besar (otomatis) |
| **Sub Judul (H2)** | `## Sub Judul` | `<h2>Sub Judul</h2>` | Ukuran sedang nggo bab |
| **Sub-Sub Judul (H3)** | `### Anak Sub` | `<h3>Anak Sub</h3>` | Ukuran lebih kecil |
| **Teks Tebal (Bold)** | `**Teks Tebal**` | `<strong>Teks</strong>` | **Teks Tebal** |
| **Teks Miring (Italic)** | `*Teks Miring*` | `<em>Teks Miring</em>` | *Teks Miring* |
| **Teks Dicoret (Strikethrough)** | `~~Teks Dicoret~~` | `<del>Teks Dicoret</del>` | ~~Teks Dicoret~~ |
| **Garis Pembatas (HR)** | `---` *(tanda hubung 3x)* | `<hr />` | Garis lurus horizontal |
| **Kutipan (Blockquote)** | `> Isi kutipan Anda` | `<blockquote>Kutipan</blockquote>` | Kothak info menyamping |

---

## 2. Format Tautan (Link) & Media Gambar

Cara menyematkan rujukan link luar atau memasukkan gambar tutorial tanpa menyentuh tag HTML.

| Fungsi Elemen | Sintaks Markdown Murni | Padanan Tag HTML |
| :--- | :--- | :--- |
| **Tautan / Link Aktif** | `[Situs Hugo](https://gohugo.io)` | `<a href="https://gohugo.io">Situs Hugo</a>` |
| **Link Gambar Lokal/Online**| `![Deskripsi](https://link-gambar.com)` | `<img src="foto.png" alt="Deskripsi" />` |
| **Gambar Sekaligus Link** | `[![Alt](foto.png)](https://link.com)` | `<a href="..."><img src="..." /></a>` |
| **Tautan Otomatis** | `<https://github.io>` | `<a href="...">https://lorok-tm...</a>` |

---

## 3. Sistem Baris List (Daftar Berurutan & Poin)

Sintaks untuk membuat urutan langkah tutorial atau daftar item non-sekuensial agar rapi dan tidak pedhot.

| Jenis Daftar | Sintaks Markdown Murni | Padanan Tag HTML |
| :--- | :--- | :--- |
| **Daftar Poin (Bullet)** | `* Item 1`<br>`* Item 2`<br>`* Item 3` | `<ul>`<br>`  <li>Item 1</li>`<br>`  <li>Item 2</li>`<br>`</ul>` |
| **Daftar Angka (Ordered)**| `1. Langkah A`<br>`2. Langkah B`<br>`3. Langkah C` | `<ol>`<br>`  <li>Langkah A</li>`<br>`  <li>Langkah B</li>`</ol> |
| **Daftar Bersarang (Sub)** | `1. Langkah Utama`<br>`   * Sub Langkah` *(spasi 3x)* | Usul bersarang gabungan `<ol>` dan `<ul>` |

---

## 4. Penulisan Kode Blok & Inline Code (Penting untuk Tutorial)

Ini adalah senjata utama blogger tutorial untuk menampilkan skrip kodingan agar terbungkus kotak hitam yang rapi.

| Fungsi Kode | Sintaks Markdown Murni | Padanan Tag HTML |
| :--- | :--- | :--- |
| **Kode di Tengah Kalimat** | Gunakan tanda petik satu miring: \`hugo server\` | `<code>hugo server</code>` |
| **Blok Kode (Satu Paragraf)**| Gunakan pagar petik tiga di awal dan akhir:<br>\`\`\`toml<br>theme = "ananke"<br>\`\`\` | `<pre><code>theme = "ananke"</code></pre>` |

---

## 5. Pembuatan Tabel Data (Struktur Kompleks)

Membuat tabel menggunakan Markdown murni ternyata sangat ringkes tanpa perlu mengetik belasan tag `<tr>` atau `<td>` yang ruwet.

### Sintaks Markdown Murni:
```markdown

| Nama Fitur | Status Keamanan | Efek Samping |
| :--- | :--- | :--- |
| Markdown Murni | 100% Sangat Aman | Tampilan bawaan standar |
| Tag HTML Mentah | Riskan Injeksi | Sangat fleksibel |
```

### Padanan Tag HTML (Sangat Panjang):
```html
<table>
  <thead>
    <tr><th>Nama Fitur</th><th>Status Keamanan</th></tr>
  </thead>
  <tbody>
    <tr><td>Markdown Murni</td><td>100% Sangat Aman</td></tr>
  </tbody>
</table>
```

---

## Kesimpulan

Dengan menguasai tabel contekan di atas, Anda terbukti bisa memproduksi artikel tutorial yang kaya fitur, rapi secara estetika, lan ramah SEO tanpa perlu membuka celah keamanan `unsafe = true` di file `hugo.toml`. Selalu gunakan **Markdown Murni** demi kenyamanan menulis dan keamanan mutlak website Anda!
