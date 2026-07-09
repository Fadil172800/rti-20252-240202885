# WS-05: Variabel & Metrik

> **Bab 5 — Metric, Measurement & Data**

---

## Ringkasan Materi

### Measurement Alignment Model

Setiap pengukuran yang valid harus bisa ditelusuri melalui rantai ini tanpa lompatan logis:

```
Problem → Concept → Variable → Metric → Data → Result
```

### Operationalization = Keputusan Desain

Menerjemahkan konsep abstrak menjadi variabel terukur bukan proses mekanis. "Code quality" yang diukur via SonarQube code smells membawa asumsi implisit. Setiap operasionalisasi harus didokumentasikan dan dijustifikasi.

### Empat Tipe Data (NOIR)

| Tipe | Ciri | Contoh | Operasi Valid |
|------|------|--------|---------------|
| **Nominal** | Kategori, tanpa urutan | Jenis algoritma (RF, SVM, CNN) | Modus, chi-square |
| **Ordinal** | Urutan, interval tidak sama | Skala Likert (1-5) | Median, Spearman |
| **Interval** | Jarak bermakna, tanpa nol absolut | Suhu Celsius | Mean, Pearson, t-test |
| **Ratio** | Jarak bermakna + nol absolut | Waktu eksekusi (ms) | Semua operasi |

Tipe data menentukan uji statistik yang valid. Kebanyakan metrik performa TI = ratio; persepsi pengguna = ordinal.

### Kriteria Pemilihan Metrik

- **Representative** — Mewakili konsep yang diteliti
- **Sensitive** — Cukup peka menangkap perbedaan bermakna (hindari ceiling effect)
- **Feasible** — Bisa dikumpulkan dalam batasan waktu dan biaya

### Pre-registration

Metrik harus ditentukan **sebelum** eksperimen. Memilih metrik setelah melihat data = **p-hacking**. Metrik tambahan yang ditemukan kemudian dilaporkan sebagai *exploratory*, bukan *confirmatory*.

### Primary vs Secondary Metric

- **Primary Metric** — Langsung terikat ke hipotesis, menentukan kesimpulan
- **Secondary Metric** — Pendukung, dilaporkan di samping primary; statusnya suplementer

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Pemilihan metrik | Berdasarkan kebiasaan/tool yang ada | Berdasarkan construct validity |
| Anomali | Dihapus untuk laporan bersih | Diinvestigasi — bisa jadi temuan |
| Kapan dipilih | Setelah sistem jadi (monitoring) | Sebelum eksperimen (by design) |

### Istilah Penting

- **Operationalization** — Transformasi konsep abstrak menjadi variabel terukur
- **Construct Validity** — Sejauh mana pengukuran benar-benar mengukur konsep yang dimaksud
- **Measurement Scale** — Klasifikasi data (NOIR) yang menentukan analisis valid
- **Multi-metric Evaluation** — Menggunakan beberapa metrik untuk menangkap konsep kompleks

---

## Template A.5 — Definisi Variabel, Metrik & Justifikasi

```
VARIABLE & METRIC DEFINITION

Research Question

Bagaimana performa model EfficientNet-B6 dalam mengklasifikasikan penyakit daun padi berdasarkan metrik Accuracy, Precision, Recall, dan F1-Score?

| Variabel | Tipe | Konsep | Metrik | Skala | Satuan | Cara Mengukur | Justifikasi |
|----------|------|--------|--------|-------|--------|---------------|-------------|
| Model EfficientNet-B6 | IV | Model Deep Learning untuk klasifikasi citra | EfficientNet-B6 | Nominal | - | Model yang digunakan pada proses pelatihan | Menjadi objek utama yang dievaluasi pada artikel |
| Accuracy | DV | Tingkat ketepatan klasifikasi | Accuracy Score | Ratio | % | Perhitungan berdasarkan confusion matrix | Mengukur persentase prediksi yang benar |
| Precision | DV | Ketepatan prediksi pada setiap kelas | Precision Score | Ratio | % | TP / (TP + FP) | Mengukur ketepatan prediksi positif |
| Recall | DV | Kemampuan mendeteksi seluruh data positif | Recall Score | Ratio | % | TP / (TP + FN) | Mengukur sensitivitas model |
| F1-Score | DV | Keseimbangan Precision dan Recall | F1-Score | Ratio | % | Harmonic Mean Precision dan Recall | Cocok digunakan pada dataset yang tidak seimbang |
| AUC | DV | Kemampuan model membedakan setiap kelas | Area Under Curve | Ratio | - | Perhitungan ROC Curve | Mengukur kualitas klasifikasi secara keseluruhan |

Alignment Check

[x] Setiap langkah terdokumentasi

[x] Tidak ada lompatan logis

[x] Metrik mengukur variabel yang dimaksud (construct validity)
```

---

## Latihan 1 — Operationalization Chain

Gunakan RQ dari WS-04. Definisikan variabel dan metriknya.

**RQ:** Bagaimana performa model EfficientNet-B6 dalam mengklasifikasikan penyakit daun padi berdasarkan Accuracy, Precision, Recall, dan F1-Score?

| Variabel              | Tipe | Konsep Abstrak                    | Metrik Konkret   | Skala (NOIR) | Satuan |
| --------------------- | ---- | --------------------------------- | ---------------- | ------------ | ------ |
| Model EfficientNet-B6 | IV   | Model Deep Learning               | EfficientNet-B6  | Nominal      | -      |
| Accuracy              | DV   | Ketepatan klasifikasi             | Accuracy Score   | Ratio        | %      |
| Precision             | DV   | Ketepatan prediksi                | Precision Score  | Ratio        | %      |
| Recall                | DV   | Kemampuan menemukan data positif  | Recall Score     | Ratio        | %      |
| F1-Score              | DV   | Keseimbangan Precision dan Recall | F1-Score         | Ratio        | %      |
| AUC                   | DV   | Kemampuan klasifikasi             | Area Under Curve | Ratio        | -      |



**Apakah ada lompatan logis dalam rantai?** [ ] Ya / [X] Tidak
> Justifikasi:
Accuracy, Precision, Recall, F1-Score, dan AUC merupakan metrik evaluasi yang umum digunakan pada penelitian klasifikasi citra sehingga sesuai untuk mengukur performa model EfficientNet-B6.
---

## Latihan 2 — Evaluasi Metrik

Evaluasi metrik DV yang dipilih di Latihan 1 menggunakan 3 kriteria.

| Kriteria       | Skor (1–5) | Justifikasi                                                                                         |
| -------------- | ---------- | --------------------------------------------------------------------------------------------------- |
| Representative | **5**      | Accuracy, Precision, Recall, dan F1-Score secara langsung menggambarkan performa model klasifikasi. |
| Sensitive      | **5**      | Perubahan performa model akan terlihat pada perubahan nilai setiap metrik evaluasi.                 |
| Feasible       | **5**      | Seluruh metrik dapat dihitung secara otomatis menggunakan library Scikit-Learn.                     |

**Apakah perlu secondary metric?** [x] Ya
> **Apa dan mengapa?**AUC digunakan sebagai metrik tambahan karena mampu menggambarkan kemampuan model dalam membedakan setiap kelas secara keseluruhan.

**Contoh kasus ceiling effect untuk metrik ini:**
> Jika dua model memiliki Accuracy yang hampir sama, maka Precision, Recall, F1-Score, dan AUC dapat memberikan informasi tambahan mengenai kualitas klasifikasi pada setiap kelas.
---

## Latihan 3 — Data Quality Check

Bayangkan data yang akan dikumpulkan dari eksperimen. Evaluasi 4 dimensi kualitas data.

| Dimensi            | Pertanyaan                                | Jawaban  | Strategi Mitigasi                                                                                    |
| ------------------ | ----------------------------------------- | -------- | ---------------------------------------------------------------------------------------------------- |
| Completeness       | Apakah seluruh data tersedia?             | Ya       | Memastikan seluruh citra berhasil dimuat sebelum proses pelatihan.                                   |
| Consistency        | Apakah format data seragam?               | Ya       | Seluruh citra diproses menggunakan ukuran dan format yang sama.                                      |
| Validity           | Apakah data mengukur objek yang dimaksud? | Ya       | Menggunakan dataset Rice Leafs yang telah diberi label penyakit daun padi.                           |
| Representativeness | Apakah data mewakili kondisi nyata?       | Sebagian | Mengakui bahwa dataset publik memiliki keterbatasan sehingga diperlukan pengujian pada dataset lain. |


---

## Refleksi

> Mengapa memilih metrik setelah melihat data dianggap p-hacking? Apa bedanya dengan eksplorasi data yang sah?

**Jawaban:**
> Memilih metrik setelah melihat hasil eksperimen dapat menyebabkan p-hacking, karena peneliti cenderung hanya memilih metrik yang mendukung hasil yang diinginkan sehingga mengurangi objektivitas penelitian. Sebaliknya, eksplorasi data yang sah dilakukan untuk memahami karakteristik data tanpa mengubah tujuan penelitian maupun metrik utama yang telah ditentukan sejak awal.
