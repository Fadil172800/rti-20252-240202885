# 06 - Hasil Penelitian

Folder ini berisi seluruh hasil eksperimen yang diperoleh setelah proses pelatihan dan evaluasi model **EfficientNet-B6** menggunakan pendekatan **Transfer Learning** pada dataset **Rice Leafs**.

Seluruh output dihasilkan dari notebook penelitian yang dijalankan pada **Google Colab Free** menggunakan **TensorFlow 2.x** dan **Keras**. Evaluasi model dilakukan menggunakan metrik **Accuracy**, **Precision**, **Recall**, **F1-Score**, **Classification Report**, dan **Confusion Matrix** sesuai dengan rancangan penelitian.

---

# Ringkasan Hasil Penelitian

| Komponen | Hasil |
|----------|-------|
| Model | EfficientNet-B6 |
| Pendekatan | Transfer Learning |
| Dataset | Rice Leafs |
| Jumlah Kelas | 4 |
| Total Dataset | 3.355 citra |
| Input Size | 224 × 224 piksel |
| Batch Size | 2 |
| Epoch Maksimum | 25 |
| Accuracy | **63,04%** |

---

# Model Summary

Dokumen berikut berisi ringkasan arsitektur model EfficientNet-B6 yang digunakan pada penelitian.

| File | Deskripsi |
|------|-----------|
| `01-model-summary.md` | Dokumentasi arsitektur model. |
| `01-model-summary.png` | Visualisasi struktur model EfficientNet-B6. |

---

# Training History

Dokumen berikut berisi hasil proses pelatihan model.

| File | Deskripsi |
|------|-----------|
| `02-training-history.csv` | Riwayat nilai accuracy dan loss setiap epoch. |
| `02-training-history.md` | Dokumentasi hasil pelatihan model. |
| `02-training-history.png` | Grafik perkembangan accuracy dan loss selama proses training. |
| `02-training-log.txt` | Log lengkap proses pelatihan model. |

---

# Evaluasi Model

Evaluasi dilakukan menggunakan data validation setelah proses pelatihan selesai.

Metrik evaluasi meliputi:

- Accuracy
- Precision
- Recall
- F1-Score

Dokumen evaluasi terdiri dari:

| File | Deskripsi |
|------|-----------|
| `03-evaluation-metrics.csv` | Ringkasan metrik evaluasi model. |
| `05-evaluation-result.md` | Dokumentasi hasil evaluasi model. |
| `05-evaluation-result.png` | Visualisasi hasil evaluasi model. |

---

# Confusion Matrix

Dokumen berikut menyajikan hasil Confusion Matrix yang digunakan untuk mengevaluasi kemampuan model dalam mengklasifikasikan empat kelas penyakit daun padi.

| File | Deskripsi |
|------|-----------|
| `03-confusion-matrix.md` | Dokumentasi Confusion Matrix. |
| `03-04-confusion-matrix-classification-report.png` | Visualisasi Confusion Matrix beserta Classification Report. |

Empat kelas yang dievaluasi meliputi:

- Brown Spot
- Healthy
- Hispa
- Leaf Blast

---

# Classification Report

Classification Report digunakan untuk mengevaluasi performa model pada masing-masing kelas.

Metrik yang disajikan meliputi:

- Precision
- Recall
- F1-Score
- Support

Dokumen yang tersedia:

| File | Deskripsi |
|------|-----------|
| `04-classification-report.md` | Dokumentasi Classification Report. |
| `04-classification-report.txt` | Hasil Classification Report dalam format teks. |

---

# Contoh Hasil Prediksi

Folder ini juga menyajikan beberapa contoh hasil prediksi model terhadap data validasi.

| File | Deskripsi |
|------|-----------|
| `06-sample-prediction.md` | Dokumentasi hasil prediksi model. |
| `06-sample-prediction.png` | Contoh hasil prediksi beserta label sebenarnya. |

Visualisasi ini menunjukkan kemampuan model dalam mengenali penyakit daun padi pada data yang belum pernah digunakan selama proses pelatihan.

---

# Ringkasan Penelitian

Ringkasan eksperimen disimpan dalam file berikut.

| File | Deskripsi |
|------|-----------|
| `07-research-summary.csv` | Ringkasan parameter penelitian dan hasil akhir eksperimen. |

Ringkasan tersebut memuat informasi seperti:

- Model yang digunakan
- Dataset
- Jumlah kelas
- Ukuran input
- Epoch
- Accuracy
- Loss
- Parameter pelatihan

---

# Isi Folder

| Berkas | Deskripsi |
|---------|-----------|
| `01-model-summary.md` | Ringkasan arsitektur model. |
| `01-model-summary.png` | Visualisasi model. |
| `02-training-history.csv` | Riwayat pelatihan. |
| `02-training-history.md` | Dokumentasi training. |
| `02-training-history.png` | Grafik training. |
| `02-training-log.txt` | Log pelatihan. |
| `03-confusion-matrix.md` | Dokumentasi Confusion Matrix. |
| `03-04-confusion-matrix-classification-report.png` | Visualisasi Confusion Matrix dan Classification Report. |
| `03-evaluation-metrics.csv` | Nilai metrik evaluasi. |
| `04-classification-report.md` | Dokumentasi Classification Report. |
| `04-classification-report.txt` | Classification Report format teks. |
| `05-evaluation-result.md` | Ringkasan hasil evaluasi. |
| `05-evaluation-result.png` | Visualisasi hasil evaluasi. |
| `06-sample-prediction.md` | Dokumentasi prediksi. |
| `06-sample-prediction.png` | Contoh hasil prediksi. |
| `07-research-summary.csv` | Ringkasan penelitian. |
| `README.md` | Dokumentasi folder output. |

---

# Hubungan dengan Penelitian

Folder ini merupakan hasil akhir dari implementasi model pada folder **05-kode**.

Seluruh dokumen pada folder ini digunakan sebagai dasar penyusunan:

- Analisis hasil penelitian.
- Pembahasan pada laporan penelitian.
- Manuskrip ilmiah.
- Presentasi sidang penelitian.

---

# Keterkaitan dengan Repository

| Folder | Deskripsi |
|---------|-----------|
| [00-admin](../00-admin/) | Administrasi penelitian |
| [01-proposal](../01-proposal/) | Proposal penelitian |
| [02-literatur](../02-literatur/) | Studi literatur |
| [03-teori](../03-teori/) | Landasan teori |
| [04-data](../04-data/) | Dataset penelitian |
| [05-kode](../05-kode/) | Implementasi model |
| [07-manuskrip](../07-manuskrip/) | Manuskrip penelitian |
| [08-laporan](../08-laporan/) | Laporan penelitian |
| [09-docs](../09-docs/) | Dokumentasi penelitian |

---

# Catatan

Folder **06-output** berisi seluruh hasil eksperimen penelitian mulai dari ringkasan model, proses pelatihan, evaluasi performa, visualisasi hasil, hingga contoh prediksi model.

Seluruh output pada folder ini dihasilkan langsung dari notebook penelitian pada folder **05-kode** sehingga eksperimen dapat direproduksi kembali apabila notebook dijalankan menggunakan dataset dan konfigurasi yang sama.
