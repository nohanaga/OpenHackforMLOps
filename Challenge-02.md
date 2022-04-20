# Challenge 2 – クラウドでモデルを作成する

[< Previous Challenge](./Challenge-01.md) - **[Home](../README.md)** - [Next Challenge >](./Challenge-03.md)

## Introduction

この課題の目的は、ローカルで開発していたトレーニングをクラウドにスケールする際の方法論を理解することです。

クラウド上でモデルをトレーニングするための一般的な方法は、[環境](https://docs.microsoft.com/azure/machine-learning/concept-environments)、[コンピューティング ターゲット](https://docs.microsoft.com/azure/machine-learning/concept-compute-target)、[トレーニング Python スクリプト](https://docs.microsoft.com/ja-jp/azure/machine-learning/tutorial-1st-experiment-sdk-train#create-training-scripts)をそれぞれ作成し、実行構成としてパッケージ化します。その後、実行構成をクラウドに送信してトレーニングジョブを起動します。

[Challenge 1](./Challenge-01.md) では 1 つの Notebook 上ですべてが完結しましたが、今回はなぜこうする必要があるのでしょうか。得られるメリットについてチームで議論します。

## Description

機械学習モデルの作成は、ローカル コンピューター上で開始し、後でクラウドベースのクラスターにスケールアウトするのが一般的です。Azure Machine Learning では、トレーニング スクリプトを変更しなくても、さまざまなコンピューティング先でトレーニング スクリプトを実行できます。

ソフトウェアの依存関係の管理は、開発者にとって一般的なタスクです。手動による煩雑なソフトウェア構成を行わずに、モデル作成を再現できることを保証する必要があります。**環境**には、Python パッケージ、環境変数、およびソフトウェア設定を指定します。

## Work
1. 新しいノートブックを作成します。
1. Azure Machine Learning クラウドでトレーニングを実行するための**トレーニング スクリプト**を作成します。今回は事前に提供された `./scripts/train.py` の中身を参照し、前のチャレンジで Notebook セルに記載されているコードと見比べながら差異を明らかにします。
1. 事前に提供された conda 環境仕様 YAML ファイル `arima-env.yml` をロードして**環境**を作成します。
1. 実行するコードの情報と実行のための設定情報をパッケージ化して、クラウド上に送信して実行します。

**注意**: Azure Machine Learning によって Docker イメージをビルドし、指定に従って、そのコンテナー内に Python 環境が作成されます。Docker イメージはキャッシュされて再利用されます。通常、新しい環境での最初の実行時には、イメージがビルドされるため時間がかかります。


## 成功基準
- トレーニング Python スクリプトのコードを理解すること。
- スクリプトの実行構成に環境、コンピューティング ターゲット、トレーニング Python スクリプトをセットし、実験を送信すること。
- リモート環境で ARIMA モデルを作成し、モデルを Pickle 形式で保存すること。


## 学習リソース

 - [Azure Machine Learning 環境とは?](https://docs.microsoft.com/azure/machine-learning/concept-environments)
 - [Azure Machine Learning でソフトウェア環境を作成して使用する](https://docs.microsoft.com/azure/machine-learning/how-to-use-environments)
 - [チュートリアル: 初めての機械学習モデルをトレーニングする](https://docs.microsoft.com/azure/machine-learning/tutorial-1st-experiment-sdk-train)
 - [トレーニングの実行を構成して送信する](https://docs.microsoft.com/azure/machine-learning/how-to-set-up-training-targets)
 