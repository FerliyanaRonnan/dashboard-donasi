# Dashboard Donasi CRM JLF Performance Analytics

Dashboard analitik interaktif berbasis web (single-file HTML) untuk memantau performa program donasi/fundraising CRM JLF sepanjang tahun 2025. Dibangun dari hasil data cleaning & EDA atas dataset transaksi donasi, lalu divisualisasikan dalam satu halaman ringkas yang siap dibuka di browser tanpa instalasi apa pun.

## ✨ Fitur

- **KPI Ringkas** = Total donasi, jumlah transaksi, jumlah donatur, donatur baru, repeat rate, dan rata-rata donasi dalam satu baris kartu.
- **Performa per Program** = Bar chart total donasi per program (Wakaf Al-Qur'an, Qurban, Zakat, dll.) beserta tabel perubahan nominal semester 1 → semester 2 (Δ%).
- **Perilaku & Kontribusi Donatur** = Donut chart kontribusi per kategori donatur (Premium, Repeat, Pasif, Baru) dan tabel Top 10 donatur berdasarkan total donasi.
- **Tren Musiman & Pola Transaksi** = Line chart tren donasi bulanan (Jan–Des 2025) dan bar chart distribusi transaksi per hari dalam seminggu.
- **Sebaran Geografis** = Horizontal bar chart total donasi per wilayah (10 kota, dipimpin Surabaya).
- Desain gelap (dark mode) dengan aksen cyan/violet, tipografi Space Grotesk + Inter + JetBrains Mono, dan layout yang responsif untuk mobile.

## 🗂️ Struktur Proyek

```
dashboard-donasi/
├── index.html   # Seluruh dashboard (HTML, CSS, JS, dan data) dalam satu file
└── README.md    # Dokumentasi proyek ini
```

## 🚀 Cara Menjalankan

Tidak perlu build tool atau server khusus cukup buka file HTML di browser:

1. Clone atau unduh repo ini.
2. Buka `index.html` langsung di browser (double-click), **atau**
3. Jalankan local server sederhana lalu akses via `localhost`:
   ```bash
   python3 -m http.server 8000
   # lalu buka http://localhost:8000 di browser
   ```

> Membutuhkan koneksi internet karena font (Google Fonts) dan library chart (Chart.js via CDN) dimuat dari CDN eksternal.

## 🧱 Teknologi

| Komponen | Teknologi |
|---|---|
| Struktur & Styling | HTML5, CSS3 (custom properties, grid, gradient) |
| Visualisasi Data | [Chart.js 4.4.1](https://www.chartjs.org/) via CDN |
| Font | Space Grotesk, Inter, JetBrains Mono (Google Fonts) |
| Data | JSON statis tertanam langsung di dalam `<script>` (`index.html`) |

## 📊 Sumber Data

Data merupakan hasil olahan dari **500 transaksi donasi** dari **186 donatur unik** di **10 wilayah**, mencakup periode **Januari–Desember 2025**. Data telah melalui proses *data cleaning* dan *exploratory data analysis (EDA)* sebelum diringkas menjadi metrik-metrik yang ditampilkan pada dashboard (total per program, kategori donatur, tren bulanan, pola harian, dan sebaran wilayah).

## ✏️ Kustomisasi

Karena seluruh data tersimpan sebagai satu objek JavaScript (variabel `D`) di bagian bawah `index.html`, dashboard dapat digunakan kembali untuk dataset lain dengan mengganti isi objek tersebut mengikuti struktur yang sama (`months`, `monthly_total`, `programs`, `program_total`, `kategori`, `top10`, `semester`, `wilayah`, `wilayah_total`, `kpi`, dll.) tanpa perlu mengubah kode chart maupun styling.

## 📄 Lisensi

https://dashboard-donasi.vercel.app/
