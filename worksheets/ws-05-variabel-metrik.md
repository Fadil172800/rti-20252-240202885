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
**VARIABLE & METRIC DEFINITION**

**Research Question:**  
Apakah metode EfficientNet-B6 menghasilkan accuracy dan F1-Score yang lebih tinggi dibandingkan CNN standar pada klasifikasi penyakit daun padi?

| Variabel | Tipe | Konsep | Metrik | Skala | Satuan | Cara Mengukur | Justifikasi |
|----------|------|--------|--------|-------|--------|---------------|-------------|
| **Jenis Model Deep Learning** | IV | Metode klasifikasi citra | EfficientNet-B6 vs CNN standar | Nominal | - | Menentukan model yang digunakan saat training | Digunakan untuk membandingkan performa dua metode |
| **Accuracy** | DV | Ketepatan klasifikasi | Accuracy Score | Ratio | % | Menggunakan confusion matrix hasil pengujian model | Accuracy menunjukkan tingkat prediksi benar model |
| **Precision** | DV | Ketepatan prediksi positif | Precision Score | Ratio | % | Perhitungan TP / (TP + FP) | Mengukur ketepatan model dalam prediksi kelas |
| **Recall** | DV | Kemampuan menemukan data positif | Recall Score | Ratio | % | Perhitungan TP / (TP + FN) | Mengukur kemampuan model mendeteksi semua kelas |
| **F1-Score** | DV | Keseimbangan precision dan recall | F1-Score | Ratio | % | Perhitungan harmonic mean precision dan recall | Digunakan pada data yang tidak seimbang |
| **Jumlah Epoch** | CV | Intensitas training model | 25 dan 50 epoch | Ratio | epoch | Parameter training model | Menjaga konsistensi eksperimen |
| **Ukuran Input Citra** | CV | Resolusi citra | 224 dan 528 | Ratio | pixel | Resize citra sebelum training | Memastikan perbandingan model adil |

**Alignment Check:**
* [x] Setiap langkah terdokumentasi
* [x] Tidak ada lompatan logis
* [x] Metrik mengukur apa yang dimaksud (construct validity)
```

---

## Latihan 1 — Operationalization Chain

Gunakan RQ dari WS-04. Definisikan variabel dan metriknya.

**RQ:** Apakah metode EfficientNet-B6 menghasilkan accuracy dan F1-Score yang lebih tinggi dibandingkan CNN standar pada klasifikasi penyakit daun padi?

| Variabel         | Tipe | Konsep Abstrak                    | Metrik Konkret                 | Skala (NOIR) | Satuan |
| ---------------- | ---- | --------------------------------- | ------------------------------ | ------------ | ------ |
| **Jenis Model**  | IV   | Metode deep learning              | EfficientNet-B6 vs CNN standar | Nominal      | -      |
| **Accuracy**     | DV   | Ketepatan klasifikasi             | Accuracy Score                 | Ratio        | %      |
| **F1-Score**     | DV   | Keseimbangan precision dan recall | F1-Score                       | Ratio        | %      |
| **Jumlah Epoch** | CV   | Intensitas training               | 25 dan 50 epoch                | Ratio        | epoch  |


**Apakah ada lompatan logis dalam rantai?** [ ] Ya / [X] Tidak
> Justifikasi:
Accuracy dan F1-Score merupakan metrik standar pada klasifikasi citra sehingga valid digunakan untuk mengukur performa model deep learning.
---

## Latihan 2 — Evaluasi Metrik

Evaluasi metrik DV yang dipilih di Latihan 1 menggunakan 3 kriteria.

| Kriteria           | Skor (1-5) | Justifikasi                                                       |
| ------------------ | ---------- | ----------------------------------------------------------------- |
| **Representative** | 5          | Accuracy secara langsung menunjukkan performa klasifikasi model   |
| **Sensitive**      | 4          | Accuracy cukup sensitif dalam mendeteksi perubahan performa model |
| **Feasible**       | 5          | Accuracy mudah dihitung menggunakan confusion matrix              |

**Apakah perlu secondary metric?** [x] Ya
> **Apa dan mengapa?** **Resource Usage (CPU/RAM Usage)**. F1-Score diperlukan karena dataset memiliki beberapa kelas yang jumlah datanya tidak seimbang sehingga accuracy saja belum cukup.
**Contoh kasus ceiling effect untuk metrik ini:**
> Jika semua model memiliki accuracy yang hampir sama tinggi, maka perbedaan performa antar model menjadi sulit terlihat hanya menggunakan accuracy.

---

## Latihan 3 — Data Quality Check

Bayangkan data yang akan dikumpulkan dari eksperimen. Evaluasi 4 dimensi kualitas data.

| Dimensi                | Pertanyaan                          | Jawaban                                    | Strategi Mitigasi                           |
| ---------------------- | ----------------------------------- | ------------------------------------------ | ------------------------------------------- |
| **Completeness**       | Apakah semua data tersedia?         | Ya, semua citra digunakan dalam eksperimen | Memastikan tidak ada data rusak atau hilang |
| **Consistency**        | Apakah data konsisten?              | Ya, semua citra memiliki format yang sama  | Melakukan preprocessing dan resize citra    |
| **Validity**           | Apakah data mengukur yang dimaksud? | Ya, citra memang berisi penyakit daun padi | Menggunakan dataset terpercaya              |
| **Representativeness** | Apakah data mewakili kondisi nyata? | Sebagian besar ya                          | Menggunakan beberapa kelas penyakit berbeda |

---

## Refleksi

> Mengapa memilih metrik setelah melihat data dianggap p-hacking? Apa bedanya dengan eksplorasi data yang sah?

**Jawaban:**
> Memilih metrik setelah melihat hasil eksperimen disebut p-hacking karena peneliti dapat memilih metrik yang hanya mendukung hasil yang diinginkan. Hal tersebut membuat penelitian menjadi tidak objektif. Sedangkan eksplorasi data yang sah dilakukan untuk menemukan pola baru tanpa memanipulasi hasil utama penelitian.
