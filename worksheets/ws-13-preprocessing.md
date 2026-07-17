# WS-13: Data Preprocessing

> **Bab 13 — Preprocessing & Persiapan Data untuk Analisis**

---

## Ringkasan Materi

### Data Refinement Pipeline

```
Raw Data → Cleaning → Transformation → Normalization → Processed Data → Analysis Ready
```

Setiap tahap memiliki tujuan berbeda. **Preprocessing bukan langkah teknis biasa** — setiap keputusan preprocessing adalah keputusan riset yang bisa mengubah kesimpulan.

### Empat Prinsip Preprocessing

| Prinsip | Deskripsi |
|---------|----------|
| **Consistency** | Metode sama untuk data yang sama |
| **Transparency** | Setiap langkah terdokumentasi |
| **Reproducibility** | Orang lain bisa mengulang dengan hasil sama |
| **Minimal Distortion** | Ubah sesedikit mungkin; jika normalisasi tidak perlu, jangan lakukan |

### Cleaning Triad

| Masalah | Strategi | Risiko |
|---------|---------|--------|
| **Missing values** | | |
| — Listwise deletion | Missing < 5%, random | Data loss |
| — Mean/median imputation | Sedikit missing, dist. normal | Mengurangi variabilitas |
| — Model-based imputation | Banyak missing, pola sistematis | Introduces dependency |
| — Flag & separate | Missing karena alasan substantif | Kompleksitas analisis |
| **Duplikat** | Identifikasi → verifikasi → hapus | False positive (data mirip ≠ duplikat) |
| **Error format** | Standardisasi tipe, encoding | Kehilangan informasi saat konversi |

### Normalisasi — Kapan & Metode Mana

| Metode | Formula | Output | Sensitif Outlier? |
|--------|---------|--------|-------------------|
| Min-max | (x-min)/(max-min) | [0, 1] | Ya |
| Z-score | (x-mean)/std | Unbounded | Lebih robust |
| Robust scaling | (x-median)/IQR | Unbounded | Paling robust |

**Kunci:** Parameter normalisasi harus dihitung dari **training set saja** — bukan seluruh data. Pelanggaran = **data leakage**.

### Data Leakage Prevention

Data leakage terjadi ketika informasi dari test set "bocor" ke preprocessing:
- Normalisasi parameter dari seluruh dataset ← **SALAH**
- Cross-validation dilakukan sebelum split ← **SALAH**
- Feature selection menggunakan label test set ← **SALAH**

### Jebakan Kognitif

1. "Preprocessing cuma teknis — tidak perlu detail" → bisa ubah kesimpulan
2. "Lebih banyak preprocessing = lebih bersih = lebih baik" → over-processing distorsi data
3. "Normalisasi selalu diperlukan" → belum tentu, tergantung metode analisis
4. "Imputation sama untuk semua situasi" → strategi harus sesuai konteks

---


## Template A.13 — Preprocessing Documentation Log

```
PREPROCESSING LOG

Dataset           : Rice Leafs (Kaggle)
Jumlah data awal  : 3.355 citra

Cleaning:

| Masalah | Jumlah Kasus | Penanganan | Justifikasi |
|---|---|---|---|
| Missing | 0 | Tidak ada tindakan | Dataset lengkap |
| Duplikat | 0 | Tidak ada tindakan | Tidak ditemukan citra duplikat pada dataset yang digunakan |
| Error | 0 | Tidak ada tindakan | Seluruh citra berhasil dibaca dan diproses |

Transformation:

| Transformasi | Variabel | Detail | Alasan |
|---|---|---|---|
| Resize | Seluruh citra | 224 × 224 piksel | Menyesuaikan input EfficientNet-B6 |
| Data Augmentation | Data latih | RandomFlip, RandomRotation, RandomZoom, RandomContrast | Meningkatkan variasi data latih dan mengurangi overfitting |
| Preprocessing | Seluruh citra | preprocess_input() EfficientNet | Menyesuaikan format input model pretrained |

Normalization

Metode    : preprocess_input() EfficientNet-B6

Alasan    : Model pretrained ImageNet memerlukan preprocessing bawaan agar distribusi piksel sesuai dengan saat model dilatih.

Parameter : Fungsi preprocess_input() diterapkan pada data setelah pembagian training dan validation sehingga tidak terjadi data leakage.

Leakage Check

[x] Parameter preprocessing diterapkan setelah train-validation split

[x] Tidak ada informasi validation/test yang digunakan pada proses training

[x] Pembagian data dilakukan sebelum proses pelatihan

Jumlah data akhir : 3.355 citra

Script tersedia : [x] Ya → Google Colab Notebook
```

---

## Latihan 1 — Cleaning Plan

Periksa dataset Anda (atau dataset contoh) dan dokumentasikan masalah yang ditemukan.

| Masalah | Jumlah Kasus | Penanganan | Justifikasi |
|---|---|---|---|
| Missing value | 0 | Tidak ada | Dataset lengkap |
| Duplikat | 0 | Tidak ada | Tidak ditemukan citra duplikat pada dataset yang digunakan |
| Error file | 0 | Tidak ada | Seluruh file berhasil dibaca TensorFlow |

**Jumlah data sebelum cleaning:** 3.355 citra
**Jumlah data setelah cleaning:** 3.355 citra
**Persentase data yang hilang/berubah:** 0%

---

## Latihan 2 — Normalisasi Decision

Tentukan apakah data Anda perlu normalisasi, dan jika ya, metode apa yang tepat.

| Variabel | Range Asli | Metode | Alasan |
|---|---|---|---|
| Nilai piksel citra | 0–255 | `preprocess_input()` EfficientNet-B6 | Menyesuaikan input model pretrained EfficientNet-B6 |

> Accuracy, Precision, Recall, dan F1-Score merupakan metrik evaluasi sehingga tidak melalui proses preprocessing maupun normalisasi.

**Apakah normalisasi diperlukan?** [v] Ya / [ ] Tidak

**Justifikasi:**
> Citra masukan diproses menggunakan fungsi preprocess_input() bawaan EfficientNet-B6 agar distribusi nilai piksel sesuai dengan karakteristik model pretrained ImageNet. Tidak dilakukan normalisasi tambahan seperti Min-Max Scaling atau Z-score karena sudah ditangani oleh fungsi preprocessing tersebut.

**Leakage check:**
- [v] Preprocessing dilakukan setelah train-validation split.
- [v] Tidak ada informasi data validasi yang digunakan selama pelatihan.

---

## Latihan 3 — Preprocessing Report

Buat ringkasan preprocessing lengkap — dokumentasi yang cukup bagi orang lain untuk mereplikasi.

```
PREPROCESSING SUMMARY

1. Dataset
Rice Leafs (Kaggle)

2. Data awal
3.355 citra
4 kelas

3. Cleaning

- Missing values : 0 kasus
- Duplikat : 0 kasus
- Error pembacaan file : 0 kasus

Dataset dipertahankan seluruhnya karena tidak ditemukan data yang perlu dihapus selama proses cleaning.

4. Transformation

- Resize citra menjadi 224 × 224 piksel
- Data augmentation menggunakan RandomFlip, RandomRotation, RandomZoom, dan RandomContrast
- Preprocessing menggunakan preprocess_input() EfficientNet-B6

5. Normalisasi

Metode :
preprocess_input() EfficientNet-B6

Parameter dihitung dari :
Fungsi preprocess_input() diterapkan pada data training dan validation setelah proses pembagian data sehingga tidak terjadi data leakage.

6. Data akhir

3.355 citra
4 kelas

7. Leakage Check

[v] Lulus
```

---

## Refleksi

> Apakah Anda pernah melakukan normalisasi "karena biasa dilakukan" tanpa mempertimbangkan apakah benar-benar diperlukan? Apa risiko over-preprocessing?

Pada awal mempelajari machine learning, saya menganggap bahwa normalisasi selalu diperlukan pada setiap penelitian. Setelah mempelajari karakteristik model EfficientNet-B6, saya memahami bahwa model pretrained telah menyediakan fungsi preprocess_input() yang dirancang khusus untuk menyesuaikan distribusi nilai piksel dengan data saat proses pretraining. Oleh karena itu, normalisasi tambahan seperti Min-Max Scaling atau Z-score tidak diperlukan pada penelitian ini.

Over-preprocessing dapat menyebabkan perubahan distribusi data yang sebenarnya tidak diperlukan sehingga berpotensi menurunkan performa model, menyulitkan proses reproduksi penelitian, dan meningkatkan risiko data leakage apabila preprocessing dilakukan sebelum pembagian data latih dan data validasi.
