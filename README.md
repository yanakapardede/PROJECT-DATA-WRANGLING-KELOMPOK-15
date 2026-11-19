# PROYEK DATA WRANGLING
## KELOMPOK 15

# Analisis Pengaruh Curah Hujan dan Inflasi terhadap Harga Bahan Pokok di Pulau Jawa Tahun 2024

## Anggota Kelompok

| No. | Nama | Institusi |
|:---:|---|---|
| 1 | Shafa Fatimah Az Zahra | Universitas Negeri Jakarta |
| 2 | Yanaka Sofia Pardede | Universitas Negeri Surabaya |
| 3 | Putri Sofiyatus Salwa | Universitas Negeri Surabaya |

**Dosen Pengampu:** Ulfa Siti Nuraini, S.Stat., M.Stat.

---

## Deskripsi Proyek

Proyek ini merupakan proyek mata kuliah **Data Wrangling** yang bertujuan untuk mengintegrasikan, membersihkan, dan mengeksplorasi data curah hujan, inflasi pangan, serta harga bahan pokok di enam provinsi Pulau Jawa sepanjang tahun 2024.

Data yang digunakan berasal dari tiga sumber utama, yaitu Badan Meteorologi, Klimatologi, dan Geofisika (BMKG), Badan Pusat Statistik (BPS), serta Pusat Informasi Harga Pangan Strategis Nasional (PIHPS).

Proses pengerjaan meliputi pengumpulan data dari berbagai sumber, integrasi dataset, penanganan nilai yang tidak valid, standardisasi format data, serta eksplorasi menggunakan statistik deskriptif dan visualisasi.

Hasil akhir proyek berupa dataset yang telah melalui proses pembersihan dan penggabungan sehingga dapat digunakan untuk analisis lebih lanjut mengenai hubungan antara curah hujan, inflasi, dan harga berbagai komoditas bahan pokok.

Penjelasan lebih lengkap mengenai proses pengerjaan dan hasil analisis dapat dilihat pada laporan proyek yang tersedia di folder `docs/`.

## Sumber Data

Penelitian ini menggunakan tiga sumber data utama sebagai berikut:

| Sumber | Data yang Digunakan | Format Asal |
|---|---|---|
| BMKG | Data curah hujan harian | Excel (.xlsx) |
| BPS | Data inflasi bulanan subkelompok Makanan, Minuman, dan Tembakau | CSV |
| PIHPS | Data harga harian bahan pokok berdasarkan komoditas | Excel (.xlsx) |

Ketiga sumber data tersebut diintegrasikan untuk memperoleh dataset yang memuat informasi curah hujan, inflasi, dan harga bahan pokok pada masing-masing provinsi selama tahun 2024.

## Cakupan Data

Dataset yang digunakan dalam proyek ini memiliki cakupan sebagai berikut:

- **Periode:** Januari–Desember 2024.
- **Wilayah:** Enam provinsi di Pulau Jawa.
- **Provinsi:** Banten, DKI Jakarta, Jawa Barat, Jawa Tengah, DI Yogyakarta, dan Jawa Timur.
- **Jumlah Komoditas:** 10 komoditas bahan pokok.
- **Jumlah Observasi Akhir:** 72 observasi.
- **Jumlah Kolom:** 14 kolom.

### Daftar Komoditas

Komoditas bahan pokok yang dianalisis meliputi:

1. Bawang merah
2. Bawang putih
3. Beras
4. Cabai merah
5. Cabai rawit
6. Daging ayam
7. Daging sapi
8. Gula pasir
9. Minyak goreng
10. Telur ayam

Dataset akhir terdiri dari 72 observasi yang merepresentasikan kombinasi enam provinsi dan 12 bulan pengamatan selama tahun 2024.

## Tahapan Pengolahan Data

Proses pengolahan data dilakukan melalui beberapa tahapan utama sebagai berikut.

### 1. Data Integration

Tahap integrasi dilakukan untuk menggabungkan data dari BMKG, BPS, dan PIHPS yang memiliki struktur serta format berbeda.

Beberapa proses yang dilakukan meliputi:

- Menggabungkan file berdasarkan bulan, provinsi, dan komoditas.
- Mengagregasikan data curah hujan harian menjadi rata-rata bulanan.
- Mendeteksi header secara otomatis pada file BPS.
- Mengubah struktur data PIHPS dari format wide menjadi long, kemudian melakukan pivot sesuai kebutuhan analisis.

### 2. Data Cleaning

Tahap pembersihan dilakukan untuk memastikan data memiliki format yang konsisten dan dapat digunakan dalam analisis.

Proses yang dilakukan meliputi:

- Menangani kode error BMKG, seperti 8888, 9999, dan tanda `-`.
- Menstandarkan penulisan nama bulan.
- Menyeragamkan format tanggal.
- Mengonversi nilai harga menjadi tipe data numerik.
- Memeriksa kelengkapan dan konsistensi data.

### 3. Data Merging

Setelah proses integrasi dan pembersihan selesai, ketiga dataset digabungkan berdasarkan kolom `Provinsi` dan `Bulan`.

Hasil penggabungan disimpan dalam file `DATA_ANALISIS.csv` yang menjadi dataset utama untuk proses eksplorasi dan analisis selanjutnya.

### 4. Exploratory Data Analysis (EDA)

Tahap eksplorasi dilakukan untuk memahami karakteristik data dan mengidentifikasi pola hubungan antarvariabel.

Analisis yang dilakukan meliputi:

- Statistik deskriptif.
- Pemeriksaan missing value.
- Pemeriksaan data duplikat.
- Deteksi outlier menggunakan metode Interquartile Range (IQR).
- Analisis korelasi antarvariabel.
- Visualisasi distribusi dan hubungan antarvariabel.

## Hasil dan Pembahasan

Berdasarkan proses pengolahan dan eksplorasi data, diperoleh beberapa hasil utama sebagai berikut.

### 1. Hasil Data Cleaning

Setelah proses integrasi dan pembersihan dilakukan, dataset akhir memiliki karakteristik berikut:

| Keterangan | Hasil |
|---|---:|
| Jumlah Observasi | 72 |
| Jumlah Kolom | 14 |
| Missing Value | 0 |
| Data Duplikat | 0 |

Hasil pemeriksaan menunjukkan bahwa dataset akhir tidak memiliki missing value maupun data duplikat.

Dengan demikian, dataset telah melalui proses pemeriksaan kelengkapan dan konsistensi sebelum digunakan dalam analisis lebih lanjut.

### 2. Hasil Analisis Korelasi

Berdasarkan hasil eksplorasi korelasi, diperoleh beberapa temuan berikut:

- Curah hujan memiliki korelasi positif sedang dengan inflasi, yaitu sebesar **0,46**.
- Curah hujan memiliki korelasi positif dengan harga cabai merah, yaitu sebesar **0,38**.
- Inflasi memiliki korelasi sangat lemah dengan harga sebagian besar komoditas bahan pokok.

Nilai korelasi tersebut menggambarkan arah dan kekuatan hubungan linear antarvariabel pada dataset yang digunakan.

### 3. Analisis Fluktuasi Harga Komoditas

Berdasarkan hasil eksplorasi harga bahan pokok, ditemukan perbedaan tingkat fluktuasi antar komoditas.

- **Komoditas dengan fluktuasi tinggi:** Cabai merah, cabai rawit, dan bawang merah.
- **Komoditas dengan fluktuasi relatif rendah:** Beras, gula pasir, dan minyak goreng.

Perbedaan tersebut menunjukkan bahwa setiap komoditas memiliki pola perubahan harga yang berbeda sepanjang tahun 2024.

### 4. Temuan Utama

Berdasarkan hasil visualisasi dan eksplorasi data, scatter plot belum menunjukkan pola hubungan linear yang jelas antara beberapa variabel yang dianalisis.

Oleh karena itu, diperlukan analisis statistik lanjutan untuk memahami hubungan curah hujan dan inflasi terhadap perubahan harga bahan pokok secara lebih mendalam.

Perlu diperhatikan bahwa hasil korelasi menunjukkan hubungan statistik, bukan hubungan sebab-akibat secara langsung.

## Cara Menjalankan Proyek

Berikut langkah-langkah untuk menjalankan proyek ini.

### 1. Clone Repository

Unduh repository menggunakan perintah berikut:

```bash
git clone https://github.com/Salwaa297/data-wrangling-harga-bahan-pokok-jawa-2024.git
```

Masuk ke direktori proyek:

```bash
cd data-wrangling-harga-bahan-pokok-jawa-2024
```

### 2. Install Dependencies

Pastikan Python sudah tersedia, kemudian instal library yang dibutuhkan:

```bash
pip install pandas numpy openpyxl matplotlib seaborn plotly
```

### 3. Buka Notebook

Buka notebook menggunakan Jupyter Notebook atau Google Colab.

### 4. Siapkan Dataset

Pastikan file dataset tersedia sesuai dengan struktur direktori yang digunakan dalam notebook.

Jika menggunakan Google Colab, sesuaikan path folder data dengan lokasi penyimpanan dataset.

### 5. Jalankan Notebook

Jalankan setiap sel notebook secara berurutan mulai dari proses integrasi data, data cleaning, data merging, hingga Exploratory Data Analysis (EDA).

## Notebook Proyek

Notebook Google Colab dapat diakses melalui tautan berikut:

[Data Wrangling Project - Kelompok 15 (Google Colab)](https://colab.research.google.com/drive/1nKoi7BLYIqDPi1ijbCR2vHbcl2P9-TTm?usp=sharing)

## Rencana Analisis Lanjutan

Sebagai pengembangan dari hasil eksplorasi data, penelitian ini direncanakan untuk dilanjutkan dengan analisis regresi linear berganda.

Metode tersebut akan digunakan untuk mengeksplorasi hubungan antara curah hujan dan inflasi terhadap harga komoditas bahan pokok.

Model regresi linear berganda yang direncanakan adalah:

\[
Y = \beta_0 + \beta_1X_1 + \beta_2X_2 + \varepsilon
\]

Dengan keterangan:

- **Y:** Harga komoditas bahan pokok.
- **X₁:** Curah hujan.
- **X₂:** Inflasi.
- **β₀:** Konstanta.
- **β₁ dan β₂:** Koefisien regresi.
- **ε:** Error atau residual.

Analisis lanjutan ini diharapkan dapat memberikan pemahaman yang lebih mendalam mengenai hubungan curah hujan dan inflasi dengan perubahan harga bahan pokok di Pulau Jawa.
