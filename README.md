# 📈 MSFT Hisse Senedi Fiyat Yönü Tahmin Projesi

## Proje Amacı

Bu projede Microsoft (MSFT) hisse senedinin **ertesi gün fiyatının yukarı mı aşağı mı gideceğini** tahmin etmeye çalışıyoruz. Yani bu bir **binary classification** problemi.

Veri olarak Yahoo Finance'den çekilen 1986-2024 arası günlük OHLCV (Open, High, Low, Close, Volume) verisini kullandık.

## Ne Yaptık?

- Veriyi keşfettik (EDA)
- Teknik indikatörler ve domain-knowledge featureları ürettik (hareketli ortalamalar, RSI, momentum vs.)
- Missing value ve outlier analizi yaptık
- Birden fazla model denedik (Logistic Regression, Random Forest, GBM, XGBoost, LightGBM, CatBoost)
- Cross-validation ile karşılaştırdık
- Hyperparameter tuning (Optuna) uyguladık
- SHAP ile feature importance çıkardık

## Klasör Yapısı

```
msft_ml_project/
│
├── MSFT_ml_notebook.ipynb   # Ana notebook (her şey burada)
├── requirements.txt          # Gerekli kütüphaneler
└── README.md                 # Bu dosya
```

## Nasıl Çalıştırılır?

```bash
pip install -r requirements.txt
jupyter notebook MSFT_ml_notebook.ipynb
```

## Sonuçlar (Özet)

En iyi model **LightGBM** oldu. ROC-AUC ~0.57 civarında çıktı ki bu hisse senedi tahmininde fena sayılmaz (piyasalar gerçekten zor şeyler).

## Notlar

- Bu bir eğitim/öğrenme projesidir, finansal tavsiye değildir!
- Veri: MSFT Daily OHLCV (1986-03-13 / 2024-10-30)
- 9737 gözlem, 7 orijinal kolon

---

