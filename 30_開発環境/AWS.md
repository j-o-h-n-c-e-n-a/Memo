
## AWS Innovate 2019
  http://ds.advg.jp/adpds_deliver/p/iframe?adpds_site=sbbit&adpds_frame=1910a3
* データベース移行
* セキュリティ
* AI/ML
* Serverless
* AWS アンチパターン
* 資格対策：アソシエイト、プロフェッショナル
* SAP教材
* https://budougumi0617.github.io/2019/05/12/pass-aws-solution-architect-associate/

## Black Belt Online Seminar
* AWS Elastic Beanstalk
* AWS Lambda Part1, 2
* Amazon Simple Storage Service (S3)
* Amazon DynamoDB
* Amazon CloudWatch
* Amazon API Gateway

## 出題範囲
### 分野 1: 回復性の高いアーキテクチャを設計する 34% 
* 1.1 信頼性と回復性の高いストレージを選択する。 
* 1.2 AWS サービスを使用した分離機構を設計する方法を定義する。 
* 1.3 多層アーキテクチャソリューションを設計する方法を定義する。 
* 1.4 可用性またはフォルトトレラント性 (あるいはその両方) が高いアーキテクチャを設計する 方法を定義する。 
### 分野 2: パフォーマンスに優れたアーキテクチャを定義する 24% 
* 2.1 パフォーマンスの高いストレージとデータベースを選択する。 
* 2.2 キャッシュを使用してパフォーマンスを向上させる。 
* 2.3 伸縮性と拡張性を備えたソリューションを設計する。 
### 分野 3: セキュアなアプリケーションおよびアーキテクチャを規定する 26% 
* 3.1 アプリケーション層をセキュリティ保護する方法を定義する。 
* 3.2 データをセキュリティ保護する方法を定義する。 
* 3.3 単一の VPC アプリケーション用のネットワークインフラストラクチャーを定義する。 
### 分野 4: コスト最適化アーキテクチャを設計する 10% 
* 4.1 コスト最適化ストレージを設計する方法を定義する。 
* 4.2 コスト最適化コンピューティングを設計する方法を定義する。 
### 分野 5: オペレーショナルエクセレンスを備えたアーキテクチャを定義する 6%
* 5.1 オペレーショナルエクセレンスを実現するソリューションの設計特性を選択する


## AWSの仕組み
## AWSの操作
## アソシエイト試験概要
## AWSの全体像

## IAMの概要
### IAM設計
### IAMグループへのポリシー適用(ハンズオン) ポリシー、グループ、ロール
### IAMケーススタディ：自社組織に必要な権限設定
* IT管理者：フルアクセス＋MFA：管理ポリシーAdministrator
* 運用管理者：運用ツール全般＋開発環境(DevOps)：ツール ELB/EC2/RDS/S3/Auto-Scaling/VPC Config/CloudTrail/CloudWathch
* アプリ開発者：担当しているアプリの開発範囲のみ：ツール ELB/EC2/RDS/S3/Auto-Scaling/VPC 

## EC2の概要
* EC2でWEBサーバーを立ち上げる(ハンズオン)
* Elastic IPの設定(ハンズオン)
* Bashコマンドによる設定
  
* EC2からバッチでS3にデータ保存
* S3のみへアクセスできるポリシーを作成
* EC2にそのポリシーを割り当てる

* EBSの概要
* AMIとsnapshotの活用(ハンズオン)
* EC2のまとめ

## VPCの概要
* VPCとの接続
* VPCの設計
* VPCとサブネットを設定する（ハンズオン）

## VPC関連のハンズオン
* VPC/サブネットにサーバーを設定する(ハンズオン)
* ネットワークACL(ハンズオン)
* VPCエンドポイント(ハンズオン)
* VPC Flow logs
* VPCのまとめ
* 小テスト VPCテスト

## S3の概要
* S3の用途
* S3ハンズオン
  + S3パケットの作成と操作（ハンズオン）
  + S3のバージョン管理（ハンズオン)
  + S3のライフサイクル管理（ハンズオン)
  + EC2からS3ファイルの取得（ハンズオン)
  + AWS CLIの導入（ハンズオン)
* S3プロパティの活用(ハンズオン)
* S3の外部接続
* S3のまとめ
* S3小テスト

## AWSアーキテクチャ設計の基礎
* Well-Architected Framework
* AWSベストプラクティス
* AWS設計ケーススタディ
* Well-Architected Frameworkのまとめ
* 信頼性の確保
* 高可用性の確保
* 信頼性の高いアーキテクチャ構築の実践

## ELBの概要
* ELBによる冗長構成(ハンズオン)
* ELBによる冗長構成(ハンズオン)
* Auto-Scalingの概要
* Auto-Scalingの設定(ハンズオン)
* RDSの概要

## 参考
https://d1.awsstatic.com/training-and-certification/docs-sa-assoc/AWS%20Certified%20Solutions%20Architect%20-%20Associate_Exam%20Sample_v1.5_FINALJP.pdf
https://aws.amazon.com/jp/about-aws/events/aws-innovate/
https://aws.amazon.com/jp/aws-jp-introduction/aws-jp-webinar-service-cut/
https://aws.amazon.com/jp/whitepapers/?whitepapers-main.sort-by=item.additionalFields.sortDate&whitepapers-main.sort-order=desc
https://aws.amazon.com/jp/certification/certified-solutions-architect-associate/

http://aws.clouddesignpattern.org/index.php/メインページ
