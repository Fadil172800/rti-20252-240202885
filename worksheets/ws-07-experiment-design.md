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

Bagaimana pengaruh variasi ukuran input citra dan jumlah epoch terhadap performa model EfficientNet-B6 dalam mengklasifikasikan penyakit daun padi?

Hypothesis :

Variasi ukuran input citra dan jumlah epoch mempengaruhi performa model EfficientNet-B6 berdasarkan Accuracy, Precision, Recall, F1-Score, dan AUC.

Tipe Eksperimen :

[ ] Comparison
[ ] Ablation
[X] Parameter

Kondisi Eksperimen

| Kondisi | Deskripsi | IV Value | CV Settings |
|---------|-----------|----------|-------------|
| Skenario 1 | EfficientNet-B6 | Input 224×224, Epoch 25 | Dataset Rice Leafs, 5-Fold Cross Validation |
| Skenario 2 | EfficientNet-B6 | Input 224×224, Epoch 50 | Dataset Rice Leafs, 5-Fold Cross Validation |
| Skenario 3 | EfficientNet-B6 | Input 528×528, Epoch 25 | Dataset Rice Leafs, 5-Fold Cross Validation |
| Skenario 4 | EfficientNet-B6 | Input 528×528, Epoch 50 | Dataset Rice Leafs, 5-Fold Cross Validation |

Fairness Checklist

[x] Dataset identik untuk semua skenario.

[x] Preprocessing dilakukan dengan prosedur yang sama.

[x] Arsitektur model tetap menggunakan EfficientNet-B6.

[x] Environment pelatihan menggunakan perangkat dan software yang sama.

[x] Metrik evaluasi sama (Accuracy, Precision, Recall, F1-Score, dan AUC).

Threat Analysis

| Threat Type | Ancaman Spesifik | Mitigasi |
|-------------|------------------|----------|
| Internal | Variasi hasil akibat proses training | Menggunakan konfigurasi eksperimen yang sama pada setiap skenario |
| External | Dataset berasal dari satu sumber | Menjelaskan keterbatasan penelitian pada bagian pembahasan |
| Construct | Accuracy belum cukup menggambarkan performa model | Menggunakan Precision, Recall, F1-Score, dan AUC sebagai metrik tambahan |
| Conclusion | Variasi parameter belum mencakup seluruh kemungkinan konfigurasi | Membatasi kesimpulan hanya pada parameter yang diuji |

Statistical Plan

Analisis yang digunakan :
Perbandingan nilai Accuracy, Precision, Recall, F1-Score, dan AUC pada setiap kombinasi ukuran input dan jumlah epoch.

Justifikasi :
Untuk mengetahui konfigurasi parameter EfficientNet-B6 yang memberikan performa klasifikasi terbaik.

Alpha :
Tidak disebutkan pada artikel.

Effect Size :
Tidak dianalisis pada artikel.
```

---

## Latihan 1 — Desain Eksperimen

Susun desain eksperimen berdasarkan RQ, variabel, dan sistem dari WS-04 sampai WS-06.

**RQ:** Bagaimana pengaruh variasi ukuran input citra dan jumlah epoch terhadap performa model EfficientNet-B6 dalam mengklasifikasikan penyakit daun padi?
**Tipe eksperimen:** [ ] Comparison / [ ] Ablation / [X] Parameter

| Kondisi    | Deskripsi       | IV Value                | CV Settings                                 |
| ---------- | --------------- | ----------------------- | ------------------------------------------- |
| Skenario 1 | EfficientNet-B6 | Input 224×224, Epoch 25 | Dataset Rice Leafs, 5-Fold Cross Validation |
| Skenario 2 | EfficientNet-B6 | Input 224×224, Epoch 50 | Dataset Rice Leafs, 5-Fold Cross Validation |
| Skenario 3 | EfficientNet-B6 | Input 528×528, Epoch 25 | Dataset Rice Leafs, 5-Fold Cross Validation |
| Skenario 4 | EfficientNet-B6 | Input 528×528, Epoch 50 | Dataset Rice Leafs, 5-Fold Cross Validation |



---

## Latihan 2 — Fairness Checklist

Evaluasi apakah desain eksperimen di Latihan 1 sudah fair.

| Kriteria             | Status   | Detail                                                                          |
| -------------------- | -------- | ------------------------------------------------------------------------------- |
| Dataset identik      | ✅ Setara | Menggunakan dataset Rice Leafs yang sama pada seluruh skenario.                 |
| Preprocessing setara | ✅ Setara | Resize dan preprocessing dilakukan dengan prosedur yang sama.                   |
| Tuning effort setara | ✅ Setara | Model dan parameter selain ukuran input serta epoch dibuat sama.                |
| Environment identik  | ✅ Setara | Pelatihan dilakukan menggunakan environment Google Colab yang sama.             |
| Metrik evaluasi sama | ✅ Setara | Accuracy, Precision, Recall, F1-Score, dan AUC digunakan pada seluruh skenario. |


**Ada yang tidak fair?** [ ] Ya / [X] Tidak


---

## Latihan 3 — Threat Analysis

Identifikasi ancaman validitas untuk desain eksperimen ini.

| Threat Type | Ancaman Spesifik                                  | Mitigasi                                                                        |
| ----------- | ------------------------------------------------- | ------------------------------------------------------------------------------- |
| Internal    | Variasi hasil akibat proses training              | Menggunakan konfigurasi eksperimen yang sama pada setiap skenario               |
| External    | Dataset hanya berasal dari satu sumber            | Menjelaskan keterbatasan penelitian dan menyarankan pengujian pada dataset lain |
| Construct   | Accuracy belum cukup menggambarkan performa model | Menambahkan Precision, Recall, F1-Score, dan AUC                                |
| Conclusion  | Parameter yang diuji masih terbatas               | Kesimpulan dibatasi hanya pada kombinasi parameter yang diuji                   |



**Ancaman mana yang paling sulit dimitigasi?** External Validity
**Mengapa?**
> Karena penelitian hanya menggunakan satu dataset (Rice Leafs), sehingga kemampuan model untuk melakukan generalisasi pada dataset atau kondisi lapangan yang berbeda belum dapat dipastikan.

---

## Refleksi

> Sebuah paper melaporkan "metode kami mengalahkan semua baseline." Apa 3 pertanyaan pertama yang harus diajukan untuk mengevaluasi klaim ini?

**Jawaban:**
1. Apakah seluruh skenario eksperimen menggunakan dataset dan preprocessing yang sama sehingga perbandingan berlangsung secara adil?
2. Apakah konfigurasi parameter setiap eksperimen dijelaskan secara lengkap sehingga hasilnya dapat direproduksi?
3. Apakah peningkatan performa terlihat secara konsisten pada seluruh metrik evaluasi (Accuracy, Precision, Recall, F1-Score, dan AUC), bukan hanya pada satu metrik saja?
