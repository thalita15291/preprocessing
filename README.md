# implementasi tahap *preprocessing* data (kdd)
## studi kasus: *credit approval dataset*

[![status proyek](https://img.shields.io/badge/status-selesai-green.svg)](https://github.com/thalita15291/preprocessing)
[![metode utama](https://img.shields.io/badge/metode-pipeline%20%26%20standardscaler-blue.svg)](https://archive.ics.uci.edu/dataset/27/credit+approval)

---

### 1. deskripsi proyek dan tujuan

studi kasus preprocessing data (kdd) pada **credit approval dataset**. fokus pada perancangan **pipeline**, **standardisasi skala**, dan verifikasi data siap untuk *data mining*.

**tujuan:** mentransformasi data mentah menjadi data yang **bersih, terstandardisasi ($\text{mean} \approx 0, \text{std} \approx 1$), dan siap** untuk pemodelan.

### 2. metodologi implementasi (*pipeline* terintegrasi)

seluruh proses *cleaning* dan *transformation* diotomatisasi menggunakan **pipeline** dan **columntransformer**.

| tahap | teknik implementasi | fungsi |
| :--- | :--- | :--- |
| **transformation** (*scaling*) | `standardscaler()` | menstandardisasi skala data numerik. |
| **cleaning** (*imputation*) | `simpleimputer(median / most_frequent)` | mengatasi *missing value* ('?'). |
| **seleksi akhir** | `train_test_split(test_size=0.3)` | membagi data menjadi set *training* dan *testing* (70:30). |

---

### 3. verifikasi keberhasilan *transformation* (bukti serius)

keberhasilan `standardscaler` diverifikasi secara numerik. ini adalah **bukti** bahwa data siap untuk model berbasis jarak.

#### hasil *output* statistik (bukti standardisasi)

```text
                a2            a3            a8           a11           a14           a15
mean -1.829569e-17 -1.026401e-16  7.519003e-17 -2.316854e-17 -3.901962e-17  1.171808e-17
std   1.000726e+00  1.000726e+00  1.000726e+00  1.000726e+00  1.000726e+00  1.000726e+00
