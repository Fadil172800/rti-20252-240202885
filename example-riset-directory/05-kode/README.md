# 05 - Implementasi Program

Folder ini berisi implementasi program yang digunakan pada penelitian **"Klasifikasi Penyakit Daun Padi Menggunakan EfficientNet-B6 dengan Pendekatan Transfer Learning"**.

Seluruh proses pengembangan, pelatihan model, evaluasi, dan visualisasi hasil dilakukan menggunakan **Google Colab** dengan bahasa pemrograman **Python** dan framework **TensorFlow**.

---

# Lingkungan Pengembangan

| Komponen | Keterangan |
|----------|------------|
| **Platform** | Google Colab Free |
| **Bahasa Pemrograman** | Python 3 |
| **Framework** | TensorFlow 2.x |
| **Library Deep Learning** | TensorFlow Keras |
| **Model** | EfficientNet-B6 |
| **Dataset** | Rice Leafs Dataset |
| **Sistem Operasi** | Linux (Google Colab Runtime) |

---

# Tahapan Implementasi

Implementasi program dilakukan melalui beberapa tahapan berikut.

## 1. Import Library

Library yang digunakan antara lain:

- TensorFlow
- Keras
- NumPy
- Pandas
- Matplotlib
- Scikit-Learn
- Glob
- OS

---

## 2. Persiapan Dataset

Tahapan ini meliputi:

- Membaca dataset Rice Leafs.
- Menentukan lokasi dataset.
- Membuat dataset training dan validation menggunakan `image_dataset_from_directory()`.
- Pembagian dataset menggunakan **80% data training** dan **20% data validation**.

---

## 3. Preprocessing Data

Tahap preprocessing dilakukan sebelum proses pelatihan model.

Meliputi:

- Resize citra menjadi **224 × 224 piksel**.
- Batch processing.
- Dataset Prefetch.
- Preprocessing menggunakan `preprocess_input()` milik EfficientNet.

---

## 4. Pembangunan Model

Model dibangun menggunakan arsitektur **EfficientNet-B6** dengan pendekatan **Transfer Learning**.

Konfigurasi model meliputi:

- Bobot awal **ImageNet**
- `include_top=False`
- Global Average Pooling
- Batch Normalization
- Dropout
- Dense Softmax

---

## 5. Pelatihan Model

Model dilatih menggunakan dataset training dengan konfigurasi sebagai berikut.

| Parameter | Nilai |
|-----------|-------|
| Epoch Maksimum | 25 |
| Optimizer | Adam |
| Learning Rate | 0.0001 |
| Loss Function | Sparse Categorical Crossentropy |
| Batch Size | 2 |

> **Catatan:** Pelatihan menggunakan callback **EarlyStopping**, **ReduceLROnPlateau**, dan **ModelCheckpoint** untuk memperoleh model terbaik serta mengurangi risiko overfitting.

---

## 6. Evaluasi Model

Setelah proses pelatihan selesai, model dievaluasi menggunakan beberapa metrik.

- Accuracy
- Precision
- Recall
- F1-Score
- Classification Report
- Confusion Matrix

---

## 7. Visualisasi Hasil

Program menghasilkan beberapa visualisasi, antara lain:

- Grafik Accuracy
- Grafik Loss
- Confusion Matrix
- Contoh hasil prediksi

Seluruh hasil visualisasi disimpan pada folder **06-output**.

---

## Isi Folder

| Berkas | Deskripsi |
|---------|-----------|
| [PRAKTIKUMB6.ipynb](PRAKTIKUMB6.ipynb) | Notebook utama penelitian yang berisi seluruh proses implementasi model **EfficientNet-B6**, mulai dari persiapan dataset, preprocessing, pembangunan model, pelatihan, evaluasi, hingga visualisasi hasil penelitian. |
| [README.md](README.md) | Dokumentasi folder implementasi program yang menjelaskan lingkungan pengembangan, tahapan implementasi, struktur kode, serta hubungan implementasi dengan keseluruhan penelitian. |

---

# Hubungan dengan Penelitian

Implementasi pada folder ini digunakan untuk:

- Membaca dataset penelitian.
- Melakukan preprocessing citra.
- Membangun model EfficientNet-B6.
- Melatih model menggunakan Transfer Learning.
- Mengevaluasi performa model.
- Menghasilkan model klasifikasi penyakit daun padi.

---

# Keterkaitan dengan Repository

| Folder | Deskripsi |
|---------|-----------|
| [00-admin](../00-admin/) | Administrasi penelitian |
| [01-proposal](../01-proposal/) | Proposal penelitian |
| [02-literatur](../02-literatur/) | Studi literatur |
| [03-teori](../03-teori/) | Landasan teori |
| [04-data](../04-data/) | Dataset dan preprocessing |
| [06-output](../06-output/) | Hasil pelatihan dan evaluasi model |
| [07-manuskrip](../07-manuskrip/) | Manuskrip penelitian |
| [08-laporan](../08-laporan/) | Laporan penelitian |
| [09-docs](../09-docs/) | Dokumentasi penelitian |

---

# Catatan

Folder **05-kode** hanya berisi implementasi program penelitian.

Seluruh hasil eksperimen seperti **model hasil pelatihan (.keras)**, **training history**, **grafik accuracy dan loss**, **confusion matrix**, **classification report**, **hasil evaluasi**, serta **contoh prediksi** didokumentasikan pada folder **06-output**.

Notebook pada folder ini dapat dijalankan kembali menggunakan Google Colab untuk mereproduksi seluruh tahapan penelitian mulai dari persiapan dataset hingga evaluasi model.
