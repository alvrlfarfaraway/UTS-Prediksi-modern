# Prediksi Default Kartu Kredit (UTS Machine Learning)

Nama: Alverrell Gustivierda Zidna Fann
NIM: 2404220021

Eksperimen machine learning untuk memprediksi apakah nasabah kartu kredit akan **default pada bulan berikutnya**, memakai *Default of Credit Card Clients Dataset* (30.000 observasi, [Kaggle](https://www.kaggle.com/datasets/uciml/default-of-credit-card-clients-dataset)). Metrik utama adalah **F1-score**, dengan 5-fold Stratified Cross Validation.

## Isi repository
| Path | Keterangan |
|---|---|
| `notebooks/UTS_PMML_Credit.ipynb` | Notebook lengkap: Data Understanding, Data Preparation, Experiment 1 sampai 5, beserta kode dan output |
| `requirements.txt` | Daftar library yang dipakai |

Dataset tidak disimpan di repository. Notebook mengunduhnya langsung dari Kaggle memakai `kagglehub`.

## Ringkasan hasil
| Exp | Model | CV F1 | Test Acc | Test Prec | Test Rec | Test F1 |
|---|---|---|---|---|---|---|
| 1 | Logistic Regression (baseline) | 0.3692 | 0.8082 | 0.6841 | 0.2464 | 0.3623 |
| 2 | Logistic Regression + preprocessing | 0.3641 | 0.8088 | 0.6923 | 0.2442 | 0.3610 |
| 3 | Random Forest (hasil Experiment 3) | 0.4704 | 0.8138 | 0.6371 | 0.3677 | 0.4663 |
| 4 | Random Forest + GridSearchCV | 0.5452 | 0.7927 | 0.5295 | 0.5607 | 0.5447 |
| 5 | XGBoost | 0.4783 | 0.8178 | 0.6630 | 0.3587 | 0.4655 |

## Cara menjalankan (Google Colab)
1. Buka notebook di Colab (File, lalu Upload notebook, atau buka dari GitHub).
2. Hapus tanda `#` pada sel pertama (`!pip install -q kagglehub`) bila `kagglehub` belum terpasang.
3. Jalankan seluruh sel (Runtime, lalu Run all). Grid search Random Forest membutuhkan waktu cukup lama.

## Cara menjalankan (lokal)
```bash
pip install -r requirements.txt
jupyter notebook notebooks/UTS_PMML_Credit.ipynb
```
