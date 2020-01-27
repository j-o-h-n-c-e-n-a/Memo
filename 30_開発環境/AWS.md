
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

## AWSアカウント登録後に対応すること
1. ルートアカウントの利用を停止する
2. 多要素認証を有効化する
3. AWS Cloud Trail を有効化する
4. AWSの請求レポートを有効化する

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

## 1．AWS概要
### AWSの仕組み
  * VPC
    + Route53：DNS
    + ELB
      - EC2 → S3 
      - EC2 → RDS
  * マネージド型とアンマネージド型サービス
#### グローバルインフラ構成
* リージョン
  + AZ
    - エッジローケーション
#### リージョン間連携
* 
* 
* 
* 
* 
#### エッジロケーション
### AWSの操作
* マネジメントコンソール
* インスタンス操作（SSH等）
* AWS CLI 操作
### アソシエイト試験概要
### AWSの全体像
### サポート体制と料金プラン
  * サポート：ベーシック/開発者/ビジネス/エンタープライズ
  * プラン毎の制限
    + VPC数
    + IAMユーザ数
    + TrustedAdvisorの機能
### AWSアーキテクチャ設計の基礎
  * Well-Architected Framework
    1. 運用上の優秀性
    2. 安全性：セキュリティ
    3. 信頼性
    4. パフォーマンス効率
    5. コスト最適化
  * AWSベストプラクティス
  * AWS設計ケーススタディ
  * Well-Architected Frameworkのまとめ
  * 信頼性の確保
    + ELB/AutoScaling/RDS
  * 高可用性の確保
  * 信頼性の高いアーキテクチャ構築の実践

## 2．コンピューティングとストレージ
### EC2の概要
  コンピューティング能力の提供
  * EC2でWEBサーバーを立ち上げる(ハンズオン)
  * Elastic IPの設定(ハンズオン)
    + 再起動してもIPアドレスが維持される
    + 他には、パブリックとプライベートがある
    + 利用していない場合に課金される
  * Bashコマンドによる設定
    + 外部DNSホスト名
    + ユーザ名とメタデータ
  * ハードウェア占有インスタンスとDedicatedHosts
    + 専用ハードウェアが提供される
    + ハードウェア占有インスタンスはホストコンピューターを指定できないが、DedicatedHostsはできる
    + 課金単位も異なる
### Auto Scaling
  * Auto-Scalingの概要
    + Auto-Scalingグループ
  * Auto-Scalingの設定(ハンズオン)
### EBS(Elastic Block Store)
  * EBSの概要
    + インスタンスに接続するとOSから認識されるブロックストレージ
  * AMIとSnapshotの活用(ハンズオン)
    + AMI(AmazonMachineImage)
      - AWSの加増ディスクのサービスであるEBSのスナップショットにルートボリュームの付加情報を追加したもの  
  * EC2のまとめ
    + 支払方法：通常はオンデマンドだが、リザーブドやスポットといった割引利用の方法もある
### S3(Simple Storage Service)の概要
  * S3の用途
    + EC2からバッチでS3にデータ保存
    + S3のみへアクセスできるポリシーを作成
    + EC2にそのポリシーを割り当てる
  * S3ハンズオン
    + S3パケットの作成と操作（ハンズオン）
    + S3のバージョン管理（ハンズオン)
    + S3のライフサイクル管理（ハンズオン)
    + EC2からS3ファイルの取得（ハンズオン)
    + AWS CLIの導入（ハンズオン)
  * S3プロパティの活用(ハンズオン)
  * S3の外部接続
  * S3のまとめ
    + バージョニング
    + ライフサイクル
    + 静的ウェブホスティング
    + 暗号化
  * S3小テスト
### Glacier
  低コストアーカイブ向けストレージ
### ECS/EKS/Fargate
  コンテナに関するサービス
### Lambda
  サーバーレスでマネージドな
### APIGateway
  
### Strage Gateway/EFS
  Strage Gatewayはオンプレミス環境からの接続用アプライアンス。EFSは分散ストレージ

## 3．セキュリティとネットワーキング
### IAM
  ユーザ権限管理
#### IAMグループへのポリシー適用(ハンズオン) ポリシー、グループ、ロール
* ユーザー
  + ルートユーザー：何でもできる。漏洩防止のために普段は使用しない。MFAを設定しておく。
  + Administrator
* グループ
  + 認証方式
    - MFA：多要素認証
* ポリシー
  + 管理ポリシー
    - AWS管理ポリシー
    - カスタム
  + インラインポリシー
* ロール
#### IAMケーススタディ：自社組織に必要な権限設定
  * IT管理者
    + フルアクセス＋MFA：管理ポリシーAdministrator
  * 運用管理者
    + 運用ツール全般＋開発環境(DevOps)
    + ツール ELB/EC2/RDS/S3/Auto-Scaling/VPC Config/CloudTrail/CloudWathch
  * アプリ開発者
    + 担当しているアプリの開発範囲のみ
    + ツール ELB/EC2/RDS/S3/Auto-Scaling/VPC
### セキュリティサービス
#### 責任共有モデル
  セキュリティに対してAWSとユーザーとで責任分解して対応する責任共有モデルとなっている
#### Shield
  DDos対策
#### WAF
#### セキュリティグループ
  ステートフル：ルールで許可された通信の戻りの通信も自動的に許可されます
#### ネットワークACL
  ステートレス：通信の行き（アウトバウンド）と戻り（インバウンド）で、ルールの設定が必要です
### VPCの概要
### VPCとの接続
### VPCの設計
### VPC関連のハンズオン
  * VPCとサブネットを設定する（ハンズオン）
  * VPC/サブネットにサーバーを設定する(ハンズオン)
  * ネットワークACL(ハンズオン)
  * VPCエンドポイント(ハンズオン)
  * VPC Flow logs
  * VPCのまとめ
  * 小テスト VPCテスト
### ELB(Elastic Load Balancing)の概要
  * ELBによる冗長構成(ハンズオン)
  * ELBによる冗長構成(ハンズオン)  
### Route53
  フルマネージドのネームサーバー、トラフィックルーティング、ヘルスチェックとDNSフェイルオーバー
#### ネームサーバー
  * ルートを起点にすべてのFQDNを探索できるように構成された分散データベース
  * NSレコードとGlueによる親ゾーンから子ゾーンへの権限移譲の仕組み
  * レコードを構成する5つの要素
    + NAME
    + TTL
    + CLASS
    + TYPE
    + RDATA
  * 用途に応じたリソースレコードタイプ
  * CNAMEレコードタイプの制約とZoneApex
  * 正常応答のキャッシュ、不存在応答のネガティブキャッシュ
### Direct Connect
  オンプレとの専用線
  * 論理接続
    + プライベートとパブリックがある
  * Direct Connect Gateway
    + 複数のリージョンをまたがるVPCのリソース同志はDirectConnectGateway経由で通信できない
    + オンプレからオンプレ、VPCからVPCへの折り返し通信は不可
  * パートナー経由
  * 可用性
    + デュアルロケーション（リージョンを分散：東阪）
### CloudFront
  コンテンツ配信（CDN）ネットワーク
  * コンテンツのキャッシュ
  * Webコンテンツや動画などを分散ネットワーク上で配信が可能

## 4．データベース
### RDS
#### リードレプリカ
#### ストレージタイプ
  汎用SSD、プロビジョンドIOPS、Magnetic
#### バックアップ
* SQL Server DB インスタンスでは SQL Server データベースのミラーリング (DBM) が使用される
### Aurora
  リレーショナルデータベース。他のRDSに比較して高いスループットを提供している。
#### ストレージ構成
#### フェイルオーバーの仕組み
### DyanamoDB
  key-value形式のデータベース（NoSQL）
  * 複数のAZに保存される
  * テーブルの読み書き容量を制御
    + プロビジョニングされたスループット容量
### ElastiCache
  インメモリキャッシュ
### Redshift
  列指向データベース

## 5．管理とガバナンス
### CloudWatch
  AWSリソースとAWSで実行されるアプリケーションの監視サービス
#### Logs
  AWSのログ収集サービス
#### Events
  AWSリソースの変更をトリガーとしてアクションを実行するサービス
### CloudTrail
  AWSサービスの操作を監視し、AWSアカウントのガバナンス／コンプライアンス/運用とリスクの監査を実施するためのサービス
### Config
  リソースの操作履歴
  * ルール
  * ダッシュボード
  * アグリゲータ
### TrustedAdvisor
  パフォーマンス・セキュリティ最適化
#### チェック項目
  * コスト最適化
  * パフォーマンス
  * セキュリティ
  * 耐障害性
### オペレーション自動化サービス
#### CloudFormation
  テンプレートによるインフラ構築
  * スタック
    + デプロイする単位。複数のスタックを組み合わせて1つの環境を作成することが可能
  * デザイナー
    + デプロイするAWSリソースとその設定情報を記載したテンプレートを作成するツール
#### Beanstalk
#### AWS OpsWorks

## 6．アプリケーション統合
### SQS
  メッセージキューサービス
### SNS
  通知サービス
### SES
  メール通知サービス
### SWF
  ワークフローサービス

## 7．分析サービス
### Redshift
  * 分析に使用されるが、S3のデータを分析できない
### Kinesis
  リアルタイムに大量のストリーミングで^多を収集する一連のサービス群です。
1. Data Streams 
2. Data Firehose
3. Data Analytics
4. Video Streams
### EMR
  Hadoop のマネージドサービス
### Data Pipeline
  異なるAWSコンピューティングとストレージサービス間でデータを確実に処理および移動するのに役立つウェブサービス
### Glue
  完全に管理された抽出、変換、および読み込み（ETL）サービス
  * S3のデータ分析には使用しない
### Athna
  標準SQLを使用してAmazon S3のデータを簡単に分析できるインタラクティブなクエリサービス。
### QuickSight
  RedShiftなどのデータウェアハウスやS3、Athena、EDSなどのAWSのデータソースに接続できるBIツール

## 8. 移行とコスト管理のサービス
### 移行のためのサービス
### コスト管理のためのサービス

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

## 機械学習
### SageMaker

## 参考
### AWS活用資料集
https://d1.awsstatic.com/training-and-certification/docs-sa-assoc/AWS%20Certified%20Solutions%20Architect%20-%20Associate_Exam%20Sample_v1.5_FINALJP.pdf
https://aws.amazon.com/jp/about-aws/events/aws-innovate/
https://aws.amazon.com/jp/aws-jp-introduction/aws-jp-webinar-service-cut/
https://aws.amazon.com/jp/whitepapers/?whitepapers-main.sort-by=item.additionalFields.sortDate&whitepapers-main.sort-order=desc
https://aws.amazon.com/jp/certification/certified-solutions-architect-associate/
### その他
https://dev.classmethod.jp/cloud/aws/2018-aws-re-entering-security/
http://aws.clouddesignpattern.org/index.php/メインページ
https://aws-exam.net/saa/
https://dev.classmethod.jp/cloud/aws/aws-summary-2020/
https://awsjp.com/

### Qwiklabs
* [](https://dev.classmethod.jp/cloud/aws/saa-exam-usecase-training-in-qwiklabs/)
* [](https://dev.classmethod.jp/cloud/aws/mesoko-r53-cdn/)