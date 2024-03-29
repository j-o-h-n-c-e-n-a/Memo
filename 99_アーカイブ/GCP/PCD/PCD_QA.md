
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
    答え：４
    (1) 負荷テストのベスト プラクティス　https://cloud.google.com/run/docs/about-load-testing?hl=ja
「API へのユーザートラフィックは複数の送信元 IPアドレスから発信されます」 「負荷は追加のテストインスタンスを使用してスケールアップできます」
A, B はスケールアップのことが記述されていないので、除外できます。
C は「複数の送信元 IPアドレスから発信」という点で条件を満たさないでしょう。
D はCloud Shell自体が負荷テストを行っているわけではなく、負荷テストを行うインスタンスを徐々に増やすオペレーションをしています。
複数のCoupute Engineから負荷テストを行うことは、実行環境としては最も安定した方法であり複数のIPアドレスから発信されるという条件も満たしています。
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
    答え：１，３
    (1) ビルドを高速化する際のおすすめの方法　https://cloud.google.com/build/docs/optimize-builds/speeding-up-builds?hl=ja
    (2) ビルド用の vCPU を増やす　https://cloud.google.com/build/docs/optimize-builds/increase-vcpu-for-builds?hl=ja
A は正解です。高 CPU 仮想マシンタイプにすると短時間でビルドできるようになります。
B は不正解です。VM に Container Registry をデプロイしてもビルドは高速になりません。
C は正解です。以降のステップで、テストとレジストリへの push のために同じコンテナが使用されます。
D は不正解です。Ubuntu コンテナ イメージは python:3.7-alpine イメージよりもはるかに大きくなります。
E は不正解です。Cloud Storage にアプリケーション ソースコードを保存しても、アプリケーションをビルドする時間は短縮されません。
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
    答え：４
    (1) キャッシュされた Docker イメージの使用　https://cloud.google.com/build/docs/optimize-builds/speeding-up-builds?hl=ja#using_a_cached_docker_image
Artifact Registry(もしかしたらまだ馴染みが薄いかもしれませんが、Google Container Registry(GCR)と同等のものです(GCRの上位の機能)) へのプッシュは極通常のステップであり、削除するべきものではありません。
Aではないです。
「新しい Docker レジストリを VPC にデプロイし」初耳の行いですね。
Bは有無を言わさず除外です。
「Cloud Storage バケットにイメージアーティファクトを保存」これも初耳です。
Cも有無を言わさず除外です。
正解はD しかないです。
Reference に示した資料を参照しておきましょう。
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
    答え：３
    (1) OAuth 2.0 を使用した Google API へのアクセス　https://developers.google.com/identity/protocols/oauth2?hl=ja
A は不正解です。OAuth クライアント ID にはドメイン全体の権限を付与できません。
B は不正解です。機能するユーザーが限定されます（委任されたドメイン全体の権限を付与した元のドメインのユーザーのみ）。
C は正解です。OAuth 2.0 ウェブ認可はすべてのユーザーに対して機能する一方、ドメイン委任は単一のドメインに対してのみ機能します。
D は不正解です。ユーザーのドライブには書き込まれません。
また、署名付き JWT を使用して Drive API に対して認証することはできません。    
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
    答え：２
    (1) Cloud Run から接続する　https://cloud.google.com/sql/docs/mysql/connect-run?hl=ja　の「Cloud SQL への接続」の「プライベートIP」タブを参照
「規制要件により、Cloud SQL インスタンスへの接続には内部 IP アドレスを使用する」とのことですので、C, Dは除外です。
Aは何を言っているのか分かりません。Referenceに示した公式資料に記載があるので、正解は B です。
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
    答え：４
    (1) ロールバック、段階的なロールアウト、トラフィックの移行　https://cloud.google.com/run/docs/rollouts-rollbacks-traffic-migration?hl=ja#split-traffic
A は不正解です。パターン化された A/B テストの実施方法があるため、定期的に個別の負荷テストを行う必要性は小さくなります。
B は不正解です。本番環境が正確にシミュレートされません。
C は不正解です。説明にあるとおり、スモークテストでは新機能をすぐに全ユーザーに公開することになります。
D は正解です。トラフィック分割により、全ユーザーに影響を与えることなく実際のユーザーによるテストを行うことができ、負荷テストの費用を削減できます。    
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
    答え：４
「ビルド パイプラインを構築」という事で、このパイプラインに関係するのは
Cloud Build：
    Cloud Source Registory へのソースのコミット等をトリガーにビルドパイプラインを開始したりcloudbuild.yml等を使って各種操作が実行できます。
Artifact Registry：
    ビルドしたコンテナイメージを保持するサービスです。
    ほぼ同じ機能のGoogle Container Registry (GCR)が先行して使われており有名ですが、数年前より GCRから Artifact Registryへの移行が推奨されています。
    GCRでできる事は出来るGCRよりも上位のサービスですので、知らなかった方は押さえておいて下さい。
Binary Authorization:
    GCRやArtifact Registryにコンテナイメージを保存する際に脆弱性チェックを自動的に行い、チェックが完了していることを保証します。
    Cloud StorageやCloud Armorは特にビルドパイプラインには必要がありません。
以上より、GKEクラスタへのデプロイに関連するサービスの組み合わせは、D が正解です。
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
    答え：１
「MySQLリレーショナルデータベーススキーマを使用する」とありますので、CloudSQLのMySQLを使うで決まりです。
CloudSQL(MySQL)というマネージドサービスがあるので、VM(GCE)にMySQLを使うという使い方はほぼしません。
Bはすぐに除外できます。
C, D, E は全てNoSQLですので、これもすぐに排除できます。（この問題は簡単です）
正解は A です。
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
    答え：１
説明
    (1) Kubernetes のベスト プラクティス: readiness プローブと liveness プローブを使用したヘルス チェックの設定　https://cloud.google.com/blog/products/containers-kubernetes/kubernetes-best-practices-setting-up-health-checks-with-readiness-and-liveness-probes
    (2) Liveness、Readiness、および Startup プローブの構成　https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/
AかBかで非常に悩む問題です。
Reference (2) の資料に「デッドロックに対する迅速な反応を損なうことなくLiveness Probeのパラメーターを設定することは難しい場合があります。」 とあるので、initialDelaySeconds での設定が難しいケースがあるものと思います。
そのような場合に、Startupプローブの設定が有効と記述されていますので、A を正解とします。
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
    答え：４
    (1) Workload Identity　https://cloud.google.com/kubernetes-engine/docs/concepts/workload-identity?hl=ja#what_is
直接的に各種キーを扱うよりも Workload Identity を利用する認証方法が「Google が推奨するベストプラクティス」です。
従って D が正解です。(Workload Identityの記述が選択肢の中に１つしかないなら、ほぼそれが正解です）
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
    答え：４
    (1) アクセス制御　https://cloud.google.com/kubernetes-engine/docs/concepts/access-control?hl=ja#rbac
    (2) ロールベースのアクセス制御を使用してクラスタでアクションを認可する　https://cloud.google.com/kubernetes-engine/docs/how-to/role-based-access-control?hl=ja
Aは不正解です。Viewerでは統合の為の変更作業ができないでしょう。
Bは不正解です。別クラスタを作成してしまってはテストにならないでしょう。
Cは不正解です。「クラスタプロジェクトに対する編集者の役割」付与してしまっては名前空間を作成した意味が薄れます。既存環境を不用意に変更してしまう可能性があり、推奨される方法とは思えません。
Dは正解です。RBACを使用することで、1つの名前空間内のリソースに対するアクセス権を定義できるので、安全に確認をする事ができます。
</div></details>

## Q. 1-12
Terraform を使用してラップトップから Google Cloud にリソースをデプロイする必要があります。
Google Cloud 環境のリソースはサービスアカウントを使用して作成する必要があります。
Cloud Identity には roles/iam.serviceAccountTokenCreator の Identity and Access Management (IAM) ロールと Terraform を使用してリソースをデプロイするために必要な権限があります。
Google が推奨するベストプラクティスに従って必要なリソースをデプロイするように開発環境を構築したいと考えています。
どうすればいいでしょうか？
1. サービスアカウントのキーファイルをJSON形式でダウンロードし、ラップトップに保存します。GOOGLE_APPLICATION_CREDENTIALS環境変数をダウンロードしたキーファイルのパスに設定します
2. コマンドラインから次のコマンドを実行します。gcloud config set auth/impersonate_service_account service-account-name@project.iam.gserviceaccount.com。GOOGLE_OAUTH_ACCOUNT_TOKEN 環境変数をgcloud auth print-access-token コマンドによって返される値に設定します
3. コマンドラインから次のコマンドを事項します。gcloud auth application-default login。開いたブラウザウィンドウで個人の資格情報を使用して認証します。
4. サービスアカウントのキーファイルをJSON形式でHashicorpValutに保存します。TerraformをVaultと統合してキーファイルを動的に取得し、有効期間の短いアクセストークンを使用してValutに対して認証します
<details><div>
    答え：２
    (1) Using Google Cloud Service Account impersonation in your Terraform code　https://cloud.google.com/blog/topics/developers-practitioners/using-google-cloud-service-account-impersonation-your-terraform-code
A, DはService Accountをローカルに保存する事を前提としているので、ベストプラクティスではありません。
CはCloud クライアントライブラリ、Google API クライアントライブラリ、REST API と RPC API によって使用されるアプリケーションのデフォルト認証情報を設定する方法になり本問題のケースには当てはまりません。
Bの方法は Reference (1)で示されている方法になります。したがって正解は B となります。
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
    答え：１，４
    (1) Cloud Storage　https://cloud.google.com/storage?hl=ja
問題として取り上げられやすく、きちんと押さえていれば確実に正解できる問題なので、Referenceに記載した公式ドキュメントで良く勉強しておきましょう。
選択肢を見ずに、 「ライフサイクル管理を設定して、7年保持、3年以上経過したデータはArchive Storageに変更」という内容を実現する選択肢（2つ）が正解だな、と頭に浮かびます。
これに当てはまるのは、A, D となります。
特にパケットを移動する必要はなく、ストレージの種類を変更できるので、E の処理は必要ありません。
B, Cは要件的に重要な3年後のアクション(コストに影響を与えます）が語られていないのでアウトです。
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
    答え：２
    (1) Google Kubernetes Engine を使用した負荷分散テスト　https://cloud.google.com/architecture/distributed-load-testing-using-gke?hl=ja
想定されるパフォーマンスが出せるかの測定と、負荷環境をスケールできるという点で、B.が要件を満たしています。
A.は指定のパフォーマンスの測定に言及されていません。
C.もパフォーマンスが測定されていません。
D.は自動スケールの要件に合っていません。
従ってB. が正解です。
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
    答え：２
A.は通信がブロックされてしまうので、アプリケーションがこれまで通りに動作しなくなってしまうので、ダメでしょう。
Aは除外。
C.も要件が分かってない内容ですね。「暗号化する必要があります」をやってないので除外です。
D.は「アプリケーションに追加します」がアウトです。
「最小限に抑え」という場合は、ほとんどの場合 =「完全に抑えて」です。
B.が一番楽な方法で、実際にこの要件を満たすことができます。
正解は B です。
なお、現在 Istio on GKEは非推奨となり、現在は　Anthos Service Mesh の利用が推奨されています。
</div></details>

## Q. 1-16
App Engine スタンダード環境と Memorystore for Redis を使用する eコマース Webアプリケーションを開発しています。
ユーザーがアプリにログインするとアプリケーションはユーザーの情報 (セッション、名前、住所、設定など) をキャッシュします。
この情報はチェックアウト時にすばやく取得できるように保存されます。
ブラウザでアプリケーションをテストしているときに 502 Bad Gateway エラーが発生します。アプリケーションが Memorystore に接続していないと判断しました。
このエラーの理由は何でしょうか？
1. MemorystoreforRedisインスタンスがパブリックIPアドレスなしでデプロイされました
2. AppEngineインスタンスとは異なるリージョンでサーバレスVPCアクセスコネクタを構成しました
3. DevOpsチームにおるインフラストラクチャのアップデート宙にAppEngineとMemorystore感の接続を許可するファイアウォールルールが削除されました
4. AppEngineインスタンスとは異なる可用性の高いゾーンの別のサブネットでサーバレスVPCアクセスコネクタを使用するようにアプリケーションを構成しました
<details><div>
    答え：２
    (1) レスポンス エラーのトラブルシューティング　https://cloud.google.com/endpoints/docs/openapi/troubleshoot-response-errors?hl=ja
    (2) Virtual Private Cloud　https://cloud.google.com/vpc/docs/serverless-vpc-access?hl=ja
    (3) Memorystore for Redis の概要　https://cloud.google.com/memorystore/docs/redis/redis-overview?hl=ja#connecting
    (4) サーバーレス VPC アクセスを構成する　https://cloud.google.com/vpc/docs/configure-serverless-vpc-access?hl=ja#creating_a_connector
通常Memorystore for Redisは内部の処理のキャッシュとして利用されパブリックIPは無しでデプロイされるのでAは間違いである(A.の記述には特に問題はない）と判断できます。
サーバーレスVPCコネクタ経由でMemorystore に接続する場合、プライベートネットワークで接続するため、パブリックアドレスは必要ありません。
VPCネットワーク通信は別のサブネット間の通信が可能なのでDも間違いと分かります。
B, Cの２択になりますが、Bの記述が完全に問題であると判断できます。
サーバレス VPC アクセス コネクタは同一リージョン内でのみ利用可能です。
C. も通信できない原因としてはあり得ますが、この場合4xx系のエラーになるのではないでしょうか。
問題文に対して特定の原因が設定されている点も違和感があります。
色々なケースを総括する一般的な解答が望ましいと感じます。
この問題に関しては C. よりも Bの方がシンプルで決定的であることから、B を正解として選択します。
</div></details>

## Q. 1-17
Google Kubernetes Engine クラスタ内のさまざまなチームが使用するアプリケーションのリソース共有ポリシーを設計しています。
すべてのアプリケーションが実行に必要なリソースにアクセスできるようにする必要があります。
どうすればいいでしょうか？ (回答は 2 つ)
1. オブジェクト使用でリソースの制限と要求を指定します
2. 各チームの名前空間を作成し、リソースクォータを各名前空間荷添付します
3. LimitRangeを作成して名前空間のデフォルトコンピューティングリソース要件を指定します
4. アプリケーションごとにK8sサービスアカウントを作成し、各KSAを名前空間に割り当てます
5. AutosPolicyControllerを使用してすべての名前空間にラベルアノテーションを適用します。taitsとtolerationsを使用して名前空間のリソース共有を許可します
<details><div>
    答え：２，３
    (1) Kubernetes サービス アカウントを使用する　https://cloud.google.com/kubernetes-engine/docs/how-to/kubernetes-service-accounts?hl=ja
    (2)Kubernetesドキュメント　https://kubernetes.io/ja/docs/concepts/policy/limit-range/
    (3)リソースクォータ　https://kubernetes.io/ja/docs/concepts/policy/resource-quotas/
A, D, E ともリソースへのアクセスは許可されますが、特定アプリケーションが利用可能なすべてのリソースを専有してしまう恐れがあることに対する 対応が行われていないので、状況によっては「すべてのアプリケーションが実行に必要なリソースにアクセスできる」が出来ない可能性があります。
B, C の対応により特定のアプリがリソースを占有してしまう事を防ぐことができます。
正解は B, C となります。
</div></details>

## Q. 1-18
最近、モノリシックアプリケーションをマイクロサービスに分割して Google Cloud に移行しました。
マイクロサービスの 1つは Cloud Functions を使用してデプロイされます。
アプリケーションをモダナイズするときに下位互換性のないサービスの APIに変更を加えます。
元の APIを使用する既存の呼び出し元と新しい APIを使用する新しい呼び出し元の両方をサポートする必要があります。
どうすればいいでしょうか？
1. 基のCloudFunctionsをそのままにして、新しいAPIを使用して2つ目のCloudFunctionsをデプロイします。ロードバランサを使用してバージョン間で呼び出しを分散します
2. 基のCloudFunctionsをそのままにして、変更されたAPIのみを含む2つ目のCloudFunctionsをデプロイします。呼び出しは正しい関数に自動的にルーティングされます
3. 基のCloudFunctionsをそのままにして、新しいAPIを使用して2つ目のCloudFunctionsをデプロイします。CloudEndpointsを使用してバージョン管理されたAPIゲートウェイを提供します
4. 新しいAPIをサポートするためにコードを変更した後、CloudFunctionsを再デプロイします。APIの両方のバージョンに対する要求は呼び出しに腹案れるバージョン識別子に基づいて実行されます
<details><div>
    答え：３
    (1) クイックスタート: ESPv2 を使用して Cloud Functions 用の Cloud Endpoints OpenAPI を設定する　https://cloud.google.com/endpoints/docs/openapi/set-up-cloud-functions-espv2?hl=ja
    (2) API のバージョニング　https://cloud.google.com/endpoints/docs/openapi/versioning-an-api?hl=ja#backwards-incompatible
    (3) Cloud Load Balancing のドキュメント　https://cloud.google.com/load-balancing/docs?hl=ja
バージョン間での呼び出しの分散はロードバランサーでは行わないのでA は不正解です。
リクエストに対して何らかの振り分けを行わないと新しいCloud Functions へのアクセスは発生しないので、Bは不正解です。
Dは、この方法でも可能かもしれませんが、旧処理がのちには廃止される可能性が感じられること、ソフトウェア的に２バージョンの処理書かれている状態はエレガントではないことを考え選択肢から外してよいと思います。
C の方法で対応が可能です。正解は C となります。
</div></details>

## Q. 1-19
HTTP と HTTPS の両方でアクセスでき、Compute Engine インスタンスで実行される Webアプリケーションを開発しています。
アプリのメンテナンスを行うためにリモートラップトップから Compute Engine インスタンスの 1つにSSH 接続する必要がある場合があります。
Google が推奨するベストプラクティスに従いながらインスタンスをどのように構成するべきでしょうか？
1. TCPプロキシロードバランサの背後にあるプライベートIPアドレスを使用して、ComputeEngineのWebサーバインスタンスでバックエンドを設定します
2. ファイアウォールルールを構成して、すべてのメッシュの上り（内向き）トラフィックがComputeEngineのWebサーバに接続できるようにします。各サーバには一意の外部IPアドレスがあります
3. SSHアクセス用にCloudIdentity-AwareProxyAPIを構成します。次にアプリケーションWebトラフィック用のHTTP(S)ロードバランサの背後にあるプライベートIPアドレスを使用してComputeEngineサーバを構成します
4. HTTP(S)ロードバランサの外部にあるプライベートIPアドレスを使用してComputeEngineのWebサーバインスタンスでバックエンドを設定します。パブリックIPアドレスを使用して要塞ホストを設定し、ファイアウォールポートを開きます。要塞ホストを使用してWebインスタンスに接続します
<details><div>
    答え：３
    (1) 高度な方法による Linux VM への接続  https://cloud.google.com/compute/docs/instances/connecting-advanced?hl=ja#cloud_iap
A.の方法ではComputeEngineにプライベートIPしか設定されていないので単純なインターネットアクセスできません。
B.の方法では全ての人にサーバーを公開しているので安全な方法であありません。
C.の方法はIAPを通してプライベートIPに接続できる方法です。
D.は踏み台サーバーがアクセスしたいインスタンスと同一VPC内にないのでアクセスできません。
</div></details>

## Q. 1-20
Google Cloud で実行される有名なステートレス Web アプリケーションを開発しています。
トラフィックがない日もあれば、急増する日もあるなど、ユーザーからのトラフィックは予測不可能できません。
アプリケーションを自動的にスケールアップおよびスケールダウンする必要があり、アプリケーションの実行に関連するコストを最小限に抑える必要があります。
どうすればいいでしょうか？
1. CloudfirestoreをデータベースとしてPythonでアプリケーションを構成します。アプリケーションをCloudRunにデプロイします。
2. CloudfirestoreをデータベースとしてC#でアプリケーションを構成します。アプリケーションをAppEngineフレキシブル環境にデプロイします。
3. CloudfirestoreをデータベースとしてPythonでアプリケーションを構成します。アプリケーションをAppEngineスタンダード環境にデプロイします。
4. CloudfirestoreをデータベースとしてPythonでアプリケーションを構成します。自動スケーリングを使用して、アプリケーションをComputeEngineマネージドインスタンスにデプロイします。
<details><div>
    答え：１
「トラフィックがない日もあれば」、「自動的にスケールアップおよびスケールダウン」、「コストを最小限に抑える」から正解はA.で決まりです。
Cloud Firestoreは使った分だけ料金が発生し、Cloud Runもアクセスが無い場合はゼロスケール（インスタンス0)します。
どちらもスケーリングします。
Bは「App Engineフレキシブル」がゼロスケールしませんので、アクセスが無くても費用が発生します。
Cは、アクセスが無くてもCloud SQLに費用が発生しますしスケーリングに弱いです。（App Engine スタンダードはゼロスケールに対応しています）
Dは「Compute Engine マネージドインスタンスグループ」がゼロスケールに対応していません。
という事で、この問題は迷うことなくA.が正解です。
ちなみにゼロスケールは実際のサービスではその状態からアクセスが発生した時にコールドスタートと言って、立ち上がりに時間がかかりスムーズにアクセスが処理できないことが問題となっています。
仕様的には（理屈上は）ゼロスケールの状態にできるが実際のサービス上は出来ない場合が多いというのが実情の様です。
ただし、こういった試験問題では特別にゼロスケールが問題となるような記述が無い限り、ストレートにゼロスケール出来る事が大きな利点と考えて良いでしょう。
</div></details>

## Q. 1-21
単一の Cloud Pub/Sub トピックにサブスクライブしてメッセージを受信し、対応する行をデータベースに挿入するアプリケーションを設計しています。
アプリケーションは Linux で実行され、プリエンプティブル仮想マシン(スポットVM)を活用してコストを削減します。
正常なシャットダウンを開始するシャットダウンスクリプトを作成する必要があります。
どうすればいいでしょうか？
1. プロセス間シグナルを使用してデータベースから切断するようにアプリケーションプロセスに通知するシャットダウンスクリプトを記述します
2. サインインしているすべてのユーザーにComputeEngineインスタンスがダウンするというメッセージをブロードキャストし、現在の作業を保存してサインアウトするように指示するシャットダウンスクリプトを作成します
3. アプリケーションによって5分ごとにポーリングされる場所にファイルを書き込むシャットダウンスクリプトを作成します。ファイルが読み取られた後、アプリケーションはデータベースから切断されます
4. シャットダウンが進行中であることを通知するメッセージをPub/Subトピックにパブリッシュするシャットダウンスクリプトを作成します。アプリケーションはメッセージを読み取った後、データベースから切断します
<details><div>
    答え：１
    (1) シャットダウン スクリプトの実行　https://cloud.google.com/compute/docs/shutdownscript?hl=ja
シャットダウンの際、シャットダウンスクリプトが実行されるので、C.に記載のようなポーリング処理は必要ない事が分かります。
よってC.は真っ先に選択肢から消せるでしょう。
B.は基本的にサービス中のサーバーにログインして作業をしている事はありませんのでかなり特殊なケースであると考えられます。
このケースをフォローしなくても問題ないでしょう（通常しません）。
正解は AかDに絞られます（やる内容は同じ）が、A.の方が即時性が高く、Dはかなり冗長です。
このためにトピックを用意することは通常行わないでしょう。
ということで、A.が正解となります。
</div></details>

## Q. 1-22
Compute Engine で財務部門用の企業ツールを開発しており、ユーザーを認証して財務部門の人間であることを確認する必要があります。
どうすればいいでしょうか？
1. HTTP(S)ロードバランサのCloudIdentity-AwareProxyを有効にし、財務部門のユーザーを含むGoogleグループにアクセスを制限します。提供されたJSONWebトークンをアプリケーション内で確認します
2. HTTP(S)ロードバランサのCloudIdentity-AwareProxyを有効にし、財務部門のユーザーを含むGoogleグループにアクセスを制限します。財務チームの全員にクライアント側証明書を発行し、アプリケーションで証明書を検証します
3. CloudArmorSecurityPoliciesを構成して企業IPアドレス範囲のみにアクセスを制限します。提供されたJSONWebトークンをアプリケーション内で検証します
4. CloudArmorSecurityPoliciesを構成して企業IPアドレス範囲のみにアクセスを制限します。財務チームの全員にクライアント側証明書を発行し、アプリケーションで証明書を検証します
<details><div>
    答え：１
    (1) Google Cloud Armor の概要　https://cloud.google.com/armor/docs/cloud-armor-overview?hl=ja
    (2) プログラムによる認証　https://cloud.google.com/iap/docs/authentication-howto?hl=ja
Google Cloud Armor は、分散型サービス拒否（DDoS）攻撃や、クロスサイト スクリプティング（XSS）、SQL インジェクション（SQLi）などのアプリケーション攻撃など、さまざまなタイプの脅威から Google Cloud のデプロイを保護するのに役立ちます。
認証を行うものではありませんので、C. D.は正解から外れます。
Reference(2)に記載のアプリケーションへのユーザーアカウントでの認証方法より、Aが正解と分かります。
</div></details>

## Q. 1-23
Cloud クライアントライブラリを使用し、アプリケーション内の画像を Cloud Storage にアップロードしています。
アプリケーションのユーザーはアップロードが完了しないことがあると報告し、クライアント ライブラリは HTTP 504 ゲートウェイ タイムアウト エラーを報告します。
アプリケーションのエラーに対する回復力を高めたいと考えています。
アプリケーションにどのような変更を加える必要がありますか？
1. クライアントライブラリ呼び出しの周りに指数バックオフプロセスを記述します
2. クライアントライブラリ呼び出しの周りに1秒の待機時間のバックオフプロセスを記述します
3. アプリケーションに再試行ボタンを設計し、エラーが発生した場合にクリックするようにユーザーに依頼します
4. オブジェクトのキューを作成し、アプリケーションが10分後に再試行することをユーザーに通知します
<details><div>
    答え：１
    (1) Cloud Storage　https://cloud.google.com/storage/docs/retry-strategy?hl=ja
再試行に関しては一定の時間ではなく、指数バックオフ戦略が標準的なエラー処理方法ですので、固定値を使っている B, Dは除外(Dはちょっと長すぎでしょ)です。
C.も良い気がしますが、なるべくオペレーションの手間を失くす事と、「指数バックオフ」というキーワードがあることから A が正解となります。
</div></details>

## Q. 1-24
エンドユーザーからの要求を処理するアプリケーションを開発しています。
許可されていないユーザーへのアクセスを制限しながら許可されたエンド ユーザーがアプリケーションを介して関数に対して認証できるようにするにはアプリケーションによって呼び出される Cloud Functions を保護する必要があります。
ソリューションの一部として Google ログインを統合し、Google が推奨するベストプラクティスに従う必要があります。
どうすればいいでしょうか？
1. ソースコードリポジトリからデプロイし、ユーザーにrole/cloudfunctions.viewerロールを付与します
2. ソースコードリポジトリからデプロイし、ユーザーにrole/cloudfunctions.invokerロールを付与します
3. gcloudを使用してローカルマシンからデプロイし、ユーザーにrole/cloudfunctions.adminロールを付与します
4. gcloudを使用してローカルマシンからデプロイし、ユーザーにrole/cloudfunctions.developerロールを付与します
<details><div>
    答え：２
最小権限の原則より、C, Dは強すぎと考えられます。
Aのロールでは実行できないので、B が正解となります。
</div></details>

## Q. 1-25
開発チームは Java を使用していくつかの Cloud Functions を構築し、対応する統合およびサービス テストも行いました。
関数をビルドしてデプロイし、Cloud Build を使用してテストを開始します。
Cloud Build ジョブは、コードの検証に成功した直後にデプロイの失敗を報告しています。
どうすればいいでしょうか？
1. ClouodFunctions インスタンスの最大数を確認します
2. CloudBuildトリガーに正しいビルドパラメータがあることを確認します
3. truncated eexponential backoff ポーリング戦略を使用してテストを再試行します
4. CloudBuildサービスアカウントにCloudFunstions開発者ロールが割り当てられていることを確認します
<details><div>
    答え：４
    (1) ビルドエラーのトラブルシューティング　https://cloud.google.com/build/docs/troubleshooting?hl=ja
Aは問題文から無関係と考えられます。
通常１つの用途に1つのCloud Functions （フルマネージドサービス。オートスケール）で、大量のCloud Functionsを利用している状況は読みとれません。除外です。
Cは基本的に正常であるが、状況によっては失敗する可能性があるという状況は読みとれず、原因を探らずただ単にリトライしているので誤りでしょう。除外です。
B, Dは微妙に感じましたが、コードの検証で、ビルドは出来ると捉え、D であると判断します。
正解は D です。
</div></details>

## Q. 1-26
Google Kubernetes Engine (GKE) にデプロイされたアプリケーションの 1つで断続的なパフォーマンスの問題が発生しています。
チームはサードパーティのログソリューションを使用しています。
ログを表示できるように GKEクラスタの各ノードにこのソリューションをインストールします。
どうすればいいでしょうか？
1. サードパーティのソリューションをDaenmonSetとしてデプロイします
2. コンテナイメージを変更して監視ソフトウェアを含めます
3. SSHを使用してGKEノードに接続し、ソフトウェアを手動でインストールします
4. Terraformを使用してサードパーティソリューションをデプロイし、ロギングPodをKubernetesデプロイとしてデプロイします
<details><div>
    答え：１
    (1) GKE クラスタのアーキテクチャ　https://cloud.google.com/kubernetes-engine/docs/concepts/cluster-architecture?hl=ja
各ノードに必ず１つのPodが配置されるデプロイメントはDaemonSetですので、これを使えば良いでしょう。
B, C, D の記載内容はいずれも本問の要求を満たしていません。
Bは、DaemonSet 以外ではノードにPodが配置されない可能性があり、Podが動作していないノードを監視できません。
また全Podに監視ソフトウェアが入っている状態は、全体には必要のない処理でサーバーリソースを圧迫している事になり良い状態とは言えません。
ノードはPodの起動に必要な最小限のシステムとなっているので、そこにアプリケーションをインストールするのは避けたいです（できないのではないでしょうか）。
（Cの記載内容） DもBと同様通常のPodであれば、全ノードに必ず１つ存在することは保障されないでしょう。
(1)の資料も参考にすると本問は DaemonSetがキーワードだと思いますので、A が正解となります。
</div></details>

## Q. 1-27
ユーザーが管理するキーとユーザーが管理するサービスアカウントを使用して Cloud Storage API に対して認証するオンプレミスアプリケーションがあります。
アプリケーションは Dedicated Interconnect リンクを介して限定公開の Googleアクセスを使用して Cloud Storage に接続します。
Cloud Storage バケット内のオブジェクトにアクセスするためのアプリケーションからのリクエストが 403 Permission Denied エラーコードで失敗していることに気付きました。
この問題の考えられる原因は何でしょうか？
1. バケット内のフォルダ構造とオブジェクトパスが変更されている
2. サービスアカウントの定義済みロールの権限が変更されている
3. サービスアカウントキーがローテーションされましたが、アプリケーションサーバで更新されていない
4. オンプレミスデータセンターからGCPへのInterconnectリンクが一時的に停止されている
<details><div>
    答え：２
403エラーは権限に関するエラーですので、まずD.はないですね（この場合はおそらく502 Bad Gatewayになるでしょう）。
Aの場合は404（ファイルが見つかりません)でしょう。
キーのローテションに失敗した場合は、Cloud Storage アクセスの認証に失敗し、エラーは 401 Unauthorized になるものと思われます。
エラーコードが403 Permission Deniedという事で、Cloud Storageにはアクセス出来ているが、ReadなりWriteの権限がなく、Permission Deniedとなったものと思われます。
したがって考えられる原因は B となります。
</div></details>

## Q. 1-28
Cloud Run でホストされている Webサイトのトラフィックが急増したときの応答が遅すぎると、ユーザーから苦情が寄せられています。
トラフィックのピーク時により優れたユーザーエクスペリエンスを提供したいと考えています。
どうすればいいでしょうか？
1. アプリケーションの起動時にデータベースからアプリケーション構成と静的データを読み取ります
2. ビルド時にアプリケーション構成と静的データをアプリケーションイメージにパッケージ化します
3. 応答がユーザーに返された後、バックグラウンドで可能な限り多くの作業を実行します
4. タイムアウトの例外とエラーによってCloudRunインスタンスがすぐに終了し、代わりにインスタンスを開始できるようにします
<details><div>
    答え：２
A はこの問題に特に関連性がない記述です。
D のようにエラーが頻繁に発生する状態は、その状況そのものが問題なので、本件とは別の問題と思われますし、インスタンスの再起動となるとどんなに高速でも応答が遅くなるでしょう。
C.の対応で可能な部分を非同期通信にしたり、Pub/Subの利用を考える事でユーザー エクスペリエンスの改善に繋がりそうですが、トータルの処理時間はほぼ変わらない事と、十分にスケールアウトされていればアプリケーション処理の遅延は発生しないと考えられます。
問題は、トラフィックが急増したときに、十分なスピードでコンテナのスケールアウトが進まず、全体のパフォーマンスに影響を与えていると考えられます。
コンテナの起動スピードを改善する為に B の内容を考える必要があるでしょう。
従って、この問題の正解は B となります。
</div></details>

## Q. 1-29
ユーザーが昼夜を問わずゲームを操作するため、トラフィックパターンが予測できないシングルプレイヤーモバイルゲームバックエンドを開発しています。
リクエストを処理するのに十分なリソースを確保することでコストを最適化しながら過剰なプロビジョニングを最小限に抑える必要があります。
また、トラフィックの急増を効率的に処理するシステムも必要です。
どのコンピューティングプラットフォームを使用するべきでしょうか？
1. Cloudrun
2. マネージドインスタンスグループを使用するComputeEngine
3. 非マネージドインスタンスグループを使用するComputeEngine
4. クラスタの自動スケーリングを使用するGKE
<details><div>
    答え：１
「トラフィックの急増を効率的に処理する」事から、A, D. の２択に絞られます。
Dは定義した最小サイズまでにしかスケールしないことや、スケールインの際にノード削減の為に、一次的なサービスの中断が発生する可能性があります。
このような状況がある為、フルマネージド、ゼロスケールまでスケールイン可能な A をより最適と判断します。 正解は A です。
</div></details>

## Q. 1-30
Cloud Run にデプロイされた本番環境のビジネスクリティカルなアプリケーションをサポートしています。
アプリケーションはアプリケーションの使いやすさに影響を与える HTTP500 エラーを報告しています。
特定の時間枠内でエラー数がリクエストの 15% を超えたときにアラートを受け取る必要があります。
どうすればいいでしょうか？
1. CloudMonitoringAPIを使用するCloudFunstionsを作成します。CloudSchedulerを使用してCloudFunstionsを毎日トリガーし、エラー数が定義された閾値を超えた場合にアラートを出します
2. GoogleCloudコンソールのCloudRunページに移動し、サービスリストからサービスを選択します。指標タブを使用してそのリビジョンのエラー数を視覚化し、ページを毎日更新します
3. CloudMonitoringでアラートポリシーを作成し、エラー数が定義された閾値を超えた場合にアラートを送信します
4. CloudMonitoringAPIを使用するCloudFunctionsを作成します。CloudComposerを使用してCloudFunctionsを毎日トリガーし、エラー数が定義された閾値を超えた場合にアラートを送信します
<details><div>
    答え：３
指標に基づいた、アラートの発出は Cloud Monitor を使います（さすがに選択肢３つにありますね）。
Cloud Monitoring は特に別なツールとの連携無しにリソースの状態を監視し、定義された閾値を越えた場合にアラートを送信することが可能です。
正解は C です。
</div></details>

## Q. 2-1
Google Kubernetes Engine (GKE) でマイクロサービス アプリケーションとしてオンライン ゲーム プラットフォームを開発しています。
ソーシャル メディアのユーザーはアプリケーションへの特定の URL 要求の読み込み時間が長いことに不満を持っています。
アプリケーションのパフォーマンスのボトルネックを調査し、ユーザー リクエストの待ち時間が非常に長い HTTP リクエストを特定する必要があります。
どうすればいいでしょうか？
1. kubectlを使用してGKEワークロードメトリクスを構成します。CloudMonitoringに指標を送信するすべてのPodを選択します。CloudMonitoringでアプリケーション指標のカスタムダッシュボードを作成しますしてGKEクラスタのパフォーマンスのボトルネックを特定します。
2. マイクロサービスを更新してHTTP要求メソッドとURLパスをSTDOUTに記録します。ログルータを使用してコンテナログをCloudLoggingに送信します。CloudLoggingでフィルタをさくせいしたてさまざまなメソッドとURLパスにわたるユーザーリクエストのレイテンシを評価します
3. OpenTelemetryトレースパッケージをインストールしてマイクロサービスを計測します。アプリケーションコードを更新して検査と分析のためにトレースをTraceに送信します。Traceで分析レポートを作成してユーザーの要求を分析します。
4. GKEノードにtcpdumpをインストールします。tcpdumpを事項してネットワークトラフィックを長期にわたってキャプチャ氏、データを収集します。Wiresharkを使用してデータファイルを分析し、高レイテンシの原因を特定します。
<details><div>
    答え：３
(1) Cloud Trace 用の計測
https://cloud.google.com/trace/docs/setup?hl=ja#when-to-instrument
要件としてはリクエストのレイテンシーの測定ですね。
その場合は Trace を利用しますので、Cが正解となります。
Aは、CPUやメモリーの使用率を監視し、閾値を超えた場合にアラートを出す仕組みです。
Bはアプリの不具合や実行状態を見るためのログ出力に関する記述です。
レイテンシーの計測への関連性は薄いです。
Dはネットワークに何らかの不具合がある場合の調査に関する記述となっています。
</div></details>

## Q. 2-2
自社の開発チームが、コンテナ イメージでさまざまなオープンソースのオペレーティング システムを使用することを必要としています。
イメージがパブリッシュされるとき、共通脆弱性識別子（CVE）のスキャンが必要となります。
このスキャン処理がソフトウェア開発のアジリティに影響することがあってはなりません。
可能な場所ではマネージド サービスを使用することを希望しています。
どうすればよいですか。
1. ContainerAnalysisAPIを有効にして、Artifactregistoryでイメージの脆弱性スキャンを実施する
2. コードチェックインでトリガーされ、コードのCVEをスキャンするCloudRunサービスを作成する
3. 商用サポートされていないベースイメージを開発環境で使用することを禁止する
4. CloudMonitoringを使用してCloudBuildの出力を確認し、脆弱性のあるバージョンが使用されているかどうかを判断する
<details><div>
    答え：1
(1) Scan images for OS vulnerabilities automatically
https://cloud.google.com/container-analysis/docs/os-scanning-automatically#viewing_vulnerabilities_and_other_occurrences
(2) Container Analysis と脆弱性スキャン
https://cloud.google.com/container-registry/docs/container-analysis?hl=ja
A は正解です。
Container Analysis API により、Debian、Ubuntu、Alpine、Red Hat Enterprise Edition、National Vulnerability Database の各ソースの CVE のイメージ スキャンが可能になります。
B は不正解です。
この方法は機能する場合もありますが、マネージド サービスの条件を満たしていません。
C は不正解です。
この方法は機能しますが、アジャイル ソフトウェア開発の文化に反しており、進捗を妨げる可能性があります。
D は不正解です。
Cloud Monitoring ではログをスキャンできても、脆弱性に関する分析情報は得られません。
</div></details>

## Q. 2-3
本番環境の Google Kubernetes Engine (GKE) クラスタでアプリケーションを実行しています。
Cloud Deploy を使用してアプリケーションを本番 GKE クラスタに自動的にデプロイします。
開発プロセスの一環としてアプリケーションのソース コードを頻繁に変更することを計画しており、変更をリモート ソース コード リポジトリにプッシュする前に変更をテストするツールを選択する必要があります。
ツールセットは次の要件を満たす必要があります。
- 頻繁なローカル変更を自動的にテストします。
- ローカルデプロイは本番デプロイをエミュレートします。
最小限のリソースを使用してラップトップでコンテナのビルドと実行をテストするにはどのツールを使用しますか？
1. DockerComposeとdockerd
2. Terraformとkubeadm
3. MinnikubeとSkafold
4. KanikoとTekton
<details><div>
    答え：3
(1) Google Cloud Deploy で Skaffold を使ってみる
https://cloud.google.com/deploy/docs/using-skaffold/getting-started-skaffold?hl=ja
(2) Cloud Code と Skaffold モジュールで Kubernetes マイクロサービス アプリケーションの開発とデバッグを迅速化 | Google Cloud 公式ブログ
https://cloud.google.com/blog/ja/topics/developers-practitioners/developers-practitionersdevelop-and-debug-kubernetes-microservice-applications-fast-with-google-cloud
ラップトップPCで開発を行うために kubernetes 環境をローカルに作るとなると、Minikubeの利用になります。
Aはコンテナの実行、B.はリソースの構築を設定ファイルで行う為のツール、Dはコンテナイメージのビルドの際に利用できるツールです（kanikoは本当に２回目以降のイメージビルドが高速になる（キャッシュが利用されているのでしょう）のでお勧めです）。
正解は C となります。
(他の問題でもローカル環境での開発、テストは効率が良いとされています（実際にそう思います）
</div></details>

## Q. 2-4
あなたは、Cloud クライアント ライブラリに対応していない新しいプログラミング言語でアプリケーションを開発しています。
アプリケーションでは、REST API 呼び出しを作成して Google Cloud サービスを呼び出します。
アプリケーションは関連するサービス アカウントを使用して Cloud Run で実行されます。
Google Cloud サービスの呼び出しを可能にするにはどうしたら良いでしょう。
1. APIキーをアプリケーションに含め、その値をAuthorizationヘッダーに渡す
2. メタデータサーバーからアクセストークンを取得し、その値をAuthorizationヘッダーに渡す
3. GOOGLE‗APPLICATION_CREDENTIALS環境変数の値として、サービスアカウントのAPIキーを使用する
4. gloud auth application-default print-access-token の値を、スタートアップ時にGOOGLE‗APPLICATION_CREDENTIALS環境変数にパスが設定されたファイルに保存する
<details><div>
    答え：2
(1) OAuth 2.0 を使用した Google API へのアクセス
https://developers.google.com/identity/protocols/oauth2?hl=ja#4.-send-the-access-token-to-an-api.
(2) コンテナ ランタイムの契約
https://cloud.google.com/run/docs/container-contract?hl=ja#metadata-server
(3) サービス ID
https://cloud.google.com/run/docs/securing/service-identity?hl=ja
解説：
A は不正解です。
APIキーは認可トークンとは異なり、HTTP リクエストの Authorization ヘッダーで渡された場合は考慮されません。
B は正解です。
メタデータ サーバーから取得して HTTP リクエストの Authorization ヘッダーで Google Cloud に渡したアクセス トークンは、サービス アカウントとして正常に認証に利用できます。
C は不正解です。
GOOGLE_APPLICATION_CREDENTIALS には、API キーの値ではなく、アクセス トークンを含むファイルの名前を設定する必要があります。
D は不正解です。
GOOGLE_APPLICATION_CREDENTIALS は、アクセス トークンではなく、API キーを含むファイルを参照するために使用されます。
</div></details>

## Q. 2-5
チームは大規模な Google Kubernetes Engine (GKE) クラスタを管理しています。
現在、複数のアプリケーションチームが同じ名前空間を使用してクラスタ用のマイクロサービスを開発しています。
組織はマイクロサービスを作成するために追加のチームをオンボードすることを計画しています。
各チームの作業のセキュリティと最適なパフォーマンスを確保し、複数の環境を構成する必要があります。
コストを最小限に抑え Google が推奨するベスト プラクティスに従います。
どうすればいいでしょうか？
1. 既存のクラスタ内の各チームに対して新しい役割ベースのアクセス制御を作成し、リソースクウォータを定義します
2. 既存のクラスタ内の環境ごとに新しい名前空間を作成し、リソースクウォータを定義します
3. チームごとに新しいGKEクラスタを作成します
4. 既存のクラスタ内の各チームに新しい名前空間を作成し、リソースクウォータを定義します
<details><div>
    答え：1
(1) GKE RBAC のベスト プラクティス
https://cloud.google.com/kubernetes-engine/docs/best-practices/rbac?hl=ja
設問を読むと、チーム毎にリソースを分けたいことがわかります。
「複数の環境を構成する」という要件もありますが、まずはチームごとの環境が先決で、さらにその上に複数の環境を（開発環境、テスト環境等）作ることになります。
ここで B は除外。
あとは「コストを最小限に抑え」という条件もありますので、C も除外できます(コストを考えなければ一番ですけどね)。
A, Dはかなり似ていますが、「各チームの作業のセキュリティと」「クラスタ用のマイクロサービスを開発しています」
という記述を考えると、現状、総合的にには同じアプリケーションを構成するマイクロサービスをそれぞれのチームが開発しており、「同じ名前空間を使用して」というのは考慮不足でそうなってしまったというわけではなく、あえてそうしていると解釈できます。
そう考えると A を選択する事になるでしょう。
Roleはユーザーやユーザーグループに割り当てられるので、これで各チーム毎へのロールの割り当ては可能でしょう。
正解は A となります。
</div></details>

## Q. 2-6
あなたの会社では、分析を行うユースケースを増やすことを計画しています。
新しいユースケースのあるデータ分析では、SQL を使用してほぼリアルタイムでイベントを分析する必要があります。
対象のデータは急速な増加が見込まれており、できる限りマネージド サービスを使用したいと考えています。
どうすればよいですか。
1. 先ず大規模なComputeEngineインスタンス上にKafkaインスタンスを作成する。その後、ソースからKafkaパイプラインにイベントをストリーミングし、Dataflowを利用してこれらのイベントをCloudStorageに取り込む
2. まずPub/Subのトピックとサブスクリプションを作成する。その後、ソースからイベントをPub/Subにストリーミングし、Dataflowを利用してこれらのイベントをCloudStorageに取り込む
3. まずPub/Subのトピックとサブスクリプションを作成する。その後、ソースからイベントをPub/Subにストリーミングし、Dataflowを利用してこれらのイベントをBigQueryに取り込む
4. まずPub/Subのトピックとサブスクリプションを作成する。その後、ソースからイベントをPub/Subにストリーミングし、Dataflowを利用してこれらのイベントをDatastoreモードのFirestoreに取り込む
<details><div>
    答え：3
(1) Pub/Sub から BigQuery へのストリーミング
https://cloud.google.com/dataflow/docs/tutorials/dataflow-stream-to-bigquery?hl=ja
(2) データ分析設計パターン
https://cloud.google.com/architecture/reference-patterns/overview?hl=ja#general_analytics
A は不正解です。これはフルマネージド ソリューションではありません。
B は不正解です。
Cloud Storage は、個々のイベントを挿入したり、SQL で分析したりする場合には適していません。
C は正解です。
この説明に含まれる 3 つのプロダクトすべてが大規模にスケーリング可能です。
さらに、BigQuery にデータを書き込むことで、すぐに SQL で分析できるようになります。
D は不正解です。
Datastore モードの Firestore は、個別のイベントを挿入したり、分析したりする場合には適していません。
</div></details>

## Q. 2-7
チームは Cloud Storage イベントによってトリガーされる Cloud Functions を開発しています。
Google が推奨するベストプラクティスに従いながら Cloud Functions のテストと開発を加速したいと考えています。
どうすればいいでしょうか？
1. CloudAuditLogsが元のCloudFunctionsでcloudfunctions.functions.sourcecodeset操作を検出したときにトリガーされる新しいCloudFunctionsを作成します。モックリクエストを新しい関数に送信して機能を評価します
2. CloudFunctionsのコピーを作成し、HTTPでトリガーされるようにコードを書き直します。HTTPエンドポイントをトリガーして新しいバージョンを編集及びテストします。モックリクエストを新しい関数に送信して機能を評価します
3. FunctionsFrameworksライブラリをインストールし、localhostでCloudFunctionsを構成します。関数のコピーを作成し、新しいバージョンを編集します。curlを使用して新しいバージョンをテストします
4. GoogleCloudコンソールでCloudFunctionsのコピーを作成します。GoogleCloudConsoleのインラインエディタを使用して新しい関数のソースコードを変更します。新しい関数を呼び出すようにWebアプリケーションを変更し、本番環境で新しいバージョンをテストします
<details><div>
    答え：3
(1) ローカルでの開発
https://cloud.google.com/functions/docs/running/overview?hl=ja
解説：
テストはローカル環境で行うのが最も効率がよく、Google が推奨するベストプラクティスとなっています。
Google Cloud 環境で開発を行うと、テストの結果修正が必要な場合、テストに必要なコードを追加する場合に都度デプロイを行わなければならず非効率です。
選択肢の中で唯一、ローカル環境でテストを行っている C が正解です。
Functions, Pub/Subのテストが問われる場合、ほぼローカルでのテストを行っている選択肢が正解と考えて良いでしょう。
</div></details>

## Q. 2-8
Cloud Logging で、重要な監査アクティビティの情報を取得しています。
Cloud Logging から情報を読み取り、ほぼリアルタイムでログの分析を行う必要があります。
複数のプロセスでログデータに対して異なる種類の分析を行うにはどうすればよいですか。
1. Cloud Logging APIからログを直接読み取るアプリを作成する
2. Pub/Subに対してCloud Logging辛苦を設定し、Pub/Subトピックからログを読み取る
3. Cloud Logging API から直接読み取るCloudFunctionsのエンドポイントを作成し、ログをDataprocにコピーする
4. CloudStorageに対してCloud Loggingシンクを設定し、CloudStorageバケットからログを読み取る
<details><div>
    答え：2
A は不正解です。
この API には読み取りに関する制限があり、複数の読み取り処理を行うソリューションには適していません。(https://cloud.google.com/logging/quotas)
B は正解です。
このソリューションはほぼリアルタイムです。（https://cloud.google.com/logging/docs/export/using_exported_logs#pubsub-availability）
C は不正解です。
これは効率的なソリューションではありません。
（https://cloud.google.com/dataproc/docs/concepts/jobs/life-of-a-job）
D は不正解です。
このソリューションはリアルタイムではありません。（https://cloud.google.com/logging/docs/export/using_exported_logs#gcs-availability）
</div></details>

## Q. 2-9
Go で記述され、Google Kubernetes Engine にデプロイされた Webアプリケーションをモニタリングしています。
CPU とメモリの使用率が増加していることに気付きます。
CPU とメモリのリソースを最も多く消費しているソースコードを特定する必要があります。
どうすればいいでしょうか？
1. VMでスナップショットデバッガーエージェントをダウンロード、インストール、開始します。最も時間がかかる関数のデバッグスナップショットを取得します。コールスタックフレームを確認し、スタック内のそのレベルにあるローカル変数を特定します
2. CloudProfilerパッケージをアプリケーションにインポートし、Profilerエージェントを初期化します。生成されたフレームグラフをGoogleCloudコンソールで確認して、時間のかかる関数を特定します
3. OpenTelemetryおよびTraceエクスポートパッケージをアプリケーションにインポートし、トレースプロバイダーを作成します。トレースのファイ用ページでアプリケーションのレイテンシデータを確認し、ボトルネックが発生している場所を特定します
4. Webアプリケーションののログを収集するCloudLoggingクエリを作成します。アプリケーションの最も長い関数の最初と最後のタイムスタンプの差を計算して時間のかかる関数を特定するPythonスクリプトを作成します
<details><div>
    答え：2
(1) Cloud Profiler の概要
https://cloud.google.com/profiler/docs/about-profiler?hl=ja
解説：
特定の処理のパフォーマンスを測定するには、Cloud Profilerを利用します。
A は特定の関数のパフォーマンスは測定できません。
現在動作している処理の不具合調査の為にデバッグ出力を追加する等、不具合の調査に有効です。
B は要求されている事を実現可能です。
C はレイテンシーの調査には有効ですが、CPUやメモリーの消費量が多い処理を特定するには直接的ではありません。
D は記載の方法でレイテンシーの調査は出来ると思いますが、Cと同様です。
正解は B となります。
</div></details>

## Q. 2-10
マイクロサービス アプリケーションを Google Kubernetes Engine (GKE) にデプロイしています。
アプリケーションは毎日更新されます。Linux オペレーティング システム (OS) で実行される多数の個別のコンテナをデプロイすることを想定しています。
新しいコンテナの既知の OS の脆弱性についてアラートを受け取る必要があります。
Google が推奨するベスト プラクティスに従います。
どうすればいいでしょうか？
1. gcloud CLIを使用してContainerAnalysisを呼び出し、新しいコンテナイメージをスキャンします。各デプロイの前に脆弱性の結果を確認してください
2. ContainerAnalysisを有効にし、新しいコンテナイメージをArtifactregistoryにアップロードします。各デプロイの前に脆弱性の結果を確認してください
3. ContainerAnalysisを有効にし、新しいコンテナイメージをArtifactregistoryにアップロードします。各デプロイの前に重大な脆弱性の結果を確認してください
4. ContainerAnalysisRESTAPIを使用してContainerAnalysisを呼び出し、新しいコンテナイメージをスキャンします。各デプロイの前に脆弱性の結果を確認してください
<details><div>
    答え：2
解説：
Artifact Registryへのアップロードの際にContainer Analysis指定により脆弱性のスキャンを自動的に行うことができるのでこれを使わない手はありません。
B, Cの２択です。
重大か重大ではないかの線引きは難しいので、脆弱性が検知されたらすべてアラートを出した方が良いでしょう。
正解は B となります。
</div></details>

## Q. 2-11
最近、Go アプリケーションを Google Kubernetes Engine (GKE) にデプロイしました。
運用チームは運用トラフィックが少ない場合でもアプリケーションの CPU 使用率が高いことに気付きました。
運用チームからアプリケーションの CPU リソース消費を最適化するよう依頼されました。
最も多くの CPU を消費する Go 関数を特定したいと考えています。
どうすればいいでしょうか？
1. CloudLoggingにデータを記録するためにGKEクラスタにFluentBitデーモンセットをデプロイします。ログを分析してアプリケーションコードのパフォーマンスに関する洞察を得ます
2. CloudMonitoringでカスタムダッシュボードを作成してアプリケーションのCPUパフォーマンス指標を評価します
3. SSHを使用してGKEノードに接続します。シェルでtopコマンドを実行してアプリケーションのCPU使用率を抽出します
4. Goアプリケーションを変更してプロファイリングデータを取得します。CloudProfilerのフレームグラフでアプリケーションのCPUメトリックを分析します
<details><div>
    答え：4
(1) Cloud Profiler のドキュメント
https://cloud.google.com/profiler/docs?hl=ja#docs
解説：
Cloud Profilerでどの処理がCPUの使用率が高いか確認する事ができます。
Aのログからはその処理がCPU使用率が高いかを判定することは難しいでしょう。
B, C は全体的なCPU使用率しか分かりません。
正解は D となります。
</div></details>

## Q. 2-12
Cloud Run を使用して Webアプリケーションをホストしています。
アプリケーションプロジェクトID とアプリケーションが実行されているリージョンを安全に取得し、この情報をユーザーに表示する必要があります。
最もパフォーマンスの高いアプローチを使用したい。
どうすればいいでしょうか？
1. HTTPリクエストを使用してhttp://metadata.google.internal/エンドポイントでMetadata-Flavor:Googleヘッダーを使用して利用可能なメタデータサーバにクエリを実行します
2. GoogleCloudコンソールでプロジェクトダッシュボードに移動し、構成の詳細を収集します。CloudRunのVariables&Sercretsタブに移動し、必要な環境変数をKey/Value形式で追加します
3. GoogleCloudコンソールでプロジェクトダッシュボードに移動し、構成の詳細を収集します。アプリケーション構成情報をCloudRunのインメモリコンテナファイルシステムに書き込みます
4. アプリケーションからCloudAssetInventoryAPIへのAPI呼び出しを行い、リクエストをフォーマットしてインスタンスメタデータを含めます
<details><div>
    答え：1
(1) コンテナ ランタイムの契約(Cloud Run)
https://cloud.google.com/run/docs/container-contract?hl=ja
解説：
B, Cは手作業なので無しですね。
人間がやることなので設定をミスって間違った情報が表示されかねません。
D.の方法でも実現は可能と思いますが、Cloud Asset Inventory API で得られる情報は膨大で殆どのデータが不必要なものであり、パフォーマンスの悪化につながりかねません。
Aの方法が最もパフォーマンスの高いアプローチでしょう。
正解は A です。
</div></details>

## Q. 2-13
Google Kubernetes Engine (GKE) クラスタに数百のマイクロサービスをデプロイすることを計画しています。
マネージドサービスを使用して GKE 上のマイクロサービス間の通信をどのように保護する必要がありますか？
1. マネージドSSL証明書でグローバルHTTP(S)ロードバランサを使用してサービスを保護します
2. GKEクラスタにオープンソースのIstioをデプロイし、サービスメッシュでmTLSを有効にします
3. GKEにcert-anagerをインストールして、SSL証明書を自動的に更新します
4. AuthosServiceMeshをインストールし、ServiceMeshでmTLSを有効にします
<details><div>
    答え：4
数百のマイクロサービス間通信となると、もう設定ファイルなどでコントロールすることは不可能となります。
Istioは OSS で GKEに対する kubernetesのようなものです。（GKEはフルマネージドサービスではありませんが）
Anthos Service MeshがIstioのマネージドサービスです。
「マイクロサービス間通信（サービスメッシュ）をコントロールするマネージドサービスはなぁ〜んだ？」
という問題の答えは D となります。
</div></details>

## Q. 2-14
複数のルームをホストし、各ルームのメッセージ履歴を保持するチャット ルーム アプリケーションを設計しています。
データベースとして Cloud Firestore を選択しました。
Cloud Firestore でデータをどのように表すべきでしょうか？
（下図のA, B, C, D の図は選択肢のA, B, C, D の内容の図を示しています）
1. RoomのCollectionを作成します。RoomごとにMessageの内容をリストしたドキュメントを作成します。
2. RoomのCollectionを作成します。Roomごとに各Messageのドキュメントを含むCollectionを作成します。
3. RoomのCollectionを作成します。RoomごとにMessageを含むドキュメントを作成します
4. RoomのCollectionを作成し、Roomごとのドキュメントを作成します。Messageごとに１つのドキュメントを使用してMessage用に個別のCollectionを作成します。各ルームのドキュメントにはMessageへの参照のリストが含まれています
<details><div>
    答え：3
(1) Cloud Firestore データモデル
https://firebase.google.com/docs/firestore/data-model?hl=ja#hierarchical-data
解説：
CollectionとDocumentが１セットでDocumentが実際の構造化データとなります
各ルーム毎にメッセージがあり、メッセージ部分もCollectionとDocument構成にします。
ドキュメントは１つでも良いですが、日毎とか100件毎に新しいドキュメントにする等が可能です
（実運用経験による）
Room(Collection) -+- Room0(Document)
                                   |
                                  ...
                                   |
                                  +- RoomN(Document) - Messge(Collection) -+- Message0(Document)
                                                                                                                     |
                                                                                                                    ...
                                                                                                                     |
                                                                                                                    +- MessageN(Document)
という事で、本問に関しては他の説明の間違いを説明するのではなく、正しい状況説明から C が正解となります。
</div></details>

## Q. 2-15
最近、組織はレガシー アプリケーションを Google Kubernetes Engine に再プラットフォーム化する取り組みを開始しました。
モノリシック アプリケーションをマイクロサービスに分解する必要があります。
複数のインスタンスには共有ファイルシステムに保存されている構成ファイルへの読み取りおよび書き込みアクセス権があります。
この移行を管理するために必要な労力を最小限に抑え、アプリケーションコードの書き直しを避けたいと考えています。
どうすればいいでしょうか？
1. 新しいCloudStorageバケットを作成し、FUSEを介してコンテナにマウントします
2. 新しい永続ディスクを作成し、ボリュームを共有PersistentCloumeとしてマウントします
3. 新しいFilestoreインスタンスを作成し、ボリュームをNFSPersistentCloumeとしてマウントします
4. 新しいConfigMapとvolumeMountを作成して、構成ファイルの内容を保存します
<details><div>
    答え：3
(1) Persistent Volumes
https://kubernetes.io/docs/concepts/storage/persistent-volumes/#access-modes
(2) Filestore CSI ドライバを使用して Filestore インスタンスにアクセスする
https://cloud.google.com/filestore/docs/csi-driver?hl=ja
(3) Cloud Storage FUSE
https://cloud.google.com/storage/docs/gcs-fuse?hl=ja
解説：
基本的にCloud Storageは PCのHDDやSSDのような使い方ではなく非構造化オフジェクト（画像、ログデータ等）の保存に使われます。
FUSEはCloud StorageをHDD感覚で使えるようにはなりますが、結局元がCloud Storageで通常のテキストファイルの保存、更新などには向きません。
そして高レイテンシーです。
以上実際に使用した経験で、かなり用途が絞られる感じがありますので、テキストファイルの共有に使うのは得策ではありません（というか使わない）。
Aは除外。
BはReadオンリーであれば使えますが、複数インスタンスからの書き込みには制限がある（出来ないに等しい）ので、「読み取りおよび書き込み」であれば選択から外れます。除外です。
ConfigMapもPodからの書き換えは出来ないので除外。
ということで、Cが正解です。
Cは特に問題はありません。
</div></details>

## Q. 2-16
会社の企業ポリシーではすべてのソースファイルの最初に著作権に関するコメントが必要であると規定されています。
各ソース commit によってトリガーされるカスタムステップを Cloud Build に記述したいと考えています。
ソースに著作権が含まれていることを検証し、含まれていない場合は後続のステップのために追加するトリガーが必要です。
どうすればいいでしょうか？
1. /workspace内のファイルを調べ、各ソースファイルの著作権を確認して追加する新しいDockerコンテナを構築します。変更されたファイルはソースリポジトリに明示的にコミットされます
2. /workspace内のファイルを調べ、各ソースファイルの著作権を確認して追加する新しいDockerコンテナを構築します。変更されたファイルをコミットする必要はありません
3. CloudStorageバケット内のファイルを調べ、各ソースファイルの著作権を確認して追加する新しいDockerコンテナを構築します。変更されたファイルはCloudStorageバケットに書き戻されます
4. CloudStorageバケット内のファイルを調べ、各ソースファイルの著作権を確認して追加する新しいDockerコンテナを構築します。変更されたファイルはソースリポジトリに明示的にコミットされます
<details><div>
    答え：1
テキストの編集用途に Cloud Storageを使うのは適切ではないのでC, Dは除外。
Bでは修正が保存されない事になるで除外。
残り A が正解です。
Aの記載内容に特に問題はありません。
</div></details>

## Q. 2-17
Google Kubernetes Engine でコンテナ化されたアプリケーションを実行しています。
コンテナ イメージは Container Registry (Artifact Registry) に保存されます。
チームは CI/CD プラクティスを使用しています。
既知の重大な脆弱性を持つコンテナのデプロイを防ぐ必要があります。
どうすればいいでしょうか？
1. WebSecurityScannerを使用してアプリケーションを自動的にクロールします。アプリケーションログでスキャン結果を確認し、コンテナに既知の重大な脆弱性がないことを証明します。BinaryAuthrizationを使用してコンテナがデプロイされる前に証明書の提供を強制するポリシーを実装します
2. WebSecurityScannerを使用してアプリケーションを自動的にクロールします。CloudConsoleのスキャンの詳細ページでスキャン結果を確認し、コンテナに既知の重大な脆弱性がないことを証明します。BinaryAuthrizationを使用してコンテナがデプロイされる前に証明書の提供を強制するポリシーを実装します
3. ContainerScanningAPIを有効にして脆弱性スキャンを実行します。CloudConsoleのContainerRegistryで脆弱性レポートを確認し、コンテナに既知の重大な脆弱性がないことを証明します。BinaryAuthrizationを使用してコンテナがデプロイされる前に証明書の提供を強制するポリシーを実装します
4. ContainerScanningAPIを有効にして脆弱性スキャンを実行します。ContainerScanningAPIを介してプログラムで脆弱性レポートを確認し、コンテナに既知の重大な脆弱性がないことを証明します。BinaryAuthrizationを使用してコンテナがデプロイされる前に証明書の提供を強制するポリシーを実装します
<details><div>
    答え：4
コンテナの脆弱性スキャンにはContainer Scanning APIを使います。
自動化するためにプログラムで脆弱性レポートのチェックを行います。
従って D が正解となります。
</div></details>

## Q. 2-18
コンテナ化されたアプリケーションの新しいバージョンはテスト済みで Google Kubernetes Engine の本番環境にデプロイする準備ができています。
運用前の環境で新しいバージョンの完全な負荷テストを行うことができなかったため、デプロイ後にパフォーマンスの問題がないことを確認する必要があり、デプロイは自動化する必要があります。
どうすればいいでしょうか？
1. CloudLoadBalancing を使用し、バージョン間のトラフィックをゆっくりと増やします。CloudMonitoringを使用してパフォーマンスの問題を探します
2. カナリアデプロイを使用し、継続的デリバリーパイプラインを介してアプリケーションをデプロイします。CloudMonitoringを使用してパフォーマンスの問題を探します。メトリックがサポートするようにトラフィックを増加させます
3. Blue/Greenデプロイを使用し、継続的デリバリーパイプラインを介してアプリケーションをデプロイします。CloudMonitoringを使用してパフォーマンスの問題を探し、指標がそれをサポートしているときに完全に起動します
4. kubectlを使用してアプリケーションをデプロイし、spec.updateStrategv.typeをRollingUpdateに設定します。CloudMonitoringを使用してパフォーマンスの問題を探し、問題がある場合はkubectlrollbackコマンドを実行します
<details><div>
    答え：2
(1) カナリア デプロイ戦略を使用する
https://cloud.google.com/deploy/docs/deployment-strategies/canary?hl=ja#types_of_canary
解説：
Cloud Load Balancing により新バージョン、旧バージョンの振り分けは出来ません。
また、Dはコマンドラインベースでの操作を行っているのと、問題が発生する状況までUpdateが進んでからrollbackすることになるのでサービスに影響を与えてしまう戦略でしょう。
B, C. の２択になりますが、Cでは一旦新バージョンに切り替えないと状況が分かりませんが、Bではアラートが発生するレベルの手前で rollback可能です。
従って正解は B となります。
</div></details>

## Q. 2-19
Google Kubernetes Engine でホストされている新しいヨーロッパバージョンの Web サイトをデプロイする必要があります。
現在の Web サイトと新しい Webサイトは同じ HTTP(S) ロードバランサの外部IPアドレスを介してアクセスする必要がありますがドメイン名は異なります。
どうすればいいでしょうか？
1. 新しいドメインに一致するホストルールで新しいIngressリソースを定義します
2. 新しいドメインに一致するホストルールで既存のIngressリソースを変更します
3. 既存のIPアドレスをloadbalanceripとして指定して、タイプloadbalancerの新しいサービスを作成します
4. 新しいIngressリソースを生成し、既存のIPアドレスをKubernetes.io/ingress.global-static-ip-nameアノテーション値として指定します
<details><div>
    答え：2
(1) Ingress
https://kubernetes.io/docs/concepts/services-networking/ingress/#name-based-virtual-hosting
解説：
新しいドメインにマッチするホストルールを、既存のIngressリソースに追加することができます。
これにより、同じIPアドレス、ロードバランサー、Ingressを使用しながら、新しいWebサイトにトラフィックをルーティングすることができます。
新しい Ingress リソースは必要ないので、A, Dは不正解です。
Ingressの設定で特定のドメイン名を、サービス名で振り分けることができます。
特にLoadBalancer タイプのサービスを必要としませんの　C は不正解です。
B が正解となります。
</div></details>

## Q. 2-20
会社は顧客の購入履歴を保存し、次の要件を満たすデータベースソリューションを必要としています。
* 顧客は送信後すぐに購入を照会できます。
* さまざまなフィールドで購入をソートできます。
* 異なるレコード形式を同時に保存できます。
これらの要件を満たすストレージオプションはどれでしょうか？
1. ネイティブモードのCloudFirestore
2. オブジェクト読み取りを使用したCloudStorage
3. SQLSELECTステートメントを使用したCloudSQL
4. グローバルクエリを使用したDatastoreモードのCloudFirestore
<details><div>
    答え：1
「異なるレコード形式を同時に保存できます」がNoSQLの特徴なので、B, C.は即座に排除できるので、A, D の二択問題となります。
AかBかの判断に決め手が見つからず難しいですが、特にDatastoreモードを使う利用する必要がない限りはネイティブモードの使用で良いと考えられるので、Aを正解とします。
</div></details>

## Q. 2-21
POST 経由で呼び出される HTTP Cloud Functions があります。
各送信のリクエスト本文には数値データとテキストデータを含むフラットでネストされていない JSON 構造があります。
Cloud Functions が完了すると収集されたデータは多くのユーザーが並行して進行中の複雑な分析にすぐに利用できるようになります。
サブミッションをどのように永続化する必要がありますか？
1. 各POSTリクエストのJSONデータをDatastoreに直接永続化します
2. POSTリクエストのJSONデータを変換し、BigQueryにストリーミングします
3. POSTリクエストのJSONデータを変換し、リージョンのCloudSQLクラスタに保存します
4. 各POSTリクエストのJSONデータを個別のファイルとしてCloudStorageないに保存し、ファイル名にリクエスト識別子を含めます
<details><div>
    答え：2
「並行して進行中の複雑な分析にすぐに利用できるようになります」という記述から、すぐに分析可能な選択肢を選ぶ必要があります。
B.以外は、保存の事ののみが言及されており、分析に対する記述がありません（記載内容のままでは分析に利用できる状態にない）
B.はデータウェアハウスであるBigQueryに格納してるのですぐに分析に利用することができます。
従って、B が正解です。
</div></details>

## Q. 2-22
クライアントが特定の期間、Web サイトからファイルをダウンロードできるようにするアプリケーションを開発しています。
Google が推奨するベスト プラクティスに従いながらこのタスクを完了するにはアプリケーションをどのように設計するべきでしょうか？
1. ファイルを電子メールの添付ファイルとしてクライアントに送信するようにアプリケーションを構成します
2. ファイルのCloudStorage署名付きURLを生成して割り当てます。クライアントがダウンロードできるURLを作成します
3. 有効期限が指定された一時的なCloudStorageバケットを作成し、バケットにダウンロード権限を付与します。ファイルをコピーし、クライアントに送信します
4. 有効期限が指定されたHTTPCookieを生成します。時間が有効な場合はCloudStorageバケットからファイルをコピーし、クライアントがファイルをダウンロードできるようにします
<details><div>
    答え：2
(1) 署名付き URL(Cloud Storage)
https://cloud.google.com/storage/docs/access-control/signed-urls
解説：
Bの方法がベストプラクティスとなります。
最良の方法は、バケット内の特定のファイルに対して時間制限付きの読み取りアクセスを与えることができる、Cloud Storage署名付きURLを使用することです。
</div></details>

## Q. 2-23
チームは会社の eコマース プラットフォームを開発しています。
ユーザーは Web サイトにログインし、ショッピング カートに商品を追加します。
ユーザーは 30 分間操作がないと自動的にログアウトされます。
ユーザーが再度ログインするとショッピング カートが保存されます。
Google が推奨するベスト プラクティスに従ってユーザーのセッションとショッピング カートの情報をどのように保存しますか？
1. セッション情報をPub/Subに保存し、ショッピングカート情報をCloudSQLに保存する
2. ショッピングカート情報をファイル名がSESSIONIDであるCloudStorage上のファイルに保存します
3. セッションとショッピングカート情報を複数のComputeEngineインスタンスで実行されているMySQLに保存します
4. セッション情報をRedisまたはMemcachedに保存し、ショッピングカート情報をCloudfirestoreに保存します
<details><div>
    答え：4
(1) Memorystore
https://cloud.google.com/memorystore?hl=ja
(2) Memorystore を使用したデータのキャッシュ
https://cloud.google.com/appengine/docs/standard/go111/using-memorystore?hl=ja
解説：
セッション情報の高速なアクセスと、一定時間で利用できなくなるという要件を満たすリソースとしてはMecchachedやRedisが多く使われているのでGoogle Cloudでは、
Memorystore for Redis(or Memcached) を使うのが良いでしょう。
ショッピング情報のような柔軟性の高い構造化データの保存先としては、NoSQLすなわちCloud Firestoreが適しています。
BはCloud Storege, C.はComputeEngineに展開したMySQLといった記述がとてもベストとは思えないですね。
(Cloud SQLというマネージドサービスがあるので、「ComputeEngineにMySQLを導入して使う」はほぼ間違いと思ってよいかと思います)
A.も何かをトリガーにして何かを処理するというケースではないため本件の内容にそぐわないと分かります。
D.には特に問題を感じることはなく、要件を満たしています。
正解は D となります。
</div></details>

## Q. 2-24
Google Kubernetes Engine の採用と VS Code や IntelliJ を含む開発環境との統合を促進する開発者ツールを評価しています。
どうすればいいでしょうか？
1. CloudCodeを使用してアプリケーションを開発します
2. CloudShell統合コードエディタを使用してコードと構成ファイルを編集します
3. CloudNotebookインスタンスを使用してデータを取り込んで処理し、モデルをデプロイします
4. CloudShellを使用してコマンドラインからインフラストラクチャとアプリケーションを管理します
<details><div>
    答え：1
(1) Cloud Code
https://cloud.google.com/code?hl=ja
解説：
(1)の資料により、A が正解となります。
B, Dでは要件を満たせません。
CはAI系のツールです。
</div></details>

## Q. 2-25
チームは Google Kubernetes Engine (GKE) で実行されるステートレス サービスを開発しています。
GKE クラスタで実行されている他のサービスのみがアクセスできる新しいサービスをデプロイする必要があります。
サービスは変化する負荷に対応するためにできるだけ迅速にスケーリングする必要があります。
どうすればいいでしょうか？
1. VerticalPodAutoscalerを使用してコンテナをスケーリングし、ClousterIPサービスを介して公開します
2. VerticalPodAutoscalerを使用してコンテナをスケーリングし、NodePortサービスを介して公開します
3. HorizontalPodAutoscalerを使用してコンテナをスケーリングし、ClousterIPサービスを介して公開します
4. HorizontalPodAutoscalerを使用してコンテナをスケーリングし、NodePortサービスを介して公開します
<details><div>
    答え：3
(1) サービス
https://cloud.google.com/kubernetes-engine/docs/concepts/service?hl=ja#services_of_type_clusterip
解説：
問題文には特にCPU負荷が増大するような処理を実行しているというな、VPAを必要とする特徴が記述されないので、負荷はアクセス量と考えスケールは水平スケールであると判断します。
GKEクラスタのサービス間通信のみという内容から、ClusterIP が利用されていると判断できます。
従って正解は C となります。
（ClusterIPがよくわからない場合は、Google検索などで調べて勉強しましょう。ここでの解説は割愛させて頂きます）
</div></details>

## Q. 2-26
開発チームは App Engine で構築した Node.js アプリケーションをステージング環境から本番環境に移行するために Cloud Build を使用しています。
このアプリケーションはステージング環境の webphotos-staging という名前の Cloud Storage バケットに保存されている写真の複数のディレクトリに依存しています。
移行後、これらの写真は本番環境の webphotos-prod という名前の Cloud Storage バケットで利用できる必要があります。
可能であればプロセスを自動化したいとも考えています。
どうすればいいでしょうか？
1. 写真をwebhosts-prodに手動でコピーします
2. アプリケーションのapp.yamiファイルに起動スクリプトを追加して写真をwebphotos-stagingからwebphotos-prodに移動します
3. 移行ステップの前に引数を使用してcloudbuild.yamlにビルドステップを追加します。[cp -r fs://webphotos-staging fs://webphotos-prod]
4. 移行ステップの前に引数を使用してcloudbuild.yamlにビルドステップを追加します。[cp -A fs://webphotos-staging fs://webphotos-prod]
<details><div>
    答え：3
A.は「手動」の時点で却下です。（「可能であればプロセスを自動化したい」という場合は、まず可能なやり方の選択になるでしょう）
B.はアップリケーション起動の度にコピーが発生しますし、本番とステージングでコピーが可能か不明、AppEngineに gsutilコマンドまたはgcloudコマンドのインストールが必要など本番サーバーとして相応しくない状況が必要となります。
C.は使っているコマンドが gsutil, D.は gcloud コマンドを使っていますので、Cloud StorageのオブジェクトのコピーであればCが正解になります。
なお、最近は、gcloud コマンドでも CloudStorageのオブジェクトのコピーが可能になりました（2022.9頃GA（General Availability））が、その際のコマンドは gcloud storage cp となりますので、やはりD. は不正解です。
これまではCloudStorageのオブジェクト操作といえば gsutil で決まりでしたが、今後は gcloud storage cp も問われる問題が出てくるかもしれません。
</div></details>

## Q. 2-27
認証サービスからの監査イベントの取り込みを再設計してトラフィックの大幅な増加を処理できるようにする必要があります。
現在、監査サービスと認証システムは同じ Compute Engine 仮想マシンで実行されています。
新しいアーキテクチャで次の Google Cloud ツールを使用する予定です。
* それぞれが認証サービスのインスタンスを実行する複数の Compute Engine マシン
* それぞれが監査サービスのインスタンスを実行する複数の Compute Engine マシン
* 認証サービスからイベントを送信するための Cloud Pub/Sub。
システムが大量のメッセージを処理し、効率的にスケーリングできるようにするにはトピックとサブスクリプションをどのように設定する必要がありますか？
1. Pub/Subトピックを1つ作成します。Pullサブスクリプションを1つ生成して監査サービスがメッセージを共有できるようにします
2. Pub/Subトピックを1つ作成します。監査サービスインスタンスフォトに1つPullサブスクリプションを作成してサービスがメッセージを共有できるようにします
3. Pub/Subトピックを1つ作成します。エンドポイントが監査サービスの前にあるロードバランサを指す1つのPushサブスクリプションを作成します
4. 認証サービスごとに1つのPub/Subトピックを作成します。1つの監査サービスで使用されるトピックごとに1つのPullサブスクリプションを作成します
5. 認証サービスごとに1つのPub/Subトピックを作成します。トピックごとに1つのPullサブスクリプションを作成し、エンドポイントが1つの監査サービスを指すようにします
<details><div>
    答え：1
D. E. は認証サービスのスケーリングに対応出来ないので、真っ先に選択肢から外れます。
B.は同じ認証処理に対して重複して監査処理が行われる事になるので、これも容易に除外できます。
C.は前半はよさそうに見えます（実は私はエンドポイントにpushするという事が可能かどうか分からりませんが、可能だとして（経験は無いですが可能なように思える））が、Pushでサブスクリプションを行うと、処理負荷がダイレクトにサブスクライバーにかかることになりトラフィック負荷が大幅に増える環境では使用に適さないと考えます(大量にPushされてもサブスクライバーは処理しきれない状況が発生する可能性がある為、高負荷でPushは間違いと考えて良いでしょう)。
C.のPushに対して、通常使われるPullサブスクリプションはスケーリングを抑えても順次処理することができるので、安心感のある安全な方法です。
「効率的にスケーリングできるようにする」という点で条件に最も合っていると考えられますので、A.が正解となります。
</div></details>

## Q. 2-28
Cloud Pub/Sub サブスクリプションからクレジット カード データを読み取るアプリケーションを開発しています。
コードを記述し、単体テストを完了しました。Google Cloud にデプロイする前に Cloud Pub/Sub 統合をテストする必要があります。
どうすればいいでしょうか？
1. メッセージを発行するサービスを作成し、Pub/Subエミュレータをデプロイします。パブリッシュサービスでランダムなコンテンツを生成し、エミュレータにパブリッシュします
2. アプリケーションにメッセージを発行するサービスを作成します。本番環境のPub/Subからメッセージを収集し、パブリッシングサービスを通じてそれらを再生します
3. メッセージを発行するサービスを作成し、Pub/Subエミュレータをデプロイします。本番環境のPub/Subからメッセージを収集し、エミュレータに公開します
4. メッセージを発行するサービスを作成し、Pub/Subエミュレータをデプロイします。パブリッシュサービスでエミュレータにテストメッセージの標準セットをパブリッシュします
<details><div>
    答え：4
解説：
開発、テストは実際のインスタンスを利用するよりも、ローカルで行う方がコーティング、動作チェックが最も楽な方法になります。
ソースコードの開発では、おそらく殆どの開発でローカルでの開発環境を整えていると思いますが、Cluod Pub/Sub のテストも同様です。
基本的にはローカル上のテストに本番環境を絡めるのは誤りと考えます（実運用では、必要性があるケースに直面する場合もあるかもしれませんが）。
本問題に限らず、ローカルでの検証（つまり各種エミュレーターの利用）は有効で、問題と指定はそれが記述されている選択肢が正解となっています。
ここでは、A, D.の二択にまではすぐに絞れます。
サブスクリプションを処理する処理の単体テストは完了していることから、その処理が想定するメッセージが送信できれば良いと考えられるので、単体テストで使われたであろうメッセージをパブリッシュすれば良いと考えられます。
従って D.を正解として選択します。
</div></details>

## Q. 2-29
API バックエンドが複数のクラウド プロバイダで実行されています。
API のネットワーク遅延に関するレポートを生成したいと考えています。
どのような手順で実行するべきでしょうか？(回答は 2 つ)
1. Zipkinコレクタを使用してデータを収集します
2. Fluendエージェントを使用してデータを収集します
3. ClooudTraceを使用してレポートを生成します
4. CloudDebuggerを使用してレポートを生成します
5. CloudProfilerを使用してレポートを生成します
<details><div>
    答え：1,3
(1) Cloud Trace と Zipkin の使用
https://cloud.google.com/trace/docs/zipkin?hl=ja
(2) Cloud Profiler の概要
https://cloud.google.com/profiler/docs/about-profiler?hl=ja
解説：
Google Cloud の分散トレース システムである Cloud Trace を使用すると、ユーザーや他のアプリケーションからの受信リクエストをアプリケーションが処理するのにかかる時間や、リクエストの処理時に実行されるオペレーション（RPC 呼び出しなど）が完了するのにかかる時間を知ることができます。
BのFluentdは、個々のシステム毎に管理されている大量のログファイルを収集、解析し、ストレージに集約、保存を行うツールとして活用されています。
よって、遅延の調査というテーマに関して直接的ではありません（ログから何らかの手がかりは得られるかもしれませんが、試験問題的には除外される選択肢でしょう）。
D.のDebuggerは不具合の調査に有効です。
E.のProfilerはCPU 使用率やメモリ割り当てなどの情報を継続的に収集する、オーバーヘッドの少ないプロファイラです。収集した情報から情報の生成元であるソースコードが特定されるので、最もリソースを消費しているアプリケーション部分を容易に識別できます。アプリケーションの特定が難しい場合でも、パフォーマンスの特徴を把握できます。(以上(2)より抜粋)
ネットワーク遅延の調査ではTracerの方が有効でしょう。
これらと(1)の情報から A, Cが正解となります。
(1)の内容を知らなくても、以上のように考えて消去法で、A, C を選択することが可能でしょう。
</div></details>

## Q. 2-30
オンプレミス データセンターを Google Cloud に移行する最終段階にいます。
締め切りが迫っており、廃止予定のサーバで Web API が実行されていることを発見しました。
Google Cloud への移行中にこの API をモダナイズするためのソリューションを推奨する必要があります。
* 最新の Web API は次の要件を満たす必要があります。
* 毎月末のトラフィックの多い時間帯に自動スケーリング
* Python 3.x で書かれています
開発者は頻繁なコード変更に対応して新しいバージョンを迅速にデプロイできなければなりません
この移行のコスト、労力、運用上のオーバーヘッドを最小限に抑える必要があります。
どうすればいいでしょうか？
1. AppEngineフレキシブル環境にコードモダナイズしてデプロイします
2. AppEngineスタンダード環境にコードモダナイズしてデプロイします
3. モダナイズされたアプリケーションをn1-standard-1 ComputeEngineインスタンスにデプロイします
4. 開発チームにアプリケーションを書き直してGKEでDockerコンテナとして実行するように依頼します
<details><div>
    答え：2
「コスト、労力、運用上のオーバーヘッドを最小限」という事で、マネージドサービスが使われている選択肢が正解で間違いなし。
ということで、選択肢は A, Bに絞られます。
ゼロスケールが可能であることと、急激なスパイクにより強い「App Engine スタンダード」を選択しましょう。
B が正解です。
</div></details>

## Q. 3-1
ベスト プラクティスに準拠するために Cloud Build の手順を確認して更新しています。
現在、ビルド手順は次のとおりです。
1．ソース リポジトリからソース コードを取得します。
2．コンテナ イメージをビルドする
3．ビルドしたイメージを Artifact Registry にアップロードします。
ビルドされたコンテナ イメージの脆弱性スキャンを実行するステップを追加する必要があり、スキャンの結果を Google Cloud で実行されているデプロイ パイプラインで利用できるようにする必要があります。
他のチームのプロセスを混乱させる可能性のある変更を最小限に抑えたいと考えています。

どうすればいいでしょうか？
1. BineryAuthorizarion を有効にし、コンテナイメージに脆弱性がないことを証明するように構成します
2. ビルドされたコンテナイメージをDockerHubインスタンスにアップロードし、脆弱性をスキャンします
3. AritifactRegistryでContainerSccanningAPIを有効にし、ビルドされたコンテナイメージの脆弱性をスキャンします
4. AritifactRegistryをAquaSecurityインスタンスに追加し、構築されたコンテナイメージの脆弱性をスキャンします
<details><div>
    答え：３
脆弱性のスキャン機能  Artifact Registr  に備わっている機能なので、これを利用すればOKです。

Aは証明書の発行で脆弱性スキャンの話をしていません。

Bのような事をするケースを聞いたことがありません。

Dもかなりおかしなことをしていますね。Artifact Registryはプロジェクトで利用許可するば使えますので、このようなおかしなことをする必要がありません。

(Artifact Registry は Google Container Registry(GCR)の上位のContainer Registryです。

現在GCRを使っている場合はArtifact Registryへの移行が推奨されています。)
</div></details>

## Q. 3-2
Google Cloud で実行されるウェブ アプリケーションを開発しています。

ほとんどの日はトラフィックがなく、それ以外の日は大きいスパイクが発生するため、着信するユーザー トラフィックのレートは予測できないと想定しています。

アプリケーションが自動的にスケールアップ、スケールダウンするようにするとともに、アプリケーションの実行に伴う費用を最小化する必要があります。どうすればよいですか。
1. Firestoreをデータベースとしてアプリケーションを構成します。そのアプリケーションをCloudRunにデプロイする
2. Firestoreをデータベースとしてアプリケーションを構成します。そのアプリケーションをGKEクラスタにデプロイする
3. CloudSQLをデータベースとしてアプリケーションを構成します。そのアプリケーションをGKEクラスタにデプロイする
4. Firestoreをデータベースとしてアプリケーションを構成します。そのアプリケーションをComputeEngineマネージドインスタンスグループにデプロイし、自動スケーリングを適用する
<details><div>
    答え：１
解説：
A は正解です。Cloud Run はゼロへのスケーリングをサポートしています。
さらに、Firestore の費用はストレージのみです。
そのため、トラフィックがない場合は運用の費用はゼロです。
B は不正解です。
GKE はゼロへのスケーリングを行いません。
C は不正解です。
GKE はゼロへのスケーリングを行いません。
さらに、Cloud SQL の実行に関連する費用が発生します。
D は不正解です。
Compute Engine はゼロへのスケーリングを行わないインスタンスを管理します。
少なくとも 1 つのインスタンスが実行されている必要があります。
Reference:
(1) サーバーレス
https://cloud.google.com/serverless?hl=ja
(2) Cloud Run
https://cloud.google.com/run?hl=ja
</div></details>

## Q. 3-3
チームは Google Kubernetes Engine (GKE) クラスタでホストされるアプリケーションを作成しました。

アプリケーションを 2つの異なる地域の2つのGKEクラスターにデプロイされているレガシーRESTサービスに接続する必要があります。

アプリケーションとターゲットサービスを柔軟性のある方法で接続したい。

また、別のポートでレガシーサービスのヘルスチェックを実行できるようにしたいと思います。

接続をどのように設定しますか？ (回答は 2 つ)
1. サイドカープロキシでTrafficDirectorを使用してアプリケーションをサービスに接続します
2. プロキシレスTrafficDirector構成を使用してアプリケーションをサービスに接続します
3. レガシーサービスのファイアウォールを構成してプロキシからのヘルスチェックを許可する
4. アプリケーションからのヘルスチェックを許可するようにレガシーサービスのファイアウォールを構成します
5. 従来のサービスのファイアウォールを構成してTrafficDirectorコントロールプレーンからのヘルスチェックを許可する
<details><div>
    答え：1,3
解説：
なかなか難しい問題かと思います。
このアプリケーションは「レガシーRESTサービスに接続する必要があります」との事から、通信はhttps で行う事になります。
この場合はサイドカープロキシーで Traffic Director を使用する事になります。
これにより設問に記載の要件を満たすことができます。
プロキシーを利用していることから、Cの「プロキシからのヘルスチェックを許可する」が適切であると考えます。
ヘルスチェックのリクエストはプロキシーを通して行われるので、Eは不正解です。
従って本問題の正解は A, C となります。
Reference:
(1) 複数の GKE クラスタで共有 VPC を使用した Traffic Director の構成
https://cloud.google.com/architecture/configuring-traffic-director-with-shared-vpc-on-multiple-gke-clusters?hl=ja
(2) Traffic Director の概要
https://cloud.google.com/traffic-director/docs/overview?hl=ja
(3) プロキシレス gRPC サービスを使用した Traffic Director の概要
https://cloud.google.com/traffic-director/docs/proxyless-overview?hl=ja
(4) ヘルスチェックの概要
https://cloud.google.com/load-balancing/docs/health-check-concepts?hl=ja
</div></details>

## Q. 3-4
オンプレミス データセンターを Google Cloud に移行する最終段階にいるとします。
最終期限が迫っていますが、サーバーで実行しているウェブ API が廃止予定であることがわかりました。
この API のモダナイズと Google Cloud への移行を両立させるソリューションを提案する必要があります。
モダナイズ後のウェブ API は、次の要件を満たしている必要があります。
* 毎月末のトラフィックが多い期間に自動スケールする
* Python 3.x で記述されている
* デベロッパーが頻繁なコード変更に応じた新しいバージョンを素早くデプロイできる
サービス実行に伴う費用、作業、運用オーバーヘッドを最小限に抑えるには、どうすれば良いですか。
1. コードをモダナイズしてAppEngineフレキシブル環境にデプロイします。
2. コードをモダナイズしてCloudRunにデプロイします。
3. モダナイズしたアプリケーションをn1-standaed-1ComputeEngineインスタンスにデプロイする
4. GKEでのコンテナとして実行されるようにアプリケーションを作り直すことを開発チームに依頼する
<details><div>
    答え：2
解説：
A は不正解です。
このアプローチはすべての要件を満たしますが、費用が最小ではありません。
App Engine フレキシブルでは、常に 1 つ以上のインスタンスがオンラインになります。
B は正解です。
Cloud Run はすべての要件を満たします。
従量課金制で、0 インスタンスから自動スケーリングするように設計され、秒単位でデプロイできます。
C は不正解です。
解決策にはなりますが、要件をすべて満たすわけではありません。
単一インスタンスは自動的にスケーリングしません。
さらに、すべての要件を満たすには、追加の作業と継続的なサーバー管理や設定などが必要になります。
D は不正解です。
要件をすべて満たしますが、費用や作業が最小ではありません。
Reference:
(1) App Engine フレキシブル環境
https://cloud.google.com/appengine/docs/flexible?hl=ja
(2) App Engine 環境を選択する
https://cloud.google.com/appengine/docs/the-appengine-environments?hl=ja
(3) Cloud Run とは
https://cloud.google.com/run/docs/overview/what-is-cloud-run?hl=ja
</div></details>

## Q. 3-5
インターネットに接続するマイクロサービス アプリケーションを Google Kubernetes Engine (GKE) にデプロイする必要があります。
A/B テスト方法を使用して新機能を検証したいと考えています。
新しいコンテナ イメージ リリースをデプロイするには次の要件があります。
新しいコンテナイメージをデプロイする際のダウンタイムはありません。
新しい本番リリースは本番ユーザーのサブセットを使用してテストおよび検証されます。
どうすればいいでしょうか？
1. CI/CDパイプラインを構成してコンテナのバージョンを最新バージョンに置き換えてデプロイマニュフェストを更新します。Deploymentマニュフェストファイルを適用してクラスタないにPodを再作成します。アプリケーションの機能を以前のリリースバージョンと比較してアプリケーションのパフォーマンスを検証し、問題が発生した場合はロールバックします
2. 新しいバージョンようにGKEに2番目の名前空間を作成します。必要な数のPodを使用して2番目の名前空間のデプロイ攻勢を作成します。新しいコンテナバージョンを2番目の名前空間にデプロイする。Ingress構成を更新してトラフィックを新しいコンテナバージョンの名前空間にルーティングします
3. GKEクラスタにAnthosServiceMeshをインストールします。GKEクラスタに2つのDeploymentを作成し、それらに異なるバージョン名のラベルを付けます。Istioルーティングルールを実装して新しいバージョンのアプリケーションを参照するDeploymentにトラフィックのごく一部を送信します
4. Podを徐々に新しいリリースバージョンに置き換えることでローリングアップデータバージョンを実装します。ロールアウト中に新しいユーザーのサブセットに対するアプリケーションのパフォーマンスを検証し、問題が発生した場合はロールバックします
<details><div>
    答え：3
解説：
まず D はないですね。
新バージョンにどんどん置き換わってしまい、検証が十分に行えません。
A/B テストを行うアップデート方法ではありません。
Aも全体を新バージョンに変更した後に検証を行うことになり、同じ条件での比較はできないので却下でしょう。(A/Bテストとは言えないでしょう)
Bはアクセス元のアプリケーションの更新は行わないと考えられるので、どういうルールで振り分けるのかが不明です（アクセスURLは同じ）
Istioにはマイクロサービス間通信のトラフィック制御機能があるので、一定数のトラフィックを簡単に新バージョンに向けらるでしょう。
Anthos Service Meshとは Istioのマネージドサービスです。
正解は C です。
もし正解に迷った場合は、最終的に手間のかからないマネージドサービスを利用している選択肢を選ぶと正解の可能性が高いでしょう。
Referenceの(1)は抑えておきましょう。デプロイ戦略系の問題に強くなれます。
Reference:
(1) アプリケーションのデプロイとテストの戦略
https://cloud.google.com/architecture/application-deployment-and-testing-strategies?hl=ja
(2) Anthos Service Mesh
https://cloud.google.com/anthos/service-mesh?hl=ja
</div></details>

## Q. 3-6
あなたの会社で提供しているマルチプレーヤー ゲームは米国で人気があります。
そこで今回、提供範囲を他のリージョンにも拡大することになりました。
また、ユーザー同士がポイントを交換できる新機能をリリースする予定です。
この機能は全世界のユーザーが利用できるようにします。
会社で現在使用している MySQL バックエンドでは、ゲームをホストしている Compute Engine インスタンスが間もなく上限に達します。
そのため、対象のリージョン全体での整合性と高可用性を実現できる他のデータベースに移行することを検討しています。
どのデータベースを選択すればよいですか。
1. BigQuery
2. CloudSQL
3. CloudSpanner
4. CloudBigtable
<details><div>
    答え：3
解説：
A は不正解です。
BigQuery をトランザクション データベースとして使用することはできません。
B は不正解です。
Cloud SQL では複数のリージョンでの高可用性を実現できません。
C は正解です。
Cloud Spanner のみがグローバルでの整合性と可用性を実現できます。
D は不正解です。
Cloud Bigtable ではグローバルでの可用性を実現できません。
(1) Cloud Spanner
https://cloud.google.com/spanner?hl=ja
</div></details>

## Q. 3-7
最近、ログデータを Cloud Storage バケットに毎日転送する Web アプリケーションを開発しました。
認証されたユーザーは重要なイベントについて過去 2 週間のログを定期的に確認します。
その後、ログは年に 1 回、外部監査人によってレビューされます。
データは 7 年以上保存する必要があります。
これらの要件を満たし、コストを最小限に抑えるストレージ ソリューションを提案したいと考えています。
どうすればいいでしょうか？ (回答は 2 つ)
1. バケットロック機能を使用してデータの保持ポリシーを設定します
2. スケジュールされたジョブを実行して、14日以上経過したオブジェクトのストレージクラスをColdlineに設定します
3. Coldlineストレージバケットへのアクセスが必要なユーザーのためにJSONWebTokenを作成します
4. ライフサイクル管理ポリシーを作成して14日以上経過したオブジェクトのストレージクラスのColdlineに設定します
5. ライフサイクル管理ポリシーを作成して14日以上経過したオブジェクトのストレージクラスをNearlineに設定します
<details><div>
    答え：1,4
解説：
問題として取り上げられやすく、きちんと押さえていれば確実に正解できる問題なので、Referenceに記載した公式ドキュメントで良く勉強しておきましょう。
まず、不用意な削除や確実に保持期間を守れるA. は正解でしょう。
2週間後は１年に１度程度しか参照されないのでストレージオプションを変更しておくべきでしょう。
現状ではは Archive Storege が適切ですが、新たに追加されたオプションでこのオプションが存在しない場合は1年に一回ほどのアクセスの場合は、ColdlineStorageが使われていました。
現状ベストではないですが、選択肢の中では D. のColdline Storageを使用する設定が最も良い選択となります。
B.のように特別な操作をしなくともCloud Storageの機能としてオプションの変更が可能です。
余計なツールを使って一生懸命オプションを変更しようとしている選択肢は誤りの可能性が高いです。
ここでもBに記載の操作の必要はありません。
Cは最初からColdlineではない事や、7年後の削除や監査に必要な大事なデータの保護、すでに「認証されたユーザーは」という記載があることから考えて適切ではありません。
Nearlineは1か月～３か月位に参照される場合に適切でColdlineよりも頻繁に参照が必要な場合に選択するオプションなので、本問の場合は Coldline よりもコスト高となり不適切です。
正解は、A, D となります。
Reference:
(1) Cloud Storage
https://cloud.google.com/storage?hl=ja
(2) 保持ポリシーと保持ポリシーのロック
https://cloud.google.com/storage/docs/bucket-lock?hl=ja
</div></details>

## Q. 3-8
あなたの組織のウェブサイトは Compute Engine にデプロイされています。
マーケティング チームでは、異なる 3 つのデザインのウェブサイトでコンバージョン率をテストしたいと考えています。
アプリケーションのコードを変更することはできません。どうすればよいですか。
1. ウェブサイトをCloudRunにデプロイし、トラフィック分割を使用する
2. ウェブサイトを3つの個別のリビジョンとしてCloudRunにデプロイします。
3. ウェブサイトを3つの個別の機能としてCloudRunにデプロイします。
4. ウェブサイトをCloudFunctionsにデプロイし、カスタムコードを実装して異なるデザインを表示します
<details><div>
    答え：1
解説：
A は正解です。この方法により、トラフィックを単一のドメインにルーティングし、割合に基づいてトラフィックを分割できます。
B は不正解です。ドメイン名はリビジョンに基づいて変更されます。
C, Dは不正解です。
C, D いずれにしても Aに比べてデプロイの手間がかかりますし、Cloud Functions がWebサイトとして利用されることはありません(Reference(2)のユースケース例にありません）。
Reference:
(1) ロールバック、段階的なロールアウト、トラフィックの移行(Cloud Run)
https://cloud.google.com/run/docs/rollouts-rollbacks-traffic-migration?hl=ja
(2) Cloud Functions の概要
https://cloud.google.com/functions/docs/concepts/overview?hl=ja
</div></details>

## Q. 3-9
オンラインの eコマース Web サイトを管理する組織で働いています。
会社は世界中に拡大する予定です。
ただし、ストアは現在 1つの特定の地域にサービスを提供しています。
SQLデータベースを選択し、組織の成長に合わせて拡張できるスキーマを構成する必要があります。
すべての顧客トランザクションを格納するテーブルを作成し、顧客 (CustomerId) とトランザクション (TransactionId) が一意であることを確認したいと考えています。
どうすればいいでしょうか。
1. 主キーとして設定されたTransctionldとCustomerldを持つCloudSQLテーブルを作成します。Transctionldには増分番号を使用します
2. TransctionldとCustomerldが主キーとして構成されたCloudSQLテーブルを作成する。Transctionldにはランダムな文字列を使用します。
3. TransctionldとCustomerldが主キーとして構成されたCloudSpannerテーブルを作成する。Transctionldにはランダムな文字列を使用します。
4. TransctionldとCustomerldが主キーとして構成されたCloudSpannerテーブルを作成する。Transctionldには増分番号を使用します
<details><div>
    答え：3
解説：
今後「世界中に拡大する予定」からマルチリージョンに対応し、スケーラビリティの高いSQLデーターベースを選択することから、データーベースとしては Cloud Spannerを選択します。
Cloud Spannerで効果的な分散性能を発揮する為には、プライマリーキーはシーケンシャルではないキーを選択する必要がありますので、正解は C となります。
Reference:
(1) スキーマ設計のベスト プラクティス
https://cloud.google.com/spanner/docs/schema-design?hl=ja
</div></details>

## Q. 3-10
新しい API をデプロイする責任があります。
その API には 3 つの異なる URL パスがあります。
* https://yourcompany.com/students
* https://yourcompany.com/teachers
* https://yourcompany.com/classes
コード内で異なる関数を呼び出すには各 API URL パスを構成する必要があります。
どうすればいいでしょうか？
1. HTTPロードバランサを使用して公開されるバックエンドサービスとしてCloudFunctionsを1つ作成します
2. 直接公開される3つのCloudFunctionsを作成します
3. 直接公開されるCloudFunctionsを1つ作成します
4. HTTPロードバランサを使用して公開される3つのバックエンドサービスとして3つのCloudFunctionsを作成します
<details><div>
    答え：4
解説：
異なる関数を呼び出したいとのことなので、Cloud Functionsは3つ必要です。
公開する場合は、外部用のURLをGoogle Cloud内のURLにマッピングする必要があるので、直接公開は出来ません。
Cloud Functionsを3つ用意する事と、ロードバランサーを使用する必要があることから、正解は D となります。
</div></details>

## Q. 3-11
最近、本番環境で実行されている Cloud Spanner データベースインスタンスを持つ新しいチームに参加しました。
上司から Cloud Spanner インスタンスを最適化してデータベースの高い信頼性と可用性を維持しながらコストを削減するよう依頼されました。
どうすればいいでしょうか？
1. CloudLoggingを使用してエラーログを確認し、必要な最小容量が見つかるまで、Spanner処理ユニットを少しずつ減らします
2. CloudTraceを使用してCloudSpannerへの受信リクエストの1秒当たりのリクエストをモニタリングし、必要な最小容量が見つかるまで、CloudSpanner処理ユニットを少しずつ減らします
3. ClouMonitoringを使用してCPU使用率をモニタリングし、必要な最小容量が見つかるまでCloudSpanner処理ユニットを少しずつ減らします
4. SnapshotDebuggerを使用してアプリケーションエラーをチェックし、必要な最小容量が見つかるまでCloudSpanner処理ユニットを少しずつ減らします
<details><div>
    答え：3
解説：
エラーやレイテンシーを調査しているわけではないので、そういった記述をしている選択肢は除外できます。
この時点で A, B, Dが除外できます。
C の内容を確認すると良いのではないでしょうか。
リソースの使用率を監視しながら、処理ユニットを減らし、いい感じに寸止めしたいですね（冗談です。あまりにもギリギリは止めておきましょう）。
Reference (1) 内にもほぼ同様の手順が記載されています。
いざという時は Spannerも自動スケールする(実際はコールドスタートではサービスに影響がでてしまうので準備しておくのが良いようです）ので、通常の適正値はきちんと判断してコストを抑える事は大事だと思います。
正解は C となります。
Reference:
(1) コンピューティング容量の増減
https://cloud.google.com/spanner/docs/compute-capacity?hl=ja#increasing_and_decreasing_compute_capacity
</div></details>

## Q. 3-12
Cloud Pub/Sub メッセージを読み取って処理するアプリケーションが Google Kubernetes Engine (GKE) にデプロイされています。
各 Pod は 1分あたり一定数のメッセージを処理します。
メッセージが Cloud Pub/Sub トピックにパブリッシュされる頻度は 1日および 1週間を通して大きく異なります。
これには一度に大規模なメッセージのバッチが時折パブリッシュされることもあります。
メッセージをタイムリーに処理できるように GKE Deployment をスケーリングしたいと考えています。
ワークロードを自動的に適応させるには どの GKE 機能を使用しますか？
1. Autoモードの垂直Podオートスケーラー
2. レコメンデーションモードの垂直Podオートスケーラー
3. 外部メトリックに基づく水平Podオートスケーラー
4. リソース使用率に基づく水平Podオートスケーラー
<details><div>
    答え：3
解説：
リクエストの増減によるスケーリングは水平スケールになりますので、垂直スケールは除外します。
Professional Cloud Developerの問題で垂直スケールが出てくることはほぼないのではないかと思います。
垂直スケールはインスタンス自体を強化することなので、Date Enginearの世界では必要な事なのかもしれません。
CPU使用率、メモリー使用率等のPodやクラスタの内部指標に基づいてスケールするわけではなく、Pub/Subをサブスクライブする為のスケールなので外部メトリックスによる水平スケールとなります。
よって正解は C となります。
</div></details>

## Q. 3-13
マイクロサービス アーキテクチャを使用するアプリケーションを設計しています。
クラウドとオンプレミスにアプリケーションをデプロイする予定です。
アプリケーションがオンデマンドでスケールアップできるようにし、マネージドサービスを可能な限り使用できるようにする必要があります。
どうすればいいでしょうか？
1. Antosによって管理される複数のGKEクラスタ上のマルチクラスタデプロイでオープンソースのIstioをデプロイします。
2. Anthosを使用して各環境にGKEクラスタを作成し、CloudRunforAntosを使用してアプリケーションを各クラスタにデプロイします
3. Anthosを使用して各環境にGKEクラスタをインストールし、CloudBuildを使用して各クラスタにアプリケーションのDeploymentを作成します
4. クラウドにGKEクラスタを作成し、オープンソースのK8Sをオンプレミスにインストールします。外部ロードバランサを使用し、2つの環境にトラフィックを分散します
<details><div>
    答え：2
解説：
A, C, Dは明らかにマネージドサービスを使用していないか言及がありません。
C.は Deployment を作成するという事からGKEでしょう。
よって正解は B となります。
B. の記述内容に特に問題はありません。
</div></details>

## Q. 3-14
チームは金融機関向けのアプリケーションを構築しています。
アプリケーションのフロントエンドは Compute Engine で実行され、データは Cloud SQL と 1つの Cloud Storage バケットに存在します。
アプリケーションは PII を含むデータを収集し、Cloud SQL データベースと Cloud Storage バケットに保存します。
PII データを保護する必要があります。
どうすればいいでしょうか？
1. フロントエンドのみがCloudSQLデータベースと通信できるように関連するファイアウォールを構成します。IAMを使用し、フロントエンドサービスアカウントのみにCloudStorageバケットへのアクセスを許可します
2. フロントエンドのみがCloudSQLデータベースと通信できるように関連するファイアウォールを構成します。プライベートアクセスを有効にして、フロントエンドがCloudStorageバケットに非公開でアクセスできるようにします
3. CloudSQLのプライベートIPアドレスを構成します。VPC-SCを使用してサービス境界を作成します。CloudSQLデータベースとCloudStorageバケットを同じサービス境界に追加します
4. CloudSQLのプライベートIPアドレスを構成します。VPC-SCを使用してサービス境界を作成します。CloudSQLデータベースとCloudStorageバケットを異なるサービス境界に追加します
<details><div>
    答え：3
解説：
フロントエンドがPIIデーターを含むCloudSQLに通信できるのは危険です。
A, Bは除外ですね。
複数のVPC-SCするのは冗長で管理も複雑になるので、C で十分でしょう。
C が正解となります。
</div></details>

## Q. 3-15
オンプレミスの Linux 仮想マシン (VM) で実行されているスタンドアロンJavaアプリケーションを費用対効果の高い方法で Google Cloud に移行する必要があります。
リフトアンドシフトアプローチを採用しないことに決め、代わりにアプリケーションをコンテナに変換して最新化することを計画しています。
このタスクをどのように達成する必要がありますか？
1. MigrateforAnthosを使用し、VMをコンテナとしてGKEクラスタに移行します
2. VMをRAWディスクとしてエクスポートし、イメージとしてインポートします。インポートしたイメージからComputeEngineインスタンスを作成します
3. MigrateforComputeEngineを使用してVMをComputeEngineインスタンスに移行し、CloudBuildを使用してそれをコンテナに変換します
4. Jibを使用してソースコードからDockerイメージを構築し、Artifactregistoryにアップロードします。アプリケーションをGKEクラスタにデプロイし、アプリケーションをテストします
<details><div>
    答え：4
解説：
「アプリケーションをコンテナに変換して最新化する」という事から、オンプレス上で動作しているアプリをそのままGoogle Cloudに持ってくるわけではないことからB, Cは除外ですね。
(CはVMをGCEに移行してコンテナ化って、そういう事じゃないでしょ)
A, Dは迷うところですが、AがまずはVMを丸っとコンテナ化するというのはまさしくリフトアンドシフトと言えるでしょう。
Jibでオンプレミスのアプリケーションを簡単にコンテナ化できます。
従って、本問題の正解は D となります。
Reference:
(1) Anthos の詳細: Java のレガシー アプリケーションを変換する
https://cloud.google.com/blog/ja/topics/anthos/java-app-modernization-with-anthos/
(Jibで簡単にコンテナ化できる記述があります)
(2) Jib を使用して Java コンテナを構築する
https://cloud.google.com/java/getting-started/jib?hl=ja
(3) Jib の紹介 ? Java Docker イメージをより良く構築する
https://cloud.google.com/blog/products/application-development/introducing-jib-build-java-docker-images-better
</div></details>

## Q. 3-16
ユーザーに属するファイルを Cloud Storage に保存する必要があるアプリケーションを開発しています。
各ユーザーが Cloud Storage に独自のサブディレクトリを持つようにします。
新しいユーザーが作成されると対応する空のサブディレクトリも作成されます。
どうすればいいでしょうか？
1. 長さが０バイトの末尾のスラッシュで終わるサブディレクトリの名前を持つオブジェクトを作成します
2. サブディレクトリの名前でオブジェクトを作成し、そのサブディレクトリ内のオブジェクトをすぐに削除します
3. 長さが０バイトでWRITERアクセス制御リスト許可を持つサブディレクトリの名前を持つオブジェクトを作成します
4. 長さが０バイトのサブディレクトリの名前を持つオブジェクトを作成します。Content-TypeメタデータをCLOUDSTORAGE_FOLDERに設定します
<details><div>
    答え：1
解説：
CloudStorageには空のフォルダーを作成する事ができます。
特にダミーのオブジェクトを作る必要はないので、ストレートに A の対応でOKです。
Reference (1) をご参照下さい。
正解は A となります。
Referecne:
(1) フォルダ
https://cloud.google.com/storage/docs/folders?hl=ja#overview
</div></details>

## Q. 3-17
チームは Google Cloud で実行されるサービスを開発しています。
Cloud Pub/Sub トピックに送信されたメッセージを処理してから保存したいと考えています。
データの重複やデータの競合を避けるために、各メッセージは 1回だけ処理する必要があります。
最も安価で最もシンプルなソリューションを使用する必要があります。
どうすればいいでしょうか？
1. Dataprocジョブでメッセージを処理し、出力をストレージに書き込みます
2. ApacheBeamのPub/SubIOパッケージを使用してDataflowストリーミングパイプラインでメッセージを処理し、出力をストレージに書き込みます
3. CloudFunstionsを使用してメッセージを処理し、データを重複排除するジョブを実行できるBigQueryの場所に結果を書き込みます
4. Dataflowストリーミングパイプラインでメッセージを取得してCloudBigtableに保存し、別のDataflowストリーミングパイプラインを使用してメッセージの重複を取り除きます
<details><div>
    答え：2
解説：
Dはシンプルではないですね。
除外です。
A, Cは別途プログラム処理を行わなければならない点で「最も安価で最もシンプルなソリューション」としては B に劣るでしょう。
Cに関しては更にBigQueryの使い方も贅沢な使い方に感じます。
「最も安価で最もシンプルなソリューション」としては B が正解となります。
Reference:
(1) Pub/Sub を使用したストリーミング
https://cloud.google.com/dataflow/docs/concepts/streaming-with-cloud-pubsub?hl=ja
</div></details>

## Q. 3-18
開発チームは .NET レガシ アプリケーションの保守を任されています。
アプリケーションは時折変更され、最近更新されました。
目標は環境から環境へと CI/CD パイプラインを移動しながら、アプリケーションが一貫した結果を提供できるようにすることです。
外部要因とホスティング環境間の依存関係が問題にならないようにしながら、デプロイコストを最小限に抑える必要がありますがコンテナは組織でまだ承認されていません。
どうすればいいでしょうか？
1. .NET Coreを使用してアプリケーションを書き直し、Cloudrunにデプロイします。リビジョンを使用して環境を分離します
2. CloudBuildを使用してビルドごとに新しいComputeEngineイメージとしてアプリケーションをデプロイします。各環境でこのイメージを使用します
3. MSWebDeployを使用してアプリケーションをデプロイし、常に最新パッチ適用済MSWindowServerベースイメージをComputeEngineで使用するようにします
4. CloudBuildを使用してアプリケーションをパッケージ化し、GKEクラスタにデプロイします。名前空間を使用して環境を分離します
<details><div>
    答え：2
解説：
「コンテナは組織でまだ承認されていません」という記述から、A, D.が真っ先に除外できます。
「外部要因とホスティング環境間の依存関係が問題にならないようにしながら」という記述から、Compute Engine イメージとしてデプロイし実行する事が必要です。
従って正解は B となります。
Reference:
(1) Google Cloud における .NET アプリケーションのモダナイゼーションへの移行
https://cloud.google.com/architecture/modernization-path-dotnet-applications-google-cloud?hl=ja
</div></details>

## Q. 3-19
運用チームからプロジェクト内で実行されている Cloud Bigtable、Memorystore、Cloud SQL データベースを一覧表示するスクリプトを作成するよう依頼されました。
スクリプトではユーザーがフィルター式を送信して表示される結果を制限できるようにする必要があります。
どのようにデータを取得しますか？
1. HBaseAPI、RediAPI、MySQL接続を使用してデータベースリストを取得します。結果を結合し、フィルタを適用して結果を表示します。
2. HBaseAPI、RediAPI、MySQL接続を使用してデータベースリストを取得します。結果を個別にフィルタを適用してそれらを組み合わせて結果を表示します
3. gcloud bigtable instances list、glcoud redis instances list、gcloud sql databases list を事項します。アプリケーション内でフィルタを使用し、結果を表示します
4. gcloud bigtable instances list、glcoud redis instances list、gcloud sql databases list を事項します。各コマンドで-filterフラグを使用し、結果を表示します
<details><div>
    答え：4
解説：
glcoud instancesコマンドで要件を満たすことができます。
-filter オプションでフィルタリングできるので、これを利用する方が、アプリ内でフィルタリング処理するよりも簡単です。
従って正解は D です。
</div></details>

## Q. 3-20
後にそれらの購入をキャンセルまたは変更できる顧客からの購入を処理する eコマース アプリケーションを管理します。
注文量が非常に変動しやすく、バックエンドの注文処理システムが一度に 1つの要求しか処理できないことがわかりました。
使用量に関係なく、顧客のためにシームレスなパフォーマンスを確保したいと考えています。
顧客の注文更新リクエストは生成された順序で実行されることが重要です。
どうすればいいでしょうか？
1. WebSocketを介して購入及び変更要求をバックエンドに送信します
2. 購入と変更のリクエストをRESTリクエストとしてバックエンドに送信します
3. pullモードでPub/Subサブスクライバーを使用し、Datastoreを使用して注文を管理します
4. pushモードでPub/Subサブスクライバーを使用し、Datastoreを使用して注文を管理します
<details><div>
    答え：3
解説：
A, B.は特に「顧客のためにシームレスなパフォーマンスを確保したい」という点が説明されていないので選択肢から外れます。
C, D. の二択問題です。
Push では負荷が高い場合に、サブスクライバーが処理しきれなくなる恐れがあります。
トピックを順次処理することができるpullサブスクリプション（Pub/Subの利用方法としてはほぼこの使い方です）を使用することで、問題文の要件を果たすことができます。
正解は C となります。
Reference：
- pull サブスクリプション
  https://cloud.google.com/pubsub/docs/pull?hl=ja
</div></details>

## Q. 3-21
HTTP Cloud Functions を使用してデスクトップ ブラウザとモバイルアプリケーションクライアントの両方からのユーザーアクティビティを処理するアプリケーションがあります。
この関数は HTTP POST を使用したすべてのメトリック送信のエンドポイントとして機能します。
従来の制限により、関数は Web またはモバイルセッションでユーザーがリクエストしたドメインとは別のドメインにマップする必要があります。
Cloud Functions のドメインは https://fn.example.com です。
デスクトップおよびモバイルクライアントはドメイン https://www.example.com を使用します。
関数の HTTP レスポンスにヘッダーを追加してこれらのブラウザおよびモバイル セッションのみがメトリクスを Cloud Functions に送信できるようにする必要があります。
どのレスポンスヘッダーを追加するべきでしょうか？
1. Access-Control-Allow-Origin:*
2. Access-Control-Allow-Origin:https://*.example.com
3. Access-Control-Allow-Origin:https://fn.example.com
4. Access-Control-Allow-Origin:https://www.example.com
<details><div>
    答え：4
解説：
https://www.example.comからのリクエストのみを許可する事になるので、D が正解です。
</div></details>

## Q. 3-22
チームは Cloud Identity によって維持されるユーザーID を使用して実行されるアプリケーションを Google Cloud で開発しています。
アプリケーションの各ユーザーにはメッセージが発行される関連付けられた Cloud Pub/Sub トピックと、同じユーザーが発行されたメッセージを取得する Cloud Pub/Sub サブスクリプションがあります。
許可されたユーザーのみが、独自の特定の Cloud Pub/Sub トピックとサブスクリプションをパブリッシュ、サブスクライブできるようにする必要があります。
どうすればいいでしょうか？
1. リソースレベルでユーザーIDをpubsub.publisherロールとpubsub.subscriberロールにバインドします
2. プロジェクトレベルでユーザーIDをpubsub.publisherロールとpubsub.subscriberロールを付与します
3. ユーザーIDにpubsub.topics.create、pubsub.subscriptions.create 権限を含むカスタムロールを付与します
4. pubsub.publisher、pubsub.subscriber ロールを持つサービスアカウントとして実行するようにアプリケーションを構成します
<details><div>
    答え：1
解説：
特定のPub/Subリソースに対して特定のユーザーがpublish と subscribe 可能と考えるのがこの問題の最小権限であると考えられます。
Cの creator権限は権限が強すぎます。
DはユーザーIDへの付与の言及がないので「許可されたユーザーのみ」ではなくアプリケーションの全ユーザーに権限がついてしまいます。
Bは「特定の Cloud Pub/Sub トピックとサブスクリプション...」に反する事になります。
正解は A です。
その他の権限付与はそれよりも広範囲もしくは不必要に強い権限を付与しています。
</div></details>

## Q. 3-23
チームは PostgreSQL データベースと Cloud Run を使用して新しいアプリケーションを開発しています。
すべてのトラフィックが Google Cloud で非公開に保たれるようにする責任があります。
マネージド サービスを使用し、Google が推奨するベストプラクティスに従います。
どうすればいいでしょうか？
1. 同じプロジェクトでCloudSQLとCloudRunを有効にします。CloudSQLのプライベートIPアドレスを構成し、プライベートサービスアクセスを有効にします。サーバレスVPCアクセスコネクタを作成します。コネクタを使用してCloudSQLに接続するようにCloudRunを構成します
2. PostgreSQLをComputeEngine仮想マシンにインストールし、同じプロジェクトでCloudRunを有効にします。VMのプライベートIPアドレスを構成し、プライベートサービスアクセスを有効にします。サーバレスVPCアクセスコネクタを作成します。コネクタを使用してPostgreSQLをホストするVMに接続するようにCloudRunを構成します
3. CloudSQLとCloudRunを異なるプロジェクトで使用します。CloudSQLのプライベートIPアドレスを構成し、プライベートサービスアクセスを有効にします。サーバレスVPCアクセスコネクタを作成します。2つのプロジェクト間にVPN接続を設定し、コネクタを使用してCloudSQLに接続するようにCloudRunを構成します
4. ComputeEngineVMにPostgreSQLをインストールし、さまざまなプロジェクトでCloudRunを有効にします。VMのプライベートIPアドレスを構成し、プライベートサービスアクセスを有効にします。サーバレスVPCアクセスコネクタを作成します。2つのプロジェクト間にVPN接続を設定し、コネクタを使用してPostgreSQをホストするVMにアクセスするようにCloudRunを構成します
<details><div>
    答え：1
解説：
「マネージド サービスを使用」とある場合、そうでないものを真っ先に潰せます（マネージドサービスにどんなものがあるかは最低限勉強してほしいポイントです）。
この視点から、B, Dは除外され２択問題となります。
（MySQL, PostgreSQLを使う場合は Cloud SQLを使います。
ComputeEngineにインストールするB, Dのような使い方は、ほぼ間違いと考えて良いでしょう。）
Cは、最初の記述から「はぁ？なんで異なるプロジェクト？？」とハテナがいくつもついてしまいます。
...というのは経験来るものですが、通常１つのアプリケーションは１つのプロジェクトの中で開発すると覚えておいてください。
特に記述がない限りは開発しているアプリのリソースは１つのプロジェクト内にあると考えてください。
正解は A です。
</div></details>

## Q. 3-24
Compute Engine インスタンスで実行されるアプリケーションを管理します。
また、Compute Engine インスタンスで実行されているスタンドアロンの Docker コンテナで複数のバックエンド サービスを実行しています。
バックエンド サービスをサポートする Compute Engine インスタンスは複数のリージョンのマネージド インスタンス グループによってスケーリングされます。
呼び出し元のアプリケーションを疎結合にしたいと考えています。
リクエストで見つかった HTTP ヘッダーの値に基づいて選択された個別のサービス実装を呼び出すことができる必要があります。
バックエンド サービスを呼び出すにはどの Google Cloud 機能を使用するべきでしょうか？
1. TrafficDirector
2. ServiceDirectory
3. Anthosサービスメッシュ
4. 内部HTTPロードバランサ
<details><div>
    答え：1
解説：
B.は異なる環境(Google Cloud とオンプレミスなど)で同じサービスを展開するのに利用機能なので除外。
C.コンテナ間の通信をコントロールするものなので、本件のバックエンドサービスはComputeEngineインスタンスで実行されているという事なので除外。
D.は特定のリージョン(ロードバランサーと同じリージョン)に存在するバックエンドサービスのみで利用できるため、本件の要件に合いません。
従ってAが正解となります。
Reference (1)のドキュメントより、Trafific Directorはグローバルなサービスメッシュ、バックエンドサービスがCompute Engine 仮想マシン（VM）インスタンスで実行されているアプリケーションに対応しています。
Reference:
(1) Traffic Director | Google Cloud
https://cloud.google.com/traffic-director?hl=ja
https://cloud.google.com/traffic-director/docs/features?hl=ja
(2) Service Directory | ドキュメンテーション
https://cloud.google.com/service-directory/docs/overview
(3) Cloudd Load Balancing | ドキュメント | ガイド
https://cloud.google.com/load-balancing/docs/l7-internal?hl=ja
</div></details>

## Q. 3-25
Cloud SQL と通信する Compute Engine インスタンスにアプリケーションをデプロイしています。
Cloud SQL Proxy を使用してアプリケーションのインスタンスに関連付けられたサービス アカウントを使用し、アプリケーションがデータベースと通信できるようにします。
サービス アカウントに割り当てられたロールに最小限のアクセスを提供するという、Google が推奨するベストプラクティスに従います。
どうすればいいでしょうか？
1. プロジェクト編集者の役割を割り当てます
2. プロジェクト所有者の役割を割り当てます
3. CloudSQLクライアントの役割を割り当てます
4. CloudSQL編集者の役割を割り当てます
<details><div>
    答え：3
解説：
アプリケーションは、CloudSQLに読み書きできれば十分と考えられるので、最小権限の原則に従い、Cが正解となります。
A, Bは説明するまでもないでしょう。
Dは開発中に限られた開発メンバーへの権限付与としては必要でしょう。
しかし最終的なアプリケーションに付与する権限として強すぎます。
Reference：
(1) Cloud SQL Auth Proxy について
https://cloud.google.com/sql/docs/mysql/sql-proxy?hl=ja
(2) ロールと権限
https://cloud.google.com/sql/docs/mysql/roles-and-permissions?hl=ja
</div></details>

## Q. 3-26
従業員が社内でコミュニティ イベントを開催できるようにする社内アプリケーションを開発しています。
単一の Compute Engine インスタンスにアプリケーションをデプロイしました。
会社は Google Workspace (旧：G Suite) を使用しており、会社の従業員がどこからでもアプリケーションに対して認証できるようにする必要があります。
どうすればいいでしょうか？
1. インスタンスにパブリックIPアドレスを追加し、ファイアウォールルールを使用してインスタンスへのアクセスを制限します。会社のプロキシを唯一の送信元IPアドレスとして許可します
2. インスタンスの前にHTTPロードバランサを追加し、Identity-AwareProxyを設定します。会社のドメインがWebサイトにアクセスできるようにIAP設定を構成します
3. 会社のネットワークとGoogleCloudのインスタンスのVPCロケーションの間にVPNトンネルを設定します。必要なファイアウォールルールとルーティング情報をオンプレミスネットワークとGoogleCloudネットワークの両方に構成します
4. インスタンスにパブリックIPアドレスを追加し、インターネットからのトラフィックを許可します。ランダムハッシュを生成し、このハッシュを含み、インスタンスを指すサブドメインを作成します。このDNSアドレスを会社の従業員に配布します
<details><div>
    答え：2
解説：
A.は「会社のプロキシを唯一の送信元 IP アドレスとして許可」とあるので、一般的には社内からではないとアクセスできない環境と見なせます。
(社外からはVPNで社内ネットワークに接続する等の別条件が必要になります）
C.はオンプレミスとGoogle Cloudを接続するための方法の１つが記載されていますが、Compute Engine インスタンスにアプリケーションがあるという事ですので無関係な記載です。
D.はインターネットに全公開で、URLが分かればアクセスできてしまいますので、危険な公開方法です。
サブドメインをスクランブル化していますが、危険です。
ということで、消去法でもB.を正解とする事ができます。
B.に記載の内容を確認すると、設問の内容より、会社ではGoogle Workspaceを利用しているので、従業員は会社用のGoogleアカウントを持っており、IAPで認証することが可能です。
B.で正解です。
Reference：
(1) Identity-Aware Proxy
https://cloud.google.com/iap/docs/concepts-overview?hl=ja
</div></details>

## Q. 3-27
開発したアプリケーションを Cloud Run でホストしようとしています。
このアプリケーションはログレコードをテキストとしてローカル ファイルに書き込みます。
ログが Cloud Logging に書き込まれるようにし、さらに、保守する必要があるコードの量を最小化する必要があります。
どうすればよいですか。
1. コードにCloudLoggingライブラリをインポートして、そのログの書き込みに使用する
2. プログラミング言語のロガーを使用して、標準出力ストリームと標準エラーストリームにログを書き込む
3. ログファイルをwww.mycompany.com/logに公開する。ブラウザを使用してファイルを手動でダウンロードしてCloudStorageにアップロードする
4. cronを使用して、ログファイルを1日に1回CloudStorageにコピーするジョブをスケジュールする
<details><div>
    答え：2
解説：
A. 不正解です。
ライブラリを使用することは技術的には可能ですが、保守するコードが大量になります。
B. 正解です。
Cloud Run は stdout と stderr 経由で Cloud Logging に直接的に統合されます。
C. 不正解です。
このタスクは手動で実行することが必要になります。さらに、これは最も安全なアプローチではありません。
D. 不正解です。
データを Cloud Storage バケットにコピーすることはできますが、これを行ってもログデータを Cloud Logging 内に格納するという目標には役立ちません。
Reference:
(1) ログの記録と表示
https://cloud.google.com/run/docs/logging?hl=ja#container-logs
(2) Logging client libraries
https://cloud.google.com/logging/docs/reference/libraries
</div></details>

## Q. 3-28
顧客、注文、在庫のデータを Cloud Spanner 内のリレーショナルテーブルとして保存する eコマースアプリケーションを開発しています。
最近の負荷テスト中に Cloud Spanner のパフォーマンスが期待どおりに直線的にスケーリングしていないことがわかりました。
原因はどれでしょうか？
1. 32ビットの数値に64ビットの数値型を使用します
2. 任意精度の値に対するSTRINGデータ型を使用します
3. 単調に増加する主キーとしてのバージョン１UUIDを使用します
4. パラメータ化されたSQLクエリのSTARTS_WITHキーワードの代わりにLIKEを使用します
<details><div>
    答え：3
解説：
Cloud Spannerの利用で最も考慮すべき事の1つが主キーを単調に増加するような値を取らないようにすることです。
（自動的に行われている負荷分散（水平分割）が上手く機能せず、特定のノードにデータが集まってしまいます）
Cloud Spannerの利用上の注意点として最も有名な事ですので、Cloud Spannerを利用していたり、勉強されている方には、C.が原因であることは一撃で分かると思います。
A. B. D. は設問の内容にはどれも無関係です。
</div></details>

## Q. 3-29
会社ではソースコードを Cloud Source Repositories リポジトリに保存しています。
会社はソース コードがリポジトリにコミットされるたびにコードをビルドしてテストしたいと考えており、管理され、運用オーバーヘッドが最小限のソリューションを必要としています。
どのような方法を使用するべきでしょうか？
1. ソースコードのコミットごとに構成されたトリガーでCloudBuildを使用します
2. マーケットプレイス経由でデプロイされ、ソースコードのコミットを監視するように構成されたJenkinsを使用します
3. ソースコードのコミットを監視するように構成されたオープンソースの継続的インテグレーションツールでComputeEngine仮想マシンインスタンスを使用します
4. ソースコードコミットトリガーを使用し、AppEngineサービスをトリガーしてソースコードをビルドするPub/Subトピックにメッセージをプッシュします
<details><div>
    答え：1
解説：
Aは一般的な利用法です。
基本的な事は、Cloud Build のみで可能です。
特にその他のツールを利用する必要性は問題文からは読み取れませんので、A が正解です。
</div></details>

## Q. 3-30
Istio を使用して Google Kubernetes Engine (GKE) でマイクロサービスアプリケーションを管理します。
GKE クラスタに Istio AuthorizationPolicy、Kubernetes NetworkPolicy、mTLS を実装することでマイクロサービス間の通信チャネルを保護します。
特定の URL への 2つの Pod 間の HTTPリクエストが失敗し、他のURLへの他のリクエストは成功することがわかりました。
接続の問題の原因は何でしょうか？
1. KuberbetesNetworkPolicyリソースがPod間のHTTPトラフィックをブロックしています
2. HTTPリクエストを開始するPodが正しくないTCPポートを介してターゲットPodに接続しようとしています
3. クラスタの承認ポリシーがアプリケーションないの特定パスに対するHTTP要求をブロックしている
4. クラスタには許可モードで構成されたmTlsがありますがPodのサイドカープロキシは暗号化されていないトラフィックをプレーンテキストで送信しています　
<details><div>
    答え：3
解説：
A は不正解です。
Kubernetes NetworkPolicy のリソースでは、選択されたパスではなく、Pod のグループ間のHTTPトラフィックをブロックできます。
B は不正解です。
クライアントのPodがサーバーと通信するために使用するポートが誤っていると、PodのリクエストはすべてのURLパスで失敗します。
C は正解です。
Istio 認可ポリシーによって、Pod 間で特定の URLパスについて HTTP メソッドをブロックできます。
D は不正解です。
Istio を使用した mTLS 構成によってHTTPリクエストの失敗は発生しません。
  PERMISSIVE モード（デフォルト構成）では、サービスは平文と mTLS 暗号化トラフィックの両方を受け入れることができます。
Reference:
(1) HTTP Traffic
https://istio.io/latest/docs/tasks/security/authorization/authz-http/
(2) Network Policies
https://kubernetes.io/docs/concepts/services-networking/network-policies/
(3) Mutual TLS Migration
https://istio.io/latest/docs/tasks/security/authentication/mtls-migration/
</div></details>

## Q. 4-1
クラスタ内部での保持が必要なさまざまなマイクロサービスを使用するアプリケーションを開発しているとします。
特定の数のレプリカを使用して各マイクロサービスを構成できる必要があります。
また、マイクロサービスをどのくらいの数のレプリカにスケーリングするかにかかわらず、一貫した方法で、特定のマイクロサービスを別のマイクロサービスからアドレス指定できる必要もあります。
このソリューションは Google Kubernetes Engine で実装する予定です。どうすればよいですか。
1. 各マイクロサービスをDeploymentとしてデプロイする。Serviceを使用してクラスタでDeploymentを公開する。ServiceのDNS名を使用して、クラスタ内の他のマイクロサービスからDeploymentをアドレス指定する。
2. 各マイクロサービスをDeploymentとしてデプロイする。Ingressを使用してクラスタでDeploymentを公開する。IngressのDNS名を使用して、クラスタ内の他のマイクロサービスからDeploymentをアドレス指定する。
3. 各マイクロサービスをPodとしてデプロイする。Serviceを使用してクラスタでPodを公開する。ServiceのDNS名を使用して、クラスタ内の他のマイクロサービスからDeploymentをアドレス指定する。
4. 各マイクロサービスをPodとしてデプロイする。Ingressを使用してクラスタでPodを公開する。IngressのDNS名を使用して、クラスタ内の他のマイクロサービスからDeploymentをアドレス指定する。
<details><div>
    答え：１
説明
Reference:
(1)サービス
https://cloud.google.com/kubernetes-engine/docs/concepts/service?hl=ja
解説：
フィードバック
A は正解です。
Service はクラスタ内部に DNS エントリを持っており、他のマイクロサービスはそれを使用して、Service のターゲットとなっている Deployment の各 Pod をアドレス指定できます。
B は不正解です。
Ingress は外部または内部の HTTP(S) ロードバランサを使用して Service を公開し、直接 Deployment には適用されません。
C は不正解です。
Pod はマイクロサービスの単一インスタンスであり、Deployment が複数のレプリカで構成される場合があります。
D は不正解です。
B と C の両方の誤りが組み合わされています。
</div></details>

## Q. 4-2
自社用の e コマース プラットフォームをチームで開発しています。
ユーザーはウェブサイトにログインしてショッピング カートに商品を追加します。
アクティブでない状態が 30 分続くと、ユーザーは自動的にログアウトします。
ユーザーが再びログインした場合は、そのユーザーのショッピング カートを使用できるようにします。
Google が推奨するベスト プラクティスに沿ってユーザーのセッションとショッピング カートの情報を保存するには、どのようにしますか。
1. セッションとショッピングカートの情報をローカルメモリに保存し、GoogleHTTPロードバランサでCookieベースのセッションアフィニティを有効にする
2. CloudStorageのオブジェクトにショッピングカートの情報を保存し、オブジェクト名をセッションIDに保存する
3. セッションとショッピングカート情報をBigQueryに保存する
4. MemorystoreforRedisにセッション情報を保存し、ショッピングカートの情報をFirestoreに保存する
<details><div>
    答え：４
説明
Reference：
(1) Memorystore
https://cloud.google.com/memorystore?hl=ja
解説：
A は不正解です。
ローカルメモリはプロセスが終了するときに失われるため、カート情報が失われます。
B は不正解です。
セッション情報のために Cloud Storage バケットにアクセスすることは、低速でコストが高くなります。これは Google Cloud のベスト プラクティスではありません。
C は不正解です。
BigQueryではカートとセッションに対する頻繁な更新を処理できません。
D は正解です。
Memorystore はセッション情報を保存するソリューションとして標準的かつ高速であり、Firestore はショッピング カートのような小規模な構造化データに最適です。
ユーザーは必要に応じて新しいセッションのショッピング カートにマッピングされます。
</div></details>

## Q. 4-3
新しい Go アプリケーションを Cloud Run にデプロイする予定です。
ソースコードは Cloud Source Repositories に保存されます。
ソース コードのコミット時に実行されるフルマネージドの自動化された継続的デプロイパイプラインを構成する必要があります。
最も単純なデプロイソリューションを使用したい。
どうすればいいでしょうか？
1. ワークステーションでcronジョブを構成して作業ディレクトリでgcloud run deploy --source を定期的に実行します
2. Jenkins トリガーを構成してCloudSourceRepositories にコミットされたソースコードごとにコンテナのビルドとデプロイプロセスを実行します
3. ビルドパックを使用してCloudRunのソースリポジトリから新しいリビジョンの継続的なデプロイを構成する
4. CloudBuildを使用してCloudSourceRepositoryにコミットされたソースコードごとにコンテナのビルド及びデプロイプロセスを実行するように構成されたトリガーを使用します
<details><div>
    答え：４
説明
解説：
基本的には何かをトリガーにしてデプロイパイプラインを実行するのが正解なので、cron で定期実行で処理しているものは除外して良いでしょう。
Aは除外です。
後は現実的にはいろいろあるかもしれませんが、試験では複雑な設定はないので、Cloud Build のみで実現可能と思えるケースが殆どですので、別なツールを使っていたり絡めているものは正解ではないと見て良いでしょう。
本問の場合も、BのJenkins, Cの buildPackを使う必要性がある設定が記述されていないので、こんな事する必要なしと考えて良いでしょう。
ということで正解は D となります。
（殆どの問題は、Cloud Build だけで実行するものが正解です）
</div></details>

## Q. 4-4
認証サービスからの監査イベントの取り込みを再設計して、トラフィックの大幅な増加に対処できるようにする必要があります。
現在、監査サービスと認証サービスは同じ Compute Engine 仮想マシン（VM）で実行されています。
各サービスを Compute Engine VM インスタンスの独自のプールに分割し、Pub/Sub を使用して認証サービスから監査サービスにイベントを送信することを計画しています。
システムが確実に大量のメッセージを処理し、効率的にスケーリングできるようにするには、Pub/Sub トピックとサブスクリプションをどのように設計しますか。
1. １つのPub/Subトピックを作成する。１つのPullサブスクリプションを作成する
2. １つのPub/Subトピックを作成する。監視サービスインスタンスごとに１つのPullサブスクリプションを作成する
3. １つのPub/Subトピックを作成する。１つのpushサブスクリプションを作成する
4. 認証サービスごとに１つのPub/Subトピックを作成する。トピックごとに１つのpullサブスクリプションを作成する
5. 認証サービスごとに１つのPub/Subトピックを作成する。トピックごとに１つのpushサブスクリプションを作成する
<details><div>
    答え：１
説明
Reference:
(1) サブスクリプション タイプを選択する(Cloud Pub/Sub)
https://cloud.google.com/pubsub/docs/subscriber?hl=ja#push-subscription
解説：
A は正解です。
これは最も柔軟にスケーリングできる方法で、認証サービスと監査サービスを負荷に応じて独立してサイズ設定できます。
B は不正解です。
サブスクリプションごとにコピーが作成され、メッセージが重複します。
C は不正解です。
システムをスケーリングできるものの、push サブスクリプションは、大量のメッセージの処理には適していません。
D は不正解です。
システムをスケーリングできるものの、それぞれの監査サービスがすべてのサブスクリプションをリッスンすることになります。
E は不正解です。
システムをスケーリングできるものの、それぞれの監査サービスがすべてのサブスクリプションをリッスンすることが必要になります。
さらに、push サブスクリプションは、大量のメッセージの処理には適していません。
</div></details>

## Q. 4-5
Cloud Run と Cloud Firestore in Datastore モードで実行される新しい小売システムに取り組んでいるリードデベロッパーです。
Web UI の要件はユーザーがシステムにアクセスしたときにシステムが利用可能な製品のリストを表示し、ユーザーがすべての製品を参照できるようにすることです。
Cloud Firestore に保存されているすべての利用可能な製品のリストを返すことにより、実用最小限の製品 (MVP) フェーズでこの要件を実装しました。
稼働開始から数か月後、Cloud Run インスタンスが HTTP 500: コンテナ インスタンスがビジー時間中にメモリ制限を超えているというエラーで終了していることに気付きました。
このエラーは Datastore エンティティの読み取り数の急増と同時に発生します。
Cloud Run がクラッシュするのを防ぎ、Datastore エンティティの読み取り回数を減らす必要があります。
システムのパフォーマンスを最適化するソリューションを使用したいと考えています。
どうすればいいでしょうか？
1. 整数オフセットを使用して製品リストを返すクエリを変更します
2. 制限を使用して製品リストを返すクエリを変更します
3. Cloudrunの攻勢を変更してメモリの上限を引き上げます
4. カーソルを使用して製品リストを返すクエリを変更します
<details><div>
    答え：４
説明
Reference:
(1)ベスト プラクティス(Datastore)
https://cloud.google.com/datastore/docs/best-practices?hl=ja#queries
解説：
負荷が高くなりリクエストはさばけるものの応答データを処理するメモリーが足りなくなってしまうので、製品リストの一部をどう返すかという問題になります。
Cは有効化もしれませんが「システムのパフォーマンスを最適化するソリューション」に反していいるでしょう（コストにもかかわりますので、エンジニアとしてそこに簡単に逃げたくはないですね）。
Bは具体性に欠けます。
Referenceに示した資料を見ると、Aを行ってもアプリケーションが結果を途中から受けないというだけで、全体のデータは受け取っている旨の記述がありますので、Bでいう制限も同様の可能性があります。
Referenceを見ると、カーソルを使うとよさそうです。
正解は D となります。
</div></details>

## Q. 4-6
あなたはアプリケーションのパフォーマンスを分析しています。
クラスタ内にある Cloud Bigtable の特定のテーブルが他のテーブルより使用率が高く、エンドユーザーに対してアプリケーションのパフォーマンスの一貫性がないことが確認されました。
一部のテーブルでは似た名前の行キーのデータが多くなっており、それらのテーブルは使用率が高く、他のテーブルは使用率が低いことがわかりました。
また、ユーザーの郵便番号が行キーの最初の要素になっており、その郵便番号から作成されたプロファイルによるアプリケーション使用率が高いこともわかりました。
行キーの生成方法を可読形式に変更して、Cloud Bigtable の要求がクラスタ内で均等に分散されるようにするには、どうすればよいですか。
1. シーケンシャルに生成される整数値を使用する
2. 可読形式の複数の属性を連結して使用する
3. 行の内容のMD5八種のサブセットを使用する
4. ミリ秒単位であらわされたUNIXエポック形式のタイムスタンプを使用する
<details><div>
    答え：２
説明
Reference:
(1) スキーマ設計のベスト プラクティス(Cloud Bigtable)
https://cloud.google.com/bigtable/docs/schema-design?hl=ja#types_of_row_keys
(2) 時系列データ用のスキーマ設計(Cloud Bigtable)
https://cloud.google.com/bigtable/docs/schema-design-time-series?hl=ja#ensure_that_your_row_key_avoids_hotspotting
解説：
A は不正解です。
元の値の分散状況によっては、シーケンシャルに生成される整数値によってホットスポット化をもたらす可能性があります。
B は正解です。
十分な数の属性を区切って使用することで、十分な分散を実現できます。
C は不正解です。
現在は、この方法は推奨されていません。この方法では、問題のトラブルシューティングが困難になります。
D は不正解です。
タイムスタンプは行キーの候補として適切ではありません。
複数の更新が短い時間に連続して発生し、ミリ秒レベルで同じ時刻に実行されると、誤って ID の競合が発生します。
Cloud Spannerも同じ原因でパフォーマンス低下が発生しますので覚えておいて下さい。
（Cloud SpannerはCloud Bigtableのベース技術が使われています）
</div></details>

## Q. 4-7
アプリケーションは Google Kubernetes Engine クラスタでコンテナとして実行されています。
安全なアプローチを使用してアプリケーションにシークレットを追加する必要があります。
どうすればいいでしょうか？
1. K8Sシークレットを作成し、そのシークレットを環境変数としてコンテナに渡します
2. CloudKeyManagementServiceキーを使用してクラスタでアプリケーションレイヤーのシークレット暗号化を有効にします
3. 認証情報をCloudKMSに保存します。CloudKMSから認証情報を読み取るためのGoogleサービスアカウントを作成します。GSAを.jsonファイルとしてエクスポートし、CloudKMSから認証情報を読み取ることができるボリュームとして.jsonファイルをコンテナに渡します
4. 認証情報をSecretManagerに保存します。SecretManagerから認証情報を読み取るためのGSAを作成します。コンテナを実行するためのKSAを作成します。WorkloadIdentityを使用してKSAがGSAとして機能するように構成します
<details><div>
    答え：４
説明
Reference:
(1) Secret Manager のベスト プラクティス
https://cloud.google.com/secret-manager/docs/best-practices?hl=ja
(2) Good practices for Kubernetes Secrets
https://kubernetes.io/docs/concepts/security/secrets-good-practices/
解説：
Workload Identityを使う方法が正解です。
正解は D となります。
</div></details>

## Q. 4-8
チームは給与計算アプリケーションをサポートする対話型音声応答 (IVR) システムのビジネスロジックを実装するバックエンドアプリケーションを作成しています。
IVR システムには次の技術的特徴があります。
各顧客の電話は固有の IVR セッションに関連付けられています。
IVR システムはセッションごとにバックエンドへの個別の永続的な gRPC 接続を作成します。
接続が中断された場合はIVR システムは新しい接続を確立するため、その通話にわずかな遅延が発生します。
バックエンド アプリケーションのデプロイに使用するコンピューティング環境を決定する必要があります。
現在の通話データを使用して次のことを判断します。
通話時間は 1 ～ 30 分
電話は通常、営業時間内
特定の既知の日付 (例: 給料日) の前後、または大規模な給与計算の変更が発生したときに電話の急増がある
コスト、労力、運用上のオーバーヘッドを最小限に抑えたいと考えています。
バックエンド アプリケーションをどこにデプロイするべきでしょうか？
1. ComputeEngine
2. StandardモードのK8Sクラスタ
3. CloudFunctions
4. CloudRun
<details><div>
    答え：４
説明
Reference:
(1) Cloud Functions と Cloud Run: それぞれの使いどころ
https://cloud.google.com/blog/ja/products/serverless/cloud-run-vs-cloud-functions-for-serverless
解説：
問題文から、ゼロスケール可能なマネージドサービスを使うのが適切ということで、C, D のどちらかが正解までは簡単にたどり着けるでしょう。
イベント駆動型であれば、Cloud Functions が適していますが、直接アクセスする対話型のサービスであることから、D のCloud Runを使用するのが最も適切と判断します。
正解は D となります。
</div></details>

## Q. 4-9
最近、新しいアプリケーションを開発しました。
Dockerfile なしで Cloud Run にアプリケーションをデプロイしたいと考えています。
組織ではすべてのコンテナ イメージを一元管理されたコンテナリポジトリにプッシュする必要があります。
Google Cloud サービスを使用してコンテナをどのように構築しますか？ (回答は 2 つ)
1. ソースコードをArtifactregistoryにプッシュします
2. CloudBuildジョブを送信してイメージをプッシュします
3. packCLIでpackbuildコマンドを使用します
4. gcloud run deploy CLI コマンドに--sourceフラグを含めます
5. gcloud run deploy CLI コマンドに--platform=kubernetesフラグを含めます
<details><div>
    答え：３，４
説明
Reference:
(1) ソースコードからのデプロイ
https://cloud.google.com/run/docs/deploying-source-code?hl=ja
解説：
Reference (1)をご参照下さい。
Aは不正解です。
Artifact Registryはビルド後のコンテナイメージやパッケージを管理します。
ここで示されている方法でもコンテナイメージの保存に使われます。
ソースコードの管理は行いません（Cloud Source Repositoryと混同しないようご注意下さい）。
Bは不正解です。
Dockerfileなしでイメージをビルドする具体的なが示されていません。
Cは正解です。
pack build コマンドを使用する事で、Dockerfile無しにソースコードからイメージをビルドする事が出来ます。
Dは正解です。
gcloud run deploy と --source フラグを使用して、新しいサービスとリビジョンをソースコードから直接 Cloud Run にデプロイできます。
Eは不正解です。
Cloud Runへのデプロイなので、このフラグは使いません。
正解は C, D となります。
</div></details>

## Q. 4-10
Google Kubernetes Engine (GKE) で Deployment を構成する必要があります。
コンテナがデータベースに接続できることを確認するチェックを含めたいとします。
Pod が接続に失敗した場合はコンテナでスクリプトを実行して正常なシャットダウンを完了する必要があります。
デプロイをどのように構成しますか？
1. 2つのジョブを作成します。1つのコンテナがデータベースに接続できるかどうかを確認するジョブでもう1つはPodが失敗した場合にシャットダウンスクリプトを実行するジョブです
2. コンテナがデータベースに接続できない場合に失敗するコンテナのlivenessProbeを使用してDeploymentを作成します。コンテナが失敗した場合にシャットダウンスクリプトを事項するPrestopライフサイクルハンドラーを構成します
3. サービスの可用性をチェックするPostStartライフサイクルハンドラを使用してDeploymentを作成します。コンテナが失敗した場合にシャットダウンスクリプトを実行するPreStopライフサイクルハンドラーを構成します
4. サービスの可用性をチェックするinitContainerを使用してDeploymentを作成します。Podに障害が発生した場合にシャットダウンスクリプトを実行するPreStopライフサイクルハンドラーを構成します
<details><div>
    答え：２
説明
Reference:
(1) コンテナライフサイクルフック
https://kubernetes.io/docs/concepts/containers/container-lifecycle-hooks/#hook-details
(2) コンテナの初期化
https://kubernetes.io/docs/concepts/workloads/pods/init-containers/
解説：
AはそもそもDeploymentに関する記述がないので却下でしょう。
DB接続に失敗し処理が先に進まず、livenessProbeに引っ掛かると、Podの再起動がかかりますが、その前にPrestopに指定した処理を呼び出すことができますので、ここでシャットダウンが可能です。
Bは正解ですね。
念のため後続の選択肢も見てみましょう。
PostStartはPodのコンテナが作成された直後に実行されますが、この時点ではPodがDBの接続に成功するか失敗するかは分かりませんので何も出来ません。
PreStopを呼び出すトリガーがないのでCは間違いです。
initContainerはアプリとは別のコンテナでinitContainerの実行が完了してもアプリケーションコンテナがデータベースに接続できるかは保障されないでしょう。
やはり正解は B となります。
</div></details>

## Q. 4-11
急速に成長している金融テクノロジーの新興企業で働いています。
Go で記述され、シンガポール リージョン (asia-southeast1) の Cloud Run でホストされている支払い処理アプリケーションを管理します。
支払い処理アプリケーションは、同じくシンガポール リージョンにある Cloud Storage バケットに格納されたデータを処理します。
このスタートアップはアジア太平洋地域へのさらなる拡大を計画しています。
今後 6 か月以内にジャカルタ、香港、台湾にペイメント ゲートウェイをデプロイする予定です。
各場所にはトランザクションが行われた国に顧客データが存在する必要があるデータ所在地要件があります。
これらのデプロイ コストを最小限に抑える必要があります。
どうすればいいでしょうか？
1. 各リージョンにCloudStorageバケットを作成し、各リージョンに決済アプリケーションのCloudRunサービスを作成します
2. 各リージョンにCloudStorageバケットを作成し、シンガポールリージョンに支払処理アプリケーションの３つのCloudRunサービスを作成します
3. アジアマルチリージョンに３つのCloudStorageバケットを作成し、シンガポールリージョンに支払アプリケーションの３つのCloudRunサービスを作成します
4. アジアマルチリージョンに３つのCloudStorageバケットを作成し、シンガポールリージョンに支払アプリケーションの３つのCloudRunサービスを作成します
<details><div>
    答え：
説明
解説：１
「ジャカルタ、香港、台湾にペイメント ゲートウェイをデプロイする」との事から、これらの各リージョンに、決済アプリケーションの Cloud Runがデプロイされます。
そして、「トランザクションが行われた国に顧客データが存在する必要がある」という条件から、やはり各リージョンに Cloud Storage バケットを作成することになります。
従って正解は A です。
B, C, Dはいずれも決済トランザクション処理と顧客データの所在地が異なる結果となります(よく読んでみて下さい)。
</div></details>

## Q. 4-12
アプリケーションに単体テストを追加する予定です。
パブリッシュされた Cloud Pub/Sub メッセージがサブスクライバーによって順番に処理されることをアサートできる必要があります。
単体テストの費用対効果と信頼性を高める必要があります。
どうすればいいでしょうか？
1. モッキングフレームワークを実装します
2. 各テスターのトピックとサブスクリプションを作成します
3. テスターによるフィルターをサブスクリプションに追加します
4. Cloud Pub/Subエミュレータを使用します
<details><div>
    答え：４
説明
Reference：
(1) エミュレータを使用したローカルでのアプリのテスト | Cloud Pub/Sub ドキュメント | Google Cloud
  https://cloud.google.com/pubsub/docs/emulator?hl=ja
解説：
実際のコンテンツの開発経験があると実感できると思いますが、主にプログラムは自分のPCで開発し、それを自分のPCで動かして動作確認する方法が効率がよく、ほとんどの場合このような環境を構築して開発していると思います。
基本的にはローカルで動作確認ができる環境が効率よくGoogleもそれを推奨していると感じます。
ということで本問題は D が正解です。
手元のアプリ（ローカルで動作）が Pub/Subにパブリッシュしてそれが受信されている事、サブスクライバーが処理することを手元で確認できれば最高です。
「単体テストの費用対効果と信頼性を高める」にマッチしていると考えられます。
</div></details>

## Q. 4-13
Google Kubernetes Engine (GKE) にデプロイされたアプリケーションがあります。
Google Cloud マネージドサービスに対して承認済みのリクエストを行うにはアプリケーションを更新する必要があります。
これを 1回限りの設定にしたいと考えており、セキュリティキーを自動ローテーションして暗号化されたストレージに保存するというセキュリティのベストプラクティスに従う必要があります。
Google Cloud サービスへの適切なアクセス権を持つサービスアカウントをすでに作成しています。
何をするべきでしょうか？
1. WorkloadIdentityを使用し、GoogleサービスアカウントをGKEPPodに割り当てます
2. Googleサービスアカウントをエクスポートし、それをKubernetesSecretとしてPodと共有します
3. Googleサービスアカウントをエクスポートし、アプリケーションのソースコードに埋め込む
4. Googleサービスアカウントをエクスポートし、HashicorpValutにアップロードして、アプリケーション動的サービスアカウントを生成します
<details><div>
    答え：１
説明
Reference：
(1) Workload Identity を使用する
  https://cloud.google.com/kubernetes-engine/docs/how-to/workload-identity?hl=ja
(2) サービスアカウントの使用に関するベストプラクティス
https://cloud.google.com/iam/docs/best-practices-service-accounts?hl=ja#use-workload-identity
解説：
GoogleではWorkload Identityの利用をベストプラクティスとしていますので、Workload Identityが出てきたらそれが正解です。
正解は A となります。
</div></details>

## Q. 4-14
複数のマイクロサービスで構成されるアプリケーションを設計しています。
各マイクロサービスには独自の RESTful API があり、個別の Kubernetes サービスとしてデプロイされます。
APIに変更があった場合にこれらの APIのコンシューマーが影響を受けないようにし、APIの新しいバージョンがリリースされたときにサードパーティシステムが中断されないようにする必要があります。
Googleが推奨するベストプラクティスに従って、アプリケーションへの接続をどのように構成しますか？
1. APIのURLを使用するIngressを使用し、リクエストを適切なバックエンドにルーティングします
2. ServiceDiscoveryシステムを活用し、リクエストで指定されたバックエンドに接続します
3. 複数のクラスタを使用し、DNSエントリを使用してリクエストを別のバージョン管理されたバックエンドにルーティングします
4. 複数のバージョンを同じサービスに統合し、POSTリクエストでAPIバージョンを指定する
<details><div>
    答え：１
説明
解説：
本問題ではRESTful APIが変更になると考えると、AのIngressの設定で、適切なバックエンドへのルーティングが可能です。
BのService Discoveryは主にKubernetes内部の通信の話で、Ingressで外部URLと内部URLのマッピングが出来ていれば特に意識するものではありません。
特に複数クラスタを使う必要性がありませんので C は除外。
ソース管理が複雑になったり、そもそももともとのAPIにGETリクエストがある場合はどうするのか等 D は記載内容が曖昧なので除外です。
正解は A となります。
</div></details>

## Q. 4-15
会社には Google Cloud に保存されているすべてのデータを顧客管理の暗号鍵で暗号化することを要求する新しいセキュリティイニシアチブがあります。
Cloud Key Management Service (KMS) を使用して鍵へのアクセスを構成する予定です。
「職務分離」の原則とGoogle が推奨するベスト プラクティスに従う必要があります。
どうすればいいでしょうか？ (回答は 2 つ)
1. 独自のプロジェクトでCloudKMSをプロビジョニングします
2. CLoudKMSプロジェクトに所有者を割り当てないでください
3. キーが使用されているプロジェクトでCLoudKMSをプロビジョニングします
4. CloudKMSのキーが使用されているプロジェクトのオーナーにroles/cloudkms.adminロールを付与します
5. CloudKMSのカギが使用されているプロジェクトの所有者とは異なるユーザーにCloudKMSプロジェクトの所有者の役割を付与します
<details><div>
    答え：１，２
説明
Reference:
(1) 職掌分散
https://cloud.google.com/kms/docs/separation-of-duties?hl=ja
(2) Cloud KMSを徹底解説
https://blog.g-gen.co.jp/entry/cloud-kms-explained
解説：
Referenceに挙げた資料から、A, Bを正解とします。
D, E は付与する権限が大きすぎるので良くないでしょう。
独自プロジェクトで鍵管理を行う方がより厳格であることから、CよりもAの方がセキュリティーが高い対応であると考えます。
</div></details>

## Q. 4-16
Compute Engine インスタンスが通常の実行レベルで起動するのを妨げる低レベルのLinux 構成ファイルに入力ミスがあります。
今日、Compute Engine インスタンスを作成したばかりでファイルの調整以外のメンテナンスは行っていません。
このエラーをどのように修正する必要がありますか？
1. scpを使用してファイルをダウンロードし、ファイルを変更してから変更したバージョンをアップロードします
2. SSH経由でComputeEngineインスタンスを構成してログインし、ファイルを変更します
3. シリアルポート経由でComputeEngineインスタンスを構成してログインし、ファイルを変更します
4. リモートデスクトップクライアントを使用してComputeEngineインスタンスを構成してログインし、ファイルを変更します
<details><div>
    答え：３
説明
Reference:
(1) シリアルコンソールを使用したトラブルシューティング
https://cloud.google.com/compute/docs/troubleshooting/troubleshooting-using-serial-console?hl=ja
解説：
Compute Engineはまだ起動できていないと考えると、C 以外は不可能です。
特にGoogle Cloud に限らず、シリアルポート経由でのコンピューターへの接続は大昔から行われていた常套手段です。
</div></details>

## Q. 4-17
会社ではゾーン障害によるGoogle Kubernetes Engine (GKE) API停止が発生したばかりです。
将来ゾーンで障害が発生した場合にユーザーへのサービスの中断を最小限に抑え、可用性の高い GKE アーキテクチャをデプロイしたいと考えています。
どうすればいいでしょうか？
1. ゾーンクラスタをデプロイします
2. リージョンクラスタをデプロイします
3. マルチゾーンクラスタをデプロイします
4. GKEオンプレミスクラスタをデプロイします
<details><div>
    答え：２
説明
Reference:
(1) Google Kubernetes Engine（GKE）
https://cloud.google.com/kubernetes-engine/docs/concepts/types-of-clusters?hl=ja
解説：
Referenceに記載の資料を参照ください。
Aはシングルゾーンの為、可用性が低いです。
Dもシングルポイントと考えられるため可用性が低いです（そこが故障したらサービス継続不可能）。
Cは複数のゾーンにノードが存在しますが、コントロールプレーンが１つのゾーンにしかないためそこに障害が発生した場合、完全なサービス継続が難しくなります。
リージョンクラスタは、複数のゾーンにノードがあるだけでなく、各ゾーンにコントロールプレーンが存在するため、可用性に優れています。
したがって正解は B です。
</div></details>

## Q. 4-18
Google Kubernetes Engine (GKE) で実行されるマイクロサービス ベースのアプリケーションを開発しています。
一部のサービスはさまざまな Google Cloud API にアクセスする必要があります。
Google が推奨するベスト プラクティスに従って、クラスタでこれらのサービスの認証をどのように設定しますか？ (回答は 2 つ)
1. GKEノードにアタッチされたサービスアカウントを使用します
2. gcloudコマンドラインツールを使用し、クラスタでWorkloadIdentityを有効にします
3. シークレット管理サービスからGoogleサービスアカウントキーにアクセスします
4. Googleサービスアカウントキーを中央シークレット管理サービスに保存します
5. glcoud を使用し、roles/iam.eorkloadidentity を使用して、K8SサービスアカウントとGoogleサービスアカウントをバインドします
<details><div>
    答え：２，５
説明
Reference:
(1) Workload Identity を使用する
https://cloud.google.com/kubernetes-engine/docs/how-to/workload-identity?hl=ja
解説：
Google Cloudのリソースアクセスで最も推奨される方法が Workload Identity を使った認証です。
シークレットキーなどを保存して使う方法は可能な限り選択すべきではありません。
与えられた選択肢の中からは、Workload Identityの使用に関係する、B, E. が正解となります。
</div></details>

## Q. 4-19
バージョン管理システム、Cloud Build、Container Registry で構成される CI/CD パイプラインを構築しています。
新しいタグがリポジトリにプッシュされるたびに Cloud Build ジョブがトリガーされます。
このジョブは、新しいコードで単体テストを実行し、新しい Docker コンテナ イメージをビルドして、それを Container Registry にプッシュします。
パイプラインの最後のステップでは、新しいコンテナを本番環境の Google Kubernetes Engine (GKE) クラスタにデプロイする必要があります。
次の要件を満たすツールとデプロイ戦略を選択する必要があります。
ゼロダウンタイムが発生します
テストは完全に自動化されています
ユーザーにロールアウトする前にテストできる
必要に応じてすばやくロールバックできます
どうすればいいでしょうか？
1. 新しいコードのA/Bテストとして構成されたSpinnakerパイプラインをトリガーし、成功した場合はコンテナを本番環境にデプロイします
2. 新しいコードのカナリアテストとして構成されたSpinnakerパイプラインをトリガー氏、成功した場合はコンテナを本番環境にデプロイします
3. K8S CLI ツールを使用して別のClooudBuildジョブをトリガーし、カナリアテストを実行できるGKEクラスタに新しいコンテナをデプロイします
4. K8S CLI ツールを使用する別のClooudBuildジョブをトリガーし、シャドーテストを実行できるGKEクラスタに新しいコンテナをデプロイします
<details><div>
    答え：４
説明
Reference：
(1) アプリケーションのデプロイとテストの戦略 #シャドーテスト パターン
  https://cloud.google.com/architecture/application-deployment-and-testing-strategies?hl=ja#shadow_test_pattern
解説：
カナリアテストでは一部が本番環境で新バージョンに置き換わっているため、「ユーザーにロールアウトする前にテスト」に適していないでしょう。
「すばやくロールバック」にも合っていないとみなせるかもしれません。
従ってB, C. は選択肢から外れます。
本門はデプロイ戦略を主題としており、旧バージョンと新バージョンの効果やパフォーマンスの比較を行っているわけではないので、Aもテーマから外れます。
（本質的ではないのですが、わざわざSpinnakerを使っている点も正解ではないパターンです）
Reference (1)の資料を参照すると、シャドーテストが本問題に最もマッチした、テスト込みのデプロイ戦略であることが分かります。
正解は D となります。
</div></details>

## Q. 4-20
Google ドライブの API にアクセスし、ユーザーからファイルを Google ドライブに保存する許可を取得する必要がある JavaScript Web アプリケーションを開発しました。
アプリケーションの承認アプローチを選択する必要があります。
どうすればいいでしょうか？
1. APIキーを作成します
2. SAMLトークンを作成します
3. サービスアカウントを作成します
4. OAuthクライアントIDを作成します
<details><div>
    答え：４
説明
Reference：
(1) API 固有の承認および認証情報
https://developers.google.com/drive/api/guides/api-specific-auth?hl=ja
解説：
各ユーザーの認証が必要なので、D が正解となります。
</div></details>

## Q. 4-21
Webアプリケーションは企業のイントラネットにデプロイされます。
Webアプリケーションを Google Cloud に移行する必要があります。
Webアプリケーションは会社の従業員のみが使用でき、出張中に従業員がアクセスできる必要があります。
アプリケーションの変更を最小限に抑えながら Webアプリケーションのセキュリティとアクセシビリティを確保する必要があります。
どうすればいいでしょうか？
1. アプリケーションへのHTTPリクエストごとに認証資格情報を確認するようにアプリケーションを構成します。
2. Identity-AwareProxyを構成し、従業員がパブリックIPアドレスを介してアプリケーションにアクセスできるようにします
3. ユーザーに企業アカウントへのログインを要求するComputeEngineインスタンスを構成します。WebアプリケーションのDNSを変更してプロキシを通じてComputeEngineインスタンスを指すようにします。認証後、ComputeEngineインスタンスはWebアプリケーションとの間でリクエストを転送します。
4. ユーザーに企業アカウントへのログインを要求するComputeEngineインスタンスを構成します。WebアプリケーションのDNSを変更してプロキシを通じてComputeEngineインスタンスを指すようにします。認証後、ComputeEngineインスタンスはWebアプリケーションを放素とするパブリックIPアドレスにHTTPリダイレクトを発行します。
<details><div>
    答え：３
説明
A. このオプションでは、HTTP(S)リクエストごとに認証チェックを実装するために、アプリケーションに大幅な変更が必要になる可能性が高く、アプリケーションの変更を最小限に抑えるという要件に反する。
B. IAP（Identity-Aware Proxy）は、Google Cloud Platformの機能であり、IDおよびコンテキストベースのアクセス制御を使用してリソースへのアクセスを保護することができます。IAPを使用すると、リソース（ウェブ・アプリケーションなど）へのアクセスを、認証され許可されたユーザーまたはサービス・アカウントのみに制限することができます。
しかし、このシナリオでは、ウェブ・アプリケーションは企業のイントラネット上でホストされているため、パブリックIPアドレスを持たず、インターネットからアクセスすることはできません。また、IAP を使用して、イントラネットでホストされているアプリケーションへのアクセスを、その IP アドレスによって制限することはできません。
D. これらのオプションには、プロキシとして機能するCompute Engineインスタンスを設定し、企業アカウントを通じてユーザーを認証することが含まれます。また、WebアプリケーションをホストするパブリックIPアドレスへのHTTPリダイレクトが含まれるため、従業員のみにアクセスを制限する必要性に合致しない可能性があります。
正解
C. このアプローチでは、Google Cloudのインフラストラクチャを利用して、Webアプリケーションへのアクセスを許可する前に、企業のイントラネットを通じてユーザーを認証することができます。プロキシとして動作するCompute Engineインスタンスを設定し、WebアプリケーションのDNSをこのプロキシを指すように変更することで、Webアプリケーションへのアクセスは、企業イントラネットで認証された従業員のみに制限されます。さらに、この方法では、従業員がインターネットにアクセスできる環境であれば、出張中でもWebアプリケーションにアクセスすることができます。
誤り説明
Reference:
(1) ID 認識型プロキシを使用した Web サイトへのアクセスの制御
https://cloud.google.com/blog/topics/developers-practitioners/control-access-your-web-sites-identity-aware-proxy
解説：
Aの方法は利便性が悪い上にアプリケーションに認証処理を実装しているので、「アプリケーションの変更を最小限に抑えながら」とう点に反します。
設問的には「最小限に抑え」とか「可能な限り」等の表現が使われている場合がありますが、この場合実際には最小限とか可能な限りではなく、できるだけ避けたい要素が完全に排除されているものが正解です。
Aは一発アウトです。
C, Dは昔ながら踏み台サーバー経由的な手法になっているので、これも正解の匂いがしません（古いやり方は正解の可能性が低いです。モダナイゼーションされたものが正解です）。
B.の方法に問題は無い為、B が正解です。
</div></details>

## Q. 4-22
チームは Google Kubernetes Engine で実行されるサービスを開発しています。
チームのコードは Cloud Source Repositories に保存されています。
コードを本番環境にデプロイする前に、コードのバグをすばやく特定する必要があります。
自動化に推進して開発者のフィードバックを改善し、プロセスをできるだけ効率的にしたいと考えています。
どうすればいいでしょうか？
1. Spinnaker を使用してGitタグに基づくコードからコンテナイメージの構成を自動化します
2. CloudBuildを使用してGitタグに基づくコードからコンテナイメージの構成を自動化します
3. Spinnakerを使用して本番環境へのコンテナイメージのデプロイを自動化します
4. CloudBuildを使用してフォークされたバージョンに基づくコードからコンテナイメージのビルドを自動化します
<details><div>
    答え：２
説明
Reference：
(1) Kubernetes Source to Prod(Spinnaker)
https://spinnaker.io/docs/guides/tutorials/codelabs/kubernetes-v2-source-to-prod/
解説：
基本的にはGoogleCloudが提供する機能のみでの開発が正解の可能性が高いです。
A, Cは外して良いと思います。
Bの方法が一般的に利用されている方法ですので、この問題の正解は B となります。
仕事（講師の経験）では、Gitのタグの生成をトリガーにデプロイを管理するのは極一般的ですが、学生などの場合はどうなのでしょう。
企業での開発経験があれば、B が身近な方法としてリアルに正解である事が見通せると考えていますが、経験がない場合は、
1. GoogleCloud内の機能を優先する、
2.それらしく難しい事を言っている（稀に本当にそういうプロセスが必要な場合もありますが、多くは単純な方が正解）選択肢は怪しいと
考えると正解にたどり着ける確率が高まると思います。
SpinnakerもJenkinsと並んで人気のツールで、実際利用している場合も多い（現実の制作では色々と付加的なステップが必要な事も多いと思います）すが、殆どの設問は基本的には Cloud Build でなんでもできると立場を取っています。
難しい特別なケースを一般的な設問としては設定するのはリスクが高い（解決策も多岐に渡ってしまう）と感じられるため、ごく単純なモデルケースが舞台となるため、Cloud Buildで十分なシチュエーションとなるとも考えられます。
本問題の場合、A も完全な間違いとは言えないですが、Cloud Build で十分であり Spinnakerを使う必要がないと見ます。
</div></details>

## Q. 4-23
NFS 共有に構成を格納するレガシー アプリケーションをコンテナ化しました。
このアプリケーションを Google Kubernetes Engine (GKE) にデプロイする必要があり、構成が取得されるまでアプリケーションがトラフィックを処理しないようにする必要があります。
どうすればいいでしょうか？
1. gsutilユーティリティを使用して起動時にDockerコンテナ内からファイルをコピーし、ENTRYPOINTスクリプトを使用してサービスを開始します
2. GKEクラスタにPersistentVolumeClaimを作成します。ボリュームから構成ファイルにアクセスし、ENTRYPOINTスクリプトを使用してサービスを開始します
3. DockerfileでCOPYステートメントを使用して構成をコンテナイメージにロードします。構成が使用可能で敦子とを確認し、ENTRYPOINTスクリプトを使用してサービスを開始します
4. 起動スクリプトをGKEインスタンスグループに追加してノードの起動時にNFS共有をマウントします。構成ファイルをコンテナにコピーし、ENTRYPOINTスクリプトを使用してサービスを開始します
<details><div>
    答え：２
説明
解説：
この案件にCloudStorageを持ち出すのは「ないわー」という感じですね。
Aは速攻除外です。
DokerfileのCOPYはローカルファイルをDockerイメージにコピーするコマンドなので、Cも除外。
Dのノードの起動にNFS共有をマウントするという点が大袈裟で、各ノードがNFS共有をマウントすることになる点も非効率であると思われます。
PersistentVolumeClaimはGKEクラスタで一般的に利用可能ですので、この問題は B が適切と判断できるでしょう。
</div></details>

## Q. 4-24
CI/CD チームと協力してチームが導入した新機能のトラブルシューティングを行う開発者です。
CI/CD チームは HashiCorp Packer を使用して開発ブランチから新しい Compute Engine イメージを作成しました。
イメージは正常にビルドされましたが起動していません。
CI/CD チームで問題を調査する必要があります。
どうすればいいでしょうか？
1. 新しい機能ブランチを作成し、ビルドチームにイメージの再構築を依頼します
2. デプロイされた仮想マシンをシャットダウンし、ディスクをエクスポートしてからローカルにマウントしてブートログにアクセスします
3. Packerをローカルにインストールし、ComputeEngineイメージをローカルでブル度してから個人のGoogleCloudプロジェクトで実行します
4. シリアルポートを使用してComputeEngineOSログを確認し、CloudLoggingのログを確認してシリアルポートへのアクセスを確認します
<details><div>
    答え：４
説明
Reference：
(1) Compute Engine | ドキュメント | サポート
https://cloud.google.com/compute/docs/troubleshooting/troubleshooting-using-serial-console?hl=ja
(2) Jenkins、Packer、Kubernetes を使用したイメージ構築の自動化  |  Cloud アーキテクチャ センター  |  Google Cloud
https://cloud.google.com/architecture/automated-build-images-with-jenkins-kubernetes?hl=ja
解説：
起動に失敗したインスタンスへのシリアルポートに接続してアクセスができます。
Aは原因を特定していない、Cはローカルビルドや個人環境でで実行しても同じ事が再現されるだけで、根本的な原因が解決できるとは限らない方法だと思います。
Bは有効かもしれませんがDに比べてかなり手間がかかる方法です（D であっさり行けるので何でそんな事してるの？という感じです）
正解は D です。
</div></details>

## Q. 4-25
Google Kubernetes Engine クラスタにデプロイされるマイクロサービス ベースのアプリケーションを開発しています。
アプリケーションは Cloud Spanner データベースの読み取りと書き込みを行う必要があります。
コードの変更を最小限に抑えながらセキュリティのベスト プラクティスに従います。
Google Spanner 認証情報を取得するにはアプリケーションをどのように構成するべきでしょうか？
1. 適切なサービスアカウントを作成し、WorkloadIdentityを使用してPodを実行します
2. アプリケーション資格情報をK8Sシークレットとして保存し、環境変数として公開します
3. 適切なルーティングルールを構成し、VPCネイティブクラスタを使用してデータベースを直接接続する
4. CloudKeyManagementServiceを使用してアプリケーション資格情報を保存し、データベース接続が確立されるたびにそれらを取得します
<details><div>
    答え：１
説明
Reference：
(1) IAM
https://cloud.google.com/iam/docs/best-practices-for-using-workload-identity-federation?hl=ja
(2) Google Kubernetes Engine（GKE）
https//cloud.google.com/kubernetes-engine/docs/how-to/workload-identity?hl=ja
(3) Introducing Workload Identity: Better authentication for your GKE applications
https://cloud.google.com/blog/products/containers-kubernetes/introducing-workload-identity-better-authentication-for-your-gke-applications
解説：
Workload Identityを使うアクセス方法がベストプラクティスとして示されていますので本問はAが正解です。
基本的に暗号化等されていても直接サーバー内に情報を保持する方法はWorkload Identityを利用する方法に劣ります(B, C)。
Cは特に何の制限も行っていないので誤りです。
GoogleではWorkload Identityの使用を推奨しているので選択肢にこのワードが入っている場合、正解である可能性が極めて高いです。
</div></details>

## Q. 4-26
Compute Engine アプリケーションを Google Kubernetes Engine に移行することにしました。
コンテナ イメージをビルドし、Cloud Build を使用して Artifact Registry にプッシュする必要があります。
どうすればいいでしょうか？ (回答は 2 つ)
1. アプリケーションのソースコードを含むディレクトリでgcloudbuildssubmitを実行します
2. アプリケーションのソースコードを含むディレクトリで gcloudrundeployapp-name?image.gcr.io/$PROJECT_ID/app-nameを実行します
3. アプリケーションソースコードを含むディレクトリでgcloudrundeployapp-name?image.gcr.io/$PROJECT_ID/app-nameを実行します
4. アプリケーションソースディレクトリで次の内容を含むcloudbuild.yamlという名前のファイルを作成します。
5. アプリケーションソースディレクトリで次の内容を含むcloudbuild.yamlという名前のファイルを作成します。
<details><div>
    答え：１，４
説明
解説：
イメージのURLが Google Container Registry(gcr.io....) の形式になっていますが、それは全選択肢共通なので、考えない（見なかった）事にしましょう。
(もとは、Google Container Registry(GCR) だったところ、単純に Artifact Registry に置き換えたのでしょう。
そうなるとURLも変わってしまいます。
みなさんArtifact Registry 使ってますか？
今は GCR よりそっちの利用が推奨されているのでもし使っていなかったら移行しましょう)
A.はイメージをビルドする時のコマンドですので正しいです（この設問はCI/CDパイプラインはまだ使ってない状況での話のようです）。
B.はデプロイのコマンドですので、設問の内容と異なります。
C.はイメージの名前を変更するコマンドですので、設問の内容と異なります。
Cloud Build では、一般的に cloudbuild.yaml というyamlでビルドに実行するコマンドを指定できます。
Dはイメージを Artifact Registry (GCRにしてますが、そういうことにしておきましょう）にPUSHしています。
Eはデプロイしてしまってますね。
ということで、A, D (を合わせた gcloud build submit コマンド）を使って、イメージをArtifact Registry (記述のままだとGoogle Container Registryにですが）にPush しています。
</div></details>

## Q. 4-27
Google Cloud での新しいアプリケーションのデプロイ手法を設計しています。
デプロイ計画の一環として、ライブトラフィックを使用して新しいアプリケーションと既存のアプリケーションの両方のパフォーマンスメトリックを収集したいと考えています。
起動前に完全な実稼働負荷に対してテストする必要があります。
どうすればいいでしょうか？
1. カナリアテスト戦略を使用します
2. Bule/Greenデプロイ戦略を使用します
3. ローリングアップデートデプロイ戦略を使用します
4. デプロイ時にトラフィックミラーリングでA/Bテスト戦略を使用します
<details><div>
    答え：
説明
Reference:
(1) アプリケーションのデプロイとテストの戦略
https://cloud.google.com/architecture/application-deployment-and-testing-strategies?hl=ja
解説：
A.は本番環境の一部のトラフィックでテストを行う戦略、Bは新バージョンを事前に準備しておいて、瞬時に新旧の切り替えを行う戦略なので、本問題の条件には合わないと思います。
C.は新バージョンへの更新がどんどん進んでしまうので論外でしょう。
この問題は私も良く分かりませんでした(Aかと思いましたが「完全な実稼働負荷に対するテスト」という条件が引っ掛かりました）が、(1)の資料にあるシャドーテストがD.にあたり本問題の条件を満たしています。
正解はDとなります。
</div></details>

## Q. 4-28
Compute Engine インスタンスで起動するアプリケーションをソフトウェア開発プロセスの環境 (開発、QA、ステージング、本番) に対応する複数の異なるプロジェクトに分けて開発しています。
各プロジェクトのインスタンスのアプリケーション コードは同じですが構成が異なります。デプロイ中、各インスタンスはサービスを提供する環境に基づいてアプリケーションの構成を受け取る必要があります。
このフローを構成するためのステップ数を最小限に抑えたいと考えています。
どうすればいいでしょうか？
1. インスタンスを作成するときにgcloudコマンドを使用して起動スクリプトを構成し、正しい環境を示すプロジェクト名を決定します
2. 各プロジェクトでそれが提供する環境を値とするメタデータキー環境を構成します。デプロイツールを使用してインスタンスメタデータをクエリし、環境値に基づいてアプリケーションを構成します
3. 選択したデプロイツールを各プロジェクトのインスタンスにデプロイします。デプロイジョブを使用してバージョン管理システムから適切な構成ファイルを取得し、各インスタンスにアプリケーションをデプロイするときに構成を適用します
4. 各インスタンスの起動中にencironmentという名前のインスタンスカスタムメタデータキーを構成します。この値はインスタンスが提供する環境です。デプロイツールを使用してインスタンスメタデータをクエリし、環境値に基づいてアプリケーションを構成します。
<details><div>
    答え：
説明
Reference：
(1) VM メタデータについて
https://cloud.google.com/compute/docs/metadata/overview?hl=ja
解説：
特に明示的にメタデータを設定しなくても、デフォルトのメタデータキーのセットで各環境の判別はできると考えます。
それに対して、A, D は回りくどい処理を行っていると思われます。
C に関しても、この方法で出来ないとは言えませんが、バージョン管理システムで管理される情報ファイルから情報を得るという冗長かつ信頼度が低い方法を行っていると考えられます。
B が最も適切なアプローチであると考えます。
</div></details>

## Q. 4-29
CI/CD パイプラインに Cloud Build を使用して特定のファイルを Compute Engine 仮想マシンにコピーするなど、いくつかのタスクを完了しています。
パイプラインでは同じパイプライン内の後続のビルダーがアクセスできるようにパイプライン内の 1つのビルダーで生成されたフラットファイルが必要です。
パイプライン内のすべてのビルダーがファイルにアクセスできるようにするにはファイルをどのように保存するべきでしょうか？
1. ComputeEngineインスタンスのメタデータを使用し、ファイルの内容を保存および取得します
2. ファイルの内容を/workspaceのファイルに出力します。後続のビルドステップで同じ/workspaceから読み取ります
3. gsutilを使用し、ファイルの内容をCloudStorageオブジェクトに出力します。後続のビルドステップで同じオブジェクトから読み取ります
4. curlを介してHTTPPOSTを実行するビルド引数を別のWebサーバに追加して1つのビルダーで値を保持します。後続のビルドステップからcul経由でHTTPGETを使用して、値を読み取ります
<details><div>
    答え：
説明
解説：
特に気密性の高い情報を扱うなどの記載はありませんので、難しいことは考える必要はない要件です。
B.に記載の内容で要件が満たせます。
</div></details>

## Q. 4-30
継承した Google Kubernetes Engine で Webアプリケーションを実行しています。
アプリケーションが既知の脆弱性を持つライブラリを使用しているかどうか、または XSS 攻撃に対して脆弱であるかどうかを判断したいと考えています。
どのサービスを使用するべきでしょうか？
1. CloudArmor
2. Debugger
3. WebSecurityScanner
4. ErrorReporting
<details><div>
    答え：3
説明
Reference：
(1) Web Security Scanner の概要
https://cloud.google.com/security-command-center/docs/concepts-web-security-scanner-overview?hl=ja
(2) Google Cloud Armor の概要
https://cloud.google.com/armor/docs/cloud-armor-overview?hl=ja
(3) Error Reporting
https://cloud.google.com/error-reporting?hl=ja
(4) 非推奨(Cloud Debugger)
https://cloud.google.com/debugger/docs/deprecations?hl=ja
解説：
CのWebセキュリティスキャナーはWebアプリケーションの脆弱性をチェックする機能です。
A は分散型サービス拒否（DDoS）攻撃や、クロスサイトスクリプティング（XSS）、SQLインジェクション（SQLi）などのアプリケーション攻撃など、さまざまなタイプの脅威から Google Cloud のデプロイを保護するのに役立ちます。
脆弱性のチェックではなく、外部からのアクセスを保護するファイヤーウォールの役割を果たします。
B はアプリケーションの不具合(バグ)の原因を調査する為のツールです(Cloud Debuggerは。2023年5月31日に非推奨となり代わりにSnapshot Debuggerが使えるようです）。
D は実行中のクラウドサービスで発生したクラッシュの回数をカウントし、分析と集計を行います。
正解は C となります。
</div></details>

## Q. 5-1
Cloud Run にデプロイされ、Cloud Functions を使用する新しいアプリケーションに取り組んでいます。
新しい機能が追加されるたびに新しい Cloud Functions と Cloud Run サービスがデプロイされます。
ENV 変数を使用してサービスを追跡し、サービス間通信を有効にしますが ENV 変数のメンテナンスが難しくなっています。
スケーラブルな方法で動的検出を実装したいと考えています。
どうすればいいでしょうか？
1. CloudRunAdminApiとCloudFunstionsAPIを使用してマイクロサービスを構成し、GoogleCloudプロジェクトにデプロイされたCloudRunサービスとCloudFunstionsをクエリします
2. ServiceDirectoryn甘え空間を作成します。API呼び出しを使用してデプロイ時にサービスを登録し、実行時にクエリを実行します
3. FunctionsとRunサービスエンドポイントの名前を変更するには十分に文書化された命名規則を使用します
4. 単一のComputeEngineインスタンスにHashicorpコンソールをデプロイします。デプロイ時にサービスをコンソールに登録し、実行時にクエリを実行します
<details><div>
    答え：2
説明
Reference:
(1) サービス ディレクトリの概要
https://cloud.google.com/service-directory/docs/overview
解説：
Cはアナログな方法で、Dは追加リソースが必要となり今一つです。
Aは特に問題の解決策になっていなです。
B が正解となります。
Referenceの資料をご参照ください。
</div></details>

## Q. 5-2
Google Kubernetes Engine（GKE）で実行するマイクロサービス ベースのアプリケーションを開発しているとします。
一部のサービスは、さまざまな Google Cloud API にアクセスする必要があります。
Google 推奨のベスト プラクティスに沿ってクラスタでこれらのサービスの認証を設定するには、どうすればよいですか（2 つ選択してください）。
1. GKEノードに関連付けられたサービスアカウントを使用する
2. gcloudコマンドラインツールを経由して、クラスタでWorkloadIdentityを有効にする
3. SercretManagerからGoogleサービスアカウントキーにアクセスします
4. GoogleサービスアカウントキーをSercretManagerに登録する
5. gcloudでroles/iam.workloadidentityuserを使用して、googleサービスアカウントとK8sサービスアカウントをバインドする
<details><div>
    答え：2,5
説明
Reference:
(1) Workload Identity を使用する
https://cloud.google.com/kubernetes-engine/docs/how-to/workload-identity?hl=ja
解説：
A は不正解です。
機能する場合もありますが、すべてのサービスが同じサービス アカウントを使用するため、権限の区別や詳細なロギングを実現できません。
B と E はともに、GKE と Google サービス アカウントを接続するため、GKE は Google サービス アカウントでサービスを認証できます。
C, D は不正解です。
この方法は可能であるものの推奨されません。
サービス アカウントのキーのローテーションが必須であるためです。
</div></details>

## Q. 5-3
最近、アプリケーションに影響を与える政府規制が可決されました。
コンプライアンスの目的で特定のアプリケーションログの複製をアプリケーションのプロジェクトからセキュリティチームに限定されたプロジェクトに送信する必要があります。
どうすればいいでしょうか？
1. セキュリティチームのプロジェクトでユーザー定義のログバケットを作成します。CloudLoggingシンクを構成してアプリケーションのログをセキュリティチームのプロジェクトのログバケットにルーティングします
2. _rewuiredログバケットからプロジェクト内のセキュリティチームのログバケットにコピーするジョブを作成します
3. _defaultログバケットシンクルールを変更してログをセキュリティチームのログバケットに再ルーティングします
4. システムイベントログを_rewuiredログバケットからプロジェクトのセキュリティチームのログバケットにコピーするジョブを作成します
<details><div>
    答え：1
説明
解説：
ログの受け渡しは sync で出来るので、わざわざコピーしている選択肢は除外です。
A, C の２択となります。
「特定のアプリケーションログ」のみが必要なので、A の処理が適切です。

正解は A となります。
</div></details>

## Q. 5-4
開発中の Cloud Run サービスのロギングを構成しています。
コンテナ インスタンスは、構造化ログを標準出力（stdout）ストリームと標準エラー（stderr）ストリームに書き込みます。
自動的に作成されたリクエストログをコンテナログに相互に関連付けたいと考えています。
どうすればよいですか。
1. CloudTraceにトレースを送信するためにアプリケーションを計測可能にする
2. リクエストごとに一意のIDをランダムに生成して、Snapshotdebuggerを使用してログポイントを追加する
3. ヘッダー値をX-Cloud-Trace-Contextとして、ログステートメントにlogging-googleapis.com/traceフィールドを追加する
4. リクエストごとに一意のIDをランダムに生成して、ログステートメントにlogging-googleapis.com/traceフィールドを追加する
<details><div>
    答え：3
説明
Reference:
(1) ログの記録と表示
https://cloud.google.com/run/docs/logging?hl=ja#correlate-logs
(2) 構造化ロギング
https://cloud.google.com/logging/docs/structured-logging?hl=ja
解説：
A は不正解です。
Cloud Trace は、レイテンシ データを調べるために使用します。
B は不正解です。
最大 24 時間アクティブなままとなる一時的なロギングが追加されます。
C は正解です。
ログエクスプローラに「親子」関係が作成されます。
D は不正解です。
自動生成されたリクエストログにコンテナログは関連付けられません。
logging.googleapis.com/labels は主にユーザーが生成した構造化されたログのためのもので、コンテナログ内には関連付けできる対応する要素がありません。
</div></details>

## Q. 5-5
Google Kubernetes Engine での Deployment の更新中にアプリケーションが強制的にシャットダウンされたことに気付きました。
アプリケーションが終了する前にデータベース接続を閉じませんでした。
アプリケーションを更新して正常なシャットダウンを確実に完了したいと考えています。
どうすればいいでしょうか？
1. コードを更新して受信したsigtermシグナルを処理し、データベースから正常に切断します
2. PodDisruptionBudgetを構成してPdが強制的にシャットダウンされないようにします
3. アプリケーションのterminationGracePeriodSecondsを増やします
4. アプリケーションをシャットダウンするPreStopフックを構成します
<details><div>
    答え：1
説明
Reference:
(1) Kubernetes best practices: terminating with grace
https://cloud.google.com/blog/products/containers-kubernetes/kubernetes-best-practices-terminating-with-grace
解説：
問われていることは「正常なシャットダウンを確実に完了したい」ということで、この一つの要件に「アプリケーションが終了する前にデータベース接続を閉じ(る)」
が含まれるでしょう。
シャットダウン時の処理を問題にしているので、Bは完全に問題を理解していないですね。
C, D に関してはデータベース接続が閉じられなかった事に対する対策が述べられていません。
従って正解は A となります。
</div></details>

## Q. 5-6
あなたは、Cloud Run で Java アプリケーションを実行しています。
アプリケーションのエラー メッセージが Error Reporting コンソールに表示されません。どうすればよいですか。
1. そのJavaアプリケーションにCloudMonitoringクライアントライブラリがバンドルされていることを確認する
2. アプリケーションログが正しいRegionalStorageバケットに書き込まれていることを確認する
3. アプリケーションエラーがstderrに書き込まれていることを確認する
4. system.out.printinを使用して例外をログに記録する
<details><div>
    答え：3
説明
Reference:
(1) トラブルシューティング
https://cloud.google.com/error-reporting/docs/troubleshooting?hl=ja
(2) Error Reporting
https://cloud.google.com/run/docs/error-reporting?hl=ja
解説：
A は不正解です。
Cloud Run でのエラーレポートに外部ライブラリは必要ありません。
B は不正解です。
Error Reporting はリージョン ログバケットに格納されているログや、他のプロジェクトにルーティングされたログの分析は行いません。
C は正解です。
Error Reporting で認識されるには、エラーは Cloud Run で stderr に書き込まれる必要があります。
D は不正解です。
system.out.println は stderr ではなく stdout に出力します。
</div></details>

## Q. 5-7
あなたは大規模な組織の開発者です。
Web アプリケーションを Google Kubernetes Engine (GKE) にデプロイしています。
DevOps チームは Cloud Deploy を使用してアプリケーションを GKE の Dev、Test、Prod クラスタにデプロイする CI/CD パイプラインを構築しました。
Cloud DeployがDevクラスタにアプリケーションを正常にデプロイした後、それをTestクラスタに自動的に昇格させたいと考えています。
Google が推奨するベスト プラクティスに従って、このプロセスをどのように構成するべきでしょうか？
1. clouddeploy-operationsトピックからのsucceeded Pub/SubメッセージをリスんするCloudBuildトリガーを作成します。CloudBuildを構成して、アプリケーションをテストクラスタに昇格されるステップを含めます
2. DeployAPIを呼び出してアプリケーションをテストクラスタに昇格させるCloudFunctionsを作成します。cloud-buildsトピックからのSuccededPub/Subメッセージによってトリガーされるようにこの関数を構成します
3. DeployAPIを呼び出してアプリケーションをテストクラスタに昇格させるCloudFunctionsを作成します。clouddeploy-operationsトピックからのSuccededPub/Subメッセージによってトリガーされるように関数を構成します
4. gke-deployビルダーを使用するCloudBuildパイプラインを作成します。cloud-buildsトピックからのSuccededPub/SubメッセージをリスんするCloudBuildトリガーを作成します。このパイプラインを構成してテストクラスタへのデプロイ手順を実行します
<details><div>
    答え：1
説明
Reference:
(1) Google Cloud Deploy と他のシステムとの統合
https://cloud.google.com/deploy/docs/integrating?hl=ja#integrating_with_automated_testing
解説：
「アプリケーションを正常にデプロイした後、それをTestクラスタに自動的に昇格」とのことですので、まずはDevクラスタでデプロイが完了している必要があります。
よって正解は、A, Cの２択となります(B, D.は「cloud-buildsトピック」なので、まだイメージがビルドされただけです)。
Cloud Build 自体に指定のスクリプトを実行する機能が備わっているので、他のツールの手助けは殆どの場合不要で、わざわざ Cloud Functionsで処理を行わせる必要がありません。
従って正解は A となります。
</div></details>

## Q. 5-8
新しいアプリケーションコードを本番環境にプロモートする前にさまざまなユーザーに対してテストを実施する必要があります。
この計画にはリスクが伴いますがアプリケーションの新しいバージョンを運用ユーザーでテストし、オペレーティングシステムに基づいてアプリケーションの新しいバージョンに転送されるユーザーを制御したいと考えています。
新しいバージョンでバグが発見された場合、アプリケーションの新しくデプロイされたバージョンをできるだけ早くロールバックする必要があります。
どうすればいいでしょうか？
1. アプリケーションをCloudRunにデプロイします。リビジョンタグに基づいてトラフィック分割を使用し、ユーザートラフィックのサブセットを新しいバージョンに転送します
2. AuthosServiceMeshを使用してGKEアプリケーションをデプロイします。トラフィック分割して、ユーザーエージェントヘッダーに基づいてユーザートラフィックのサブセットを新しいバージョンに転送します
3. アプリケーションをAppEngineにデプロイします。トラフィック分割を使用し、IPアドレスに基づいてユーザートラフィックのサブセットを新しいバージョンに転送します
4. アプリケーションをComputeEngineにデプロイします。TrafficDirectorを使用し、事前定義された重みに基づいてユーザートラフィックのサブセットを新しいバージョンに転送します
<details><div>
    答え：2
説明
解説：
「オペレーティングシステムに基づいてアプリケーションの新しいバージョンに転送されるユーザーを制御したい」とのことで、オペレーティングシステムはユーザーエージェントで判定可能です。
Cloud Run, Anthos Service Mesh, App Engine, Traffic Directorの全てでトラフィック分割は可能ですが、選択肢の中で、ユーザーエージェントでの振り分けを言及しているのは B のみです。
したがって本問題は B が正解です。
</div></details>

## Q. 5-9
ユーザーに代わって Google Cloud API を介して Google Cloud サービスと対話する必要がある Java Web サーバを開発しています。
ユーザーは Google Cloud ID を使用して Google Cloud API に対して認証できる必要があります。
Web アプリケーションにどのワークフローを実装する必要がありますか？
1. ユーザーがアプリケーションにアクセスしたらGoogleのユーザー名とパスワードの入力を求めます。SHAパスワードハッシュをユーザーの名称と共にアプリケーションのデータベースに保存します。アプリケーションは、Authorizationリクエストヘッダーにユーザーの名称とパスワードのハッシュを含むHTTPSリクエストを使用してGoogleCloudAPIに対して認証を行います
2. ユーザーがアプリケーションにアクセスしたらGoogleのユーザー名とパスワードの入力を求めます。HTTPSリクエストでユーザーの名称とパスワードをGoogleCloud認可サーバーに転送し、アクセストークンをリクエストします。Googleサーバーはユーザーの認証情報を検証し、アプリケーションにアクセストークンを返します。アプリケーションはアクセストークンを使用してGoogleCloudAPIを呼び出します
3. ユーザーがアプリケーションにアクセスしたら要求された権限のリストを含むGoogleCloudの同意画面にユーザーをルーティングし、SSOを使用してGoogleアカウントにサインインするようにユーザーに促します。ユーザーがサインインしてどうしするとアプリケーションはGoogleサーバーから認証コードを受け取ります。GoogleサーバーはブラウザのCookieに保存されている認証コードをユーザーに返します。ユーザーはCookieの認証コードを使用してGoogleCloudAPIに対して認証を行います
4. ユーザーがアプリケーションにアクセスしたら要求された権限のリストを含むGoogleCloudの同意画面にユーザーをルーティングし、SSOを使用してGoogleアカウントにサインインするようにユーザーに促します。ユーザーからサインインして同意するとアプリケーションはGoogleサーバーから認証コードを受け取ります。アプリケーションは認証コードをアクセストークンをと交換するようGoogleサーバーに要求します。GoogleサーバーはアプリケーションがGoogleCloudAPIを呼び出すために使用するアクセストークンで応答します
<details><div>
    答え：4
説明
Reference:
(1) OAuth 2.0 を使用した Google API へのアクセス
https://developers.google.com/identity/protocols/oauth2?hl=ja
(2) ウェブサーバー アプリケーションに OAuth 2.0 を使用する
https://developers.google.com/identity/protocols/oauth2/web-server?hl=ja
解説：
Google Cloud API を呼び出すためにはアクセストークンを使用するので、それが取得できる選択肢として、B, D が残ります。
Bの方法はユーザー名、パスワードの通信が２回発生する点、Dよりもセキュリティー面で劣るでしょう。
Dでは、アプリケーション側にはユーザー名、パスワードの通信は発生しません。
認証は全てGoogle Serverに任せる D の方が優れた方法だと思います。
Reference (1) のシナリオ/ウェブサーバーアプリケーションでも認証後に認証コードを受け取った後、認証コードをアクセストークンと交換するフローが示されています。
したがって D が正解となります。
</div></details>

## Q. 5-10
Cloud Storage バケットに保存された非公開の画像と動画を含む Webアプリケーションを開発しています。
ユーザーは匿名であり、Google アカウントを持っていません。
アプリケーション固有のロジックを使用して、画像とビデオへのアクセスを制御したいと考えています。
アクセスをどのように構成しますか？
1. 各WebアプリケーションユーザーのIPアドレスをキャッシュしてCloudArmorを使用して名前付きIPテーブルを作成します。ユーザーがバックエンドバケットにアクセスできるようにするCloudArmorセキュリティポリシーを作成します
2. StorageObjectViewerIAMロールをalluserに付与します。Webアプリケーションによる認証後にユーザーがバケットにアクセスできるようにします
3. Identity-AwareProxyを構成してWebアプリケーションでユーザーを認証します。IAPによる認証後にユーザーがバケットにアクセスできるようにします
4. バケットへの読み取りアクセスを許可する署名付きURLを生成します。Webアプリケーションによる認証後にユーザーがURLにアクセスできるようにします
<details><div>
    答え：4
説明
Reference:
(1) 署名付き URL(Cloud Storage)
https://cloud.google.com/storage/docs/access-control/signed-urls?hl=ja#should-you-use
解説：
Aは例えばモバイル通信ユーザーの場合簡単にIPアドレスが変わってしまうので適切ではありません。
B, Cは「Google アカウントを持っていません」という前提条件により実現できないでしょう。
残りは D となりますが、この方法はこういったケースでの典型的な解決方法です。
正解は D です。
</div></details>

## Q. 5-11
ライブストリームをブロードキャストするマイクロサービス アプリケーションを Google Kubernetes Engine (GKE) にデプロイしています。
予測できないトラフィック パターンと同時にユーザー数の大きな変動が予想されます。
アプリケーションは次の要件を満たす必要があります。
人気のあるイベント中に自動的にスケーリングし、高可用性を維持
ハードウェア障害が発生した場合の回復力
デプロイメント パラメーターをどのように構成しますか？ (回答は 2 つ)
1. マルチゾーンノードプールを使用してワークロードを均等に分散します
2. 複数のゾーンノードプールを使用してワークロードを均等に分散します
3. クラスタオートスケーラーを使用してノードプールないのノード数を変更し、水平Podオートスケーラーを使用してワークロードをスケーリングします
4. クラスタノードを使用してComputeEngineのマネージドインスタンスグループを作成します。マネージドインスタンスグループの自動スケーリングルールを構成します
5. GKEのCPUとメモリの使用率に基づいてCloudMonitoringでアラートポリシーを作成します。CPUとメモリの使用率が事前に定義された閾値を超えた場合にスクリプトを実行してワークロードをスケーリングするように勤務中のエンジニアに依頼します
<details><div>
    答え：1,3
説明
Reference:
(1)スケーラビリティを計画する
https://cloud.google.com/kubernetes-engine/docs/concepts/planning-scalability?hl=ja#choosing_multi-zonal_or_single-zone_node_pools
解説：
A, B がものすごく微妙ですが、明確に「マルチゾーンノード プール」と記述されている方を選択します。
GKEでは「Compute Engine のマネージドインスタンス グループ」は使いませんので、Dは除外です。
「自動的にスケーリングし」という条件からCとEではCを選択することになります。
GKEは特にCloud Monitoringでの指標に頼らず独自の設定でスケーリングします(特に別途スクリプトを実行する必要がありません)
従って正解は A, C となります。
</div></details>

## Q. 5-12
チームはさまざまなソースからのニュース記事を集約するアプリケーションを維持する責任があります。
モニタリング ダッシュボードには一般公開されているリアルタイムレポートが含まれており、Compute Engine インスタンス上でWebアプリケーションとして実行されます。
外部の利害関係者とアナリストは認証なしで安全なチャネルを介してこれらのレポートにアクセスする必要があります。
この安全なチャネルをどのように構成するべきですか？
1. インスタンスにパブリックIPアドレスを追加します。インスタンスのサービスアカウントキーを使用してトラフィックを暗号化します
2. CloudSchedulerを使用して1時間ごとにCloudBuildをトリガーし、レポートからエクスポートします。レポートをパブリックCloudStorageバケットに保存します
3. モニタリングダッシュボードの前にHTTPロードバランサを追加します。通信チャネルを保護するようにIdentity-AwareProxyをを構成します
4. モニタリングダッシュボードの前にHTTPロードバランサを追加します。トラフィックの暗号化のためにロードバランサにGoogleマネージドSSL証明書を設定します
<details><div>
    答え：4
説明
Reference:
(1) Google マネージド SSL証明書を使用する
https://cloud.google.com/load-balancing/docs/ssl-certificates/google-managed-certs?hl=ja
解説：
A, Bはほぼ全開状態ですね。
サービスアカウントを使用して HTTPSトラフィックを暗号化することはできません(Aの記述の間違い)。
Bの定期的なエクスポートは、リアルタイムの要件を満たしません。
A, Bは除外してよさそうです。
外部の関係者への公開ということで、D が正解です。
外部の HTTPS エンドポイントが提供され、Google マネージド サービスと有効な SSL 証明書が使用されます。
Cに記載のIAP は通信チャネルを保護するのではなくユーザーを認証します。
技術的には、チャネルは Cloud Load Balancing によってすでに保護されていますが、適切な証明書が使用されません。
（内部関係者で GoogleWorkspace で管理されるユーザーIDが発行されているなら C の方法が使えるでしょう）
</div></details>

## Q. 5-13
Go アプリケーションから Cloud Spanner データベースに書き込んでいます。
Google が推奨するベストプラクティスを使用してアプリケーションのパフォーマンスを最適化したい。
どうすればいいでしょうか？
1. Cloudクライアントライブラリを使用してCloudSpannerに書き込みます
2. GoogleAPIクライアントライブラリを使用してCloudSpannerに書き込みます
3. カスタムgRPCクライアントライブラリを使用してCloudSpannerに書き込みます
4. サードパーティのHTTPクライアントライブラリを使用してCloudSpannerに書き込みます
<details><div>
    答え：1
説明
Reference:
(1) Cloud クライアント ライブラリ
https://cloud.google.com/apis/docs/cloud-client-libraries?hl=ja
(2) Google API Client Libraries
https://developers.google.com/api-client-library?hl=ja
解説：
アプリケーション（プログラム）から様々なリソースの機能を利用する場合、それぞれのリソースのCloud クライアントライブラリを使用して実装します。
それしか言いようがありませんね。
BはGoogle マップ、Google ドライブ、YouTube などのさまざまな Google サービスにプログラムでアクセス為のAPIです。
Cloud Spannerのようなリソースにアクセスする場合は、Cloudクライアントライブラリを使用します。
gRPCを直接使うのはプログラムが複雑になるので避けたいです。
Cloudクライアントライブラリが対象リソースの制御に必要な処理を行っているので、Cloudクライアントライブラリを使えばその部分の処理を書く必要がありません。
Dはもうそこまでしなくていいでしょうという感じです（バグも怖い、というかそもそも存在するか不明。あったとしてもGoogleが推奨するベストプラクティスなわけないでしょう）。
正解は A となります。
</div></details>

## Q. 5-14
最近、OpenTelemetry を使用して新しいアプリケーションを計測し、Trace でアプリケーション リクエストのレイテンシを確認したいと考えています。
特定のリクエストが常にトレースされるようにする必要があります。
どうすればいいでしょうか？
1. 10分待ってからCloudTraceがこれらのタイプの要求を自動的にキャプチャーすることを確認します
2. 開発プロジェクトからこのタイプのリクエストを繰り返し送信するカスタムスクリプトを作成します。
3. CloudTraceAPIを使用してカスタム属性をトレースに適用します
4. 適切なパラメータを使用してX-Cloud-Trace-Contextヘッダーをリクエストに追加します
<details><div>
    答え：4
説明
Reference:
(1) Cloud Trace 用の計測
https://cloud.google.com/trace/docs/setup?hl=ja#force-trace
解説：
特定のリクエストに D に記載の内容を適用すれば、そのリクエストのレイテンシーを計測できます。
Aはリクエストが特定されていません。
Bはそのリクエストの単体テストでのレイテンシーとなり通常丈太でのレイテンシーと異なり正確なデータを計測していない可能性があります。
「特定のリクエストが常にトレースされる」という要件にも合っていないでしょう。
Cは元のトレースデータの出所、が不明です。
特定のリクエストを常にトレースしたデータを入手する手段が明確なら有りかもしれませんがそこの記述がないのでアウトです。
Dが正解となります。
</div></details>

## Q. 5-15
Google Cloud で実行される会社の eコマースプラットフォームの支払いシステムを管理します。
会社は内部監査目的で 1年間、コンプライアンス要件を満たすために 3年間、ユーザーログを保持する必要があります。
オンプレミスストレージの使用量を最小限に抑え、簡単に検索できるようにするには新しいユーザーログを Google Cloud に保存する必要があります。
ログが正しく保存されていることを確認しながら、労力を最小限に抑えたいと考えています。
どうすればいいでしょうか？
1. バケットがロックオンになっているCloudStorageバケットにログを保存します
2. 3年間の保存期間でCloudStorageバケットにログを保存します
3. ログをCloudLoggingにカスタムの保持期間を持つカスタムログとして保存します
4. 1年間の保持期間でCloudStorageバケットにログを保存します。1年後、保持期間が2年の別のバケットにログを移動します
<details><div>
    答え：3
説明
Reference:
(1) Cloud 監査ログのベスト プラクティス
https://cloud.google.com/logging/docs/audit/best-practices?hl=ja
解説：
「簡単に検索できるようにする」ということから、Loggingのデータ保持期間を3年にすれば良いでしょう。
Cloud Storageでは「簡単に検索」という要件が満たせません。
</div></details>

## Q. 5-16
アプリケーションは複数のゾーンのマネージド インスタンス グループ (MIG) 内の数百の Compute Engine インスタンスにデプロイされています。
重大な脆弱性をすぐに修正するために新しいインスタンス テンプレートをデプロイする必要がありますが、サービスへの影響を回避する必要があります。
インスタンス テンプレートを更新した後、MIG に対してどのような設定を行う必要がありますか？
1. 最大サージを100%に設定します
2. 更新モードをopportunisticに設定します
3. 最大使用不可を100%に設定します
4. 最小待機時間を0秒に設定します
<details><div>
    答え：4
説明
Reference:
(1) MIG で VM 構成の更新を自動的に適用する
https://cloud.google.com/compute/docs/instance-groups/rolling-out-updates-to-managed-instance-groups?hl=ja#minimum_wait_time
解説：
Cはサービスに影響が出る更新になる(使用不可でも更新されてしまう）ので除外。
BはVMを手動更新することになりますが「複数のゾーンのマネージドインスタンスグループ (MIG) 内の数百のCompute Engine」
という事で選択したくありません。
A.に関しては特に100%にする必要性はないと思われます。
インスタンス更新(ヘルスチェックは完了済み）後にすぐに適用する D が正解となります。
</div></details>

## Q. 5-17
このアーキテクチャ図は何千ものデバイスからデータをストリーミングするシステムを示しています。
パイプラインにデータを取り込み、データを保存し、SQL ステートメントを使用してデータを分析したいと考えています。
ステップ 1、2、3、4 で使用する Google Cloud サービスはどれでしょうか？
1. AppEngine、Pub/Sub、BigQuery、Firestore
2. Dataflow、Pub/Sub、Firestore、BigQuery
3. Pub/Sub、Dataflow、BigQuery、Firestore
4. Pub/Sub、Dataflow、Firestore、BigQuery
<details><div>
    答え：４
説明
解説：
ストリーミングの処理はPub/SubからDataflowを通じて必要なリソースへの取り込みが典型的な利用のしかたなので、C,  D に絞り込めます。
3.がTransaction Databese, 4.が Analytics ということは、3: Transaction処理できるDBソリューション(大容量）, 4: BigQueryと考えられます。
これに当てはまるのは、D. という事になりなす。
3.の Cloud Firestoreは要件的に問題ありません。
</div></details>

## Q. 5-18
アプリケーションは Compute Engine で実行されるコードによって編成された一連の疎結合サービスで構成されています。
特定のバージョンのサービスを見つけて使用する新しい Compute Engine インスタンスをアプリケーションで簡単に立ち上げたいと考えています。
これはどのように構成しますか？
1. サービスエンドポイント情報を実行時に取得され、目的のサービスへの接続に使用されるメタデータとして定義します
2. サービスエンドポイント情報を実行時に取得され、目的のサービスへの接続に使用されるラベルデータとして定義します
3. 実行時に環境変数から取得され、目的のサービスへの接続に使用されるサービスエンドポイント情報を定義します
4. サービスを定義して、固定のホスト名とポートを使用して目的のサービスに接続します。エンドポイントのサービスを新しいバージョンに置き換えます
<details><div>
    答え：1
説明
Reference:
(1) VM メタデータについて
https://cloud.google.com/compute/docs/metadata/overview?hl=ja
(2) 用語集
https://cloud.google.com/apis/design/glossary?hl=ja#api_service_endpoint
解説：
C, D の方法は A. の方法に比べて柔軟性が低いでしょう。
B はラベルの取得方法が難しいと思います。
良く使われる(Reference (1)参照）A の方法が最も簡単で柔軟な方法でしょう。
正解は A となります。
</div></details>

## Q. 5-19
Cloud Build を使用して継続的インテグレーション パイプラインを構成し、Google Kubernetes Engine (GKE) への新しいコンテナ イメージのデプロイを自動化しています。
パイプラインはソース コードからアプリケーションをビルドし、個別のステップで単体テストと統合テストを実行し、コンテナを Container Registry にプッシュします。
アプリケーションは Python Web サーバ上で実行されます。
Dockerfile は次のとおりです。
FROM python:3.7-alpine -
COPY . /app -
WORKDIR /app -
RUN pip install -r requirements.txt
CMD [ "gunicorn", "-w 4", "main:app" ]
Cloud Build の実行が完了するまでに予想以上の時間がかかっていることに気付きました。
ビルド時間を短縮したいと思っています。
どうすればいいでしょうか？ (回答は 2 つ)
1. CloudBuildの実行にはより高いCPUを備えた仮想マシンのサイズを選択します
2. VPCないのComputeEngineにContainerRegistryをデプロイし、それを使用して最終的なイメージを保存します
3. ビルド構成ファイルで--chache-from引数を使用し、後続のビルドのためにDockerイメージをキャッシュします
4. Dockerfileの基本イメージをubuntu:latestに変更し、パッケージマネージャユーティリティを使用してPython3.7をインストールします
5. アプリケーションのソースコードをCloudStorageに保存し、gsutilを使用してソースコードをダウンロードするようにパイプラインを構成します
<details><div>
    答え：1,3
説明
解説：
設問の案件でB, E のようなやり方は見たことも聞いたこともありませんので、除外。
D が有効なパフォーマンスの向上につながる根拠がありませんし、基本イメージはalpinaよりもubuntuの方が大きいのではないかと思われます。
従って正解は A, C. です。
A.は明らかにビルドの高速化につながります。
キャッシュも利用できればよりパフォーマンスが向上します。
正解は A, C です。
</div></details>

## Q. 5-20
最近、Google Kubernetes Engine にアプリケーションをデプロイしましたがアプリケーションの新しいバージョンをリリースする必要があります。
新しいバージョンで問題が発生した場合に備え、以前のバージョンに即座にロールバックする機能が必要です。
どのデプロイモデルを使用する必要がありますか？
1. ローリングデプロイを実行し、デプロイ完了後に新しいアプリケーションをテストします
2. A/Bテストを実行し、新しいテストが実装された後、定期的にアプリケーションをテストします
3. Blue/Greenデプロイを実行し、デプロイ後に新しいアプリケーションをテストします
4. カナリアデプロイを実行し、新しいバージョンのデプロイ後に新しいアプリケーションを定期的にテストします
<details><div>
    答え：3
説明
解説：
A.は既存のPodと新しいPodを徐々に入れ替えていくデプロイ戦略なので、即座にロールバックは出来ません。
B.はテストの方法に関する説明でデプロイ戦略が説明されていません。
C.はリソースが余計にかかりますが、古い実行環境と新しい実行環境を２重に準備し、準備が出来たら新しいアプリケーションい切り替えるデプロイ戦略です。
旧実行環境がそのまま残されているので、問題があった場合は即座に旧環境にロールバックする事が可能なデプロイ戦略です。
D. は、一部のPodを新バージョンにデプロイし、問題がないか確認後に全体を切り替えていくデプロイ戦略です。
一部とは言え、新バージョンを旧バージョンにデプロイし直す必要があり、即座にロールパックとは行きません。
以上より C. が正解となります。
</div></details>

## Q. 5-21
アプリケーションを Compute Engine にデプロイしています。
Compute Engine インスタンスの 1つを起動できませんでした。
どうすればいいでしょうか？ (回答は 2 つ)
1. ファイルシステムが破損しているかどうかを確認します
2. 別のSSHユーザーとしてComputeEngineにアクセスします
3. インスタンスでのFWルール、またはルートのトラブルシューティング
4. インスタンスの起動ディスクが完全にいっぱいかどうかを確認します
5. インスタンスとの間のネットワークトラフィックがドロップされているかどうかを確認します
<details><div>
    答え：1,4
説明
Reference:
(1) VM の起動のトラブルシューティング
https://cloud.google.com/compute/docs/troubleshooting/vm-startup?hl=ja#identify_the_reason_why_the_boot_disk_isnt_booting
解説：
Bは全く無関係の記述かと思われます。
C, Eは他のインスタンスが起動出来ていることから起動失敗の原因とは考えづらいです。
これらと特定のインスタンスの問題であることから、A, D が正解と考えられます。
</div></details>

## Q. 5-22
オンプレミスから Google Cloud への会社のアプリケーションの移行を計画する任務を負っています。
会社のモノリシック アプリケーションは eコマースWebサイトです。
アプリケーションは Google Cloud にデプロイされたマイクロサービスに段階的に移行されます。
会社の収益の大部分はオンライン販売によって生み出されているため、移行中のリスクを最小限に抑えることが重要です。
機能に優先順位を付け、移行する最初の機能を選択する必要があります。
どうすればいいでしょうか？
1. フロントエンドと製品データベースに統合されている製品カタログを移行します
2. フロントエンド、注文データベース、サードパーティの支払いベンダーに統合された支払処理を移行します
3. 注文データベース、在庫システム、サードパーティの配送ベンダーと統合された注文フルフィルメントを移行します
4. フロントエンド、カートデータベース、在庫システム、支払処理システムに統合されたショッピングカートを移行します
<details><div>
    答え：１
説明
解説：
モノシリックなアプリケーションをマイクロサービスに段階的に移行する方法としてはなるべく影響が大きくない簡単なサービスから徐々にマイクロサービスに移行する事が推奨されています。
B, C, D は、他のシステムとも連携しており複雑な処理であるのに比べてAは簡単な処理であると考えられるので、A が正解です。
</div></details>

## Q. 5-23
Google Cloud のさまざまなプロジェクトでコンテナを作成して実行しています。
開発中のアプリケーションは Google Kubernetes Engine (GKE) 内から Google Cloud サービスにアクセスする必要があります。
どうすればいいでしょうか？
1. GoogleサービスアカウントをGKEノードに割り当てます
2. Googleサービスアカウントを使用してWorkloadIdentityでPodを実行します
3. Googleサービスアカウントの資格情報をK8Sシークレットとして保存します
4. GKEロールベースのアクセス制御でGoogleサービスアカウントを使用する
<details><div>
    答え：２
説明
解説：
各種サービスのアクセスには Workload Identityを利用してアクセスすることがベストプラクティスとなっているので、Bが正解となります。
</div></details>

## Q. 5-24
最近、アプリケーションを開発しました。
パブリック IP アドレスを持たない Compute Engine インスタンスから Cloud Storage API を呼び出す必要があります。
どうすればいいでしょうか？
1. キャリアピアリングを使用します
2. VPCネットワークピアリングを使用します
3. 共有VPCネットワークを使用します
4. 限定公開のGoogleアクセスを使用します
<details><div>
    答え：４
説明
Reference：
(1) Virtual Private Cloud
https://cloud.google.com/vpc/docs/private-google-access?hl=ja
(2) 限定公開の Googleアクセス
https://cloud.google.com/vpc/docs/private-google-access?hl=ja
(3) 共有 VPC
https://cloud.google.com/vpc/docs/shared-vpc?hl=ja
(4) VPC ネットワークピアリング
https://cloud.google.com/vpc/docs/vpc-peering?hl=ja
(5) キャリア ピアリングの概要
https://cloud.google.com/network-connectivity/docs/carrier-peering?hl=ja
解説：
AはオンプレミスとGoogleCloudの接続に用いられる方法の１つ、Bは異なるVPCネットワークどうしの接続ですので、まず選択肢か除外できます。
（アプリケーションからCloud Storageを使いたいというごく普通の話ですのでそんな大きな話ではありません）
キャリア ピアリング：
サービス プロバイダ経由で Google Workspace などの Google アプリケーションにアクセスし、エンタープライズ クラスのネットワーク サービスによってインフラストラクチャを Google に接続するためのもの。
VPC ネットワーク ピアリング：
異なる VPC ネットワーク内のワークロードがプライベート（RFC 1918）空間で通信できるように、VPC ネットワークをピアリングするためのものです。
トラフィックは Google のネットワーク内に留まり、公共のインターネットを経由することはありません
Cも異なるプロジェクトでVPCネットワークを共有する話なので、本件とは関連性が無いと考えられます。
共有 VPC：
組織内の複数のプロジェクトから共通の VPC ネットワークにリソースを接続し、そのネットワークの内部 IP を使用して安全で効率的な相互通信を行うためのもの。
消去法的に D と考えられます。
限定公開の Googleアクセスは各サブネットワークで使用できます。
これを有効にすると、外部 IP アドレスがなくても、サブネットワーク内のインスタンスからパブリック Google API エンドポイントと通信できます。
Referenceで上げた公式ドキュメントもご参照ください。
</div></details>

## Q. 5-25
アプリケーション用に「fully baked」または「golden」の Compute Engine イメージを作成する必要があります。
アプリケーションが実行されている環境 (テスト、ステージング、本番) に応じてアプリケーションをブートストラップして適切なデータベースに接続する必要があります。
どうすればいいでしょうか？
1. 適切なデータベース接続文字列をイメージに埋め込み、環境ごとに異なるイメージを作成します
2. ComputeEngineインスタンスを作成するときに接続するデータベースの名前を含むタグを追加します。アプリケーションでComputeEngineAPIにクエリを事項手現在のインスタンスのタグを取得し、そのタグを使用しt適切なデータベース接続文字列を作成します。
3. ComputeEngineインスタンスを作成するときにDATABASEのキーと適切なデータベース接続文字列の値を持つメタデータ項目を作成します。アプリケーションでDATABASE環境変数を読み取り、その値を使用して適切なデータベースに接続します
4. ComputeEngineインスタンスを作成するときにDATABASEのキーと適切なデータベース接続文字列の値を持つメタデータ項目を作成します。アプリケーションでメタデータサーバーにDATABASE値をクエリし、その値を使用して適切なデータベースに接続します
<details><div>
    答え：４
説明
Reference:
(1) VM メタデータにアクセスする
https://cloud.google.com/compute/docs/metadata/querying-metadata?hl=ja
解説：
データベースに接続するためのユーザー名、パスワード、データベース等の情報をソースコードに組み込んだり、実行環境に環境変数やファイルとして保存することはセキュリティー上推奨されません。
実行中にリアルタイムにメタデータサーバーから取得する方法が最も安全で、推奨される方法となります。
従って本問の正解は D となります。
</div></details>

## Q. 5-26
Google Kubernetes Engine (GKE) クラスタ内の顧客に専用のブログソフトウェアをデプロイする SaaS プロバイダがいます。
各顧客が自分のブログにのみアクセスでき、他の顧客のワークロードに影響を与えないように安全なマルチテナントプラットフォームを構成したいと考えています。
どうすればいいでしょうか？
1. GKEクラスタでアプリケーションレイヤのシークレットを有効にしてクラスタを保護します
2. テナントごとに名前空間をデプロイして各ブログのデプロイでネットワークポリシーを使用します
3. GKEAuditLoggingを使用して悪意のあるコンテナを特定し、検出時に削除する
4. ブログソフトウェアのカスタムイメージを構築し、BineryAuthrizationを使用して信頼できないイメージのデプロイを防止します
<details><div>
    答え：２
説明
Reference：
(1) クラスタ マルチテナンシー
https://cloud.google.com/kubernetes-engine/docs/concepts/multitenancy-overview?hl=ja
解説：
選択肢のB.以外は設問の内容とは、かけ離れた内容の記載となっています。
各ユーザーが各ユーザー用の閉じた環境を使い他のユーザーへの影響を与えないということで、B.が問われている内容に最も適切な回答です。
本番以外の環境を構築する際、リソースの節約のために、1つのGKEクラスタを、複数の開発サーバー、テスト用サーバー等にnamespace（名前空間）を利用して、別々のGKEクラスタであるかのように構築して利用する事は良くあることでしょう。
それと同じような事をサービスでも利用していることになります。
何か保護しなければならないような認証情報のようなものの利用が問われているわけではないので、A.は消去。
監査ログに関する設問でもないので、C.は消去。
検証済みイメージのデプロイに関する設問でもないので、D.も消去となります。
</div></details>

## Q. 5-27
チームは Google Kubernetes Engine で実行されるサービスを開発しています。
Google が推奨する手法を使用してログデータを標準化し、最小限の手順でデータをより有用なものにする必要があります。
どうすればいいでしょうか？ (回答は 2 つ)
1. ログ分析を容易にするためにBigQueryへのアプリケーションログの集約エクスポートを作成します
2. ログ分析を容易にするためにCloudStorageへのアプリケーションログの集約エクスポートを作成します
3. ログ出力を単一業のJSONとして標準出力に書き込み、構造化ログとしてCloudLoggingに取り込みます
4. アプリケーションコードでLoggingAPIを使用して構造化されたログをCloudLoggingに書き込むことを義務付けます
5. Pub/SubAPIを使用して構造化データをPub/Subに書き込み、Dataflowストリーミングパイプラインを作成してログを正規化し、分析のためにBigQueryに書き込むことを義務付けます
<details><div>
    答え：1，3
説明
Reference:
(1) GKE ログの管理
https://cloud.google.com/stackdriver/docs/solutions/gke/managing-logs?hl=ja#best_practices
解説：
Reference(1)に記載のベストプラクティスから、A, Cが正解となります。
Loggingから自動的に必要なログをフィルターしてBigQueryに取り込むことができます。

C, DともにLoggingに出力されますが、標準出力への出力の方が「最小限の手順」という条件を満たすと判断します。
実際には開発初期段階で、Logging API への出力関数を作って、ログの出力にそれを使うのも楽な方法ですが、Loggerに直接プログラムからログを出力している場合には、Loggerが使えない環境では標準出力に出力する等の対応が必要です。（コンテナ自体はGKE上でなくても動作させることが出来る為）
最近は、filterしなくても、BigQueryからLoggingのデータにアクセス出来るようですが、Loggingのデフォルトのデータ保持期間が30日と比較的短い
（運営タイトルでユーザーからの質問対応をする上では若干危険な期間ですね）ので、必要なものはBigQueryにエクスポートしておいた方が良いです。
</div></details>

## Q. 5-28
既存の Apache / MySQL / PHP アプリケーション スタックを単一のマシンから Google Kubernetes Engine に移植しています。
アプリケーションをコンテナ化する方法を決定する必要があります。アプローチは可用性に関して Google が推奨するベスト プラクティスに従う必要があります。
どうするべきでしょうか？
1. 各コンポーネントを個別のコンテナにパッケージ化します。実装プロープとライブネスプロープを実装します
2. アプリケーションを単一のコンテナにパッケージ化します。プロセス管理ツールを使用して、各コンポーネントを管理します
3. 各コンポーネントを個別のコンテナにパッケージ化します。スクリプトを使用してコンポーネントの起動を調整します
4. アプリケーションを単一のコンテナにパッケージ化します。コンテナへのエントリポイントとしてbashスクリプトを使用し、各コンポーネントをバックグラウンドジョブとして生成します
<details><div>
    答え：１
説明
Reference：
(1)コンテナ構築のおすすめの方法
https://cloud.google.com/architecture/best-practices-for-building-containers?hl=ja
(2)コンテナ運用のベストプラクティス
https://cloud.google.com/architecture/best-practices-for-operating-containers?hl=ja
解説：
Reference(1)の記載の説明より、A, C のいずれかが正解となります。
Reference (2)の「アプリケーションの状態を公開する」という推奨事項に、livenessProbe, readnessProbeによるヘルスチェックの利用を言及していますので、Aが正解となります。
この辺の知識がないと、A, C の選択は迷うところです。
k8s(kubernetesの事をこう書きます。k+間8文字+s という事です)に関してしっかり学ばれていれば、livenessProbe, readnessProbeは利用しておくべき事の知識は得ていると思います。
</div></details>

## Q. 5-29
会社の開発チームはローカル環境からリソースを管理したいと考えています。
各チームの Google Cloud プロジェクトへのデベロッパー アクセスを有効にするよう依頼されました。
Google が推奨するベスト プラクティスに従って効率を最大化します。
どうすればいいでしょうか？
1. ユーザーをプロジェクトに追加し、関連する役割をユーザーに割り当て、関連する各プロジェクトIDをユーザーに提供します
2. ユーザーをプロジェクトに追加し、関連する役割をユーザーに割り当て、関連する各プロジェクト番号をユーザーに提供します
3. グループを作成し、ユーザーをそのグループに追加し、関連する役割をグループに割り当ててから、関連する各プロジェクトIDをユーザーに提供します
4. グループを作成し、ユーザーをそのグループに追加し、関連する役割をグループに割り当ててから、関連する各プロジェクト番号をユーザーに提供します
<details><div>
    答え：３
説明
解説：
グループを作成し、そのグループに役割を与える事でグループ内のユーザー全員に同じ役割を与えることが出来る為、ある一定のユーザーに同じ役割を与える場合に推奨される方法です（賢い方法ですよね）。
従って、パット見で正解は C, D の２択に絞られます。
開発チームは、特定のプロジェクト（プロジェクト名、プロジェクトIDからなる）内で開発を行いますので、開発場所となるプロジェクトIDを提供（お知らせ）する、という記述内容が適切です。
従って、C が正解です。
</div></details>

## Q. 5-30
クラスタの内部に留まる必要があるさまざまなマイクロサービスを使用してアプリケーションを開発しています。
特定の数のレプリカを使用して各マイクロサービスを構成する機能が必要です。
また、マイクロサービスがスケーリングするレプリカの数に関係なく、他のマイクロサービスから特定のマイクロサービスに一様に対処する機能も必要です。
このソリューションを Google Kubernetes Engine に実装する予定です。
どうすればいいでしょうか？
1. 各マイクロサービスをDeploymentとしてデプロイします。Serviceを使用してクラスタ内のDeploymentを公開し、ServiceのDNS名を使用してクラスタ内の他のマイクロサービスからそれをアドレス指定します
2. 各マイクロサービスをDeploymentとしてデプロイします。Ingressを使用してクラスタ内のDeploymentを公開し、Ingress IPアドレスを使用してクラスタ内の他のマイクロサービスからDeploymentに対処します
3. 各マイクロサービスをPodとしてデプロイします。Serviceを使用してクラスタ内のPodを公開し、ServiceのDNS名を使用してクラスタ内の他のマイクロサービスからそれをアドレス指定します
4. 各マイクロサービスをPodとしてデプロイします。Ingressを使用してクラスタ内のPodを公開し、Ingress IPアドレスを使用してクラスタ内の他のマイクロサービスからPodをアドレス指定します
<details><div>
    答え：1
説明
解説：
Podはkubernetes内のリソースの最小単位ですべてが最終的にはそこに行きつくので「Pod としてデプロイ」という表現にまず違和感を感じましょう。
この時点で私なら、C, Dは除外となります。
Kubernetes上のデプロイ単位となるPodの上位リソースとして、Deployment(ReplicaSet), DeamonSet, StatefulSet, Job, CronJobを抑えておきましょう。
「Deploymentとしてデプロイ」、「DeamonSetとしてデプロイ」というのがしっくりした表現です。
で、A, Bを見ていくと...
スケーリングすると新たなDeploymentにはIPアドレスが付与されますが、それだと他のDeploymentがそのIPアドレスが分かりません。
ということで、Pod間は通常IPアドレス直接指定では通信しません。
サービス名を使って通信します（そしてサービスに紐づく複数のDeploymentへのバランシングをヨロシクやってくれます）。
という事で正解は A となります。
最近の実務では Cloud Run等のマネージドサービスの利用が主流に感じていますが、Google Cloudを勉強する上では GKE を中心に勉強するとそこから全体の知識が集まってくるような感じがしますので、GKEは勉強のし所だと思います。
</div></details>

## Q. 6-1
Google Kubernetes Engine (GKE) で実行されているアプリケーションがあります。
アプリケーションは現在ロギングライブラリを使用しており、標準出力に出力しています。
ログをCloud Logging にエクスポートする必要があり、ログに各リクエストに関するメタデータを含める必要があります。
これを実現するには最も簡単な方法を使用します。
どうすればいいでしょうか？
1. アプリケーションのログライブラリをCloudLoggingライブラリに変更し、ログをCloudLoggingにエクスポートするようにアプリケーションを構成します
2. JSON形式でログを出力するようにアプリケーションを更新し、必要なメタデータをJSONに追加します
3. アプリケーションを更新してログをCSV形式で出力し、必要なメタデータをCSＶに追加します
4. 各GKEノードにFluentBitエージェントをインストールし、エージェントが/var/logからすべてのログをエクスポートするようにします
<details><div>
    答え：1
説明
Reference:
(1) GKE ログの管理
https://cloud.google.com/stackdriver/docs/solutions/gke/managing-logs?hl=ja#best_practices
説明
不正解
B. 
ロギングにJSONを使用するとメタデータを含めることができますが、このアプローチでは、アプリケーションの既存のロギング・コードに、より広範な変更が必要になる可能性が高いです。
C. 
CSVは構造化されたロギングの典型的な形式ではなく、Cloud Loggingとうまく適合しないため、この方法はさらに面倒になります。
D. 
この方法は、追加の設定とメンテナンスが必要になる可能性があり、要件を満たすための最も簡単な方法ではありません。Fluent Bit はログプロセッサーとフォワーダーであり、それを使用することは、このシナリオでは不必要な複雑さを伴うかもしれません。
正解
A. このオプションは Cloud Logging と直接統合し、各リクエストに関するメタデータを含めることを可能にします。Cloud Logging ライブラリは Google Cloud サービスとシームレスに動作するように設計されているため、GKE アプリケーションからログをエクスポートするための論理的でシンプルな選択肢となります。
誤り解説：
Reference (1)の記述と、「もっとも簡単な方法」とメタデータの出力に言及している事からB を正解とします。
A はソースコードの変更が大きいと考え「最も簡単な方法」には反していると考えられます。
※CloudRunの場合は標準出力に書き出すと良いが、今回はGKEなので素直にライブラリに頼る方がよさそう
ログデーターはJson形式なので、Cは除外。
D は回りくどくこのような方法を取る必要がありません。
一般に Fluent は AWSやAZURE等の別なクラウドを使っているがログ解析だけはBigQueryで行いたいといった場合にログを集めてloggingに出力する等を行いますが、Google Cloud 環境では直接 Cloud Loggingに出力できるので、あまり必要性はないのではないかと思われます。
正解は B となります。
</div></details>

## Q. 6-2
アプリケーションが Google Kubernetes Engine（GKE）クラスタのコンテナとして実行されています。
Kubernetes API サーバーへの呼び出しによって Secret が公開されることを防ぐ、安全なアプローチを使用して、アプリケーションに Secret を追加する必要があります。
どうすればよいですか。
1. kubernetesシークレットを作成し、そのシークレットを環境変数としてコンテナに渡す
2. CloudKeyManagementServiceを使用して、GKEアプリケーションレイヤのシークレットの暗号化をクラスタで有効にする
3. CloudKMSにシークレットを格納する。CloudKMSからシークレットを読み取るためにGoogleサービスアカウントを作成する。サービスアカウントキーをJSON形式でエクスポートしてそのJSONファイルをCloudKMSからシークレットを読み取ることができるConfigMapVolumeとしてコンテナにマウントする
4. シークレットをSercretManagerに格納する。SercretManagerからシークレットを読み取るためのGoogleサービスアカウントを作成する。コンテナを実行するためのK8sサービスアカウントを作成する。WorkloadIdentityを使用してGoogleサービスアカウントとして認証する
<details><div>
    答え：４
説明
Reference:
(1) Workload Identity を使用する
https://cloud.google.com/kubernetes-engine/docs/how-to/workload-identity?hl=ja
(2) Cloud Key Management Service のドキュメント
https://cloud.google.com/kms/docs?hl=ja
(3) Secret
https://kubernetes.io/docs/concepts/configuration/secret/
(4) Secret Manager のコンセプトの概要
https://cloud.google.com/secret-manager/docs/overview?hl=ja
解説：
A は不正解です。
Kubernetes Secret は文字列をエンコードするのみであるため、Secret を読み取ることができる誰もがそれをデコードできます。
B は不正解です。
GKE アプリケーションレイヤで Secret を暗号化しても、Secret はやはり Kubernetes API サーバーからの base64 エンコードされた文字列として提示されます。
C は不正解です。
Cloud KMS は実際の Secret ではなく暗号鍵の格納に使用されます。また、Google サービス アカウント キーを Volume として渡すとしていますが、Secret を読み取ることができる誰もがこれを読み取ることができます。
D は正解です。
これにより、Secret を安全に格納するサービスと、Workload Identity で安全に Secret を取得するアプローチが提供されます。
</div></details>

## Q. 6-3
プロジェクト A とプロジェクト B という 2 つの Google Cloud プロジェクトがあります。
プロジェクト B の Cloud Storage バケットに出力を保存する Cloud Functions をプロジェクト A に作成する必要があります。
最小権限の原則に従う必要があります。
どうすればいいでしょうか？
1. プロジェクトBにGoogleサービスアカウントを作成します。このサービスアカウントにプロジェクトBにあるストレージバケットに対するroles/storage.objectcreaterのロールを割り当てます。プロジェクトBのサービスアカウントでプロジェクトAにFunctionsをデプロイします。
2. プロジェクトAでGoogleサービスアカウントを作成します。このサービスアカウントにプロジェクトBにあるストレージバケットに対するroles/storage.objectcreaterのロールを割り当てます。プロジェクトAのサービスアカウントでFunctionsをデプロイします。
3. プロジェクトAのデフォルトのAppEngineサービスアカウントを決定します。プロジェクトAでデフォルトのAppEngineサービスアカウントを使用してFunctionsをデプロイします。デフォルトのAppEngineサービスアカウントにプロジェクトBにあるストレージバケットのroles/storage.objectcreaterのロールを割り当てます
4. プロジェクトBのデフォルトのAppEngineサービスアカウントを決定します。プロジェクトAでデフォルトのAppEngineサービスアカウントを使用してFunctionsをデプロイします。デフォルトのAppEngineサービスアカウントにプロジェクトBにあるストレージバケットのroles/storage.objectcreaterのロールを割り当てます
<details><div>
    答え：２
説明
Reference:
(1) サービス アカウントの概要
https://cloud.google.com/iam/docs/service-account-overview?hl=ja
(2) Cloud Storage に適用される IAM のロール
https://cloud.google.com/storage/docs/access-control/iam-roles?hl=ja
(3) 最小限の権限
https://cloud.google.com/iam/docs/using-iam-securely?hl=ja#least_privilege
解説：
プロジェクトAのCloud FunctionsはプロジェクトAのサービスアカウントで作成します。
プロジェクトAで作成したサービスアカウントにロールを追加することで、プロジェクトAのサービスアカウントで作られたCloud Functions にもロールが追加されます。
このサービスアカウントにプロジェクトBのCloud Storageに書き込みが行える最低限のロールがあればいいわけです。
これを踏まえて見ていくと。
異なる Google Cloud プロジェクトにあるサービス アカウントで Cloud Functions の関数を実行することはできませんので A は不正解です。
BはプロジェクトAで作成したサービス アカウントにプロジェクトBのCloud Storage のroles/storage.objectCreator ロールが付与されたので、FunctionsはStorageの objectCreatorになれました。
C, DはAppEngineのサービスアカウントに何やらやっているので無関係です。
正解は B となります。
</div></details>

## Q. 6-4
ローカルテストでは問題がなく、Compute Engine インスタンスにデプロイするとパフォーマンスが大幅に低下するアプリケーションがあります。
変更は最小限にして問題を診断する必要があります。どうすればよいですか。
1. Cloudサポートにチケットを提出し、アプリケーションがローカルでは高速に動作することを説明する
2. Cloudデバッガのスナップショットを使用して、特定時点でのアプリケーション野実行を確認する
3. CloudProfilerを使用して、アプリケーションのどの関数に最も時間がかかっているのかを判断する
4. アプリケーションにロギングコマンドを追加し、CloudLoggingを使用して、レイテンシの問題がどこで発生しているのかを確認する
<details><div>
    答え：３
説明
Reference:
(1) Cloud Profiler のドキュメント
https://cloud.google.com/profiler/docs?hl=ja
解説：
A は不正解です。
自分のマシンでは動作したのに Google Cloud では動作しないと主張しても有用性はありません。
B は不正解です。
デバッガのスナップショットでは、ある時点のアプリケーションの状況を確認できるのみです。
C は正解です。
関数ごとのレイテンシと、レイテンシの履歴情報が提供されます。
D は不正解です。
有効ではありますが、必要な作業量が多くなり、明確で最適な選択肢ではありません。
</div></details>

## Q. 6-5
API呼び出し元の認証、過剰なリクエストの制御、メトリックのレポートを行うパブリックAPI を構築する必要があります。
このアーキテクチャを完成させるにはどのツールを使用しますか？
1. AppEngine
2. CloudEndpoints
3. Identity-AwareProxy
4. HTTP負荷分散のためのGKEIngress
<details><div>
    答え：2
説明
Reference:
(1) Cloud Endpoints
https://cloud.google.com/endpoints?hl=ja
(2) 割り当てについて
https://cloud.google.com/endpoints/docs/openapi/quotas-overview?hl=ja
解説：
「API呼び出し元の認証、過剰なリクエストの制御、メトリックのレポートを行う」を満たすのは Cloud Endpoints です。
これら3つの機能（認証、割り当て / レート制限、指標）はすべて、Cloud Endpoints のコア機能です。
(Reference参照)
AはApp Engineはアプリケーションの実行環境ですので、通常要求されているような機能を行うことはありません。
Cは認証機能しか持ちません。
Ingressは選択肢にも書いているように分散機能があります。
主な役割は外部URLをクラスタ内のURLに変換しL7ロードバランシングを提供します。
SSL認証などは行いますが要求されているような機能は持ちません。
正解は B となります。
</div></details>

## Q. 6-6
あなたのチームが管理しているウェブ アプリケーションは、現在、ユーザー セッションの情報をオンプレミスの PostgreSQL データベースに保存しています。
このデータベースをオンプレミスに残して、ウェブ アプリケーションを Google Cloud に移行することになりました。
移行後に高いレイテンシが検出されたため、クイックテストを何件か実施してデータポイントを収集し、パフォーマンスを改善する費用対効果の高い解決策をテクニカル リーダーに提案する必要があります。
まず、スキーマを変更せずにデータベースを Google Cloud に移行して、レイテンシが低減されるかを確認します。
次に、PostgreSQLの代わりにクラウド上のマネージド NoSQL データベースを使用してユーザーセッションの情報を保存します。
マネージドサービスを使用して効率的にデータポイントを収集するにはどうすればよいですか。
1. データベースをCloudSQLに移行し、データをCloudStorageにインポートする
2. データベースをBigQueryに移行し、データをネイティブモードのFilestoreにインポートする
3. データベースをCloudSQLに移行し、データをネイティブモードのFilestoreにインポートする
4. GoogleCloudでComputeEngineインスタンスを作成して、PostgreSQLとMongoDBのサーバーソフトウェアをインストールし、データベースをPostgreSQLに、データをMongoDBにそれぞれ移行する
<details><div>
    答え：3
説明
Reference:
(1) Bigtable の概要
https://cloud.google.com/bigtable/docs/overview?hl=ja
(2) Firestore エクスポートからのデータの読み込み
https://cloud.google.com/bigquery/docs/loading-data-cloud-firestore?hl=ja
(3) オンプレミスの PostgreSQL クラスタを Google Cloud に移行する
https://cloud.google.com/architecture/migrating-postgresql-to-gcp?hl=ja
解説：
A は不正解です。
Cloud Storage は、ユーザー セッション情報の保存に効果的な NoSQL データベースではありません。
B は不正解です。
BigQuery は、データ ウェアハウスです。挿入された行を更新 / 削除する機能が限定的であるため、セッションの進行状況に応じて変化するユーザー セッション データには不適切です。
C は正解です。
Cloud SQL はマネージド PostgreSQL データベースで、移行時にスキーマの変更は不要です。
ネイティブ モードの Firestore は、ユーザー セッション情報の保存用途に推奨されており、こうしたテストに最適です。
D は不正解です。
マネージド サービスが使用されておらず、データベース サーバーの管理が必要になるため、テストにかかる時間が増加します。
</div></details>

## Q. 6-7
Cloud Run を使用して新しい Web アプリケーションを開発し、コードを Cloud Source Repositories にコミットしています。
可能な限り最も効率的な方法で新しいコードをデプロイしたいと考えています。
コンテナをビルドしてコマンド gcloud run deploy を実行する Cloud Build の YAML ファイルをすでに作成しています。
次に何をすべきですか？
1. コードがリポジトリにプッシュされたときに通知されるようにPub/Subトピックを作成します。イベントがトピックに発行されたときにビルドファイルを実行するPub/Subトリガーを作成します
2. 開発ブランチにプッシュされるリポジトリコードに応答してビルドファイルを実行するビルドトリガーを作成します
3. WebhookURLへのHTTPPOST呼び出しに応答してビルドファイルを実行するWebhookビルドトリガーを作成します
4. 次のコマンドを24時間ごとに実行するcronジョブを作成します
<details><div>
    答え：2
説明
解説：
Cloud Build を使うことで、Cloud Source Repositories(CSR)へのコミットやタグの作成等のフックで、作成した yaml ファイルを実行する事が簡単に行うことができます。
本問題での要求であれば、A, C のような回りくどい仕組み(Cloud Build 以外にも他のtoolを利用するような仕組み)の作成は不要です。
Cronジョブも特定の時間にならないと実行されないので非効率です。
ソースの更新をフックしてすぐにビルドスクリプトを実行できます。
従って、正解は B となります。
</div></details>

## Q. 6-8
Deployment リソースを使用して新しいアプリケーションリビジョンを本番環境の Google Kubernetes Engine (GKE) にデプロイする予定です。
コンテナが正しく機能しない可能性があります。
リビジョンのデプロイ後に問題が発生した場合のリスクを最小限に抑える必要があります。
Google が推奨するベストプラクティスに従います。
どうすればいいでしょうか？
1. 80%のPodDisruptionBudgetでローリングアップデートを実行します
2. HorizontalPodAutoscalerスケールダウンポリシーの値を0にし、ローリングアップデートを実行します
3. DeploymentをStatfulsetに変換し、80%のPodDisruptionBudgetでローリングアップデートを実行します
4. DeploymentをStatfulsetnに変更し、HorizontalPodAutoscalerスケールダウンポリシーの値を0にしてローリングアップデートを実行します
<details><div>
    答え：1
説明
Reference:
(1) ローリングアップデートの実行
https://kubernetes.io/ja/docs/tutorials/kubernetes-basics/update/update-intro/
(2) PodDisruptionBudgets を使用して Kubernetes クラスターの停止を回避する方法
https://blog.knoldus.com/how-to-avoid-outages-in-your-kubernetes-cluster-using-pdb/
(3) GKE best practices: Day 2 operations for business continuity
https://cloud.google.com/blog/products/containers-kubernetes/ensuring-reliability-and-uptime-for-your-gke-cluster
解説：
特に Deployment を Stateful にする必要性はないので、C, D は選択肢から除外できます。
StatefulSetの特徴としては、
(1) 作成される Pod 名のサフィックスは数字のインデックスが付与されたものになる
sample-statefulset-0、sample-statefulset-1、...、sample-statefulset-N
(2) Pod 名が変わらない
(3) データを永続化するための仕組みを有している
というもので、問題で述べられている更新で、これらの特徴が必要である必要性がありません。
講師の実務経験では、Redisを複数のPodとして構成した際にPod名が変わらなかったり、データの永続性の特徴の為に StatefulSetのPodを利用したことがあります。
A, Bを見ていきましょう。
PodDisruptionBudget(RDB)を80%に設定したローリングアップデートは、GKEの本番環境に新しいリビジョンをデプロイした後の問題のリスクを最小化するのに役立ちます。
PDB は、アップデート中に利用可能な状態を維持する必要がある配備のポッド数を指定し、トラフィックや需要の増加に対処するための十分な容量を確保します。
PDB を 80% に設定することで、アップデート中に少なくとも 80% のポッドが利用できるようになり、アプリケーションに障害が発生するリスクを軽減することができます。
Aが正解のようです。
B はスケールダウンのポリシーの設定を行っており、アップデートの戦略には関係のない設定です。
従って本問題の正解は A となります。
</div></details>

## Q. 6-9
チームは Cloud Functions コードの単体テストを開発しています。
コードは Cloud Source Repositories リポジトリに保存されます。
テストの実施は顧客の責任です。
コードを Cloud Functions にデプロイするために必要な権限を持っているのは特定のサービス アカウントだけです。
最初にテストに合格しないとコードをデプロイできないようにする必要があります。
単体テスト プロセスをどのように構成する必要がありますか？
1. CloudBuildを構成してCloudFunstionsをデプロイします。コードがテストに合格すると、デプロイの承認が送信されます
2. 特定のサービスアカウントをビルドエージェントとして使用してCloudFunstionsをデプロイするようにCloudBuildを構成します。デプロイが成功したら単体テストを実行します
3. CloudBuildを構成して単体テストを実行します。コードがテストに合格すると開発者はCloudFunstionsをデプロイします
4. 特定のサービスアカウントをビルドエージェントとして使用して単体テストを実行するようにCloudBuildを構成します。コードがテストに合格するとCloudBuildはCloudFunstionsをデプロイします
<details><div>
    答え：4
説明
解説：
A, Bは単体テストとデプロイの順番が逆なので除外です。
Cは自動化されていないので、Dに劣ります。
Dは全てが自動化されています。正解は D となります。
</div></details>

## Q. 6-10
Cloud Shell から kubectl を使用して Google Kubernetes Engine (GKE) クラスタに接続しようとしています。
パブリック エンドポイントを使用して GKE クラスタをデプロイしました。
Cloud Shell から次のコマンドを実行します。
gcloud container clusters get-credentials <cluster-name> ---zone <none> --project <project-name>
kubectlコマンドがエラーメッセージを返さずにタイムアウトすることに気付きました。
この問題の最も可能性の高い原因は何でしょうか？
1. ユーザーアカウントにはkubectlを使用してクラスタとやり取りする権限がありません
2. CloudShellの外部IPアドレスはクラスタの承認済ネットワークの一部ではありません
3. CloudShellはGKEクラスタと同じVPCの一部ではありません
4. VPCファイアウォールがクラスタのエンドポイントへのアクセスをブロックしている
<details><div>
    答え：2
説明
Reference:
(1) トラブルシューティング(GKE)
https://cloud.google.com/kubernetes-engine/docs/troubleshooting?hl=ja#connection_refused
(2) 限定公開クラスタの作成
https://cloud.google.com/kubernetes-engine/docs/how-to/private-clusters?hl=ja#cloud_shell
解説：
Aの場合は「権限がない」というエラーがかえってくるでしょう。
現象として通信がブロックされてGKEクラスタに到達していないようです。
同一VPC内での話となるので、C, Dは除外できます。
このエラーの原因として考えられるのは、B です。
</div></details>

## Q. 6-11
それぞれの Cloud Storage バケット内のユーザーオブジェクトのメタデータ内の特定のプロパティを取得する必要がある新しい公開アプリケーションを開発しています。
プライバシーとデータレジデンシーの要件により、オブジェクトデータではなく、メタデータのみを取得する必要があります。
取得プロセスのパフォーマンスを最大化する必要があります。
どのようにメタデータを取得しますか？
1. バッチ方式を使用します
2. compose方式を使用します
3. コピー方式を使用します
4. fieldsリクエストパラメータを使用します
<details><div>
    答え：4
説明
Reference:
(1)バケットのサイズとメタデータを取得する
https://cloud.google.com/storage/docs/getting-bucket-size-and-metadata?hl=ja
解説：
Reference (1)で示した資料から D が正解です。
(REST API例)
curl -X GET -H "Authorization: Bearer OAUTH2_TOKEN" "https://storage.googleapis.com/storage/v1/b/BUCKET_NAME?fields=location%2CstorageClass"
(結果例)
{
  "location": "US",
  "storageClass": "STANDARD"
}
</div></details>

## Q. 6-12
分散マイクロサービス アーキテクチャを使用するアプリケーションを構築しています。
Java で記述されたマイクロサービスの 1つでパフォーマンスとシステムリソースの使用率を測定したいと考えています。
どうすればいいでしょうか？
1. CloudProfilerを使用してサービスを計測し、サービスのCPU使用率とメソッドレベルでの実行時間を測定します
2. Debuggerを使用してサービスを計測し、サービスエラーを調査します
3. CloudTraceを使用してサービスを計測し、リクエストのレイテンシを測定します
4. OpenCensusを使用してサービスを計測し、サービスレイテンシを測定し、カスタム指標をCloudMonitoringに書き込みます
<details><div>
    答え：１
説明
Reference:
(1) Cloud Trace
https://cloud.google.com/trace?hl=ja
(2) Cloud Profiler の概要
https://cloud.google.com/profiler/docs/about-profiler?hl=ja
(3) 分散トレースを使用して OpenCensus と Cloud Trace でマイクロサービスのレイテンシを監視する
https://cloud.google.com/architecture/using-distributed-tracing-to-observe-microservice-latency-with-opencensus-and-stackdriver-trace?hl=ja
解説：
OpenCensusはサービスメッシュ全体のトレースと指標を収集できるツールですが、ここでは
「マイクロサービスの 1つでパフォーマンスと・・・」ということなので、これを使う必要はないでしょう。
パフォーマンスに関する事なので、Profilerか Traceになります。
Traceはレイテンシーの測定分析を行うのに使用します。
ProfilerではCPU使用率、ヒープメモリーの使用率、スレッド数、経過時間等のリソースの使用率やパフォーマンスが測定できます。
ということで正解は A となります。
</div></details>

## Q. 6-13
静的コンテンツをユーザーに提供する高可用性でグローバルにアクセス可能なアプリケーションを構築しています。
ストレージとサービスコンポーネントを構成する必要があります。
ユーザーの信頼性を最大限に高めながら管理のオーバーヘッドと待ち時間を最小限に抑える必要があります。
どうすればいいでしょうか？
1. マネージドインスタンスグループを作成し、VM間で静的コンテンツをレプリケートします。外部ロードバランサを作成します。CloudCDNを有効にし、マネージドインスタンスグループにトラフィックを送信します
2. 非マネージドインスタンスグループを作成し、VM間で静的コンテンツをレプリケートします。外部ロードバランサを作成します。CloudCDNを有効にし、非マネージドインスタンスグループにトラフィックを送信します
3. StandardストレージクラスのリージョンCloudStorageバケットを作成します。静的コンテンツをバケットに入れます。外部IPアドレスを予約し、外部ロードバランサを作成します。CloudCDNを有効にし、トラフィックをバックエンドバケットに送信します
4. StandardストレージクラスのマルチリージョンCloudStorageバケットを作成します。静的コンテンツをバケットに入れます。外部IPアドレスを予約し、外部ロードバランサを作成します。CloudCDNを有効にし、トラフィックをバックエンドバケットに送信します
<details><div>
    答え：4
説明
Reference:
(1) Cloud CDN の概要
https://cloud.google.com/cdn/docs/overview?hl=ja
解説：
静的サービスなので、データが配信出来ればＯＫですので、C, Dに絞られます。
「グローバルにアクセス可能なアプリケーション」「オーバーヘッドと待ち時間を最小限に抑える」
という事で、正解は D となります。
Cloud CDNにデータがまだキャッシュされていない場合、オリジンサーバーであるCloud Storageからデータを取得してキャッシュします。
その際に、Cloud Storageがマルチリージョンの方が低レイテンシーとなります。
アクセス元に近いCDNが同じくそのCDNに近い Cloud Storageからデータを取得することができます。
これが C と D の違いです。
（静的サービスの内容が完全にCDNにキャッシュされた状態では、CとDに差は出ません。）
</div></details>

## Q. 6-14
最近、オンプレミスのモノリシック アプリケーションを Google Kubernetes Engine (GKE) のマイクロサービスアプリケーションに移行しました。
このアプリケーションは CRM システムや個人を特定できる情報 (PII) を含む MySQLデータベースなど、オンプレミスのバックエンドサービスに依存しています。
バックエンドサービスは規制要件を満たすためにオンプレミスのままにしておく必要があります。
オンプレミスデータセンターと GCPの間に Cloud VPN 接続を確立しました。
GKE上のマイクロサービスアプリケーションからバックエンドサービスへの一部のリクエストが帯域幅の変動によるレイテンシの問題が原因で失敗し、アプリケーションがクラッシュしていることに気付きました。
レイテンシの問題にどのように対処しますか？
1. Memorystoreを使用し、頻繫にアクセスされるPIIデータをオンプレミスのMySQLデータベースからキャッシュします
2. Istioを使用し、GKE上のマイクロサービスとオンプレミスサービスを含むサービスメッシュを作成します
3. GoogleCloudとオンプレミス間の接続用にCloudVPNトンネルの数を増やします
4. CloudVPNのデフォルト値から最大転送単位の値を減らし、ネットワーク層のパケットサイズを減らします
<details><div>
    答え：3
説明
解説：
Aは有効な場合もありますが、全てのデーターがキャッシュ可能かどうか分かりません。
Bはもともとオンプレミスのバックエンドと通信するマイクロサービスは限られていると考えられるので解決にはつながらないと思います。
Cは単純に帯域幅が増える解決策なので有効です。
Dは逆にレイテンシーがさらに悪くなる可能性があります。
従って、本問の正解は C となります。
</div></details>

## Q. 6-15
Google Kubernetes Engine クラスタで実行される複数のマイクロサービスで構成されるアプリケーションを開発しています。
1つのマイクロサービスはオンプレミスで実行されているサードパーティデータベースに接続する必要があります。
資格情報をデータベースに保存し、セキュリティのベストプラクティスに従ってこれらの資格情報をローテーションできるようにする必要があります。
どうすればいいでしょうか？
1. 認証情報をサイドカーコンテナプロキシに保存し、それを使用してサードパーティデータベースに接続します
2. サービスメッシュを構成し、マイクロサービスのPodからデータベースへのトラフィックを許可または制限します
3. 認証情報を暗号化されたボリュームマウントに保存し、PersistentVolumeClaimをクライアントPodに関連付けます
4. 資格情報をK8Sシークレットとして保存し、CloudKMSプラグインを使用して暗号化と復号化を処理します
<details><div>
    答え：4
説明
Reference:
(1) アプリケーション レイヤで Secret を暗号化する
https://cloud.google.com/kubernetes-engine/docs/how-to/encrypting-secrets?hl=ja#reencrypt-secrets
解説：
A, Cは例え暗号化されているにしても（Aに至ってはその記述もありません）簡単にアクセス出来る状態は避けたいです。
B.は、トラフィックの許可、制限に関する内容になっていますので、アクセス資格とは無関係な内容となっています。
という事で、正解は D です。
Dの記述内容にも問題はありません。
</div></details>

## Q. 6-16
階層データ構造をデータベースに格納するモバイルアプリケーションを構築しています。
このアプリケーションにより、オフラインで作業しているユーザーはオンラインに戻ったときに変更を同期できます。
バックエンド サービスは、サービス アカウントを使用してデータベース内のデータを強化します。
このアプリケーションは非常に人気があると予想され、シームレスかつ安全にスケーリングする必要があります。
どのデータベースと IAM ロールを使用しますか？
1. CloudSQLを使用してroles/cloudsql.edoterロールをサービスアカウントに割り当てます
2. CloudBigtableを使用し、roles/bigtable.viwerロールをサービスアカウントに割り当てます
3. Firestoreをネイティブモードで使用し、roles/datastore.userロールをサービスアカウントに割り当てます
4. FirestoreをDatastoreモードで使用し、roles/datastore.viwerロールをサービスアカウントに割り当てます
<details><div>
    答え：3
説明
Reference:
(1) Firestore を使用したスケーラブルなアプリケーションの構築
https://cloud.google.com/architecture/building-scalable-apps-with-cloud-firestore?hl=ja
解説：
「安全にスケーリングする必要があります」という事からまずはスケーリングに強いリソースを見ます。
この点では A だけ除外できます（もっと削れると良かったですが）。
残りは大容量かつスケールに強い製品なので、ゲームで起こりがちな急激なスパイクには耐えられます。
B, Cのロールが viewerなので書き込みが出来ないことが分かるので、C が正解です。
</div></details>

## Q. 6-17
Knative で実行されているオンプレミス コンテナを Google Cloud に移行したいと考えています。
移行がアプリケーションのデプロイ戦略に影響を与えないようにする必要があり、マネージドサービスを使用したいと考えています。
コンテナをデプロイするには、どの Google Cloud サービスを使用しますか？
1. CloudRun
2. ComputeEngine
3. GKE
4. AppEngine
<details><div>
    答え：1
説明
Reference:
(1) マネージド Knative サービスの Cloud Run を一般提供開始
https://cloud.google.com/blog/ja/products/serverless/knative-based-cloud-run-services-are-ga/
(2) サーバーレス
https://cloud.google.com/serverless?hl=ja
(3) App Engine 環境を選択する
https://cloud.google.com/appengine/docs/the-appengine-environments?hl=ja
(4) Knative
https://cloud.google.com/knative?hl=ja
(5) Google Kubernetes Engine と Cloud Run: どちらを使用する必要がありますか?
https://cloud.google.com/blog/products/containers-kubernetes/when-to-use-google-kubernetes-engine-vs-cloud-run-for-containers
解説：
「マネージドサービスを使用」ということで、A, D の２択となります。
App Engine フレキシブル環境ではコンテナを実行できるものの、アプリケーションのデプロイ戦略に重大な変更を加えることが必要になります。
マネージドKnative サービスが Cloud Run ですので、A が正解となります。
</div></details>

## Q. 6-18
あなたの会社のプロダクトチームでは、Google Kubernetes Engine（GKE）クラスタで稼働しているステートレスな分散型サービスを自動でスケーリングしてほしいという依頼をお客様から受けています。
この機能を 2週間以内にリリースするために、最小限の変更で実現できるソリューションを求めています。
どうすればよいですか。
1. 垂直Pod自動スケーリングをデプロイし、CPU負荷に基づいてスケーリングします
2. 垂直Pod自動スケーリングをデプロイし、カスタム指標に基づいてスケーリングします
3. 水平Pod自動スケーリングをデプロイし、CPU負荷に基づいてスケーリングします
4. 水平Pod自動スケーリングをデプロイし、カスタム指標に基づいてスケーリングします
<details><div>
    答え：3
説明
Reference:
(1) コンテナ リソースのリクエストと制限のスケール
https://cloud.google.com/kubernetes-engine/docs/how-to/vertical-pod-autoscaling?hl=ja
(2) 垂直 Pod 自動スケーリング
https://cloud.google.com/kubernetes-engine/docs/concepts/verticalpodautoscaler?hl=ja
(3) 指標に基づいて Pod の自動スケーリングを最適化する
https://cloud.google.com/kubernetes-engine/docs/tutorials/autoscaling-metrics?hl=ja
解説：
分散サービスとの記載より、負荷に応じて分散度合いをスケールする事になるので、ここでのスケールは水平分割と判断できるため、C, D の２択となります。
カスタム指標の必要性が分かりません。
Podの数が増えれば、それぞれがCPUを消費する為、Podの増加につれて、CPU負荷が上がり、一定水準を越えた場合、ノードのスケールアップが必要となります。
CPU負荷に基づいたスケーリングは最低限必要です。
Cの方法により最小限のコード変更で要件を満たすことができます。
Dの方法は機能しますが、Cloud Monitoring のインテグレーションと、場合によってはアプリケーションの変更が必要になります。
従って本問題の正解は C であることが分かります。
</div></details>

## Q. 6-19
会社の開発チームは Docker ビルドでさまざまなオープン ソース オペレーティング システムを使用したいと考えています。
会社の環境で公開されたコンテナでイメージが作成された場合、それらをスキャンして Common Vulnerabilities and Exposures (CVE) を探す必要があります。
スキャン プロセスがソフトウェア開発の俊敏性に影響を与えてはなりません。
可能な限りマネージド サービスを使用したいと考えています。
どうすればいいでしょうか？
1. ContainerRegistryで脆弱性スキャン設定を有効にします
2. コードのチェックインでトリガーされるCloudFunctionsを作成し、CVEのコードをスキャンします
3. 開発環境で非商用ベースイメージの使用を禁止します
4. CloudMonitoringを使用してCloudbuildの出力を確認し、脆弱なバージョンが使用されているかどうかを判断
します
<details><div>
    答え：1
説明
解説：
Container Registry (Artifact Registry)に脆弱性スキャンの機能があるので、これを有効にすればOKです。
他の選択肢にあるような余計な処理を行う必要はありません。
正解は A となります。
</div></details>

## Q. 6-20
一部のアプリケーションを Google Cloud に移行しました。
オンプレミスとクラウドにデプロイされたアプリケーションの両方にオンプレミスにデプロイされた従来の監視プラットフォームを使用しています。
クラウドアプリケーションのタイムクリティカルな問題に対する通知システムの応答が遅いことがわかりました。
どうすればいいでしょうか？
1. モニタリングプラットフォームをCloudMonitoringに置き換えます
2. ComputeEngineインスタンスにCloudMonitoringエージェントをインストールします
3. 一部のトラフィックを古いプラットフォームに戻します。2つのプラットフォームで同時にA/Bテストを実行します
4. CloudLoggingとCloudMonitoringを使用してログを取得して監視し、アラートを送信します。それらを既存のプラットフォームに送信します
<details><div>
    答え：4
説明
不正解
A. Stackdriverは強力な監視とロギングのソリューションですが、既存の監視プラットフォーム全体を置き換えるのは大変な作業です。通知が遅いという特定の問題を解決するには、このオプションはやり過ぎかもしれません。
正解
C. Stackdriver（現在はCloud Monitoring and Cloud Loggingとして知られている）を利用することで、タイムクリティカルな問題に対してGoogle Cloudのアラート機能を利用することができます。こうすることで、既存の監視プラットフォームと統合しながら、迅速な通知というメリットを得ることができます。Stackdriverで特定のアラート条件を設定し、必要に応じてログとメトリクスを既存のシステムに転送できます。オプションCでは、Google Cloudのアラート機能を活用しながら、既存の監視プラットフォームの部分を残すことができます。
リンク
https://cloud.google.com/monitoring/alerts/concepts-indepth#notification-latency
誤り説明
解説：
A. 全体を Cloud Monitoring に置き換えることは、通知システムの応答の改善につながります。
B. 特に「Compute Engine インスタンス」を使っているとの記載はありませんので誤りです。
C. 「通知システムの応答が遅い」事の解決を説明する内容になっていません。
D. 既存のプラットフォームを使い続けている点で全体的な問題の改善となるかは不明です。
Cloud Logging も通常はアラート指標には関与しません。
正解は A です。
</div></details>

## Q. 6-21
チームは Google Cloud で実行されるサービスを開発しています。
データ処理サービスを構築する必要があり、Cloud Functions を使用します。
関数によって処理されるデータは機密情報です。
呼び出しが許可されたサービスからのみ行われるようにし、機能を保護するために Google が推奨するベストプラクティスに従う必要があります。
どうすればいいでしょうか？
1. プロジェクトでIdentity-AwareProxyを有効にし、権限を使用しいて機能アクセスを保護します
2. Functionsビューアーの役割を持つサービスアカウントを作成し、そのサービスアカウントを使用して関数を呼び出します
3. FunctionsInvokerロールを盛るサービスアカウントを作成し、そのサービスアカウントを使用して関数を呼び出します
4. 保護する関数と同じプロジェクトで呼び出し元サービスのOAuth2.0クライアントIDを作成し、これらの資格情報を使用して関数を呼び出します
<details><div>
    答え：3
説明
Reference：
(1) How to securely invoke a Cloud Functions from Google Kubernetes Engine running on another GCP project
https://medium.com/google-cloud/how-to-securely-invoke-a-cloud-function-from-google-kubernetes-engine-running-on-another-gcp-79797ec2b2c6
解説：
許可されたサービスからの呼び出しに対する許可であり、ユーザー認証は必要ないのでA, Dは選択肢から外れます。
データ処理を行うので B のビューアー権限では役割不足と考えられるので B も選択肢から外れ、結果 C が正解と判断できます。
C の記述自体にも特に問題はありません。
これでＯＫです。
</div></details>

## Q. 6-22
新しいアプリケーションを Google Kubernetes Engine にデプロイしましたがパフォーマンスが低下しています。
ログは Cloud Logging に書き込まれ、Prometheus サイドカーモデルを使用して指標を取得しています。
ログからのメトリックとデータを関連付けてパフォーマンスの問題をトラブルシューティングし、コストを最小限に抑えながらリアルタイムのアラートを送信する必要があります。
どうすればいいでしょうか？
1. CloudLoggingログからカスタム指標を作成し、Promethusを使用して、CloudMonitoringRESTAPIを使用して結果をインポートします
2. CloudLoggingのログとPromethus指標をCloudBigtableにエクスポートします。クエリを実行して結果を結合し、Googleデータポータルで分析します
3. Loggingのログをエクスポートし、Promethus指標をBigQueryにストリーミングします。繰り返しクエリを実行して結果を結合し、CloudTasksを使用して通知を送信します
4. Promethus指標ををエクスポートし、CloudMonitoringを使用してそれらを外部指標として表示します。CloudMonitoringを構成してログからログベースの指標を作成し、それらをPromethusデータと関連付けます
<details><div>
    答え：4
説明
Reference：
(1) Cloud Logging のモニタリング データによる GKE アプリのトラブルシューティング迅速化
  https://cloud.google.com/blog/ja/products/operations/troubleshoot-gke-faster-with-monitoring-data-in-your-logs
(2) Prometheus 指標の使用
  https://cloud.google.com/stackdriver/docs/solutions/slo-monitoring/sli-metrics/prometheus?hl=ja
解説：
「アラートを送信する必要があります」という記載内容から、Cloud Monitoring を利用している選択肢が正解となるでしょう。A, D の２択問題です。
問題文から、既にPrometheus指標は作成されているので、それを利用している D が正解と見なせます。
どちらもアラートの通知までの明記はありませんが、Dの方がよりアラートを通知できる条件が記載されています。
</div></details>

## Q. 6-23
次の設計要件を持つ新しいアプリケーションを開発しています。
アプリケーションインフラストラクチャの作成と変更はバージョン管理され、監査可能です。
アプリケーションおよびデプロイインフラストラクチャは Googleマネージドサービスを可能な限り使用します。
アプリケーションはサーバレスコンピューティングプラットフォームで実行されます。
アプリケーションのアーキテクチャをどのように設計する必要がありますか？
1. アプリケーションとインフラストラクチャのそーそコードをGitリポジトリに保存します。CloudBuildを使用してTrraformでアプリケーションインフラストラクチャをデプロイします。アプリケーションをパイプラインステップとしてFunctionsにデプロイします
2. GoogleCloudMarketplaceからJenkinsをデプロイし、Jenkinsで継続的インテグレーションパイプラインを定義します。パイプラインステップを構成してGitリポジトリからアプリケーションソースコードをプルします。アプリケーションソースコードをパイプラインステップとしてAppEngineにデプロイします
3. CloudBuildで継続的インテグレーションパイプラインを作成し、DeploymentManagerテンプレートを使用してアプリケーションインフラストラクチャをデプロイするようにパイプラインを構成します。パイプラインステップを構成して最新のアプリケーションソースコードを含むコンテナを作成します。コンテナをパイプラインステップとしてComputeEngineインスタンスにデプロイします
4. gcloudコマンドを使用してアプリケーションインフラストラクチャをデプロイします。CloudBuildを使用してアプリケーションソースコードを変更するための継続的インテグレーションパイプラインを定義します。Gitリポジトリからアプリケーションソースコードをプルするパイプラインステップを構成し、コンテナ化されたアプリケーションを作成します。新しいコンテナをパイプラインステップとしてCloudRunにデプロイします
<details><div>
    答え：1
説明
Reference：
(1) Google Cloud での CI/CD
https://cloud.google.com/docs/ci-cd?hl=ja
解説：
インフラストラクチャの作成もバージョン管理したいことから、設定ファイルでインフラストラクチャの構成できるTerramformの利用が真っ先に頭に浮かびます。
（この時点で正解はほぼAであろう事が分かります）
これが記載されているのはAで、その他もマネージドサービスの利用(Cloud Build)、サーバーレスコンピューティングの利用(Cloud Functions)を行っており、全ての要件を満たしています。
BはJenkinsを利用している点で条件に少し外れます（「可能な限り使用」なので完全に誤りではないですが、Aには劣ります）
CはComputeEngineを使うという事で、「サーバレス コンピューティング プラットフォームで実行されます」に完全に反しているので真っ先に除外。
Dは文面からはインフラストラクチャーのデプロイメントのバージョン管理を行っていない（行いにくい）と判定できます。
実際にはどこかに実行するコマンドラインが記録されており、そのドキュメントをバージョン管理すれば良いと思いますが、少し原始的な感じがしますし、あくまで「そうだろうな」という想像で明記はされていないのでDはアウトとみなします。
A.はかなり記載が端折られてはいますが、とくに大きな間違いが見当たりません。
「インフラストラクチャの作成と変更はバージョン管理され、監査可能」が決め手でしょう。
従ってこの問題の正解は A となります。
CI/CDの問題で利用されるテクノロジーは(1)で「注目のプロダクト」として挙げ荒れれている、
Cloud Build, Artifact Regisitry, Cloud Source Repositories でこれらの３つを利用している環境が正解であることが多いです。
Artifact Registry は 以前は GoogleContainerRegistry (gcr) が良く使われていました（今でもつかわれています）が、現在はgcrの上位プロダクトであるArtifact Registryの利用が薦められています。
Artifact Registryにまだ馴染みが無い方もおられるかもしれませんが gcr <= Artifact Registry と覚えておいてください。
新しい試験問題では、gcr の記載は無くなって行くでしょう。
</div></details>

## Q. 6-24
ユーザーがニュース記事のコメントを読んだり投稿したりできるアプリケーションを開発しています。
Cloud Firestore を使用してユーザーが送信したコメントを保存および表示するようにアプリケーションを構成したいと考えています。
不明な数のコメントと記事をサポートするにはスキーマをどのように設計するべきでしょうか？
1. 各コメントを記事のサブコレクションに保存します
2. 各コメントを記事の配列プロパティに追加します
3. 各コメントをドキュメントに保存し、コメントのキーを記事の配列プロパティに追加します
4. 各コメントをドキュメントに保存し、コメントのキーをユーザープロファイルの配列プロパティに追加します
<details><div>
    答え：1
説明
不正解
B. 
配列は、個々の配列要素に対するクエリをサポートしていないことや、同時更新を処理する際の課題など、Firestoreではいくつかの制限があります。多数のコメントがある場合、これは問題になる可能性があります。
C. 
各コメントを個別のドキュメントに格納し、それらのコメントを記事上の配列で参照することは、オプション B と同様の制限につながる可能性があります。
D. 
コメントのキーをユーザプロファイルの配列プロパティに格納することは、コメントをユーザにリンクしますが、直接記事にはリンクしません。それは特定の記事に対するすべてのコメントを取得する効率的な方法を提供しません。
正解
A. 
このアプローチはFirestoreのネストされたコレクションのサポートを利用します。各コメントを記事のサブコレクションにドキュメントとして格納することで、指定された記事のすべてのコメントを簡単にクエリでき、記事ごとに無制限のコメント数をサポートします。
誤り解説：
Cloud Firestoreにはドキュメントという単位でデータが保存されるので、正解をC, Dに絞り込みます。
ユーザーキーをデータに保存しておけば、そのユーザーのコメントを検索する事ができるので、要件に合っています。
A, B, C いずれもユーザーとコメントを紐づける情報が不明なので、「ユーザーが送信したコメントを（保存および）表示する」
することが出来ない、と判断することもできると思います。
ちなみにFirestoreでは、単一キーに対しては自動的にインデックスが付加されるため、ユーザーID等をキーにした検索は特に何もしなくても高速です。
正解はDとなります。
</div></details>

## Q. 6-25
Linux を実行している Compute Engine インスタンスでホストされているパッケージ化されたアプリケーションと社内で開発されたアプリケーションが混在しています。
これらのアプリケーションは、ログレコードをテキストとしてローカルファイルに書き込み、ログを Cloud Logging に書き込む必要があります。
どうすればいいでしょうか？
1. ファイルの内容をLinuxSyslogデーモンにパイプします
2. googleバージョンのfluentdをComputeEngineインスタンスにインストールします
3. ComputeEngineインスタンスにGoogleバージョンのcollectedをインストールします
4. cronを使用して1日1回ログファイルをCloudstorageにコピーするジョブをスケジュールします
<details><div>
    答え：2
説明
Reference：
(1) Logging エージェントを構成する
https://cloud.google.com/logging/docs/agent/logging/configuration?hl=ja
解説：
Reference (1)の通り、fluentd が利用できます。
A はログレコードの在りかが定まらないので、B の方法に劣るでしょう。
C のcollectdはサーバーの統計情報を収集するツールです。
D はCloud Loggingに書き込む記載が一切ありませんので、誤りです。
正解は B となります。
</div></details>

## Q. 6-26
他の Google Cloud リソースにアクセスする Cloud Functions を作成しました。
最小権限の原則を使用して環境を保護したいと考えています。
どうすればいいでしょうか？
1. リソースにアクセスするための編集者権限を持つ新しいサービスアカウントを作成します。デプロイ担当者にはアクセストークンを取得するためのアクセス許可が与えられます
2. リソースにアクセスするためのカスタムIAMロールを持つ新しいサービスアカウントを作成します。デプロイ担当者にはアクセストークンを取得するためのアクセス許可が与えられます
3. リソースにアクセスするための編集者権限を持つ新しいサービスアカウントを作成します。デプロイ担当者には、新しいサービスアカウントとして機能する権限が与えられます
4. リソースにアクセスするためのカスタムIAMロールを持つ新しいサービスアカウントを作成します。デプロイ担当者には新しいサービスアカウントとして機能する権限が与えられます
<details><div>
    答え：4
説明
Reference：
(1) Least privilege for Cloud Functions using Cloud IAM
https://cloud.google.com/blog/products/application-development/least-privilege-for-cloud-functions-using-cloud-iam?hl=en
解説：
「最小権限の原則」から過剰な権限の付与が行われていないか考えます。
A, B は権限の利用の仕方の違いはありますが、「編集者権限」が過剰と思えます。
特定のリソースの利用が明記されており、そこに「読み書きする」等の状況が特定されていればあり得ますが、そのリソースに対する編集者ロールの利用は可能であると思いますが、本問題では不特定多数のリソースと考えるしかありません。
その場合、全てのリソースに対して編集者ロールは過剰であると考えるべきでしょう。
本問題ではB, D の必要に応じたカスタムロールの利用の方が「最小権限の原則」に即していると考えます。
デプロイ担当者はCloud Functionsにこのサービスアカウントを適用してCloud Functionsを生成すればよいので、アクセストークンを使う必要はありません。
したがって正解は D となります。
</div></details>

## Q. 6-27
小さなスタートアップ企業のWeb開発チームで働いています。
チームは Cloud Storage や Cloud Build などの Google Cloud サービスを使用して Node.js アプリケーションを開発しており、バージョン管理に Gitリポジトリを使用しています。
上司から週末に電話があり、会社の Webサイトの 1つを緊急に更新するように指示されました。
開発者はあなただけです。
仕事用のラップトップを持っておらず、会社以外のコンピュータにソースコードをローカルに保存することは許可されていません。
開発者環境をどのように設定しますか？
1. テキストエディタとGitコマンドラインを使用して公共のコンピュータからソースコードの更新をプルリクエストとして送信します
2. テキストエディタとGitコマンドラインを使用して公共のコンピュータで実行されている仮想マシンからソースコードの更新をプルリクエストとして送信します
3.CloudShellと組み込みのコードエディタを開発に使用してソースコードの更新をプルリクエストとして送信します 
4. CloudStorageバケットを使用して編集が必要なソースコードを保存します。バケットを公共のコンピュータにドライブとしてマウントし、コードエディタを使用してコードを更新します。バケットのバージョニングを有効にしてチームのGitリポジトリを参照します
<details><div>
    答え：3
説明
解説：
A, B は会社以外のコンピュータでソースコードを使っていると取れますので、その点で問題の条件から消去することができます。
D も一旦公共のコンピュータにソースコードを持ってきて編集する事になるでしょう。
Cloud ShellはCloud コンソール内で利用できるShell (プロジェクト内のVM上で稼働）ですので、ここにソースコードを持ってきてもOKです。
Cloudコンソールへのアクセス（明確に記載はないですが、C, Dの対応には必要、休日対応を想定して、Cloudコンソールにアクセスできる状況は作ってあると考えて良いと思います）という面では同じですが、
行う内容をC, Dで比較した場合、D は特殊でC は自然な作業内容です。
(Dはあっさりと「編集が必要なソースコードを保存します」と書いてありますが、Cloud Shellに一旦 cron なり pullした上での保存になりますので、Cloud Shellに持ってきた時点でCの対応を行えば良いです)
正解はCとなります。
</div></details>

## Q. 6-28
本番環境にデプロイされたアプリケーションがあります。
新しいバージョンがデプロイされたらすべての本番トラフィックがアプリケーションの新しいバージョンにルーティングされるようにする必要があります。
また、新しいバージョンに問題が発生した場合に元に戻せるように以前のバージョンをデプロイしたままにしておくことも必要です。
どのデプロイ戦略を使用するべきでしょうか？
1. Blue/Greenデプロイ戦略
2. カナリアテスト
3. ローリングデプロイ
4. 再作成デプロイ
<details><div>
    答え：1
説明
解説：
まず、C, D が選択肢から外れることはすぐに分かるでしょう。
Cは徐々に新バージョンがデプロイしていくので、「以前のバージョンをデプロイしたままにしておくことも必要」に反します。
Dは全てのPodを削除してから新しいPodが作られるので、これも「以前のバージョンをデプロイしたままにしておくことも必要」に反します。
「元に戻せる」、「以前のバージョンをデプロイしたままにしておく」という記述から Blue/Greenデプロイを選択するのが正解となります。
B の可能性も考えられますが、旧バージョンの一部を新バージョンに置き換えるデプロイ戦略ですので、「以前のバージョンをデプロイしたままにしておく」
という記述に反していると考えられます。
本問題は A が正解です。
</div></details>

## Q. 6-29
あなたは、給与処理用の内部アプリケーションに取り組んでいる開発者です。
従業員がタイムシートを送信できるようにするアプリケーションのコンポーネントを構築しています。
これにより、いくつかの手順が開始されます。
タイムシートが送信されたことを通知する電子メールが従業員とマネージャーに送信されます。
ベンダーの API の給与処理にタイムシートが送信されます。
人数計画のためにタイムシートがデータ ウェアハウスに送信されます。
これらの手順は相互に依存しておらず、任意の順序で完了することができます。
新しいステップが検討されており、異なる開発チームによって実装されます。
各開発チームは、それぞれのステップに固有のエラー処理を実装します。
どうすればいいでしょうか？
1. 対応するダウンストリームシステムを呼び出して必要なアクションを完了するステップ府ごとに、Functionsをデプロイします。
2. 各ステップのPub/Subトピックを作成します。ダウンストリーム開発チームごとにサブスクリプションを作成して、ステップのトピックをサブスクライブします
3. タイムシート提出用のPub/Subトピックを作成する。下流の開発チームごとにサブスクリプションを作成して、トピックをサブスクライブします 
4. GKEにデプロイされるタイムシートマイクロサービスを作成します。マイクロサービスは、各ダウンストリームステップを呼び出し、正常な応答を待ってから次のステップを呼び出します
<details><div>
    答え：3
説明
解説：
A, D は任意の順序での処理ではなく特定の順番による呼び出しが行われると考えられるため、除外します。
タイムシートの送信をトピックとすればよく、複数のトピックを使う必要性がありません。
従って、この問題の正解は C となります。
</div></details>

## Q. 6-30
会社では Cloud Logging を使用して大量のログデータを管理しています。
ログをサードパーティアプリケーションにプッシュして処理するリアルタイムのログ分析アーキテクチャを構築する必要があります。
どうすればいいでしょうか？
1. CloudLoggingのログエクスポートをPub/Subに作成します
2. BigQueryへのCloudLoggingログエクスポートを作成します
3. CloudStorageへのCloudLoggingログエクスポートを作成します
4. CloudLoggingのログエントリを読み取り、サードパーティアプリケーションに送信するFunctionsを作成します
<details><div>
    答え：1
説明
解説：
まずは、Pub/Subに送信し、サービス外でそれを処理するのが良いでしょう。
B, Cはリアルタイム性が低いと思えます。
DもCloud Functions の呼び出しロジックが不明なのでリアルタイム性が低いと思います。
正解は A です。
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

## Q. 
1. 
2. 
3. 
4. 
<details><div>
    答え：
</div></details>
