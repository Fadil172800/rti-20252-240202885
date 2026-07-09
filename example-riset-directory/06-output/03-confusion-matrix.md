# Confusion Matrix

## Hasil Evaluasi Model

Confusion Matrix yang diperoleh dari pengujian model EfficientNet-B6 adalah sebagai berikut.

| Actual \ Predicted | BrownSpot | Healthy | Hispa | LeafBlast |
|--------------------|----------:|--------:|-------:|----------:|
| BrownSpot | 70 | 27 | 1 | 6 |
| Healthy | 6 | 273 | 13 | 6 |
| Hispa | 0 | 77 | 13 | 23 |
| LeafBlast | 29 | 47 | 13 | 67 |

## Keterangan

- Model mampu mengklasifikasikan kelas **Healthy** dengan paling baik.
- Kesalahan klasifikasi masih cukup tinggi pada kelas **Hispa** dan **LeafBlast**.
- Confusion Matrix digunakan untuk mengetahui distribusi prediksi benar dan salah pada setiap kelas.
