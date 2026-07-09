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
SYSTEM-EXPERIMENT MAPPING

Research Question

Bagaimana performa model EfficientNet-B6 dalam mengklasifikasikan penyakit daun padi berdasarkan metrik Accuracy, Precision, Recall, F1-Score, dan AUC?

Variable → Component Mapping

| Variabel | Tipe | Komponen Sistem | Cara Manipulasi/Pengukuran |
|----------|------|-----------------|----------------------------|
| Model EfficientNet-B6 | IV | Modul Training Model | Menggunakan arsitektur EfficientNet-B6 sebagai model klasifikasi |
| Accuracy | DV | Modul Evaluasi | Dihitung dari confusion matrix |
| Precision | DV | Modul Evaluasi | Dihitung menggunakan classification report |
| Recall | DV | Modul Evaluasi | Dihitung menggunakan classification report |
| F1-Score | DV | Modul Evaluasi | Dihitung menggunakan classification report |
| AUC | DV | Modul Evaluasi | Dihitung dari ROC Curve |
| Ukuran Input Citra | CV | Modul Preprocessing | Resize citra menjadi 224×224 dan 528×528 piksel |
| Jumlah Epoch | CV | Parameter Training | Menggunakan 25 dan 50 epoch |
| Dataset Rice Leafs | CV | Dataset Loader | Dataset tetap sebanyak 3.355 citra |

4 Prinsip Desain

[x] Traceability — Seluruh variabel penelitian dipetakan ke komponen sistem.

[x] Variable Isolation — Variasi ukuran input dan epoch diuji tanpa mengubah dataset.

[x] Measurement Integration — Seluruh metrik dihitung secara otomatis setelah proses pengujian.

[x] Reproducibility — Eksperimen dapat diulang menggunakan konfigurasi yang sama.

Experimental Setup

Input:
Dataset Rice Leafs sebanyak 3.355 citra dengan empat kelas (Healthy, Leaf Blast, Hispa, dan Brown Spot).

Parameter:
- Model : EfficientNet-B6
- Input Size : 224×224 dan 528×528
- Epoch : 25 dan 50

Output:
Accuracy, Precision, Recall, F1-Score, AUC, Confusion Matrix, dan Classification Report.
```

---

## Latihan 1 — Variable-to-Component Mapping

Gunakan RQ dan variabel dari WS-05. Petakan ke komponen sistem.

**RQ:**Bagaimana performa model EfficientNet-B6 dalam mengklasifikasikan penyakit daun padi berdasarkan Accuracy, Precision, Recall, F1-Score, dan AUC?

| Variabel              | Tipe | Komponen Sistem      | Cara Manipulasi / Pengukuran                          |
| --------------------- | ---- | -------------------- | ----------------------------------------------------- |
| Model EfficientNet-B6 | IV   | Modul Training Model | Menggunakan EfficientNet-B6 sebagai model klasifikasi |
| Accuracy              | DV   | Modul Evaluasi       | Dihitung dari confusion matrix                        |
| Precision             | DV   | Modul Evaluasi       | Dihitung menggunakan classification report            |
| Recall                | DV   | Modul Evaluasi       | Dihitung menggunakan classification report            |
| F1-Score              | DV   | Modul Evaluasi       | Dihitung menggunakan classification report            |
| AUC                   | DV   | Modul Evaluasi       | Dihitung menggunakan ROC Curve                        |
| Ukuran Input Citra    | CV   | Modul Preprocessing  | Resize menjadi 224×224 dan 528×528 piksel             |
| Jumlah Epoch          | CV   | Parameter Training   | Menggunakan 25 dan 50 epoch                           |


**Apakah semua variabel bisa di-map?** [X] Ya / [ ] Tidak

---

## Latihan 2 — 4 Prinsip Desain

Evaluasi desain sistem terhadap 4 prinsip.

| Prinsip             | Status      | Bukti / Penjelasan                                                           |
| ------------------- | ----------- | ---------------------------------------------------------------------------- |
| **Traceability**    | ✅ Terpenuhi | Semua variabel penelitian memiliki komponen sistem yang sesuai.              |
| **Modularity**      | ✅ Terpenuhi | Modul preprocessing, training, dan evaluasi dipisahkan sehingga mudah diuji. |
| **Controllability** | ✅ Terpenuhi | Ukuran input dan jumlah epoch dikontrol selama eksperimen.                   |
| **Measurability**   | ✅ Terpenuhi | Accuracy, Precision, Recall, F1-Score, dan AUC dihitung secara otomatis.     |


**Prinsip mana yang paling sulit dipenuhi?** Controllability
**Strategi untuk mengatasinya:**
> Menjaga dataset, konfigurasi perangkat lunak, dan parameter eksperimen tetap sama pada setiap skenario sehingga hasil pengujian dapat dibandingkan secara objektif.

---

## Latihan 3 — Ablation Study Planning

Jika sistem memiliki 3 komponen utama, rencanakan ablation study.

> **Panduan jumlah kondisi:** Untuk 3 komponen (A, B, C), kondisi minimal yang direkomendasikan:
> Full + (-A) + (-B) + (-C) = 4 kondisi dasar. Jika waktu memungkinkan, tambahkan kombinasi ganda: (-A,-B), (-A,-C), (-B,-C) = 7 kondisi. Sesuaikan dengan computational cost dan tenggat waktu penelitian.

| Kondisi  | Komponen A (Model)      | Komponen B (Ukuran Input) | Komponen C (Jumlah Epoch) | Hasil yang Diharapkan                                                           |
| -------- | ----------------------- | ------------------------- | ------------------------- | ------------------------------------------------------------------------------- |
| **Full** | ✅ EfficientNet-B6       | ✅ 224×224                 | ✅ 50 Epoch                | Memberikan performa terbaik sesuai hasil penelitian.                            |
| **– A**  | ❌ Tanpa EfficientNet-B6 | ✅ 224×224                 | ✅ 50 Epoch                | Eksperimen tidak dapat dijalankan karena model merupakan komponen utama sistem. |
| **– B**  | ✅ EfficientNet-B6       | ❌ 528×528                 | ✅ 50 Epoch                | Menguji pengaruh perubahan ukuran input terhadap performa model.                |
| **– C**  | ✅ EfficientNet-B6       | ✅ 224×224                 | ❌ 25 Epoch                | Menguji pengaruh jumlah epoch terhadap hasil klasifikasi.                       |


**Komponen mana yang diprediksi paling berkontribusi?** Komponen A (Model EfficientNet-B6).
**Mengapa?**
> Karena EfficientNet-B6 merupakan komponen utama yang melakukan proses ekstraksi fitur dan klasifikasi citra. Tanpa model tersebut, proses klasifikasi tidak dapat dilakukan. Sementara ukuran input dan jumlah epoch merupakan parameter pelatihan yang memengaruhi performa model.
---

## Refleksi

> Apa risiko jika sistem dibangun seperti produk (monolitik, fitur lengkap) lalu baru dilakukan eksperimen? Mengapa arsitektur modular penting untuk riset?
**Jawaban:**
> Jika sistem dibangun seperti produk yang kompleks sebelum eksperimen dilakukan, maka akan muncul banyak faktor yang dapat memengaruhi hasil penelitian sehingga sulit mengetahui penyebab utama perubahan performa model. Arsitektur modular memudahkan peneliti mengontrol setiap komponen eksperimen, sehingga hubungan antara variabel penelitian dan hasil yang diperoleh menjadi lebih jelas, valid, serta mudah direproduksi.
