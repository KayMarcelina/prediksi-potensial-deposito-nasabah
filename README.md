 # Proyek Capstone - Model Machine Learning untuk Prediksi Deposito Nasabah Bank

Proyek ini merupakan bagian dari pembelajaran Data Science, yang bertujuan untuk membangun model machine learning dalam memprediksi apakah seorang nasabah akan melakukan **deposit** atau tidak, berdasarkan data historis kampanye marketing sebuah bank.

## Tujuan Proyek

Membantu tim marketing bank agar bisa:
- Menargetkan nasabah yang lebih potensial
- Mengurangi biaya kampanye
- Meningkatkan efektivitas promosi bank


## Dataset

Dataset ini berasal dari  Bank Marketing Campaign dataset. Yang terdiri dari beberapa kolom:

**Customer profile**
- age
- job
- balance
- housing
- loan

**Marketing data**
- contact: Contact communication type.
- month: Last contact month of the year.
- campaign: Number of contacts performed during this campaign and for this client.
- pdays: Number of days after the client was contacted from the previous campaign.
- poutcome: Outcome of the previous marketing campaign.
- deposit: Whether the customer deposits or not.

## Step by Step

1. **Business Understanding**
   - Menggali informasi tentang produk deposito berjangka di sebuah bank
   - Memahami hubungan antara kolom di dataset dan produk
2. **Eksplorasi Data**
   - Analisis distribusi fitur numerik dan kategorikal
   - Identifikasi outlier (contoh: `balance`, `age`, `campaign`, `pdays`)
3. **Pra-processing**
   - Encoding data kategorikal
   - Feature engineering: grup umur, kampanye, balance, dan pdays
   - Buat fitur tambahan: saldo negatif, apakah pernah dihubungi sebelumnya
4. **Pemodelan**
   - Benchmark model: Random Forest, XGBoost
   - Hyperparameter tuning
   - Penanganan data imbalance dengan SMOTE
5. **Evaluasi**
6. **Kesimpulan dan Rekomendasi**


## Algoritma yang Digunakan
| algo	                  |mean_f2	  |std	      |all score                      |
|-------------------------|-----------|-----------|-------------------------------|
|Logistic Regression      |0.637849   |0.021340   |[0.64, 0.67, 0.6, 0.65, 0.63]  |
|KNeighbors               |0.616026   |0.025163   |[0.62, 0.66, 0.61, 0.6, 0.59]  |
|Decision Tree            |0.611517   |0.008607   |[0.62, 0.62, 0.6, 0.6, 0.61]   |
|Random Forest            |0.649276   |0.013262   |[0.64, 0.67, 0.63, 0.66, 0.65] |
|AdaBoost                 |0.603874   |0.016934   |[0.61, 0.59, 0.58, 0.61, 0.63] |
|Gradient Boosting        |0.634951   |0.020581   |[0.66, 0.66, 0.61, 0.64, 0.61] |
|XGBoost                  |0.640365   |0.016751   |[0.66, 0.66, 0.63, 0.64, 0.62] |


---

## Hasil Evaluasi

Confusion Matrix with Threshold 0.35:
 [[430 385]
 [157 589]]

Classification Report:
               precision    recall  f1-score   support

           0       0.73      0.53      0.61       815
           1       0.60      0.79      0.68       746

    accuracy                           0.65      1561
   macro avg       0.67      0.66      0.65      1561
weighted avg       0.67      0.65      0.65      1561

## Dari hasil evaluasi threshold bisa kita lihat bahwa threshold 0.35 bisa menekan kerugian dari yang sebelumnya sebesar 12.27% menjadi 14.23%. Pengurangan ini menunjukkan efektivitas model dalam memprediksi nasabah yang berpotensi untuk deposit.


## Struktur Folder
- Dataset: data_bank_marketing_campaign.csv
- Jupyter Notebooks: capstone_modul3.ipynb
- Model terbaik yang disimpan: model_randomforest_v1.sav
- File persentasi: Potensial_nasabah_deposito.pptx

Silakan buka file capstone_modul3.ipynb untuk melihat seluruh proses dari data cleaning sampai evaluasi model.


