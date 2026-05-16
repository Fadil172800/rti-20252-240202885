# WS-07: Experimental Design & Validity

> **Bab 7 — Experimental Design & Validity**

---

## Ringkasan Materi

### Correlation ≠ Causality

Kausalitas membutuhkan 3 syarat:
1. **Covariance** — X dan Y bergerak bersama
2. **Temporal precedence** — X berubah sebelum Y
3. **Elimination of alternatives** — Tidak ada faktor lain yang menjelaskan Y

Controlled experiment adalah satu-satunya metode yang bisa membuktikan kausalitas.

### Empat Jenis Validitas

| Jenis | Pertanyaan | Ancaman Umum |
|-------|-----------|-------------|
| **Internal** | Apakah hubungan IV→DV nyata? | Confounding variable, selection bias |
| **External** | Apakah bisa digeneralisasi? | Dataset terlalu spesifik |
| **Construct** | Apakah mengukur konsep yang benar? | Metrik tidak sesuai |
| **Conclusion** | Apakah kesimpulan statistik valid? | Sample size kecil, uji salah |

Internal dan external validity sering berkonflik: semakin terkontrol (internal kuat) → semakin artificial (external lemah).

### Tiga Tipe Eksperimen dalam Riset TI

| Tipe | Deskripsi | Kapan Digunakan |
|------|----------|----------------|
| **Comparison Study** | Metode A vs B pada kondisi identik | Membandingkan pendekatan berbeda |
| **Ablation Study** | Full system → lepas komponen satu per satu | Mengukur kontribusi tiap komponen |
| **Parameter Study** | Variasikan satu parameter, amati dampak | Uji sensitifitas/robustness |

### Fairness dalam Perbandingan

Perbandingan yang adil = **kondisi identik** untuk semua metode: dataset sama, preprocessing sama, tuning effort sebanding, environment sama, metrik sama.

Contoh tidak adil: Transformer (30 fitur tambahan + Bayesian optimization) vs RF (default params) → hasilnya misleading.

### Threats to Validity = Diidentifikasi Sebelum Eksperimen

Ancaman validitas harus diidentifikasi **sebelum** eksperimen dan mitigasinya dirancang sebagai bagian dari desain — bukan ditulis sebagai boilerplate setelah selesai.

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Tujuan testing | Memastikan sistem memenuhi requirement | Membuktikan hubungan kausal antar variabel |
| Baseline | Versi sebelumnya (last release) | Metode tervalidasi dari literatur |
| Kegagalan | Bug → fix → release | H₀ tidak ditolak → tetap kontribusi ilmiah |
| Sukses | 100% test pass | Evidence valid — mendukung atau menolak hipotesis |

### Istilah Penting

- **Causality** — Hubungan sebab-akibat (covariance + temporal + elimination)
- **Controlled Experiment** — Ubah satu variabel, kontrol sisanya, amati efek
- **Fairness** — Semua metode diuji pada kondisi yang benar-benar identik
- **Threats to Validity** — Faktor yang bisa melemahkan kesimpulan jika tidak dimitigasi
- **Conclusion Validity** — Validitas statistik: power, sample size, uji yang tepat

---

## Template A.7 — Desain Eksperimen Lengkap

```
EXPERIMENT DESIGN

Research Question :
Apakah metode EfficientNet-B6 menghasilkan accuracy dan F1-Score yang lebih tinggi dibandingkan CNN standar pada klasifikasi penyakit daun padi?

Hypothesis :
EfficientNet-B6 memiliki accuracy dan F1-Score lebih tinggi dibanding CNN standar pada dataset citra daun padi.

Tipe Eksperimen :
[X] Comparison  [ ] Ablation  [ ] Parameter

Kondisi Eksperimen:

| Kondisi | Deskripsi | IV Value | CV Settings |
|---------|-----------|----------|-------------|
| Control | Model klasifikasi dasar | CNN Standar | Dataset 3355 citra, epoch 50, input size 224 |
| Treatment | Model deep learning modern | EfficientNet-B6 | Dataset 3355 citra, epoch 50, input size 224 |

Fairness Checklist:

[x] Dataset identik untuk semua kondisi (Menggunakan dataset citra daun padi yang sama).
[x] Preprocessing setara (Resize citra dan preprocessing dilakukan dengan cara yang sama).
[x] Tuning effort setara (Kedua model menggunakan jumlah epoch dan parameter training yang sama).
[x] Environment identik (Training dilakukan pada hardware dan software environment yang sama).
[x] Metrik evaluasi sama (Accuracy, Precision, Recall, dan F1-Score).

Threat Analysis:

| Threat Type | Ancaman Spesifik | Mitigasi |
|-------------|-----------------|----------|
| Internal | Perbedaan performa hardware saat training | Menggunakan perangkat dan environment yang sama |
| External | Dataset hanya berasal dari satu sumber | Menggunakan beberapa kelas penyakit daun padi |
| Construct | Accuracy tidak cukup menggambarkan performa | Menambahkan F1-Score sebagai secondary metric |
| Conclusion | Hasil dipengaruhi random seed training | Melakukan pengujian berulang menggunakan cross-validation |

Statistical Plan:

Uji statistik   :Perbandingan rata-rata accuracy dan F1-Score antar model.

Justifikasi     :Digunakan untuk mengetahui apakah EfficientNet-B6 benar-benar lebih baik dibanding CNN standar.

Alpha           :0.05

Effect size min :Perbedaan accuracy minimal 3%.
```

---

## Latihan 1 — Desain Eksperimen

Susun desain eksperimen berdasarkan RQ, variabel, dan sistem dari WS-04 sampai WS-06.

**RQ:** Apakah metode EfficientNet-B6 menghasilkan accuracy dan F1-Score yang lebih tinggi dibandingkan CNN standar pada klasifikasi penyakit daun padi?
**Tipe eksperimen:** [X] Comparison / [ ] Ablation / [ ] Parameter

| Kondisi   | Deskripsi                               | IV Value        | CV Settings                  |
| --------- | --------------------------------------- | --------------- | ---------------------------- |
| Control   | Klasifikasi menggunakan CNN standar     | CNN Standar     | Dataset 3355 citra, epoch 50 |
| Treatment | Klasifikasi menggunakan EfficientNet-B6 | EfficientNet-B6 | Dataset 3355 citra, epoch 50 |


---

## Latihan 2 — Fairness Checklist

Evaluasi apakah desain eksperimen di Latihan 1 sudah fair.

| Kriteria                 | Status   | Detail                                          |
| ------------------------ | -------- | ----------------------------------------------- |
| **Dataset identik**      | ✅ Setara | Menggunakan dataset citra daun padi yang sama   |
| **Preprocessing setara** | ✅ Setara | Resize dan preprocessing citra sama             |
| **Tuning effort setara** | ✅ Setara | Jumlah epoch dan parameter training dibuat sama |
| **Environment identik**  | ✅ Setara | Training dilakukan pada perangkat yang sama     |
| **Metrik evaluasi sama** | ✅ Setara | Accuracy, Recall, Precision, dan F1-Score       |


**Ada yang tidak fair?** [ ] Ya / [X] Tidak


---

## Latihan 3 — Threat Analysis

Identifikasi ancaman validitas untuk desain eksperimen ini.

| Threat Type | Ancaman Spesifik                             | Mitigasi                                            |
| ----------- | -------------------------------------------- | --------------------------------------------------- |
| Internal    | Performa model dipengaruhi spesifikasi GPU   | Menggunakan hardware yang sama                      |
| External    | Dataset belum mewakili semua kondisi nyata   | Menambahkan variasi data jika memungkinkan          |
| Construct   | Accuracy terlalu tinggi pada kelas mayoritas | Menggunakan F1-Score untuk evaluasi tambahan        |
| Conclusion  | Hasil eksperimen hanya dilakukan satu kali   | Menggunakan cross-validation dan pengujian berulang |


**Ancaman mana yang paling sulit dimitigasi?** External Validity
**Mengapa?**
> Karena dataset penelitian belum tentu mewakili semua kondisi penyakit daun padi di dunia nyata seperti perbedaan pencahayaan, kualitas kamera, dan kondisi lingkungan pertanian.

---

## Refleksi

> Sebuah paper melaporkan "metode kami mengalahkan semua baseline." Apa 3 pertanyaan pertama yang harus diajukan untuk mengevaluasi klaim ini?

**Jawaban:**
1. Apakah semua metode diuji menggunakan dataset dan kondisi yang sama?
2. Apakah baseline menggunakan parameter terbaik atau hanya default?
3. Apakah hasil perbedaannya signifikan secara statistik dan diuji lebih dari satu kali?
