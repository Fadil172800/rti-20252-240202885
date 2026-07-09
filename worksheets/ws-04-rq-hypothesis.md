# WS-04: Research Question & Hypothesis

> **Bab 4 — Research Question, Contribution & Hypothesis**

---

## Ringkasan Materi

### RQ Bukan Pertanyaan Biasa

Research Question yang baik secara implisit mengandung cetak biru eksperimen: subjek, baseline, metrik, domain, dataset.

| Kualitas | Contoh |
|----------|--------|
| **Buruk** | "Bagaimana pengaruh deep learning terhadap deteksi malware?" |
| **Baik** | "Apakah CNN menghasilkan F1-Score lebih tinggi dari RF pada CIC-MalMem-2022?" |

Perbedaan: RQ yang baik menyebutkan **metode spesifik**, **metrik terukur**, **baseline**, dan **dataset**.

### Tiga Jenis RQ

| Jenis | Pola | Kebutuhan |
|-------|------|-----------|
| **Comparison** | A vs B → mana lebih baik? | ≥ 2 metode, metrik sama |
| **Improvement** | A' vs A → modifikasi lebih baik? | Pre/post, bukti perbaikan |
| **Exploratory** | Faktor X₁...Xₙ → pengaruh terhadap Y? | Multi-variabel, korelasi/regresi |

### Contribution Statement

Tiga jenis kontribusi: **Improvement** (metode terbukti lebih baik), **Comparison** (perbandingan sistematis yang belum ada), **Novel Approach** (pendekatan baru). Kontribusi harus terhubung langsung dengan gap — kontribusi tanpa gap = klaim tanpa justifikasi.

### Hypothesis H₀ / H₁

- **H₀** (Null) = Tidak ada perbedaan signifikan — asumsi default, harus dibuktikan salah
- **H₁** (Alternative) = Ada perbedaan signifikan — diterima hanya jika H₀ ditolak
- Harus **falsifiable**, mengandung **metrik terukur**, dirumuskan **SEBELUM eksperimen**

### Rantai Operasionalisasi

```
RQ → Variable → Metric → Data → Analysis
```

Jika rantai ini tidak lengkap, RQ belum mature. Bi-directional: RQ yang tidak bisa jadi hipotesis testable harus direvisi mundur.

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Tujuan pertanyaan | Apa yang harus dibangun? | Apa yang harus dibuktikan? |
| Bentuk jawaban | Sistem yang berfungsi | Bukti empiris terukur |
| Sukses diukur oleh | User satisfaction, uptime | Signifikansi statistik, effect size |
| Jika gagal | Debug dan perbaiki | Laporkan, analisis mengapa |

### Istilah Penting

- **Research Question (RQ)** — Pertanyaan spesifik: variabel terukur + metrik + konteks
- **Contribution Statement** — Apa yang diketahui setelah riset selesai yang sebelumnya belum ada
- **H₀ / H₁** — Null vs Alternative Hypothesis
- **Falsifiability** — Kondisi hipotesis ditolak harus bisa didefinisikan sebelum eksperimen
- **Operationalization** — Proses mewujudkan konsep abstrak menjadi variabel terukur

---

## Template A.4 — RQ-Contribution-Hypothesis

```
RQ-CONTRIBUTION-HYPOTHESIS

Gap Statement :
Performa klasifikasi penyakit daun padi menggunakan EfficientNet-B6 masih memiliki keterbatasan pada beberapa kelas penyakit sehingga masih diperlukan evaluasi lebih lanjut terhadap penerapan model tersebut.

Research Question

Tipe :
[ ] Comparison
[X] Improvement
[ ] Exploratory

Formulasi :

Bagaimana performa model EfficientNet-B6 dalam mengklasifikasikan penyakit daun padi berdasarkan metrik Accuracy, Precision, Recall, dan F1-Score?

Variabel IV :
Model Deep Learning EfficientNet-B6.

Variabel DV :
Performa klasifikasi penyakit daun padi.

Metrik :
Accuracy, Precision, Recall, F1-Score, AUC, dan Confusion Matrix.

Dataset :
Rice Leafs sebanyak 3.355 citra yang terdiri dari empat kelas penyakit daun padi.

Baseline :
Penelitian klasifikasi penyakit daun padi menggunakan arsitektur CNN pada penelitian sebelumnya.

Quality Check RQ

[X] Variabel spesifik

[X] Metrik jelas

[X] Baseline ada

[X] Konteks disebutkan

[X] Memerlukan eksperimen

Contribution Statement

Apa yang baru diketahui :

Mengetahui kemampuan model EfficientNet-B6 dalam melakukan klasifikasi penyakit daun padi berdasarkan metrik evaluasi standar.

Jenis kontribusi

[X] Improvement

[ ] Comparison

[ ] Novel Approach

Gap yang diisi

Memberikan evaluasi terhadap performa EfficientNet-B6 pada klasifikasi penyakit daun padi sebagai dasar penelitian lanjutan.

Hypothesis Pair

H₀ :

Model EfficientNet-B6 belum mampu memberikan performa klasifikasi penyakit daun padi yang lebih baik dibandingkan penelitian sebelumnya.

H₁ :

Model EfficientNet-B6 mampu memberikan performa klasifikasi penyakit daun padi yang baik berdasarkan metrik Accuracy, Precision, Recall, dan F1-Score.

Threshold :

Mengacu pada hasil evaluasi model yang diperoleh dari proses eksperimen.

Justifikasi Threshold :

Penelitian berfokus pada evaluasi performa model berdasarkan metrik klasifikasi, bukan pada pengujian signifikansi statistik.
```

---

## Latihan 1 — Dari Gap ke RQ

Gunakan gap yang ditemukan di WS-03. Transformasikan menjadi Research Question.

**Gap dari WS-03:** Performa klasifikasi penyakit daun padi masih belum optimal sehingga diperlukan evaluasi lebih lanjut terhadap penerapan EfficientNet-B6.

**RQ versi pertama (tulis bebas):**
> Bagaimana performa EfficientNet-B6 dalam mengklasifikasikan penyakit daun padi?
> 
**Evaluasi RQ:**

| Komponen        | Ada? | Isi                                   |
| --------------- | ---- | ------------------------------------- |
| Metode spesifik | Ya   | EfficientNet-B6                       |
| Metrik terukur  | Ya   | Accuracy, Precision, Recall, F1-Score |
| Baseline        | Ya   | Penelitian CNN sebelumnya             |
| Dataset/Konteks | Ya   | Dataset Rice Leafs                    |


**Tipe RQ:** [ ] Comparison / [X] Improvement / [ ] Exploratory

**RQ versi revisi (setelah evaluasi):**
> Bagaimana performa model EfficientNet-B6 dalam mengklasifikasikan penyakit daun padi berdasarkan metrik Accuracy, Precision, Recall, dan F1-Score menggunakan dataset Rice Leafs?
---

## Latihan 2 — Hypothesis Pair

Rumuskan pasangan hipotesis dari RQ di Latihan 1.

| Komponen              | Isi                                                                                                                                             |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| H₀                    | Model EfficientNet-B6 belum mampu memberikan performa klasifikasi penyakit daun padi yang lebih baik dibandingkan penelitian sebelumnya.        |
| H₁                    | Model EfficientNet-B6 mampu memberikan performa klasifikasi penyakit daun padi yang baik berdasarkan Accuracy, Precision, Recall, dan F1-Score. |
| Metrik                | Accuracy, Precision, Recall, F1-Score                                                                                                           |
| Threshold             | Mengacu pada hasil evaluasi model                                                                                                               |
| Justifikasi Threshold | Penelitian bertujuan mengevaluasi performa model berdasarkan metrik klasifikasi tanpa melakukan pengujian statistik inferensial.                |



**Apakah hipotesis ini falsifiable?** [X] Ya / [ ] Tidak
> Bagaimana cara membuktikannya salah?
Melakukan implementasi EfficientNet-B6 pada dataset Rice Leafs kemudian mengevaluasi performanya menggunakan Accuracy, Precision, Recall, F1-Score, dan Confusion Matrix. Jika hasil evaluasi menunjukkan performa yang rendah, maka hipotesis tidak didukung.
---

## Latihan 3 — Rantai Operasionalisasi

Lengkapi rantai dari RQ hingga metode analisis.

| Tahap           | Isi                                                                             |
| --------------- | ------------------------------------------------------------------------------- |
| RQ              | Bagaimana performa EfficientNet-B6 dalam mengklasifikasikan penyakit daun padi? |
| Variable (IV)   | Model EfficientNet-B6                                                           |
| Variable (DV)   | Performa klasifikasi                                                            |
| Metric          | Accuracy, Precision, Recall, F1-Score                                           |
| Data Source     | Dataset Rice Leafs sebanyak 3.355 citra                                         |
| Analysis Method | Analisis metrik evaluasi model dan Confusion Matrix                             |



**Apakah rantai lengkap?** [X] Ya / [ ] Tidak
> Jika tidak, tahap mana yang perlu direvisi? ______________

---

## Refleksi

> Ambil satu judul skripsi/paper yang pernah dibaca. Coba ekstrak RQ-nya. Apakah RQ tersebut memenuhi semua komponen (metode, metrik, baseline, konteks)? Jika tidak, apa yang hilang?

**Judul:** Klasifikasi Penyakit Daun Padi Menggunakan Model Deep Learning EfficientNet-B6
**RQ yang diekstrak:** Bagaimana performa model EfficientNet-B6 dalam mengklasifikasikan penyakit daun padi berdasarkan metrik evaluasi klasifikasi?
**Komponen yang hilang:** Sebagian besar sudah terpenuhi karena artikel menjelaskan metode, dataset, dan metrik evaluasi yang digunakan. Namun, artikel belum menjelaskan secara rinci pembandingan dengan metode lain sehingga baseline penelitian masih dapat dikembangkan pada penelitian lanjutan.
