Final Project Submission — Image Classification with CNN (CIFAR-10)

Proyek ini membangun model Convolutional Neural Network (CNN) untuk melakukan klasifikasi gambar menggunakan dataset CIFAR-10.
Model dilatih, divalidasi, diuji, dan diekspor dalam tiga format berbeda: SavedModel, TensorFlow Lite (TFLite), dan TensorFlow.js (TFJS).
```
============================================================
STRUKTUR DIREKTORI SUBMISSION
============================================================
```
```
submission
│
├── saved_model
│   ├── saved_model.pb
│   ├── fingerprint.pb
│   ├── keras_metadata.pb
│   └── variables/
│       ├── variables.data-00000-of-00001
│       └── variables.index
│
├── tflite
│   ├── model.tflite
│   └── label.txt
│
├── tfjs_model
│   ├── model.json
│   ├── group1-shard1of2.bin
│   └── group1-shard2of2.bin
│
├── Notebook.ipynb
├── README.md
└── requirements.txt
```
```
============================================================
DATASET — CIFAR-10
============================================================
```
Dataset CIFAR-10 terdiri dari 60.000 gambar 32x32 piksel dalam 10 kelas:

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

Pembagian dataset:
- 50.000 gambar training
- 10.000 gambar testing
- Validation set: 10% dari training
```
============================================================
ARSITEKTUR MODEL
============================================================
```
Model dibangun menggunakan Keras Sequential dengan komponen:

- Conv2D
- BatchNormalization
- MaxPooling2D
- Dropout
- Dense

Optimizer: Adam
Loss: Sparse Categorical Crossentropy
Metrics: Accuracy
```
============================================================
CALLBACK YANG DIGUNAKAN
============================================================
```
- ModelCheckpoint (berdasarkan val_accuracy)
- EarlyStopping (monitoring val_loss)
- ReduceLROnPlateau
```
============================================================
HASIL TRAINING
============================================================
```
Model menunjukkan akurasi 80–90% tergantung jumlah epoch.
Plot accuracy dan loss tersedia dalam Notebook.ipynb.
```
============================================================
INFERENCE (BUKTI PREDIKSI)
============================================================
```
Contoh:

True: frog
Keras Pred : frog
TFLite Pred : frog

Inference dilakukan menggunakan model TFLite dan ditampilkan pada akhir notebook.
```
============================================================
FORMAT MODEL YANG DISIMPAN
============================================================
```
SavedModel (backend/server)
  → submission/saved_model/

TensorFlow Lite (mobile & embedded)
  → submission/tflite/model.tflite

TensorFlow.js (web)
  → submission/tfjs_model/model.json
```
============================================================
CARA MENJALANKAN NOTEBOOK
============================================================
```
1. Install dependencies:
   pip install -r requirements.txt

2. Jalankan notebook:
   jupyter notebook Notebook.ipynb
```
============================================================
TOOLS & LIBRARY
============================================================
```
- Python 3.10
- TensorFlow / Keras
- NumPy
- Matplotlib
- TensorFlow Lite
- TensorFlow.js Converter
```
============================================================
END
============================================================
```
