# WS-11: Data Validation & Integrity

> **Bab 11 — Validasi Data & Integritas**

---

## Ringkasan Materi

### Data Trust Model

```
Raw Data → Data Cleaning → Consistency Check → Validation Process → Trusted Data
```

Data mentah belum bisa dipercaya. Harus melewati pipeline validasi sebelum siap untuk analisis statistik.

### Empat Pilar Data Quality

| Pilar | Deskripsi | Contoh Pelanggaran |
|-------|----------|-------------------|
| **Accuracy** | Nilai dalam range masuk akal | Akurasi = 1.5 (di luar [0,1]) |
| **Consistency** | Format seragam di semua run | Run 1: CSV, Run 2: JSON |
| **Completeness** | Tidak ada data hilang dari plan | 97 dari 100 run tercatat |
| **Validity** | Data sesuai desain eksperimen | Parameter baseline tercampur treatment |

### Proses Validasi Progresif

1. **Format validation** — Tipe file, header, kolom
2. **Range validation** — Nilai dalam batas logis
3. **Consistency validation** — Format seragam antar-run
4. **Logic validation** — Data cocok dengan desain eksperimen

Jika gagal di langkah awal → tidak perlu lanjut.

### Anomaly Detection — 3 Jenis

| Jenis | Deskripsi | Deteksi |
|-------|----------|---------|
| **Statistical outlier** | Nilai di luar distribusi normal | IQR: < Q1-1.5×IQR atau > Q3+1.5×IQR |
| **Contextual anomaly** | Normal absolut, abnormal dalam konteks | Run 1-10: ~91%, Run 11-20: ~88% |
| **Pattern anomaly** | Pola sistematis (bukan random) | Performa menurun berurutan |

**Prinsip:** Detect → Investigate → Document → Decide — **JANGAN langsung hapus.**

### Engineering vs Research Validation

| Aspek | Engineering | Research |
|-------|-----------|---------|
| Tujuan | Data sesuai spesifikasi bisnis | Data layak untuk analisis statistik |
| Missing data | Impute / set default | Investigasi penyebab → dokumentasi |
| Outlier | Bug → fix | Mungkin temuan → investigasi |
| Dokumentasi | Minimal (log error) | Komprehensif (anomali + keputusan) |

### Jebakan Kognitif

1. "Logging otomatis ≠ data benar" → bisa ada bug di logger
2. "Outlier = hapus" → bisa jadi temuan penting
3. "Dataset kecil tidak perlu validasi" → justru lebih rentan
4. "Mean normal = data benar" → [94, 95, 93, **44**, 94] → mean 84% terlihat wajar

---


## Template A.11 — Data Validation Checklist

```
DATA VALIDATION CHECKLIST

Completeness:

☑ Semua skenario tercakup

☑ Jumlah run sesuai rencana

☑ Tidak ada file output hilang

Missing: 0 dari 1 data eksperimen

Format Consistency:

☑ File CSV memiliki format dan struktur yang konsisten

☑ File model (.keras dan .h5) berhasil disimpan tanpa error

☑ Seluruh file output dapat dibuka dan digunakan kembali

Range & Logic:

☑ Nilai berada pada rentang yang masuk akal

☑ Tidak ada waktu negatif

☑ Metrik berada pada rentang 0–1

Anomali ditemukan:
Tidak ditemukan anomali yang memengaruhi hasil penelitian.

Validation Check:

☑ Hasil evaluasi sesuai dengan konfigurasi eksperimen

☑ Parameter sesuai proposal

☑ Output berhasil dihasilkan

Keputusan:

☑ Data siap dianalisis

☐ Perlu cleaning

☐ Perlu re-run (skenario: -)
```

---

## Latihan 1 — Completeness Check

Verifikasi apakah semua data yang direncanakan sudah terkumpul.

| Skenario | Run Direncanakan | Run Tercatat | Missing | Alasan |
|---|---|---|---|---|
| EfficientNet-B6 Transfer Learning | 1 | 1 | 0 | - |

**Total expected:** 1 | **Total actual:** 1 | **Missing:** 0

**Keputusan untuk data missing:**
> Seluruh data eksperimen berhasil diperoleh sesuai dengan rencana. Tidak terdapat data yang hilang sehingga seluruh hasil dapat digunakan pada proses analisis.

---

## Latihan 2 — Anomaly Investigation

Periksa data Anda untuk anomali. Gunakan metode IQR atau z-score.

**Dataset sampel (atau data Anda sendiri):**

| Metrik | Nilai |
|---|---|
| Accuracy | 0.6304 |
| Precision | 0.5876 |
| Recall | 0.6304 |
| F1-Score | 0.5845 |

**Deteksi outlier:**
- Q1 = Tidak dapat dihitung (jumlah observasi tidak mencukupi)
- Q3 = Tidak dapat dihitung
- IQR = Tidak dapat dihitung
- Outlier = Tidak dapat dievaluasi karena jumlah observasi tidak mencukupi untuk analisis statistik menggunakan metode IQR

**Investigasi (untuk setiap outlier):**

| Outlier | Nilai | Kemungkinan Penyebab | Keputusan |
|---|---|---|---|
| Tidak ada yang dapat dievaluasi | - | Jumlah observasi hanya satu | Tidak diperlukan tindakan |

---

## Latihan 3 — Validation Report

Buat laporan validasi ringkas untuk dataset eksperimen Anda.

**1. Completeness**

Seluruh data hasil eksperimen yang direncanakan berhasil dikumpulkan sehingga tidak terdapat data yang hilang.

**2. Format**

[✓] Konsisten

Seluruh file output penelitian berhasil dihasilkan sesuai formatnya masing-masing. File CSV memiliki struktur data yang konsisten, sedangkan file model (.keras dan .h5) berhasil disimpan tanpa error dan dapat digunakan kembali.

**3. Range Check**

Seluruh metrik evaluasi (Accuracy, Precision, Recall, dan F1-Score) berada pada rentang nilai yang valid yaitu 0–1.

Tidak ditemukan nilai yang berada di luar batas logis.

**4. Logic Check**

[✓] Parameter sesuai rencana eksperimen

Konfigurasi model, ukuran input, jumlah epoch, batch size, optimizer, serta random seed sesuai dengan konfigurasi yang telah ditetapkan sebelum eksperimen dilaksanakan.

**Kesimpulan**

[✓] Data siap dianalisis

Seluruh data hasil eksperimen telah memenuhi aspek completeness, consistency, validity, dan accuracy sehingga layak digunakan pada tahap analisis hasil penelitian. Validasi dilakukan terhadap hasil eksperimen yang tersedia sesuai dengan ruang lingkup penelitian.

---

## Refleksi

> Apa perbedaan antara "data yang benar" dan "data yang dipercaya"? Mengapa proses validasi formal diperlukan meskipun data dikumpulkan secara otomatis?

Data yang benar adalah data yang berhasil diperoleh dari proses eksperimen sesuai dengan hasil komputasi sistem. Namun, data yang dipercaya merupakan data yang telah melalui proses validasi sehingga dapat dipastikan lengkap, konsisten, berada pada rentang nilai yang logis, dan sesuai dengan rancangan penelitian. Meskipun data dikumpulkan secara otomatis menggunakan Google Colab, proses validasi tetap diperlukan untuk memastikan tidak terjadi kesalahan akibat konfigurasi eksperimen, kerusakan file, inkonsistensi format, maupun kesalahan selama proses pelatihan dan evaluasi model. Dengan demikian, hasil penelitian menjadi lebih andal dan dapat dipertanggungjawabkan secara ilmiah.
