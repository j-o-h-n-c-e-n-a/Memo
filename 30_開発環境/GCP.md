## 4つのケーススタディ
### 1. 
### 2. 
### 3．
### 4．
### メルカリ
    https://cloud.google.com/blog/ja/topics/customers/google-cloud-platform-mercari-kubernetes

## 試験ガイド
### 1. クラウド ソリューション アーキテクチャの設計と計画
#### 1.1 ビジネス要件を満たすソリューション インフラストラクチャを設計する。以下のような点を考察します。
* ビジネス ユースケースとプロダクト戦略
* 費用の最適化
* アプリケーション設計の支援
* 外部システムとの統合
* データの移動
* 設計上の決定のトレードオフ
* 構築、購入、変更
* 成果の測定方法（重要業績評価指標（KPI）、投資収益率（ROI）、指標など）
* コンプライアンスと可観測性
#### 1.2 技術要件を満たすソリューション インフラストラクチャを設計する。以下のような点を考察します。
* 高可用性とフェイルオーバーの設計
* クラウド リソースの柔軟性
* 成長要件を満たすスケーラビリティ
* パフォーマンスとレイテンシ
#### 1.3 ネットワーク、ストレージ、コンピューティング リソースを設計する。以下のような点を考察します。
* オンプレミス環境またはマルチクラウド環境との統合
* クラウド ネイティブ ネットワーキング（VPC、ピアリング、ファイアウォール、コンテナ ネットワーキング）
* データ処理技術の選択
* 適切なストレージ タイプの選択（オブジェクト、ファイル、RDBMS、NoSQL、NewSQL など）
* コンピューティング リソースの選択（プリエンプティブ、カスタム マシンタイプ、特殊なワークロードなど）
* プラットフォーム プロダクトへのコンピューティング ニーズのマッピング
#### 1.4 移行計画を作成する（ドキュメントやアーキテクチャ図など）。以下のような点を考察します。
* 既存システムとソリューションの統合
* ソリューションをサポートするためのシステムおよびデータの移行
* ライセンスのマッピング
* ネットワーク計画
* テストと概念実証
* 依存関係の管理の計画
#### 1.5 将来のソリューションの向上を想定する。以下のような点を考察します。
* クラウドおよび技術の向上
* ビジネスニーズの進化
* 普及活動と提唱

### 2. ソリューション インフラストラクチャの管理とプロビジョニング
#### 2.1 ネットワーク トポロジを構成する。以下のような点を考察します。
* オンプレミスへの拡張（ハイブリッド ネットワーキング）
* マルチクラウド環境への拡張（GCP 間の通信を含む）
* セキュリティとデータの保護
#### 2.2 ストレージ システムを個別に構成する。以下のような点を考察します。
* データ ストレージの割り当て
* データ処理、コンピューティングのプロビジョニング
* セキュリティとアクセスの管理
* データ転送とレイテンシを考慮したネットワーク構成
* データ保持とデータ ライフサイクルの管理
* 拡大するデータの管理
#### 2.3 コンピューティング システムを構成する。以下のような点を考察します。
* コンピューティング システムのプロビジョニング
* コンピューティングの変動性の構成（プリエンプティブル vs. 標準）
* コンピューティング ノードのネットワーク構成
* インフラストラクチャのプロビジョニング テクノロジーの構成（Chef、Puppet、Ansible、Terraform、Deployment Manager など）
* Kubernetes によるコンテナのオーケストレーション

### 3. セキュリティとコンプライアンスを考慮した設計
#### 3.1 セキュリティを考慮して設計する。以下のような点を考察します。
* Identity and Access Management（IAM）
* リソース階層（組織、フォルダ、プロジェクト）
* データ セキュリティ（鍵管理、暗号化）
* ペネトレーション テスト
* 職掌分散（SoD）
* セキュリティ制御（監査、VPC Service Controls、組織のポリシーなど）
* Cloud KMS での顧客管理の暗号鍵の管理
#### 3.2 コンプライアンスを考慮して設計する。以下のような点を考察します。
* 法規制（健康記録のプライバシー、児童のプライバシー、データのプライバシー、所有権など）
* 商用（クレジット カードの情報処理などのセンシティブ データ、個人を特定できる情報（PII）など）
* 業界の認定資格（SOC 2 など）
* 監査（ログを含む）
### 4.技術プロセスやビジネス プロセスの分析と改善
#### 4.1 技術プロセスを分析、定義する。以下のような点を考察します。
* Software Development Lifecycle Plan（SDLC）
* 継続的インテグレーション、継続的デプロイ
* トラブルシューティング、事後分析の方法
* テストと検証
* サービス カタログとプロビジョニング
* ビジネスの継続性と障害復旧
#### 4.2 ビジネス プロセスを分析、定義する。以下のような点を考察します。
* ステークホルダー管理（影響と便宜）
* チェンジ マネジメント
* チームの評価、スキルの準備
* 意思決定プロセス
* お客様の成功管理
* コストの最適化、リソースの最適化（CAPEX / OPEX）
#### 4.3 本番環境でソリューションの復元力を確保する手順を開発する（カオス工学など）

### 5. 実装の管理
#### 5.1 ソリューションを確実に導入できるように開発チームやオペレーション チームに助言する。 以下のような点を考察します。
* アプリケーション開発
* API のベスト プラクティス
* フレームワークのテスト（読み込み、単体、統合）
* データおよびシステムの移行ツール
#### 5.2 GCP SDK（gcloud、gsutil、bq）を使用して Google Cloud を操作する。以下のような点を考察します。
* ローカル インストール
* Google Cloud Shell
### 6 ソリューションとオペレーションの信頼性の確保
#### 6.1 モニタリング、ロギング、プロファイリング、通知ソリューション
#### 6.2 デプロイとリリースの管理
#### 6.3 運用中のソリューションのサポート支援
#### 6.4 品質管理方法の評価


## 参考資料
* [Google Cloud ソリューション](https://cloud.google.com/solutions/?hl=ja)
* [ドキュメント](https://cloud.google.com/docs/?hl=ja)
* [Professional Cloud Architect](https://cloud.google.com/certification/practice-exam/cloud-architect)
* [AWSプロフェッショナルのためのGCP](https://cloud.google.com/docs/compare/aws/?hl=ja)
* [Azure プロフェッショナルのためのGCP](https://cloud.google.com/docs/compare/azure/?hl=ja)
* [CloudOnAir](https://inthecloud.withgoogle.com/jp-onair-19/archive.html)
* [codelabs](https://codelabs.developers.google.com/)
* [coursera](https://www.coursera.org/learn/gcp-fundamentals-aws)
* [GCPUG](https://gcpug.jp/about)
* [1 行でわかる Google Cloud Platform](https://cloud.google.com/blog/ja/products/gcp/google-cloud-platform-paperprint?utm_source=feedburner&utm_medium=feed&utm_campaign=Feed:%2BGoogleCloudPlatformJapanBlog%2B(Google%2BCloud%2BPlatform%2BJapan%2BBlog))
* []()

### Qwiklabs
    ラボ用のユーザーIDとパスワードでログインする
* [](https://google.qwiklabs.com/focuses/1734?locale=ja&parent=catalog)
* [](https://google.qwiklabs.com/catalog?format%5B%5D=courses&utm_source=cloud-dot-google&utm_medium=website)



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
