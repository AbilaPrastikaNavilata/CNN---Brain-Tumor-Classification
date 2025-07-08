🧠 Klasifikasi Gambar Tumor Otak Menggunakan CNN
📍 Deteksi Tumor Otak dari Citra MRI Berbasis Convolutional Neural Network

🎯 Tujuan Proyek
Mengembangkan model Convolutional Neural Network (CNN) yang mampu mengklasifikasikan gambar MRI otak ke dalam dua kelas:
✅ Tumor
❌ Non-Tumor

🧰 Teknologi yang Digunakan
Teknologi	Fungsi
Python	Bahasa pemrograman utama
TensorFlow & Keras	Framework untuk membangun dan melatih model deep learning
OpenCV & PIL	Pemrosesan gambar (grayscale, resize, normalisasi)
Matplotlib	Visualisasi grafik dan gambar
Google Colab	Lingkungan pemrograman cloud berbasis Jupyter
KaggleHub	Akses dataset MRI tumor otak

📦 Dataset
Dataset berasal dari Kaggle:
🧩 brain-mri-images-for-brain-tumor-detection

Kelas:

yes → Gambar MRI dengan tumor (155 gambar)

no → Gambar MRI tanpa tumor (98 gambar)

Total: 253 gambar
Ukuran gambar: 224 x 224 piksel
Warna: RGB

🔧 Preprocessing Data
Resize semua gambar ke ukuran 224x224 piksel

Konversi ke RGB & normalisasi ke [0, 1]

Labeling:

Tumor = 1

Non-tumor = 0

Split Data:

80% data latih

20% data uji

Batching: dengan batch_size = 32

🧠 Arsitektur Model CNN
python
Copy
Edit
model = Sequential([
    Conv2D(32, (3,3), activation='relu', input_shape=(224,224,3)),
    MaxPooling2D((2,2)),
    Flatten(),
    Dense(256, activation='relu'),
    Dropout(0.5),
    Dense(1, activation='sigmoid')
])
Optimizer: Adam

Loss: binary_crossentropy

Aktivasi Output: Sigmoid

📈 Hasil Pelatihan Model
Dilatih selama 10 epoch dengan akurasi akhir:

Epoch	Train Accuracy	Val Accuracy
1	58.89%	45.00%
5	84.11%	95.00%
10	100.00%	100.00%

🎯 Final Accuracy (Testing): 85.64%
📉 Final Loss (Testing): 0.6342

