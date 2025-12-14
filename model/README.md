# 情緒分析模型
本專案採用如下模型
1. Tfidf + Logistic Regression
2. FinBERT
## 資料前處理
使用Kaggle Dataset `ankurzing/sentiment-analysis-for-financial-news`，並以8:2比例切分為訓練：測試資料

請見`Kaggle_Data_Preprocess.ipynb`
測試集請見`X_test`及`y_test`，訓練集請見`X_train`及`y_train`
## Tfidf + Logistic Regression
## FinBERT
本專案使用HuggingFace上[`yiyanghkust/finbert-tone`](https://huggingface.co/yiyanghkust/finbert-to)提供的模型
## 已被捨棄的模型
- FastText + Logistic Regression：因在測試集的表現劣於Tfidf，故不採用
