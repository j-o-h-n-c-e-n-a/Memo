## 概要説明
* 責任共有モデル
* 基本サービス
* 監視サービス
* セキュリティサービス
* コストとアカウントについて

## AWSアカウント登録後に対応すること
1. ルートアカウントの利用を停止する
2. 多要素認証を有効化する
3. AWS Cloud Trail を有効化する
4. AWSの請求レポートを有効化する
* 複数アカウントが必要な場合、Organizations も

## ハンズオン - トレーニング
### VPC関連
  * VPCとサブネットを設定する
  * VPC/サブネットにサーバーを設定する
  * ネットワークACL
  * VPCエンドポイント
### EC2関連
  * WEBサーバーを立ち上げる
  * Elastic IPの設定
  * Auto-Scalingの設定
### EBS(Elastic Block Store)
  * AMIとSnapshotの活用
### ELB
  * 冗長構成
### S3(Simple Storage Service)
  * 基本操作
    + S3パケットの作成と操作
    + S3のバージョン管理
    + S3のライフサイクル管理
    + EC2からS3ファイルの取得
    + AWS CLIの導入
  * S3プロパティの活用
#### IAMグループへのポリシー適用 
* ポリシー、グループ、ロール
### Trusted Advisor Personal Health Dashboard
### CloudWatch
### Route53
### WAF
### Cloudformation
### Sagemaker
* 機械学習基盤について
* 機械学習の流れ
* 事例紹介
### Glue
    完全に管理された抽出、変換、および読み込み（ETL）サービス
### Lambda

### CI/CD
  いかにお客様に早く価値を提供することができるのか？を改善する活動
#### CodePipeline
* Commit
* Build
* Deploy

### サービス活用
* Web API 構築編
* 音声文字起こし & 感情分析パイプライン構築編


## 用語集
 * ADFS
  + ADにサインインした後に生成されるトークンに基づいてWebアプリケーションへのログインに利用可能なトークンを生成することでID連携を行うサービス
 * ADS
  + オンプレミス上で実行されているアプリケーションを自動的に検出し、システムの一覧、依存関係、性能情報を収集するサービス
 * Athena
  + S3のデータに対してテーブル定義を作り、標準的なSQLを直接発行できるAWSのサービス
 * AutoRecovery：異常検知後のアクション
  + 再起動により別ハードウェアで起動されるため、ハードウェア起因の障害は回避できる可能性が高くなる
 * AZ(AvailabilityZone)
  + 互いに隣接しているデータセンターの集まり
 * ENI(ElasticNecworkInterface)
  + 仮想ネットワークインターフェース
 * Marketplace：AMIを購入できる
 * SLA
 * エッジローケーション
 * キーペア
 * セキュリティグループ
 * プレイスメントグループ
 * メトリクスの監視：CloudWatch
  + プッシュ通知：SNS（SimpleNotificationService）
 * Cognito
  + モバイル管理サービス：Firebaseのようなもの？
 * Device Farm
  + モバイルデバイス管理：MDMのようなもの？

## 参考
### AWS活用資料集
* https://aws.amazon.com/jp/about-aws/events/aws-innovate/
* https://aws.amazon.com/jp/aws-jp-introduction/aws-jp-webinar-service-cut/
* https://aws.amazon.com/jp/certification/certified-solutions-architect-associate/
* https://aws.amazon.com/jp/whitepapers/
### その他
* http://aws.clouddesignpattern.org/index.php/メインページ
* https://dev.classmethod.jp/articles/aws-study-kaji/
* https://awsjp.com/
* https://aws-exam.net/saa/
* https://dev.classmethod.jp/cloud/aws/2018-aws-re-entering-security/
* https://dev.classmethod.jp/cloud/aws/aws-summary-2020/
* https://dev.classmethod.jp/articles/lesson-of-aws-certification-saa-taking-2-times/

### Qwiklabs
* [1](https://dev.classmethod.jp/cloud/aws/saa-exam-usecase-training-in-qwiklabs/)
* [2](https://dev.classmethod.jp/cloud/aws/mesoko-r53-cdn/)

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
  * Route53
  * ELB

#devaxconnect