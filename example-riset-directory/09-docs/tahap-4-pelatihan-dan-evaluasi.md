# Tahap 4 — Pelatihan dan Evaluasi Model

**Status:** Selesai

**Bergantung pada:** [tahap-3-implementasi-model.md](tahap-3-implementasi-model.md)

**Lokasi Kode:** [../05-kode/PRAKTIKUMB6 (1).ipynb](../05-kode/PRAKTIKUMB6%20(1).ipynb)

**Lokasi Output:** [../06-output/](../06-output/)

---

# Tujuan

Tahap ini bertujuan untuk melatih model **EfficientNet-B6** menggunakan dataset Rice Leafs yang telah dipreprocessing, kemudian mengevaluasi performa model menggunakan beberapa metrik evaluasi sehingga diperoleh hasil klasifikasi yang dapat dianalisis pada laporan penelitian dan manuskrip ilmiah.

---

# Deliverable

- [x] Proses pelatihan model berhasil dilakukan.
- [x] Training history berhasil direkam.
- [x] Model terbaik berhasil disimpan menggunakan ModelCheckpoint.
- [x] EarlyStopping berhasil menghentikan pelatihan pada epoch terbaik.
- [x] Accuracy dan Loss berhasil dihitung.
- [x] Confusion Matrix berhasil dibuat.
- [x] Classification Report berhasil dihasilkan.
- [x] Precision, Recall, dan F1-Score berhasil dihitung.
- [x] Contoh hasil prediksi berhasil dibuat.
- [x] Ringkasan hasil penelitian berhasil didokumentasikan.

---

# Konfigurasi Pelatihan

| Parameter | Nilai |
|-----------|-------|
| Model | EfficientNet-B6 |
| Dataset | Rice Leafs |
| Total Dataset | 3.355 citra |
| Jumlah Kelas | 4 |
| Ukuran Input | 224 × 224 piksel |
| Batch Size | 2 |
| Maximum Epoch | 25 |
| Optimizer | Adam |
| Learning Rate | 0.0001 |
| Loss Function | Sparse Categorical Crossentropy |

---

# Proses Pelatihan

Pelatihan dilakukan menggunakan dataset training sebesar **80%**, sedangkan **20%** digunakan sebagai data validation.

Selama proses pelatihan diterapkan beberapa callback, yaitu:

- EarlyStopping
- ReduceLROnPlateau
- ModelCheckpoint

ModelCheckpoint digunakan untuk menyimpan model dengan performa terbaik, sedangkan EarlyStopping menghentikan pelatihan apabila nilai validation loss tidak lagi mengalami peningkatan sehingga mengurangi risiko overfitting.

---

# Evaluasi Model

Evaluasi dilakukan menggunakan data validation setelah proses pelatihan selesai.

Metrik evaluasi yang digunakan meliputi:

- Accuracy
- Precision
- Recall
- F1-Score
- Classification Report
- Confusion Matrix

---

# Hasil Penelitian

Ringkasan hasil penelitian ditunjukkan pada tabel berikut.

| Komponen | Hasil |
|----------|-------|
| Model | EfficientNet-B6 |
| Dataset | Rice Leafs |
| Jumlah Dataset | 3.355 citra |
| Jumlah Kelas | 4 |
| Accuracy | **63,04%** |
| Precision | Berdasarkan Classification Report |
| Recall | Berdasarkan Classification Report |
| F1-Score | Berdasarkan Classification Report |

---

# Output Penelitian

Tahap pelatihan menghasilkan beberapa dokumen sebagai berikut.

| Dokumen | Keterangan |
|----------|------------|
| [01-model-summary.md](../06-output/01-model-summary.md) | Ringkasan arsitektur model. |
| [01-model-summary.png](../06-output/01-model-summary.png) | Visualisasi model EfficientNet-B6. |
| [02-training-history.md](../06-output/02-training-history.md) | Dokumentasi proses pelatihan. |
| [02-training-history.csv](../06-output/02-training-history.csv) | Riwayat accuracy dan loss setiap epoch. |
| [02-training-history.png](../06-output/02-training-history.png) | Grafik training history. |
| [02-training-log.txt](../06-output/02-training-log.txt) | Log proses pelatihan. |
| [03-confusion-matrix.md](../06-output/03-confusion-matrix.md) | Dokumentasi Confusion Matrix. |
| [03-04-confusion-matrix-classification-report.png](../06-output/03-04-confusion-matrix-classification-report.png) | Visualisasi Confusion Matrix dan Classification Report. |
| [03-evaluation-metrics.csv](../06-output/03-evaluation-metrics.csv) | Nilai metrik evaluasi. |
| [04-classification-report.md](../06-output/04-classification-report.md) | Dokumentasi Classification Report. |
| [04-classification-report.txt](../06-output/04-classification-report.txt) | Classification Report format teks. |
| [05-evaluation-result.md](../06-output/05-evaluation-result.md) | Ringkasan hasil evaluasi. |
| [05-evaluation-result.png](../06-output/05-evaluation-result.png) | Visualisasi hasil evaluasi. |
| [06-sample-prediction.md](../06-output/06-sample-prediction.md) | Dokumentasi hasil prediksi. |
| [06-sample-prediction.png](../06-output/06-sample-prediction.png) | Contoh hasil prediksi model. |
| [07-research-summary.csv](../06-output/07-research-summary.csv) | Ringkasan hasil penelitian. |

---

# Interpretasi Hasil

Berdasarkan hasil evaluasi, model EfficientNet-B6 mampu melakukan klasifikasi terhadap empat kelas penyakit daun padi dengan nilai akurasi sebesar **63,04%**.

Nilai Precision, Recall, dan F1-Score menunjukkan bahwa performa model berbeda pada setiap kelas. Kelas **Healthy** memiliki performa terbaik, sedangkan kelas **Hispa** memiliki nilai Recall dan F1-Score yang lebih rendah sehingga masih terdapat beberapa kesalahan klasifikasi pada kelas tersebut.

Hasil Confusion Matrix menunjukkan bahwa sebagian citra penyakit memiliki karakteristik visual yang mirip sehingga menyebabkan model masih mengalami kesalahan dalam membedakan beberapa kelas.

Secara keseluruhan, model berhasil melakukan klasifikasi sesuai tujuan penelitian, meskipun masih terdapat peluang peningkatan performa melalui proses fine-tuning, penambahan data latih, maupun penerapan teknik augmentasi data.

---

# Hasil Verifikasi

Tahap pelatihan dan evaluasi berhasil dilakukan dengan hasil sebagai berikut.

- Model berhasil dilatih menggunakan Google Colab.
- Training history berhasil direkam.
- Model terbaik berhasil disimpan.
- Accuracy berhasil dihitung.
- Classification Report berhasil dibuat.
- Confusion Matrix berhasil dibuat.
- Contoh hasil prediksi berhasil ditampilkan.
- Seluruh output penelitian berhasil didokumentasikan.

---

# Catatan Implementasi

Pelatihan dilakukan menggunakan Google Colab Free sehingga proses pelatihan dipengaruhi oleh keterbatasan memori dan GPU yang tersedia.

Untuk menyesuaikan keterbatasan tersebut digunakan:

- Batch Size = 2
- Image Size = 224 × 224 piksel
- EarlyStopping
- ReduceLROnPlateau

Konfigurasi tersebut memungkinkan proses pelatihan berjalan dengan stabil tanpa mengalami kegagalan akibat keterbatasan sumber daya komputasi.

---

# Hasil Tahap 4

Tahap pelatihan dan evaluasi menghasilkan beberapa luaran utama sebagai berikut.

- Model EfficientNet-B6 hasil pelatihan.
- Training History.
- Accuracy dan Loss.
- Classification Report.
- Confusion Matrix.
- Contoh hasil prediksi.
- Ringkasan hasil penelitian.

Seluruh hasil pada tahap ini menjadi dasar penyusunan laporan penelitian, analisis hasil, pembahasan, serta manuskrip ilmiah pada tahap berikutnya.
