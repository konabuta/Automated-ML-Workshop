# Automated-ML-Workshop

Microsoft Automated ML Workshop Materials 

<br/>

## Sample Code
| Algorithm | Environment | Automated ML Type | Description | 
| --- | --- | --- | --- |
| Classification (Tabular) | Azure ML service Python SDK [ [Remote](Sample/Azure-Machine-Learning-service/Churn-classification-explainer-remote.ipynb) / [Local](Sample/Azure-Machine-Learning-service/Churn-classification-explainer.ipynb) ]| Automated ML | 顧客離反分析| 
| Classification (Tabular)| Azure ML service Python SDK [ [Remote](Sample/Azure-Machine-Learning-service/FactoryQC-classification-explainer-remote.ipynb) / [Local](Sample/Azure-Machine-Learning-service/FactoryQC-classification-explainer.ipynb) ]| Automated ML | 製品品質の予測| 
| Regression (Tabular)| Azure ML service Python SDK [ [Local](Sample/Azure-Machine-Learning-service/Automobile-regression-explainer.ipynb) / [Remote](Sample/Azure-Machine-Learning-service/Automobile-regression-explainer-remote.ipynb) ]| Automated ML | 中古車価格の予測| 
| Classification (Image)| Optuna + Azure ML service Python SDK [ [Remote](Sample/Azure-Machine-Learning-service/Mnist-classification-keras-Optuna.ipynb) ]| Optuna | MNIST 文字認識| 
| Classification (Image)| Neural Network Intelligence [ [Remote](Sample/NNI/MNIST/) ]| Tree-structured Parzen Estimator | MNIST 文字認識| 



<br/>

## Tuning Algorithm

### [Azure Machine Learning service - Automated ML](./Azure-Machine-Learning-service.md)
### [Optuna](https://optuna.org/)
### [Neural Network Intelligence](https://github.com/microsoft/nni)

<br/>    
  
## Setup
### Azure Machine Learning service

Azure Machine Learning service が提供している Notebook VM を利用すると、Python SDK が既にインストールされた Jupyter Notebook / JupyterLab を利用することができます。

[Notebook VM 利用手順](https://docs.microsoft.com/ja-JP/azure/machine-learning/service/quickstart-run-cloud-notebook)

既存のカーネルを利用しない or ローカルPCなど別環境で Azure Machine Learning service を利用する際は、新たに Python SDK をインストールします。

```bash
# New Conda
conda create -n myenv Python=3.6
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
See https://github.com/pfnet/optuna#installation

### Neural Network Intelligegnce
See https://github.com/microsoft/nni#install--verify

<br/>

## Reference
- [自動機械学習とは？ (製品ドキュメント)](https://docs.microsoft.com/ja-JP/azure/machine-learning/service/concept-automated-ml?WT.mc_id=oreilly-webinar-lazzeri)
- [アウトプットの理解 (製品ドキュメント)](https://docs.microsoft.com/ja-jp/azure/machine-learning/service/how-to-understand-automated-ml)
- [Automated ML Sample Notebook (GitHub)](https://github.com/Azure/MachineLearningNotebooks/tree/master/how-to-use-azureml/automated-machine-learning)
- [Probabilistic Matrix Factorization for Automated Machine Learning
(Microsoft Research Paper)](https://www.microsoft.com/en-us/research/publication/probabilistic-matrix-factorization-for-automated-machine-learning/)


