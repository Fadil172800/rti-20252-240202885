# WS-09: Implementation & Environment

> **Bab 9 — Implementasi Riset & Kontrol Lingkungan**

---

## Ringkasan Materi

### Implementasi Riset ≠ Coding Biasa

Tujuan implementasi riset bukan membuat software yang berfungsi, melainkan membangun **instrumen pengukuran yang konsisten**. Setiap modul harus di-mapping ke variabel (dari Bab 6), parameter harus config-driven, dan logging aktif dari hari pertama.

> **Mengapa reproducibility penting?** Sains dibangun di atas prinsip verifikasi — temuan harus bisa dikonfirmasi oleh peneliti lain. _Replicability crisis_ yang terjadi di banyak paper riset ML/AI disebabkan oleh environment tidak terdokumentasi: orang lain tidak bisa reproduksi, hasil diragukan, kepercayaan terhadap temuan hilang. Prinsip: **dokumentasi environment = snapshot kredibilitas riset Anda.**

### Reproducible Implementation Model

```
Design → Implementation → Environment Setup → Execution Consistency → Reproducibility → Trustworthy Result
```

Setiap transisi memiliki syarat:
- Design → Implementation: kode sesuai mapping variabel-ke-komponen
- Implementation → Environment: versi, dependency, seed, path, OS eksplisit
- Environment → Consistency: seed terkunci, urutan deterministik
- Consistency → Reproducibility: dokumentasi lengkap
- Reproducibility → Trust: siapa pun ikuti dokumentasi → hasil sama/serupa

### Repeatability vs Reproducibility

| Level | Peneliti | Environment | Hasil |
|-------|---------|-------------|-------|
| **Repeatability** | Sama | Sama | Sama persis |
| **Reproducibility** | Berbeda | Berbeda (ikuti docs) | Sama/serupa |

Capai **repeatability** dulu, baru **reproducibility**.

### Engineering vs Research Perspective

| Aspek | Engineering | Research |
|-------|-----------|---------|
| Tujuan | Sistem berfungsi untuk user | Instrumen pengukuran konsisten |
| Dependency | Update ke terbaru | Lock di versi spesifik |
| Testing | Unit, integration, E2E | Repeatability test (run ulang → sama?) |
| Dokumentasi | User guide, API docs | Environment spec, execution steps, expected output |
| Config | Default masuk akal | Setiap parameter eksplisit & adjustable |

### Jebakan Kognitif

1. Menunda environment setup → bug sulit dilacak
2. Tidak pakai version control → hasil tidak bisa direkonstruksi
3. Menolak Docker/container → "di laptop saya bisa" saat review
   - **Docker** = teknologi container yang "membungkus" aplikasi beserta seluruh dependency-nya dalam satu unit terisolasi. Hasilnya: kode berjalan identik di laptop, server, maupun reviewer lain. Intro singkat: `docker run -v $(pwd):/workspace environment-image python run_experiment.py`
4. 3× hasil sama ≠ repeatable (bisa cache/state tersimpan)

### Dependency Locking

Mengandalkan "install library terbaru" berbahaya: versi berbeda = perilaku berbeda = hasil tidak reproducible. Praktik:
- **Python**: buat `requirements.txt` dengan versi eksplisit: `scikit-learn==1.3.2`, lalu kunci dengan `pip freeze > requirements.txt`
- **Conda**: gunakan `conda env export > environment.yml` untuk snapshot lengkap
- **Node.js/R/Julia**: gunakan `package-lock.json` / `renv.lock` / `Project.toml` — semua fungsi serupa: lock versi + hash

### Istilah Penting

- **Environment Specification** — Deskripsi lengkap: hardware, OS, runtime, library + versi, config, seed
- **Dependency** — Komponen eksternal yang harus di-lock versinya
- **Config-driven** — Parameter dieksternalisasi ke file konfigurasi, bukan hardcode

---

# WS-09: Implementation & Environment

> **Bab 9 — Implementasi Riset & Kontrol Lingkungan**

---

## Template A.9 — Dokumentasi Setup Eksperimen

```
EXPERIMENT SETUP DOCUMENTATION

Hardware:

CPU     : Intel Xeon (Google Colab Runtime)
RAM     : ±12 GB RAM
GPU     : NVIDIA Tesla T4 atau GPU yang tersedia pada Google Colab Free
Storage : Google Drive dan Google Colab Storage

Software:

OS        : Linux (Ubuntu - Google Colab)
Runtime   : Python 3.11
Framework : TensorFlow 2.18.0, Keras

Dependencies:

| Library      | Version | Sumber      | Kegunaan                                 |
|--------------|---------|-------------|-------------------------------------------|
| Python       | 3.11    | Google Colab | Bahasa pemrograman utama                 |
| TensorFlow   | 2.18.0  | pip         | Implementasi EfficientNet-B6             |
| NumPy        | 1.26.4  | pip         | Operasi numerik                          |
| Pandas       | 2.2.2   | pip         | Pengolahan dataset                       |
| Scikit-learn | 1.5.2   | pip         | Evaluasi model                           |
| Matplotlib   | 3.10.0  | pip         | Visualisasi hasil                        |
| OpenCV       | 4.10.0  | pip         | Pembacaan citra                          |

Konfigurasi:

Config File     : Google Colab Notebook (05-kode/PRAKTIKUMB6(1).ipynb)
Random Seed     : 42

Hyperparameters :

- Model            : EfficientNet-B6
- Transfer Learning: Feature Extraction
- Input Size       : 224 × 224
- Epoch            : 25
- Batch Size       : 2
- Optimizer        : Adam
- Validation       : Single Split (80% Training, 20% Validation)

Callbacks :

- EarlyStopping
- ReduceLROnPlateau
- ModelCheckpoint

Reproducibility Check

[x] Dependency dan konfigurasi eksperimen telah didokumentasikan.

[x] Random seed ditetapkan pada Python, NumPy, dan TensorFlow.

[x] Implementasi model terdokumentasi pada notebook Google Colab (05-kode/PRAKTIKUMB6(1).ipynb).

[x] Repository GitHub menyimpan proposal, notebook implementasi, output eksperimen, manuskrip, laporan penelitian, dan dokumentasi pendukung.
```

---


## Latihan 1 — Environment Specification

Dokumentasikan environment yang digunakan selama eksperimen.

| Komponen | Spesifikasi |
|---|---|
| CPU | Intel Xeon (Google Colab Runtime) |
| RAM | ±12 GB RAM |
| GPU | NVIDIA Tesla T4 atau GPU yang tersedia pada Google Colab Free |
| OS | Linux (Ubuntu - Google Colab) |
| Runtime | Python 3.11 |
| Framework | TensorFlow 2.18.0 dan Keras |
| Random Seed | 42 |

### Dependencies

| Library | Version | Alasan Dibutuhkan |
|---|---|---|
| Python | 3.11 | Bahasa pemrograman utama |
| TensorFlow | 2.18.0 | Implementasi model EfficientNet-B6 |
| NumPy | 1.26.4 | Operasi numerik |
| Pandas | 2.2.2 | Pengolahan dataset |
| Scikit-learn | 1.5.2 | Perhitungan Accuracy, Precision, Recall, F1-Score, Confusion Matrix |
| Matplotlib | 3.10.0 | Visualisasi hasil pelatihan |
| OpenCV | 4.10.0 | Membaca dan memproses citra |

---

## Latihan 2 — Dokumentasi Pelaksanaan Eksperimen

Penelitian ini menggunakan satu kali proses pelatihan sesuai rancangan penelitian pada proposal dengan metode **single split** (80% data latih dan 20% data validasi). Oleh karena itu, pengujian repeatability tidak dilakukan karena penelitian berfokus pada satu skenario eksperimen menggunakan lingkungan **Google Colab Free**. Hasil pelatihan tersebut selanjutnya digunakan sebagai dasar evaluasi, analisis, penyusunan laporan penelitian, dan manuskrip ilmiah.

| Run | Seed | Metrik Utama | Status |
|---|---|---|---|
| 1 | 42 | Accuracy | Completed |

**Hasil yang diperoleh:**

| Run | Accuracy | Status |
|---|---|---|
| 1 | 63,04% | Completed |

### Checklist kontrol yang diterapkan

- ☑ Random seed ditetapkan pada Python, NumPy, dan TensorFlow.
- ☑ Cache dibersihkan sebelum proses pelatihan.
- ☑ Konfigurasi eksperimen yang sama digunakan pada setiap pengujian.
- ☑ Dataset menggunakan pembagian data (train-validation split) yang sama.

---

## Latihan 3 — README Eksperimen

```
# Judul Eksperimen

Klasifikasi Penyakit Daun Padi Menggunakan EfficientNet-B6 dengan Pendekatan Transfer Learning

## 1. Environment

Google Colab

Python 3.11

TensorFlow 2.18.0

GPU NVIDIA Tesla T4 atau GPU yang tersedia pada Google Colab Free

## 2. Installation

Instalasi library dilakukan secara manual menggunakan pip:

pip install tensorflow==2.18.0
pip install numpy==1.26.4
pip install pandas==2.2.2
pip install matplotlib==3.10.0
pip install scikit-learn==1.5.2
pip install opencv-python-headless==4.10.0

## 3. Data

Dataset Rice Leafs

Jumlah data : 3.355 citra

Jumlah kelas : 4

- Brown Spot
- Healthy
- Hispa
- Leaf Blast

## 4. Execution

Eksperimen dijalankan menggunakan Google Colab mulai dari proses import library, preprocessing dataset, data augmentation, pembangunan model EfficientNet-B6, proses pelatihan menggunakan transfer learning, hingga evaluasi model. Hasil pelatihan kemudian dievaluasi menggunakan Accuracy, Precision, Recall, F1-Score, Confusion Matrix, dan Classification Report.

## 5. Configuration

Model :
EfficientNet-B6

Transfer Learning :
Feature Extraction

Input Size :
224 × 224

Epoch :
25

Batch Size :
2

Validation :
Single Split (80% Training, 20% Validation)

Optimizer :
Adam

Random Seed :
42

Callbacks :
- EarlyStopping
- ReduceLROnPlateau
- ModelCheckpoint

## 6. Output

- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix
- Classification Report
- Grafik Accuracy
- Grafik Loss
- training_history.csv
- evaluation_metrics.csv
- research_summary.csv
- Training Log (.txt)
- Model (.keras)
- Model (.h5)
```

---

## Refleksi

> Apakah eksperimen Anda saat ini bisa direproduksi oleh orang lain tanpa bantuan Anda? Komponen apa yang masih hilang?

**Level saat ini:**

- ☑ Repeatability
- ☐ Reproducibility

**Catatan:**

Eksperimen telah memiliki dokumentasi yang mencakup proposal penelitian, notebook implementasi, dataset, hasil pelatihan, manuskrip, laporan penelitian, serta dokumentasi pendukung pada repository GitHub. Dokumentasi tersebut memungkinkan penelitian dipahami dan direproduksi pada lingkungan yang serupa. Untuk meningkatkan reproducibility, penelitian selanjutnya dapat menambahkan file requirements.txt atau environment.yml yang memuat seluruh dependency beserta versinya secara otomatis sehingga eksperimen lebih mudah direproduksi pada lingkungan yang berbeda. Meskipun demikian, dokumentasi yang tersedia telah memadai untuk mendukung pelaksanaan kembali eksperimen pada lingkungan Google Colab dengan konfigurasi yang sama.
