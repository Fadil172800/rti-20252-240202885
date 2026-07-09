# 04-data

Data yang digunakan dan dihasilkan selama proses penelitian **Klasifikasi Penyakit Daun Padi Menggunakan EfficientNet-B6 dengan Pendekatan Transfer Learning**.

Folder ini berisi dataset penelitian, hasil pembagian data, serta keluaran (output) mentah dari proses pelatihan dan evaluasi model yang nantinya digunakan pada tahap analisis hasil penelitian.

---

# Dataset Penelitian

Dataset yang digunakan adalah **Rice Leafs Dataset** yang diperoleh dari Kaggle.

Jumlah data:

| Kelas | Jumlah Citra |
|--------|-------------:|
| Healthy | 1488 |
| BrownSpot | 523 |
| Hispa | 565 |
| LeafBlast | 779 |
| **Total** | **3355** |

Karakteristik dataset:

- Format gambar: JPG/PNG
- Warna: RGB
- Jumlah kelas: 4
- Ukuran citra setelah preprocessing: **224 × 224 piksel**
- Sumber dataset: Kaggle Rice Leafs Dataset

---

# Pembagian Dataset

Dataset dibagi menggunakan metode **Train-Validation Split**.

| Dataset | Persentase |
|----------|-----------:|
| Training | 80% |
| Validation | 20% |

Pembagian dilakukan sebelum proses pelatihan model agar data validasi tidak ikut digunakan selama proses training.

---

# Isi yang Diharapkan

Folder ini berisi data mentah (raw data) yang digunakan maupun dihasilkan selama eksperimen, antara lain:

- Dataset Rice Leafs
- Hasil pembagian dataset (Training dan Validation)
- Model terbaik hasil pelatihan (.keras/.h5)
- History pelatihan model
- Nilai Accuracy dan Loss setiap epoch
- Confusion Matrix
- Classification Report
- Hasil prediksi model
- File log pelatihan Google Colab

---

# Metadata Eksperimen

Informasi yang dicatat selama pelaksanaan eksperimen meliputi:

- Tanggal pelaksanaan eksperimen
- Platform: Google Colab Free
- Framework: TensorFlow 2.x
- Bahasa pemrograman: Python 3
- Model: EfficientNet-B6
- Pendekatan: Transfer Learning
- Optimizer: Adam
- Batch Size: 2
- Epoch maksimum: 25
- Image Size: 224 × 224 piksel
- Split dataset: 80% Training, 20% Validation

---

# Catatan

Data pada folder ini merupakan **data mentah (raw data)** hasil proses pelatihan dan evaluasi model.

Data tersebut belum dianalisis maupun divisualisasikan. Seluruh proses pengolahan data, perhitungan metrik evaluasi, visualisasi grafik, serta interpretasi hasil penelitian disajikan pada folder **06-output** dan dibahas lebih lanjut pada bagian hasil penelitian.
