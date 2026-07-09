# 04-data
Folder ini berisi dataset penelitian beserta hasil eksplorasi (Exploratory Data Analysis/EDA) yang dilakukan sebelum proses pelatihan model EfficientNet-B6.
Dataset yang digunakan merupakan **Rice Leafs Dataset** yang diperoleh dari Kaggle dan digunakan sebagai sumber data utama pada penelitian **Klasifikasi Penyakit Daun Padi Menggunakan EfficientNet-B6 dengan Pendekatan Transfer Learning**.
---
# Dataset
Nama Dataset
Rice Leafs Dataset
Sumber
Kaggle
Jumlah kelas
- Healthy
- BrownSpot
- Hispa
- LeafBlast
Total Dataset
3.355 citra
---
# Distribusi Dataset
Distribusi jumlah citra setiap kelas.
| Kelas | Jumlah |
|--------|-------:|
| Healthy | 1488 |
| LeafBlast | 779 |
| Hispa | 565 |
| BrownSpot | 523 |
| **Total** | **3355** |
File:
```
01-distribusi-dataset.png
```
Keterangan
Grafik menunjukkan bahwa dataset memiliki distribusi kelas yang tidak seimbang (imbalanced dataset), di mana kelas **Healthy** memiliki jumlah citra paling banyak dibandingkan kelas lainnya.
---
# Contoh Dataset
File
```
02-contoh-dataset.png
```
Keterangan
Berisi beberapa contoh citra dari masing-masing kelas penyakit daun padi.
Kelas yang ditampilkan meliputi:
- BrownSpot
- Healthy
- Hispa
- LeafBlast
Visualisasi ini digunakan untuk memastikan kualitas dataset sebelum dilakukan preprocessing.
---
# Distribusi Resolusi Gambar
File
```
03-distribusi-resolusi.png
```
Keterangan
Grafik memperlihatkan distribusi ukuran (width dan height) citra pada dataset Rice Leafs.
Karena ukuran citra tidak seragam, seluruh gambar diubah menjadi **224 × 224 piksel** agar sesuai dengan ukuran input model EfficientNet-B6.
---
# Pembagian Dataset
Dataset dibagi menjadi dua bagian.
| Dataset | Persentase |
|----------|-----------:|
| Training | 80% |
| Validation | 20% |
Pembagian dilakukan menggunakan fungsi **image_dataset_from_directory()** pada TensorFlow dengan parameter **validation_split = 0.2** sehingga data training dan validation berasal dari dataset yang sama tanpa terjadi data leakage.
---
# Metadata Dataset
| Informasi | Nilai |
|-----------|-------|
| Dataset | Rice Leafs |
| Total Gambar | 3355 |
| Jumlah Kelas | 4 |
| Format | JPG / PNG |
| Color Space | RGB |
| Ukuran Input Model | 224 × 224 Pixel |
| Training Split | 80% |
| Validation Split | 20% |
---
# Isi Folder
Folder ini berisi file berikut.
- README.md
- 01-distribusi-dataset.png
- 02-contoh-dataset.png
- 03-distribusi-resolusi.png
- dataset-info.md
---
# Catatan
Folder **04-data** hanya berisi dataset dan hasil eksplorasi data (Exploratory Data Analysis/EDA) sebelum proses pelatihan model.
Seluruh hasil pelatihan dan evaluasi model, seperti **history training**, **accuracy**, **loss**, **confusion matrix**, **classification report**, **grafik performa model**, serta **hasil prediksi**, disimpan pada folder **06-output** karena merupakan hasil eksperimen, bukan data mentah.
