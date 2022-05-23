# 
## 1.デプロイ

### 可用性、スケーラビリティ、メンテナンス
#### EC2、AutoScaling
* ELB配下のWebサーバーをAutoScaling
    + 特徴
        - Webサーバーの負荷に応じてスケール
        - EC2は複数AZに分散し高可用性を担保
    + スケーリングトリガーの例
        - ELBのリクエスト数
        - アプリケーションサブグループ内EC2の平均CPU使用率
* SQSのジョブを処理するワーカーをAutoScaling
    + 特徴
        - ワーカーの負荷に応じてスケール
        - EC2は複数AZに分散し高可用性を担保
        - スポットインスタンスがマッチするケースが多い
    + スケーリングトリガーの例
        - キュー内のメッセージ数
* ECSホストのAutoScaling
    + 特徴
        - ECSクラスタ内のホストを負荷に応じてスケール
        - ホストへのタスクの配置・管理はECSが実施
    + スケーリングトリガーの例
        - ECSホストのCPU使用率
        - ECSホストのメモリ使用率
#### ELB
* 環境でELB作成したあとはELBのタイプを変えることはできない。
* セキュリティグループの割り当て
* スティッキーセッション
* AutoScalingとの連携
* ECSのALB対応
    + ALBによりECSコンテナをまたがった負荷分散
* ACMとの統合
    + ACMを使用して、証明書のリクエストと管理を容易に実施
    + 無料で利用可能
    + ELBに対する証明書の設定を数クリックで完了
* Route 53 DNSフェイルオーバー対応
    + Route53のヘルスチェック機能とELBが連携
* OpsWorksのELB対応
    + OpsWorksでELBをレイヤーにアタッチして、負荷分散が可能
* AWS Trusted AdvisorによるELBのチェック
    + ELBのセキュリティとフォールトトレランスをチェック
#### S3、EBS
* CloudFrontとの連携
* CloudWatchによるメトリクス管理
* CloudTrailによるAPI管理
    + 操作ログを収集する
#### RDS

### リリースプロセス
### CI/CDパイプライン
### デプロイパターン
#### Blue/Greenデプロイメント
* 特徴
    + アプリケーションのデプロイ時にASGを再作成
    + ELBまたはDNSで環境を切替
    + ASG作成にはCloudFormationを利用することで環境構築を自動化可能
### デプロイサービス
#### Codeシリーズ
##### CodeCommit
* AWS SNS、Lambda、CloudWatch Event Rulesを使用して通知が可能。
* クロスアカウントアクセス有
##### CodeBuild
* フックの順序
    1. アプリケーションストップ
    2. バンドルをダウンロード
    3. beforeInstall
    4. afterInstall
    5. アプリケーションスタート
    6. サービスの検証
* CodeBuildコンテナは実行終了時に削除される
* Dockerイメージは、プライベートレジストリからのものも使用できる
##### CodeDeploy
##### CodePipeline
##### CodeStar
##### CodeArtifact
#### CodeGuru
#### AWS CloudFormation
#### AWS OpsWorks
#### Elastic Beanstalk
### サーバーレスアーキテクチャ
#### 代表的なサーバーレスサービス
#### 一般的なサーバーレスアーキテクチャ
### AWS SAM

## 2.セキュリティ
### 責任共有モデル
### ネットワークセキュリティ
#### VPC
### 認証と認可
#### IAM
#### Cognito
### データおよびアプリケーションのセキュリティ、暗号化
#### KMS
#### HSM
### 確認
    CloudWatch、CloudTrail
#### API Gateway
    イベントとして API Gateway のすべての API コールをキャプチャ
* リクエストの IP アドレス、リクエスタ、時間を含める
* イベント履歴を確認
* 証跡を作成して S3 バケットにイベントを送信
* API とそのバックエンドサービスにおけるレイテンシーを分析
* 特定のリクエストに着目したサンプリングルールを設定
* サービスマップは個々の地域のデータではなく全ての地域のデータが表示される
### IAM,STSおよびIdentityFederation
* IAM：明示的に拒否するポリシーがある場合、他の許可されたステートメントを上書きする

## 3.開発
### グローバルインフラストラクチャー
#### AWSリージョン
#### アベイラビリティーゾーン
#### エッジロケーション
##### CloudFront

### 開発環境
#### AWS API
#### SDK
    認証情報を参照する順番   
1. 環境変数
2. java system properties
3. デフォルトのcredential profileファイル
4. コンテナのcredentials
5. EC2のInstance profile credentials
#### Toolkit
#### AWS Cloud9

### ストレージ
#### Amazon Elastic Block StoreとAmazon Elastic File System
#### Amazon Simple Storage Service（S3）
### データベース
#### Amazon RDS、Amazon Aurora
#### Amazon ElastiCache
#### Amazon DynamoDB
    NoSQL。トランザクションが不要で結果整合性が担保されていればよいデータが対象
* 読み込みキャパシティユニット（結果整合性なら最大4KBで2回/s）
* グローバルセカンダリインデックスでは一貫性のある読み取りをサポートしていない
* 一貫性のある読み取りをDAXクラスターにリクエストした場合、結果はキャッシュされない
* DynamoDBストリームとLambdaトリガーの併用はベストプラクティス
* プロジェクション式

### コンピューティング、API
#### Lambda
* タイムアウトは最大15分
* 環境変数は最大4KB
* 関数をスケジューリングするベストプラクティスはCloudWatch Iventを使用すること
* エイリアス機能
#### API Gateway
* Cognito設定
    + IDプール
    + ユーザープール
* エンドポイント
    + エッジ最適化
    + リージョン
    + プライベート
* オプションキャッシュ
    + API キャッシュの TTL 値はデフォルトで 300 秒
    + ステージ毎に設定
    + キャッシュを検証する 2 つの方法
        - CloudWatch メトリクス: CacheHitCount と CacheMissCount
        - タイムスタンプを作成し、API レスポンスに含める
* スロットリング制限
* リソースポリシー

### メッセージング、ステート制御、イベント
#### SQS
* メッセージ保持期間（デフォルト4日間）
* 自動的にメッセージを取得して、ターゲットの Lambda 関数にルーティングします
* Lambda 関数が正常に完了すると、メッセージを削除します
* 通信データの暗号化、CloudTrailに記録
* FIFO キュー（1回）
* デッドレターキュー：使用すると、処理できないメッセージを後で分析するために分離できます
* 可視性タイムアウト：Amazon SQS で、他の消費コンポーネントがメッセージの受信と処理を行わないようにする期間
#### SNS、SES
#### MQ
* オンプレミスからAWSへのブリッジ
* サードパーティクラウドとのコネクタ
#### Kinesis Streams 
#### StepFunctions
#### EventBridge
    イベント駆動

### コンテナ
* ECS Task PlacementはECS with EC2のみ使用可能
    + 3つのタイプ
        1. Binpack - 使用するインスタンスの数を最小にしようとする most cost effective
        2. Ramdom - タスクをランダムに配置する
        3. Spread - インスタンスIDやAZに基づいてタスクを分散配置する
    + 2つの制約
        1. distinctInstance - それぞれのタスクは異なるコンテナインスタンスに配置する
        2. memberOf - クラスタークエリ言語を使用して制約を定義可能     example:t2のインスタンスにのみタスクを配置する

## 4.リファクタリング
    ベストプラクティスへの理解を深めること
### DVA の原則(ベストプラクティス)
* スケールアップよりもスケールアウト
* アクセスキーより IAM ロールが望ましい
* アンマネージドサービスよりもマネージド
* リソースや API を直接公開する事は避け、AWS エッジサービスや API ゲートウェイを使用する
* サーバーにセッション状態を保存していては優れたアーキテクチャにはならない
* インフラストラクチャを疎結合化する
* サーバーレス化する
* トラブルシューティング時には、セキュリティグループや NACL を常に確認する
* VPC のプライベートサブネット内に作成されたインスタンスは、NAT を使用しない限りインターネットと通信することが出来ない
* インターネットと通信するには、インターネットゲートウェイとルートテーブルのルートが必要
* EBS ボリュームは、EC2 インスタンスに疎結合されている。
    + ブートボリュームの場合を除いて、アタッチまたはデタッチできる
### スケーラビリティを確保する
### 環境を自動化する
### 使い捨て可能にする
### 疎結合にする
### サーバーではなくサービスを設計する
### 適切なデータベースを選択する
### 単一障害点をなくす
### コストを最適化する
### キャッシュを使用する
### すべてのレイヤーでセキュリティを実装する
### 増え続けるデータを処理する

### 移行
#### 6つのR
    Re-HostとRe-platform
1. Retain
    + 今は変更を加えず、将来再検討する
2. Re-host
    + リフト、シフトする
3. Refactor
    + 再設計
4. Re-platform
    + リフト、変更、シフトする
5. Replace
    + 既にクラウドに存在するソリューションを購入する
6. Retire
    + アプリケーションやシステムが価値を提供しているかどうかを評価する
#### 実施に向けて

## 5.モニタリングとトラブルシューティング
    ベストプラクティスへの理解を深めること
### モニタリング
#### CloudWatch
* 基本的なモニタリングにアラームを設定する場合 - 少なくとも5分
* 詳細なモニタリングにアラームを設定する場合 - 少なくとも1分
#### CloudTrail

#### VPCフローログ
#### X-Ray
* SQSと統合されている場合、リソースヘッダーはSQSのメッセージサイズ等に影響しない
* サンプリングルールのデフォルト - 1秒あたりに1つのリクエスト、ホスト毎の追加の5%の要求がリクエストされる
* X-Ray SDKが提供するもの 
    + インターセプター コードに追加して受信 HTTP リクエストをトレースする
    + クライアントハンドラー アプリケーションが他の AWS サービスの呼び出しに使用する AWS SDK クライアントを計測する
    + An HTTP クライアント 別の内部および外部 HTTP ウェブサービス呼び出しを計測する

### トラブルシューティング
#### スロットリングエラー
#### エクスポネンシャルバックオフ
#### セキュリティのトラブルシューティング

## 0. ベストプラクティス


## 参考
https://docs.aws.amazon.com/whitepapers/latest/practicing-continuous-integration-continuous-delivery/welcome.html?did=wp_card&trk=wp_card
https://docs.aws.amazon.com/whitepapers/latest/change-management-in-the-cloud/change-management-in-the-cloud.html?did=wp_card&trk=wp_card
https://docs.aws.amazon.com/wellarchitected/latest/serverless-applications-lens/welcome.html?did=wp_card&trk=wp_card
https://docs.aws.amazon.com/whitepapers/latest/s3-optimizing-performance-best-practices/welcome.html?did=wp_card&trk=wp_card
https://docs.aws.amazon.com/wellarchitected/latest/management-and-governance-lens/management-and-governance-lens.html?did=wp_card&trk=wp_card
https://docs.aws.amazon.com/wellarchitected/latest/saas-lens/saas-lens.html?did=wp_card&trk=wp_card
https://docs.aws.amazon.com/whitepapers/latest/practicing-continuous-integration-continuous-delivery/welcome.html?did=wp_card&trk=wp_card
https://docs.aws.amazon.com/wellarchitected/latest/cost-optimization-pillar/welcome.html?did=wp_card&trk=wp_card
https://docs.aws.amazon.com/wellarchitected/latest/performance-efficiency-pillar/welcome.html?did=wp_card&trk=wp_card
https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/welcome.html?did=wp_card&trk=wp_card
https://docs.aws.amazon.com/whitepapers/latest/building-scalable-secure-multi-vpc-network-infrastructure/welcome.html?did=wp_card&trk=wp_card
https://docs.aws.amazon.com/whitepapers/latest/real-time-communication-on-aws/welcome.html?did=wp_card&trk=wp_card
https://docs.aws.amazon.com/whitepapers/latest/microservices-on-aws/microservices-on-aws.html
https://docs.aws.amazon.com/whitepapers/latest/tagging-best-practices/tagging-best-practices.html
https://docs.aws.amazon.com/whitepapers/latest/kms-best-practices/welcome.html?did=wp_card&trk=wp_card
https://docs.aws.amazon.com/whitepapers/latest/blue-green-deployments/welcome.html?did=wp_card&trk=wp_card
https://docs.aws.amazon.com/wellarchitected/latest/serverless-applications-lens/welcome.html?did=wp_card&trk=wp_card


## サンプル問題

### Q. 
1. 
2. 
3. 
4. 
<details><div>
    答え：
</div></details>


### Q. 
1. 
2. 
3. 
4. 
<details><div>
    答え：
</div></details>


### Q. 
1. 
2. 
3. 
4. 
<details><div>
    答え：
</div></details>


### Q. 
1. 
2. 
3. 
4. 
<details><div>
    答え：
</div></details>


### Q. 
1. 
2. 
3. 
4. 
<details><div>
    答え：
</div></details>

