# 06-output

Folder ini berisi seluruh hasil eksperimen yang diperoleh setelah proses pelatihan dan evaluasi model **EfficientNet-B6** menggunakan pendekatan **Transfer Learning** pada dataset **Rice Leafs**.

Seluruh output dihasilkan dari notebook penelitian yang dijalankan pada **Google Colab Free** menggunakan **TensorFlow 2.x** dan **Keras**. Evaluasi model dilakukan menggunakan metrik **Accuracy, Precision, Recall, F1-Score, Confusion Matrix**, dan **Classification Report** sesuai dengan rancangan penelitian.

---

# Hasil Pelatihan Model

Output pelatihan model meliputi proses training menggunakan dataset training (80%) dan validation (20%).

Beberapa hasil yang diperoleh antara lain:

- Training Accuracy
- Validation Accuracy
- Training Loss
- Validation Loss
- History Training

File yang dihasilkan:

```
01-model-summary.md
01-model-summary.png
02-training-history.csv
02-training-log.txt
03-accuracy-loss.png
```

---

# Grafik Accuracy dan Loss

File

```
03-accuracy-loss.png
```

Keterangan

Grafik menunjukkan perkembangan nilai **Accuracy** dan **Loss** selama proses pelatihan model.

Visualisasi ini digunakan untuk mengevaluasi proses konvergensi model serta mendeteksi kemungkinan terjadinya **overfitting** maupun **underfitting**.

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
06-evaluation-result.md
```

Keterangan

File berisi ringkasan hasil evaluasi model berupa nilai **Loss** dan **Accuracy** yang diperoleh dari proses pengujian menggunakan data validation.

---

# Confusion Matrix

File

```
04-confusion-matrix.png
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
05-classification-report.md
06-classification-report.txt
```

Keterangan

Classification Report menampilkan nilai:

- Precision
- Recall
- F1-Score
- Support

untuk setiap kelas penyakit daun padi.

Laporan ini digunakan sebagai evaluasi utama performa model selain Accuracy.

---

# Contoh Hasil Prediksi

File

```
07-sample-prediction.png
```

Keterangan

Berisi beberapa contoh citra daun padi beserta label sebenarnya dan hasil prediksi model EfficientNet-B6.

Visualisasi ini digunakan untuk melihat kemampuan model dalam melakukan klasifikasi terhadap data yang belum pernah digunakan selama proses pelatihan.

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

Ringkasan ini dibuat secara otomatis pada akhir notebook penelitian.

---

# Model Hasil Training

Model terbaik hasil pelatihan disimpan menggunakan callback **ModelCheckpoint**.

Nama file:

```
best_efficientnetb6.keras
```

Karena ukuran file model sekitar **158 MB**, file tersebut **tidak disertakan pada repository GitHub** karena melebihi batas maksimum ukuran file GitHub (100 MB).

Model dapat diunduh melalui Google Drive berikut:

**https://drive.google.com/file/d/1mXJlk0n4VKApzQjJJVQ1el_oqPn4RmHL/view?usp=sharing**

---

# Isi Folder

Folder **06-output** berisi file berikut.

- README.md
- 01-model-summary.md
- 01-model-summary.png
- 02-training-history.csv
- 02-training-log.txt
- 03-accuracy-loss.png
- 04-confusion-matrix.png
- 04-evaluation-metrics.csv
- 05-classification-report.md
- 06-classification-report.txt
- 06-evaluation-result.md
- 07-sample-prediction.png
- 08-research-summary.csv

---

# Catatan

Folder **06-output** berisi seluruh hasil eksperimen penelitian mulai dari proses pelatihan model, evaluasi performa, visualisasi hasil, hingga ringkasan penelitian.

Model terbaik (`best_efficientnetb6.keras`) disimpan secara terpisah pada Google Drive karena ukuran file melebihi batas maksimum yang diizinkan oleh GitHub. Notebook penelitian pada folder **05-kode** tetap dapat dijalankan kembali untuk menghasilkan model tersebut.
