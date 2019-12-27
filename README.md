# Automated-ML-Workshop

Microsoft Automated ML Workshop Materials 

- Module 0. 環境のセットアップ
- Module 1. 自動機械学習 Automated ML GUI & Python SDK  
- Module 2. モデル解釈可能性 Model Interpret  
- Module 3. Advanced Topics  

<br/>

## Sample Code
| Algorithm | Environment | Version | Description | Other | 
| --- | --- | --- | --- | --- | 
| Classification (Tabular) | [AzureML - AutoML](Sample/Azure-Machine-Learning/Churn-classification-explainer-remote.ipynb)| Azure ML Python SDK 1.0.76 | 顧客離反分析| |
| Classification (Tabular)| [AzureML - AutoML](Sample/Azure-Machine-Learning/FactoryQC-classification-explainer-remote.ipynb)| Azure ML Python SDK 1.0.62 | 製品品質の予測| |
| Regression (Tabular)| [AzureML - AutoML](Sample/Azure-Machine-Learning/Automobile-regression-explainer-remote.ipynb)|Azure ML Python SDK  1.0.76 | 中古車価格の予測| |
| Forecasting (Tabular)| [AzureML - AutoML](Sample/Azure-Machine-Learning/Energy-demand-forecasting-explainer-remote.ipynb)|Azure ML Python SDK  1.0.76 | エネルギー需要予測| |
| Classification (Image)| [AzureML - HyperDrive](Sample/Azure-Machine-Learning/Image-Classification-catdog-dataset-Hyperdrive.ipynb)|Azure ML Python SDK  1.0.76 | 犬猫の画像分類| |
| Classification (Image)| [Optuna + Azure Machine Learning](Sample/Optuna/Mnist-classification-keras-Optuna.ipynb)| Azure ML Python SDK 1.0.65 |  MNIST 文字認識| Azure Database for MySQL へ接続  |
| Classification (Image) | [Neural Network Intelligence](Sample/NNI/MNIST/)| NNI 1.1 | MNIST 文字認識| Tree-structured Parzen Estimator |



<br/>

## Tuning Algorithm

-  [Azure Machine Learning service - Automated ML](./Azure-Machine-Learning-service.md)
-  [Optuna](https://optuna.org/)
-  [Neural Network Intelligence](https://github.com/microsoft/nni)

<br/>    


## Model Interpretability

- [BlackBox モデル解釈の概要](./Model-Agnostic-Methods.md)
- [自動機械学習におけるモデル解釈可能性 (製品ドキュメント)](https://docs.microsoft.com/ja-jp/azure/machine-learning/service/how-to-machine-learning-interpretability-automl)

<br>
 
## Setup
### Azure Machine Learning

#### Azure Machine Learning ワークスペースのセットアップ

必要な環境準備の手順は下記チュートリアルをご参照ください。

- Azure Machine Learning  の環境構築とチュートリアル<br>
・ [チュートリアル:Python SDK で初めての ML 実験を作成する](https://docs.microsoft.com/ja-JP/azure/machine-learning/service/tutorial-1st-experiment-sdk-setup)<br>
・ [チュートリアル: 最初の ML モデルをトレーニングする](https://docs.microsoft.com/ja-JP/azure/machine-learning/service/tutorial-1st-experiment-sdk-train)

ある程度の機械学習や Python の知識も必要になります。普段あまり機械学習に触れていない方は下記のトレーニングコースをご参照ください。

- Aidemy 無償トレーニングコース
    - [機械学習概論](https://aidemy.net/courses/2010)
    - [Python入門](https://aidemy.net/courses/3010)

#### Python 開発環境 をローカル環境で構築する場合
Azure Machine Learning が提供している Notebook VM を利用すると、Python SDK が予めインストールされた Jupyter Notebook / JupyterLab を利用することができます。

既存のカーネルを利用しない or ローカルPC etc 別環境で Azure Machine Learning を利用する際は、新たに Python SDK をインストールします。

```bash
# New Conda
conda create -n myenv python=3.6
# Activate 
conda activate myenv
```
```bash
# Package Install
pip install --upgrade azureml-sdk[notebooks,automl,explain,contrib] azureml-dataprep
```
```bash
# Jupyter Kernel
python -m ipykernel install --user --name myenv --display-name myenv
```

詳細は構築手順は[こちらのページ](https://docs.microsoft.com/ja-JP/azure/machine-learning/service/how-to-configure-environment#local)をご参照ください。

### Optuna
See  https://github.com/pfnet/optuna#installation

### Neural Network Intelligegnce
See  https://github.com/microsoft/nni#install--verify

<br/>

## Reference
- [自動機械学習とは？ (製品ドキュメント)](https://docs.microsoft.com/ja-JP/azure/machine-learning/service/concept-automated-ml?WT.mc_id=oreilly-webinar-lazzeri)
- [アウトプットの理解 (製品ドキュメント)](https://docs.microsoft.com/ja-jp/azure/machine-learning/service/how-to-understand-automated-ml)
- [モデル解釈可能性 (製品ドキュメント)](https://docs.microsoft.com/ja-JP/azure/machine-learning/service/how-to-machine-learning-interpretability)
- [Automated ML Sample Notebook (Microsoft Official)](https://github.com/Azure/MachineLearningNotebooks/tree/master/how-to-use-azureml/automated-machine-learning)
- [Probabilistic Matrix Factorization for Automated Machine Learning (Microsoft Research AutoML Meta Learning)](https://www.microsoft.com/en-us/research/publication/probabilistic-matrix-factorization-for-automated-machine-learning/)

- [Interpret-Community (Interpret Library by Microsoft)](https://github.com/interpretml/interpret-community)

- [Interpretable Machine Learning (General Guidance)](https://christophm.github.io/interpretable-ml-book/)

- [機械学習モデル解釈ナイト (DLLAB)](https://dllab.connpass.com/event/153453/)