# 情緒分析模型
本專案採用如下模型
1. Tfidf + Logistic Regression
2. FinBERT
## Tfidf + Logistic Regression
## FinBERT
本專案使用HuggingFace上[`yiyanghkust/finbert-tone`](https://huggingface.co/yiyanghkust/finbert-to)提供的模型
## 已被捨棄的模型
- FastText + Logistic Regression：因在測試集的表現劣於Tfidf，故不採用
