# 1. プログラムの目的
### LLM由来の値が機械学習モデルの特徴量として予測に有用か検証する。   

#### 検証したLLM由来の値
- log likelihood（v1）
- 隠れ層（v2で実装予定）  
   
# 2. フォルダ構成
#### dataset
- Telecom_customer churn.csv（[kaggle](https://www.kaggle.com/code/dhanyabahadur/churn-prediction-on-telecom-dataset)元データ）
- Telecom_customer churn_10+1.csv（Telecom_customer churn.csvから10個の特徴量とchurnのみ取り出したもの）
- loglikelihood_10000.csv（Telecom_customer churn_10+1.csvのうち、最初の10,000行を取り出し、loglikelyhood_telecom.ipynbでloglikelyhoodを算出したデータ）
#### prompt
- 10,000レコード分のプロンプトを出力する用のディレクトリ（GitHubには容量的にuploadできないので空にしている）

#### jupyter notebook
- churn-predict-lightgbm.ipynb（機械学習用プログラム）
- loglikelyhood_telecom.ipynb（ローカルLLMを使用しlog likelihoodを算出するプログラム）
- make_prompt_from_churn_csv.ipynb（解約予測を問うプロンプト作成用プログラム）

# 3. 実行方法
* make_prompt_from_churn_csv.ipynbでプロンプト作成
* loglikelyhood_telecom.ipynbでlog likelihoodのデータセットを作成（10,000行で3時間以上の時間がかかる。既にデータセット格納済み）
* churn-predict-lightgbm.ipynbで機械学習