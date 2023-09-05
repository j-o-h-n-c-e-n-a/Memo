
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
1. 
2. 
3. 
4. 
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
1. 
2. 
3. 
4. 
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
1. 
2. 
3. 
4. 
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
1. 
2. 
3. 
4. 
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
1. 
2. 
3. 
4. 
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
1. 
2. 
3. 
4. 
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
1. 
2. 
3. 
4. 
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
1. 
2. 
3. 
4. 
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
1. 
2. 
3. 
4. 
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
1. 
2. 
3. 
4. 
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
