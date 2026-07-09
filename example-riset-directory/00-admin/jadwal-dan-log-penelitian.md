# Jadwal & Log Pelaksanaan Penelitian

Nama: Syukron Nur Fadillah
NIM: 240202885
Judul: Klasifikasi Penyakit Daun Padi Menggunakan EfficientNet-B6 dengan Pendekatan Transfer Learning
Dataset: Rice Leafs (3.355 citra, 4 kelas)
Platform: Google Colab Free (Python 3, TensorFlow 2.x)

Catatan kronologis pelaksanaan penelitian berdasarkan proposal, implementasi pada Google Colab, dan hasil eksperimen.

## Log Pelaksanaan

| Tanggal             | Tahap                                     | Aktivitas                                                                                                                                                                                                                                                            | Referensi                      |
| ------------------- | ----------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------ |
| **20 Juni 2026**    | Tahap 1 — Proposal & Revisi               | Penyusunan proposal penelitian berdasarkan hasil analisis literatur (WS-01 s.d. WS-08). Revisi proposal meliputi penyempurnaan Research Question, hipotesis, variabel penelitian, metode eksperimen, serta penyesuaian dengan kemampuan komputasi Google Colab Free. | `01-proposal/`                 |
| **21–22 Juni 2026** | Tahap 2 — Studi Literatur                 | Analisis jurnal utama Milano et al. (2024) serta beberapa penelitian pendukung mengenai EfficientNet dan klasifikasi penyakit daun tanaman. Identifikasi research gap dan penyusunan landasan teori penelitian.                                                      | `02-literatur/`                |
| **23 Juni 2026**    | Tahap 3 — Persiapan Dataset & Environment | Mengunduh dataset Rice Leafs dari Kaggle (3.355 citra, 4 kelas), menyiapkan Google Colab, TensorFlow, NumPy, Pandas, Matplotlib, Scikit-learn, serta membangun struktur folder penelitian.                                                                           | `04-data/`, `05-kode/`         |
| **24 Juni 2026**    | Tahap 4 — Preprocessing Data              | Melakukan pengecekan dataset, resize citra menjadi 224×224 piksel, pembagian data menggunakan stratified split 80% data latih dan 20% data validasi, serta membangun pipeline tf.data.                                                                               | `05-kode/`                     |
| **25–27 Juni 2026** | Tahap 5 — Implementasi Model              | Implementasi EfficientNet-B6 menggunakan bobot pretrained ImageNet dengan pendekatan transfer learning. Penambahan callback EarlyStopping, ReduceLROnPlateau, dan ModelCheckpoint.                                                                                   | `05-kode/PRAKTIKUMB6.ipynb`    |
| **28 Juni 2026**    | Tahap 6 — Pelatihan Model                 | Melakukan proses training model menggunakan Google Colab Free dengan batch size 2 dan maksimum 25 epoch. Proses berhenti otomatis menggunakan EarlyStopping pada epoch terbaik.                                                                                      | `05-kode/`, `06-output/`       |
| **29 Juni 2026**    | Tahap 7 — Evaluasi Model                  | Menghasilkan Accuracy, Precision, Recall, F1-Score, Classification Report, Confusion Matrix, grafik akurasi, grafik loss, serta melakukan prediksi pada data validasi.                                                                                               | `06-output/`                   |
| **30 Juni 2026**    | Tahap 8 — Analisis Hasil                  | Analisis performa EfficientNet-B6 berdasarkan hasil evaluasi. Membandingkan hasil penelitian dengan jurnal acuan dan mengidentifikasi keterbatasan penelitian.                                                                                                       | `07-manuskrip/`                |
| **1–5 Juli 2026**   | Tahap 9 — Penyusunan Laporan              | Penyusunan Bab Hasil dan Pembahasan, pengisian Worksheet WS-09 sampai WS-16, penyusunan tabel, grafik, confusion matrix, serta dokumentasi hasil eksperimen.                                                                                                         | `07-manuskrip/`, `08-laporan/` |
| **6–9 Juli 2026**   | Tahap 10 — Revisi & Finalisasi            | Pemeriksaan konsistensi proposal dengan implementasi penelitian, revisi laporan berdasarkan hasil eksperimen, pengecekan referensi, serta penyusunan struktur repository penelitian.                                                                                 | `08-laporan/`, `09-docs/`      |
| **10 Juli 2026**    | Tahap 11 — Dokumentasi Akhir              | Finalisasi seluruh dokumen penelitian, penyusunan folder riset (00-admin sampai 09-docs), dan persiapan unggah ke GitHub Repository.                                                                                                                                 | Seluruh folder penelitian      |

Hasil Utama Penelitian

| Metrik         |                             Hasil |
| -------------- | --------------------------------: |
| Dataset        |                       3.355 citra |
| Jumlah Kelas   |                                 4 |
| Pembagian Data |     80% Training : 20% Validation |
| Model          |                   EfficientNet-B6 |
| Pendekatan     |                 Transfer Learning |
| Input Size     |                  224 × 224 piksel |
| Batch Size     |                                 2 |
| Maksimum Epoch |                                25 |
| Optimizer      |                              Adam |
| Accuracy       |                        **63,04%** |
| Precision      | Berdasarkan Classification Report |
| Recall         | Berdasarkan Classification Report |
| F1-Score       | Berdasarkan Classification Report |


## Status Ringkas

Status Ringkas
✅ Tahap 1 — Proposal & Revisi
✅ Tahap 2 — Studi Literatur
✅ Tahap 3 — Persiapan Dataset
✅ Tahap 4 — Preprocessing
✅ Tahap 5 — Implementasi Model
✅ Tahap 6 — Pelatihan Model
✅ Tahap 7 — Evaluasi Model
✅ Tahap 8 — Analisis Hasil
✅ Tahap 9 — Penyusunan Laporan
✅ Tahap 10 — Finalisasi
✅ Tahap 11 — Dokumentasi Penelitian

## Checklist Sebelum Pengumpulan

- [x] Proposal telah direvisi sesuai masukan dosen
- [x] Dataset Rice Leafs telah digunakan sesuai proposal
- [x] Script Python (Google Colab) selesai dan dapat dijalankan kembali
- [x] Model EfficientNet-B6 berhasil dilatih menggunakan pendekatan transfer learning
- [x] Accuracy, Precision, Recall, F1-Score, Classification Report, dan Confusion Matrix telah dihasilkan
- [x] Model hasil pelatihan (.keras/.h5) telah disimpan
- [x] Worksheet WS-01 s.d. WS-16 telah diselesaikan
- [x] Laporan penelitian telah diselesaikan
- [x] Struktur folder riset (00-admin s.d. 09-docs) telah lengkap
- [ ] Seluruh file telah diunggah ke GitHub Repository
- [ ] 
## Korespondensi

| Tanggal      | Pihak          | Topik                                            | Status    |
| ------------ | -------------- | ------------------------------------------------ | --------- |
| 20 Juni 2026 | Dosen Pengampu | Penyusunan dan revisi proposal penelitian        | ✅ Selesai |
| 5 Juli 2026  | Dosen Pengampu | Konsultasi hasil implementasi dan evaluasi model | ✅ Selesai |
| 10 Juli 2026 | Dosen Pengampu | Finalisasi laporan penelitian                    | ✅ Selesai |

