# 05-kode

Folder ini berisi implementasi program yang digunakan pada penelitian **Klasifikasi Penyakit Daun Padi Menggunakan EfficientNet-B6 dengan Pendekatan Transfer Learning**.

Seluruh eksperimen dilakukan menggunakan **Google Colab** dengan bahasa pemrograman Python dan framework TensorFlow.

---

# Platform Pengembangan

| Komponen | Keterangan |
|----------|------------|
| Platform | Google Colab Free |
| Bahasa Pemrograman | Python 3 |
| Framework | TensorFlow 2.x |
| Library Deep Learning | TensorFlow Keras |
| Model | EfficientNet-B6 |
| Dataset | Rice Leafs Dataset |
| Sistem Operasi | Linux (Google Colab Runtime) |

---

# Tahapan Program

Implementasi program terdiri dari beberapa tahapan utama sebagai berikut.

## 1. Import Library

Mengimpor seluruh library yang diperlukan, seperti:

- TensorFlow
- NumPy
- Matplotlib
- Scikit-Learn
- Pandas
- OS
- Glob

---

## 2. Persiapan Dataset

Tahap ini meliputi:

- Membaca dataset Rice Leafs
- Menentukan lokasi folder dataset
- Membuat data training dan validation menggunakan `image_dataset_from_directory()`
- Pembagian dataset 80% training dan 20% validation

---

## 3. Preprocessing Data

Tahapan preprocessing dilakukan sebelum proses pelatihan model.

Meliputi:

- Resize citra menjadi 224 × 224 piksel
- Batch processing
- Prefetch dataset
- Preprocessing menggunakan fungsi `preprocess_input()` milik EfficientNet

---

## 4. Pembuatan Model

Model dibangun menggunakan arsitektur **EfficientNet-B6** dengan pendekatan **Transfer Learning**.

Konfigurasi utama meliputi:

- Bobot awal ImageNet
- include_top = False
- Global Average Pooling
- Batch Normalization
- Dropout
- Dense Softmax

---

## 5. Training Model

Model dilatih menggunakan dataset training dengan parameter yang telah ditentukan.

Parameter utama:

| Parameter | Nilai |
|-----------|-------|
| Epoch | 25 |
| Optimizer | Adam |
| Learning Rate | 0.0001 |
| Loss Function | Sparse Categorical Crossentropy |
| Batch Size | 32 |

---

## 6. Evaluasi Model

Setelah proses pelatihan selesai dilakukan evaluasi menggunakan:

- Accuracy
- Loss
- Precision
- Recall
- F1-Score
- Classification Report
- Confusion Matrix

---

## 7. Visualisasi Hasil

Program menghasilkan beberapa visualisasi berupa:

- Grafik Accuracy
- Grafik Loss
- Confusion Matrix
- Contoh hasil prediksi

---

# Struktur Folder

Folder ini berisi file sebagai berikut.

```
05-kode
│
├── README.md
├── penelitian_efficientnet_b6.ipynb
├── penelitian_efficientnet_b6.py
└── requirements.txt
```

---

# Keterangan File

| File | Keterangan |
|------|------------|
| penelitian_efficientnet_b6.ipynb | Notebook utama penelitian pada Google Colab |
| penelitian_efficientnet_b6.py | Script Python hasil konversi notebook |
| requirements.txt | Daftar library yang digunakan |
| README.md | Dokumentasi implementasi program |

---

# Catatan

Implementasi program pada folder ini hanya berisi kode sumber penelitian.

Seluruh hasil pelatihan model, grafik performa, confusion matrix, classification report, serta hasil prediksi disimpan pada folder **06-output**.
