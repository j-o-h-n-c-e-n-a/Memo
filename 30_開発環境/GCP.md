## テスト概要
    ソリューションインフラストラクチャの設計を満たす
### ビジネス要件
* ビジネスユースケースと製品戦略
* コストの最適化
* アプリケーション設計のサポート
* 統合
* データの移動–データ移行
* トレードオフ
* ビルド、購入、または変更
* 成功の測定（例：主要業績評価指標（KPI）、投資収益率（ROI）、指標）
### 技術的要件
* 高可用性およびフェールオーバー設計
* クラウドリソースの弾力性
* 成長要件を満たすスケーラビリティ
### ネットワーク、ストレージ、およびコンピューティングリソースの設計
* オンプレミス/マルチクラウド環境との統合
* データストレージのニーズの識別とストレージへのマッピングシステム
* データフロー図
* ストレージシステムの構造（オブジェクト、ファイル、RDBMS、NoSQL、NewSQL など）
* コンピューティングニーズをプラットフォーム製品にマッピングする
### 移行計画を作成する
* ソリューションを既存のシステムと統合する
* ソリューションをサポートするためのシステムとデータの移行
* ライセンスマッピング
* ネットワークおよび管理計画
* テストと概念実証
### ソリューションと運用の信頼性の確保
* モニタリング/ロギング/アラートソリューション
* 展開およびリリース管理
* 運用上のトラブルシューティングのサポート
* 品質管理対策の評価
### 設計上の考慮事項
* サービス定義
* マルチティアアーキテクト
* 復元力、スケーラビリティ、可用性、およびHA
* セキュリティ、コンプライアンス-データセキュリティ（プライバシー）、サービス拒否
* キャパシティプランニングとコスト最適化
* SRE –展開、監視、アラート、およびインシデント管理
* サービス測定-SLO、SLA、および主要な指標
### 将来のソリューションの改善を想像する
* クラウドとテクノロジーの改善
* ビジネスニーズの進化
* 伝道と擁護

## 4つのケーススタディ
### 1. Mountkirk Games
#### ユースケースの理解と要約
    https://cloud.google.com/certification/guides/cloud-architect/casestudy-mountkirkgames-rev2/?hl=ja

* 大規模な初期費用なしで拡張性と可用性の高いインフラストラクチャ
* 懸念事項を考慮し、次のパラメータを使用してインフラストラクチャの設計を開始できます
  + サービス定義
  + マルチティアアーキテクト
  + 弾力性、スケーラビリティ、可用性、HA
  + セキュリティ、コンプライアンス-データセキュリティ（プライバシー）、サービス拒否
  + キャパシティプランニングとコスト最適化
  + SRE –展開、監視、アラート、およびインシデント管理
  + サービス測定-SLO、SLA、および主要指標

#### Gaming platform
* Performance
* Custom VM vs Kubernetes, App Engine.
* Auto Scaling
* Saving State
* Persistent Backup
* Sharing information between VM

#### インフラ要件
    以前にクラウド拡張に失敗している
* SLO、SLI、SLAについて
* 私たちはほとんど常に利用できるようにしたい..アプリケーション…
  + 手段 
* SLOの–サービスレベル目標（通常のビジネス要件）..ゲームバックエンドは少なくとも98.0％の時間で利用可能である必要があります
  + これらをどのように測定するのか->インジケータで..
* SLI –ゲームアプリケーションはバックエンドサーバーに接続できます…-これをどのように測定しますか？
  + バックエンドに問題が発生した場合にサポートする人は責任を負いませんか…
  + 大陸のすべてのユーザーは、昼間または24時間以内に使用しますか？
  + 開始するためのいくつかの仮定を行います…。

#### Compute Service Options
    動的なスケールアップ・ダウン、カスタマイズされたLinuxで動作する
##### 仮想マシン
* OSを自由にカスタマイズできます。
* 自動スケーリングと負荷分散を使用する
* CDNをサポート
* <u>自分で仮想マシンを管理する必要があります..</u>
* <u>自動スケーリングポリシーを定義する必要があります</u>
##### App Engine
* 無限にスケーラブルなアプリケーションバックエンドを持つことができます。
* Opsプラットフォームなし
  - コードをデプロイする開発者プラットフォーム
* 標準（サンドボックスランタイム）とフレキシブル（Docker）オプション
* <u>OSをカスタマイズするオプションはありません</u>
##### コンテナエンジン
* GCPでKubernetesを実行する
* プラットフォームに依存しない
* スマートデフォルトと制御リソースを備えています-CPU / RAM
* <u>アプリケーションはコンテナ化する必要があります..</u>
* <u>クラスターを管理する必要があります</u>
##### クラウド機能
* イベントベース..
* 操作なし、サーバーレス。
* <u>プログラミング環境の限られた選択</u>
* <u>低遅延ではありません</u>

#### Database Service Options
    マネージドNoSQLデータベースに接続する
    どのデータベースサービスを選択するべきか、FAQがある
##### Cloud SQL
* リレーショナルデータベース、ACID-> MySQL –最大10 TB
* 複数のリードレプリカ
* ユースケース：CMS、金融、eコマース
* <u>厳格なスキーマ</u>、
* <u>水平方向のスケーラビリティの制限</u>
##### データストア
* マネージド、ドキュメント指向のNoSqlデータベース
* 水平方向にスケーラブルで、最終的に一貫性があり、低レイテンシ
* 半構造データに対応
* 使用例：ユーザープロファイル、状態ストレージ
* <u>OSをカスタマイズするオプションはありません</u>
##### Cloud Spanner
* 水平方向に拡張可能な高可用性リレーショナルデータベース
* 使用例：水平方向のスケーラビリティを備えたRDBMS
* <u>構造化データで動作します…</u>
##### Cloud BigTable
* 完全に管理された低遅延、列指向データベース
* ユースケース：アドテック、ファイナンス、IOT
* <u>構造化データのみで動作します</u>
* <u>低遅延ではありません</u>
##### Cloud BigQuery
* 拡張性の高い管理されたEDW
* OLAPワークロードとペタバイト規模まで
* ユースケース：EDW、BI Analytics、Data Science、BigData SQLを使用します。
* 制限事項…。

#### Storage Service Options
##### クラウド永続ディスク、ローカルSSD、Ramディスク
* VMストレージ、VM間の共有、サイズに応じたスケーリング、ソフトウェアをインストールする、Blob Storage
* <u>Commuteサービスからのみ使用</u>
##### クラウドストレージ
* ファイルストレージのようなオブジェクトストレージ
* 高い拡張性と耐久性
* 地域および多地域で利用可能
* 使用例：構造化されていないデータ、画像、動画、
* OSまたはソフトウェアをインストールすることはできません。
* 次のディレクトリにはできません
##### モバイル– Firebaseのクラウドストレージ
* ドキュメントSQLデータベースなし
* 水平方向にスケーラブルで、最終的に一貫性がある
* プラットフォームに依存しない
* <u>アプリケーションはコンテナ化する必要があります..</u>
* <u>クラスターを管理する必要があります</u>
##### Firebase Realtime DBとホスティング
* すべてのモバイルアプリケーションデータの同期ユーザー
* <u>特定の目的に使用されます。</u>

#### BIと分析
##### Big Table–ユーザーセッションとゲームデータ
* マネージドサービス
* 低遅延および水平方向にスケーラブル
* 半構造文書データベース…
##### クラウドストレージ
* 画像、製品ビデオ、バックアップおよび長期アーカイブ
##### Cloud BigQuery for Analytics ..

#### スケーラビリティ
##### Compute Engineインスタンスの考慮事項
    カスタムと事前定義
* ラージインスタンスとスモールインスタンス
  + メモリとCPUのニーズ-高CPU、高メモリ、標準など
  + ローカルSSDと永続ディスク-高IOPSと永続性
  + vCPUとCPU
* *プリエンプティブマシンタイプ
  + バッチ作業として実行でき、再開できる作業。
  + 賞–画像…
* ネットワークスループット-> -vCPU-> 2gbps
* ディスクサイズ/タイプvs IOPS-> SSD vs HDD
* その他
  + ライブ移行アクション、自動再起動、起動およびシャットダウン
  + ダウンスクリプト–テンプレート
##### 自動スケーリング ニーズ
* インスタンステンプレートとインスタンスグループ。
  + OSのカスタマイズが必要です-カスタムイメージを意味します
##### 自動スケーリング ポリシー 
* 起動時に必要なサーバーの数そして、いくつの地域で...
  + ゲームは世界全体または世界の一部
  + あなたはいくつかから始めることができます...
#### HA
##### 負荷分散
* 地域 対 多地域 - グローバル
* HTTP（s）またはTCPまたはSSH、内部 vs 外部
* ビジネス要件をご覧ください…
##### CDN
* リアルタイムでゲームにプッシュされる静的コンテンツを使用していますか？
* バックエンドからの負荷がどれだけ削減され、トラフィックトラフィックがCDNコストよりも削減

#### キャパシティプラン, コスト管理
* 十分–これらのパラメーターの多くは、ニーズに基づいて調整できます!!!!
  + インスタンスタイプ、Auto Scalingポリシー、水平スケーリングと垂直スケーリング、マルチリージョン可用性、ディスクIP、ネットワークパフォーマンスなどなど。
* 基本的な最小から開始します。ビジネス戦略に基づいて…立ち上げ当初は、マルチは必要ありません
* 地域または大規模なインスタンス..

#### 失敗の設計
* 状態をどこかに..そして、できる限りステートレスなプロセスを構築します…
* SPOFなし…設計– N + 1またはN + 2…複数の小型マシンと少数の大型マシンに焦点を当てるマシン..
* カスケードの失敗を避ける…。
* サービスの設計が低下します…過負荷の場合…12ファクターを見てください。
* 失敗に備える
* 事前に準備する.. SLOを定義する...失敗にどう対処するか..

#### 復元力と高可用性
* マルチゾーン
* マルチリージョン
* レプリケーション
* デプロイメントマネージメント
* テストDR
* 復元するプロセスを定義およびテストする

#### セキュリティとコンプライアンス
* マルチプロジェクト
* ネットワークVPC
  + NATゲートウェイ
  + 踏み台サーバー
* サブネット
  + グループ
  + Firewallルール
* 攻撃の種類
  + DDOS
* IAMとサービスアカウント
* 暗号化
  + KMS
  + カスタムキー
  + キーローテーション
  + キー暗号化
  + セキュリティスキャナー
* 要塞サーバーとNATゲートウェイ

### 2. TerramEarth
    https://cloud.google.com/certification/guides/cloud-architect/casestudy-terramearth-rev2/?hl=ja
* Upload Performance – Zip file ftp of stream – What technology you choose for tera byte data
* Machine Learing for fuel efficiency to adjust parameter
* Connect Machines
* Upload frequency
* ftp server to data warehouse performance
* Analytics
* Binary vs csv file upload vs stream
* Machine to Machine Communications – IPV6 , Secure Channel , trusted platform ModuleTPM. Do not trust all other components etc
* Increase performance – from 20% connected to 80% connected , ftp to stream, CSV to binary data etc

### 3．Dress4Win
    https://cloud.google.com/certification/guides/cloud-architect/casestudy-dress4win-rev2/?hl=ja
* Network Connection – VPN
* Mobile Application – Millions request – what option do you choose forbackend?
* Upload and process Image
### メルカリ
    https://cloud.google.com/blog/ja/topics/customers/google-cloud-platform-mercari-kubernetes


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
