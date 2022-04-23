# Challenge 5 – 機械学習パイプラインのトリガーとオーケストレーション

[< Previous Challenge](./Challenge-04.md) - **[Home](./README.md)** - [Next Challenge >](./Challenge-06.md)

## Introduction
機械学習パイプラインの構築によってトレーニング・デプロイコードのモジュール化が進み、品質や生産性が向上してきました。すでに機械学習パイプラインができているので、あとは何らかのイベントや状態変化に応じてトレーニングが自動実行されれば非常に効率的です。トレーニングに用いるデータは継続的に更新されるため、その都度トレーニングを手動で起動するのは面倒です。

この課題の目的は、機械学習パイプラインをプログラムでスケジュールする方法について理解することです。

## Description
機械学習パイプラインは時刻またはファイルシステムの変更に基づいてスケジュールを作成することができます。時刻ベースのスケジュールを使用すると、データの誤差の監視などの日常的なタスクを行うことができます。 変更ベースのスケジュールを使用すると、新しいデータがアップロードされたり古いデータが編集されたりといった、不規則な変更や予期しない変更に対処できます。

また、Azure DevOps や Github Actions を使うことで機械学習パイプラインをより大きな MLOps オーケストレーション パイプラインの一部として呼び出すことができます。

## Hack
すでに他のオーケストレーションツールやバッチアプリケーションをお持ちの場合は、そちらを使ってトリガーしてもかまいません。

1. 新しいノートブックを作成します。
1. [Challenge 4](./Challenge-04.md) で作成したパイプラインID を使用して 5 分間隔で起動する時刻ベースのスケジュールを作成して複数回実行されることを確認します。（実際は月次など適切な更新間隔にセットします）
1. 作成した時刻ベースのパイプラインのスケジュールを無効化します
1. [Challenge 4](./Challenge-04.md) で作成したパイプラインID を使用して特定のフォルダの変更を監視する変更ベースのスケジュールを作成します
1. 作成した変更ベースのパイプラインのスケジュールを無効化します

## 成功基準
- 時刻ベースのスケジュールが 5 分単位で起動されていること。
- 変更ベースのスケジュールが正常に起動されていること。
- パイプラインのスケジュール無効化されていること。


## 学習リソース
 - [機械学習パイプラインをトリガーする](https://docs.microsoft.com/ja-jp/azure/machine-learning/how-to-trigger-published-pipeline)
 - [Azure Pipelinesを使用してデータの準備、機械学習モデルのトレーニング、デプロイ、監視を行う](https://docs.microsoft.com/ja-jp/azure/devops/pipelines/targets/azure-machine-learning?context=azure%2Fmachine-learning%2Fcontext%2Fml-context&view=azure-devops&tabs=classic)
 - [Azure Machine Learning で GitHub Actions を使用する](https://docs.microsoft.com/ja-jp/azure/machine-learning/how-to-github-actions-machine-learning?view=azure-devops)
