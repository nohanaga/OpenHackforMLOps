# OpenHack for MLOps

## Introduction

MLOps は、データサイエンティストやアプリ開発者が ML/AI モデルを本番環境に導入するのを支援するためのツールです。ML ライフサイクルのあらゆるアセットの追跡、バージョン管理、再利用を可能にし、このライフサイクルの管理を効率化するオーケストレーションサービスを提供します。この Hack は、Azure Machine Learning と Azure DevOps/Github Actions を使用して、AI アプリケーションの継続的インテグレーションと継続的デリバリー（CI/CD）パイプラインを構築する方法を理解するのに役立ちます。

この Hack に関わるソリューションは、Adventure Works 社の時系列データセットで構築され、日々のトランザクションを予測するものです。したがって、これは予測タスクですが、CI/CD プロセスはあらゆる AI シナリオに簡単に適用できます。

## Scenario
この OpenHack では、Adventure Works という架空の大規模多国籍製造企業をベースにしています。この企業は、北米、ヨーロッパ、およびアジアのマーケットを対象に、金属製自転車や複合材製自転車の製造および販売を行っています。従業員 290 人の米国ワシントン州ボセルの拠点に加え、自社のマーケット基盤全体にわたって複数の地域販売チームを配置しています。

20XX年、世界的なサプライチェーンの混乱から Adventure Works 社のサプライチェーン担当役員から、AI を使った製品の需要予測プロジェクトの立ち上げが緊急で指示されました。製品に対する需要の急増を正確に予測することで、自社は競争上の優位性を得ることができます。また、予測が改善されると、需要の増加に合わせて生産を拡大できるようになり、不要な在庫を保持するリスクが軽減されます。あなたはこの急ごしらえのプロジェクトに参画することになったデータサイエンティストチームの一人です。

この Hack では、AI モデルを継続的にデプロイし、本番環境で維持するという、企業にとって共通の課題を解決します。真のビジネス価値を得るために、DevOps と CI/CD プロセスを中心とした標準的なエンジニアリングプラクティスを ML ライフサイクルにどのように採用できるかを見ていきます。

あなたのチームには、経験豊富なコーチが割り当てられており、あなたの作業に助言を与え、レビューすることで支援します。しかし、コーチは課題の解決策を提供することはありませんので、チームで課題を解決する必要があります。

チームメンバーは Hack セクションに記載されたタスクを行い、成功基準を満たす必要があります。タスクが完了した時点でコーチに成功基準を満たしていることを説明し、合格すれば次のチャレンジに進むことができます。

課題を解くためのヒントは学習リソース セクションの中に必ずあります。Hack がスタックしてしまったら学習リソースに立ち返ってください。


## 対象者
 - データサイエンティスト
 - ML エンジニア
 - DevOps エンジニア
 - データ/ビジネスアナリスト

## Contents

 - Challenge-00 [前提条件](./Challenge-00.md)
 - Challenge-01 [ローカルでモデルを作成する](./Challenge-01.md)
 - Challenge-02 [クラウドでモデルを作成する](./Challenge-02.md)
 - Challenge-03 [クラウドにモデルをデプロイする](./Challenge-03.md)
 - Challenge-04 [トレーニング・デプロイパイプラインの作成](./Challenge-04.md)
 - Challenge-05 [機械学習パイプラインのトリガーとオーケストレーション](./Challenge-05.md)
 - Challenge-06 [再トレーニングとモデル評価](./Challenge-06.md)
 - Challenge-07 [CLIv2+YAML による MLOps](./Challenge-07.md)

## Additional Contents
この OpenHack は、ETL/ELT などのデータインジェストプロセスによってデータウェアハウスに蓄積されたデータを活用するシナリオです。もし、データインジェストプロセスやデータウェアハウスソリューションの構築を体験されたい場合は「OpenHack for Modern Data Warehousing」の受講をおすすめします。Modern Data Warehousing と MLOps を経験することで、データ分析に関する End-to-End の技術を習得できます。

## Contributed by
 - [microsoft/WhatTheHack 032-MLOpsFromScratch](https://github.com/microsoft/WhatTheHack/tree/master/032-MLOpsFromScratch)
 - [microsoft/MLOpsPython](https://github.com/microsoft/MLOpsPython)
 - [**notanaha/oh4ml-lite**](https://github.com/notanaha/oh4ml-lite)
 - [**tsmatsuz/oh4ml-lite-github-workflow**](https://github.com/tsmatsuz/oh4ml-lite-github-workflow)
 - [**tsmatsuz/oh4ml-lite-cli2**](https://github.com/tsmatsuz/oh4ml-lite-cli2)