## NNIによる MNIST文字認識モデルのハイパーパラメータチューニング

## 必要な設定
1. ハイパーパラメータ探索空間定義ファイル
2. トレーニング Pythonスクリプト
3. 学習設定ファイル



### 1. ハイパーパラメータ探索空間定義ファイル [search_space.json](./search_space.json)

ハイパーパラメータの探索空間を定義します。ここでは、ドロップアウト率 (dropout_rate)、学習率 (learning_rate) などを指定しています。 

```json
{
    "dropout_rate":{"_type":"uniform","_value":[0.5, 0.9]},
    "conv_size":{"_type":"choice","_value":[2,3,5,7]},
    "hidden_size":{"_type":"choice","_value":[124, 512, 1024]},
    "batch_size": {"_type":"choice", "_value": [1, 4, 8, 16, 32]},
    "learning_rate":{"_type":"choice","_value":[0.0001, 0.001, 0.01, 0.1]}
}
```


### 2. トレーニング Pythonスクリプト [mnist.py](./mnist.py)

python でのトレーニングスクリプトを作成します。

NNI に対応するために、下記の対応が必要です (抜粋)。


```python
# NNI ライブラリのインポート
import nni
```

```python
# NNI Tuner からハイパーパラメータの受け取り
tuner_params = nni.get_next_parameter()
```

```python
# エポック毎の精度の記録
nni.report_intermediate_result(test_acc)
```

### 3. 学習設定ファイル [config.yml](./config.yml)

機械学習モデル学習の設定をファイルで定義します。

※ 詳細は、ドキュメント [Experiment config reference](https://nni.readthedocs.io/en/latest/Tutorial/ExperimentConfig.html#Experiment-config-reference) を参照ください。

```yaml
authorName: default
experimentName: example_mnist
trialConcurrency: 1
maxExecDuration: 1h
maxTrialNum: 10
#choice: local, remote, pai
trainingServicePlatform: local
searchSpacePath: search_space.json
#choice: true, false
useAnnotation: false
tuner:
  #choice: TPE, Random, Anneal, Evolution, BatchTuner, MetisTuner, GPTuner
  #SMAC (SMAC should be installed through nnictl)
  builtinTunerName: TPE
  classArgs:
    #choice: maximize, minimize
    optimize_mode: maximize
trial:
  command: python3 mnist.py
  codeDir: .
  gpuNum: 0
  ```



## 実行

Terminal から実行します。

```shell
cd Sample/NNI/MNIST
nnictl create --config config.yml
```

Web UI (default : http://127.0.0.1:8080) から結果を確認できます。

<img src="../../../docs/images/nni-mnist-webui.gif">
