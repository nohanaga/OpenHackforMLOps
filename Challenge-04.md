# Challenge 4 – トレーニング・デプロイパイプラインの作成

[< Previous Challenge](./Challenge-03.md) - **[Home](./README.md)** - [Next Challenge >](./Challenge-05.md)

## Introduction

この課題の目的は、**機械学習パイプライン**を使用して、機械学習ワークフローの構築、最適化、管理を行う方法について理解することです。

**機械学習パイプライン**を使用し、機械学習フェーズをつなげるワークフローを作成して管理します。たとえば、パイプラインには、データ準備、モデル トレーニング、モデル デプロイ、推論/スコアリングの各フェーズが含まれることが考えられます。それぞれのフェーズには、複数のステップを含めることができ、各ステップは、さまざまなコンピューティング先において無人実行することができます。

![aml-pipelines-concept](./images/004.png)

機械学習の各フェーズをパイプライン化することのメリットを[解説](https://docs.microsoft.com/ja-jp/azure/machine-learning/concept-ml-pipelines#key-advantages)を参照しながら理解します。

## Description

Azure Machine Learning のパイプラインの複数のステップを組み合わせて構成して、共有可能で再利用可能な Azure Machine Learning ワークフローであるパイプラインを構築できます。 パイプラインの各ステップは、ステップの内容 (スクリプトと依存関係) に加えて入力とパラメーターが変更されていない場合に、以前の実行結果を再利用できるように構成することができます。

Azure Machine Learning SDK を介して使用できる組み込みステップは多数あります。[azureml.pipeline.steps パッケージ](https://docs.microsoft.com/ja-JP/python/api/azureml-pipeline-steps/azureml.pipeline.steps?view=azure-ml-py)のリファレンス ドキュメントを参照してください。本チャレンジで用いるのは、最も柔軟性の高いクラスである Python スクリプトを実行する `PythonScriptStep` です。これは Python コードを自由にパイプライン化できるため
上図のような機械学習フェーズを自分の好みの粒度でステップ化できます。今回はここから 3 つのフェーズをステップとして切り出してパイプライン化を試みます。

## Hack

1. 新しいノートブックを作成します。
1. パイプラインの手順で必要なデータへのアクセスに使用されるデータストアを設定します。
1. パイプラインの手順間で一時データを渡すために `OutputFileDatasetConfig` オブジェクトを構成します。
1. トレーニングの実行環境を `RunConfiguration` オブジェクトを作成して構成する
1. `train.py` を使用してトレーニングを実行する 1 つ目のパイプライン ステップを作成する
1. `register.py` を作成してモデルを登録する 2 つ目のパイプライン ステップを作成する
1. `deploy.py` を作成してモデルを `Azure Container Instances(ACI)` にデプロイする 3 つ目のパイプライン ステップを作成する
1. パイプライン ステップからパイプラインを構成する
1. 実験でパイプラインを実行する
1. パイプラインを発行する
1. 発行されたパイプラインを実行する

## 成功基準
- 作成したパイプラインのステップが `[train, register, deploy]` の 3 ステップで構成されていること。
- パイプラインエンドポイントにパイプラインがアクティブ状態で登録されていること。
- 発行されたパイプラインが正常に実行されること。


## 学習リソース
 - [Azure Machine Learning パイプラインとは](https://docs.microsoft.com/ja-jp/azure/machine-learning/concept-ml-pipelines)
 - [Why build pipelines?](https://github.com/Azure/MachineLearningNotebooks/tree/master/how-to-use-azureml/machine-learning-pipelines#why-build-pipelines)
 - [Azure Machine Learning SDK で機械学習パイプラインを作成して管理する](https://docs.microsoft.com/ja-jp/azure/machine-learning/how-to-create-machine-learning-pipelines)
 - [機械学習パイプラインを発行して追跡する](https://docs.microsoft.com/ja-jp/azure/machine-learning/how-to-deploy-pipelines)
 