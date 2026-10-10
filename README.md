# grokking Deep Learning (MANNING)

Reproduksi kode dan pendalaman teoritis untuk bab 1-10 dari buku *Grokking Deep Learning* karya Andrew W. Trask (Manning).
Repositori ini merupakan tugas pengayaan individu untuk mata kuliah Deep Learning. Setiap bab memiliki notebook dengan:

1. **ringkasan bab**,
2. **penjelasan teoritis** tentang konsep-konsep utama,
3. **reproduksi kode**, ditulis hanya menggunakan numpy (seperti pada buku) dan dieksekusi, dilengkapi dengan output serta plot, dan
4. **poin-poin kunci (key takeaways)**.

Buku ini membangun deep learning dari nol: tidak ada framework yang digunakan dalam bab-bab ini, sehingga setiap forward pass, gradien, dan pembaruan bobot terlihat secara jelas.

## Struktur Repositori

```
.
├── README.md
├── requirements.txt
├── data/mnist/                 # MNIST (file idx gzip) yang digunakan oleh bab 7-10
└── notebooks/
    ├── Chapter 1 - Introducing Deep Learning.ipynb
    ├── Chapter 2 - Fundamental Concepts.ipynb
    ├── Chapter 3 - Forward Propagation.ipynb
    ├── Chapter 4 - Gradient Descent.ipynb
    ├── Chapter 5 - Generalizing Gradient Descent.ipynb
    ├── Chapter 6 - Backpropagation.ipynb
    ├── Chapter 7 - Picturing Neural Networks.ipynb
    ├── Chapter 8 - Regularization and Batching.ipynb
    ├── Chapter 9 - Activation Functions.ipynb
    └── Chapter 10 - Convolutional Neural Networks.ipynb
```

## Ikhtisar Bab

| # | Bab | Gagasan Utama |
|---|---|---|
| 1 | Introducing Deep Learning | Mengapa deep learning penting; AI vs ML vs DL; proses belajar berarti menyesuaikan bobot untuk mengurangi error. Konseptual, dengan satu demo kecil. |
| 2 | Fundamental Concepts | Supervised vs unsupervised learning, model parametrik vs non-parametrik, dan alur *predict -> compare -> learn*. |
| 3 | Forward Propagation | Cara jaringan membuat prediksi: penjumlahan berbobot, banyak input/output, matriks bobot, hidden layer, dasar-dasar numpy. |
| 4 | Gradient Descent | Langkah membandingkan (*compare*) dan belajar (*learn*): squared error, hot-and-cold learning, turunan (derivatif), `weight_delta = delta * input`, learning rate dan divergensi. |
| 5 | Generalizing Gradient Descent | Gradient descent dengan banyak bobot: banyak input, output, dan keduanya (outer product); membekukan (*freezing*) bobot; makna dari bobot. |
| 6 | Backpropagation | Mengapa jaringan dua layer gagal pada pola non-linear, hidden layer dengan ReLU, dan propagasi balik (*backpropagating*) delta pada jaringan tiga layer. |
| 7 | Picturing Neural Networks | Diagram yang disederhanakan (layer sebagai vektor, bobot sebagai matriks), ringkasan korelasi, bobot sebagai templat. |
| 8 | Regularization and Batching | Overfitting pada MNIST, early stopping, dropout, dan mini-batch gradient descent. |
| 9 | Activation Functions | Sigmoid, tanh, ReLU, dan softmax, turunannya, serta jaringan MNIST berbasis tanh + softmax. |
| 10 | Convolutional Neural Networks | Pembagian bobot (*weight sharing*) dengan kernel, mengekstrak bagian gambar, CNN yang dilatih dengan numpy, efisiensi parameter. |

### Deskripsi Singkat Setiap Bab
* **Bab 1** memberikan motivasi deep learning dan menyatakan filosofi buku: pahami matematika dengan membangun segalanya sendiri. Notebook menjelaskan hierarki AI/ML/DL dan mendemonstrasikan pembelajaran sebagai penyesuaian satu "knob".
* **Bab 2** memberikan kosakata yang digunakan pada bab selanjutnya. Demo: model supervised satu parameter, k-means (unsupervised), dan k-nearest neighbors (non-parametrik).
* **Bab 3** hanya membahas prediksi (forward propagation) menggunakan contoh jari kaki / rekor menang-kalah / jumlah penggemar, mulai dari satu bobot hingga hidden layer.
* **Bab 4** memperkenalkan pembelajaran melalui pengukuran error dan gradient descent, serta menunjukkan secara eksperimental bagaimana learning rate mengontrol konvergensi dan divergensi.
* **Bab 5** memperluas gradient descent ke jaringan dengan banyak bobot dan output serta menunjukkan bahwa error dapat mencapai nol bahkan dengan bobot yang dibekukan.
* **Bab 6** adalah jaringan dalam pertama: masalah lampu lalu lintas (*streetlight problem*) menunjukkan bahwa pola non-linear membutuhkan hidden layer dengan non-linearitas yang dilatih menggunakan backpropagation.
* **Bab 7** bersifat konseptual: memberikan gambaran mental untuk menalar jaringan, termasuk ringkasan korelasi dan gagasan bahwa bobot adalah templat (plot ekstensi pada MNIST).
* **Bab 8** melatih pada MNIST dan mendemonstrasikan overfitting, kemudian menguranginya dengan dropout dan batching.
* **Bab 9** menjelaskan cara memilih fungsi aktivasi dan membangun jaringan klasifikasi standar (hidden layer tanh, output softmax).
* **Bab 10** memperkenalkan konvolusi dan mengimplementasikan layer konvolusional, gradiennya, serta loop pelatihan penuh dalam numpy.

## Catatan
* Hanya Bab 1-10 yang dicakup, sesuai dengan cakupan tugas. Bab 11-15 dari buku (NLP, RNN, framework, LSTM, dan federated learning) tidak direproduksi di sini.
* Seluruh kode merupakan implementasi numpy saya sendiri dari gagasan buku dan mungkin berbeda detailnya (hiperparameter, vektorisasi, nama variabel) dari daftar di buku. Oleh karena itu, hasilnya mungkin sedikit berbeda dari buku.
* MNIST: 1.000 gambar pelatihan pertama digunakan untuk pelatihan dan seluruh 10.000 gambar pengujian untuk evaluasi, seperti di buku. File gzip di `data/mnist/` adalah file idx asli MNIST.

## Cara Menjalankan

```bash
git clone <url-repo-anda>
cd grokking-Deep-Learning
pip install -r requirements.txt
jupyter notebook notebooks/
```

Notebook menggunakan jalur relatif (`../data/mnist/`), jadi bukalah dari folder `notebooks`. Bab 10 melatih CNN dengan numpy dan memakan waktu sekitar satu menit pada CPU.

## Referensi
Trask, A. W. *Grokking Deep Learning*. Manning Publications, 2019.
