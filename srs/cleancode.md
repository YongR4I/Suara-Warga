# Panduan Penulisan Kode (Clean Code)
**Berlaku untuk:** HTML (Tailwind CSS), CSS, JavaScript

Dokumen ini berisi standar penulisan kode untuk memastikan struktur proyek tetap rapi, konsisten, dan mudah dipahami, khususnya dalam pengelolaan *utility classes* dari Tailwind.

## 1. Aturan Umum & Kerapihan
* **Indentasi:** Gunakan **2 spasi** secara konsisten. Jangan gunakan *tab*.
* **Penamaan File:** Gunakan format *kebab-case* (contoh: `index.html`, `app.js`).
* **Komentar Secukupnya:**
  * Tulis kode yang menjelaskan dirinya sendiri (*self-documenting*).
  * Hindari komentar yang mendeskripsikan hal yang sudah jelas dari nama variabel atau *class* Tailwind.
  * Gunakan komentar **hanya** untuk menjelaskan *mengapa* (logika rumit atau trik tata letak tertentu).

## 2. Standar Penulisan HTML & Tailwind
Karena Tailwind menggunakan banyak *class* di HTML, penulisan harus disiplin agar tetap bisa dibaca dengan baik.

* **Gunakan HTML Semantik:** Meskipun pakai Tailwind, jangan gunakan `<div>` untuk semuanya. Tetap gunakan `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, dan `<footer>` sesuai konteks kontennya.
* **Urutan Penulisan Class Tailwind:**
  Tulis *class* secara terstruktur agar mudah dilacak (sangat disarankan menggunakan `prettier-plugin-tailwindcss` agar otomatis). Jika manual, gunakan urutan berikut:
  1. Tata letak & Posisi (*flex, grid, absolute, relative, z-index*)
  2. Dimensi (*w-..., h-...*)
  3. Spasi (*m-..., p-...*)
  4. Tipografi (*text-..., font-..., leading-...*)
  5. Visual & Warna (*bg-..., border-..., shadow-...*)
  6. State & Responsif (*hover:, focus:, md:, lg:*)
* **Kerapihan Class yang Panjang:**
  Jika *class* terlalu panjang (lebih dari 80-100 karakter) dan membuat HTML sulit dibaca, pertimbangkan untuk memecah baris atribut `class` (terutama jika menggunakan *framework* JS) atau ekstrak menjadi komponen utilitas di CSS jika elemen tersebut diulang belasan kali.

## 3. Standar Penulisan CSS (Khusus Tailwind)
* **Maksimalkan `tailwind.config.js`:**
  Jangan tulis warna atau ukuran custom di file CSS biasa. Masukkan semua *custom value* (warna *brand*, font kustom, ukuran spesifik) ke dalam file konfigurasi `tailwind.config.js`.
* **Gunakan `@apply` Secukupnya:**
  Hindari memindahkan semua *class* Tailwind ke dalam file `.css` menggunakan `@apply`. Gunakan `@apply` **hanya** untuk komponen dasar yang benar-benar dipakai berulang kali secara identik (misal: tombol `.btn`, input `.form-input`).
* **Hindari Inline Styles:**
  Jangan pernah menggunakan atribut `style="..."` di HTML. Jika ada nilai yang dinamis, manfaatkan *arbitrary values* bawaan Tailwind (contoh: `bg-[#1a1a1a]` atau `w-[320px]`).

## 4. Standar Penulisan JavaScript
* **Deklarasi Variabel:** Selalu gunakan `const`. Gunakan `let` hanya jika nilai akan berubah. Dilarang menggunakan `var`.
* **Format Penamaan:** Gunakan *camelCase* untuk variabel dan fungsi (contoh: `toggleMenu`, `fetchData`). Awali nama fungsi dengan kata kerja.
* **Manipulasi DOM dengan Tailwind:**
  Saat menggunakan JavaScript untuk memanipulasi tampilan (misal: membuka modal), lakukan dengan menambah/menghapus *class* Tailwind (contoh: `element.classList.toggle('hidden')`), bukan dengan mengubah properti *style* secara langsung.