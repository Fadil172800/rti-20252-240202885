# Tahap 1 — Persiapan Penelitian

**Status:** Selesai

---

# 1. Perumusan Masalah

Tahap awal penelitian dilakukan dengan mengidentifikasi permasalahan pada proses klasifikasi penyakit daun padi. Identifikasi penyakit secara manual membutuhkan waktu, pengalaman, dan pengetahuan dari pakar sehingga berpotensi menimbulkan kesalahan klasifikasi apabila dilakukan oleh pengguna umum.

Berdasarkan permasalahan tersebut, penelitian ini mengusulkan penggunaan metode **Deep Learning** menggunakan model **EfficientNet-B6** dengan pendekatan **Transfer Learning** untuk membantu proses klasifikasi penyakit daun padi secara otomatis berdasarkan citra digital.

---

# 2. Studi Literatur

Studi literatur dilakukan untuk memperoleh dasar teori serta menentukan metode yang digunakan dalam penelitian.

Literatur yang dipelajari meliputi:

- Artificial Intelligence
- Machine Learning
- Deep Learning
- Convolutional Neural Network (CNN)
- EfficientNet
- Transfer Learning
- TensorFlow dan Keras
- Computer Vision
- Rice Leaf Disease
- Evaluasi model klasifikasi citra

Referensi utama penelitian adalah jurnal Milano et al. (2024) mengenai klasifikasi penyakit daun padi menggunakan EfficientNet-B6.

---

# 3. Penentuan Dataset

Dataset yang digunakan adalah **Rice Leafs Dataset** yang diperoleh dari Kaggle.

Spesifikasi dataset:

| Komponen | Keterangan |
|-----------|------------|
| Dataset | Rice Leafs |
| Total Citra | 3.355 |
| Jumlah Kelas | 4 |
| Format | JPG / PNG |
| Sumber | Kaggle |

Empat kelas yang digunakan terdiri dari:

- Healthy
- Brown Spot
- Hispa
- Leaf Blast

---

# 4. Perancangan Arsitektur Penelitian

Arsitektur penelitian dirancang agar seluruh proses eksperimen berjalan secara sistematis.

Alur penelitian terdiri dari:

```
Dataset
      │
      ▼
Preprocessing
      │
      ▼
Resize Image (224×224)
      │
      ▼
Split Dataset (80:20)
      │
      ▼
Transfer Learning
(EfficientNet-B6)
      │
      ▼
Training Model
      │
      ▼
Evaluasi Model
      │
      ▼
Accuracy
Precision
Recall
F1-Score
Classification Report
Confusion Matrix
```

---

# 5. Perancangan Variabel Penelitian

## Variabel Independen

Model yang digunakan pada penelitian.

| Variabel | Keterangan |
|-----------|------------|
| EfficientNet-B6 | Model Deep Learning berbasis CNN dengan Transfer Learning |

---

## Variabel Dependen

Performa model klasifikasi.

| Variabel | Keterangan |
|-----------|------------|
| Accuracy | Tingkat ketepatan klasifikasi |
| Precision | Ketepatan prediksi |
| Recall | Kemampuan menemukan kelas sebenarnya |
| F1-Score | Rata-rata harmonik Precision dan Recall |

---

## Variabel Kontrol

| Variabel | Nilai |
|-----------|--------|
| Dataset | Rice Leafs |
| Image Size | 224 × 224 piksel |
| Batch Size | 2 |
| Optimizer | Adam |
| Epoch Maksimum | 25 |

---

# 6. Lingkungan Penelitian

Implementasi penelitian dilakukan menggunakan Google Colab Free.

| Komponen | Spesifikasi |
|-----------|-------------|
| Platform | Google Colab Free |
| Bahasa Pemrograman | Python 3 |
| Framework | TensorFlow 2.x |
| Library | TensorFlow Keras |
| Hardware | Google Colab Runtime |

---

# 7. Keputusan Penelitian

Beberapa keputusan yang ditetapkan sebelum implementasi adalah sebagai berikut.

1. Menggunakan dataset Rice Leafs sebagai sumber data penelitian.
2. Menggunakan model EfficientNet-B6 sesuai dengan jurnal acuan.
3. Menggunakan pendekatan Transfer Learning dengan bobot awal ImageNet.
4. Ukuran citra ditetapkan sebesar **224 × 224 piksel**.
5. Dataset dibagi menjadi **80% data training** dan **20% data validation**.
6. Optimizer yang digunakan adalah **Adam**.
7. Evaluasi model dilakukan menggunakan Accuracy, Precision, Recall, F1-Score, Classification Report, dan Confusion Matrix.

---

# 8. Hasil Tahap 1

Tahap persiapan penelitian telah menghasilkan beberapa dokumen penting sebagai dasar pelaksanaan penelitian berikutnya.

- Proposal penelitian.
- Rumusan masalah dan tujuan penelitian.
- Studi literatur.
- Penentuan dataset.
- Perancangan metodologi penelitian.
- Penentuan model EfficientNet-B6.
- Penentuan parameter penelitian.
- Rencana implementasi penelitian.

Tahap ini menjadi dasar pelaksanaan proses preprocessing data, implementasi model, pelatihan, dan evaluasi pada tahap selanjutnya.
