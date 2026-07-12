# 04 - Dataset Penelitian

Folder ini berisi dataset penelitian beserta hasil **Exploratory Data Analysis (EDA)** yang dilakukan sebelum proses pelatihan model **EfficientNet-B6**.

Dataset yang digunakan merupakan **Rice Leafs Dataset** yang diperoleh dari **Kaggle** dan digunakan sebagai sumber data utama pada penelitian **"Klasifikasi Penyakit Daun Padi Menggunakan EfficientNet-B6 dengan Pendekatan Transfer Learning"**.

Seluruh proses eksplorasi data dilakukan untuk memastikan kualitas dataset sebelum memasuki tahap preprocessing, pelatihan model, dan evaluasi.

---

## Informasi Dataset

| Keterangan | Informasi |
|------------|-----------|
| **Nama Dataset** | Rice Leafs Dataset |
| **Sumber** | Kaggle |
| **Total Citra** | 3.355 |
| **Jumlah Kelas** | 4 |
| **Kelas** | Healthy, Brown Spot, Hispa, Leaf Blast |
| **Format Gambar** | JPG / PNG |
| **Color Space** | RGB |
| **Ukuran Input Model** | 224 × 224 piksel |

---

## Distribusi Dataset

Distribusi jumlah citra pada masing-masing kelas ditampilkan pada gambar berikut.

**File:**

- `01-distribusi-dataset.png`

| Kelas | Jumlah |
|--------|-------:|
| Healthy | 1488 |
| Leaf Blast | 779 |
| Hispa | 565 |
| Brown Spot | 523 |
| **Total** | **3355** |

**Keterangan**

Visualisasi menunjukkan bahwa dataset memiliki distribusi kelas yang **tidak seimbang (imbalanced dataset)**. Kelas **Healthy** memiliki jumlah citra paling banyak, sedangkan **Brown Spot** memiliki jumlah citra paling sedikit. Kondisi ini menjadi salah satu faktor yang dapat memengaruhi performa model klasifikasi.

---

## Contoh Dataset

**File:**

- `02-contoh-dataset.png`

Visualisasi ini menampilkan contoh citra dari setiap kelas pada dataset.

Kelas yang ditampilkan meliputi:

- Brown Spot
- Healthy
- Hispa
- Leaf Blast

**Keterangan**

Tahap ini dilakukan untuk memastikan bahwa setiap kelas memiliki kualitas citra yang baik dan sesuai sebelum dilakukan preprocessing.

---

## Distribusi Resolusi Gambar

**File:**

- `03-distribusi-resolusi.png`

**Keterangan**

Visualisasi menunjukkan distribusi ukuran (width dan height) citra pada dataset Rice Leafs.

Karena ukuran citra tidak seragam, seluruh gambar diubah menjadi **224 × 224 piksel** agar sesuai dengan ukuran input model **EfficientNet-B6**.

---

## Pembagian Dataset

Proses pembagian dataset dilakukan menggunakan fungsi `image_dataset_from_directory()` dari TensorFlow.

| Dataset | Persentase |
|----------|-----------:|
| Training | 80% |
| Validation | 20% |

**Keterangan**

Pembagian dataset menggunakan parameter `validation_split = 0.2` sehingga data training dan validation berasal dari dataset yang sama tanpa menyebabkan **data leakage**.

Informasi lebih lengkap mengenai proses pembagian dataset tersedia pada:

- [04-pembagian-data.md](04-pembagian-data.md)

---

## Metadata Dataset

Informasi rinci mengenai dataset tersedia pada:

- [dataset-info.md](dataset-info.md)
- [dataset-statistik.md](dataset-statistik.md)

Ringkasan metadata ditampilkan pada tabel berikut.

| Informasi | Nilai |
|-----------|-------|
| Dataset | Rice Leafs |
| Total Gambar | 3.355 |
| Jumlah Kelas | 4 |
| Format | JPG / PNG |
| Color Space | RGB |
| Ukuran Input | 224 × 224 piksel |
| Training Split | 80% |
| Validation Split | 20% |

---

## Isi Folder

| Berkas | Deskripsi |
|--------|-----------|
| `01-distribusi-dataset.png` | Visualisasi distribusi jumlah citra setiap kelas. |
| `02-contoh-dataset.png` | Contoh citra dari masing-masing kelas. |
| `03-distribusi-resolusi.png` | Visualisasi distribusi resolusi citra. |
| `04-pembagian-data.md` | Dokumentasi proses pembagian dataset. |
| `dataset-info.md` | Informasi umum dataset. |
| `dataset-statistik.md` | Statistik dataset penelitian. |
| `README.md` | Dokumentasi folder dataset. |

---

## Hubungan dengan Penelitian

Dataset pada folder ini digunakan sebagai dasar dalam:

- Proses preprocessing data.
- Pelatihan model EfficientNet-B6.
- Evaluasi performa model.
- Analisis hasil penelitian.

Seluruh implementasi model menggunakan dataset yang terdokumentasi pada folder ini.

---

## Keterkaitan dengan Repository

| Folder | Deskripsi |
|---------|-----------|
| [00-admin](../00-admin/) | Administrasi penelitian |
| [01-proposal](../01-proposal/) | Proposal penelitian |
| [02-literatur](../02-literatur/) | Studi literatur |
| [03-teori](../03-teori/) | Landasan teori |
| [05-kode](../05-kode/) | Implementasi model EfficientNet-B6 |
| [06-output](../06-output/) | Hasil pelatihan dan evaluasi model |
| [07-manuskrip](../07-manuskrip/) | Manuskrip penelitian |
| [08-laporan](../08-laporan/) | Laporan penelitian |
| [09-docs](../09-docs/) | Dokumentasi penelitian |

---

## Catatan

Folder **04-data** hanya berisi dataset beserta hasil **Exploratory Data Analysis (EDA)** yang dilakukan sebelum proses pelatihan model.

Seluruh hasil eksperimen, seperti **training history**, **akurasi**, **loss**, **confusion matrix**, **classification report**, **grafik performa model**, **model hasil pelatihan**, serta **hasil prediksi**, didokumentasikan pada folder **06-output** karena merupakan keluaran dari proses eksperimen, bukan bagian dari data awal penelitian.
