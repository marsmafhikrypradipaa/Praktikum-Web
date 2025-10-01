# Analisis Kode Instagram Profile Clone

Repositori ini berisi analisis singkat tentang pendekatan responsif dan skalabilitas dari kode kloning halaman profil Instagram yang dibuat dengan Bootstrap 5.

---

### 1. Konfigurasi Grid Postingan (`col-*`)

Sistem grid digunakan untuk memastikan tata letak postingan optimal di semua ukuran layar (desain responsif).

- `col-12`: **1 kolom** di layar ekstra kecil (ponsel vertikal).
- `col-sm-6`: **2 kolom** di layar kecil (ponsel horizontal).
- `col-md-4`: **3 kolom** di layar medium (tablet).
- `col-lg-3`: **4 kolom** di layar besar (desktop).

**Tujuannya**: Mengadaptasi jumlah kolom secara dinamis agar konten tetap mudah dilihat sesuai lebar perangkat.

---

### 2. Penempatan Tombol "Follow" di Mobile

Tombol "Follow" tetap mudah dijangkau di perangkat mobile melalui dua pendekatan utama:

1.  **Alur HTML Alami**: Di mobile, elemen ditampilkan secara vertikal sesuai urutan di kode HTML. Tombol ditempatkan tepat setelah nama pengguna, membuatnya berada di posisi fokus yang mudah dijangkau.
2.  **Utilitas Flexbox**: Di layar yang lebih besar (`md` ke atas), kelas seperti `flex-md-row` dan `order-md-*` digunakan untuk menata ulang elemen secara horizontal tanpa mengubah struktur HTML.

---

### 3. Skalabilitas untuk 50+ Postingan

Grid Bootstrap **secara visual siap** untuk menangani 50+ postingan. Namun, akan muncul masalah **kinerja** dan **UX**.

#### Masalah Potensial:

- **Kinerja Lambat**: Memuat 50+ gambar sekaligus akan memperlambat waktu muat halaman secara drastis.
- **UX Buruk**: Halaman menjadi terlalu panjang untuk di-scroll oleh pengguna.

#### Solusi:

- **Lazy Loading**: Gunakan atribut `loading="lazy"` pada tag `<img>` untuk menunda pemuatan gambar hingga pengguna scroll ke dekatnya.
- **Infinite Scroll / Paginasi**: Muat postingan secara bertahap (misalnya per 12 item) saat pengguna scroll ke bawah (Infinite Scroll) atau mengklik halaman berikutnya (Paginasi).

Struktur grid yang ada sudah mendukung implementasi solusi ini dengan sempurna.
