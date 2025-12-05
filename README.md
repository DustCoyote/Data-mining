README

# 1. 實驗環境 (Environment)

本實驗於 Google Colab 執行，並使用下列 Python 版本與套件。

Python 版本

Python 3.10 以上

套件安裝
pip install kagglehub pandas numpy seaborn matplotlib plotly scikit-learn


# 2. 資料集來源 (Dataset Source)

使用之資料集為 Kaggle Diabetes Data Set。

資料來源
https://www.kaggle.com/datasets/mathchi/diabetes-data-set

使用 KaggleHub 下載方式如下：

import kagglehub
from kagglehub import KaggleDatasetAdapter

file_path = "diabetes.csv"

diabetes_df = kagglehub.load_dataset(
    KaggleDatasetAdapter.PANDAS,
    "mathchi/diabetes-data-set",
    file_path,
)

# 3. 實驗方法與模型 (Methods)

比較多種傳統與自訂損失函數之二元分類方法，包含：

# 3.1 傳統方法

Delta Rule (SSE)

ADALINE (MSE)

Logistic Regression (BCE)

# 3.2 ANYLOSS 系列

採用 soft confusion matrix 技術，透過可微分的 TP、FP、FN、TN 估計，目標直接優化下列指標：

Loss 名稱	目的
AccAim	最大化 Accuracy
F1Aim	最大化 F1 Score
F0.5Aim	偏重 Precision
F2Aim	偏重 Recall
GAim	最大化 G-Mean
BAim	最大化 Balanced Accuracy


# 4.使用方法
依序執行colab的各個Cell即可
