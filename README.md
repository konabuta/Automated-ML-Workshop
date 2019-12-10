# Automated-ML-Workshop

Microsoft Automated ML Workshop Materials 

<br/>

## Sample Code
| Algorithm | Environment | Version | Description | 
| --- | --- | --- | --- |
| Classification (Tabular) | [Azure Machine Learning](Sample/Azure-Machine-Learning-service/Churn-classification-explainer-remote.ipynb)| Azure ML Python SDK 1.0.76 | 顧客離反分析| 
| Classification (Tabular)| [Azure Machine Learning](Sample/Azure-Machine-Learning-service/FactoryQC-classification-explainer-remote.ipynb)| Azure ML Python SDK 1.0.62 | 製品品質の予測| 
| Regression (Tabular)| [AAzure Machine Learning](Sample/Azure-Machine-Learning-service/Automobile-regression-explainer.ipynb)|Azure ML Python SDK  1.0.76 | 中古車価格の予測| 
| Classification (Image)| [Optuna + Azure Machine Learning](Sample/Azure-Machine-Learning/Mnist-classification-keras-Optuna.ipynb)| Azure ML Python SDK 1.0.65 |  MNIST 文字認識| 
| Tree-structured Parzen Estimator for Classification (Image) | [Neural Network Intelligence](Sample/NNI/MNIST/)| NNI 1.1 | MNIST 文字認識| 



<br/>

## Tuning Algorithm

### [Azure Machine Learning service - Automated ML](./Azure-Machine-Learning-service.md)
### [Optuna](https://optuna.org/)
### [Neural Network Intelligence](https://github.com/microsoft/nni)

<br/>    
  
## Setup
### Azure Machine Learning

Azure Machine Learning が提供している Notebook VM を利用すると、Python SDK が予めインストールされた Jupyter Notebook / JupyterLab を利用することができます。

[Notebook VM 利用手順](https://docs.microsoft.com/ja-JP/azure/machine-learning/service/quickstart-run-cloud-notebook)

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
- [Automated ML Sample Notebook (GitHub)](https://github.com/Azure/MachineLearningNotebooks/tree/master/how-to-use-azureml/automated-machine-learning)
- [Probabilistic Matrix Factorization for Automated Machine Learning
(Microsoft Research Paper)](https://www.microsoft.com/en-us/research/publication/probabilistic-matrix-factorization-for-automated-machine-learning/)


