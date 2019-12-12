
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
### AWSの操作
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
  2. セキュリティ
  3. 信頼性
  4. パフォーマンス効率
  5. コスト最適化
* AWSベストプラクティス
* AWS設計ケーススタディ
* Well-Architected Frameworkのまとめ
* 信頼性の確保
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
* Auto-Scalingの設定(ハンズオン)
### EBS(Elastic Block Store)
* EBSの概要
  + インスタンスに接続するとOSから認識されるブロックストレージ
* AMIとsnapshotの活用(ハンズオン)
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
### APIGateway
### Strage Gateway/EFS
  Strage Gatewayはオンプレミス環境からの接続用アプライアンス。EFSは分散ストレージ

## 3．セキュリティとネットワーキング
### IAM
  ユーザ権限管理
#### IAMグループへのポリシー適用(ハンズオン) ポリシー、グループ、ロール
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
#### Shield
  DDos対策
#### WAF
#### セキュリティグループ
  ステートフル：ルールで許可された通信の戻りの通信も自動的に許可されます
#### ネットワークACL
  ステートレス：通信の行き（アウトバウンド）と戻り（インバウンド）で、ルールの設定が必要です
### VPCの概要
* VPCとの接続
* VPCの設計
* VPCとサブネットを設定する（ハンズオン）
### VPC関連のハンズオン
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

## 4．データベース
### RDS
### Aurora
### DyanamoDB
### ElastiCache
  インメモリキャッシュ
### Redshift

## 5．管理とガバナンス
### CloudWatch
  モニタリング
### CloudTail
  ユーザの操作履歴
### Config
  リソースの操作履歴
### TrustedAdvisor
  パフォーマンス・セキュリティ最適化
### オペレーション自動化サービス
#### CloudFormation
  テンプレートによるインフラ構築

## 6．アプリケーション統合
### SQS/SNS/SES
### SWF

## 7．分析サービス
### Redshift
### Kinesis
### EMR
### Data Pipeline
### Glue
### Athna
### QuickSight

## 8. 移行とコスト管理のサービス
### 移行のためのサービス
### コスト管理のためのサービス

## 用語集
* AZ(AvailabilityZone)：互いに隣接しているデータセンターの集まり
* エッジローケーション
* ENI(ElasticNecworkInterface)：仮想ネットワークインターフェース
* SLA
* AMI(AmazonMachineImage)
* キーペア
* セキュリティグループ
* プレイスメントグループ
* メトリクスの監視：CloudWatch
  + プッシュ通知：SNS（SimpleNotificationService）
* AutoRecovery：異常検知後のアクション
  + 再起動により別ハードウェアで起動されるため、ハードウェア起因の障害は回避できる可能性が高くなる
* Marketplace：AMIを購入できる

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
