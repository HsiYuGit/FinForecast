# 情緒分析模型
本專案採用如下模型
1. Tfidf + Logistic Regression
2. FinBERT
3. GPT
## 資料前處理
使用Kaggle Dataset `ankurzing/sentiment-analysis-for-financial-news`，並以8:2比例切分為訓練：測試資料

請見`Kaggle_Data_Preprocess.ipynb`

測試集請見`X_test`及`y_test`，訓練集請見`X_train`及`y_train`；如須合併檔案，請用`Merge_CSV.ipynb`
## Tfidf + Logistic Regression
## FinBERT
本專案使用HuggingFace上[`yiyanghkust/finbert-tone`](https://huggingface.co/yiyanghkust/finbert-to)提供的模型
## GPT
本專案使用`gpt-4.1-nano-2025-04-14`<br>
微調超參數如下：
```
Epochs: 3
Batch size: 7
LR multiplier: 0.1
Seed: 707577940
```
### 表現
因Dashboard限制，僅能測試500筆資料。
- 微調前：表現與FinBERT無明顯差距
```
              precision    recall  f1-score   support

    negative       0.75      0.95      0.84        63
     neutral       0.90      0.65      0.75       284
    positive       0.62      0.88      0.73       153

    accuracy                           0.76       500
   macro avg       0.76      0.83      0.77       500
weighted avg       0.80      0.76      0.76       500

[[ 60   3   0]
 [ 19 184  81]
 [  1  17 135]]
```
- 微調後：表現明顯優於FinBERT
```
              precision    recall  f1-score   support

    negative       0.82      0.95      0.88        63
     neutral       0.91      0.86      0.88       284
    positive       0.82      0.85      0.83       153

    accuracy                           0.87       500
   macro avg       0.85      0.89      0.87       500
weighted avg       0.87      0.87      0.87       500

[[ 60   3   0]
 [ 12 243  29]
 [  1  22 130]]
```
## 已被捨棄的模型
- FastText + Logistic Regression：因在測試集的表現劣於Tfidf，故不採用
