# WS-03: Literature Mapping & Gap

> **Bab 3 — Literature Review, Research Gap & Baseline**

---

## Ringkasan Materi

### Literature Review = Positioning, Bukan Ringkasan

Literature review bukan merangkum paper satu per satu. Pendekatan yang benar adalah **concept-centric** — organisasi berdasarkan tema, metode, atau variabel. Tujuan: menemukan **pola, kontradiksi, dan gap**.

### Empat Jenis Research Gap

| Jenis Gap | Deskripsi | Contoh |
|-----------|----------|--------|
| **Performance Gap** | Performa belum memadai | Akurasi deteksi hanya 78% pada kasus tertentu |
| **Method Gap** | Pendekatan belum diterapkan | Belum ada yang pakai transformer untuk task ini |
| **Data Gap** | Dataset terbatas/tidak representatif | Semua studi pakai dataset sintetis |
| **Context Gap** | Belum diuji pada konteks berbeda | Belum ada evaluasi di negara berkembang |

Gap terkuat = kombinasi 2+ jenis.

### Systematic Search Strategy

1. **Database**: IEEE Xplore, ACM DL, Scopus, Google Scholar
2. **Boolean query** yang terdokumentasi eksplisit
3. **Snowballing**: backward (telusuri referensi) + forward (cari yang mengutip)
4. Klaim "belum ada penelitian" harus didukung **bukti pencarian**

### Baseline Selection — 3 Kriteria

| Kriteria | Pertanyaan |
|----------|-----------|
| **Relevan** | Apakah menyelesaikan masalah yang sama? |
| **Representatif** | Apakah mewakili common practice? |
| **State-of-the-Art** | Apakah terbaru/terbaik? |

Membandingkan deep learning 2024 dengan decision tree sederhana tanpa justifikasi = **straw man comparison** (perbandingan tidak jujur).

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Tujuan baca literatur | Mencari solusi yang sudah ada | Memahami apa yang belum terjawab |
| Cara membaca paper | Tutorial, how-to | Metode, limitasi, gap |
| Baseline | Framework terpopuler | State-of-the-art yang rigorous |
| Dokumentasi pencarian | Tidak diperlukan | Wajib (reproducible) |

### Istilah Penting

- **Concept-centric** — Organisasi literatur berdasarkan konsep/metode, bukan per penulis
- **Snowballing** — Backward (telusuri referensi) + Forward (cari yang mengutip paper kunci)
- **Research Position** — Pernyataan eksplisit posisi riset terhadap studi sebelumnya
- **Straw man comparison** — Memilih baseline lemah agar metode sendiri terlihat lebih baik

---

## Template A.3 — Literature Mapping & Gap Identification

```
LITERATURE MAPPING

Topik      : Klasifikasi Penyakit Daun Padi Menggunakan Deep Learning EfficientNet-B6
Database   : Google Scholar, IEEE Xplore, ResearchGate
Query      : ("rice leaf disease" OR "plant disease classification") AND ("CNN" OR "EfficientNet" OR "deep learning")
Tahun      : 2020–2024
Hasil awal : Beberapa artikel diperoleh melalui proses pencarian, kemudian dilakukan proses screening sehingga diperoleh lima artikel yang relevan.

Literature Matrix (Concept-Centric)

| Study | Tahun | Method | Dataset | Result | Limitation |
|-------|-------|--------|---------|--------|------------|
| Amanda Caecilia Milano et al. | 2024 | EfficientNet-B6 | Rice Leafs (3.355 citra) | EfficientNet-B6 mampu melakukan klasifikasi penyakit daun padi dengan performa yang cukup baik | Akurasi masih belum optimal dan beberapa kelas masih sering salah diklasifikasikan |
| Singh et al. | 2023 | EfficientNet-B6 | Bean Leaf Dataset | EfficientNet-B6 memiliki performa lebih baik dibanding beberapa CNN lainnya | Fokus penelitian bukan pada daun padi |
| Yuliany et al. | 2022 | CNN | Dataset hama tanaman padi | CNN mampu melakukan klasifikasi hama tanaman | Belum menggunakan arsitektur CNN modern |
| Agustiani et al. | 2022 | Random Forest + Color Histogram | Dataset daun padi | Mampu melakukan klasifikasi penyakit daun padi | Performa lebih rendah dibanding Deep Learning |
| Atila et al. | 2021 | EfficientNet | PlantVillage Dataset | EfficientNet memiliki akurasi tinggi pada klasifikasi penyakit tanaman | Belum diterapkan secara khusus pada penyakit daun padi di Indonesia |

Pola yang ditemukan

• Metode yang paling banyak digunakan adalah CNN dan EfficientNet.
• Sebagian besar penelitian menggunakan dataset citra daun tanaman.
• Keterbatasan yang sering muncul adalah performa model yang belum optimal pada kelas tertentu serta pengujian yang masih terbatas pada dataset tertentu.

---

Gap 1 : Performance Gap

Deskripsi
Performa klasifikasi penyakit daun padi masih memiliki ruang untuk ditingkatkan karena beberapa kelas penyakit masih sulit dibedakan.

Bukti
Artikel Amanda Caecilia Milano et al. (2024) menunjukkan bahwa beberapa kelas penyakit masih sering mengalami kesalahan klasifikasi meskipun menggunakan EfficientNet-B6.

Signifikansi
Peningkatan performa klasifikasi akan membantu proses identifikasi penyakit menjadi lebih akurat sehingga dapat mendukung pengambilan keputusan dalam penanganan penyakit tanaman.

------------------------------------------------------------

Gap 2 : Method Gap

Deskripsi
Masih terbatas penelitian yang mengimplementasikan dan mengevaluasi EfficientNet-B6 menggunakan pendekatan Transfer Learning pada dataset Rice Leafs sebagai dasar pengembangan penelitian lanjutan.

Bukti
Sebagian besar penelitian berfokus pada perbandingan berbagai arsitektur CNN, sedangkan implementasi EfficientNet-B6 pada konteks penelitian lanjutan masih dapat dieksplorasi.

Signifikansi
Penelitian lanjutan diperlukan untuk mengetahui bagaimana implementasi EfficientNet-B6 pada konfigurasi yang berbeda sehingga dapat menjadi referensi pengembangan sistem klasifikasi penyakit daun padi.

------------------------------------------------------------

Baseline Selection

| Baseline | Relevansi | Representatif | Source |
|----------|-----------|---------------|--------|
| CNN Standar | Banyak digunakan pada penelitian klasifikasi citra tanaman | Metode pembanding yang umum digunakan | Yuliany et al. (2022) |
| EfficientNet-B6 | Digunakan pada penelitian klasifikasi penyakit daun padi | Menjadi artikel acuan penelitian | Amanda Caecilia Milano et al. (2024) |
```

---

---

## Latihan 1 — Concept-Centric Literature Table

Topik riset: Klasifikasi Penyakit Daun Padi Menggunakan Deep Learning EfficientNet-B6.
Query pencarian: ("rice leaf disease" OR "plant disease classification")
AND
("CNN" OR "EfficientNet")
Database

Google Scholar, IEEE Xplore

| No | Study                         | Tahun | Method          | Dataset                   | Result                                             | Limitation                                               |
| -- | ----------------------------- | ----- | --------------- | ------------------------- | -------------------------------------------------- | -------------------------------------------------------- |
| 1  | Amanda Caecilia Milano et al. | 2024  | EfficientNet-B6 | Rice Leafs                | Performa klasifikasi penyakit daun padi cukup baik | Masih terdapat kesalahan klasifikasi pada beberapa kelas |
| 2  | Singh et al.                  | 2023  | EfficientNet-B6 | Bean Leaf Dataset         | EfficientNet-B6 memiliki performa tinggi           | Dataset bukan daun padi                                  |
| 3  | Yuliany et al.                | 2022  | CNN             | Dataset hama tanaman padi | CNN efektif untuk klasifikasi                      | Belum menggunakan CNN modern                             |
| 4  | Agustiani et al.              | 2022  | Random Forest   | Dataset daun padi         | Dapat melakukan klasifikasi penyakit               | Akurasi lebih rendah dibanding Deep Learning             |
| 5  | Atila et al.                  | 2021  | EfficientNet    | PlantVillage Dataset      | Performa EfficientNet tinggi                       | Belum diterapkan pada konteks Indonesia                  |


Pola yang terlihat — Metode dominan:
CNN dan EfficientNet merupakan metode yang paling banyak digunakan pada penelitian klasifikasi penyakit tanaman.

Limitasi yang berulang:
Sebagian besar penelitian masih memiliki keterbatasan pada performa klasifikasi kelas tertentu dan kemampuan generalisasi model terhadap dataset lain.
---

## Latihan 2 — Gap Identification

| Jenis Gap       | Ditemukan | Gap Statement                                                                                                               |
| --------------- | --------- | --------------------------------------------------------------------------------------------------------------------------- |
| Performance Gap | ☑ Ya      | Performa klasifikasi penyakit daun padi masih dapat ditingkatkan karena beberapa kelas penyakit masih sulit dibedakan.      |
| Method Gap      | ☑ Ya      | Implementasi EfficientNet-B6 menggunakan pendekatan Transfer Learning masih dapat dikembangkan sebagai penelitian lanjutan. |
| Data Gap        | ☑ Ya      | Sebagian besar penelitian masih menggunakan satu dataset sehingga kemampuan generalisasi model belum banyak dievaluasi.     |
| Context Gap     | ☑ Ya      | Implementasi pada kondisi pertanian Indonesia masih relatif terbatas.                                                       |


Gap utama yang dipilih: Performance Gap dan Method Gap.

Mengapa gap ini penting?

Karena peningkatan performa klasifikasi akan membantu menghasilkan sistem identifikasi penyakit daun padi yang lebih akurat. Selain itu, implementasi EfficientNet-B6 sebagai penelitian lanjutan dapat memberikan referensi baru bagi pengembangan sistem klasifikasi penyakit tanaman.
---

## Latihan 3 — Baseline Selection

| No | Baseline        | Mengapa Relevan                                            | Mengapa Representatif                                | Apakah SOTA? | Sumber                               |
| -- | --------------- | ---------------------------------------------------------- | ---------------------------------------------------- | ------------ | ------------------------------------ |
| 1  | CNN Standar     | Banyak digunakan pada penelitian klasifikasi citra tanaman | Menjadi metode pembanding yang umum                  | Tidak        | Yuliany et al. (2022)                |
| 2  | EfficientNet-B6 | Digunakan pada artikel acuan penelitian                    | Merupakan model CNN modern dengan performa yang baik | Ya           | Amanda Caecilia Milano et al. (2024) |


---


## Refleksi

**Apakah pemilihan baseline ini bisa dianggap straw man?** [ ] Ya / [X] Tidak
>Justifikasi: Baseline dipilih berdasarkan metode yang benar-benar digunakan pada penelitian sebelumnya sehingga perbandingan dilakukan secara adil dan memiliki dasar ilmiah.

**Jawaban:**
> Research gap bukan sekadar menyatakan bahwa belum ada penelitian sebelumnya, tetapi harus dibuktikan melalui kajian literatur. Dengan membandingkan beberapa penelitian, dapat diketahui keterbatasan yang masih muncul, seperti performa klasifikasi yang belum optimal, keterbatasan metode, maupun penggunaan dataset yang masih terbatas. Research gap tersebut kemudian menjadi dasar dalam penyusunan proposal penelitian yang akan diimplementasikan pada tahap selanjutnya.
