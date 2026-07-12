# Klasifikasi Penyakit Daun Padi Menggunakan EfficientNet-B6 dengan Pendekatan Transfer Learning

**Peneliti:** Syukron Nur Fadillah  
**NIM:** 240202885  
**Program Studi:** Informatika – Universitas Putra Bangsa

---

# Ringkasan Penelitian

Penelitian ini bertujuan untuk mengklasifikasikan penyakit daun padi menggunakan model **EfficientNet-B6** dengan pendekatan **Transfer Learning**.

Dataset yang digunakan adalah **Rice Leafs Dataset** yang terdiri dari **3.355 citra** dengan empat kelas penyakit, yaitu:

- Healthy
- Brown Spot
- Hispa
- Leaf Blast

Seluruh proses penelitian dilakukan menggunakan **Google Colab Free** dengan framework **TensorFlow 2.x** dan bahasa pemrograman **Python**.

Tahapan penelitian meliputi proses pengumpulan dataset, preprocessing data, implementasi model EfficientNet-B6, pelatihan model, evaluasi performa menggunakan beberapa metrik klasifikasi, hingga penyusunan manuskrip dan laporan penelitian.

Dokumentasi lengkap tahapan penelitian tersedia pada:

➡️ **[09-docs/rencana-penelitian.md](09-docs/rencana-penelitian.md)**

---

# Informasi Penelitian

| Komponen | Keterangan |
|----------|------------|
| Judul | Klasifikasi Penyakit Daun Padi Menggunakan EfficientNet-B6 dengan Pendekatan Transfer Learning |
| Model | EfficientNet-B6 |
| Pendekatan | Transfer Learning |
| Framework | TensorFlow 2.x |
| Bahasa | Python |
| Platform | Google Colab Free |
| Dataset | Rice Leafs Dataset |
| Jumlah Dataset | 3.355 citra |
| Jumlah Kelas | 4 |
| Ukuran Input | 224 × 224 piksel |
| Batch Size | 2 |
| Epoch Maksimum | 25 |
| Optimizer | Adam |
| Accuracy | **63,04%** |

---

# Struktur Repository

| Folder | Deskripsi |
|---------|-----------|
| [00-admin](00-admin/) | Administrasi penelitian, jadwal pelaksanaan, dan log penelitian. |
| [01-proposal](01-proposal/) | Proposal penelitian dalam format DOCX dan PDF. |
| [02-literatur](02-literatur/) | Referensi ilmiah dan jurnal utama yang digunakan pada penelitian. |
| [03-teori](03-teori/) | Landasan teori, arsitektur penelitian, dan metodologi penelitian. |
| [04-data](04-data/) | Dataset penelitian, metadata dataset, hasil Exploratory Data Analysis (EDA), dan pembagian dataset. |
| [05-kode](05-kode/) | Notebook implementasi EfficientNet-B6 menggunakan Google Colab. |
| [06-output](06-output/) | Hasil pelatihan model, evaluasi, confusion matrix, classification report, visualisasi, dan ringkasan penelitian. |
| [07-manuskrip](07-manuskrip/) | Manuskrip penelitian dalam format DOCX dan PDF. |
| [08-laporan](08-laporan/) | Laporan penelitian lengkap dalam format DOCX dan PDF. |
| [09-docs](09-docs/) | Dokumentasi setiap tahapan penelitian mulai dari perencanaan hingga penyusunan manuskrip. |

---

# Tahapan Penelitian

| Tahap | Status | Dokumentasi |
|--------|:------:|-------------|
| Tahap 1 — Persiapan Penelitian | ✅ | [tahap-1-persiapan-penelitian.md](09-docs/tahap-1-persiapan-penelitian.md) |
| Tahap 2 — Persiapan Dataset | ✅ | [tahap-2-persiapan-dataset.md](09-docs/tahap-2-persiapan-dataset.md) |
| Tahap 3 — Implementasi Model | ✅ | [tahap-3-implementasi-model.md](09-docs/tahap-3-implementasi-model.md) |
| Tahap 4 — Pelatihan dan Evaluasi Model | ✅ | [tahap-4-pelatihan-dan-evaluasi.md](09-docs/tahap-4-pelatihan-dan-evaluasi.md) |
| Tahap 5 — Penyusunan Manuskrip | ✅ | [tahap-5-penyusunan-manuskrip.md](09-docs/tahap-5-penyusunan-manuskrip.md) |

---

# Hasil Penelitian

Ringkasan hasil penelitian yang diperoleh adalah sebagai berikut.

| Metrik | Hasil |
|--------|-------:|
| Accuracy | **63,04%** |
| Dataset | 3.355 citra |
| Jumlah Kelas | 4 |
| Model | EfficientNet-B6 |
| Pendekatan | Transfer Learning |
| Framework | TensorFlow 2.x |

Evaluasi model dilakukan menggunakan:

- Accuracy
- Precision
- Recall
- F1-Score
- Classification Report
- Confusion Matrix

Seluruh hasil eksperimen tersedia pada folder:

➡️ **[06-output](06-output/)**

---

# Dokumen Penelitian

| Dokumen | Lokasi |
|----------|--------|
| Proposal Penelitian | [01-proposal](01-proposal/) |
| Studi Literatur | [02-literatur](02-literatur/) |
| Landasan Teori | [03-teori](03-teori/) |
| Dataset Penelitian | [04-data](04-data/) |
| Implementasi Model | [05-kode](05-kode/) |
| Hasil Penelitian | [06-output](06-output/) |
| Manuskrip | [07-manuskrip](07-manuskrip/) |
| Laporan Penelitian | [08-laporan](08-laporan/) |
| Dokumentasi Penelitian | [09-docs](09-docs/) |

---

# Teknologi yang Digunakan

- Python
- TensorFlow 2.x
- TensorFlow Keras
- NumPy
- Pandas
- Matplotlib
- Scikit-Learn
- Google Colab

---

# Struktur Penelitian

```
Proposal
      │
      ▼
Studi Literatur
      │
      ▼
Persiapan Dataset
      │
      ▼
Preprocessing
      │
      ▼
Implementasi EfficientNet-B6
      │
      ▼
Training Model
      │
      ▼
Evaluasi Model
      │
      ▼
Analisis Hasil
      │
      ▼
Manuskrip
      │
      ▼
Laporan Penelitian
```

---

# Status Repository

| Tahapan | Status |
|---------|:------:|
| Proposal | ✅ |
| Studi Literatur | ✅ |
| Dataset | ✅ |
| Implementasi Model | ✅ |
| Pelatihan Model | ✅ |
| Evaluasi Model | ✅ |
| Manuskrip | ✅ |
| Laporan Penelitian | ✅ |
| Dokumentasi Penelitian | ✅ |

---

# Penulis

**Syukron Nur Fadillah**

NIM: **240202885**

Program Studi Informatika

Universitas Putra Bangsa

---

# Lisensi

Repository ini disusun untuk keperluan penelitian akademik, dokumentasi tugas akhir, serta pengembangan ilmu pengetahuan pada bidang **Artificial Intelligence**, **Deep Learning**, dan **Computer Vision**.
