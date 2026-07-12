# Tahap 3 — Implementasi Model EfficientNet-B6

**Status:** Selesai

**Bergantung pada:** [tahap-2-persiapan-dataset.md](tahap-2-persiapan-dataset.md)

**Lokasi Kode:** [../05-kode/PRAKTIKUMB6 (1).ipynb](../05-kode/PRAKTIKUMB6%20(1).ipynb)

---

# Tujuan

Tahap ini bertujuan untuk mengimplementasikan model **EfficientNet-B6** menggunakan pendekatan **Transfer Learning** pada dataset Rice Leafs. Implementasi dilakukan menggunakan TensorFlow dan Keras pada lingkungan Google Colab Free sehingga model dapat digunakan untuk proses pelatihan dan evaluasi klasifikasi penyakit daun padi.

---

# Deliverable

- [x] Notebook penelitian berhasil dibuat menggunakan Google Colab.
- [x] Import seluruh library yang dibutuhkan.
- [x] Dataset berhasil dimuat menggunakan TensorFlow.
- [x] Pipeline dataset berhasil dibangun menggunakan `tf.data`.
- [x] Preprocessing citra menggunakan `preprocess_input()`.
- [x] Model EfficientNet-B6 berhasil diimplementasikan.
- [x] Bobot awal menggunakan **ImageNet**.
- [x] Pendekatan **Transfer Learning** berhasil diterapkan.
- [x] Layer klasifikasi berhasil ditambahkan.
- [x] Model berhasil dikompilasi menggunakan optimizer Adam.
- [x] Callback EarlyStopping diterapkan.
- [x] Callback ModelCheckpoint diterapkan.
- [x] Callback ReduceLROnPlateau diterapkan.

---

# Implementasi Model

Model yang digunakan merupakan **EfficientNet-B6** dengan bobot awal **ImageNet**.

Konfigurasi utama model meliputi:

| Komponen | Konfigurasi |
|----------|-------------|
| Model | EfficientNet-B6 |
| Weights | ImageNet |
| Include Top | False |
| Pooling | Global Average Pooling |
| Transfer Learning | Ya |
| Batch Normalization | Digunakan |
| Dropout | 0.30 |
| Output Layer | Dense Softmax |

---

# Konfigurasi Pelatihan

Model dikompilasi menggunakan parameter sebagai berikut.

| Parameter | Nilai |
|-----------|-------|
| Optimizer | Adam |
| Learning Rate | 0.0001 |
| Loss Function | Sparse Categorical Crossentropy |
| Metrics | Accuracy |
| Batch Size | 2 |
| Maximum Epoch | 25 |

---

# Struktur Implementasi

Implementasi pada notebook dilakukan secara bertahap sebagai berikut.

```
Import Library
        │
        ▼
Load Dataset
        │
        ▼
Preprocessing Dataset
        │
        ▼
Membangun tf.data Pipeline
        │
        ▼
Load EfficientNet-B6
(ImageNet Weights)
        │
        ▼
Transfer Learning
        │
        ▼
Menambahkan Layer Klasifikasi
        │
        ▼
Compile Model
        │
        ▼
Training Model
```

---

# Callback yang Digunakan

Untuk meningkatkan stabilitas proses pelatihan, beberapa callback diterapkan.

| Callback | Fungsi |
|----------|--------|
| EarlyStopping | Menghentikan pelatihan apabila performa validasi tidak meningkat. |
| ReduceLROnPlateau | Menurunkan learning rate ketika performa model stagnan. |
| ModelCheckpoint | Menyimpan model terbaik selama proses pelatihan. |

---

# Hasil Implementasi

Tahap implementasi model berhasil dilakukan dengan hasil sebagai berikut.

- Model EfficientNet-B6 berhasil dimuat menggunakan bobot ImageNet.
- Transfer Learning berhasil diterapkan.
- Model berhasil dikompilasi tanpa error.
- Pipeline dataset berhasil dijalankan.
- Callback berhasil diterapkan.
- Model siap digunakan untuk proses pelatihan.

---

# Verifikasi Implementasi

Implementasi diverifikasi melalui beberapa tahapan.

- Notebook berhasil dijalankan pada Google Colab.
- Dataset berhasil dikenali oleh TensorFlow.
- Arsitektur EfficientNet-B6 berhasil dibangun.
- Seluruh layer klasifikasi berhasil ditambahkan.
- Model Summary berhasil ditampilkan.
- Tidak ditemukan error pada proses kompilasi model.

Dokumentasi model tersedia pada:

- [../06-output/01-model-summary.md](../06-output/01-model-summary.md)
- [../06-output/01-model-summary.png](../06-output/01-model-summary.png)

---

# Catatan Implementasi

Implementasi dilakukan menggunakan TensorFlow Keras pada lingkungan Google Colab Free.

Karena keterbatasan memori GPU Google Colab Free, beberapa konfigurasi disesuaikan agar proses pelatihan dapat berjalan dengan stabil, seperti penggunaan ukuran citra 224 × 224 piksel, batch size 2, serta penerapan callback EarlyStopping untuk mengurangi risiko overfitting.

---

# Hasil Tahap 3

Tahap implementasi model menghasilkan beberapa komponen utama sebagai berikut.

- Notebook implementasi EfficientNet-B6.
- Arsitektur model EfficientNet-B6.
- Pipeline TensorFlow Dataset.
- Konfigurasi Transfer Learning.
- Konfigurasi optimizer dan callback.
- Model siap digunakan pada tahap pelatihan dan evaluasi.

Tahap ini menjadi dasar pelaksanaan proses pelatihan model pada Tahap 4.
