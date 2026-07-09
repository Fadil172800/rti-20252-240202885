# WS-08: Proposal Integration (UTS)

> **Bab 8 — Proposal & Checkpoint**

---

## Ringkasan Materi

### Proposal = Satu Argumen Utuh

Proposal riset bukan kumpulan bab yang independen. Ia adalah **satu argumen** yang mengalir dari masalah ke rencana solusi. Jika satu koneksi putus, seluruh proposal kehilangan koherensi.

### Integration Map — 6 Koneksi Kritis

```
Problem (Bab 2) → Gap (Bab 3) → RQ & H (Bab 4) → Metrik (Bab 5) → Sistem (Bab 6) → Eksperimen (Bab 7)
```

| Koneksi | Pertanyaan Verifikasi |
|---------|----------------------|
| Problem → Gap | Apakah gap muncul dari analisis literatur terhadap masalah? |
| Gap → RQ | Apakah RQ langsung menjawab gap yang teridentifikasi? |
| RQ → Metrik | Apakah setiap variabel di RQ punya metrik terdefinisi? |
| Metrik → Sistem | Apakah setiap metrik bisa diukur oleh komponen sistem? |
| Sistem → Eksperimen | Apakah desain eksperimen menggunakan sistem sebagai instrumen? |

### Koherensi Vertikal + Horizontal

- **Vertikal** — Alur logis atas-ke-bawah (problem → experiment). Setiap section menjawab pertanyaan yang diangkat section sebelumnya dan memunculkan pertanyaan baru.
- **Horizontal** — Konsistensi terminologi (nama variabel di RQ = di hipotesis = di metrik = di desain)

**Operasionalisasi Red Thread** (benang merah):
```
Bab 2 (Problem) → | memperkenalkan masalah X + evidensi |
                          ↓ menimbulkan pertanyaan: "apa akar gap-nya?"
Bab 3 (Gap)     → | menjawab pertanyaan tadi + membuka "lalu apa yang perlu diteliti?" |
                          ↓
Bab 4 (RQ/H)    → | menjawab gap dengan pertanyaan spesifik + prediksi terukur |
                          ↓
Bab 5-7 (Method)→ | menjawab RQ melalui desain eksperimen yang tepat |
```
Jika ada lompatan (section B tidak menjawab pertanyaan section A), red thread putus.

### Jebakan Kognitif

| Jebakan | Deskripsi |
|---------|----------|
| "Selling" Introduction | Menulis promosi, bukan menyajikan data dan gap |
| Copy-paste Methodology | Menyalin deskripsi tekstbook tanpa menyesuaikan ke RQ |
| Optimistic Timeline | Meremehkan waktu implementasi; selalu tambah buffer 30-50% |
| No Possibility of Failure | Mengimplikasikan hasil pasti sukses — proposal jujur mengakui H₀ mungkin tidak ditolak |

### Struktur Proposal

1. **Pendahuluan** — Latar belakang + problem statement (Bab 1-2)
2. **Tinjauan Pustaka** — Literature review + gap + baseline (Bab 3)
3. **RQ / Kontribusi / Hipotesis** — (Bab 4)
4. **Metodologi** — Metrik + sistem + desain eksperimen (Bab 5-7)
5. **Timeline & Output**

### Istilah Penting

- **Integration Map** — Diagram 6 koneksi kritis antar komponen proposal
- **Vertical Coherence** — Alur logis atas-ke-bawah
- **Horizontal Coherence** — Konsistensi terminologi di semua bagian
- **Checkpoint** — Titik self-assessment sebelum transisi dari desain ke eksekusi

---

## Template A.8 — Integration Checklist

```
PROPOSAL INTEGRATION CHECKLIST

Koneksi Vertikal (Flow Atas-Bawah):

[x] Problem → Gap: masalah terdokumentasi di literatur
[x] Gap → RQ: pertanyaan menjawab gap spesifik
[x] RQ → Hypothesis: hipotesis memprediksi jawaban
[x] Hypothesis → Metric: metrik mengukur variabel dalam hipotesis
[x] Metric → System: komponen sistem menghasilkan/mengukur metrik
[x] System → Experiment: desain eksperimen menggunakan sistem

Koneksi Horizontal (Konsistensi):

[x] Istilah sama di semua bagian
[x] Variabel di RQ = variabel di hipotesis = metrik di desain
[x] Scope tidak berubah dari masalah ke eksperimen

Cognitive Trap Checklist:

[x] Tidak ada paragraf "promosi" di pendahuluan (hanya data & gap)
[x] Metodologi disesuaikan ke RQ, bukan copy-paste textbook
[x] Timeline sudah ditambah buffer 30–50% dari estimasi awal
[x] Proposal mengakui kemungkinan hasil penelitian berbeda dengan penelitian acuan
[x] Tidak ada klaim "pasti berhasil" atau "meningkatkan signifikan"

Rubrik Self-Assessment

| Kriteria | 1 (Lemah) | 2 (Cukup) | 3 (Baik) | Skor |
|-----------|-----------|-----------|----------|------|
| Koherensi | | | ✓ | **3** |
| Specificity | | | ✓ | **3** |
| Feasibility | | | ✓ | **3** |
| Rigor | | | ✓ | **3** |

**Total Skor : 12 / 12**

**Catatan:**

Proposal telah memiliki hubungan yang konsisten antara problem statement, research gap, research question, hipotesis, variabel penelitian, metodologi, sistem, dan desain eksperimen. Seluruh komponen telah disesuaikan dengan implementasi penelitian menggunakan Google Colab sehingga proposal dan hasil praktikum memiliki keterkaitan yang konsisten.
```

---

## Latihan 1 — Kompilasi Proposal Mini

Kumpulkan hasil dari WS-02 sampai WS-07 menjadi satu ringkasan proposal.

| Komponen              | Sumber | Isi (1–2 kalimat)                                                                                                                                                                                                                                           |
| --------------------- | ------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Problem Statement** | WS-02  | Identifikasi penyakit daun padi secara manual masih memerlukan waktu dan berpotensi menghasilkan kesalahan diagnosis sehingga diperlukan sistem klasifikasi otomatis berbasis Deep Learning.                                                                |
| **Gap**               | WS-03  | Penelitian sebelumnya menunjukkan bahwa EfficientNet-B6 memiliki performa yang baik, namun implementasinya masih memerlukan sumber daya komputasi yang cukup besar sehingga diperlukan penyesuaian agar dapat dijalankan pada lingkungan Google Colab Free. |
| **Research Question** | WS-04  | Bagaimana performa model EfficientNet-B6 menggunakan pendekatan transfer learning dalam mengklasifikasikan penyakit daun padi berdasarkan Accuracy, Precision, Recall, F1-Score, dan Confusion Matrix?                                                      |
| **Hipotesis**         | WS-04  | Model EfficientNet-B6 dengan pendekatan transfer learning mampu memberikan performa klasifikasi yang baik berdasarkan Accuracy, Precision, Recall, F1-Score, dan Confusion Matrix.                                                                          |
| **Variabel & Metrik** | WS-05  | Variabel independen berupa penggunaan model EfficientNet-B6 dengan pendekatan transfer learning, sedangkan variabel dependen berupa Accuracy, Precision, Recall, F1-Score, Confusion Matrix, dan Classification Report.                                     |
| **Sistem**            | WS-06  | Sistem klasifikasi dibangun menggunakan EfficientNet-B6 dengan bobot awal ImageNet dan dijalankan menggunakan Google Colab pada dataset Rice Leafs.                                                                                                         |
| **Desain Eksperimen** | WS-07  | Penelitian menggunakan model EfficientNet-B6 dengan pendekatan transfer learning serta pembagian data 80% data latih dan 20% data validasi untuk mengevaluasi performa model.                                                                               |



---

## Latihan 2 — Integration Checklist

Verifikasi 6 koneksi kritis berdasarkan proposal penelitian.

| Koneksi             | Status | Bukti                                                                                                                                                                                                                                                        |
| ------------------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Problem → Gap       | ✅      | Research gap diperoleh dari penelitian sebelumnya yang menunjukkan EfficientNet-B6 memiliki performa yang baik, namun implementasinya masih perlu disesuaikan dengan keterbatasan sumber daya komputasi agar dapat diterapkan menggunakan Google Colab Free. |
| Gap → RQ            | ✅      | Research Question disusun untuk mengevaluasi performa EfficientNet-B6 menggunakan pendekatan transfer learning pada implementasi penelitian yang dilakukan.                                                                                                  |
| RQ → Hypothesis     | ✅      | Hipotesis memprediksi bahwa EfficientNet-B6 mampu memberikan performa klasifikasi yang baik berdasarkan metrik evaluasi yang digunakan.                                                                                                                      |
| Hypothesis → Metric | ✅      | Hipotesis diuji menggunakan Accuracy, Precision, Recall, F1-Score, Confusion Matrix, dan Classification Report.                                                                                                                                              |
| Metric → System     | ✅      | Sistem menghasilkan seluruh metrik evaluasi secara otomatis setelah proses pelatihan dan pengujian selesai.                                                                                                                                                  |
| System → Experiment | ✅      | Sistem digunakan sebagai instrumen utama pada eksperimen menggunakan EfficientNet-B6 dengan pembagian data 80% data latih dan 20% data validasi.                                                                                                             |



**Koneksi mana yang paling lemah?**

Hubungan antara research gap dan implementasi penelitian masih dapat diperkuat dengan menambahkan referensi mengenai penerapan transfer learning menggunakan EfficientNet-B6 pada lingkungan komputasi terbatas sehingga alasan pemilihan metode menjadi lebih kuat.

**Bagaimana cara memperkuatnya?**

> Menambahkan referensi penelitian terbaru yang membahas implementasi EfficientNet-B6 menggunakan transfer learning pada Google Colab atau lingkungan komputasi terbatas sehingga dasar pemilihan metode menjadi lebih kuat.
> 
**Konsistensi horizontal — apakah istilah dan scope konsisten?**

**[X] Ya**

Seluruh istilah telah konsisten mulai dari problem statement, research question, hipotesis, variabel penelitian, metode, sistem, hingga desain eksperimen.

---

## Latihan 3 — Rubrik Self-Assessment

Evaluasi proposal menggunakan rubrik berikut.

| Kriteria        | Skor (1–3) | Justifikasi                                                                                                                                                                                                       |
| --------------- | ---------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Koherensi**   | **3**      | Proposal memiliki alur yang logis mulai dari identifikasi masalah, research gap, research question, hipotesis, metode, hingga desain eksperimen.                                                                  |
| **Specificity** | **3**      | Dataset, model EfficientNet-B6, metode transfer learning, metrik evaluasi, dan konfigurasi eksperimen dijelaskan secara spesifik.                                                                                 |
| **Feasibility** | **3**      | Penelitian dapat dilaksanakan menggunakan Google Colab Free dan dataset Rice Leafs sesuai dengan implementasi yang telah dilakukan.                                                                               |
| **Rigor**       | **3**      | Penelitian menggunakan pendekatan Deep Learning EfficientNet-B6, preprocessing, transfer learning, serta evaluasi menggunakan accuracy, precision, recall, F1-score, confusion matrix, dan classification report. |


**Skor total:** **12 / 12**

**Apakah proposal siap untuk fase eksekusi?**

**[X] Ya**

Proposal telah memiliki keterkaitan yang konsisten antara problem statement, research gap, research question, hipotesis, metodologi, sistem, dan desain eksperimen. Selain itu, proposal telah disesuaikan dengan implementasi penelitian sehingga konsisten dengan hasil praktikum yang telah diperoleh.

---

## Refleksi

> Dari seluruh proses WS-01 sampai WS-08, bagian mana yang paling mudah dan paling sulit? Mengapa? Apa yang akan dilakukan berbeda jika mengulang dari awal?

**Bagian termudah:**

Menyusun problem statement, research gap, dan research question karena didukung oleh hasil analisis artikel acuan sehingga hubungan antarbagian dapat disusun secara sistematis.

**Bagian tersulit:**

Menyesuaikan proposal dengan implementasi penelitian. Pada awal perencanaan terdapat beberapa skenario eksperimen, sedangkan implementasi akhir menggunakan satu konfigurasi EfficientNet-B6 dengan pendekatan transfer learning. Oleh karena itu, proposal perlu disesuaikan agar seluruh komponen tetap konsisten dengan penelitian yang benar-benar dilakukan.

**Yang akan dilakukan berbeda:**

> Jika mengulang penelitian dari awal, saya akan menyusun proposal berdasarkan kemampuan komputasi yang tersedia sehingga rancangan eksperimen, implementasi, dan hasil penelitian tetap konsisten sejak awal hingga akhir penelitian.
