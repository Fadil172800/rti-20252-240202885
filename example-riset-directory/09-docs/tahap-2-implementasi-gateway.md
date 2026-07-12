# Tahap 2 — Persiapan Dataset

**Status:** Selesai

**Acuan:** [../04-data/README.md](../04-data/README.md)

**Lokasi Dataset:** [../04-data/](../04-data/)

---

# Tujuan

Tahap ini bertujuan untuk mempersiapkan dataset yang akan digunakan pada proses pelatihan model **EfficientNet-B6**. Persiapan meliputi pengumpulan dataset, eksplorasi data (Exploratory Data Analysis/EDA), preprocessing citra, serta pembagian dataset menjadi data training dan validation.

---

# Deliverable

- [x] Dataset **Rice Leafs** berhasil diperoleh dari Kaggle.
- [x] Dataset terdiri dari **3.355 citra** dengan **4 kelas**.
- [x] Eksplorasi dataset (EDA) telah dilakukan.
- [x] Distribusi jumlah citra setiap kelas berhasil dianalisis.
- [x] Contoh citra setiap kelas berhasil didokumentasikan.
- [x] Distribusi resolusi gambar berhasil dianalisis.
- [x] Seluruh citra diubah menjadi ukuran **224 × 224 piksel**.
- [x] Dataset dibagi menjadi **80% data training** dan **20% data validation**.
- [x] Pipeline dataset menggunakan **TensorFlow image_dataset_from_directory()** berhasil dibuat.
- [x] Dataset siap digunakan pada proses pelatihan model.

---

# Dataset Penelitian

Dataset yang digunakan adalah **Rice Leafs Dataset** yang diperoleh dari Kaggle.

| Informasi | Keterangan |
|-----------|------------|
| Nama Dataset | Rice Leafs |
| Sumber | Kaggle |
| Total Dataset | 3.355 citra |
| Jumlah Kelas | 4 |
| Format | JPG / PNG |

Empat kelas yang digunakan terdiri dari:

- Healthy
- Brown Spot
- Hispa
- Leaf Blast

---

# Exploratory Data Analysis (EDA)

Sebelum proses pelatihan model dilakukan, dataset dianalisis untuk mengetahui karakteristik data.

EDA meliputi:

- Analisis distribusi jumlah citra.
- Analisis contoh citra setiap kelas.
- Analisis distribusi resolusi gambar.
- Pemeriksaan kualitas dataset.

Dokumentasi hasil EDA tersedia pada:

- [01-distribusi-dataset.png](../04-data/01-distribusi-dataset.png)
- [02-contoh-dataset.png](../04-data/02-contoh-dataset.png)
- [03-distribusi-resolusi.png](../04-data/03-distribusi-resolusi.png)

---

# Preprocessing Dataset

Tahap preprocessing dilakukan agar seluruh citra memiliki format yang seragam sebelum digunakan pada proses pelatihan model.

Tahapan preprocessing meliputi:

- Resize citra menjadi **224 × 224 piksel**.
- Konversi citra ke format RGB.
- Batch processing menggunakan TensorFlow Dataset.
- Prefetch dataset untuk meningkatkan efisiensi pelatihan.
- Preprocessing menggunakan fungsi `preprocess_input()` milik EfficientNet.

---

# Pembagian Dataset

Dataset dibagi menggunakan fungsi `image_dataset_from_directory()` dengan parameter `validation_split`.

| Dataset | Persentase |
|----------|-----------:|
| Training | 80% |
| Validation | 20% |

Pembagian dilakukan secara otomatis sehingga data training dan validation berasal dari dataset yang sama tanpa menyebabkan **data leakage**.

---

# Hasil Verifikasi

Tahap persiapan dataset berhasil dilakukan dengan hasil sebagai berikut.

- Dataset berhasil dibaca oleh TensorFlow.
- Seluruh kelas berhasil dikenali.
- Jumlah citra sesuai dengan dataset asli.
- Ukuran citra telah sesuai dengan input EfficientNet-B6.
- Dataset training dan validation berhasil dibuat.
- Pipeline dataset berhasil dijalankan tanpa error.

---

# Catatan Implementasi

Implementasi persiapan dataset dilakukan menggunakan notebook penelitian pada folder berikut.

- [PRAKTIKUMB6 (1).ipynb](../05-kode/PRAKTIKUMB6%20(1).ipynb)

Sedangkan dokumentasi dataset tersedia pada folder:

- [../04-data/](../04-data/)

---

# Hasil Tahap 2

Tahap persiapan dataset telah menghasilkan beberapa luaran penting sebagai dasar pelaksanaan penelitian, yaitu:

- Dataset Rice Leafs siap digunakan.
- Dokumentasi Exploratory Data Analysis (EDA).
- Hasil distribusi dataset.
- Dokumentasi contoh citra.
- Distribusi resolusi gambar.
- Dataset training dan validation.
- Pipeline TensorFlow Dataset.
- Dataset siap digunakan pada proses implementasi model EfficientNet-B6.
