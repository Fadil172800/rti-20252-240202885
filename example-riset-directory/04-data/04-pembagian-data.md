# Pembagian Dataset

Dataset Rice Leafs terdiri dari 3.355 citra yang dibagi menjadi empat kelas, yaitu BrownSpot, Healthy, Hispa, dan LeafBlast.

Pada penelitian ini digunakan metode hold-out validation dengan pembagian:

- Data Training : 80%
- Data Validation : 20%

Pembagian dilakukan menggunakan TensorFlow sebelum proses pelatihan model EfficientNet-B6 sehingga data validasi tidak ikut digunakan selama proses training.

Ukuran input citra:
224 × 224 piksel

Batch size:
32

Framework:
TensorFlow 2.x
