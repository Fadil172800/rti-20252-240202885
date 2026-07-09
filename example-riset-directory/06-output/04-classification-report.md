# Classification Report

## Deskripsi

Classification Report merupakan hasil evaluasi model EfficientNet-B6 pada data validasi menggunakan metrik Precision, Recall, F1-Score, dan Accuracy.

---

## Hasil Evaluasi

| Kelas | Precision | Recall | F1-Score | Support |
|-------|----------:|-------:|---------:|--------:|
| BrownSpot | 0.6667 | 0.6731 | 0.6699 | 104 |
| Healthy | 0.6439 | 0.9161 | 0.7562 | 298 |
| Hispa | 0.3250 | 0.1150 | 0.1699 | 113 |
| LeafBlast | 0.6569 | 0.4295 | 0.5194 | 156 |

---

## Ringkasan Performa

| Metrik | Nilai |
|--------|-------:|
| Accuracy | 0.6304 |
| Macro Average Precision | 0.5731 |
| Macro Average Recall | 0.5334 |
| Macro Average F1-Score | 0.5289 |
| Weighted Average Precision | 0.5967 |
| Weighted Average Recall | 0.6304 |
| Weighted Average F1-Score | 0.5890 |

---

## Interpretasi

- Model memperoleh **accuracy sebesar 63,04%** pada data validasi.
- Kelas **Healthy** memiliki nilai recall tertinggi (0.9161), menunjukkan bahwa sebagian besar citra daun sehat berhasil dikenali dengan baik.
- Kinerja model pada kelas **Hispa** masih rendah dengan F1-Score sebesar 0.1699, sehingga masih terdapat kesalahan klasifikasi pada kelas tersebut.
- Hasil Classification Report digunakan bersama Confusion Matrix untuk mengevaluasi performa model pada setiap kelas penyakit daun padi.

---

## File Pendukung

```
05-classification-report.png
```

File tersebut merupakan screenshot hasil Classification Report yang dihasilkan langsung dari Google Colab setelah proses evaluasi model selesai.
