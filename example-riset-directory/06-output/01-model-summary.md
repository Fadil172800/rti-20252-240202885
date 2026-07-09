# Model Summary

## Model

EfficientNet-B6 dengan pendekatan Transfer Learning.

---

## Arsitektur Model

Base Model

- EfficientNet-B6 (ImageNet Pretrained)
- include_top = False
- pooling = average

Classifier

- BatchNormalization
- Dropout (0.3)
- Dense (4 kelas, Softmax)

---

## Input Model

| Parameter | Nilai |
|-----------|-------|
| Input Size | 224 × 224 × 3 |
| Jumlah Kelas | 4 |
| Activation Output | Softmax |

---

## Konfigurasi Training

| Parameter | Nilai |
|-----------|-------|
| Optimizer | Adam |
| Learning Rate | 0.0001 |
| Loss Function | Sparse Categorical Crossentropy |
| Metric | Accuracy |

---

## Ringkasan Model

Model dibangun menggunakan EfficientNet-B6 sebagai feature extractor dengan bobot awal ImageNet (Transfer Learning). Lapisan klasifikasi terdiri atas BatchNormalization, Dropout, dan Dense Softmax untuk menghasilkan prediksi empat kelas penyakit daun padi.

Model ini kemudian dilatih menggunakan dataset Rice Leafs dengan pembagian data 80% training dan 20% validation.
