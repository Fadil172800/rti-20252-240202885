# WS-15: Scientific Writing

> **Bab 15 — Penulisan Ilmiah**

---

## Ringkasan Materi

### Scientific Argument Flow

```
Problem → Gap → RQ → Method → Result → Analysis → Conclusion → Contribution
```

Paper ilmiah adalah **satu argumen utuh** dari masalah ke kontribusi. Setiap node harus terhubung logis ke node sebelum dan sesudahnya.

### Struktur IMRAD

| Section | Peran | Pertanyaan Kunci |
|---------|-------|-----------------|
| **Introduction** | Motivasi + frame | Why is this needed? |
| **Method** | Deskripsi (reproducible) | How was it done? |
| **Results** | Laporan objektif | What was found? |
| **Discussion** | Interpretasi + refleksi | What does it mean? |
| **Conclusion** | Ringkasan + kontribusi | So what? |

### Logical Flow — "Red Thread"

Setiap paragraf menjawab satu pertanyaan dan memicu pertanyaan berikutnya. Alur logis ini harus terasa di tiga level:
1. **Antar-kalimat** dalam paragraf
2. **Antar-paragraf** dalam section
3. **Antar-section** dalam paper

### Internal Consistency

Setiap elemen yang dijanjikan di Introduction harus hadir di Discussion/Conclusion.

**Consistency Matrix:**
```
           Intro  Method  Result  Discuss  Conclude
RQ1          ✓      ✓       ✓       ✓        ✓
RQ2          ✓      ✓       ✓       ✗ ←      ✓
Metrik-X     ✗      ✗       ✓ ←     ✗        ✗
```
**Masalah:** RQ2 dibahas di semua bagian kecuali Discussion. Metrik-X muncul di Result tapi tidak diperkenalkan di Method.

### Writing Quality Triad

| Kualitas | Deskripsi | Contoh Buruk → Baik |
|----------|----------|---------------------|
| **Clarity** | Dipahami sekali baca | "Performa meningkat" → "Accuracy meningkat dari 85.3% ke 89.7%" |
| **Precision** | Istilah eksak, tanpa ambiguitas | "signifikan" → "signifikan secara statistik (p=0.003, d=1.2)" |
| **Conciseness** | Setiap kata menambah informasi | Hapus kalimat redundan, filler words |

### Urutan Penulisan yang Disarankan

1. **Method & Results** — paling stabil, tulis pertama
2. **Discussion** — interpretasi berdasarkan hasil
3. **Introduction** — frame sesuai temuan aktual
4. **Abstract & Conclusion** — terakhir

### Target Jumlah Kata

| Section | Target |
|---------|--------|
| Introduction | 500–700 |
| Related Work | 700–1000 |
| Method | 800–1200 |
| Results | 500–800 |
| Discussion | 600–900 |
| Conclusion | 200–400 |

### Jebakan Kognitif

1. "Lebih panjang = lebih lengkap" → conciseness lebih berharga
2. "Introduction harus ditulis pertama" → justru ditulis terakhir
3. "Jargon teknis = lebih ilmiah" → clarity lebih penting
4. "Discussion = ringkasan Results" → Discussion = interpretasi + konteks

---

## Template A.15 — Paper Structure Checklist

```
PAPER STRUCTURE CHECKLIST

Title :
Klasifikasi Penyakit Daun Padi Menggunakan EfficientNet-B6 dengan Pendekatan Transfer Learning

Target :
[x] Laporan
[ ] Jurnal
[ ] Konferensi

Section Check:

[x] Abstract — memuat masalah, metode, hasil utama, dan kontribusi
[x] Introduction — konteks, research gap, research question, kontribusi penelitian
[x] Related Work — membahas penelitian terdahulu dan posisi penelitian
[x] Method — menjelaskan desain penelitian, variabel, dataset, setup, dan prosedur
[x] Results — menyajikan tabel, grafik, confusion matrix, dan hasil evaluasi
[x] Discussion — menginterpretasikan hasil, membandingkan dengan penelitian terdahulu, serta menjelaskan keterbatasan
[x] Conclusion — menjawab research question, menyampaikan kontribusi, dan saran penelitian lanjutan

Consistency Matrix

[x] Research Question konsisten pada Introduction, Method, Results, Discussion, dan Conclusion

[x] Variabel pada Method sesuai dengan hasil pada Results

[x] Klaim pada Discussion didukung oleh data hasil penelitian

[x] Limitasi penelitian dijelaskan pada Discussion dan dijadikan dasar Future Work

Writing Quality

[x] Clarity

[x] Precision

[x] Conciseness
```

---

## Latihan 1 — Paper Outline

Buat outline paper untuk riset Anda menggunakan struktur IMRAD.

| Section          | Konten Utama                                                                                                                                                                                                        | Target Kata |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------- |
| **Abstract**     | Menjelaskan permasalahan identifikasi penyakit daun padi, penggunaan EfficientNet-B6 dengan pendekatan transfer learning, hasil evaluasi model, dan kontribusi penelitian.                                          | 200–250     |
| **Introduction** | Menguraikan pentingnya deteksi penyakit daun padi, research gap dari penelitian sebelumnya, research question, tujuan penelitian, dan kontribusi penelitian.                                                        | 500–700     |
| **Related Work** | Membahas penelitian terdahulu mengenai klasifikasi penyakit daun menggunakan CNN dan EfficientNet serta posisi penelitian ini dibandingkan penelitian sebelumnya.                                                   | 700–1000    |
| **Method**       | Menjelaskan dataset Rice Leafs, preprocessing, arsitektur EfficientNet-B6, transfer learning, konfigurasi pelatihan, serta metode evaluasi menggunakan accuracy, precision, recall, F1-score, dan confusion matrix. | 800–1200    |
| **Results**      | Menyajikan hasil evaluasi model berupa tabel metrik, confusion matrix, classification report, grafik accuracy, dan grafik loss tanpa interpretasi.                                                                  | 500–800     |
| **Discussion**   | Menginterpretasikan hasil penelitian, membandingkan dengan penelitian acuan, menjelaskan keterbatasan penelitian, serta memberikan rekomendasi penelitian lanjutan.                                                 | 600–900     |
| **Conclusion**   | Menjawab research question, merangkum kontribusi penelitian, serta memberikan saran pengembangan penelitian berikutnya.                                                                                             | 200–400     |

---

## Latihan 2 — Consistency Matrix

Buat consistency matrix untuk memverifikasi internal consistency paper Anda.

|                                                          | Intro | Method | Result | Discussion | Conclusion |
| -------------------------------------------------------- | :---: | :----: | :----: | :--------: | :--------: |
| **RQ**                                                   |   ✓   |    ✓   |    ✓   |      ✓     |      ✓     |
| **Metrik utama (Accuracy, Precision, Recall, F1-Score)** |   ✓   |    ✓   |    ✓   |      ✓     |      ✓     |
| **Variabel Bebas (EfficientNet-B6 + Transfer Learning)** |   ✓   |    ✓   |    ✓   |      ✓     |      ✓     |
| **Variabel Terikat (Performa Klasifikasi)**              |   ✓   |    ✓   |    ✓   |      ✓     |      ✓     |
| **Kontribusi Penelitian**                                |   ✓   |    ✓   |    ✓   |      ✓     |      ✓     |


**Isi setiap sel:** ✓ (ada & konsisten), ✗ (missing), ~ (ada tapi inkonsisten)

**Inkonsistensi yang ditemukan:**
> Tidak ditemukan inkonsistensi. Research question, metode, variabel penelitian, metrik evaluasi, hasil penelitian, serta kesimpulan telah disusun secara konsisten sesuai dengan implementasi penelitian.

**Tindakan perbaikan:**
> Memastikan seluruh istilah yang digunakan pada proposal, implementasi, hasil penelitian, dan laporan akhir tetap konsisten sehingga tidak terjadi perbedaan interpretasi pada setiap bagian penulisan ilmiah.
---

## Latihan 3 — Writing Quality Check

Ambil satu paragraf dari tulisan Anda (atau tulis paragraf baru) dan evaluasi kualitasnya.

**Paragraf asli:**
> Penelitian ini menggunakan model EfficientNet-B6 dengan pendekatan transfer learning untuk mengklasifikasikan penyakit daun padi. Model dilatih menggunakan dataset Rice Leafs dan dievaluasi menggunakan accuracy, precision, recall, F1-score, serta confusion matrix.

| Kriteria        | Evaluasi                                            | Perbaikan                                                         |
| --------------- | --------------------------------------------------- | ----------------------------------------------------------------- |
| **Clarity**     | Sudah jelas, namun belum menyebut hasil penelitian. | Tambahkan nilai accuracy yang diperoleh.                          |
| **Precision**   | Istilah teknis sudah tepat.                         | Sebutkan pendekatan transfer learning sebagai feature extraction. |
| **Conciseness** | Tidak terdapat kalimat yang berulang.               | Tetap dipertahankan.                                              |

**Paragraf setelah perbaikan:**
> Penelitian ini menggunakan model EfficientNet-B6 dengan pendekatan transfer learning sebagai feature extractor untuk mengklasifikasikan penyakit daun padi menggunakan dataset Rice Leafs. Model dievaluasi menggunakan accuracy, precision, recall, F1-score, dan confusion matrix, serta menghasilkan accuracy sebesar 63,04% pada data validasi sehingga menunjukkan bahwa pendekatan tersebut mampu melakukan klasifikasi penyakit daun padi pada lingkungan komputasi Google Colab Free.

---

## Refleksi

> Apa perbedaan antara menulis "tentang" riset dan menulis sebagai "argumen" riset? Bagaimana urutan penulisan (Method → Discussion → Introduction) mengubah kualitas tulisan?

> Menulis tentang riset hanya menjelaskan proses atau aktivitas yang dilakukan selama penelitian. Sebaliknya, menulis sebagai argumen riset berarti setiap bagian tulisan disusun untuk mendukung jawaban terhadap research question melalui bukti yang diperoleh dari hasil penelitian. Dengan demikian, seluruh bagian paper memiliki hubungan logis dari masalah hingga kesimpulan.

Menulis dimulai dari bagian Method, kemudian Results dan Discussion, baru dilanjutkan dengan Introduction, membantu menjaga konsistensi antara tujuan penelitian, metode yang digunakan, hasil yang diperoleh, dan kesimpulan. Pendekatan ini membuat penulisan lebih terarah karena seluruh argumen dibangun berdasarkan hasil penelitian yang benar-benar telah diperoleh, bukan berdasarkan asumsi sebelum penelitian dilakukan.
