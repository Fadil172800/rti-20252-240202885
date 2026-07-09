# Model Summary

File

```
01-model-summary.png
```

---

# Model

EfficientNet-B6 dengan pendekatan Transfer Learning.

---

# Arsitektur Model

## Base Model

- EfficientNet-B6 (ImageNet Pretrained)
- include_top = False
- pooling = average

## Classifier

- BatchNormalization
- Dropout (0.3)
- Dense (4 kelas, Softmax)

---

# Input Model

| Parameter | Nilai |
|-----------|-------|
| Input Size | 224 × 224 × 3 |
| Jumlah Kelas | 4 |
| Activation Output | Softmax |

---

# Konfigurasi Training

| Parameter | Nilai |
|-----------|-------|
| Optimizer | Adam |
| Learning Rate | 0.0001 |
| Loss Function | Sparse Categorical Crossentropy |
| Metric | Accuracy |

---

# Ringkasan Parameter Model

Berdasarkan hasil `model.summary()` diperoleh informasi sebagai berikut.

| Parameter | Nilai |
|-----------|-------:|
| Total Parameters | 40.978.579 |
| Trainable Parameters | 13.828 |
| Non-Trainable Parameters | 40.964.751 |

---

# Ringkasan Model

Model dibangun menggunakan EfficientNet-B6 sebagai **feature extractor** dengan bobot awal ImageNet menggunakan pendekatan **Transfer Learning**. Lapisan klasifikasi terdiri atas **BatchNormalization**, **Dropout (0.3)**, dan **Dense Softmax** dengan empat neuron yang merepresentasikan kelas BrownSpot, Healthy, Hispa, dan LeafBlast.

Sebagian besar parameter model bersifat **non-trainable** karena bobot EfficientNet-B6 tidak dilatih ulang, sedangkan parameter pada lapisan klasifikasi menjadi **trainable** untuk menyesuaikan model dengan karakteristik dataset Rice Leafs.

Model kemudian dilatih menggunakan dataset Rice Leafs dengan pembagian **80% data training** dan **20% data validation** menggunakan TensorFlow.
