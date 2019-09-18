# Automated-ML-Workshop

Azure Machine Learning Automated ML Workshop materials 

<br/>

## Workshop Contents
### 中古車価格の予測モデリング
- [Simple](notebooks/Automobile-regression.ipynb)
- [with Explainer](notebooks/Automobile-regression-explainer.ipynb)
### 品質管理の予測モデリング
- [Simple](notebooks/FactoryQC-classification.ipynb)
- [with Explainer](notebooks/FactoryQC-classification-explainer.ipynb)
### 顧客離反の予測モデリング
- [Simple](notebooks/Churn-classification.ipynb)
- [with Explainer](notebooks/Churn-classification-explainer.ipynb)

<br/>

## Automated Machine Learning
Azure Machine Learning が提供する Automated Machine Learning は、特徴量エンジニアリング & モデル選択 & パラメータ選択を全自動で行います。

<img src="https://docs.microsoft.com/ja-jp/azure/machine-learning/service/media/tutorial-auto-train-models/flow2.png" width=400>

## Azure Machine Learning service
### [Azure Machine Learning service](https://docs.microsoft.com/ja-JP/azure/machine-learning/service/)
Azure Machine Learning service は、機械学習/深層学習のプロセスを効率的に回すオープンな分析プラットフォームです。

<img src="https://docs.microsoft.com/en-us/azure/machine-learning/service/media/concept-azure-machine-learning-architecture/workflow.png" width = "500">   


<br/>    
  
## 環境準備
### Azure Machine Learning service Python SDK

Azure Machine Learning service が提供している Notebook VM を利用すると、Python SDK が既にインストールされた Jupyter Notebook / JupyterLab を利用することができます。

[Notebook VM 利用手順](https://docs.microsoft.com/ja-JP/azure/machine-learning/service/quickstart-run-cloud-notebook)

既存のカーネルを利用しない or ローカルPCなど別環境で Azure Machine Learning service を利用する際は、新たに Python SDK をインストールします。

```python
# New Conda
conda create -n myenv Python=3.6
# Activate 
conda activate myenv
```
```python
# Package Install
pip install --upgrade azureml-sdk[notebooks,automl,explain,contrib] azureml-dataprep
```
```python
# Jupyter Kernel
python -m ipykernel install --user --name myenv --display-name myenv
```

詳細は構築手順は[こちらのページ](https://docs.microsoft.com/ja-JP/azure/machine-learning/service/how-to-configure-environment#local)をご参照ください。

<br/>

## Reference
- [自動機械学習とは？ (製品ドキュメント)](https://docs.microsoft.com/ja-JP/azure/machine-learning/service/concept-automated-ml?WT.mc_id=oreilly-webinar-lazzeri)
- [アウトプットの理解 (製品ドキュメント)](https://docs.microsoft.com/ja-jp/azure/machine-learning/service/how-to-understand-automated-ml)
- [Automated ML Sample Notebook (GitHub)](https://github.com/Azure/MachineLearningNotebooks/tree/master/how-to-use-azureml/automated-machine-learning)
- [Probabilistic Matrix Factorization for Automated Machine Learning
(Microsoft Research Paper)](https://www.microsoft.com/en-us/research/publication/probabilistic-matrix-factorization-for-automated-machine-learning/)


