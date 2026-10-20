# implementasi1
Analisis Data Keuangan dan Prediksi Risiko Keterlambatan Pembayaran
# Analisis Data Keuangan dan Prediksi Risiko Keterlambatan Pembayaran

## Deskripsi Proyek

Proyek ini merupakan implementasi studi kasus analisis data bisnis berdasarkan materi *Make Sense of Data with Analytics and AI* yang membahas pemanfaatan data analytics untuk membantu perusahaan memahami kondisi keuangan dan mendukung pengambilan keputusan.

Studi kasus yang diangkat adalah PT Maju Bersama, dengan permasalahan berupa peningkatan pendapatan penjualan yang tidak diikuti peningkatan laba bersih, kenaikan piutang, serta penurunan arus kas operasional.

Implementasi dilakukan menggunakan **Python di Google Colab** dengan pendekatan analisis deskriptif, analisis diagnostik sederhana, dan machine learning untuk memprediksi risiko keterlambatan pembayaran pelanggan.

**Catatan:** Dataset yang digunakan dalam implementasi ini merupakan data simulasi untuk keperluan pembelajaran, bukan data asli PT Maju Bersama.

## Tujuan Proyek

1. Menganalisis kondisi keuangan perusahaan berdasarkan indikator penjualan, laba bersih, piutang, dan arus kas operasional.
2. Mengidentifikasi pola data transaksi pelanggan.
3. Membangun model machine learning untuk memprediksi risiko keterlambatan pembayaran.
4. Membandingkan performa beberapa algoritma klasifikasi.
5. Mengidentifikasi faktor yang berkontribusi terhadap prediksi keterlambatan pembayaran.
6. Memberikan informasi pendukung untuk pengambilan keputusan bisnis.

## Teknologi yang Digunakan

- **Python** — bahasa pemrograman utama.
- **Google Colab** — lingkungan pengembangan dan eksekusi notebook.
- **Pandas** — pengolahan dan analisis data.
- **NumPy** — operasi numerik dan pembuatan data simulasi.
- **Matplotlib** — visualisasi data.
- **Scikit-learn** — preprocessing data, pembangunan model, dan evaluasi machine learning.

## Metode Implementasi

### 1. Pembuatan Dataset Simulasi

Dataset transaksi dibuat menggunakan Python untuk merepresentasikan data faktur pelanggan, yang mencakup informasi seperti:

- ID pelanggan dan produk.
- Tanggal faktur.
- Jumlah transaksi.
- Batas kredit pelanggan.
- Metode pembayaran.
- Jenis pelanggan.
- Jumlah hari keterlambatan pembayaran.
- Status keterlambatan pembayaran.

Selain itu, dibuat dataset keuangan bulanan selama 24 bulan untuk merepresentasikan pendapatan penjualan, biaya operasional, laba bersih, piutang, arus kas operasional, dan margin laba kotor.

### 2. Eksplorasi dan Pembersihan Data

Tahapan ini dilakukan untuk memahami struktur dataset dan memeriksa kualitas data, meliputi:

- Melihat informasi dan ringkasan statistik dataset.
- Memeriksa nilai yang hilang.
- Memeriksa data duplikat.
- Melihat distribusi kelas keterlambatan pembayaran.

### 3. Analisis dan Visualisasi Keuangan

Data keuangan divisualisasikan untuk mengamati perubahan indikator keuangan dari waktu ke waktu. Perbandingan antara dua periode juga dilakukan untuk membantu memahami perubahan kondisi bisnis.

### 4. Preprocessing Data

Sebelum digunakan untuk pemodelan, data transaksi diproses melalui beberapa tahapan:

- Membuat fitur bulan transaksi.
- Memisahkan fitur prediksi dan variabel target.
- Mengisi nilai yang hilang.
- Melakukan penskalaan fitur numerik.
- Melakukan encoding pada fitur kategorikal.
- Membagi data menjadi data latih dan data uji berdasarkan urutan waktu.

Fitur `days_late` tidak digunakan sebagai fitur prediksi karena berkaitan langsung dengan hasil keterlambatan pembayaran dan dapat menyebabkan kebocoran informasi (*data leakage*).

### 5. Pembangunan Model Machine Learning

Tiga algoritma klasifikasi digunakan untuk membandingkan kemampuan prediksi:

1. Logistic Regression.
2. Decision Tree Classifier.
3. Random Forest Classifier.

Model dilatih untuk mengklasifikasikan transaksi ke dalam kategori berisiko terlambat atau tidak terlambat berdasarkan fitur yang tersedia.

### 6. Evaluasi Model

Evaluasi dilakukan menggunakan beberapa metrik:

- **Accuracy:** proporsi prediksi yang benar dari seluruh data uji.
- **Precision:** proporsi prediksi positif yang benar-benar positif.
- **Recall:** proporsi kasus positif aktual yang berhasil terdeteksi.
- **F1-score:** ukuran keseimbangan antara precision dan recall.

Confusion matrix dan classification report juga digunakan untuk membantu memahami hasil prediksi model.

### 7. Analisis Faktor dan Prediksi Transaksi

Feature importance dari model Random Forest digunakan untuk melihat fitur yang berkontribusi terhadap prediksi model. Model terpilih juga digunakan untuk memperkirakan probabilitas keterlambatan pembayaran pada contoh transaksi baru.

Feature importance menunjukkan kontribusi relatif fitur dalam model, bukan bukti hubungan sebab-akibat.

## Cara Menjalankan Proyek

1. Buka [Google Colab](https://colab.research.google.com/).
2. Buat notebook baru atau unggah file notebook `.ipynb` proyek.
3. Jalankan setiap sel kode secara berurutan dari bagian impor library hingga prediksi transaksi.
4. Perhatikan output berupa ringkasan data, grafik keuangan, evaluasi model, dan hasil prediksi.

Library yang digunakan umumnya sudah tersedia di Google Colab. Jika diperlukan, library dapat dipasang menggunakan perintah berikut:

```python
!pip install pandas numpy matplotlib scikit-learn
```

## Hasil yang Diharapkan

Implementasi ini diharapkan menghasilkan:

- Ringkasan karakteristik dan kualitas dataset.
- Grafik tren indikator keuangan bulanan.
- Perbandingan indikator keuangan antarperiode.
- Perbandingan performa tiga algoritma klasifikasi.
- Confusion matrix dan laporan evaluasi model.
- Informasi feature importance.
- Contoh prediksi risiko keterlambatan pembayaran pelanggan.

Hasil numerik dan kesimpulan yang diperoleh hanya menggambarkan dataset simulasi. Hasil tersebut tidak dapat digunakan untuk menyatakan kondisi keuangan atau risiko pelanggan PT Maju Bersama yang sebenarnya.

## Struktur Proyek

```text
analisis-data-keuangan/
├── README.md
└── analisis_data_keuangan.ipynb
```

`README.md` berisi dokumentasi proyek, sedangkan `analisis_data_keuangan.ipynb` berisi implementasi kode Python di Google Colab.

## Pengembangan Selanjutnya

Proyek dapat dikembangkan lebih lanjut dengan menggunakan data transaksi dan keuangan aktual yang telah diizinkan untuk digunakan, menambahkan fitur relevan, melakukan validasi model berdasarkan waktu, serta menguji model pada data baru. Hasil analisis dapat digunakan sebagai bahan pertimbangan untuk pemantauan piutang, tindak lanjut penagihan, dan evaluasi kebijakan kredit pelanggan.

## Referensi

Materi studi kasus: *Make Sense of Data with Analytics and AI* — Andria Arisal, BRIN, sebagaimana dibahas dalam materi yang menjadi dasar proyek ini.
