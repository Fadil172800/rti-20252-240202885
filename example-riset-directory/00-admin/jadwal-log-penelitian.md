# Jadwal dan Log Pelaksanaan Penelitian

Dokumen ini berisi kronologi pelaksanaan penelitian mulai dari tahap penyusunan proposal hingga finalisasi laporan penelitian. Seluruh aktivitas disusun berdasarkan implementasi penelitian yang dilakukan menggunakan Google Colab dan model EfficientNet-B6 dengan pendekatan Transfer Learning.

---

## Informasi Penelitian

| Keterangan | Informasi |
|------------|-----------|
| **Nama Peneliti** | Syukron Nur Fadillah |
| **NIM** | 240202885 |
| **Program Studi** | S1 Teknik Informatika |
| **Universitas** | Universitas Putra Bangsa |
| **Judul Penelitian** | Klasifikasi Penyakit Daun Padi Menggunakan EfficientNet-B6 dengan Pendekatan Transfer Learning |
| **Dataset** | Rice Leafs (3.355 citra, 4 kelas: Healthy, Leaf Blast, Hispa, dan Brown Spot) |
| **Platform** | Google Colab Free |
| **Framework** | TensorFlow 2.x |
| **Bahasa Pemrograman** | Python |
| **Status Penelitian** | ✅ Selesai |

---

## Log Pelaksanaan

| Tanggal | Tahap | Deskripsi Kegiatan | Referensi |
|---------|-------|-----------|-----------|
| **20 Juni 2026** | Tahap 1 — Proposal & Revisi | Penyusunan proposal penelitian berdasarkan hasil analisis literatur (WS-01 s.d. WS-08). Revisi proposal meliputi penyempurnaan Research Question, hipotesis, variabel penelitian, metode eksperimen, serta penyesuaian dengan kemampuan komputasi Google Colab Free. | [01-proposal](../01-proposal/) |
| **21–22 Juni 2026** | Tahap 2 — Studi Literatur | Analisis jurnal utama Milano et al. (2024) serta beberapa penelitian pendukung mengenai EfficientNet dan klasifikasi penyakit daun tanaman. Identifikasi research gap dan penyusunan landasan teori penelitian. | [02-literatur](../02-literatur/) |
| **23 Juni 2026** | Tahap 3 — Persiapan Dataset & Environment | Mengunduh dataset Rice Leafs dari Kaggle (3.355 citra, 4 kelas), menyiapkan Google Colab, TensorFlow, NumPy, Pandas, Matplotlib, Scikit-learn, serta membangun struktur folder penelitian. | [04-data](../04-data/) • [05-kode](../05-kode/) |
| **24 Juni 2026** | Tahap 4 — Preprocessing Data | Melakukan pengecekan dataset, resize citra menjadi 224×224 piksel, pembagian data menggunakan stratified split 80% data latih dan 20% data validasi, serta membangun pipeline tf.data. | [05-kode](../05-kode/) |
| **25–27 Juni 2026** | Tahap 5 — Implementasi Model | Implementasi EfficientNet-B6 menggunakan bobot pretrained ImageNet dengan pendekatan transfer learning. Penambahan callback EarlyStopping, ReduceLROnPlateau, dan ModelCheckpoint. | [PRAKTIKUMB6.ipynb](../05-kode/PRAKTIKUMB6.ipynb) |
| **28 Juni 2026** | Tahap 6 — Pelatihan Model | Melakukan proses training model menggunakan Google Colab Free dengan batch size 2 dan maksimum 25 epoch. Proses berhenti otomatis menggunakan EarlyStopping pada epoch terbaik. | [05-kode](../05-kode/) • [06-output](../06-output/) |
| **29 Juni 2026** | Tahap 7 — Evaluasi Model | Menghasilkan Accuracy, Precision, Recall, F1-Score, Classification Report, Confusion Matrix, grafik akurasi, grafik loss, serta melakukan prediksi pada data validasi. | [06-output](../06-output/) |
| **30 Juni 2026** | Tahap 8 — Analisis Hasil | Analisis performa EfficientNet-B6 berdasarkan hasil evaluasi. Membandingkan hasil penelitian dengan jurnal acuan dan mengidentifikasi keterbatasan penelitian. | [07-manuskrip](../07-manuskrip/) |
| **1–5 Juli 2026** | Tahap 9 — Penyusunan Laporan | Penyusunan Bab Hasil dan Pembahasan, pengisian Worksheet WS-09 sampai WS-16, penyusunan tabel, grafik, confusion matrix, serta dokumentasi hasil eksperimen. | [07-manuskrip](../07-manuskrip/) • [08-laporan](../08-laporan/) |
| **6–9 Juli 2026** | Tahap 10 — Revisi & Finalisasi | Pemeriksaan konsistensi proposal dengan implementasi penelitian, revisi laporan berdasarkan hasil eksperimen, pengecekan referensi, serta penyusunan struktur repository penelitian. | [08-laporan](../08-laporan/) • [09-docs](../09-docs/) |
| **10 Juli 2026** | Tahap 11 — Dokumentasi Akhir | Finalisasi seluruh dokumen penelitian, penyusunan folder riset (00-admin sampai 09-docs), dan persiapan unggah ke GitHub Repository. | [Repository Penelitian](../) |

---

## Ringkasan Hasil Penelitian

| Metrik | Hasil |
|--------|------:|
| **Dataset** | 3.355 citra |
| **Data Training** | 2.684 citra (80%) |
| **Data Validasi** | 671 citra (20%) |
| **Jumlah Kelas** | 4 |
| **Model** | EfficientNet-B6 |
| **Pendekatan** | Transfer Learning |
| **Input Size** | 224 × 224 piksel |
| **Batch Size** | 2 |
| **Maksimum Epoch** | 25 |
| **Epoch Terbaik** | 12 |
| **Epoch Berjalan** | 17 |
| **Optimizer** | Adam |
| **Accuracy** | **65,42%** |
| **Precision** | 64,43% |
| **Recall** | 65,42% |
| **F1-Score** | 64,18% |

---

## Status Ringkas

| Tahap | Status |
|------|:------:|
| **Tahap 1 — Proposal & Revisi** | ✅ Selesai |
| **Tahap 2 — Studi Literatur** | ✅ Selesai |
| **Tahap 3 — Persiapan Dataset & Environment** | ✅ Selesai |
| **Tahap 4 — Preprocessing Data** | ✅ Selesai |
| **Tahap 5 — Implementasi Model EfficientNet-B6** | ✅ Selesai |
| **Tahap 6 — Pelatihan Model** | ✅ Selesai |
| **Tahap 7 — Evaluasi Model** | ✅ Selesai |
| **Tahap 8 — Analisis Hasil Penelitian** | ✅ Selesai |
| **Tahap 9 — Penyusunan Laporan Penelitian** | ✅ Selesai |
| **Tahap 10 — Finalisasi Dokumen** | ✅ Selesai |
| **Tahap 11 — Dokumentasi Penelitian** | ✅ Selesai |

---

## Checklist Penelitian

| No. | Komponen | Status |
|-----|----------|:------:|
| 1 | Proposal Penelitian | ☑ Selesai |
| 2 | Studi Literatur | ☑ Selesai |
| 3 | Dataset Rice Leafs | ☑ Selesai |
| 4 | Notebook Implementasi (Google Colab) | ☑ Selesai |
| 5 | Proses Training Model | ☑ Selesai |
| 6 | Evaluasi Model | ☑ Selesai |
| 7 | Laporan Penelitian | ☑ Selesai |
| 8 | Manuskrip Ilmiah | ☑ Selesai |
| 9 | Upload ke GitHub Repository | ☐ Dalam Proses |

---

## Korespondensi

| Tanggal | Pihak | Topik | Catatan | Status |
|---------|-------|-------|---------|:------:|
| 20 Juni 2026 | Dosen Pengampu | Penyusunan dan revisi proposal penelitian | Perbaikan Research Question dan metode eksperimen | ✅ Selesai |
| 5 Juli 2026 | Dosen Pengampu | Konsultasi hasil implementasi dan evaluasi model | Pembahasan mengenai akurasi model dan perbandingan dengan jurnal acuan | ✅ Selesai |
| 10 Juli 2026 | Dosen Pengampu | Finalisasi laporan penelitian | Pemeriksaan akhir laporan dan persiapan unggah repository | ✅ Selesai |

---

## Navigasi Repository

| Folder | Keterangan |
|--------|------------|
| [00-admin](../00-admin/) | Administrasi Penelitian |
| [01-proposal](../01-proposal/) | Proposal Penelitian |
| [02-literatur](../02-literatur/) | Studi Literatur |
| [03-teori](../03-teori/) | Landasan Teori |
| [04-data](../04-data/) | Dataset Penelitian |
| [05-kode](../05-kode/) | Implementasi Model |
| [06-output](../06-output/) | Hasil Pelatihan |
| [07-manuskrip](../07-manuskrip/) | Manuskrip |
| [08-laporan](../08-laporan/) | Laporan |
| [09-docs](../09-docs/) | Dokumentasi |

---

