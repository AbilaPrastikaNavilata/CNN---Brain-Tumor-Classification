# 🧠 Brain Tumor Classification using CNN

Sebuah proyek pembelajaran dan eksperimen untuk mendeteksi keberadaan tumor otak dari citra MRI menggunakan pendekatan **Convolutional Neural Network (CNN)**. Proyek ini dibangun dan diuji di **Google Colab** menggunakan **TensorFlow** dan **Python**.

---

## 🔧 Teknologi yang Digunakan

| Teknologi | Deskripsi |
|----------|-----------|
| **TensorFlow & Keras** | Framework utama untuk membangun dan melatih model CNN |
| **NumPy** | Manipulasi data numerik dan array |
| **Matplotlib** | Visualisasi hasil prediksi dan performa model |
| **PIL (Python Imaging Library)** | Membaca dan memproses gambar MRI |
| **Google Colab** | Lingkungan eksekusi notebook Python berbasis cloud |

---

## 🧠 Arsitektur Model CNN

Model CNN yang digunakan memiliki struktur sebagai berikut:

Input Image (224x224x3)
│
├─ Conv2D (32 filters, 3x3, ReLU)
├─ MaxPooling2D (2x2)
│
├─ Flatten
├─ Dense (256 units, ReLU)
├─ Dropout (rate: 0.5)
├─ Dense (1 unit, Sigmoid) → Output (0 = No Tumor, 1 = Tumor)

---


Arsitektur ini cukup sederhana namun efektif untuk klasifikasi biner gambar medis.

---

## 🔄 Cara Kerja Sistem Deteksi

1. **Preprocessing Data**
   - Semua gambar diubah ukurannya ke 224x224 piksel dan dikonversi ke format RGB
   - Normalisasi data dilakukan agar nilai piksel berada dalam rentang [0,1]
   - Dataset dibagi menjadi training, validation, dan testing

2. **Pelatihan Model**
   - Model CNN dilatih selama 10 epoch
   - Menggunakan binary crossentropy loss dan Adam optimizer
   - Validasi dilakukan dengan data yang belum dilatih

3. **Evaluasi**
   - Mengukur akurasi model terhadap data testing
   - Visualisasi akurasi dan loss selama pelatihan

4. **Prediksi Eksternal**
   - Gambar MRI dapat diunggah untuk diklasifikasikan secara real-time
   - Sistem akan memberikan output: "Tumor detected" atau "No tumor detected"

---

## 📊 Hasil Prediksi & Visualisasi

### 🎯 Akurasi Model
Model mencapai akurasi sekitar **85%** pada data pengujian.

### 📈 Grafik Akurasi dan Loss

| Akurasi | Loss |
|--------|------|
| ![accuracy](https://github.com/username/repo-name/blob/main/assets/accuracy_plot.png) | ![loss](https://github.com/username/repo-name/blob/main/assets/loss_plot.png) |

### 🖼️ Contoh Gambar MRI yang Diuji

| Tumor | Tidak Ada Tumor |
|-------|-----------------|
| ![tumor](https://github.com/username/repo-name/blob/main/assets/sample_tumor.jpg) | ![normal](https://github.com/username/repo-name/blob/main/assets/sample_normal.jpg) |

### 🔮 Prediksi Gambar Eksternal

Gambar hasil upload pengguna akan dianalisis dan diklasifikasikan sebagai berikut:

```python
Prediction: Tumor detected ✅
