
# MobileNetV3-Large Transfer Learning

## Deskripsi

Proyek ini melakukan klasifikasi gambar menjadi dua kelas:

- `botol`
- `box`

Model yang digunakan adalah MobileNetV3-Large.

Eksperimen dilakukan untuk membandingkan performa beberapa konfigurasi
MobileNetV3-Large menggunakan dataset yang sama.

## Dataset

Dataset terdiri dari 100 gambar:

| Kelas | Jumlah |
|---|---:|
| botol | 50 |
| box | 50 |
| Total | 100 |

Pembagian dataset:

- Training: 70%
- Validation: 15%
- Testing: 15%

Ukuran input model: `224 x 224`.

## Eksperimen

Tiga eksperimen dibandingkan:

### E1 — Pretrained

MobileNetV3-Large menggunakan bobot pretrained ImageNet.

### E2 — Scratch

MobileNetV3-Large dilatih tanpa bobot pretrained.

### E3 — Tuning

MobileNetV3-Large menggunakan bobot pretrained ImageNet
dan dilakukan partial fine-tuning pada sebagian layer.

## Hasil

Hasil lengkap terdapat pada:

- `hasil/tabel_3_eksperimen.csv`
- `hasil/hasil_evaluasi_3_model.csv`
- `hasil/hasil_evaluasi.txt`
- `hasil/ringkasan_3_eksperimen.txt`

Grafik:

- `hasil/grafik_akurasi_3_mode.png`
- `hasil/grafik_loss_3_mode.png`

Confusion matrix:

- `hasil/e1_pretrained_confusion_matrix.png`
- `hasil/e2_scratch_confusion_matrix.png`
- `hasil/e3_tuning_confusion_matrix.png`

## Model

Model tersimpan pada folder `model/`:

- `E1_pretrained.keras`
- `E2_scratch.keras`
- `E3_tuning.keras`

## Kesimpulan

Perbandingan ketiga eksperimen digunakan untuk melihat pengaruh
penggunaan pretrained weights dan proses fine-tuning terhadap
akurasi klasifikasi serta latency model.

Karena dataset yang digunakan berjumlah relatif kecil, hasil akurasi
perlu dipertimbangkan sebagai hasil eksperimen pada dataset ini dan
belum dapat langsung dianggap mewakili performa pada dataset yang
lebih besar.

