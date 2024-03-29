# 試験概要
## 第1分野: 複雑な組織に対応するソリューションの設計タスクステートメント
### 1: ネットワーク接続戦略を設計する。
#### 対象知識:
* AWS のグローバルインフラストラクチャ
* AWS ネットワークの概念(Amazon VPC、AWS Direct Connect、AWS VPN、推移的ルーティング、AWS コンテナサービスなど)
* ハイブリッドDNS の概念(Amazon Route 53 Resolver、オンプレミスDNS 統合など)
* ネットワークセグメンテーション(サブネット、IP アドレス指定、VPC 間の接続など)
* ネットワークトラフィックモニタリング
#### 対象スキル:
* 複数のVPC の接続オプションを評価する
* オンプレミス、コロケーション、クラウド統合の接続オプションを評価する
* ネットワークとレイテンシーの要件に基づいてAWS リージョンとアベイラビリティーゾーンを選択する
* AWS ツールを使用してトラフィックフローの問題を解決する
* サービス統合のサービスエンドポイントを活用するタスクステートメント
### 2: セキュリティコントロールを規定する。
#### 対象知識:
* AWS Identity and Access Management (IAM) とAWS Single Sign-On
* ルートテーブル、セキュリティグループ、ネットワークACL
* 暗号化キーと証明書管理(AWS Key Management Service [AWS KMS]、AWS Certificate Manager [ACM] など)
* AWS のセキュリティ、アイデンティティ、コンプライアンスのツール(AWS CloudTrail、AWS Identity and Access Management Access Analyzer、AWS Security Hub、Amazon Inspector など) 
#### 対象スキル:
* クロスアカウントアクセス管理を評価する
* サードパーティーID プロバイダーと統合する
* 保存中のデータと転送中のデータに対する暗号化戦略を導入する
* セキュリティイベントの通知と監査を一元化するための戦略を策定する
### 3: 信頼性と耐障害性に優れたアーキテクチャを設計する。
#### 対象知識:
* 目標復旧時間(RTO) と目標復旧時点(RPO)
* 災害対策戦略(AWS Elastic Disaster Recovery [CloudEndure Disaster Recovery]、パイロットライト、ウォームスタンバイ、マルチサイトの使用など) 
* データのバックアップと復元
#### 対象スキル:
* RTO およびRPO 要件に基づいて災害対策ソリューションを設計する
* 障害から自動的に復旧するアーキテクチャを実装する
* スケールアップとスケールアウトのオプションを考慮し、最適なアーキテクチャを策定する
* 効果的なバックアップ/復元の戦略を設計する
### タスクステートメント4: マルチアカウントAWS 環境を設計する。
#### 対象知識:
* AWS Organizations とAWS Control Tower
* マルチアカウントイベント通知
* 環境間のAWS リソース共有
#### 対象スキル:
* 組織の要件に最も適したアカウント構造を評価する
* 一元的なログ記録とイベント通知の戦略を推奨する
* マルチアカウントガバナンスモデルを開発する
### タスクステートメント5: コスト最適化と可視化の戦略を決定する。
#### 対象知識:
* AWS のコストおよび使用状況のモニタリングツール(AWS Trusted Advisor、AWS Pricing Calculator、AWS Cost Explorer、AWS Budgets など)
* AWS 購入オプション(リザーブドインスタンス、Savings Plans、スポットインスタンスなど)
* サイズ適正化のためのAWS 可視化ツール(AWS Compute Optimizer、Amazon S3 Storage Lens など)
#### 対象スキル:
* AWS ツールでコストと使用量をモニタリングする
* コストを事業単位にマッピングする効果的なタグ付け戦略を策定する
* 購入オプションがコストとパフォーマンスに与える影響を理解する

## 第2分野: 新しいソリューションのための設計タスクステートメント
### 1: ビジネス要件を満たす導入戦略を設計する。
#### 対象知識:
* Infrastructure as Code (IaC) (AWS CloudFormation など) 
* 継続的インテグレーション/継続的デリバリー(CI/CD)
* 変更管理プロセス
* 構成管理ツール(AWS Systems Manager など) 
#### 対象スキル:
* 新しいサービスや機能のためのアプリケーションまたはアップグレードパスを決定する
* デプロイ戦略を策定し、適切なロールバックメカニズムを実装するためのサービスを選定する
* 必要に応じてマネージドサービスを採用し、インフラストラクチャのプロビジョニングやパッチ適用のオーバーヘッドを削減する
* 複雑な開発タスクとデプロイタスクをAWS にまかせ、高度なテクノロジーを利用できるようにする
### 2: 事業継続性を確保するソリューションを設計する。
#### 対象知識:
* AWS のグローバルインフラストラクチャ
* AWS ネットワークの概念(Route 53、ルーティングメソッドなど) 
* RTO とRPO
* 災害対策シナリオ(バックアップと復元、パイロットライト、ウォームスタンバイ、マルチサイトなど) 
* AWS の災害対策ソリューション
#### 対象スキル: 
* 災害対策ソリューションを構成する
* データとデータベースのレプリケーションを構成する
* 災害対策テストを実行する
* 自動化され、費用対効果が高く、複数のアベイラビリティーゾーンおよび/またはAWS リージョンをまたいで事業継続性をサポートするバックアップソリューションのアーキテクチャを設計する
* 障害時もアプリケーションとインフラストラクチャの可用性を維持するアーキテクチャを設計する
* プロセスとコンポーネントを活用して一元的なモニタリングを行い、システム障害からプロアクティブに復旧する
### 3: 要件に基づいてセキュリティコントロールを決定する。
#### 対象知識:
* IAM
* ルートテーブル、セキュリティグループ、ネットワークACL 
* 保管中のデータと転送中のデータの暗号化オプション
* AWS サービスエンドポイント
* 認証情報管理サービス
* AWS マネージドセキュリティサービス(AWS Shield、AWS WAF、Amazon GuardDuty、AWS Security Hub など)
#### 対象スキル:
* 最小権限アクセスの原則に従ったIAM ユーザーとIAM ロールを指定する
* セキュリティグループルールとネットワークACL ルールを使用したインバウンドおよびアウトバウンドのネットワークフローを指定する
* 大規模なウェブアプリケーションの攻撃対策戦略を策定する
* 保管中のデータと転送中のデータの暗号化戦略を策定する
* サービス統合のサービスエンドポイントを指定する
* 組織の規格への準拠を維持するためのパッチ管理戦略を策定する
### 4: 信頼性の要件を満たす戦略を策定する。
#### 対象知識:
* AWS のグローバルインフラストラクチャ
* AWS ストレージサービスとレプリケーション戦略(Amazon S3、Amazon RDS、Amazon ElastiCache など)
* マルチAZ およびマルチリージョンアーキテクチャ
* オートスケーリングのポリシーとイベント
* アプリケーション統合(Amazon Simple Notification Service [Amazon SNS]、Amazon Simple Queue Service [Amazon SQS]、AWS Step Functions など)
* サービスクォータと上限
#### 対象スキル:
* ビジネス要件に基づいて可用性の高いアプリケーション環境を設計する
* 高度な技術を活用して障害に備えて設計し、シームレスなシステム回復性を確保する
* 疎結合依存関係を実装する
* 高可用性アーキテクチャを運用、保守する(アプリケーションのフェイルオーバー、データベースのフェイルオーバーなど)
* AWS マネージドサービスを活用して高可用性を実現する
* DNS ルーティングポリシーを実装する(Route 53 のレイテンシールーティングポリシー、位置情報ルーティング、シンプルルーティングなど)
### 5: パフォーマンス目標を満たすソリューションを設計する。
#### 対象知識:
* パフォーマンスモニタリングテクノロジー
* AWS のストレージオプション
* インスタンスファミリーとユースケース
* 目的別データベース
#### 対象スキル:
* さまざまなアクセスパターンに対応した大規模アプリケーションアーキテクチャを設計する
* ビジネス目標に合わせて伸縮自在なアーキテクチャを設計する
* キャッシュ、バッファリング、レプリカでパフォーマンス目標を達成するための設計パターンを適用する
* 必要なタスクに特化したサービスを選択するためのプロセス方法論を策定する
* サイズ適正化戦略を設計するタスクステートメント
### 6: ソリューションの目標と目的を達成するためのコスト最適化戦略を決定する。
#### 対象知識: 
* AWS のコストおよび使用状況のモニタリングツール(Cost Explorer、Trusted Advisor、AWS Pricing Calculator など)  
* 料金モデル(リザーブドインスタンス、Savings Plans など)
* ストレージ階層化
* データ転送コスト
* AWS が提供するマネージドサービス
#### 対象スキル:
* インフラストラクチャを選択し、適切なサイズにする機会を特定し、リソースの費用対効果を上げる
* 適切な価格モデルを特定する
* データ転送のモデル化とサービスの選択を行い、データ転送コストを削減する
* 経費支出と使用状況を認識するための戦略を策定し、制御を実装する

## 第3分野: 既存のソリューションの継続的な改善
### 1: 全体的な運用上の優秀性を高めるための戦略を作成する。
#### 対象知識:
* アラートと自動修復の戦略
* 災害対策計画
* モニタリングとログ記録のソリューション(Amazon CloudWatch など)
* CI/CD パイプラインとデプロイ戦略(ブルー/グリーン、オールアットワンス、ローリングなど)
* 構成管理ツール(Systems Manager など)
#### 対象スキル:
* 最も適したログ記録とモニタリング戦略を決定する
* 改善の機会を特定する目的で現在のデプロイプロセスを評価する
* ソリューションスタック内の自動化の機会に優先順位を付ける
* 構成管理を自動化を可能にするために適切なAWS ソリューションを提案する
* 復旧アクションの理解をサポートし、演習するための障害シナリオアクティビティを設計する
### 2: セキュリティを向上させるための戦略を決定する。
#### 対象知識:
* データ保持、データ機密性、データ規制要件
* モニタリングと修正の自動化戦略(AWS Config ルールなど)
* シークレット管理(Systems Manager、AWS Secrets Manager など)
* 最小権限アクセスの原則
* セキュリティ固有のAWS ソリューション
* パッチ適用のプラクティス
* バックアップのプラクティスと方法
#### 対象スキル:
* シークレットと認証情報を安全に管理するための戦略を評価する
* 最小権限アクセスについて環境を監査する
* 実装されたソリューションを見直し、すべてのレイヤーでセキュリティを確保する
* ユーザーとサービスの包括的なトレーサビリティを見直す
* 脆弱性の検出に対する自動対応に優先順位を付ける
* パッチと更新のプロセスを設計し、実装する
* バックアッププロセスを設計し、実装する
* 修復手法を採用する
### 3: パフォーマンスを改善するための戦略を決定する。
#### 対象知識:
* 高パフォーマンスのシステムアーキテクチャ(オートスケーリング、インスタンスフリート、プレイスメントグループなど) 
* グローバルサービス(AWS Global Accelerator、Amazon CloudFront、エッジコンピューティングサービスなど)
* モニタリングツールのセットとサービス(CloudWatch など)
* サービスレベルアグリーメント(SLA) と重要業績評価指標(KPI)
#### 対象スキル:
* ビジネス要件を測定可能な指標に変換する
* 修復ソリューション候補をテストし、提案を行う
* 新しいテクノロジーとマネージドサービスを導入する機会を提案する
* ソリューションを評価し、要件に基づいてサイズの適正化を行う
* パフォーマンスのボトルネックを特定し、調査する
### 4: 信頼性を向上させるための戦略を決定する。
#### 対象知識:
* AWS のグローバルインフラストラクチャ
* データレプリケーション方法
* スケーリング方法論(ロードバランシング、オートスケーリングなど)
* 高可用性と回復力
* 災害対策の方法とツール
* サービスクォータと上限
#### 対象スキル:
* アプリケーションの利用増加と使用傾向を把握する
* 既存のアーキテクチャを評価し、信頼性が不十分な領域を特定する
* 単一障害点を修正する
* データレプリケーション、自己修復、伸縮自在な機能とサービスを実現する
### 5: コスト最適化の機会を特定する。
#### 対象知識:
* コスト意識の高いアーキテクチャを選択する(スポットインスタンスの利用、スケーリングポリシー、リソースのサイズ適正化など) 
* 価格モデルの採用(リザーブドインスタンス、Savings Plans など)
* ネットワークとデータ転送のコスト
* コスト管理、アラート、レポート作成
#### 対象スキル:
* 使用状況レポートを分析し、使用率の低いリソースと使用率の高いリソースを特定する
* AWS ソリューションを活用して使用されていないリソースを特定する
* 予想される使用パターンに基づいて課金アラームを設計する
* AWS Cost and Usage Report をきめ細かく調査する
* コスト配分とレポート作成にタグ付けを活用する

## 第4分野: ワークロードの移行とモダナイゼーションの加速
### 1: 移行が可能な既存のワークロードとプロセスを選択する。
#### 対象知識:
* 移行アセスメントおよび追跡ツール(AWS Migration Hub など)
* ポートフォリオアセスメント
* アセットプランニング
* ワークロードの優先順位付けと移行(ウェーブプランニングなど)
#### 対象スキル:
* アプリケーション移行アセスメントを実施する
* 7 つの一般的な移行戦略(7R) に従ってアプリケーションを評価する
* 総保有コスト(TCO) を評価する
### 2: 既存ワークロードの最適な移行アプローチを決定する。
#### 対象知識:
* データ移行のオプションとツール(AWS DataSync、AWS Transfer Family、AWS Snow Family、S3 Transfer Acceleration など)
* アプリケーション移行ツール(AWS Application Discovery Service、AWS Application Migration Service [CloudEndure Migration]、AWS Server Migration Service [AWS SMS] など)
* AWS ネットワークサービスとDNS (Direct Connect、AWS Site-to  -Site VPN、Route 53 など) 
* アイデンティティサービス(AWS SSO、AWS Directory Service など)
* データベース移行ツール(AWS Database Migration Service [AWS DMS]、AWS Schema Conversion Tool [AWS SCT] など)
* ガバナンスツール(AWS Control Tower、Organizationsなど)
#### 対象スキル:
* 適切なデータベース転送メカニズムを選択する
* 適切なアプリケーション転送メカニズムを選択する
* 適切なデータ転送サービスと移行戦略を選択する
* 移行ツールに適したセキュリティ方法を適用する
* 適切なガバナンスモデルを選択する
### 3: 既存ワークロードの新しいアーキテクチャを決定する。
#### 対象知識:
* コンピューティングサービス(Amazon EC2、AWS Elastic Beanstalk など)
* コンテナ(Amazon Elastic Container Service [Amazon ECS]、Amazon Elastic Kubernetes Service [Amazon EKS]、AWS Fargate, Amazon Elastic Container Registry [Amazon ECR] など)
* AWS ストレージサービス(Amazon Elastic Block Store [Amazon EBS]、Amazon Elastic File System [Amazon EFS]、Amazon FSx、Amazon S3、Volume Gateway など) 
* データベース(Amazon DynamoDB、Amazon OpenSearch Service [Amazon Elasticsearch Service]、Amazon RDS、Amazon EC2 のセルフマネージド型データベースなど) 
#### 対象スキル:
* 適切なコンピューティングプラットフォームを選択する
* 適切なコンテナホスティングプラットフォームを選択する
* 適切なストレージサービスを選択する
* 適切なデータベースプラットフォームを選択する
### 4: モダナイゼーションと機能強化の機会を決定する。
#### 対象知識:
* サーバーレスコンピューティングサービス(AWS Lambda など)
* コンテナ(Amazon ECS、Amazon EKS、AWS Fargate など)
* AWS ストレージサービス(Amazon S3、Amazon EFS など) 
* 目的別データベース(DynamoDB, Amazon Aurora Serverless、ElastiCache など)
* 統合サービス(Amazon SQS、Amazon SNS、Amazon EventBridge [Amazon CloudWatch Events]、Step Functions など)
#### 対象スキル:
* アプリケーションコンポーネントを切り離す機会を特定する
* サーバーレスソリューションの機会を特定する
* コンテナに適したサービスを選択する
* 目的別データベースの機会を特定する
* 適切なアプリケーション統合サービスを選択する

## Link
* [AWS Certified Solutions Architect – Professional](https://explore.skillbuilder.aws/learn/course/11229/play/41694/exam-readiness-aws-certified-solutions-architect-professional-japanese-ri-ben-yu-shi-xie-ban-312)
* [ランクアップガイド](https://training.resources.awscloud.com/get-aws-certified-solutions-architect-professional-japanese/ramp-up-guide-architect-jp-2trkd728e2a8-d249-4901-a829-1cb78ce13599scchannelel)
* [公式練習問題](https://training.resources.awscloud.com/get-aws-certified-solutions-architect-professional-japanese/users-guide-aws-cert-official-question-jp)

## 試験の対象となる主要なツール、テクノロジー、概念
* コンピューティング
* コスト管理
* データベース
* 災害対策
* 高可用性
* マネジメントとガバナンス
* マイクロサービスとコンポーネントのデカップリング
* 移行とデータの転送
* ネットワーク、接続、コンテンツ配信
* セキュリティ
* サーバーレスの設計原則
* ストレージ
## 範囲内のAWS のサービスと機能
### 分析:
* Amazon Athena
* AWS Data Exchange
* AWS Data Pipeline
* Amazon EMR
* AWS Glue
* Amazon Kinesis Data Analytics
* Amazon Kinesis Data Firehose
* Amazon Kinesis Data Streams
* AWS Lake Formation
* Amazon Managed Streaming for Apache Kafka (Amazon MSK)
* Amazon OpenSearch Service
* Amazon QuickSight
### アプリケーション統合:
* Amazon AppFlow
* AWS AppSync
* Amazon EventBridge (Amazon CloudWatch Events)
* Amazon MQ
* Amazon Simple Notification Service (Amazon SNS)
* Amazon Simple Queue Service (Amazon SQS)
* AWS Step Functions
### ビジネスアプリケーション:
* Alexa for Business
* Amazon Simple Email Service (Amazon SES)
### ブロックチェーン:
* Amazon Managed Blockchain
### クラウド財務管理:
* AWS Budgets
* AWS Cost and Usage Report
* AWS Cost Explorer
* Savings Plans 
### コンピューティング:
* AWS App Runner
* AWS Auto Scaling
* AWS Batch
* Amazon EC2
* Amazon EC2 Auto Scaling
* AWS Elastic Beanstalk
* Amazon Elastic Kubernetes Service (Amazon EKS)
* Elastic Load Balancing
* AWS Fargate
* AWS Lambda
* Amazon Lightsail
* AWS Outposts
* AWS Wavelength
### コンテナ:
* Amazon Elastic Container Registry (Amazon ECR)
* Amazon Elastic Container Service (Amazon ECS)
* Amazon ECS Anywhere
* Amazon Elastic Kubernetes Service (Amazon EKS)
* Amazon EKS Anywhere
* Amazon EKS Distro
### データベース:
* Amazon Aurora
* Amazon Aurora Serverless
* Amazon DocumentDB (MongoDB 互換) 
* Amazon DynamoDB
* Amazon ElastiCache
* Amazon Keyspaces (for Apache Cassandra)
* Amazon Neptune
* Amazon RDS
* Amazon Redshift
* Amazon Timestream
### デベロッパーツール:
* AWS Cloud9
* AWS CodeArtifact
* AWS CodeBuild
* AWS CodeCommit
* AWS CodeDeploy
* Amazon CodeGuru
* AWS CodePipeline
* AWS CodeStar
* AWS X-Ray
### エンドユーザーコンピューティング:
* Amazon AppStream 2.0
* Amazon WorkSpaces
### フロントエンドのウェブとモバイル:
* AWS Amplify
* Amazon API Gateway
* AWS Device Farm
* Amazon Pinpoint
### IoT:
* AWS IoT Analytics
* AWS IoT Core
* AWS IoT Device Defender
* AWS IoT Device Management
* AWS IoT Events
* AWS IoT Greengrass
* AWS IoT SiteWise
* AWS IoT Things Graph
* AWS IoT 1-Click
### 機械学習:
* Amazon Comprehend
* Amazon Forecast
* Amazon Fraud Detector
* Amazon Kendra
* Amazon Lex
* Amazon Personalize
* Amazon Polly
* Amazon Rekognition
* Amazon SageMaker
* Amazon Textract
* Amazon Transcribe
* Amazon Translate
### マネジメントとガバナンス:
* AWS CloudFormation
* AWS CloudTrail
* Amazon CloudWatch
* Amazon CloudWatch Logs
* AWS Command Line Interface (AWS CLI)
* AWS Compute Optimizer
* AWS Config
* AWS Control Tower
* AWS License Manager
* Amazon Managed Grafana
* Amazon Managed Service for Prometheus
* AWS Management Console
* AWS Organizations
* AWS Personal Health Dashboard
* AWS Proton
* AWS Service Catalog
* Service Quotas
* AWS Systems Manager
* AWS Trusted Advisor
* AWS Well-Architected Tool
### メディアサービス:
* Amazon Elastic Transcoder
* Amazon Kinesis Video Streams
### 移行と転送:
* AWS Application Discovery Service
* AWS Application Migration Service (CloudEndure Migration)
* AWS Database Migration Service (AWS DMS)
* AWS DataSync
* AWS Migration Hub
* AWS Schema Conversion Tool (AWS SCT)
* AWS Snow ファミリー
* AWS Transfer Family
### ネットワークとコンテンツ配信:
* Amazon CloudFront  
* AWS Direct Connect
* Elastic Load Balancing (ELB)
* AWS Global Accelerator
* AWS PrivateLink
* Amazon Route 53
* AWS Transit Gateway
* Amazon VPC
* AWS VPN
### セキュリティ、アイデンティティ、コンプライアンス:
* AWS Artifact  
* AWS Audit Manager
* AWS Certificate Manager (ACM)
* AWS CloudHSM
* Amazon Cognito
* Amazon Detective
* AWS Directory Service
* AWS Firewall Manager
* Amazon GuardDuty
* AWS Identity and Access Management (IAM)
* Amazon Inspector
* AWS Key Management Service (AWS KMS)
* Amazon Macie
* AWS Network Firewall
* AWS Resource Access Manager (AWS RAM)
* AWS Secrets Manager
* AWS Security Hub
* AWS Security Token Service (AWS STS)
* AWS Shield
* AWS Single Sign-On
* AWS WAF
### ストレージ:
* AWS Backup
* Amazon Elastic Block Store (Amazon EBS)
* AWS Elastic Disaster Recovery (CloudEndure Disaster Recovery)
* Amazon Elastic File System (Amazon EFS)
* Amazon FSx (すべてのタイプに対応)
* Amazon S3
* Amazon S3 Glacier
* AWS Storage Gateway

#
## リージョンの選択時に考慮すべき主な ４ つの要素は何ですか。
1. レイテンシー、高可用性、税金、コンプライアンス
2. レイテンシー、価格、サービスの可用性、コンプライアンス
3. レイテンシー、税金、スピード、コンプライアンス
4. レイテンシー、セキュリティ、高可用性、耐障害性
<details><div>
    答え：2
アプリケーションとワークロードをホストする AWS リージョンを決定する際には、レイテンシー、価格、サービスの可用性、コンプライアンスの ４ つの主な側面を考慮する必要があります。AWS リージョンを選択するときは、これらの要素に焦点を当ててください。
</div></details>

## リージョン、アベイラビリティーゾーン、データセンター間の関係を最もよく表しているのは次のうちどれですか。
1. アベイラビリティーゾーンはリージョンのクラスターです。リージョンはデータセンターのクラスターです。
2. データセンターはアベイラビリティーゾーンのクラスターです。リージョンはアベイラビリティーゾーンのクラスターです。
3. リージョンはアベイラビリティーゾーンのクラスターです。アベイラビリティーゾーンはデータセンターのクラスターです。
4. データセンターはリージョンのクラスターです。リージョンはアベイラビリティーゾーンのクラスターです。
<details><div>
    答え：3
</div></details>

## クラウドコンピューティングの利点は次のうちどれですか。
1. 独自のデータセンターを運営および維持する
2. 市場投入までの時間の延長
3. スケールへの過剰投資
4. 数分で世界中にデプロイ
<details><div>
    答え：4
</div></details>

## AWS ルートユーザーをセキュリティ保護する際のベストプラクティスは次のうちどれですか。(２つ選択してください)
1. ルートユーザーの多要素認証 (MFA) を有効にする
2. ルートユーザーを日常的な管理タスクに使用する
3. ルートユーザーの認証情報を信頼できる同僚と共有する
4. ルートユーザーに関連付けられているアクセスキーを無効にするか削除する
5. ルートユーザーのパスワードを安全なコンテナに配置する
<details><div>
    答え：1,4
お客様はアクセスキー (アクセスキー ID およびシークレットアクセスキー) を使用し、AWS に対してプログラムによるリクエストをすることができます。ただし、AWS アカウントのルートユーザーのアクセスキーを使用しないでください。AWS アカウントのアクセスキーにより、請求情報を含む、すべての AWS サービスのお客様のリソースすべてにルートユーザーはフルアクセスできます。AWS アカウントのルートユーザーアクセスキーに関連付けられたアクセス許可を減らすことはできません。そのため、クレジットカード番号や他の機密情報を保護するのと同じように、ルートユーザーのアクセスキーを保護してください。ルートユーザーに関連付けられているアクセスキーを無効または削除し、ルートユーザーの MFA を有効にする必要があります。
</div></details>

## Amazon EC2 インスタンスタイプは何を示していますか。
1. インスタンスの配置とインスタンスサイズ
2. インスタンスファミリとインスタンスサイズ
3. インスタンステナンシーとインスタンス請求
4. インスタンス AMI とネットワーク速度
<details><div>
    答え：2
</div></details>

## サーバーレスについて当てはまるのは次のうちどれですか。
1. サーバーをプロビジョニングおよび管理する必要があります。
2. サーバーレスリソースは手動でスケールする必要があります。
3. 可用性と耐障害性を管理する必要があります。
4. アイドルリソースに対して支払うことはありません
<details><div>
    答え：4
</div></details>

## 仮想プライベートクラウド (VPC) を作成するために必要な情報は、次のうちどれですか。
1. 配置先の AZ (アベイラビリティーゾーン)
2. 配属先のサブネット
3. 配属先のサブネットグループ
4. 配属先の AWS リージョン
<details><div>
    答え：4
</div></details>

## セキュリティグループのデフォルト設定に当てはまるのは次のうちどれですか。
1. すべてのインバウンドトラフィックを許可し、すべてのアウトバウンドトラフィックをブロックする
2. すべてのインバウンドトラフィックをブロックし、すべてのアウトバウンドトラフィックを許可する
3. すべてのインバウンドとアウトバウンドトラフィックを許可
4. すべてのインバウンドとアウトバウンドトラフィックをブロック
<details><div>
    答え：2
</div></details>

## ネットワークアクセスコントロールリスト (ネットワーク ACL) は、EC2 インスタンスレベルでトラフィックをフィルタリングします。
1. 正しい
2. 誤り
<details><div>
    答え：2
ネットワーク ACL はサブネットを保護します。セキュリティグループは EC2 インスタンスの保護を担当します。
</div></details>

## Amazon Simple Storage Service (Amazon S3) のユースケースは次のうちどれですか。
1. メディアホスティング用のオブジェクトストレージ
2. ブートドライブのオブジェクトストレージ
3. EC2 インスタンスのブロックストレージ
4. 複数の EC2 インスタンスのファイルストレージ
<details><div>
    答え：1
</div></details>

## バケットの名前はすべての AWS アカウントに対して一意である必要があります。
1. 正しい
2. 誤り
<details><div>
    答え：1
</div></details>

## 医療施設の従業員は、ほとんどアクセスされない 7 年間の患者情報を保存する義務があります。どのストレージ層を使用すべきですか。
1. S3 Glacier Deep Archive
2. S3 標準
3. S3 標準 – 低頻度アクセス
4. S3 Intelligent-Tiering
<details><div>
    答え：1
</div></details>

## AWS アーキテクトは、データにばらつきがあるデータセットのデータベースを選択しています。すべてのデータが同じ属性を共有しているわけではありません。ソリューションにはどのデータベースを選択すべきですか。
1. Amazon Relational Database Service
2. Amazon Neptune
3. Amazon DynamoDB
4. Amazon QLDB
<details><div>
    答え：3
</div></details>

## Amazon リレーショナルデータベースサービス (Amazon RDS) を使用する場合、データベースを実行および運用する際にお客様が責任を負うタスクとは
1. データベースの最適化
2. 基盤となるインフラストラクチャのプロビジョニングと管理
3. DB インスタンスへの RDBMS のインストール
4. DB インスタンスの OS へのパッチのインストール
<details><div>
    答え：1
</div></details>

## EC2 Auto Scalingの ３ つのコンポーネントは何ですか。
1. テンプレート、スケーリングポリシー、EC2 Auto Scaling グループの起動
2. スケーリングポリシー、セキュリティグループ、EC2 Auto Scaling グループ
3. セキュリティグループ、インスタンスタイプ、キーペア
4. AMI ID、インスタンスタイプ、ストレージ
<details><div>
    答え：1
EC2 Auto Scaling では、EC2 インスタンスの設定テンプレートとして起動テンプレートまたは起動設定、インスタンスの最小容量、最大容量、必要な容量を指定できる EC2 Auto Scaling グループ、スケーリングポリシーの 3 つの主要コンポーネントを指定する必要があります。これにより、指定した条件の発生またはスケジュールに基づいてグループをスケールするように構成できます。
</div></details>

## Elastic Load Balancing に含まれている機能はどれですか。(2 つ選択してください)
1. Auto Scaling との統合
2. 従業員の写真を分類するための AI
3. EC2 インスタンスの垂直スケーリング
4. 受信トラフィックをインスタンスに送信
5. 必要に応じて新しいインスタンスをデプロイする
<details><div>
    答え：1,4
</div></details>

## メトリクスアラームの可能性のある状態はどれですか。
1. OK, ALARM, NOT_AVAILABLE
2. OK, ALARM, INSUFFICIENT_DATA
3. OK, ALERT, INSUFFICIENT_DATA
4. OK, ALERT, NOT_AVAILABLE
<details><div>
    答え：2
メトリクスアラームには、次の状態があります。

 OK—メトリクスまたは定義されたしきい値内に式がある場合。
アラーム—メトリクスまたは定義されたしきい値の式を超えている場合。
INSUFFICURENT_DATA—アラームが開始されたばかりか、メトリクスが使用できない、メトリクスがアラーム状態を判断するのに十分なデータがない場合。
</div></details>

## 
1. 
2. 
3. 
4. 
<details><div>
    答え：
</div></details>



# 
## 1.0  組織の複雑さに対応する設計
### クロスアカウント認証とアクセス戦略
#### クロスアカウント認証
#### ユーザー管理関連のアクセス戦略
* IAM ユーザー
* グループ
* ロール
### ネットワーク
#### グローバルインフラストラクチャー
#### ネットワークトラフィックモニタリング
#### ストレージゲートウェイ
#### 仮想プライベートクラウド (VPC) エンドポイント
### マルチアカウントの AWS 環境
#### リソースと請求の分離
#### AWS Organizations

## 2.0  新しいソリューションの設計 
### 信頼性の要件の実装戦略
#### 信頼性の要件の実装戦略
#### ビジネス継続性の確保
#### パフォーマンス目標の達成
### ビジネス継続性の確保
#### セキュリティ要件と管理
* IAM & STS
  + IAMユーザーとグループ
  + IAMポリシーとロール
* Lambda & STS
  + サービスロール
  + アカウントとの相互作用 
* Cognito & Directory Service
  + アイデンティティプロバイダー
  + SAML2.0、SSO、OpenID
#### ビジネス要件に基づいたデプロイ戦略
* Runtime/container
  + EC2
  + ECS
  + Lambda
  + Beanstalk
* Application deployment
  + CodeDeploy
  + OpsWorks
  + Beanstalk
* Code/deployment management
  + CodeCommit
  + CodePipeline
    - 承認プロセス：SNS
      1. 承認アクションの承認または拒否に必要な IAM のアクセス許可を組織内の IAM ユーザーに付与します。
      2. Amazon SNS 通知を使用している場合、CodePipeline オペレーションで使用しているサービスロールには、Amazon SNS リソースにアクセスするためのアクセス許可が含まれます。
      3. Amazon SNS 通知を使用している場合は、Amazon SNS トピックを作成し、1 人以上の受信者または 1 つ以上のエンドポイントを追加します。
      4. AWS CLI を使用してパイプラインを作成するか、CLI またはコンソールを使用してパイプラインを作成したら、承認アクションをパイプラインのステージに追加します。
      5. 承認アクションに到達するとパイプラインは停止します。Amazon SNS トピックの ARN がアクション設定に含まれている場合、通知は Amazon SNS トピックメッセージが通知されます。
      6. 承認者は、必要に応じてターゲット URL およびコメントを確認します。
      7. 承認者は、コンソール、CLIまたはSDK を使用して、概要コメントを確認して、承認または拒否となるレスポンスを送信します。承認がされるとパイプラインの実行が再開されます。拒否されるとステージステータスが「失敗」に変更され、パイプラインの実行は再開されません。
  + Beanstalk
* Infrastructure deployment
  + OpsWorks
  + CloudFormation
    - cfn-signalヘルパースクリプト
      * CloudFormation はAutoScalingRollingUpdate ポリシー を使用して Auto Scaling グループのローリング更新を制御することが可能
  + Beanstalk
    - デプロイポリシー
        * All at Once
        * Rolling
        * Rolling with addtional batch
        * immutable
#### Amazon Cognito
    フルマネージド型のソリューションで、ウェブアプリケーションとモバイルアプリケーション向けのアクセスコントロールと認証を提供します。
#### MFA のサポート
#### 保管中のデータと転送中のデータの暗号化
#### ソーシャルアイデンティティプロバイダー経由のログイン
#### SAML のサポート
### パフォーマンス目標の達成

## 3.0  移行計画
### 6つのR
1. Retain
* 今は変更を加えず、将来再検討する
2. Re-host
* リフト、シフトする
3. Refactor
* 再設計
4. Re-platform
* リフト、変更、シフトする
5. Replace
* 既にクラウドに存在するソリューションを購入する
6. Retire
* アプリケーションやシステムが価値を提供しているかどうかを評価する
### クラウドに移行する可能性のある既存のワークロードとプロセス
#### 計画
1. 検出
##### 評価とプロファイリング
##### データの要件と分類
##### 優先順位付け
##### ビジネスロジックとインフラストラクチャの依存関係
2. 設計
##### 詳細な移行計画
##### 作業量の見積もり
##### セキュリティとリスクの評価
#### 構築
1. 変換
##### ネットワークトポロジー
##### 移行
* データベース
  + 高可用性とスケーラビリティ
    - Aurora、クラスタ構成、リードレプリカ
    - AutoScaling
##### デプロイ
##### 検証
2. 移行
##### パイロットテスト
##### サポートへの移行
##### リリース管理
##### カットオーバーと廃止
#### 実行
1. 運用
##### スタッフのトレーニング
##### モニタリング
* Elastic Beanstalk の X-Ray 統合
##### インシデント管理
##### プロビジョニング
2. 最適化
##### モニタリング駆動型の最適化
##### 継続的インテグレーションと継続的デプロイ
##### Well-Architected フレームワーク

### 新しい移行ツールやサービスと、AWS の詳細な知識に基づいて移行されるソリューション
### 既存のオンプレミスのワークロードをクラウドに移行するための戦略
### 既存のソリューション向けの新しいクラウドアーキテクチャ

## 4.0  コスト管理
#### 特定のグループまたはチームのみに、選択した AWS リソースのデプロイを許可する
#### 環境ごとにポリシーを作成する
#### リソースのインスタンス化時にタグを必須にする
#### タグ付けをモニタリングし、不適切なタグのインスタンスについてアラート送信またはシャットダウンを実行する
#### CloudWatch を使用して、請求がしきい値に達したときにアラートを送信する
#### AWS またはパートナーのツールを使用して支出を分析する
### コスト効率に優れた料金モデル
### コスト最適化を行うための管理の設計と実装
### 既存のソリューションのコストを削減する機会

## 5.0  既存のソリューションの継続的な改良
### ソリューションアーキテクチャのトラブルシューティング
#### Amazon S3 サーバーアクセスログ
* 説明:リクエストタイプ、リクエストされたリソース、リクエストが実行された日時など、データリクエストに関する詳細が含まれる
* 用途:バケットアクセスの問題とデータリクエストのトラブルシューティング
#### Amazon ELB アクセスログ
* 説明:クライアントの IP アドレス、レイテンシー、サーバーの応答といった、ロードバランサーに送信される各リクエストの詳細をキャプチャする
* 用途:トラフィックパターンの分析およびネットワークの問題のトラブルシューティング
#### Amazon CloudTrail
* 説明:AWS マネジメントコンソール、AWS CLI、AWS SDK、他の AWS のサービスで実行された、アカウントに対する API コールの履歴を提供する
* 用途:誰が、何を、いつ、どこから行ったのかの監査と特定
* AWS Organizationsを利用していれば、CloudTrailにより全てのAWSアカウントをまとめてログ取得することが可能です
#### Amazon VPC フローログ
* 説明:ネットワークインターフェイスとサブネットに出入りする IP トラフィックに関する情報をキャプチャする
* 用途:ネットワークアクセスルールの適切な設定の検証と、接続およびセキュリティに関する問題のトラブルシューティング
#### Amazon CloudWatch Logs
* 説明:Amazon EC2 インスタンスやオンプレミスサーバーのログデータを使用して、アプリケーションやシステムに対するモニタリング、保存、アクセスを行う
* 用途:AWS 環境で実行される OS およびアプリケーションのモニタリングとトラブルシューティング
#### AWS Config
* 説明:AWS リソースのインベントリを提供し、リソースの設定変更を記録する
* 用途:機能停止のトラブルシューティングとセキュリティ攻撃の分析
#### CloudFront 
* 配信のキャッシュヒット率
  + オリジンが一意のオブジェクトを返すクエリ文字列パラメータのみを転送するようにCloudFront を設定する
  + Cache-Control max-age ディレクティブをオブジェクトに追加し、max-ageに対して最も長い実用的な値を指定するようにオリジンを設定する
* HTTPS を介して CloudFront から複数のドメインを提供する
  + [代替ドメイン名 (CNAME)] フィールドにすべてのドメイン名を入力します
  + ACMを利用してALBに関連づいたドメインに全てのSSL証明書を追加し、複数の証明書をロードバランサーの同じセキュアリスナーにバインドします
* Origin Protocol Policyの値として選択できる3つのオプションがあります。
  + HTTP Only
  + HTTPS Only
  + Match Viewer
    - CloudFrontはビューアーリクエストのプロトコルに応じてHTTPまたはHTTPSを使用してオリジンと通信します
#### NATインスタンスの改善
* NATゲートウェイ
* マルチAZ


### 既存ソリューションの運用上の優秀性を向上させる戦略の決定
#### 運用の連続性
#### 運用上の優秀性
* 準備
  + Trusted Advisor
  + CloudFormation
  + System Manager
* 運用
  + CloudWatch
    - SurgeQueueLengthメトリクスは正常なインスタンスへのルーティングを保留中のリクエスト (HTTP リスナー) または接続 (TCP リスナー) の合計数を提供
    - SpilloverCountはサージキューがいっぱいとなったために拒否されたリクエストの総数
    - HealthyHostCountメトリクスはロードバランサーに登録された正常なインスタンス数
    - UnHealthyHostCountはロードバランサーに登録された異常なインスタンス数
    - RequestCountは指定された間隔 (1 分または 5 分) の間に完了したリクエスト数、または接続数
  + Lambda
* 構成管理
  + Systems Manager
    - エンドポイント
    - エージェント
    - API
      * IAMロール
* 進化
  + Elasticsearch
  + CodeCommit
#### Well-Architected フレームワーク
* ビジネスやお客様のニーズを理解する
* 頻繁に、小さく、可逆的な変更を行う
* 運用上のイベントへの対応手順を作成して使用する
* サポートプロセスと手順を継続的に改善する

### 既存ソリューションの信頼性を向上させる戦略の決定
#### 高可用性を実現する設計
#### 可用性レベルを満たす
#### コストと複雑さを最小化する
#### セキュリティの改善
##### アクセスの制限
#### ユーザーベースのポリシー
* 特定のエンティティがアクセスできるのは何か
* IAM ユーザーにアタッチされる
#### リソースベースのポリシー
* 特定のリソースにアクセスできるのは誰か
* リソース上で直接アクセス権を付与する
* 一部のサービスはリソースベースのポリシーをサポートしていない
#### より細かく制御するためのポリシー条件
* ポリシーを有効化する時期の条件を指定する
* 例えば、日付と IP アドレスという条件でユーザーアクセスをさらに制限する
* ポリシー条件により MFA を強化できる
##### 各サービス
#### S3
* SSE-C 
* SSE-S3
* SSE-KMS
#### EFS

#### DynamoDB
* 暗号化クライアント
* SSE-KMS
#### Redshift
* AWS KMS
  + クロスリージョンスナップショットコピー
* AWS CloudHSM
#### EBS
* AWS KMS
#### RDS
* AWS KMS
* TDE
#### SQS/SNS
* AWS KMS
* CloudWatch カスタムメトリクス 
  + AutoScaling
