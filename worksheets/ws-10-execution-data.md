# WS-10: Experiment Execution & Data Collection

> **Bab 10 — Eksekusi Eksperimen & Pengumpulan Data**

---

## Ringkasan Materi

### Experiment Execution Pipeline

```
Design → Execution Plan → Controlled Execution → Data Collection → Data Logging → Dataset for Analysis
```

### Multiple Run = Non-Negotiable

Single run **tidak pernah cukup** untuk klaim ilmiah. Minimum 5-10 run per skenario dengan seed berbeda. Multiple run menghasilkan:
- Mean, std, confidence interval
- Distribusi hasil → uji statistik
- Variabilitas → error bar di grafik

### Execution Plan

Setiap eksperimen harus memiliki plan sebelum eksekusi:
- Daftar skenario
- Jumlah run per skenario
- Random seed per run (pre-determined!)
- Urutan eksekusi (randomisasi/counterbalancing)
- Pre-execution checklist

### Data Logging Komprehensif

Setiap run menghasilkan log terstruktur:
1. **Identitas** — Run ID, timestamp, skenario
2. **Konfigurasi** — Semua parameter, seed, code version
3. **Hasil** — Semua metrik, output detail
4. **Metadata** — Waktu eksekusi, resource usage, warning/error

Format: CSV/JSON/database — **bukan stdout yang di-copy-paste**.

### Engineering vs Research Execution

| Aspek | Engineering | Research |
|-------|-----------|---------|
| Run | Sekali (deploy) | Multiple (min 5-10, seed berbeda) |
| Logging | Error log, access log | Semua parameter, metrik, metadata |
| Anomali | Bug → fix → redeploy | Investigasi → dokumentasi → analisis |
| Urutan | Tidak penting | Bisa bias — perlu randomisasi |

### Anomali = Dokumentasi, Bukan Hapus

Run gagal/anomali tidak boleh dihapus tanpa dokumentasi. Bisa jadi:
- **Bug** → fix & re-run (dokumentasikan!)
- **Batas kemampuan metode** → DNF = temuan
- **Data yang bias** jika hanya simpan run "berhasil"

### Jebakan Kognitif

1. "Satu angka cukup" → tanpa distribusi, tidak bisa diuji
2. "Seed tidak penting" → bahkan algoritma deterministik bisa dipengaruhi library stokastik
3. "Run gagal langsung hapus" → kehilangan temuan potensial
4. "Semua run harus hari ini" → thermal throttling, fatigue

---


## Template A.10 — Execution Plan & Data Log

```
EXECUTION PLAN

| Run # | Skenario                          | Seed | Parameter                    | Status    | Waktu     | Output File                                                                               |
| ----- | --------------------------------- | ---- | ---------------------------- | --------- | --------- | ----------------------------------------------------------------------------------------- |
| 1     | EfficientNet-B6 Transfer Learning | 42   | Input=224, Epoch=25, Batch=2 | Completed | ±45 menit | `.keras`, `.h5`, `training_history.csv`, `evaluation_metrics.csv`, `research_summary.csv` |

Jumlah skenario : 1

Jumlah run yang dilaksanakan : 1

Catatan:
Penelitian ini menggunakan satu kali proses pelatihan (single run) sesuai rancangan eksperimen pada proposal menggunakan metode single split (80% data latih dan 20% data validasi). Pengujian multiple run tidak dilakukan karena berada di luar ruang lingkup penelitian ini.

DATA LOG (per run)

Run ID    : run-001

Timestamp : 28 Juni 2026

Skenario  : EfficientNet-B6 Transfer Learning

Input     : Dataset Rice Leafs (3.355 citra)

Output    :
- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix
- Classification Report
- training_history.csv
- evaluation_metrics.csv
- research_summary.csv
- RiceLeaf_EfficientNetB6.keras
- RiceLeaf_EfficientNetB6.h5

Anomali   : Tidak ditemukan anomali kritis selama proses pelatihan. EarlyStopping menghentikan pelatihan sesuai konfigurasi callback.

Catatan   : Model berhasil dilatih menggunakan Google Colab Free.
```

---

## Latihan 1 — Execution Plan

Susun execution plan untuk eksperimen Anda. Tentukan skenario, jumlah run, dan seed sebelum eksekusi.

| Run # | Skenario | Seed | Parameter Kunci | Status |
|---|---|---|---|---|
| 1 | EfficientNet-B6 Transfer Learning | 42 | Input=224, Epoch=25, Batch=2 | Completed |

**Jumlah skenario:** 1

**Jumlah run yang dilaksanakan:** 1

**Catatan:**

Penelitian menggunakan satu kali pelatihan sesuai rancangan penelitian pada proposal menggunakan metode single split (80% data latih dan 20% data validasi). Pengujian multiple run tidak dilakukan karena berada di luar ruang lingkup penelitian ini.

---

## Latihan 2 — Data Log Terstruktur

Desain format data log untuk eksperimen Anda. Tentukan field apa saja yang akan dicatat.

**Identitas:**

| Field | Contoh |
|---|---|
| Run ID | run-001 |
| Timestamp | 28 Juni 2026 |
| Skenario | EfficientNet-B6 Transfer Learning |

**Konfigurasi:**

| Field | Contoh |
|---|---|
| Seed | 42 |
| Model | EfficientNet-B6 |
| Input Size | 224 × 224 |
| Batch Size | 2 |
| Epoch | 25 |
| Optimizer | Adam |
| Validation | Single Split (80:20) |

**Hasil:**

| Metrik | Tipe Data | Range Valid |
|---|---|---|
| Accuracy | Float | 0.0 – 1.0 |
| Precision | Float | 0.0 – 1.0 |
| Recall | Float | 0.0 – 1.0 |
| F1-Score | Float | 0.0 – 1.0 |
| Loss | Float | ≥ 0 |
| Training Time | Float | > 0 |

**Format output:** [v] CSV / [ ] JSON / [ ] Database / [ ] Lainnya: ____

**Output yang dihasilkan:**

- training_history.csv
- evaluation_metrics.csv
- research_summary.csv
- RiceLeaf_EfficientNetB6.keras
- RiceLeaf_EfficientNetB6.h5

---

## Latihan 3 — Anomaly Protocol

Rencanakan bagaimana menangani anomali. Untuk setiap jenis, tentukan langkah yang diambil.

| Jenis Anomali | Contoh | Tindakan |
|---|---|---|
| Run gagal (crash) | Google Colab kehabisan RAM atau sesi terputus | Jalankan ulang notebook, bersihkan cache, dan ulangi pelatihan |
| Hasil ekstrem | Accuracy jauh lebih rendah dari hasil sebelumnya | Periksa dataset, parameter pelatihan, dan proses preprocessing |
| Waktu eksekusi anomali | Training jauh lebih lama akibat perubahan GPU | Catat jenis GPU yang digunakan dan waktu pelatihan |
| Inkonsistensi hasil | Hasil evaluasi tidak sesuai dengan konfigurasi yang diharapkan | Periksa kembali konfigurasi eksperimen, dataset, preprocessing, dan ulangi pelatihan bila diperlukan |

**Prinsip:** Detect → Investigate → Document → Decide

---

## Refleksi

> Pernahkah Anda melaporkan hasil riset/tugas dari single run? Apa risikonya? Bagaimana multiple run mengubah kepercayaan terhadap hasil?

**Pengalaman sebelumnya:**

Pada penelitian ini, hasil eksperimen diperoleh dari satu kali proses pelatihan (single run) menggunakan konfigurasi yang telah ditentukan pada proposal. Pendekatan ini memberikan gambaran awal mengenai performa model, namun hasilnya masih dapat dipengaruhi oleh faktor acak seperti inisialisasi bobot, pembagian data, maupun kondisi lingkungan komputasi. Oleh karena itu, hasil penelitian ini diinterpretasikan sesuai ruang lingkup eksperimen yang telah dirancang.

**Yang akan dilakukan berbeda:**

Pada penelitian selanjutnya, saya akan melakukan beberapa kali pengujian (multiple run) menggunakan konfigurasi yang sama sehingga konsistensi hasil dapat dievaluasi dengan lebih baik. Pendekatan ini meningkatkan kepercayaan terhadap hasil penelitian karena memungkinkan identifikasi variasi performa model dan mengurangi pengaruh faktor acak selama proses pelatihan.
