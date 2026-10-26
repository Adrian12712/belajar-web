# Jaga Pesisir

**Website Edukasi Konservasi Laut dan Pantai**
SDG 13 (Climate Action) dan SDG 14 (Life Below Water)

Proyek UTS Pemrograman Web — *Responsive Educational Website* (HTML5 dan CSS3, tanpa framework).

---

## Anggota Kelompok

| No | Nama | NIM | Tugas |
|----|------|-----|-------|
| 1 | Artika | 2515091054 | Halaman 1 dan 4 (Beranda dan Rehabilitasi Mangrove) |
| 2 | Dina | 2515091050 | Halaman 3 (Ekosistem dan Keanekaragaman Hayati) |
| 3 | Adrian | 2515091061 | Halaman 5 dan 6 (Aksi, Checklist, Form, dan Kuis) |
| 4 | Morinda Citrifolia | 2515091055 | Halaman 7 (Tentang, Referensi, Dokumentasi, dan Pengujian) |

---

## Deskripsi Website

**Jaga Pesisir** adalah website edukasi interaktif yang mengajak masyarakat memahami ancaman terhadap laut dan pesisir Indonesia, serta apa yang bisa dilakukan untuk menjaganya. Website ini mendukung dua tujuan pembangunan berkelanjutan:

- **SDG 13 (Climate Action):** ekosistem pesisir seperti mangrove menyimpan karbon (*blue carbon*) sehingga berperan dalam menahan laju perubahan iklim.
- **SDG 14 (Life Below Water):** melindungi laut dari pencemaran plastik dan menjaga keanekaragaman hayati bahari.

### Tujuan
1. Meningkatkan kesadaran tentang krisis laut dan pesisir Indonesia.
2. Menyajikan fakta yang bisa ditelusuri ke sumbernya.
3. Mendorong pengunjung untuk melakukan aksi nyata sehari-hari.

### Manfaat
- Pengunjung mendapat ringkasan data yang mudah dipahami, lengkap dengan tautan ke sumber aslinya.
- Kuis dan checklist membantu pengunjung menguji pemahaman dan mulai berkomitmen.

### Sasaran Pengguna
| Pengguna | Kebutuhan |
|----------|-----------|
| Pelajar dan remaja | Memahami ancaman sampah plastik dan pentingnya ekosistem pesisir lewat kuis dan aksi harian |
| Masyarakat umum | Memahami peran mangrove dan terumbu karang bagi iklim |
| Pendidik | Rujukan pendukung pembelajaran lingkungan hidup |

---

## Halaman Website

Website terdiri dari **7 halaman** yang saling terhubung lewat menu navigasi yang sama di setiap halaman.

| No | File | Halaman | Isi utama |
|----|------|---------|-----------|
| 1 | `index.html` | Beranda | Hero berfoto, pengantar "Laut dan Iklim", 5 kartu fakta yang bisa diklik menuju sumbernya, dan video renungan |
| 2 | `artikel.html` | Artikel | Pencemaran laut dan sampah plastik: sumber pencemaran dan infografis lama terurainya sampah |
| 3 | `edukasi.html` | Edukasi | Tiga ekosistem pesisir (terumbu karang, padang lamun, mangrove) dan satwa laut dilindungi |
| 4 | `panduan.html` | Panduan | Rehabilitasi mangrove: karbon biru, tahap penanaman, dan zonasi mangrove |
| 5 | `kuis.html` | Kuis | Kuis interaktif pilihan ganda dengan penjelasan jawaban |
| 6 | `aksi.html` | Aksi | Checklist aksi harian dan form janji Jaga Pesisir |
| 7 | `tentang.html` | Tentang | Tujuan website, tim pengembang, daftar referensi, atribusi aset, dan catatan teknologi |

---

## Teknologi

| Teknologi | Digunakan untuk |
|-----------|-----------------|
| HTML5 | Struktur halaman dengan elemen semantik |
| CSS3 | Warna, tipografi, kartu, dan seluruh tampilan, dalam satu stylesheet eksternal |
| CSS Variables | Satu sumber warna, bayangan, dan radius untuk semua halaman |
| Flexbox | Header, navigasi, dan baris elemen sejajar |
| CSS Grid | Susunan kartu fakta, kartu informasi, dan footer |
| CSS Media Queries | Penyesuaian tampilan di tablet dan smartphone |
| Google Fonts | Font *Plus Jakarta Sans* |
| GitHub Pages | Publikasi website secara online |

Tidak memakai framework CSS, template siap pakai, ataupun JavaScript untuk tampilan.

---

## Penjelasan Implementasi

### 1. Struktur HTML semantik

Setiap halaman memakai kerangka yang sama: `header` untuk judul dan navigasi, `main` untuk isi utama, dan `footer` untuk bagian bawah. Judul utama `h1` hanya ada satu per halaman, lalu dilanjutkan `h2` dan `h3` secara berurutan.

```html
<header class="site-header">
    <div class="container header-inner">
        <a href="index.html" class="brand-logo">Jaga <span>Pesisir</span></a>
        <nav class="main-nav">...</nav>
    </div>
</header>

<main>
    <section id="fakta-section" class="section">...</section>
</main>

<footer class="site-footer">...</footer>
```

**Fungsi:** Elemen semantik memberi tahu browser dan pembaca layar bagian mana yang merupakan navigasi, isi utama, dan penutup, sehingga halaman lebih mudah dibaca dan dipahami mesin pencari.

### 2. CSS eksternal dan CSS Variables

Semua halaman memakai satu file `css/style.css`, dipasang dengan:

```html
<link rel="stylesheet" href="css/style.css">
```

Warna dan ukuran yang dipakai berulang disimpan sebagai variabel di `:root`:

```css
:root {
    --navy-dark: #0f2b46;
    --teal-primary: #00a896;
    --sand-gold: #f4a261;
    --radius-md: 12px;
    --shadow-md: 0 8px 24px rgba(15, 43, 70, 0.1);
}

.stat-card {
    border-radius: var(--radius-md);
    box-shadow: var(--shadow-md);
}
```

**Fungsi:** Perubahan warna atau sudut kartu cukup dilakukan di satu tempat dan langsung berlaku di ketujuh halaman, sehingga tampilan tetap konsisten.

### 3. Navigasi antarhalaman

Menu yang sama dipasang di bagian atas setiap halaman. Halaman yang sedang dibuka diberi class `active`.

```html
<nav class="main-nav">
    <a href="index.html" class="nav-btn">Beranda</a>
    <a href="artikel.html" class="nav-btn">Artikel</a>
    <a href="edukasi.html" class="nav-btn">Edukasi</a>
    <a href="panduan.html" class="nav-btn">Panduan</a>
    <a href="kuis.html" class="nav-btn">Kuis</a>
    <a href="aksi.html" class="nav-btn">Aksi</a>
    <a href="tentang.html" class="nav-btn active">Tentang</a>
</nav>
```

Header dibuat menempel di atas layar saat halaman di-scroll:

```css
.site-header {
    position: sticky;
    top: 0;
    z-index: 1000;
}
```

**Fungsi:** Pengunjung bisa berpindah halaman kapan saja tanpa harus kembali ke atas. Semua tautan memakai nama file relatif, jadi tetap berfungsi di GitHub Pages.

### 4. Flexbox

Flexbox dipakai untuk header: logo di kiri dan menu di kanan, sejajar vertikal.

```css
.header-inner {
    display: flex;
    align-items: center;
    justify-content: space-between;
    height: 72px;
}
```

**Fungsi:** `justify-content: space-between` mendorong logo dan menu ke dua sisi, sedangkan `align-items: center` menjaga keduanya tetap di tengah secara vertikal.

### 5. CSS Grid

Grid dipakai untuk kartu-kartu yang jumlah kolomnya menyesuaikan lebar layar.

```css
.stats-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    gap: 1.5rem;
}
```

Di Beranda, 5 kartu fakta disusun 3 kartu di baris atas dan 2 kartu lebih lebar di baris bawah, memakai grid 6 kolom:

```css
.stats-grid.stats-grid-5 { grid-template-columns: repeat(6, 1fr); }
.stats-grid-5 .stat-card { grid-column: span 2; }
.stats-grid-5 .stat-card:nth-child(n+4) { grid-column: span 3; }
```

**Fungsi:** `auto-fit` dengan `minmax(240px, 1fr)` membuat kolom bertambah atau berkurang otomatis. Pada grid 6 kolom, `span 2` berarti satu kartu memakai 2 kolom (3 kartu per baris), dan `span 3` memakai 3 kolom (2 kartu per baris).

### 6. Media Queries (responsif)

Tampilan diuji pada lebar **1440 px** (desktop), **768 px** (tablet), dan **375 px** (smartphone).

```css
@media (max-width: 768px) {
    .header-inner {
        flex-direction: column;
        height: auto;
        gap: 12px;
    }
    .hero-card { padding: 2.5rem 1.5rem; }
    .section-title { font-size: 1.6rem; }
}

@media (max-width: 900px) {
    .stats-grid.stats-grid-5 { grid-template-columns: repeat(2, 1fr); }
}

@media (max-width: 600px) {
    .stats-grid.stats-grid-5 { grid-template-columns: 1fr; }
}
```

**Fungsi:** Di layar kecil, header menumpuk ke bawah, ukuran huruf judul mengecil, dan kartu fakta berubah dari 3 kolom menjadi 2 kolom, lalu 1 kolom, sehingga tidak ada scroll ke samping dan teks tetap terbaca.

### 7. Gambar dan video responsif

Foto latar hero memakai tag `<img>` yang ditumpuk di belakang teks, lengkap dengan `alt`:

```html
<div class="hero-card">
    <img class="hero-bg" src="hero-pesisir.jpg" alt="Pemandangan pantai dan laut Indonesia">
    <div class="hero-content">...</div>
</div>
```

```css
.hero-bg {
    position: absolute;
    inset: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
}
```

Video YouTube dibungkus kotak berasio 16:9:

```css
.video-responsive-box { aspect-ratio: 16 / 9; }
.video-responsive-box iframe { width: 100%; height: 100%; border: 0; }
```

**Fungsi:** `object-fit: cover` membuat foto memenuhi kotak tanpa gepeng, dan `aspect-ratio: 16 / 9` menjaga bentuk video di semua ukuran layar.

### 8. Kartu fakta yang bisa diklik

Tiap kartu fakta di Beranda adalah satu tautan yang membuka sumbernya di tab baru:

```html
<a class="stat-card stat-link" href="https://..." target="_blank" rel="noopener noreferrer">
    <div class="stat-number">3.455.628 <span>Hektar</span></div>
    <p class="stat-label">Luas mangrove Indonesia...</p>
    <p class="stat-sumber">Sumber: KLH/BPLH (31 Mar 2026) ↗</p>
</a>
```

**Fungsi:** Pengunjung bisa langsung memeriksa asal data. `rel="noopener noreferrer"` mengamankan tab yang dibuka dari halaman ini.

---

## Struktur Folder

```
jaga-pesisir/
|-- index.html          # Beranda
|-- artikel.html        # Artikel (pencemaran laut)
|-- edukasi.html        # Edukasi (ekosistem pesisir)
|-- panduan.html        # Panduan (rehabilitasi mangrove)
|-- kuis.html           # Kuis interaktif
|-- aksi.html           # Aksi (checklist dan form janji)
|-- tentang.html        # Tentang, referensi, dan atribusi
|-- hero-pesisir.jpg    # Foto latar hero di Beranda
|-- css/
|   `-- style.css       # Stylesheet bersama untuk semua halaman
`-- README.md           # Dokumentasi proyek
```

---

## Website dan Repository

| | URL |
|---|---|
| Website (GitHub Pages) | `https://USERNAME.github.io/NAMA-REPOSITORY/` |
| Repository | `https://github.com/USERNAME/NAMA-REPOSITORY` |

---

## Referensi

### Sumber Data dan Konten

| Sumber | Judul | Tahun | Tautan |
|--------|-------|-------|--------|
| KLH / BPLH | RPPEM Nasional, Fondasi Baru Perlindungan Mangrove Indonesia | 2026 | https://kemenlh.go.id/news/detail/rppem-nasional-fondasi-baru-perlindungan-mangrove-indonesia |
| Kompas Lestari | Mendagri RI: Urutan Kelima Negara Penghasil Sampah Terbanyak di Dunia | 2026 | https://lestari.kompas.com/read/2026/02/25/222039086/mendagri-ri-urutan-kelima-negara-penghasil-sampah-terbanyak-di-dunia |
| IPB University | Laut Indonesia Kian Tercemar, Pakar IPB University Kurangi Plastik | 2026 | https://www.ipb.ac.id/news/index/2026/07/laut-indonesia-kian-tercemar-pakar-ipb-university-kurangi-plastik-perkuat-kolaborasi-selamatkan-ekosistem/ |
| WWF Indonesia | Diplomasi Biru Indonesia di Konferensi Laut Dunia UNOC3 | 2025 | https://www.wwf.id/id/blog/diplomasi-biru-indonesia-di-konferensi-laut-dunia-unoc3-upaya-global-bagi-terumbu-karang |
| Mongabay Indonesia | Sembilan Tahun Peringati Hari Terumbu Karang Dunia, Bagaimana Kondisi di Indonesia? | 2018 | https://mongabay.co.id/2018/05/09/sembilan-tahun-peringati-hari-terumbu-karang-dunia-bagaimana-kondisi-di-indonesia/ |
