# Analisis Korelasi Stasiun Hujan (Pearson Correlation)

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Status-Research-orange)

## Deskripsi Proyek

Repositori ini berisi script Python untuk menganalisis hubungan statistik antar stasiun penakar hujan menggunakan metode **Korelasi Pearson (*Pearson Correlation Coefficient*)**.

Analisis ini bertujuan untuk:
1.  Mengukur seberapa kuat hubungan linear curah hujan antar stasiun.
2.  Mengevaluasi konsistensi data antar stasiun yang berdekatan.
3.  Menjadi dasar justifikasi untuk metode pengisian data kosong (*gap filling*) atau interpolasi spasial.

Output dari script ini adalah **Matriks Korelasi** dan visualisasi **Heatmap** yang menunjukkan nilai koefisien korelasi ($r$) dengan rentang -1 hingga +1.

## Metodologi

Korelasi dihitung menggunakan metode **Pearson ($r$)** dengan rumus:

$$r = \frac{\sum(x_i - \bar{x})(y_i - \bar{y})}{\sqrt{\sum(x_i - \bar{x})^2 \sum(y_i - \bar{y})^2}}$$

Dimana:
* Nilai mendekati **+1**: Korelasi positif kuat (pola hujan sangat mirip).
* Nilai mendekati **0**: Tidak ada korelasi linear.
* Nilai mendekati **-1**: Korelasi negatif kuat (berlawanan).

## Prasyarat Instalasi

Pastikan Anda telah menginstal pustaka Python berikut:

```bash
pip install pandas matplotlib seaborn openpyxl

```

## Format Data Input

Script ini mengharapkan file input bernama `CH Bulanan 7 Stasiun.csv` (atau format Excel) dengan struktur kolom sebagai berikut:

| Date | Stasiun_A | Stasiun_B | Stasiun_C | ... |
| --- | --- | --- | --- | --- |
| Sep-09 | 120.5 | 115.0 | 130.2 | ... |
| Oct-09 | 240.0 | 235.5 | 250.0 | ... |

* **Kolom 1:** Wajib bernama `Date` dengan format bulan-tahun (contoh: `Sep-09` atau `Jan-2010`).
* **Kolom Selanjutnya:** Nama-nama stasiun hujan dengan nilai curah hujan (numerik).

## Cara Penggunaan

1. Letakkan file data (`.csv` atau `.xlsx`) dalam satu folder dengan script.
2. Sesuaikan variabel `file_path` di dalam script jika nama file berbeda.
3. Jalankan script:
```bash
python analisis_korelasi.py

```


4. Hasil visualisasi akan muncul dan disimpan otomatis sebagai `korelasi_hujan.png`.

## Contoh Output Visualisasi

Script akan menghasilkan **Heatmap Korelasi** dengan skema warna:

* 🔴 **Merah Pekat:** Korelasi Tinggi (Sangat Mirip).
* 🔵 **Biru:** Korelasi Rendah/Negatif.

> *Interpretasi: Jika Stasiun A dan Stasiun B memiliki nilai korelasi > 0.7, maka data dari Stasiun A dapat digunakan untuk mengisi kekosongan data di Stasiun B (dan sebaliknya).*

## Penulis

**Jariyan Arifudin** Mahasiswa Geografi Lingkungan

Universitas Gadjah Mada (UGM)

## Lisensi & Sitasi

Kode ini didistribusikan di bawah **MIT License**.
Jika Anda menggunakan metode ini untuk penelitian, silakan sitasi repositori ini:

> Arifudin, J. (2026). *Analisis Korelasi Stasiun Hujan (Pearson Correlation)*. GitHub Repository.
