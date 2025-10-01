# Kloning Profil Instagram dengan Tailwind CSS

Proyek ini adalah halaman profil Instagram yang dibuat dengan HTML dan Tailwind CSS untuk menunjukkan pembuatan layout yang cepat dan responsif.

---

## Penjelasan Desain

### 1. Struktur Grid (`grid-cols`) 📐

- **Mobile (Default):** Menggunakan **1 kolom** (`grid-cols-1`). Ini membuat semua konten tersusun vertikal ke bawah, sehingga nyaman untuk di-scroll di layar HP yang sempit.
- **Tablet/Desktop (`md:` & `lg:`):** Berubah menjadi **3 atau 4 kolom** (`md:grid-cols-3`, `lg:grid-cols-4`). Tujuannya adalah untuk memanfaatkan lebar layar yang lebih besar agar tampilan tidak kosong dan lebih efisien.

### 2. Layout Responsif untuk Mobile 📱

Pendekatan _mobile-first_ di sini sangat bergantung pada _prefix_ `md:` dari Tailwind.

- **`flex md:hidden`**: Elemen ini **hanya tampil di mobile** (contoh: footer navigasi dan statistik versi mobile).
- **`hidden md:flex`**: Elemen ini **disembunyikan di mobile** dan baru muncul di ukuran tablet ke atas (contoh: statistik di samping foto profil).

Dengan cara ini, kita bisa menyajikan dua versi layout yang berbeda dalam satu file HTML tanpa duplikasi yang rumit.

### 3. Pendekatan Styling: Utility vs. Component ✍️

Proyek ini sepenuhnya menggunakan _utility classes_. Ini adalah sebuah pilihan dengan pertimbangan:

- **Banyak Utility (Cara di Proyek Ini):**

  - **✅ Kelebihan:** Sangat **cepat** untuk styling langsung di HTML.
  - **❌ Kekurangan:** Kode HTML jadi terlihat **ramai dan "kotor"** karena penuh dengan class.

- **Component CSS (Alternatif):**
  - **✅ Kelebihan:** HTML menjadi **jauh lebih bersih** dan mudah dibaca (misal: `<button class="btn-primary">`).
  - **❌ Kekurangan:** Membutuhkan **setup awal** di file CSS terpisah, sehingga sedikit lebih lambat untuk memulai.
