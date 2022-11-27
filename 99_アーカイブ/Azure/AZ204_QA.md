# 模擬問題
## １

### Q. Azure Web Appとして実行されるサービスとしてのソフトウェア（SaaS）ASP.NET CoreWebサービスを実装しています。Webサービスは、ストレージにオンプレミスのSQLServerデータベースを使用します。Webサービスには、データの更新を処理するWebJobも含まれています。4人の顧客がWebサービスを使用します。
    ・WebJobの各インスタンスは、単一の顧客のデータを処理し、シングルトンインスタンスとして実行する必要があります。
    ・各デプロイメントは、実稼働データを提供する前にデプロイメントスロットを使用してテストする必要があります。
    ・Azureのコストを最小限に抑える必要があります。
    ・Azureリソースは分離されたネットワークに配置する必要があります。
WebアプリのAppServiceプランを構成する必要があります。
App Serviceプランをどのように構成する必要がありますか？
それぞれで適切な設定を選択してください。

App Serviceプラン設定
・VMインスタンス数：
A:2
B:4
C:8
D:16
・価格レベル
E:Isolated
F:Standard
G:Premium
H:Consumption
<details><div>
    答え：B,E
</div></details>

### Q. あなたは、AzureFunctionを使用して注文を処理するサービスとしてのソフトウェア（SaaS）会社の開発者です。Azure Functionは現在、AzureStorageキューによってトリガーされるAzureFuntionアプリで実行されます。Kubernetesベースのイベントドリブン自動スケーリング（KEDA）を使用して、AzureFunctionをKubernetesに移行する準備をしています。Azure関数のKubernetesカスタムリソース定義（CRD）を構成する必要があります。下記の設定で、どのCRDを構成する必要がありますか？
    設定：Azure Function code
1. Secret
2. Deployment
3. ScaledObject
4. TriggerAuthntication
<details><div>
    答え：2
</div></details>

### Q. あなたは、AzureFunctionを使用して注文を処理するサービスとしてのソフトウェア（SaaS）会社の開発者です。Azure Functionは現在、AzureStorageキューによってトリガーされるAzureFunctionアプリで実行されます。Kubernetesベースのイベントドリブン自動スケーリング（KEDA）を使用して、AzureFunctionをKubernetesに移行する準備をしています。Azure関数のKubernetesカスタムリソース定義（CRD）を構成する必要があります。下記の設定で、どのCRDを構成する必要がありますか？
    設定：Polling interval
1. Secret
2. Deployment
3. ScaledObject
4. TriggerAuthntication
<details><div>
    答え：3
</div></details>

### Q. あなたは、AzureFunctionを使用して注文を処理するサービスとしてのソフトウェア（SaaS）会社の開発者です。Azure Functionは現在、AzureStorageキューによってトリガーされるAzureFunctionアプリで実行されます。Kubernetesベースのイベントドリブン自動スケーリング（KEDA）を使用して、AzureFunctionをKubernetesに移行する準備をしています。Azure関数のKubernetesカスタムリソース定義（CRD）を構成する必要があります。下記の設定で、どのCRDを構成する必要がありますか？
    設定：Azure Storageの接続文字列
1. Secret
2. Deployment
3. ScaledObject
4. TriggerAuthntication
<details><div>
    答え：1
</div></details>

### Q. 写真を管理するためのサービスとしてのソフトウェア（SaaS）を開発します。ユーザーは写真をWebサービスにアップロードし、Webサービスは写真をAzure StorageBlobストレージに保存します。ストレージアカウントの種類は汎用V2です。写真をアップロードするときは、モバイル対応バージョンの画像を作成して保存するために写真を処理する必要があります。モバイル対応バージョンの画像を作成するプロセスは、1分以内に開始する必要があります。写真処理を開始するプロセスを設計する必要があります。
    解決策：Blobストレージイベントから写真処理をトリガーします。
解決策は目標を達成していますか？
1. はい
2. いいえ
<details><div>
    答え：2
</div></details>

### Q. データストレージにAzureBlobストレージを使用するWebサイトを構築しています。30日後にすべてのBLOBをアーカイブ層に移動するようにAzureBlobストレージライフサイクルを構成します。お客様は、30日より古いデータを表示するためのサービスレベル契約（SLA）を要求しています。データリカバリの最小SLAを文書化する必要があります。どのSLAを使用する必要がありますか？
1. 少なくとも2日
2. 1～15時間
3. 少なくとも1日
4. 0～60分
<details><div>
    答え：2
</div></details>

### Q. AzureBlobストレージを使用するアプリケーションがあります。BLOBのメタデータを更新する必要があります。ソリューションを開発するために使用する必要がある3つの方法はどれですか？
1. Metadata.Add
2. SetMetadataAsync
3. FetchAttributesAsync
4. UploadFilesStream
5. SertPropertiesAsync
<details><div>
    答え：1,2,3
</div></details>

### Q. 世界中にある2,000の店舗からPOS（point-of-sale）デバイスデータを収集するAzureソリューションを開発しています。1つのデバイスで24時間ごとに2メガバイト（MB）のデータを生成できます。各店舗の場所には、データを送信する1〜5台のデバイスがあります。デバイスデータをAzureBlobストレージに保存する必要があります。デバイスデータは、デバイス識別子に基づいて相関させる必要があります。将来的には追加の店舗がオープンする予定です。デバイスデータを受信するためのソリューションを実装する必要があります。
    解決策：Azureイベントグリッドをプロビジョニングします。マシンIDをパーティションキーとして構成し、キャプチャを有効にします。
解決策は目標を達成していますか？
1. はい
2. いいえ
<details><div>
    答え：2
    代わりに、注文処理と金融取引に使用されるAzure ServiceBusを使用してください。イベントは、状態または状態変化の軽量な通知です。 イベントハブは通常、ステータスの変化に対応して使用されます。
リファレンス：
https://docs.microsoft.com/ja-jp/azure/event-grid/compare-messaging-services
</div></details>

### Q. Azure App Service APIアプリを開発し、Developmentという名前のWindowsでホストされるデプロイスロットにデプロイします。Testing and Productionという名前の追加のデプロイメントスロットを作成します。本番デプロイメントスロットで自動スワップを有効にします。スワップ操作が発生する前に、スクリプトが実行され、リソースが使用可能であることを確認する必要があります。
    解決策：web configファイルを更新して、application Initialization構成要素を含めます。スクリプトを実行するためのカスタム初期化アクションを指定します。
解決策は目標を達成していますか？
1. はい
2. いいえ
<details><div>
    答え：1
    カスタムウォームアップを指定します。一部のアプリでは、スワップの前にカスタムのウォームアップアクションが必要になる場合があります。 web configのapplicationInitialization構成要素を使用すると、カスタム初期化アクションを指定できます。スワップ操作は、このカスタムウォームアップが終了するのを待ってから、ターゲットスロットとスワップします。
</div></details>

### Q. Azure App Service APIアプリを開発し、Developmentという名前のWindowsでホストされるデプロイスロットにデプロイします。Testing and Productionという名前の追加のデプロイメントスロットを作成します。本番デプロイメントスロットで自動スワップを有効にします。スワップ操作が発生する前に、スクリプトが実行され、リソースが使用可能であることを確認する必要があります。
    解決策：テストスロットの自動スワップを有効にします。アプリをテストスロットにデプロイします。
解決策は目標を達成していますか？
1. はい
2. いいえ
<details><div>
    答え：2
    代わりに、webconfigファイルを更新して、applicationInitialization構成要素を含めます。スクリプトを実行するためのカスタム初期化アクションを指定します。一部のアプリでは、スワップの前にカスタムのウォームアップアクションが必要になる場合があります。 webconfigのapplicationInitialization構成要素を使用すると、カスタム初期化アクションを指定できます。スワップ操作は、このカスタムウォームアップが終了するのを待ってから、ターゲットスロットとスワップします。
</div></details>

### Q. Azure App Service APIアプリを開発し、Developmentという名前のWindowsでホストされるデプロイスロットにデプロイします。Testing and Productionという名前の追加のデプロイメントスロットを作成します。本番デプロイメントスロットで自動スワップを有効にします。スワップ操作が発生する前に、スクリプトが実行され、リソースが使用可能であることを確認する必要があります。
    解決策：自動スワップを無効にします。statuscheckという名前のメソッドでアプリを更新して、スクリプトを実行します。自動スワップを再度有効にして、アプリを本番スロットにデプロイします。
解決策は目標を達成していますか？
1. はい
2. いいえ
<details><div>
    答え：2
    代わりに、webconfigファイルを更新して、applicationInitialization構成要素を含めます。スクリプトを実行するためのカスタム初期化アクションを指定します。注：一部のアプリでは、スワップの前にカスタムのウォームアップアクションが必要になる場合があります。 webconfigのapplicationInitialization構成要素を使用すると、カスタム初期化アクションを指定できます。スワップ操作は、このカスタムウォームアップが終了するのを待ってから、ターゲットスロットとスワップします。
</div></details>

### Q. 写真を管理するためのサービスとしてのソフトウェア（SaaS）を開発します。ユーザーは写真をWebサービスにアップロードし、Webサービスは写真をAzure StorageBlobストレージに保存します。ストレージアカウントの種類は汎用V2です。写真をアップロードするときは、モバイル対応バージョンの画像を作成して保存するために写真を処理する必要があります。モバイル対応バージョンの画像を作成するプロセスは、1分以内に開始する必要があります。写真処理を開始するプロセスを設計する必要があります。
    解決策：AzureStorageアカウントをBlockBlobStorageストレージアカウントに変換します。
解決策は目標を達成していますか？
1. はい
2. いいえ
<details><div>
    答え：2
    アカウントを変換する必要はありません。代わりに、写真処理をBLOBアップロードからトリガーされるAzure関数に移動します
</div></details>

### Q. AzureWebアプリを開発しています。 WebアプリのTLS相互認証を構成します。Webアプリでクライアント証明書を検証する必要があります。それぞれで適切な値を選択します。
プロパティ：クライアント証明書の場所
A：HTTP request header
B：Client cookie
C：HTTP message body
D：URL query string
プロパティ：エンコードタイプ
E：HTML
F：URL
G：Unicode
H：Base64
<details><div>
    答え：A,H
HTTP request header
    ASP.NETを使用していて、クライアント証明書認証を使用するようにアプリを構成している場合、証明書はHttpRequest.ClientCertificateプロパティを介して利用できます。
Base64
    他のアプリケーションスタックの場合、クライアント証明書は、「X-ARR-ClientCert」リクエストヘッダーのbase64エンコード値を介してアプリで利用できます。 アプリケーションは、この値から証明書を作成し、それをアプリケーションの認証および承認の目的で使用できます。
    https://docs.microsoft.com/ja-jp/azure/app-service/app-service-web-configure-tls-mutual-auth
</div></details>

### Q. Azure App Service Web App for Containersを使用してDocker / Goを開発しています。Linux上のAppServiceでコンテナーを実行することを計画しています。使用するDockerコンテナイメージを特定します。現在のリソースグループはいずれも、Linuxをサポートする場所にありません。必要なリソースグループの数を最小限に抑える必要があります。アプリケーションを作成し、初期デプロイメントを実行する必要があります。ソリューションを開発するために使用する必要がある3つのAzureCLIコマンドはどれですか？
1. az group create 
2. az group update
3. az webapp update
4. az webapp create
5. az appservice plan create
<details><div>
    答え：2,4,5
</div></details>

### Q. AzureでサーバーレスJavaアプリケーションを開発しています。新しいAzureKey Vaultを作成して、新しいAzureFunctionsアプリケーションのシークレットを操作します。アプリケーションは、次の要件を満たしている必要があります。
    ・Javaコードを変更せずにAzureKeyVaultを参照します。
    ・受信アプリケーションイベントの数に基づいて、AzureFunctionsホストのインスタンスを動的に追加および削除します。
    ・コールドスタートを回避するために、インスタンスが永続的にウォームであることを確認する。
    ・VNetに接続します。
    ・AzureFunctionアプリケーションを削除する場合は、Azure KeyVaultインスタンスへの認証を削除する必要があります。
あなたは、AzureFunctionsアプリケーションにAzureKeyVaultへのアクセスを許可する必要があります。
順番に実行する必要がある3つのアクションはどれですか？
1. アプリケーションにユーザーが割り当てた管理対象IDを作成します
2. プレミアムプランタイプでAzureFunctionsアプリを作成する
3. AzureKeyVaultでアプリケーションIDのアクセスポリシーを作成します
4. AzureKeyVaultでアプリケーションIDのSSL証明書を作成します
5. AppService プランタイプを使用してAzureFunctionsアプリを作成します
6. 消費プランタイプを使用してAzureFunctionsアプリを作成します
7. システムによって割り当てられた管理対象IDまたはアプリケーションを作成します
<details><div>
    答え：2,3,7
手順1：プレミアムプランタイプでAzureFunctionsアプリを作成する
    プレミアムプランは、アイドル状態になった後も遅延なくアプリケーションを実行し、より強力なインスタンスで実行し、仮想ネットワークに接続します、事前にウォームアップされたワーカーを使用して、需要に基づいて自動的にスケーリングします。
手順2：システムによって割り当てられた管理対象IDまたはアプリケーションを作成します。
    アプリケーションにシステム割り当ての管理対象IDを作成します。
    Key Vault参照は現在、システムによって割り当てられた管理対象IDのみをサポートします。ユーザーが割り当てたIDは使用できません。
手順3：KeyVaultでアプリケーションIDのアクセスポリシーを作成する前に作成したアプリケーションIDのアクセスポリシーをKeyVaultで作成します。 
    このポリシーで「取得」シークレット権限を有効にします。
    https://docs.microsoft.com/ja-jp/azure/app-service/app-service-key-vault-references
</div></details>

### Q. あなたはウェブサイトを開発します。 AzureでWebサイトをホストすることを計画しています。Webサイトが公開された後、大量のトラフィックが発生することが予想されます。コストを最小限に抑えながら、Webサイトが引き続き利用可能で応答性が高いことを確認する必要があります。あなたは、Webサイトを展開する必要があります。何をするべきですか？
1. Webサイトを仮想マシンにデプロイします。CPU負荷が高いときに自動的にスケーリングするように仮想マシンを構成します
2. 共有サービス層を使用するAppServiceにWebサイトをデプロイします。CPU負荷が高いときに自動的にスケーリングするようにAppServiceプランを構成します
3. Webサイトを仮想マシンにデプロイします。CPU負荷が高いときにインスタンス数を増やすようにスケールセットを構成します
4. 標準サービス層を使用するAppServiceにWebサイトを展開します。CPU負荷が高いときに自動的にスケーリングするようにAppServiceプランを構成します
<details><div>
    答え：
</div></details>

### Q. Azure StorageBLOBデータを処理するためのHTTPトリガーAzureFunctionアプリを開発します。アプリは、BLOBの出力バインディングを使用してトリガーされます。アプリは4分後もタイムアウトし続けます。アプリはBLOBデータを処理する必要があります。アプリがタイムアウトしてBLOBデータを処理しないようにする必要があります。解決策：Durable Function非同期パターンを使用してblobデータを処理します。解決策は目標を達成していますか？
1. はい
2. いいえ
<details><div>
    答え：2
    関数アプリのタイムアウト設定に関係なく、230秒は、HTTPトリガー関数が要求に応答するのにかかる最大時間です。これは、Azure LoadBalancerのデフォルトのアイドルタイムアウトが原因です。処理時間が長くなる場合は、Durable Functions非同期パターンを使用するか、実際の作業を延期して即時応答を返すことを検討してください。
リファレンス：
    https://docs.microsoft.com/ja-jp/azure/azure-functions/durable/durable-functions-timers?tabs=csharp
    https://docs.microsoft.com/ja-jp/azure/azure-functions/durable/durable-functions-overview?tabs=csharp#async-http
    https://docs.microsoft.com/ja-jp/azure/azure-functions/functions-scale#timeout
</div></details>

### Q. Azure StorageBLOBデータを処理するためのHTTPトリガーAzureFunctionアプリを開発します。アプリは、BLOBの出力バインディングを使用してトリガーされます。アプリは4分後もタイムアウトし続けます。アプリはBLOBデータを処理する必要があります。アプリがタイムアウトしてBLOBデータを処理しないようにする必要があります。
    解決策：HTTPトリガーペイロードをAzure Service Busキューに渡して、キュートリガー関数で処理し、HTTP成功応答を即座に返します。
解決策は目標を達成していますか？
1. はい
2. いいえ
<details><div>
    答え：1
    キュートリガー関数によって処理されるキューへのHTTPトリガーペイロード。このアプローチにより、実際の作業を延期し、即座に応答を返すことができます。
https://docs.microsoft.com/ja-jp/azure/azure-functions/functions-best-practices
</div></details>

### Q. Azure StorageBLOBデータを処理するためのHTTPトリガーAzureFunctionアプリを開発します。アプリは、BLOBの出力バインディングを使用してトリガーされます。アプリは4分後もタイムアウトし続けます。アプリはBLOBデータを処理する必要があります。アプリがタイムアウトしてBLOBデータを処理しないようにする必要があります。
    解決策：App Serviceホスティングプランを使用するようにアプリを構成し、AlwaysOn設定を有効にします。
解決策はは目標を達成していますか？
1. はい
2. いいえ
<details><div>
    答え：2
</div></details>

### Q. 写真を管理するためのサービスとしてのソフトウェア（SaaS）を開発します。ユーザーは写真をWebサービスにアップロードし、Webサービスは写真をAzureに保存しますストレージBLOBストレージ。ストレージアカウントの種類は汎用V2です。写真をアップロードするときは、モバイル対応バージョンの画像を作成して保存するために写真を処理する必要があります。モバイル対応バージョンの画像を作成するプロセスは、1分以内に開始する必要があります。写真処理を開始するプロセスを設計する必要があります。
    解決策：写真処理を、BLOBのアップロードからトリガーされたAzure関数に移動します。
解決策は目標を達成していますか？
1. はい
2. いいえ
<details><div>
    答え：1
    Azure Storageイベントを使用すると、アプリケーションはイベントに反応できます。一般的なBlobストレージイベントシナリオには、画像またはビデオ処理、検索インデックス作成、またはファイル指向のワークフローが含まれます。イベントは、Azure Event Gridを使用して、Azure Functions、Azure Logic Appsなどのサブスクライバー、または独自のhttpリスナーにプッシュされます。
https://docs.microsoft.com/ja-jp/azure/storage/blobs/storage-blob-event-overview
</div></details>

### Q. AzureBlobストレージを使用するアプリケーションを開発しています。アプリケーションは、監査の目的で、ストレージアカウント内のBLOBおよびBLOBメタデータに発生するすべての変更のトランザクションログを読み取る必要があります。変更は、発生した順序で行う必要があり、作成、更新、削除、およびコピー操作のみが含まれ、コンプライアンス上の理由から保持されます。トランザクションログを非同期で処理する必要があります。あなたは何をするべきですか？
1. サブスクライバーのAzureFunctionsアプリでAzureEvent Gridを使用して、すべてのAzureBlobストレージイベントを処理します
2. ストレージアカウントで変更フィードを有効にし、利用可能なイベントのすべての変更を処理します
3. 成功したblobイベントについて、すべてのAzure StorageAnaclyticsログを処理します
4. Azure Monitor HTTP Data Collector API を使用し、リクエストの本文をスキャンして、成功したBLOBイベントを探します
<details><div>
    答え：2
    変更フィードの目的は、ストレージアカウントのBLOBおよびBLOBメタデータに発生するすべての変更のトランザクションログを提供することです。 変更フィードは、これらの変更の順序付けられた、保証された、耐久性のある、不変の、読み取り専用のログを提供します。 クライアントアプリケーションは、ストリーミングモードまたはバッチモードのいずれかで、いつでもこれらのログを読み取ることができます。 変更フィードを使用すると、BlobStorageアカウントで発生する変更イベントを低コストで処理する効率的でスケーラブルなソリューションを構築できます。
https://docs.microsoft.com/ja-jp/azure/storage/blobs/storage-blob-change-feed
</div></details>

### Q. AzureBlobコンテナーにアップロードされた画像を処理するAzureFunctionアプリを開発しています。画像はアップロード後できるだけ早く処理する必要があり、ソリューションは遅延を最小限に抑える必要があります。Functionアプリがトリガーされたときに画像を処理するコードを作成します。あなたは、Functionアプリを設定する必要があります。何をするべきですか？
1. AppServiceプランを使用してください。AzureBlobStorage入力トリガーを使用するようにFunctionAppを構成します
2. 消費プランを使用します。AzureBlobStorageトリガーを使用するようにFunctionアプリを構成します
3. 消費プランを使用します。タイマートリガーを使用するようにFunctionアプリを構成します
4. AppServiceプランを使用してください。AzureBlobStorageトリガーを使用するようにFunctionAppを構成します
5. 消費プランを使用します。AzureBlobStorage入力トリガーを使用するようにFunctionアプリを構成します
<details><div>
    答え：4
    質問には「できるだけ早く処理する必要があります」と書かれています。 関数アプリが消費プランに含まれている場合、関数アプリがアイドル状態になると、新しいブロブの処理に最大10分の遅延が発生する可能性があります。 そのため、AppServiceプランが必要です。
リファレンス：
    https://docs.microsoft.com/ja-jp/azure/azure-functions/functions-bindings-storage-blob-trigger?tabs=csharp
</div></details>

### Q. 次のユースケースをサポートする病院向けのソリューションを開発しています。
    ・異なる場所にいる複数のユーザーが患者レコードを更新した場合でも、最新の患者ステータスの詳細を取得する必要があります。
    ・取得する患者の健康状態の監視データは、現在のバージョンまたは以前のバージョンである必要があります。
    ・患者が退院し、すべての請求が査定された後、患者の請求記録には最終的な請求が含まれます。
Cosmos DB NoSQLデータベースをプロビジョニングし、データベースアカウントのデフォルトの整合性レベルをStrongに設定します。IndexingModeの値をConsistentに設定します。あなたは、レイテンシーとソリューションの可用性への影響を最小限に抑える必要があります。シナリオに必要な整合性の保証を満たすには、クエリレベルでデフォルトの整合性レベルをオーバーライドする必要があります。あなたは、次の内容でどの一貫性レベルを実装する必要がありますか
    ・最新の患者の状態を返します。
1. Strong
2. BoundStaleness
3. Evantual
4. Consitent prefix
<details><div>
    答え：1
    Strong consistencyは線形化可能性の保証を提供します。読み取りは、アイテムの最新のコミットされたバージョンを返すことが保証されています。クライアントには、コミットされていない書き込みや部分的な書き込みは表示されません。ユーザーは常に最新のコミットされた書き込みを読み取ることが保証されています。
</div></details>

### Q. 次のユースケースをサポートする病院向けのソリューションを開発しています。
    ・異なる場所にいる複数のユーザーが患者レコードを更新した場合でも、最新の患者ステータスの詳細を取得する必要があります。
    ・取得する患者の健康状態の監視データは、現在のバージョンまたは以前のバージョンである必要があります。
    ・患者が退院し、すべての請求が査定された後、患者の請求記録には最終的な請求が含まれます。
Cosmos DB NoSQLデータベースをプロビジョニングし、データベースアカウントのデフォルトの整合性レベルをStrongに設定します。IndexingModeの値をConsistentに設定します。あなたは、レイテンシーとソリューションの可用性への影響を最小限に抑える必要があります。シナリオに必要な整合性の保証を満たすには、クエリレベルでデフォルトの整合性レベルをオーバーライドする必要があります。あなたは、次の内容でどの一貫性レベルを実装する必要がありますか
    ・1バージョン以上遅れているヘルスモニタリングデータを返します。
1. Strong
2. BoundStaleness
3. Evantual
4. Consitent prefix
<details><div>
    答え：2
</div></details>

### Q. 次のユースケースをサポートする病院向けのソリューションを開発しています。
    ・異なる場所にいる複数のユーザーが患者レコードを更新した場合でも、最新の患者ステータスの詳細を取得する必要があります。
    ・取得する患者の健康状態の監視データは、現在のバージョンまたは以前のバージョンである必要があります。
    ・患者が退院し、すべての請求が査定された後、患者の請求記録には最終的な請求が含まれます。
Cosmos DB NoSQLデータベースをプロビジョニングし、データベースアカウントのデフォルトの整合性レベルをStrongに設定します。IndexingModeの値をConsistentに設定します。あなたは、レイテンシーとソリューションの可用性への影響を最小限に抑える必要があります。シナリオに必要な整合性の保証を満たすには、クエリレベルでデフォルトの整合性レベルをオーバーライドする必要があります。あなたは、次の内容でどの一貫性レベルを実装する必要がありますか
    ・患者が退院し、すべての料金が査定された後、最終的な料金で請求データを修正します。
1. Strong
2. BoundStaleness
3. Evantual
4. Consitent prefix
<details><div>
    答え：3
    読み取りの順序は保証されません。それ以上の書き込みがない場合、レプリカは最終的に収束します。
</div></details>

### Q. チームの開発環境を構成しています。最新のVisualStudioイメージをAzureMarketplaceからAzureサブスクリプションにデプロイします。開発環境では、組織全体のアプリケーション開発をサポートするために、いくつかのソフトウェア開発キット（SDK）とサードパーティコンポーネントが必要です。開発チーム用にデプロイされた仮想マシン（VM）をインストールしてカスタマイズします。新しいチームメンバー開発環境のプロビジョニングを可能にするには、カスタマイズされたVMを保存する必要があります。将来のプロビジョニングのために、カスタマイズしたVMを保存する必要があります。どのツールまたはサービスを使用する必要がありますか？それぞれで適切なオプションを選択してください。
・VMを一般化します。
A：Azure PowerShell
B：VisualStudioコマンドプロンプト
C：Azure Migrate
D：Azureバックアップ
・画像を保存します。
E：Azure Blob Storage
F：Azure Data Lake Storage
G：Azureファイルストレージ
H：Azureテーブルストレージ
<details><div>
    答え：A,E
AzurePowershell
    VMから直接イメージを作成すると、OSディスクやデータディスクなど、VMに関連付けられているすべてのディスクがイメージに含まれるようになります。Sysprepを使用して仮想マシンを一般化してから、AzurePowerShellを使用してイメージを作成します。
Azure BlobStorage
    画像はAzureBlobStorageに保存できます。
</div></details>

### Q. 
1. 
2. 
3. 
4. 
<details><div>
    答え：
</div></details>




