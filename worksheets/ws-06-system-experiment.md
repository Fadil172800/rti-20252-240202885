# WS-06: System-Experiment Mapping

> **Bab 6 — System Design sebagai Experimental Artifact**

---

## Ringkasan Materi

### Sistem = Instrumen Pengujian, Bukan Produk

Seorang engineer bertanya "apakah sistem bekerja?" — seorang peneliti bertanya "apa yang bisa dibuktikan sistem ini?" Sistem dalam riset adalah **artifact** — objek yang sengaja dibuat untuk menguji klaim spesifik.

### System as Experiment Model

```
RQ → Variable → System Component → Experimental Setup → Output
```

Setiap komponen sistem harus bisa ditelusuri ke variabel riset (top-down), dan setiap pengukuran harus menjawab RQ (bottom-up).

### Mapping Variabel ke Komponen

| Tipe Variabel | Peran di Sistem | Contoh |
|---------------|----------------|--------|
| **IV** (Independent) | Modul yang bisa di-toggle/swap | Algoritma A vs B |
| **DV** (Dependent) | Modul pengukuran | Logger, metrics collector |
| **CV** (Control) | Config yang dikunci | Dataset, parameter tetap |

Jika variabel tidak bisa di-map ke komponen apapun → arsitektur perlu didesain ulang.

### 4 Prinsip Desain Eksperimental

| Prinsip | Pertanyaan Kunci |
|---------|-----------------|
| **Traceability** | Komponen ini melayani variabel yang mana? |
| **Modularity** | Bisakah IV diubah tanpa memengaruhi yang lain? |
| **Controllability** | Apakah CV dieksternalisasi ke config file? |
| **Measurability** | Apakah sistem otomatis menghasilkan data yang dibutuhkan? |

### Variable Isolation melalui Arsitektur

- **Modular architecture** — Pisahkan berdasarkan variabel
- **Configuration-driven** — Ubah config (YAML/JSON), bukan code
- **Feature toggles** — On/off flag untuk ablation study

  Contoh config YAML dengan feature toggles:
  ```yaml
  model:
    type: cnn          # IV: ganti "rf" untuk kondisi baseline
  features:
    use_temporal: true  # toggle komponen temporal
    use_normalization: true  # toggle preprocessing
  experiment:
    seed: 42
    runs: 5
  ```
  Dengan pendekatan ini, berbeda kondisi eksperimen = berbeda satu baris config, **tanpa mengubah kode**.

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Tujuan sistem | Memenuhi kebutuhan user | Menguji hipotesis, menghasilkan bukti |
| Arsitektur | Optimasi performa & skalabilitas | Optimasi isolasi variabel & reprodusibilitas |
| Konfigurasi | Sering hardcoded | Dieksternalisasi ke config file |
| Fitur tambahan | Menambah nilai user | Menambah noise jika tidak terkait RQ |

### Istilah Penting

- **Artifact** — Objek yang sengaja dibuat untuk memecahkan masalah atau menguji proposisi
- **Traceability** — Kemampuan menelusuri hubungan RQ → variabel → komponen → output
- **Variable Isolation** — Mengubah hanya satu variabel sambil menahan yang lain konstan
- **Ablation Study** — Menguji kontribusi tiap komponen dengan melepasnya satu per satu
- **Configuration-driven Execution** — Semua parameter di config file, bukan hardcoded

---

## Template A.6 — Mapping RQ ke Arsitektur Sistem

```
**SYSTEM-EXPERIMENT MAPPING**

**Research Question:**  
Apakah metode EfficientNet-B6 menghasilkan accuracy dan F1-Score yang lebih tinggi dibandingkan CNN standar pada klasifikasi penyakit daun padi?

**Variable → Component Mapping:**

| Variabel | Tipe | Komponen Sistem | Cara Manipulasi/Pengukuran |
|----------|------|-----------------|---------------------------|
| **Jenis Model Deep Learning** | IV | Modul Training Model | Mengganti model CNN standar menjadi EfficientNet-B6 pada script training |
| **Accuracy & F1-Score** | DV | Modul Evaluasi Model | Menggunakan confusion matrix untuk menghitung accuracy dan F1-Score |
| **Jumlah Epoch** | CV | Parameter Training | Menentukan jumlah epoch tetap (25 dan 50) |
| **Ukuran Input Citra** | CV | Modul Preprocessing | Resize citra menjadi ukuran 224 dan 528 pixel |
| **Dataset Daun Padi** | CV | Dataset Loader | Menggunakan dataset tetap sebanyak 3355 citra |

**4 Prinsip Desain:**

* [x] **Traceability** — Setiap komponen berhubungan langsung dengan variabel penelitian.
* [x] **Variable Isolation** — Pergantian model dapat dilakukan tanpa mengubah dataset dan preprocessing.
* [x] **Measurement Integration** — Accuracy dan F1-Score dihitung otomatis setelah training selesai.
* [x] **Reproducibility** — Eksperimen dapat diulang dengan parameter yang sama.

**Experimental Setup:**

* **Input data:** 3355 citra daun padi dengan 4 kelas penyakit.
* **Parameter:** Epoch 25 dan 50, input size 224 dan 528.
* **Output format:** Nilai accuracy, precision, recall, F1-Score, dan confusion matrix.
```

---

## Latihan 1 — Variable-to-Component Mapping

Gunakan RQ dan variabel dari WS-05. Petakan ke komponen sistem.

**RQ:**Apakah metode EfficientNet-B6 menghasilkan accuracy dan F1-Score yang lebih tinggi dibandingkan CNN standar pada klasifikasi penyakit daun padi?

| Variabel         | Tipe | Komponen Sistem       | Cara Manipulasi / Pengukuran                       |
| ---------------- | ---- | --------------------- | -------------------------------------------------- |
| **Jenis Model**  | IV   | Script Training Model | Mengubah model dari CNN standar ke EfficientNet-B6 |
| **Accuracy**     | DV   | Modul Evaluasi        | Menghitung accuracy dari confusion matrix          |
| **F1-Score**     | DV   | Modul Evaluasi        | Menghitung F1-Score otomatis                       |
| **Jumlah Epoch** | CV   | Parameter Training    | Menentukan jumlah epoch tetap                      |


**Apakah semua variabel bisa di-map?** [X] Ya / [ ] Tidak

---

## Latihan 2 — 4 Prinsip Desain

Evaluasi desain sistem terhadap 4 prinsip.

| Prinsip             | Status      | Bukti / Penjelasan                                                                    |
| ------------------- | ----------- | ------------------------------------------------------------------------------------- |
| **Traceability**    | ✅ Terpenuhi | Semua variabel memiliki komponen sistem masing-masing                                 |
| **Modularity**      | ✅ Terpenuhi | Model dapat diganti tanpa mengubah preprocessing dan dataset                          |
| **Controllability** | ⚠️ Sebagian | Parameter training dapat dikontrol, tetapi performa hardware masih mempengaruhi hasil |
| **Measurability**   | ✅ Terpenuhi | Sistem otomatis menghasilkan accuracy dan F1-Score                                    |


**Prinsip mana yang paling sulit dipenuhi?** Controllability
**Strategi untuk mengatasinya:**
> Menggunakan hardware dan environment yang sama selama eksperimen agar hasil pengujian tetap konsisten.

---

## Latihan 3 — Ablation Study Planning

Jika sistem memiliki 3 komponen utama, rencanakan ablation study.

> **Panduan jumlah kondisi:** Untuk 3 komponen (A, B, C), kondisi minimal yang direkomendasikan:
> Full + (-A) + (-B) + (-C) = **4 kondisi dasar**. Jika waktu memungkinkan, tambahkan kombinasi ganda: (-A,-B), (-A,-C), (-B,-C) = **7 kondisi**. Sesuaikan dengan *computational cost* dan tenggat waktu penelitian.

| Kondisi  | Komponen A (Jenis Model) | Komponen B (Ukuran Input) | Komponen C (Jumlah Epoch) | Hasil yang Diharapkan                                     |
| -------- | ------------------------ | ------------------------- | ------------------------- | --------------------------------------------------------- |
| **Full** | ✅ EfficientNet-B6        | ✅ 224 Pixel               | ✅ 50 Epoch                | Hasil akurasi terbaik                                     |
| **– A**  | ❌ CNN Standar            | ✅ 224 Pixel               | ✅ 50 Epoch                | Akurasi lebih rendah dibanding EfficientNet-B6            |
| **– B**  | ✅ EfficientNet-B6        | ❌ 528 Pixel               | ✅ 50 Epoch                | Performa dapat berubah karena ukuran input berbeda        |
| **– C**  | ✅ EfficientNet-B6        | ✅ 224 Pixel               | ❌ 25 Epoch                | Akurasi kemungkinan menurun karena training lebih singkat |

**Komponen mana yang diprediksi paling berkontribusi?** Komponen A (Jenis Model Deep Learning)
**Mengapa?**
> Karena arsitektur EfficientNet-B6 memiliki kemampuan ekstraksi fitur yang lebih baik dibanding CNN standar sehingga dapat meningkatkan performa klasifikasi citra daun padi.
---

## Refleksi

> Apa risiko jika sistem dibangun seperti produk (monolitik, fitur lengkap) lalu baru dilakukan eksperimen? Mengapa arsitektur modular penting untuk riset?
**Jawaban:**
> Jika sistem dibuat terlalu kompleks seperti produk nyata, maka akan muncul banyak faktor lain yang mempengaruhi hasil eksperimen sehingga sulit mengetahui penyebab utama perubahan performa. Arsitektur modular penting agar peneliti dapat mengubah satu variabel tanpa mempengaruhi bagian lain sehingga hasil eksperimen lebih valid dan mudah dianalisis.
