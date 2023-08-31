
## Q. 1-1
Cloud Run にデプロイされた一連の REST API エンドポイントの負荷テストを行う必要があります。
API は HTTP POST リクエストにレスポンスします。
負荷テストは次の要件を満たす必要があります。

* ロードは複数の並列スレッドから開始されます。
* API へのユーザートラフィックは複数の送信元 IPアドレスから発信されます。
* 負荷は追加のテストインスタンスを使用してスケールアップできます。

Google が推奨するベスト プラクティスに従います。
負荷テストをどのように構成するべきでしょうか？
1. cURLがインストールされたイメージを作成し、テスト計画を実行するようにcurlを構成します。マネージドインスタンスグループにイメージをデプロイし、VMごとにイメージの1つのインスタンスを実行します
2. cURLがインストールされたイメージを作成し、テスト計画を実行するようにcurlを構成します。イメージを非マネージドインスタンスグループにデプロイし、VMごとにイメージの1つのインスタンスを実行します
3. 負荷分散テストフレームワークをプライベートGKEクラスタにデプロイします。必要に応じて追加のPodをデプロイしてより多くのトラフィックを開始し、同時ユーザ数をサポートします。
4. CloudShellで分散負荷テストフレームワークのコンテナイメージをダウンロードします。CloudShellでコンテナの複数のインスタンスを順番に開始してAPIの負荷を増やします。
<details><div>
    答え：
</div></details>

## Q. 1-2
新しいコンテナ イメージの構築を自動化するために、Cloud Build を使用して継続的インテグレーションパイプラインを構成しています。
このパイプラインでは、ソースコードからアプリケーションを構築し、単体テストと統合テストを別々のステップで実行した後、コンテナを Artifact Registry に push します。
コンテナ ビルド ファイルは次のとおりです。
```
FROM python:3.7-alpine
COPY . /app
WORKDIR /app
RUN pip install -r reuirements.txt
CMD [ "gunicorn", "-w 4", "main:app" ]
```
あなたは、Cloud Build での処理に予想より時間がかかることに気づきました。
ビルド時間を短縮するにはどうすればよいですか。 ２つ選択してください。
1. CloudBuildを実行する仮想マシンのCPU割り当てを増やす
2. VPC内のGCE VMにContainerRegistryをデプロイし、これを使用して最後のイメージを保存する
3. ビルド構成ファイルで--chache-from引数を使用して、以降のビルドのコンテナイメージをキャッシュに保存する
4. ビルドファイル内のベースイメージをubuntu:latestに変更し、パッケージマネージャユーティリティを使用してPython3.7をインストールする
5. CloudStorageにアプリケーションソースコードを保存し、gutilを使用してソースコードをダウンロードするようにパイプラインを構成する
<details><div>
    答え：
</div></details>

## Q. 1-3
Cloud Source Repositories と Cloud Build を使用して Python アプリケーションを Cloud Run にデプロイしています。
Cloud Build パイプラインを以下です。
```
steps:
    name: python
    entrypoint: pip
    args: ["install", "-r", "requirements.txt", "--user"]
    name: 'gcr.io/cloud-builders/docker'
    args: ['build', '-t'],
        'us-centrall-docker.pkg.dev/$(PROJECT_ID)/${_REPO_NAME}/myimage: $(SHORT_SHA)',?'
name: gcr.io/cloud-builders/docker'
    args: ['push', 'us-centrall-docker.pkg.dev/${PROJECT_ID}/$(_REPO_NAME)/myimage: $(SHORT_SHA)']
name: google/cloud-sdk
    args: ['gcloud', 'run', 'deploy', 'helloworld-$(SHORT_SHA)', --image-us-centrall-docker.pkg.dev/$(PROJECT_ID)/$(_REPO_NAME)/myimage: $ (SHORT_SHA)', --region', 'us-centrall', '--platform', 'managed',--allow-unauthenticated']
```
デプロイ時間を最適化し、不要な手順を回避したいと考えています。
どうすればいいでしょうか？
1. コンテナをArtifactregistryにプッシュするステップを削除します
2. 新しいDockerレジストリをVPCにデプロイし、VPC内でCloudBuildワーカープールを使用してビルドパイプラインを実行します
3. CloudRunインスタンスと同じリージョンにあるCloudStorageバケットにイメージアーティファクトを保存します
4. --chache-from引数をビルド構成ファイルのDockerビルドステップに追加します
<details><div>
    答え：
</div></details>

## Q. 1-4
Google Cloud ランタイムで実行されるように設計されたウェブ アプリケーションを作成しています。
このアプリケーションによって、ユーザーのアカウント ドメインがどれであるかに関係なく、そのユーザーのドライブにファイルが書き込まれるようにします。
Google Drive API への認証を行うようにアプリケーションを構成する必要があります。
どうすればよいですか。
1. ドメイン全体の権限が委任されたOauthクライアントIDを使用する
2. ドメイン全体の権限が委任されたサービスアカウントを使用する
3. OauthクライアントIDとhttps://www.googleapis.com/auth/drive.fileスコープを使用して、各ユーザのアクセストークンを取得する
4. サービスアカウントとhttps://www.googleapis.com/auth/drive.fileスコープを使用して、各ユーザのJWTを取得する
<details><div>
    答え：
</div></details>

## Q. 1-5
Java アプリケーションを Cloud Run にデプロイしました。
アプリケーションは Cloud SQL でホストされているデータベースにアクセスする必要があります。
規制要件により、Cloud SQL インスタンスへの接続には内部 IP アドレスを使用する必要があります。
Google が推奨するベスト プラクティスに従って、接続をどのように構成するべきでしょうか？
1. CloudSQL接続を使用してCloudRunサービスを構成します
2. サーバレスVPCアクセスコネクタを使用するようにCloudRunサービスを構成します
3. CloudSQLJavaコネクタを使用するようにアプリケーションを構成します
4. CloudSQLAuthProxyのインスタンスに接続するようにアプリケーションを構成します
<details><div>
    答え：
</div></details>

## Q. 1-6
Cloud Run にデプロイされているアプリケーションが、大量のトラフィックを受信しています。
アプリケーションに変更をデプロイすると、全ユーザーに悪影響が及ぶことが懸念されます。
費用の問題から全環境での負荷テストは避けながら、できるだけ早く新機能をデプロイする必要があります。
適切なアプローチはどれですか。
1. 本番環境のアプリケーションに対して週次の負荷テストをスケジュールする
2. ローカルの開発環境を使用して、外部で負荷テストを行う
3. ユーザーに新機能へのアクセスを許可する前に、新バージョンとしてデプロイしてスモークテストを行う、その後、全ユーザーが新機能にアクセスできるようにする
4. トラフィック分割機能を使用して一部のユーザーに新機能をテストしてもらい、徐々にトラフィック分割を調整しつつ、最終的に全ユーザーが新機能にアクセスできるようにする
<details><div>
    答え：
</div></details>

## Q. 1-7
チームは Google Kubernetes Engine (GKE) で実行されるアプリケーションのビルド パイプラインを構築しています。
セキュリティ上の理由からパイプラインによって生成されたイメージのみを GKE クラスタにデプロイする必要があります。
Google Cloud サービスのどの組み合わせを使用しますか？
1. CloudBuild,CloudStorage,BinaryAutorization
2. CloudDeploy,Cloudstorage,CloudArmor
3. CloudDeploy,Artifactregistory,CloudArmor
4. CloudBuild,Artifactregistory,BinaryAutorization
<details><div>
    答え：
</div></details>

## Q. 1-8
MySQL リレーショナル データベース スキーマを使用する Google Cloud でホストされるアプリケーションを開発しています。
アプリケーションには、データベースへの大量の読み取りと書き込みがあり、バックアップと継続的な容量計画が必要になります。
チームにはデータベースを完全に管理する時間がありませんが、小さな管理タスクを引き受けることはできます。
データベースをどのようにホストする必要がありますか？
1. データベースをホストするようにCloudSQLを構成し、スキーマをCloudSQLにインポートします
2. クライアントを使用してGoogleCloudMarketplaceからデータベースにMySQLをデプロイし、スキーマをインポートします
3. データベースをホストするようにCloudBigtableを構成し、スキーマをCloudBigtableにインポートします
4. データベースをホストするようにCloudSpannerを構成し、スキーマをCloudSpannerにインポートします
5. データベースをホストするようにCloudFirestoreを構成し、スキーマをCloudFirestoreにインポートします
<details><div>
    答え：
</div></details>

## Q. 1-9
Google Kubernetes Engine にデプロイされたコンテナがあります。
コンテナの起動が遅い場合があるため、livenessプローブを実装しました。
liveness プローブが起動時に失敗することがあります。
どうすればいいでしょうか？
1. 起動プロープを追加します
2. livenessプロープの初期遅延を増やします
3. コンテナのCPU制限を増やします
4. Readinessプロープを追加します
<details><div>
    答え：
</div></details>

## Q. 1-10
あなたは大規模な組織の開発者です。
Go で記述されたアプリケーションが本番環境の Google Kubernetes Engine (GKE) クラスタで実行されています。
BigQuery へのアクセスを必要とする新しい機能を追加する必要があります。
Google が推奨するベスト プラクティスに従って、BigQuery に GKE クラスタへのアクセスを許可したいと考えています。 どうすればいいでしょうか？
1. BigQueryにアクセスできるGoogleサービスアカウントを作成します。JSONキーをSecretManagerに追加し、Goクライアントライブラリを使用してJSONキーにアクセスします
2. BigQueryにアクセスできるGoogleサービスアカウントを作成します。サービスアカウントのJSONキーをK8sシークレットとして追加し、このシークレットを使用するようにアプリケーションを構成します
3. BigQueryにアクセスできるGoogleサービスアカウントを作成します。サービスアカウントのJSONキーをSecretManagerに追加し、initコンテナを使用して、アプリケーションが使用するシークレットにアクセスします
4. GoogleサービスアカウントとK8sサービスアカウントを作成します。GKEクラスタでWorkloadIdentityを構成し、アプリケーションのDeploymentでK8sサービスアカウントを参照します
<details><div>
    答え：
</div></details>

## Q. 1-11
チームはアプリケーションが実行されている Google Kubernetes Engine (GKE) クラスタを管理しています。
別のチームがこのアプリケーションとの統合を計画しています。
統合を開始する前に他のチームがアプリケーションに変更を加えることはできませんが GKE に統合をデプロイできることを確認する必要があります。
どうすればいいでしょうか？
1. IAMを使用してクラスタプロジェクトに対するViewerIAMロールをほかのチームに付与します
2. 新しいGKEクラスタを作成します。IAMを使用してクラスタプロジェクトに対する編集者ロールをほかのチームに付与します
3. 既存のクラスタに新しい名前空間を作成します。IAMを使用してクラスタプロジェクトに対する編集者ロールをほかのチームに付与します
4. 既存のクラスタに新しい名前空間を作成します。K8sのロールベースのアクセス制御を使用して、新しい名前空間に対する管理者のロールをほかのチームに付与します
<details><div>
    答え：
</div></details>

## Q. 1-12
Terraform を使用してラップトップから Google Cloud にリソースをデプロイする必要があります。
Google Cloud 環境のリソースはサービスアカウントを使用して作成する必要があります。
Cloud Identity には roles/iam.serviceAccountTokenCreator の Identity and Access Management (IAM) ロールと Terraform を使用してリソースをデプロイするために必要な権限があります。
Google が推奨するベストプラクティスに従って必要なリソースをデプロイするように開発環境を構築したいと考えています。
どうすればいいでしょうか？
1. サービスアカウントのキーファイルをJSON形式でダウンロードし、ラップトップに保存します。GOOGLE_APPLICATION_CREDENTIALS環境変数をダウンロードしたキーファイルのパスに設定します
2. 
3. 
4. 
<details><div>
    答え：
</div></details>

## Q. 1-13
機密性の高い非構造化データ オブジェクトを Cloud Storage バケットに保存してアクセスするアプリケーションを開発しています。
規制要件に準拠するには最初の作成から少なくとも 7 年間はすべてのデータオブジェクトを利用できるようにする必要があります。
3 年以上前に作成されたオブジェクトへのアクセスは非常にまれです (1年に 1回未満)。
ストレージコストを最適化しながらオブジェクトストレージを構成する必要があります。
どうすればいいでしょうか？ (回答は 2 つ)
1. バケットに7年間の保持ポリシーを設定します
2. IAM Conditions を使用してオブジェクトの作成日から7年後にオブジェクトへのアクセスを提供します
3. オブジェクトのバージョニングを有効にしてオブジェクトの作成後7年間、オブジェクトが誤って削除されるのを防ぎます
4. 3年後にオブジェクトを標準ストレージからArchiveSotrageに移動するバケットにオブジェクトライフサイクルポリシーを作成します
5. バケット内の各オブジェクトの経過時間を確認し、3年以上経過したオブジェクトをArchiveStorageを使用して毎日のスケジュールでCloudFunctionsをトリガーします
<details><div>
    答え：
</div></details>

## Q. 1-14
最近、Cloud Run で新しいサービスを開発しました。
新しいサービスはカスタム サービスを使用して認証し、トランザクション情報を Cloud Spanner データベースに書き込みます。
発生するボトルネックを特定しながら、アプリケーションが最大 5,000 の読み取り/秒 および 1,000 の書き込み/秒 トランザクションをサポートできることを確認する必要があり、テスト インフラストラクチャは自動スケーリングできる必要があります。
どうすればいいでしょうか？
1. テストハーネスを構築してリクエストを生成し、それをCloudRunにデプロイします。CloudLoggingを使用してVPCフローログを分析します
2. 負荷テストを動的に生成するためにLocustまたはJmeterイメージを実行するGKEクラスタを作成します。CloudTraceを使用して結果を分析します
3. Cloudtaskを作成してテスト負荷を生成する。CloudSchedulerを使用して1分あたり60000のCloudtaskトランザクションを10分間実行します。CloudMonitoringを使用して結果を分析します
4. MarketplaceのLAMPスタックイメージを使用するComputeEngineインスタンスを作成し、ApacheBencを使用してサービスに対する負荷テストを生成します。CloudTraceを使用して結果を分析します
<details><div>
    答え：
</div></details>

## Q. 1-15
セキュリティチームは Google Kubernetes Engine で実行されているすべてのデプロイ済みアプリケーションを監査しています。
監査を完了した後、チームは一部のアプリケーションがクラスタ内のトラフィックをクリア テキストで送信していることを発見しました。
アプリケーションへの変更を最小限に抑え、Google からのサポートを維持しながら、すべてのアプリケーショントラフィックをできるだけ迅速に暗号化する必要があります。
どうすればいいでしょうか？
1. ネットワークポリシーを使用し、アプリケーション間のトラフィックをブロックします
2. Istioをインストールし、アプリケーションの名前空間でプロキシインジェクションを有効にしてからmTLSを有効にします
3. アプリケーション内で信頼できるネットワークの範囲を定義し、それらのネットワークからのトラフィックのみを許可するようにアプリケーションを構成します
4. 自動化されたプロセスを使用してアプリケーションのSSL証明書をLet'sEncryptから要求し、それらをアプリケーションに追加します
<details><div>
    答え：
</div></details>

## Q. 
1. 
2. 
3. 
4. 
<details><div>
    答え：
</div></details>

## Q. 
1. 
2. 
3. 
4. 
<details><div>
    答え：
</div></details>

## Q. 
1. 
2. 
3. 
4. 
<details><div>
    答え：
</div></details>

## Q. 
1. 
2. 
3. 
4. 
<details><div>
    答え：
</div></details>

## Q. 
1. 
2. 
3. 
4. 
<details><div>
    答え：
</div></details>

## Q. 
1. 
2. 
3. 
4. 
<details><div>
    答え：
</div></details>

## Q. 
1. 
2. 
3. 
4. 
<details><div>
    答え：
</div></details>

## Q. 
1. 
2. 
3. 
4. 
<details><div>
    答え：
</div></details>

## Q. 
1. 
2. 
3. 
4. 
<details><div>
    答え：
</div></details>
