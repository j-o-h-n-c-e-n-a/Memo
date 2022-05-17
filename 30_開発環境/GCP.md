## ACE - テスト概要
### セクション 1：クラウド ソリューション環境の設定
#### 1.1 クラウド プロジェクトとアカウントを設定する。次のような作業が含まれます。
##### リソース階層の作成
##### リソース階層への組織のポリシーの適用
##### プロジェクト内の IAM ロールをメンバーに付与する
##### Cloud Identity でのユーザーとグループの管理（手動および自動）
##### プロジェクトで API を有効にする
##### Google Cloud のオペレーション スイートでのプロダクトのプロビジョニングと設定
#### 1.2 課金構成を管理する。次のような流れになります。
##### 請求先アカウントを作成する
##### プロジェクトを請求先アカウントにリンクする
##### 課金の予算とアラートを設定する
##### 課金データのエクスポートの設定
#### 1.3 コマンドライン インターフェース（CLI）、具体的には Cloud SDK をインストールして構成する（デフォルト プロジェクトの設定など）。
* Cloud SDK

### セクション 2：クラウド ソリューションの計画と構成
#### 2.1 料金計算ツールを使用して Google Cloud プロダクトの使用量の計画と見積もりを作成する
#### 2.2 コンピューティング リソースを計画し、構成する。以下のような点を考察します。
##### ワークロードに適したコンピューティング サービスを選択する（Compute Engine、Google Kubernetes Engine、Cloud Run、Cloud Functions など）
* Compute Engine
* Google Kubernetes Engine
* Cloud Run
* Cloud Functions
##### 必要に応じてプリエンプティブル VM とカスタム マシンタイプを使用する
#### 2.3 データ ストレージ オプションを計画し、構成する。 以下のような点を考察します。
##### プロダクトの選択（Cloud SQL、BigQuery、Firestore、Cloud Spanner、Cloud Bigtable など）
* Cloud SQL
* BigQuery
* Firestore
* Cloud Spanner
* Cloud Bigtable
##### ストレージ オプションの選択（ゾーン永続ディスク、リージョン バランス永続ディスク、標準、Nearline、Coldline、Archive など）
* ゾーン永続ディスク
* リージョン バランス永続ディスク
* 標準
* Nearline
* Coldline
* Archive
#### 2.4 ネットワーク リソースを計画し、構成する。次のようなタスクが含まれます。
##### 負荷分散オプションの違いを見分ける
* Cloud Load Balancing
##### 可用性を考慮してネットワーク内のリソースのロケーションを決定する
##### Cloud DNS を構成する

### セクション 3：クラウド ソリューションのデプロイメントと実装
#### 3.1 Compute Engine リソースをデプロイし、実装する。以下のようなタスクを行います。
##### Cloud Console と Cloud SDK（gcloud）を使用してコンピューティング インスタンスを起動する（例: ディスク、可用性ポリシー、SSH 認証鍵の割り当て）
##### インスタンス テンプレートを使用して、自動スケーリングされるマネージド インスタンス グループを作成する
##### インスタンス用のカスタム SSH 認証鍵の生成 / アップロード
##### Cloud Monitoring と Cloud Logging のエージェントをインストールし、構成する
##### コンピューティングの割り当てを評価し、割り当ての増加をリクエストする
#### 3.2 Google Kubernetes Engine リソースをデプロイし、実装する。以下のようなタスクを行います。
##### Kubernetes 用のコマンドライン インターフェース（CLI）である kubectl をインストールして構成する
##### AutoPilot、リージョン クラスタ、限定公開クラスタなど、さまざまな構成で Google Kubernetes Engine クラスタをデプロイする
##### コンテナ化したアプリケーションを Google Kubernetes Engine にデプロイする
##### Google Kubernetes Engine のモニタリングとロギングを構成する
#### 3.3 Cloud Run リソース、Cloud Functions リソースをデプロイし、実装する。以下のようなタスクがあります（該当する場合）。
##### アプリケーションをデプロイし、スケーリング構成、バージョン、トラフィック分割を更新する
##### Google Cloud イベント（Cloud Pub/Sub イベント、Cloud Storage オブジェクト変更通知イベントなど）を受け取るアプリケーションをデプロイする
#### 3.4 データ ソリューションをデプロイし、実装する。次のようなタスクが含まれます。
##### 製品を使用してデータシステムを初期化する（Cloud SQL、Firestore、BigQuery、Cloud Spanner、Pub/Sub、Cloud Bigtable、Dataproc、Dataflow、Cloud Storage など）
##### データを読み込む（コマンドラインによるアップロード、API による転送、インポート / エクスポート、Cloud Storage からのデータの読み込み、Cloud Pub/Sub へのデータのストリーミングなど）
#### 3.5 ネットワーキング リソースをデプロイし、実装する。以下のようなタスクを行います。
##### サブネットを持つ VPC を作成する（カスタムモード VPC、共有 VPC など）
##### カスタム ネットワーク構成を持つ Compute Engine インスタンスを起動する（内部専用 IP アドレス、限定公開の Google アクセス、静的外部 IP アドレスとプライベート IP アドレス、ネットワーク タグなど）
##### VPC 用の上り（内向き）および下り（外向き）ファイアウォール ルール（例: IP サブネット、ネットワーク タグ、サービス アカウント）を作成する
##### Cloud VPN を使用して Google VPC と外部ネットワークとの間の VPN を作成する
##### アプリケーションへのネットワーク トラフィックを分散するロードバランサの作成（グローバル HTTP(S) ロードバランサ、グローバル SSL プロキシ ロードバランサ、グローバル TCP プロキシ ロードバランサ、リージョン ネットワーク ロードバランサ、リージョン内部ロードバランサなど）
#### 3.6 Cloud Marketplace を使用してソリューションをデプロイする。以下のようなタスクを行います。
##### Cloud Marketplace カタログを閲覧し、ソリューションの詳細を見る
##### Cloud Marketplace ソリューションをデプロイする
#### 3.7 Infrastructure as Code を介してリソースを実装する。以下のようなタスクを行います。
##### Cloud Foundation Toolkit テンプレートを使用してインフラストラクチャを構築し、ベスト プラクティスを実装する
##### Google Kubernetes Engine に Config Connector をインストールして構成し、リソースの作成、更新、削除、保護に利用する

### セクション 4：クラウド ソリューションの正常なオペレーションの確保
#### 4.1 Compute Engine リソースを管理する。以下のようなタスクを行います。
##### 単一の VM インスタンスを管理する（起動、停止、構成の編集、インスタンスの削除など）
##### インスタンスへリモート接続する
##### GPU を新しいインスタンスに接続し、必要な依存関係をインストールする
##### 現在実行されている VM のインベントリ（インスタンス ID、詳細）を見る
##### スナップショットを操作する（VM からのスナップショットの作成、スナップショットの表示、スナップショットの削除など）
##### イメージを操作する（VM またはスナップショットからのイメージの作成、イメージの表示、イメージの削除など）
##### インスタンス グループを操作する（自動スケーリング パラメータの設定、インスタンス テンプレートの割り当てや作成、インスタンス グループの削除など）
##### 管理インターフェースを操作する（Cloud Console、Cloud Shell、Cloud SDK など）
#### 4.2 Google Kubernetes Engine リソースを管理する。次のようなタスクが含まれます。
##### 現在実行されているクラスタのインベントリ（ノード、Pod、サービス）を見る
##### Docker イメージを参照し、その詳細を Artifact Registry で確認する
##### ノードプールを操作する（ノードプールの追加、編集、削除など）
##### Pod を操作する（Pod の追加、編集、削除など）
##### サービスを操作する（サービスの追加、編集、削除など）
##### ステートフル アプリケーションを操作する（永続ボリューム、ステートフル セットなど）
##### 水平自動スケーリングと垂直自動スケーリングの構成を管理する
##### 管理インターフェースの操作（Cloud Console、Cloud Shell、Cloud SDK、kubectl など）
#### 4.3 Cloud Run リソースを管理する。以下のようなタスクを行います。
##### アプリケーションのトラフィック分割パラメータを調整する
##### 自動スケーリング インスタンスのスケーリング パラメータを設定する
##### Cloud Run（フルマネージド）と Cloud Run for Anthos のどちらを実行するかを決定する
#### 4.4 ストレージとデータベースのソリューションを管理する。以下のようなタスクを行います。
##### Cloud Storage のバケット内またはバケット間でオブジェクトを管理、保護する
##### Cloud Storage バケットのオブジェクト ライフサイクル管理ポリシーを設定する
##### データ インスタンス（Cloud SQL、BigQuery、Cloud Spanner、Cloud Datastore、Cloud Bigtable など）からデータを取得するクエリを実行する
##### データ ストレージ リソースのコストを見積もる
##### データ インスタンス（Cloud SQL、Datastore など）のバックアップと復元を行う
##### Dataproc、Dataflow、BigQuery のジョブ ステータスを確認する
#### 4.5 ネットワーキング リソースを管理する。以下のようなタスクを行います。
##### 既存の VPC にサブネットを追加する
##### サブネットを拡張して IP アドレスを増やす
##### 静的外部または内部 IP アドレスを予約する
##### CloudDNS、CloudNAT、ロードバランサ、ファイアウォール ルールを操作する
#### 4.6 モニタリングとロギングを行う。以下のようなタスクを行います。
##### リソース指標に基づく Cloud Monitoring アラートの作成
##### Cloud Monitoring のカスタム指標（アプリケーションやログなどの指標）の作成と取り込み
##### ログが外部システムにエクスポートされるようにログシンクを構成する（オンプレミスまたは BigQuery など）
##### ログルーターを構成する
##### Cloud Logging のログを表示、フィルタリングする
##### Cloud Logging で特定のログメッセージの詳細を見る
##### Cloud Diagnostics を使用してアプリケーションの問題を調査する（Cloud Trace データの表示、Cloud Debug を使用したアプリケーションのポイントインタイムの表示など）
##### Google Cloud のステータスを確認する

### セクション 5：アクセスとセキュリティの構成
#### 5.1 Identity and Access Management（IAM）を管理する。 以下のようなタスクを行います。
##### IAM ポリシーの表示
##### IAM ポリシーの作成
##### さまざまなロールタイプの管理とカスタム IAM ロールの定義（基本ロール、事前定義ロール、カスタムロールなど）
#### 5.2 サービス アカウントを管理する。以下のようなタスクを行います。
##### サービス アカウントの作成
##### 最小限の権限を持つ IAM ポリシー内のサービス アカウントを使用する
##### サービス アカウントをリソースに割り当てる
##### サービス アカウントの IAM の管理
##### サービス アカウントの権限借用の管理
##### 有効期間が短いサービス アカウント認証情報の作成と管理
#### 5.3 監査ログの表示

##
### IAM
### GCE
### GKE
### Cloud Storage
### BigQuery
### Terraform
### ほか
* Apache Kafkaの移行は、Cloud Pub/Sub
* Apache Beamと言えば、Cloud Dataflow
* Apache Airflowと言えば、Cloud Composer
* Hadoop環境の移行はDataproc
* HadoopのHDFSの移行はCloud Storage
* パイプラインの黄金パターンは、Cloud Pub/Sub → Cloud Dataflow → BigQuery
* BigQueryのチューニングの基本は、パーティショニングとクラスタリング
* RDBMSの移行を容易にするには、Cloud SQL
* 新規に大規模なトランザクションシステムを構築する場合は、Cloud Spanner
* データポータルでの可視化が必要であれば、分析はBigQuery
* 時系列データはCloud Bigtable
* コスト削減と言えばCloud Storage、プリエンプティブル VM
* 非エンジニア向けのデータ加工はCloud Dataprep
* オーケストラレーションと言えば、Cloud Composer
* マルチクラウドまわりは、Cloud Composer、Anthos
* 地理空間データの分析はBigQuery
* メッセージングデータ、Cloud Pub/Sub　→　Bigtable

## 参考資料
* [Google Cloud ソリューション](https://cloud.google.com/solutions/?hl=ja)
* [ドキュメント](https://cloud.google.com/docs/?hl=ja)
* [Professional Cloud Architect](https://cloud.google.com/certification/practice-exam/cloud-architect)
* [AWSプロフェッショナルのためのGCP](https://cloud.google.com/docs/compare/aws/?hl=ja)
* [Azure プロフェッショナルのためのGCP](https://cloud.google.com/docs/compare/azure/?hl=ja)
* [CloudOnAir](https://inthecloud.withgoogle.com/jp-onair-19/archive.html)
* [codelabs](https://codelabs.developers.google.com/)
* [GCPUG](https://gcpug.jp/about)
* [1 行でわかる Google Cloud Platform](https://lp.google-mkto.com/rs/248-TPC-286/images/GCP_clearfile_A4_for_PaperPrint.pdf)
* [topgate](https://www.topgate.co.jp/gcp07-how-to-start-docker-image-gke)
* [tech-run](https://www.tech-run.net/ja/contents/gke)
* [](https://cloud.google.com/blog/ja/topics/developers-practitioners/dataproc-best-practices-guide)
* []()

### Qwiklabs
    ラボ用のユーザーIDとパスワードでログインする
* [](https://google.qwiklabs.com/focuses/1734?locale=ja&parent=catalog)
* [](https://google.qwiklabs.com/catalog?format%5B%5D=courses&utm_source=cloud-dot-google&utm_medium=website)

### coursera
* [coursera_1](https://www.coursera.org/learn/gcp-fundamentals-aws)
* [coursera_2](https://www.coursera.org/specializations/gcp-architecture-jp)

* Colaboratory
* Google Research Football Environment

* Cloud Console
* Cloud Identity-Aware Proxy(IAP)


* Android Enterprise
* Cloud Identity
  + https://cloud.google.com/docs/authentication/end-user?hl=ja
1. Googleの「API Console」に自分のアプリを登録
2. 「API Console」でOAuth2認証で必要な情報を集める（Client ID、Client Secret, Redirect URIs）
3. 「OAuth 2.0 Playground」を使って許可範囲（scope）を決定する
4. 集めた情報を使ってWebViewでOAuth2認証ページを表示する
5. OAuth2認証ページでユーザー自身でアプリケーションからの接続の許可をしてもらう
6. ユーザー許可後のページタイトルから「code」を取得する
7. 「code」を使って「アクセストークン」を取得する

### Google Cloud INSIDE Digital

### Links
https://cloud.google.com/blog/ja/topics/training-certifications/expanding-at-home-learning
https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=19&cad=rja&uact=8&ved=2ahUKEwiT1KDYpefoAhXO-GEKHWcYBQY4ChAWMAh6BAgJEAE&url=https%3A%2F%2Fwww.udemy.com%2Fcourse%2Fgoogle-jp-ai%2F&usg=AOvVaw16i60ECWey0P7AJdqM-QJD
