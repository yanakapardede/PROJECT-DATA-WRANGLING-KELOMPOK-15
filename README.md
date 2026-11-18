# Analisis Pengaruh Curah Hujan dan Inflasi terhadap Harga Bahan Pokok di Pulau Jawa Tahun 2024

**Proyek Data Wrangling - Kelompok 15**

| Nama | Institusi |
|------|-----------|
| Shafa Fatimah Az Zahra | Universitas Negeri Jakarta |
| Yanaka Sofia Pardede | Universitas Negeri Surabaya |
| Putri Sofiyatus Salwa | Universitas Negeri Surabaya |

Dosen pengampu: Ulfa Siti Nuraini, S.Stat., M.Stat.

---

## Deskripsi

Proyek ini mengintegrasikan, membersihkan, dan mengeksplorasi data curah hujan, inflasi pangan, dan harga bahan pokok di enam provinsi Pulau Jawa sepanjang tahun 2024. Hasilnya berupa dataset bersih yang siap digunakan untuk analisis lanjutan.

Penjelasan lengkap tersedia pada laporan proyek (lihat folder `docs/`).

## Sumber Data

| Sumber | Data | Format Asal |
|--------|------|-------------|
| BMKG | Curah hujan harian | Excel (.xlsx) |
| BPS | Inflasi bulanan subkelompok Makanan, Minuman, dan Tembakau | CSV |
| PIHPS | Harga harian bahan pokok per komoditas | Excel (.xlsx) |

## Cakupan Data

- **Periode:** Januari - Desember 2024
- **Provinsi:** Banten, DKI Jakarta, Jawa Barat, Jawa Tengah, DI Yogyakarta, Jawa Timur
- **Komoditas (10):** bawang merah, bawang putih, beras, cabai merah, cabai rawit, daging ayam, daging sapi, gula pasir, minyak goreng, telur ayam
- **Dataset akhir:** 72 observasi (6 provinsi x 12 bulan), 14 kolom

## Alur Kerja

1. **Integrasi:** penggabungan file per bulan/provinsi/komoditas, agregasi curah hujan harian menjadi rata-rata bulanan, deteksi header otomatis pada file BPS, dan transformasi data PIHPS dari wide ke long lalu pivot.
2. **Cleaning:** penanganan kode error BMKG (8888, 9999, "-"), standardisasi nama bulan dan format tanggal, serta konversi harga ke tipe numerik.
3. **Merge:** ketiga dataset digabung berdasarkan `Provinsi` dan `Bulan` menjadi `DATA_ANALISIS.csv`.
4. **Eksplorasi:** statistik deskriptif, pengecekan missing value dan duplikasi, deteksi outlier (IQR), korelasi, dan visualisasi.

## Hasil Utama

- Tidak ditemukan missing value maupun data duplikat pada dataset akhir.
- Curah hujan berkorelasi positif sedang dengan inflasi (0,46) dan berkorelasi positif dengan harga cabai merah (0,38).
- Inflasi berkorelasi sangat lemah dengan harga sebagian besar komoditas.
- Cabai merah, cabai rawit, dan bawang merah paling fluktuatif, sedangkan beras, gula pasir, dan minyak goreng relatif stabil.
- Scatter plot tidak menunjukkan pola linear yang jelas, sehingga diperlukan analisis statistik lanjutan.


## Cara Menjalankan

```bash
git clone https://github.com/Salwaa297/Data-Wrangling-Project-Kelompok-15.git
cd Data-Wrangling-Project-Kelompok-15
pip install pandas numpy openpyxl matplotlib seaborn plotly
```

Buka notebook di Jupyter atau Google Colab, sesuaikan path folder data, lalu jalankan sel secara berurutan.

Notebook Colab: https://colab.research.google.com/drive/1nKoi7BLYIqDPi1ijbCR2vHbcl2P9-TTm?usp=sharing

## Rencana Lanjutan

Analisis regresi linear berganda untuk menguji pengaruh curah hujan dan inflasi terhadap harga komoditas:

```
Y = b0 + b1*X1 + b2*X2 + e
```

dengan Y = harga komoditas, X1 = curah hujan, dan X2 = inflasi.
