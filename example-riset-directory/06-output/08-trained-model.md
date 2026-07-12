# 08 - Trained Model

Dokumen ini menjelaskan model hasil pelatihan yang diperoleh pada penelitian **"Klasifikasi Penyakit Daun Padi Menggunakan EfficientNet-B6 dengan Pendekatan Transfer Learning"**.

Model disimpan menggunakan format **TensorFlow Keras (.keras)** sehingga dapat digunakan kembali untuk proses inferensi (prediksi) maupun pengembangan penelitian selanjutnya tanpa perlu melakukan proses pelatihan ulang.

---

# Informasi Model

| Komponen | Keterangan |
|----------|------------|
| Nama Model | `best_efficientnetb6.keras` |
| Arsitektur | EfficientNet-B6 |
| Pendekatan | Transfer Learning |
| Framework | TensorFlow Keras |
| Format File | `.keras` |
| Ukuran Model | ±158 MB |
| Platform Training | Google Colab Free |

---

# Konfigurasi Pelatihan

Model terbaik dihasilkan menggunakan konfigurasi sebagai berikut.

| Parameter | Nilai |
|-----------|-------|
| Dataset | Rice Leafs |
| Jumlah Dataset | 3.355 citra |
| Jumlah Kelas | 4 |
| Input Size | 224 × 224 piksel |
| Batch Size | 2 |
| Epoch Maksimum | 25 |
| Optimizer | Adam |
| Loss Function | Sparse Categorical Crossentropy |
| Accuracy | **63,04%** |

---

# ModelCheckpoint

Model disimpan secara otomatis menggunakan callback **ModelCheckpoint** selama proses pelatihan.

Model yang disimpan merupakan model dengan performa terbaik berdasarkan nilai **Validation Accuracy**, sehingga model tersebut digunakan pada proses evaluasi dan prediksi.

---

# Unduh Model

Karena ukuran file model melebihi batas maksimum penyimpanan GitHub (**100 MB**), file model tidak disertakan pada repository ini.

Model dapat diunduh melalui Google Drive berikut.

**Nama File**

`best_efficientnetb6.keras`

# Unduh Model

Karena ukuran file model melebihi batas maksimum penyimpanan GitHub (**100 MB**), file **best_efficientnetb6.keras** tidak disertakan pada repository ini.

Model hasil pelatihan dapat diunduh melalui tautan berikut.

| Informasi | Keterangan |
|-----------|------------|
| Nama Model | `best_efficientnetb6.keras` |
| Format | `.keras` |
| Ukuran | ±158 MB |
| Link Unduhan | **[Google Drive - best_efficientnetb6.keras](https://drive.google.com/file/d/1mXJlk0n4VKApzQjJJVQ1el_oqPn4RmHL/view?usp=sharing)** |

Atau langsung klik tautan berikut:

👉 **[Unduh Model EfficientNet-B6 (.keras)](https://drive.google.com/file/d/1mXJlk0n4VKApzQjJJVQ1el_oqPn4RmHL/view?usp=sharing)**

---

# Cara Menggunakan Model

Model dapat dimuat kembali menggunakan TensorFlow Keras.

```python
import tensorflow as tf

model = tf.keras.models.load_model("best_efficientnetb6.keras")
```

Setelah model berhasil dimuat, model dapat digunakan untuk melakukan prediksi terhadap citra daun padi baru.

---

# Hubungan dengan Repository

Dokumen ini berkaitan dengan beberapa folder berikut.

| Folder | Deskripsi |
|---------|-----------|
| [04-data](../04-data/) | Dataset penelitian yang digunakan untuk pelatihan model. |
| [05-kode](../05-kode/) | Notebook implementasi EfficientNet-B6. |
| [06-output](../06-output/) | Hasil pelatihan, evaluasi model, dan visualisasi penelitian. |
| [07-manuskrip](../07-manuskrip/) | Manuskrip penelitian. |
| [08-laporan](../08-laporan/) | Laporan penelitian lengkap. |

---

# Catatan

Model ini merupakan hasil akhir penelitian dan digunakan untuk menghasilkan seluruh metrik evaluasi, Confusion Matrix, Classification Report, serta contoh hasil prediksi yang terdapat pada folder **06-output**.

Apabila notebook pada folder **05-kode** dijalankan kembali menggunakan dataset dan konfigurasi yang sama, maka model dengan karakteristik serupa dapat direproduksi.
