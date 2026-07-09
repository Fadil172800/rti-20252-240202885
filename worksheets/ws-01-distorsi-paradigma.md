# WS-01: Distorsi & Paradigma

> **Bab 1 — Research Mindset in IT**

---

## Ringkasan Materi

### Research Trust Model

Pengetahuan ilmiah tidak muncul langsung dari kenyataan. Ia melewati **6 tahap transformasi** yang masing-masing rawan distorsi:

```
Reality → Data → Processing → Analysis → Inference → Knowledge
```

Etika mencegah distorsi yang disengaja (fabrikasi, cherry-picking). Validitas mendeteksi distorsi yang tidak disengaja (confounding variable, sampling bias).

### Tiga Jenis Validitas

| Jenis | Pertanyaan | Contoh Ancaman |
|-------|-----------|----------------|
| **Internal Validity** | Apakah hubungan kausal benar ada? | Confounding variable |
| **External Validity** | Apakah bisa digeneralisasi? | Dataset terlalu homogen |
| **Construct Validity** | Apakah mengukur hal yang benar? | Metrik tidak sesuai klaim |

### Paradigma Riset

Mata kuliah ini menggunakan pendekatan **Positivist** (fenomena TI bisa diukur objektif melalui eksperimen terkontrol) diperkuat **Design Science Research** (DSR). Penting untuk membedakan keduanya:

| Paradigma | Cara Kerja | Contoh di TI |
|-----------|-----------|---------------|
| **Positivis** | Uji hipotesis dengan eksperimen terkontrol | Apakah CNN lebih akurat dari RF pada dataset X? |
| **Design Science Research** | Bangun artefak (sistem/model/framework) untuk menguji proposisi | Dapatkah arsitektur hybrid CNN+LSTM membuktikan peningkatan recall ≥5%? |
| **Interpretivis** | Pahami makna melalui konteks & kualitatif | Bagaimana peneliti manafsirkan anomali data sensor IoT? |

Dalam DSR, artefak **bukan tujuan akhir** — ia adalah instrumen untuk menghasilkan pengetahuan. Pertanyaan riset tetap harus difalsifikasi.

### Mode Berpikir Peneliti

**Curious** (mempertanyakan fenomena) → **Critical** (mengevaluasi klaim berdasarkan bukti) → **Systematic** (merancang investigasi terstruktur dan reproducible).

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Tujuan | Membuat sistem yang bekerja | Menghasilkan pengetahuan yang valid |
| Pertanyaan khas | "Bagaimana membuatnya jalan?" | "Apakah klaim ini benar?" |
| Ukuran sukses | Sistem berfungsi, client puas | Hipotesis terjawab, temuan tervalidasi |
| Kegagalan | Harus dihindari | Harus dilaporkan (negative result = kontribusi) |

### Istilah Penting

- **Research Mindset** — Pola pikir yang menuntut bukti dan mempertanyakan asumsi
- **Research Ethics** — Prinsip perilaku: kejujuran, objektivitas, keterbukaan, akuntabilitas
- **HARKing** — Hypothesizing After Results are Known — merumuskan hipotesis setelah melihat data
- **Falsifiability** — Hipotesis harus bisa dibuktikan salah

---

## Template A.1 — Research Mindset Self-Assessment

```
Nama Peneliti    : Syukron Nur Fadillah
Tanggal          : 23 April 2026

1. Ketika membaca klaim bahwa EfficientNet-B6 meningkatkan akurasi klasifikasi penyakit daun padi hingga 77,05%:

- Pertanyaan pertama saya:
Apakah performa model EfficientNet-B6 tersebut konsisten pada seluruh proses evaluasi, atau hanya diperoleh pada kondisi tertentu sehingga belum tentu dapat digeneralisasikan?

- Data yang dibutuhkan untuk verifikasi:
Nilai Accuracy, Precision, Recall, F1-Score, AUC, Confusion Matrix, serta metode evaluasi yang digunakan pada penelitian sehingga hasilnya dapat dianalisis secara menyeluruh.

2. Posisi paradigma

Pendekatan:
[✓] Positivis
[ ] Interpretivis
[✓] Design Science
[ ] Mixed

Alasan:
Artikel membangun artefak berupa model klasifikasi penyakit daun padi menggunakan EfficientNet-B6, kemudian mengevaluasi performanya secara objektif menggunakan metrik kuantitatif sehingga sesuai dengan paradigma Positivis dan Design Science Research.

3. Identifikasi distorsi

Asumsi tersembunyi:
Dataset Rice Leafs dianggap mampu merepresentasikan karakteristik penyakit daun padi pada kondisi nyata.

Sumber bias potensial:
Distribusi jumlah citra pada setiap kelas tidak seimbang sehingga model berpotensi lebih baik mengenali kelas mayoritas dibandingkan kelas minoritas.

Langkah mitigasi:
Performa model dianalisis menggunakan Accuracy, Precision, Recall, F1-Score, AUC, dan Confusion Matrix sehingga kemampuan model pada setiap kelas dapat dievaluasi secara lebih komprehensif.

4. Komitmen etika

Data yang tidak akan dimanipulasi:
Seluruh hasil analisis terhadap artikel maupun hasil penelitian yang akan dilakukan nantinya dilaporkan secara jujur tanpa mengubah atau menghilangkan data yang tidak sesuai harapan.

Batasan yang diakui sejak awal:
Artikel menggunakan dataset publik Rice Leafs sehingga hasil penelitian masih perlu divalidasi menggunakan dataset lain agar kemampuan generalisasi model dapat diketahui.
```

---

## Latihan 1 — Identifikasi Distorsi

Pilih satu paper riset di bidang TI yang mengklaim "metode X meningkatkan performa." Telusuri setiap tahap Research Trust Model.

> **Panduan pencarian paper:** Gunakan [IEEE Xplore](https://ieeexplore.ieee.org), [ACM Digital Library](https://dl.acm.org), atau Google Scholar. Pilih paper **tahun 2020 ke atas**, di topik yang Anda minati: deteksi anomali, klasifikasi citra, NLP, keamanan siber, IoT, dsb.
>
> **Contoh domain TI:** "Deteksi anomali lalu-lintas jaringan menggunakan CNN — akurasi meningkat 94% vs baseline SVM 87%." Distorsi potensial: apakah dataset normal/anomali seimbang? Apakah hanya diuji pada satu vendor traffic?

**Paper yang dipilih:**
> Judul: Klasifikasi Penyakit Daun Padi Menggunakan Model Deep Learning EfficientNet-B6
> Penulis: Amanda Caecilia Milano, Achmad Yasid, Rima Tri Wahyuningrum (2024)
> Sumber: JITET (Jurnal Informatika dan Teknik Elektro Terapan)
> DOI: http://dx.doi.org/10.23960/jitet.v12i1.3855

| Tahap                 | Apa yang Dilakukan                                                                                                        | Potensi Distorsi                                                                                                                 |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| Reality → Data        | Peneliti menggunakan dataset Rice Leafs dari Kaggle yang terdiri dari 3.355 citra empat kelas penyakit daun padi.         | Dataset publik memiliki kondisi citra yang relatif bersih sehingga belum sepenuhnya merepresentasikan kondisi nyata di lapangan. |
| Data → Processing     | Seluruh citra diubah menjadi ukuran tertentu sesuai kebutuhan model dan dilakukan preprocessing sebelum proses pelatihan. | Proses resize dapat menghilangkan sebagian detail tekstur penyakit pada daun.                                                    |
| Processing → Analysis | Model EfficientNet-B6 dilatih menggunakan beberapa konfigurasi ukuran input dan jumlah epoch.                             | Hasil model dapat dipengaruhi oleh pemilihan parameter pelatihan sehingga performa belum tentu sama pada konfigurasi lain.       |
| Analysis → Inference  | Model dievaluasi menggunakan Accuracy, Precision, Recall, F1-Score, AUC, dan Confusion Matrix.                            | Nilai akurasi tertinggi belum tentu mencerminkan performa keseluruhan apabila tidak dianalisis bersama metrik lain.              |
| Inference → Knowledge | Peneliti menyimpulkan bahwa EfficientNet-B6 memiliki performa yang baik pada dataset Rice Leafs.                          | Generalisasi hasil penelitian masih terbatas karena hanya diuji menggunakan satu dataset.                                        |


Distorsi paling besar terjadi pada tahap: Reality → Data (External Validity)

Justifikasi: Dataset Rice Leafs berasal dari Kaggle dengan kondisi citra yang telah dikurasi sehingga berbeda dengan kondisi nyata di lahan pertanian yang memiliki variasi pencahayaan, latar belakang, kualitas kamera, dan kondisi daun yang lebih kompleks. Perbedaan tersebut dapat memengaruhi kemampuan model ketika diterapkan pada lingkungan nyata.

Dua distorsi spesifik yang teridentifikasi:

1.Class Imbalance Bias, karena jumlah citra pada setiap kelas tidak seimbang sehingga model berpotensi lebih baik mengenali kelas mayoritas dibandingkan kelas minoritas.
2.Resolution Downscaling Distortion, karena perubahan ukuran citra dapat menyebabkan hilangnya sebagian informasi tekstur yang penting untuk membedakan jenis penyakit daun.

## Latihan 2 — Analisis Kasus Etika

Skenario: Seorang peneliti menemukan bahwa jika 3 data point outlier dihapus, hasil eksperimennya menjadi signifikan. Dengan outlier, hasilnya tidak signifikan.


| Perspektif           | Analisis                                                                                                                                                                                                             |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Kejujuran ilmiah** | Peneliti wajib melaporkan seluruh hasil evaluasi secara apa adanya tanpa hanya menampilkan hasil terbaik. Seluruh metrik evaluasi harus disajikan agar pembaca memperoleh gambaran performa model secara menyeluruh. |
| **Transparansi**     | Peneliti harus menjelaskan dataset, metode preprocessing, konfigurasi model, parameter pelatihan, serta keterbatasan penelitian sehingga eksperimen dapat dipahami dan direproduksi oleh peneliti lain.              |
| **Peer Review**      | Reviewer akan mengevaluasi apakah metode penelitian dilakukan secara benar, apakah hasil yang disajikan konsisten dengan metodologi, serta apakah terdapat indikasi manipulasi data atau cherry-picking.             |


*Keputusan akhir dan justifikasi:*
>Outlier atau data yang sulit diklasifikasikan tidak boleh dihapus tanpa alasan ilmiah yang jelas. Jika terdapat data yang memang rusak atau tidak valid, alasan penghapusannya harus dijelaskan secara transparan pada bagian metodologi sehingga integritas penelitian tetap terjaga.
---

## Latihan 3 — Posisi Paradigma

*Topik riset:* Topik riset: Klasifikasi penyakit daun padi menggunakan model deep learning EfficientNet-B6.

> *Skala 1–5:* 1 = tidak sesuai sama sekali dengan topik ini, 5 = sangat sesuai dan dominan digunakan pada riset bertopik serupa.

| Kriteria                      | Positivis                                                                                 | Interpretivis                                                    | Design Science                                                                              |
| ----------------------------- | ----------------------------------------------------------------------------------------- | ---------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Kesesuaian dengan topik (1–5) | **5**                                                                                     | **1**                                                            | **5**                                                                                       |
| Jenis data yang dikumpulkan   | Data kuantitatif berupa Accuracy, Precision, Recall, F1-Score, AUC, dan Confusion Matrix. | Tidak digunakan.                                                 | Artefak berupa model klasifikasi EfficientNet-B6 beserta konfigurasi pelatihannya.          |
| Limitasi paradigma            | Bergantung pada kualitas dataset dan metrik evaluasi.                                     | Tidak menghasilkan evaluasi kuantitatif terhadap performa model. | Fokus pada pembangunan artefak sehingga evaluasi tetap bergantung pada kualitas eksperimen. |


Paradigma yang dipilih: Positivis + Design Science Research (DSR)

Alasan: Artikel membangun sebuah artefak berupa model klasifikasi penyakit daun padi menggunakan EfficientNet-B6 untuk menyelesaikan permasalahan klasifikasi citra. Kinerja model kemudian dievaluasi secara objektif menggunakan metrik kuantitatif sehingga penelitian sesuai dengan paradigma Positivis dan Design Science Research.
---

## Refleksi

> Pertanyaan Refleksi: Sebelum membaca materi ini, apakah Anda pernah mempertanyakan klaim "akurasi tinggi"? Setelah memahami rantai distorsi, pertanyaan apa yang sekarang akan Anda ajukan saat membaca paper klasifikasi citra berbasis deep learning?

**Jawaban:**
Sebelum mempelajari materi ini, saya cenderung menerima klaim akurasi tinggi sebagai indikator utama keberhasilan suatu model. Setelah memahami konsep Research Trust Model, saya menyadari bahwa nilai akurasi saja belum cukup untuk menilai kualitas penelitian.

Ketika membaca paper klasifikasi citra berbasis deep learning, saya akan mempertanyakan bagaimana dataset diperoleh, bagaimana proses preprocessing dilakukan, apakah terdapat ketidakseimbangan data, metode evaluasi yang digunakan, serta apakah hasil penelitian telah diuji menggunakan dataset lain untuk membuktikan kemampuan generalisasi model. Selain itu, saya juga akan memperhatikan apakah seluruh proses penelitian dijelaskan secara transparan sehingga hasilnya dapat direproduksi oleh peneliti lain.
