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

| Komponen              | Sumber | Isi (1–2 kalimat)                                                                                                                                                                                                                                        |
| --------------------- | ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Problem Statement** | WS-02  | Identifikasi penyakit daun padi secara manual masih memerlukan waktu dan berpotensi menghasilkan kesalahan diagnosis sehingga diperlukan sistem klasifikasi otomatis berbasis Deep Learning.                                                             |
| **Gap**               | WS-03  | Penelitian sebelumnya menunjukkan EfficientNet-B6 memiliki performa yang baik, namun implementasi menggunakan skema 5-Fold Cross Validation memerlukan sumber daya komputasi yang cukup besar sehingga kurang sesuai untuk lingkungan Google Colab Free. |
| **Research Question** | WS-04  | Bagaimana performa model EfficientNet-B6 menggunakan pendekatan transfer learning dalam mengklasifikasikan penyakit daun padi berdasarkan metrik accuracy, precision, recall, F1-score, dan confusion matrix?                                            |
| **Hipotesis**         | WS-04  | Model EfficientNet-B6 dengan pendekatan transfer learning mampu menghasilkan performa klasifikasi yang dapat dievaluasi menggunakan accuracy, precision, recall, F1-score, dan confusion matrix.                                                         |
| **Variabel & Metrik** | WS-05  | Variabel bebas berupa penggunaan model EfficientNet-B6 dengan pendekatan transfer learning, sedangkan variabel terikat berupa accuracy, precision, recall, F1-score, dan confusion matrix sebagai metrik evaluasi.                                       |
| **Sistem**            | WS-06  | Sistem klasifikasi dibangun menggunakan EfficientNet-B6 dengan bobot pretrained ImageNet yang dijalankan pada Google Colab menggunakan dataset Rice Leafs.                                                                                               |
| **Desain Eksperimen** | WS-07  | Penelitian menggunakan satu konfigurasi model EfficientNet-B6 dengan pendekatan transfer learning menggunakan pembagian data 80% data latih dan 20% data validasi (single split) untuk mengevaluasi performa model.                                      |


---

## Latihan 2 — Integration Checklist

Verifikasi 6 koneksi kritis berdasarkan proposal penelitian.

| Koneksi             | Status | Bukti                                                                                                                                                                          |
| ------------------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Problem → Gap       | ✅      | Research gap diperoleh dari penelitian sebelumnya yang menggunakan skema evaluasi dengan kebutuhan komputasi tinggi sehingga belum sesuai untuk lingkungan komputasi terbatas. |
| Gap → RQ            | ✅      | Research Question disusun untuk mengevaluasi performa EfficientNet-B6 menggunakan pendekatan transfer learning pada skema single split yang lebih ringan.                      |
| RQ → Hypothesis     | ✅      | Hipotesis memprediksi bahwa EfficientNet-B6 mampu menghasilkan performa klasifikasi yang dapat diukur menggunakan metrik evaluasi yang ditentukan.                             |
| Hypothesis → Metric | ✅      | Hipotesis diuji menggunakan accuracy, precision, recall, F1-score, dan confusion matrix.                                                                                       |
| Metric → System     | ✅      | Sistem menghasilkan seluruh metrik evaluasi setelah proses pelatihan dan pengujian model selesai.                                                                              |
| System → Experiment | ✅      | Sistem digunakan sebagai instrumen utama pada eksperimen menggunakan EfficientNet-B6 dengan transfer learning dan pembagian data single split.                                 |


**Koneksi mana yang paling lemah?**

Hubungan antara research gap dan research question masih dapat diperkuat dengan menambahkan referensi yang membahas penerapan EfficientNet-B6 pada lingkungan komputasi terbatas sehingga alasan penggunaan skema single split menjadi lebih kuat.

**Bagaimana cara memperkuatnya?**

> Menambahkan referensi penelitian terbaru mengenai implementasi transfer learning EfficientNet pada Google Colab atau lingkungan komputasi dengan sumber daya terbatas sehingga research gap memiliki dasar yang lebih kuat.

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

Menyusun latar belakang, problem statement, dan research question karena didukung oleh jurnal acuan serta hasil implementasi yang telah selesai sehingga hubungan antarbagian lebih mudah dibangun.

**Bagian tersulit:**

Menjaga konsistensi antara proposal dan implementasi penelitian. Pada awal penyusunan, rancangan penelitian masih mengacu pada beberapa skenario eksperimen, sedangkan implementasi akhir menggunakan satu konfigurasi EfficientNet-B6 dengan pendekatan transfer learning. Oleh karena itu, proposal perlu disesuaikan agar seluruh komponen tetap konsisten dengan penelitian yang benar-benar dilakukan.

**Yang akan dilakukan berbeda:**

> Jika mengulang penelitian dari awal, saya akan menetapkan rancangan eksperimen yang benar-benar sesuai dengan kemampuan komputasi yang tersedia sebelum menyusun proposal. Dengan demikian, proposal, implementasi, dan hasil penelitian akan tetap konsisten sejak awal hingga akhir penelitian tanpa memerlukan banyak revisi.
