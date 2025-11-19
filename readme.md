==================== README.txt ====================

Final Project Submission — Image Classification with CNN (CIFAR-10)

Deskripsi Proyek
Proyek ini membangun model Convolutional Neural Network (CNN) untuk melakukan klasifikasi gambar menggunakan dataset CIFAR-10. Dataset terdiri dari 60.000 gambar 32x32 piksel dengan 10 kelas. Model dilatih, dievaluasi, dan diekspor dalam format SavedModel, TensorFlow Lite (TFLite), dan TensorFlow.js (TFJS) sesuai kriteria submission.

Struktur Direktori Submission

submission
│
├── saved_model
│ ├── saved_model.pb
│ ├── fingerprint.pb
│ ├── keras_metadata.pb
│ └── variables/
│ ├── variables.data-00000-of-00001
│ └── variables.index
│
├── tflite
│ ├── model.tflite
│ └── label.txt
│
├── tfjs_model
│ ├── model.json
│ ├── group1-shard1of2.bin
│ └── group1-shard2of2.bin
│
├── Notebook.ipynb
├── README.txt
└── requirements.txt

Dataset
Dataset yang digunakan adalah CIFAR-10, dengan 10 kelas:

airplane

automobile

bird

cat

deer

dog

frog

horse

ship

truck

Jumlah data:

50.000 gambar training

10.000 gambar testing

Dataset dibagi menjadi: training set, validation set (10% dari training), dan test set.

Arsitektur Model
Model dibangun menggunakan Keras Sequential dengan beberapa layer:

Conv2D + BatchNormalization + MaxPooling

Dropout untuk mengurangi overfitting

Dense layer sebagai classifier

Optimizer: Adam

Loss: Categorical Crossentropy

Callback yang Digunakan
Model menggunakan callback berikut:

ModelCheckpoint: menyimpan model terbaik berdasarkan val_accuracy

EarlyStopping: menghentikan training jika val_loss tidak membaik

ReduceLROnPlateau: menurunkan learning rate ketika model stagnan

Hasil Training
Model menunjukkan peningkatan stabil pada accuracy dan penurunan loss selama training. Hasil validasi menunjukkan nilai akurasi sekitar 80-90% tergantung training.

Plot accuracy dan loss dapat dilihat pada Notebook.ipynb.

Inference (Pembuktian Prediksi)
Inference dilakukan menggunakan model TFLite untuk memenuhi syarat “menggunakan salah satu model”. Contoh hasil:

True: frog
Keras Pred: frog
TFLite Pred: frog

Gambar input dan output prediksi ditampilkan di akhir notebook sebagai bukti inferensi.

Format Model yang Disimpan

SavedModel (untuk server/backend)
Lokasi: submission/saved_model/

TensorFlow Lite (untuk mobile dan embedded)
Lokasi: submission/tflite/model.tflite

TensorFlow.js (untuk web dan browser)
Lokasi: submission/tfjs_model/model.json

Cara Menjalankan Notebook

Install dependencies:
pip install -r requirements.txt

Jalankan notebook:
jupyter notebook Notebook.ipynb

Tools & Library

Python 3.10

TensorFlow / Keras

NumPy

Matplotlib

TensorFlow Lite

TensorFlow.js Converter

==================== END ====================