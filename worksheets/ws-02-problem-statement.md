# WS-02: Problem Statement

> **Bab 2 — Problem Formulation & System Context**

---

## Ringkasan Materi

### Problem Formation Model

Masalah riset melewati 5 tahap transformasi. Melompat langsung dari Reality ke Variable adalah kesalahan paling umum.

```
Reality → Observed Issue (Symptom) → Diagnosed Problem (Root Cause)
→ Researchable Problem (Scoped) → Measurable Variable (Operationalized)
```

### Topic ≠ Problem ≠ Research Problem

| Level | Contoh | Status |
|-------|--------|--------|
| **Topik** | Keamanan IoT | Terlalu luas, tidak bisa diuji |
| **Problem** | MQTT tidak terenkripsi | Spesifik tapi belum riset |
| **Research Problem** | Belum ada studi membandingkan overhead TLS 1.3 vs DTLS pada MQTT di IoT RAM < 64KB | Bisa dirancang eksperimennya |

### Symptom vs Root Cause

Apa yang diamati (gejala) ≠ mengapa terjadi (akar masalah). Gunakan **5 Whys** atau **Fishbone Diagram** untuk menggali.

Contoh: "User meninggalkan checkout" (symptom) → "Waktu loading > 8 detik karena API call sequential" (root cause).

### System Thinking

Setiap masalah riset TI harus terikat pada komponen sistem: **Input → Process → Output → Outcome → Constraints → Stakeholders**.

### Problem Quality Check

Masalah riset yang layak harus memenuhi 5 kriteria:
- **Clarity** — Satu orang membaca akan paham
- **Measurability** — Ada metrik kuantitatif
- **Relevance** — Penting untuk domain
- **Testability** — Bisa gagal (falsifiable)
- **Impact** — Ada kontribusi jika terjawab

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Tujuan | Menyelesaikan masalah (*solve*) | Memahami dan membuktikan (*understand & prove*) |
| Masalah | Bug, error, fitur belum ada | Gap dalam pengetahuan |
| Scope | Selesaikan semua yang perlu | Batasi agar bisa dibuktikan |
| Output | Working system | Evidence, paper, replicable findings |

### Istilah Penting

- **Problem Statement** — Formulasi tertulis: konteks sistem + gap + dampak + justifikasi
- **System Context** — Deskripsi lengkap: input, proses, output, outcome, constraints, stakeholders
- **Problem Drift** — Masalah "bermutasi" dari pendahuluan ke metodologi karena statement awal tidak presisi
- **Solution-First Thinking** — Memulai dari solusi tanpa masalah yang jelas — berbahaya dalam riset
- **Operational Definition** — Definisi variabel yang cukup jelas agar peneliti lain bisa mengukur hal yang sama

---

## Template A.2 — Problem Statement Builder

```
PROBLEM STATEMENT BUILDER

Domain & Konteks
  Domain   : Computer Vision / Deep Learning
  Konteks  : Klasifikasi otomatis penyakit daun padi menggunakan citra digital.

System Context
  Input       : Dataset Rice Leafs yang terdiri dari 3.355 citra daun padi dalam empat kelas, yaitu Healthy, Leaf Blast, Hispa, dan Brown Spot.
  Process     : Preprocessing citra, pelatihan model EfficientNet-B6 menggunakan pendekatan Transfer Learning, kemudian evaluasi performa model menggunakan metrik klasifikasi.
  Output      : Prediksi kelas penyakit daun padi (Healthy, Leaf Blast, Hispa, atau Brown Spot).
  Outcome     : Membantu petani dan penyuluh pertanian melakukan identifikasi penyakit daun padi secara lebih cepat dan objektif.
  Constraints : Dataset berasal dari sumber publik, distribusi kelas tidak seimbang, serta kondisi citra belum sepenuhnya merepresentasikan kondisi nyata di lapangan.
  Stakeholders: Petani, penyuluh pertanian, peneliti bidang Artificial Intelligence, dan akademisi.

Fenomena → Problem
  Fenomena yang diamati           : Identifikasi penyakit daun padi masih banyak dilakukan secara manual sehingga memerlukan waktu dan bergantung pada pengalaman pengamat.
  Gejala (symptom) yang terukur   : Kesalahan identifikasi penyakit dapat menyebabkan keterlambatan penanganan sehingga menurunkan hasil panen.
  Masalah yang didiagnosis        : Belum optimalnya pemanfaatan model Deep Learning sebagai alat bantu identifikasi penyakit daun padi.
  Masalah riset (researchable)    : Bagaimana performa model EfficientNet-B6 dalam mengklasifikasikan penyakit daun padi berdasarkan citra digital?
  Variabel yang terukur           : Accuracy, Precision, Recall, F1-Score, AUC, dan Confusion Matrix.

Problem Quality Check
  [x] Clarity
  [x] Measurability
  [x] Relevance
  [x] Testability
  [x] Impact

Problem Statement (1 paragraf)

Identifikasi penyakit daun padi secara manual masih memerlukan waktu, pengalaman, dan berpotensi menimbulkan kesalahan diagnosis sehingga dapat menghambat penanganan penyakit pada tanaman. Salah satu pendekatan yang banyak digunakan adalah pemanfaatan Deep Learning untuk melakukan klasifikasi citra penyakit tanaman secara otomatis. Artikel yang dianalisis mengusulkan penggunaan arsitektur EfficientNet-B6 sebagai model klasifikasi penyakit daun padi menggunakan dataset Rice Leafs. Penelitian tersebut menjadi dasar dalam menyusun proposal penelitian untuk mengevaluasi penerapan EfficientNet-B6 sebagai solusi klasifikasi penyakit daun padi menggunakan pendekatan Transfer Learning.
```

---

## Latihan 1 — Dari Topik ke Masalah Riset

Pilih satu topik di bidang TI yang diminati. Transformasikan melalui 5 tahap Problem Formation Model.

**Topik awal:** Klasifikasi Penyakit Daun Padi Menggunakan Deep Learning


| Tahap                          | Hasil                                                                                                                   |
| ------------------------------ | ----------------------------------------------------------------------------------------------------------------------- |
| Reality                        | Penyakit daun padi masih banyak didiagnosis secara manual sehingga proses identifikasi memerlukan waktu dan pengalaman. |
| Observed Issue (Symptom)       | Kesalahan identifikasi menyebabkan keterlambatan penanganan penyakit yang berdampak pada penurunan hasil panen.         |
| Diagnosed Problem (Root Cause) | Belum optimalnya penerapan model Deep Learning untuk membantu identifikasi penyakit daun padi secara otomatis.          |
| Researchable Problem           | Bagaimana kemampuan model EfficientNet-B6 dalam mengklasifikasikan penyakit daun padi berdasarkan citra digital?        |
| Measurable Variable            | Accuracy, Precision, Recall, F1-Score, AUC, dan Confusion Matrix.                                                       |


Apakah terjebak solution-first thinking? [ ] Ya / [x] Tidak

Justifikasi: Permasalahan penelitian diawali dari kebutuhan identifikasi penyakit daun padi yang masih dilakukan secara manual. Solusi berupa penggunaan EfficientNet-B6 dipilih setelah dilakukan kajian terhadap artikel yang menjadi referensi penelitian.
---

## Latihan 2 — System Context Decomposition

Gambarkan konteks sistem dari masalah riset di Latihan 1.

| Komponen     | Deskripsi                                                                                                                                                       |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Input        | Dataset Rice Leafs sebanyak 3.355 citra yang terdiri dari empat kelas penyakit daun padi.                                                                       |
| Process      | Preprocessing citra, pelatihan model EfficientNet-B6 menggunakan pendekatan Transfer Learning, kemudian evaluasi performa model menggunakan metrik klasifikasi. |
| Output       | Prediksi kelas penyakit daun padi beserta probabilitas hasil klasifikasi.                                                                                       |
| Outcome      | Membantu proses identifikasi penyakit daun padi secara lebih cepat dan objektif.                                                                                |
| Constraints  | Dataset publik, distribusi kelas tidak seimbang, serta kondisi citra belum sepenuhnya mewakili kondisi nyata di lapangan.                                       |
| Stakeholders | Petani, penyuluh pertanian, peneliti Artificial Intelligence, dan akademisi.                                                                                    |


**
Komponen mana yang paling relevan dengan masalah riset? Komponen Process.Fokus utama artikel adalah mengevaluasi kemampuan model EfficientNet-B6 dalam melakukan klasifikasi penyakit daun padi melalui proses pelatihan dan evaluasi model.


## Latihan 3 — Problem Quality Check

Evaluasi problem statement yang sudah dibuat menggunakan 5 kriteria.

| Kriteria      | Skor (1–5) | Justifikasi                                                                                         |
| ------------- | ---------- | --------------------------------------------------------------------------------------------------- |
| Clarity       | 5          | Permasalahan identifikasi penyakit daun padi dijelaskan secara jelas dan spesifik.                  |
| Measurability | 5          | Performa model diukur menggunakan Accuracy, Precision, Recall, F1-Score, AUC, dan Confusion Matrix. |
| Relevance     | 5          | Relevan dengan penerapan Artificial Intelligence pada bidang pertanian.                             |
| Testability   | 5          | Permasalahan dapat diuji menggunakan model Deep Learning dan dataset citra daun padi.               |
| Impact        | 5          | Berpotensi membantu proses identifikasi penyakit daun padi secara lebih cepat dan akurat.           |


**Skor total:** 25 / 25

**Problem statement versi final (1 paragraf):**
Identifikasi penyakit daun padi secara manual masih memiliki keterbatasan karena membutuhkan pengalaman, waktu, dan ketelitian pengamat sehingga berpotensi menyebabkan keterlambatan penanganan penyakit. Berdasarkan artikel yang dianalisis, model EfficientNet-B6 merupakan salah satu pendekatan Deep Learning yang dapat dimanfaatkan untuk melakukan klasifikasi penyakit daun padi secara otomatis menggunakan dataset Rice Leafs. Hasil analisis terhadap artikel tersebut menjadi dasar dalam penyusunan proposal penelitian yang selanjutnya akan mengimplementasikan dan mengevaluasi model EfficientNet-B6 menggunakan pendekatan Transfer Learning.
---

## Refleksi

> Bandingkan "masalah" yang biasa ditemui saat coding (bug, error) dengan masalah riset. Apa perbedaan fundamental dalam cara mendefinisikan dan mendekati keduanya?

**Jawaban:**
Masalah pada proses pemrograman umumnya bersifat teknis, seperti bug atau error yang dapat diselesaikan dengan memperbaiki kode agar sistem berjalan sesuai spesifikasi. Sebaliknya, masalah riset berfokus pada pencarian dan pembuktian pengetahuan baru melalui proses ilmiah. Dalam penelitian ini, masalah yang dikaji bukan hanya bagaimana membangun model klasifikasi, tetapi juga bagaimana membuktikan bahwa model tersebut layak digunakan berdasarkan hasil evaluasi yang objektif. Oleh karena itu, pendekatan penyelesaiannya memerlukan analisis literatur, penyusunan proposal, implementasi, dan evaluasi secara sistematis.
