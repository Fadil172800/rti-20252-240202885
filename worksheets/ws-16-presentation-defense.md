# WS-16: Presentation & Defense (UAS)

> **Bab 16 — Presentasi & Pertahanan Ilmiah**

---

## Ringkasan Materi

### Scientific Defense Model

```
Research Work → Presentation → Questioning → Defense → Evaluation → Acceptance
```

### Presentasi ≠ Ringkasan Paper

| Paper | Presentasi |
|-------|-----------|
| Dibaca (self-paced) | Didengar (presenter-paced) |
| Detail lengkap | Ide kunci + highlight |
| Tabel numerik detail | Grafik visual + angka kunci |
| Pembaca bisa re-read | Audiens dengar sekali |

**Prinsip:** Presentasi membutuhkan **reformulasi**, bukan kompresi. Medium berbeda = pendekatan berbeda.

### Claim-Evidence-Reasoning (CER)

Setiap jawaban defense harus memiliki:
1. **Claim** — Pernyataan yang dijawab
2. **Evidence** — Data/fakta pendukung
3. **Reasoning** — Logika yang menghubungkan evidence ke claim

**Contoh:**
| Pertanyaan | Bad Answer | Good Answer (CER) |
|-----------|-----------|-------------------|
| "Kenapa hanya 3 dataset?" | "Tiga sudah cukup" | "3 dataset mewakili variasi: small-clean, medium-clean, medium-noisy [E]. Generalisasi perlu validasi lanjut — listed as limitation [R]" |
| "Hasil DS-3 menurun?" | "Itu outlier" | "Ya, karena distribusi heavy-tail melanggar asumsi Gaussian [E]. Ini menunjukkan boundary condition metode [R]" |
| "Effect size?" | "p=0.003, jadi signifikan" | "Cohen's d=1.2 (large effect) [E] — bukan hanya signifikan tapi substansial [R]" |

### Slide Design — One Slide, One Message

**Optimal 9-Slide Plan (15 menit):**

| # | Slide | Waktu | Pesan |
|---|-------|-------|-------|
| 1 | Title + context | 1 min | Apa ini tentang apa |
| 2 | Problem + motivation | 2 min | Mengapa penting |
| 3 | Gap + RQ | 1.5 min | Apa yang belum terjawab |
| 4 | Method overview | 2 min | Bagaimana dijawab (diagram) |
| 5 | Key result — tabel | 2 min | Temuan utama |
| 6 | Key result — grafik | 2 min | Pola visual |
| 7 | Interpretation + failure | 2 min | Apa artinya |
| 8 | Limitation + future | 1.5 min | Batasan & arah |
| 9 | Conclusion + contribution | 1 min | Closing message |

### Anticipatory Defense

Prediksi pertanyaan berdasarkan kategori:

| Kategori | Contoh Pertanyaan |
|---------|------------------|
| Problem | "Mengapa masalah ini penting?" |
| Gap | "Bagaimana dengan studi X yang sudah menjawab ini?" |
| Method | "Mengapa metode ini, bukan Y?" |
| Results | "Bagaimana menjelaskan anomali di DS-3?" |
| Generalization | "Apakah bisa diterapkan di domain lain?" |

### Tiga Prinsip Jawaban

1. **Direct** — Jawab dulu, elaborasi kemudian
2. **Data-based** — Tunjuk evidence spesifik
3. **Honest** — Akui limitasi jika memang ada

### Jebakan Kognitif

1. "Presentasi = semua yang ada di paper" → terlalu padat
2. "Slide cantik = presentasi bagus" → konten > estetika
3. "Tidak bisa jawab = gagal" → "I don't know, but..." menunjukkan kejujuran
4. "Tidak perlu latihan — saya paham riset saya" → latihan = menemukan celah

---


## Template A.16 — Defense Preparation Sheet

```
DEFENSE PREPARATION

Slide Deck Plan

Total slides   : 10
Time per slide : ±1,5 menit
Total time     : ±15 menit

Slide Outline

| # | Pesan Utama | Visual | Waktu |
|---|---|---|---|
| 1 | Judul Penelitian | Cover | 1 menit |
| 2 | Latar Belakang & Permasalahan | Ilustrasi penyakit daun padi | 2 menit |
| 3 | Research Gap & Research Question | Diagram penelitian | 1,5 menit |
| 4 | Metode Penelitian | Flowchart penelitian | 2 menit |
| 5 | Dataset & Arsitektur EfficientNet-B6 | Diagram model | 2 menit |
| 6 | Hasil Penelitian | Tabel Accuracy, Precision, Recall, F1-Score | 2 menit |
| 7 | Confusion Matrix & Grafik Training | Confusion Matrix + Accuracy/Loss | 2 menit |
| 8 | Pembahasan & Keterbatasan | Ringkasan hasil | 1,5 menit |
| 9 | Kesimpulan | Poin-poin utama | 1 menit |
| 10 | Sesi Tanya Jawab | Closing | - |

Anticipatory Defense Matrix

| Kategori | Pertanyaan Potensial | Jawaban (CER) |
|---|---|---|
| Problem | Mengapa memilih klasifikasi penyakit daun padi? | Deteksi dini penyakit sangat penting untuk membantu petani. Penelitian menggunakan dataset Rice Leafs dan menghasilkan accuracy 63,04%, sehingga menunjukkan model mampu melakukan klasifikasi otomatis. |
| Gap | Mengapa menggunakan EfficientNet-B6? | EfficientNet-B6 memiliki performa yang baik pada penelitian terdahulu dan efisien dalam transfer learning sehingga dipilih sebagai model penelitian. |
| Method | Mengapa tidak menggunakan fine-tuning? | Penelitian menggunakan feature extraction karena keterbatasan sumber daya Google Colab Free sehingga metode dipilih agar proses pelatihan tetap dapat berjalan dengan baik. |
| Results | Mengapa akurasi lebih rendah dibanding penelitian acuan? | Perbedaan konfigurasi eksperimen, penggunaan single split, serta keterbatasan komputasi menjadi faktor yang memengaruhi hasil penelitian. |
| Generalization | Apakah model dapat digunakan pada dataset lain? | Secara umum dapat digunakan, namun diperlukan pelatihan ulang dan evaluasi kembali karena karakteristik dataset dapat berbeda. |

Latihan

Latihan 1 : Sebelum seminar hasil — latihan penyampaian materi.

Latihan 2 : Simulasi presentasi bersama teman.

Latihan 3 : Evaluasi waktu presentasi dan perbaikan jawaban.
```

---

## Latihan 1 — Slide Outline

Rencanakan presentasi 15 menit untuk riset Anda.

| No | Pesan Utama | Visual yang Digunakan | Waktu |
|---|---|---|---|
| 1 | Judul penelitian dan identitas peneliti | Cover penelitian | 1 menit |
| 2 | Latar belakang dan permasalahan | Ilustrasi penyakit daun padi | 2 menit |
| 3 | Research gap dan research question | Diagram alur penelitian | 1,5 menit |
| 4 | Metode penelitian | Flowchart metode | 2 menit |
| 5 | Dataset dan arsitektur EfficientNet-B6 | Diagram arsitektur model | 2 menit |
| 6 | Hasil evaluasi model | Tabel Accuracy, Precision, Recall, dan F1-Score | 2 menit |
| 7 | Confusion Matrix dan grafik Accuracy/Loss | Heatmap dan grafik | 2 menit |
| 8 | Pembahasan, keterbatasan, dan saran | Ringkasan poin utama | 1,5 menit |
| 9 | Kesimpulan | Poin-poin kesimpulan | 1 menit |

**Total waktu estimasi:** 15 menit

---

## Latihan 2 — Anticipatory Defense

Prediksi 5 pertanyaan yang mungkin diajukan penguji, lalu siapkan jawaban CER.

| No | Kategori | Pertanyaan | Claim | Evidence | Reasoning |
|---|---|---|---|---|---|
| 1 | Problem | Mengapa memilih penyakit daun padi? | Deteksi dini penting untuk meningkatkan produktivitas pertanian. | Penyakit daun padi dapat menurunkan hasil panen jika terlambat dideteksi. | Sistem klasifikasi otomatis membantu proses identifikasi penyakit secara lebih cepat. |
| 2 | Method | Mengapa menggunakan EfficientNet-B6? | EfficientNet-B6 memiliki performa yang baik dalam klasifikasi citra. | Model menggunakan bobot pretrained ImageNet dan pendekatan transfer learning. | Transfer learning mempercepat proses pelatihan pada dataset terbatas. |
| 3 | Method | Mengapa tidak menggunakan fine-tuning? | Penelitian menggunakan feature extraction karena keterbatasan komputasi. | Pelatihan dilakukan menggunakan Google Colab Free dengan RAM dan GPU terbatas sehingga fine-tuning EfficientNet-B6 berpotensi membutuhkan waktu dan memori yang lebih besar. | Oleh karena itu feature extraction dipilih agar eksperimen dapat diselesaikan secara stabil sesuai dengan sumber daya yang tersedia. |
| 4 | Results | Mengapa accuracy hanya 63,04%? | Hasil dipengaruhi oleh konfigurasi eksperimen dan distribusi data. | Berdasarkan confusion matrix, kelas **Healthy** memiliki performa lebih baik dibandingkan kelas **Hispa** dan **Leaf Blast**. Performa kelas Hispa dan Leaf Blast lebih rendah dibanding Healthy. | Ketidakseimbangan jumlah data antar kelas memengaruhi kemampuan model dalam melakukan klasifikasi. |
| 5 | Generalization | Apakah metode ini dapat diterapkan pada dataset lain? | Dapat diterapkan dengan proses pelatihan ulang. | EfficientNet-B6 merupakan model umum untuk klasifikasi citra. | Dataset lain memiliki karakteristik berbeda sehingga model perlu dievaluasi kembali. |

---

## Latihan 3 — Simulasi Q&A

Minta teman/kolega mengajukan 3 pertanyaan tentang riset Anda. Catat pertanyaan dan evaluasi jawaban Anda.

| No | Pertanyaan | Jawaban Saya | Evaluasi |
|---|---|---|---|
| 1 | Mengapa menggunakan EfficientNet-B6? | Karena model memiliki performa yang baik pada penelitian terdahulu dan mendukung transfer learning sehingga sesuai dengan penelitian ini. | [✓] Direct [✓] Data-based [✓] Honest |
| 2 | Mengapa tidak membandingkan dengan CNN lain? | Fokus penelitian sejak proposal adalah mengevaluasi performa EfficientNet-B6 menggunakan transfer learning sehingga penelitian tidak dirancang sebagai studi komparatif terhadap beberapa arsitektur CNN. | [✓] Direct [✓] Data-based [✓] Honest |
| 3 | Apa keterbatasan penelitian ini? | Penelitian hanya menggunakan satu konfigurasi model, satu dataset, dan belum melakukan fine-tuning sehingga hasil masih dapat ditingkatkan pada penelitian berikutnya. | [✓] Direct [✓] Data-based [✓] Honest |

**Pertanyaan yang paling sulit dijawab:**
> Mengapa hasil penelitian memiliki accuracy lebih rendah dibandingkan penelitian acuan yang menggunakan model EfficientNet-B6?

**Apa yang perlu disiapkan lebih baik:**
> Menyiapkan penjelasan yang lebih rinci mengenai perbedaan konfigurasi eksperimen, penggunaan feature extraction tanpa fine-tuning, metode validasi, distribusi dataset, serta keterbatasan sumber daya Google Colab Free yang dapat memengaruhi performa model, serta alasan pemilihan konfigurasi penelitian sesuai ruang lingkup proposal.

---

## Refleksi

> Dari seluruh proses WS-01 sampai WS-16 — dari paradigma riset hingga presentasi — bagian mana yang paling mengubah cara Anda berpikir tentang riset? Apa satu hal yang akan selalu Anda terapkan di riset berikutnya?

**Insight terbesar:**
> Proses penyusunan proposal hingga implementasi menunjukkan bahwa penelitian tidak hanya berfokus pada memperoleh hasil terbaik, tetapi juga menjaga konsistensi antara rumusan masalah, research question, metode, implementasi, analisis, dan kesimpulan. Selain itu, saya memahami bahwa keterbatasan penelitian dan hasil yang belum optimal tetap memiliki nilai ilmiah apabila dijelaskan secara jujur dan didukung oleh analisis yang tepat.

**Yang akan selalu diterapkan:**
> Pada penelitian berikutnya, saya akan menyusun rancangan eksperimen yang realistis sesuai dengan sumber daya yang tersedia sejak awal, menjaga konsistensi antara proposal dan implementasi, serta mendokumentasikan seluruh proses penelitian secara sistematis agar hasil penelitian mudah direproduksi dan dipertanggungjawabkan secara ilmiah.
