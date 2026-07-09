# Training History

File

```
02-training-history.png
```

---

# Deskripsi

Gambar ini menampilkan perkembangan nilai **accuracy** dan **loss** selama proses pelatihan model EfficientNet-B6 menggunakan pendekatan Transfer Learning pada dataset Rice Leafs.

Model dilatih menggunakan pembagian data **80% training** dan **20% validation** selama proses eksperimen.

---

# Grafik Accuracy

Grafik accuracy menunjukkan peningkatan performa model pada data training dan validation selama proses pelatihan.

Observasi:

- Accuracy training meningkat secara bertahap pada setiap epoch.
- Accuracy validation relatif stabil dan memiliki nilai lebih tinggi dibandingkan accuracy training.
- Tidak terlihat penurunan accuracy validation yang signifikan sehingga model mampu melakukan generalisasi dengan cukup baik.

---

# Grafik Loss

Grafik loss menunjukkan perubahan nilai error selama proses pelatihan.

Observasi:

- Training loss mengalami penurunan secara konsisten.
- Validation loss juga cenderung menurun dan stabil pada akhir proses pelatihan.
- Tidak terlihat kenaikan loss yang ekstrem sehingga proses pelatihan berlangsung dengan baik.

---

# Ringkasan

Berdasarkan grafik training history, model EfficientNet-B6 berhasil mempelajari karakteristik citra daun padi dengan baik. Nilai accuracy mengalami peningkatan seiring bertambahnya epoch, sedangkan nilai loss menurun hingga mencapai kondisi yang relatif stabil. Hasil ini menunjukkan bahwa model telah berhasil dilatih menggunakan pendekatan Transfer Learning dan siap untuk dievaluasi menggunakan metrik Accuracy, Precision, Recall, F1-Score, Classification Report, serta Confusion Matrix.
