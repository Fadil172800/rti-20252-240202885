# 06-output

Folder ini berisi seluruh hasil eksperimen yang diperoleh setelah proses pelatihan dan evaluasi model **EfficientNet-B6** menggunakan pendekatan **Transfer Learning** pada dataset **Rice Leafs**.

Seluruh output dihasilkan dari notebook penelitian yang dijalankan pada **Google Colab Free** menggunakan **TensorFlow 2.x** dan **Keras**. Evaluasi model dilakukan menggunakan metrik **Accuracy, Precision, Recall, F1-Score, Confusion Matrix**, dan **Classification Report**, sesuai dengan rancangan penelitian. :contentReference[oaicite:0]{index=0}

---

# Hasil Pelatihan Model

Output pelatihan model meliputi proses training menggunakan dataset training (80%) dan validation (20%).

Beberapa hasil yang diperoleh antara lain:

- Training Accuracy
- Validation Accuracy
- Training Loss
- Validation Loss
- History Training
- Early Stopping
- Learning Rate Reduction

File yang disimpan antara lain:

```
01-history-training.png
02-training-log.txt
```

---

# Grafik Accuracy dan Loss

File

```
03-accuracy-loss.png
```

Keterangan

Grafik menunjukkan perkembangan nilai **Accuracy** dan **Loss** selama proses pelatihan model.

Visualisasi ini digunakan untuk mengevaluasi proses konvergensi model serta mendeteksi kemungkinan terjadinya overfitting atau underfitting.

---

# Evaluasi Model

Evaluasi dilakukan menggunakan data validation setelah proses training selesai.

Metrik evaluasi meliputi:

- Accuracy
- Precision
- Recall
- F1-Score

File

```
04-evaluation-metrics.csv
```

Keterangan

File berisi ringkasan hasil evaluasi model yang diperoleh dari proses pengujian menggunakan data validation. :contentReference[oaicite:1]{index=1}

---

# Confusion Matrix

File

```
05-confusion-matrix.png
```

Keterangan

Confusion Matrix digunakan untuk melihat distribusi prediksi model terhadap masing-masing kelas.

Empat kelas yang dievaluasi meliputi:

- BrownSpot
- Healthy
- Hispa
- LeafBlast

Visualisasi ini membantu mengidentifikasi kelas yang masih sering mengalami kesalahan klasifikasi.

---

# Classification Report

File

```
06-classification-report.txt
```

Keterangan

Classification Report menampilkan nilai:

- Precision
- Recall
- F1-Score
- Support

untuk setiap kelas penyakit daun padi.

Laporan ini digunakan sebagai evaluasi utama performa model selain Accuracy. :contentReference[oaicite:2]{index=2}

---

# Contoh Hasil Prediksi

File

```
07-sample-prediction.png
```

Keterangan

Berisi beberapa contoh citra daun padi beserta label sebenarnya dan hasil prediksi model EfficientNet-B6.

Visualisasi ini digunakan untuk melihat kemampuan model dalam melakukan klasifikasi terhadap data yang belum pernah dilatih sebelumnya.

---

# Ringkasan Penelitian

File

```
08-research-summary.csv
```

Keterangan

Ringkasan penelitian berisi informasi utama mengenai eksperimen, antara lain:

- Model
- Dataset
- Jumlah kelas
- Ukuran input
- Jumlah epoch
- Validation Loss
- Validation Accuracy

Ringkasan ini dibuat secara otomatis pada akhir notebook penelitian. :contentReference[oaicite:3]{index=3}

---

# Model Hasil Training

File

```
model-efficientnet-b6.keras
model-efficientnet-b6.h5
```

Keterangan

Model hasil pelatihan disimpan dalam dua format sehingga dapat digunakan kembali untuk proses inferensi maupun pengembangan penelitian selanjutnya. :contentReference[oaicite:4]{index=4}

---

# Isi Folder

Folder **06-output** diharapkan berisi file berikut.

- 01-history-training.png
- 02-training-log.txt
- 03-accuracy-loss.png
- 04-evaluation-metrics.csv
- 05-confusion-matrix.png
- 06-classification-report.txt
- 07-sample-prediction.png
- 08-research-summary.csv
- model-efficientnet-b6.keras
- model-efficientnet-b6.h5

---

# Catatan

Folder **06-output** berisi seluruh hasil eksperimen penelitian, mulai dari proses pelatihan model, evaluasi performa, visualisasi hasil, hingga model akhir yang telah disimpan. Seluruh output pada folder ini dihasilkan langsung dari notebook Google Colab dan menjadi dasar penyusunan bagian **Hasil dan Pembahasan** pada laporan penelitian.
