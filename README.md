# NVIDIA Stock Data Preprocessing

## Deskripsi Proyek

Proyek ini merupakan tugas mata kuliah Data Mining yang berfokus pada tahap *data preprocessing* menggunakan Python. Dataset yang digunakan berisi data historis harga saham NVIDIA pada periode 2014–2024.

Preprocessing dilakukan untuk memeriksa kualitas data, memastikan konsistensi format dan nilai, serta mengidentifikasi pencilan (*outlier*) sebelum dataset digunakan untuk analisis lebih lanjut.

## Tujuan

1. Memahami struktur dan karakteristik dataset harga saham NVIDIA.
2. Mengidentifikasi nilai kosong dan data duplikat.
3. Memperbaiki format tipe data yang belum sesuai.
4. Memeriksa konsistensi data harga saham.
5. Mengidentifikasi outlier menggunakan metode Interquartile Range (IQR).
6. Menghasilkan dataset yang telah melalui proses preprocessing.

## Dataset

Dataset yang digunakan adalah data historis harga saham NVIDIA dengan rentang tanggal 1 Januari 2014 hingga 12 Januari 2024.

Dataset memiliki tujuh kolom utama:

| Kolom      | Deskripsi                        |
| ---------- | -------------------------------- |
| `Date`     | Tanggal perdagangan saham        |
| `Price`    | Harga penutupan saham            |
| `Open`     | Harga pembukaan saham            |
| `High`     | Harga tertinggi saham            |
| `Low`      | Harga terendah saham             |
| `Vol.`     | Volume transaksi saham           |
| `Change %` | Persentase perubahan harga saham |

Jumlah observasi dan rentang tanggal diperiksa kembali selama proses preprocessing.

## Tools dan Library

Proyek ini menggunakan:

* **Python** — bahasa pemrograman untuk pengolahan data.
* **Pandas** — manipulasi, pembersihan, dan pemeriksaan dataset.
* **NumPy** — operasi numerik.
* **Matplotlib** — visualisasi distribusi data menggunakan boxplot.
* **Google Colab** — lingkungan untuk menjalankan kode Python.

## Tahapan Preprocessing

### 1. Import Library

Mengimpor library yang diperlukan untuk membaca, mengolah, memeriksa, dan memvisualisasikan data.

### 2. Data Loading

Membaca dataset berformat Excel menggunakan Pandas.

### 3. Data Understanding

Memeriksa struktur dataset, dimensi data, tipe data, statistik deskriptif, dan contoh observasi.

### 4. Data Cleaning

Memeriksa nilai kosong (*missing values*) dan data duplikat untuk mengetahui apakah diperlukan penanganan lebih lanjut.

### 5. Data Type Conversion

Mengonversi kolom `Vol.` menjadi tipe numerik agar dapat digunakan dalam perhitungan statistik. Kolom `Date` juga dikonversi ke format datetime.

### 6. Data Consistency Check

Memeriksa validitas tanggal serta konsistensi nilai harga saham, termasuk hubungan antara harga pembukaan, penutupan, tertinggi, dan terendah.

### 7. Data Sorting

Mengurutkan observasi berdasarkan tanggal dari periode terlama hingga terbaru.

### 8. Outlier Detection

Mengidentifikasi nilai ekstrem menggunakan metode *Interquartile Range* (IQR). Visualisasi boxplot digunakan untuk membantu memahami distribusi dan keberadaan outlier.

Batas deteksi outlier ditentukan menggunakan rumus:

* **IQR** = Q3 − Q1
* **Batas bawah** = Q1 − 1,5 × IQR
* **Batas atas** = Q3 + 1,5 × IQR

Nilai yang berada di luar kedua batas tersebut ditandai sebagai outlier. Outlier tidak langsung dihapus karena dapat mencerminkan fluktuasi harga dan aktivitas perdagangan yang sebenarnya.

### 9. Final Evaluation

Memeriksa kembali tipe data, nilai kosong, data duplikat, dan urutan tanggal setelah preprocessing.

### 10. Export Dataset

Menyimpan dataset hasil preprocessing dalam format Excel (`.xlsx`) dan CSV (`.csv`) agar dapat digunakan untuk analisis lanjutan.

## Hasil Preprocessing

Berdasarkan pemeriksaan yang telah dilakukan:

* Tidak ditemukan nilai kosong pada dataset.
* Tidak ditemukan data duplikat.
* Tidak ditemukan tanggal yang tidak valid.
* Tidak ditemukan ketidakkonsistenan berdasarkan aturan pemeriksaan harga yang diterapkan.
* Kolom volume transaksi berhasil dikonversi menjadi tipe numerik.
* Data berhasil diurutkan berdasarkan tanggal.
* Sejumlah outlier teridentifikasi pada variabel harga, volume transaksi, dan persentase perubahan harga.

Deteksi outlier dilakukan sebagai tahap identifikasi, bukan sebagai dasar untuk langsung menghapus observasi. Keputusan penanganan lebih lanjut perlu mempertimbangkan karakteristik data saham dan tujuan analisis.

## Struktur Repository

Struktur repository yang disarankan:

```text
nvidia-stock-data-preprocessing/
├── README.md
├── NVIDIA Stock Price History.xlsx
├── NVIDIA_Stock_Preprocessed.xlsx
├── NVIDIA_Stock_Preprocessed.csv
└── Preprocessing_NVIDIA_Stock.ipynb
```

Nama file dapat disesuaikan dengan file yang benar-benar diunggah ke repository.

## Cara Menjalankan

1. Unduh atau *clone* repository ini.
2. Buka notebook `Preprocessing_NVIDIA_Stock.ipynb` menggunakan Google Colab.
3. Unggah dataset sumber `NVIDIA Stock Price History.xlsx` ke lingkungan Google Colab.
4. Sesuaikan lokasi atau nama file pada kode apabila diperlukan.
5. Jalankan setiap sel kode secara berurutan.
6. Periksa hasil preprocessing dan unduh dataset hasil pengolahan.

## Kesimpulan

Proyek ini menerapkan tahapan preprocessing untuk memeriksa dan meningkatkan kualitas dataset historis harga saham NVIDIA. Pemeriksaan mencakup kelengkapan data, duplikasi, format tipe data, konsistensi harga, urutan tanggal, dan identifikasi outlier.

Hasil preprocessing dapat digunakan sebagai dasar untuk analisis data lebih lanjut, seperti analisis statistik deskriptif, visualisasi pergerakan harga saham, atau pemodelan deret waktu.

---

**Mata Kuliah:** Data Mining
**Bahasa Pemrograman:** Python
**Platform:** Google Colab
