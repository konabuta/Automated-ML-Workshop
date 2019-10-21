# Azure Machine Learning service


### [Azure Machine Learning service](https://docs.microsoft.com/ja-JP/azure/machine-learning/service/)
Azure Machine Learning service は、機械学習/深層学習のプロセスを効率的に回すための、オープンな分析プラットフォームです。

<img src="https://docs.microsoft.com/en-us/azure/machine-learning/service/media/concept-azure-machine-learning-architecture/workflow.png" width = "500">   

[こちらのスライド](https://www.slideshare.net/keitaonabuta/azure-machine-learning-service-20199)もご参照ください。
<br/><br/>


## 自動機械学習 Automated Machine Learning
Azure Machine Learning service に含まれる Automated Machine Learning は、**特徴量エンジニアリング & アルゴリズム選択 & パラメータ選択** を全自動で行います。現在は、**表形式データ (Tabular Data)** をサポートしていみあす。

<img src="docs/images/automl.gif"><br/>


自動機械学習で必要な設定は3つです。
- Dataset : 学習に必要なデータの準備
- Optimization Metric: 機械学習の種類、精度指標の指定
- Constrains : 試行するパイプライン数、最大実行時間の指定

<img src="https://docs.microsoft.com/ja-jp/azure/machine-learning/service/media/tutorial-auto-train-models/flow2.png" width=400>
<br/><br/>


## Interpretability SDK

Azure Machine Learning service が提供するモデル解釈ライブラリ。機械学習モデルのモデル全体の説明変数の重要度 (グローバル) や個々の予測値に対する説明変数の重要度 (ローカル) を理解することが可能です。

### 基本コンポーネント

<img src="https://docs.microsoft.com/ja-jp/azure/machine-learning/service/media/machine-learning-interpretability-explainability/interpretability-architecture.png" width=600><br/>

今回は **Tabulear Data (表形式データ)** について説明します。<br/>


### Mimic
**Global Surrogate** に対応する Explainer です。

Azure Machine Learning では、`LightGBM` `Linear Regression` `SGD` `Decision Tree` が利用できます。

```python
from azureml.explain.model.mimic.mimic_explainer import MimicExplainer

# you can use one of the following four interpretable models as a global surrogate to the black box model
from azureml.explain.model.mimic.models.lightgbm_model import LGBMExplainableModel
from azureml.explain.model.mimic.models.linear_model import LinearExplainableModel
from azureml.explain.model.mimic.models.linear_model import SGDExplainableModel
from azureml.explain.model.mimic.models.tree_model import DecisionTreeExplainableModel

explainer = MimicExplainer(model, 
                           x_train, 
                           LGBMExplainableModel, 
                           augment_data=True, 
                           max_num_of_augmentations=10, 
                           features=breast_cancer_data.feature_names, 
                           classes=classes)
```
<br/>

### Feature Permutation
**Permutation Feature Importance** に対応する Explainer です。

```python
from azureml.explain.model.permutation.permutation_importance import PFIExplainer 

# "features" and "classes" fields are optional
explainer = PFIExplainer(model, 
                         features=breast_cancer_data.feature_names, 
                         classes=classes)
```

<br/>

### Tabular Explainer (SHAP)

**SHAP** に対応する Explainer です。
- ツリーベースのモデルの場合は、_SHAP TreeExplainer_ を適用
- DNN モデルの場合は、_SHAP DeepExplainer_ を適用
- BlackBox モデルとして扱う場合は、_SHAP KernelExplainer_ を適用

```python
from azureml.explain.model.tabular_explainer import TabularExplainer
# "features" and "classes" fields are optional
explainer = TabularExplainer(model, 
                             x_train, 
                             features=breast_cancer_data.feature_names, 
                             classes=classes)
```
