## Practice Test3

### Q. GAEの以下のすべての構成を選択できます。
1. configure number of instances
2. configure scaling
3. choose diferent machines
4. choose custom vm
<details><div>
    答え：2,3,4
</div></details>

### Q. GCPでの相互接続サービスとは何ですか？
1. cloud vpn 
2. partner peering
3. direct peering
4. cloud interconnect
<details><div>
    答え：1,4
</div></details>

### Q. HTTPSロードバランサーは、次の手法を使用して、同じクライアントトラフィックを同じバックエンドインスタンスに送信します
1. load algorithm
2. instance serving capacity
3. session type
4. session affinity
<details><div>
    答え：4
</div></details>

### Q. Stackdriver Monitoringはカスタムメトリックに使用できます
1. true
2. false
3. 
4. 
<details><div>
    答え：1
</div></details>

### Q. Cloud SQLは、複数の世代のMySQLバージョンを提供し、次のステートメントを選択します
1. 第2世代は、最大10TBのストレージと104GBのRAMを提供します
2. ユーザー定義関数はどの世代でもサポートされていません
3. App Engine内でのみアクセス可能な第1世代
4. 第1世代はOracleデータベース
5. 両方とも無制限のストレージをサポート
<details><div>
    答え：1,2
</div></details>

### Q. 正誤問題：仮想マシンでは、カスタムイメージファイアウォールは既にインターネット用に開かれている
1. true
2. false
3. 
4. 
<details><div>
    答え：2
</div></details>

### Q. Compute Engineから外部IPアドレスを表示するために使用できるコマンド
1. ifconfig
2. gcloud
3. ip address external
4. gsutil
<details><div>
    答え：2
</div></details>

### Q. 次の質問に回答するには、Mountkirk Gamesのケーススタディを参照してください。 同社は、Compute Engine Serviceを使用してゲームバックエンドをホストし、事前定義されたマシンタイプを活用することを検討していますが、ゲームプラットフォームにはより多くのCPU over RAMが必要であることに気付きました。 彼らにはどんな選択肢がありますか？
1. クラウドは本質的に伸縮性があるため、既存のマシンにCPUを追加します
2. 選択した仮想マシンのタイプは変更できません
3. インスタンスをカスタムvm設定に変換します
4. 高CPU構成のカスタムイメージを使用してインスタンスを起動する
<details><div>
    答え：4
</div></details>

### Q. 正誤問題：単一のゾーンに複数のサブネットを作成して、異なるリソースを分離できる
1. true
2. false
3. 
4. 
<details><div>
    答え：1
</div></details>

### Q. カスタムVMは、同等の定義済みVMよりもコストが高くなる場合があります。
1. true
2. false
3. 
4. 
<details><div>
    答え：1
</div></details>

### Q. 企業は、どのネットワークが適切かをSLAとの相互接続が必要ですか？ （2つ選択）
1. cloud vpn
2. cloud interconnect
3. direct peering
4. carrier peering
<details><div>
    答え：1,2
</div></details>

### Q. 次のどれが、Google Compute EngineのCPUの高い定義済みマシンに関する有効なステートメントではないか
1. 64 TBのディスクを使用できますが、マシンには64 vcpuが必要です
2. あなたはCPUさえも持たない
3. vcpuあたり0.9gbのRAMしか使用できません
4. 高い計算要件に適しています
<details><div>
    答え：1
</div></details>

### Q. 正誤問題：デフォルトVPCと自動VPSは同じ
1. ture
2. false
3. 
4. 
<details><div>
    答え：2
</div></details>

### Q. 次の質問に回答するには、Mountkirk Gamesのケーススタディを参照してください。 同社は、カスタム仮想マシンの画像をゲームバックエンド向けGoogle Cloud Platformに取り込みたいと考えています。 どのオプションをお勧めしますか？
1. ローカルイメージのスナップショットをGoogleクラウドストレージに作成し、仮想マシンの作成に使用します
2. GCPプライベートイメージを作成するために、Googleクラウドプラットフォームにカスタムイメージを取り込みます
3. 既存のosからgoogleクラウドプラットフォーム上に仮想マシンを作成し、必要なソフトウェアをインストールするか、osに変更を加えて、その仮想マシンからイメージを作成します
4. Googleクラウドストレージにイメージを保存し、起動スクリプトを作成してソフトウェアをインストールし、必要に応じてOSを変更します
<details><div>
    答え：2
</div></details>

### Q. 会社は、世界中でアクセスされる低遅延で高可用性を必要とするウェブサイトの画像を保存したいと考えています。 最適なオプションは何ですか？
1. google cloud storage
2. google cloud sql
3. google cloud virtual machine
4. store it in on premises data center
<details><div>
    答え：1
</div></details>

### Q. 次の質問に回答するには、Mountkirk Gamesのケーススタディを参照してください。 ゲームの読み取り専用データは複数の仮想マシン間で共有する必要がありますが、一般公開されているため、クラウドストレージでホストすることは望みません。 提案する代替オプションは何ですか？
1. ローカルssdを使用してデータを共有し、nfsが他のvmにアクセスする
2. Googleクラウドストレージは、データを共有する必要がある唯一のオプションです
3. 読み取り専用永続ディスクを使用して、仮想マシン間で読み取り専用データを共有します
4. 非構造化データにクラウドSQLを使用する
<details><div>
    答え：3
</div></details>

### Q. ロードバランサーは、次の負荷分散アルゴリズムを使用して、インスタンスがビジーかどうかを確認します
1. rps,cpu utilization
2. cpu utilizations only
3. cpu and ram utilizations
4. ram utilization
<details><div>
    答え：1
</div></details>

### Q. HTTPロードバランサーが再試行するリクエストは次のうちどれですか
1. failed post reqiests
2. http load baalncer does not retry any failed request
3. failed get requests
4. failed udp request
<details><div>
    答え：3
</div></details>

### Q. 次のサービス構成クラウドCDNのどれを有効にできますか？
1. container engine
2. load balancer
3. virtual machine
4. app engine
<details><div>
    答え：2
</div></details>

### Q. Google Cloud Compute Engine内で外部IPアドレスが表示されます
1. true
2. false
3. 
4. 
<details><div>
    答え：1
</div></details>

### Q. 次の質問に回答するには、Dress4winのケーススタディを参照してください。 同社は、Google Cloud Platformへの移行中にクラウドリソースの使用を最適化したいと考えています。VMに接続されたディスクストレージに使用できるコストオプションの側面は何ですか。
1. ストレージよりも高いIOPSが必要な場合はssdを使用します
2. より良いコストのためにローカルssdと永続ディスクを使用する
3. 固定サイズの永続ディスクを使用する
4. 速度よりも価格あたりのサイズが大きい磁気ディスクを使用する
<details><div>
    答え：1,4
</div></details>

### Q. ファイアウォールは、サードパーティクライアントからのSSH接続用にGoogle Compute Engineに対してデフォルトで開いています
1. true
2. false
3. 
4. 
<details><div>
    答え：2
</div></details>

### Q. TerramEarthのケーススタディを参照して、次の質問に答えてください。 TerramEarthは、ストリーム処理を使用して、マシン上のデータをより迅速に分析することを計画しています。 どのセキュリティ対策を考慮する必要がありますか？
1. ipv6通信プロトコルを使用します
2. 内部デバイス通信にtpmの使用を検討する
3. SSL通信を使用する
4. すべてのAPI呼び出しが信頼できると考える
<details><div>
    答え：2
</div></details>

### Q. GCP Stackdriverは、GCPおよびAWSサービスに使用できます
1. true
2. fales
3. 
4. 
<details><div>
    答え：1
</div></details>

### Q. 次のマシンタイプにはGPUを接続できません
1. shared core
2. high cpu
3. high memory
4. costom machine
5. standard
<details><div>
    答え：1
</div></details>

### Q. Kubernetes Engineマスターノードは、1つを除く以下のすべてを管理します
1. runs pod
2. pod deletion
3. arts as endpoint to kubernetes engine cluster
4. schedules pod creation
<details><div>
    答え：1
</div></details>

### Q. vCPUのGoogle Compute EngineはCPUプラットフォームに依存しています
1. true
2. false
3. 
4. 
<details><div>
    答え：1
</div></details>

### Q. カスタムネットワークに関する正しい説明は何ですか？
1. routes are not defined by default
2. firewall rules are not created
3. resources can talk to each other
4. subnets are created for all regions
<details><div>
    答え：1,2
</div></details>

### Q. Cloud Interconnectについて正しい記述は何ですか？
1. cloud interconnect is vpn service
2. cloud interconnect can be implemented using publiuc iunternet
3. cloud interconnect procides secure communications by default
4. cloud interconnect provided by using partner integration
<details><div>
    答え：4
</div></details>

### Q. Google Compute Engine（VM）への接続に関する事実ではないこと
1. sshを使用してlinux vmに接続できます
2. クラウドシェルを使用してvmを接続できます
3. クラウドコンソールからrdpまたはsshを使用して接続できます
4. サードパーティのsshクライアントを使用してLinux VMに接続することはできません
5. rdpを使用してWindows VMに接続できます
<details><div>
    答え：4
</div></details>

### Q. 企業は、その存続期間中にアクセスされる場合とされない場合がある規制およびコンプライアンスデータのストレージコストを削減したいと考えていますが、アクセスが必要な場合は迅速かつ簡単に利用できるようにする必要があります。
1. cloud storage with regional storage class
2. cloud storage with coldline storage class
3. cloud storage with nearline storage class
4. wms local ssd
5. cloud persistent disk
<details><div>
    答え：2
</div></details>

### Q. Cloud Functionは、Dockerコンテナでアプリケーションを実行します
1. true
2. false
3. 
4. 
<details><div>
    答え：2
</div></details>

### Q. ポッド共有内のコンテナー
1. does not share anything
2. same application
3. ip address and namespace
4. ip address and port
<details><div>
    答え：3
</div></details>

### Q. ノードには、1つを除く次のすべてのコンポーネントが含まれます
1. cloud serviec integration
2. docket runtime
3. kubekrt agent
4. docker runtime
<details><div>
    答え：1
</div></details>

### Q. キャッシュされたPOPの場所にコンテンツが見つからない場合、Cloud CDNは次にデータを検索しますか？
1. cloud sql
2. nearby cache
3. backend service
4. cloud storage
<details><div>
    答え：2
</div></details>

### Q. 会社は、シンガポール地域でのみアクセスされるプロモーションビデオファイルを保存する必要があります。 最適なストレージオプションは何ですか？
1. cloud storage with regional storage class
2. cloud vortual machine from singapore region
3. cloud storage with muktiregional storage class
4. cloud function
5. cloud cdn
<details><div>
    答え：1
</div></details>

### Q. TerramEarthのケーススタディを参照して、次の質問に答えてください。 TerramEarthはデータ処理を使用したいと考えています-Sparkを使用したリアルタイム分析とHadoopを使用したバッチ処理、Google Cloud Platformではどのようなオプションが役立ちますか？
1. install apache apark and hadoop on google virtual machine
2. cloud dataproc
3. cloud dataflow
4. cloud machine learning
<details><div>
    答え：2
</div></details>

### Q. App Engineに対して以下のすべてのスケーリングを構成できます
1. automatic
2. hybrid
3. manual
4. content aware
<details><div>
    答え：1,3,4
</div></details>

### Q. Stackdriver Monitoringはアラートに使用できます-アラートに関係するステップ
1. report incident
2. notifications
3. aggregation
4. monitoring conditions
<details><div>
    答え：1,2,4
</div></details>

### Q. TerramEarthのケーススタディを参照して、次の質問に答えてください。 TerramEarthは、重要なデータ構成に使用している特定のVMへのアクセスを取得する必要があります。メンテナンス時にこれらのサーバーにアクセスするには、どのソリューションを使用できますか？
1. use custom vm 
2. use nat gateway
3. use baition host
4. use ssl commmunication
<details><div>
    答え：3
</div></details>

### Q. 次の質問に回答するには、Dress4winのケーススタディを参照してください。 同社は、既存の仮想マシンのワークロードをGoogle Cloud Platformに移行する必要があり、それでもコストを最適化したいと考えています。 コスト最適化のどの側面を使用できますか？
1. use only one vpc
2. start with min configuration and scale based on requirement
3. try to use less subnetworks
4. use preempmtible vm for batch work
<details><div>
    答え：2,4
</div></details>

### Q. Google Compute Engineのパフォーマンスの考慮事項
1. which hardware the vm is hosted
2. disk iops
3. gbs of ram
4. no of vcpu
<details><div>
    答え：1
</div></details>

### Q. 次の質問に回答するには、Dress4winのケーススタディを参照してください。 会社は、ネットワークの外部からアクセスされるクラウド上の仮想マシンについて懸念を持っています。外部からマシンにアクセスすることを避けるための提案は何ですか？
1. use cloud vpn
2. use service account to restrict access to vm
3. use firewall rule to allow only from your own infrastructure
4. use cloud router
<details><div>
    答え：3
</div></details>

### Q. 次のうち、ローカルSSDを選択する際の考慮事項ではないものはどれですか？
1. local disk size is fixed size
2. you can use only one local disk per vm
3. vm with local ssd can not live migrate with data sotred on local ssd
4. local ssd is ephemeral
5. local ssd can be up to 3 tb
<details><div>
    答え：2
</div></details>

### Q. Stackdriver Basicティアには次のオプションがあります
1. audit logs 30 days
2. gcp and aws services
3. other logs 7 days
4. gcp services
<details><div>
    答え：1,3,4
</div></details>

### Q. Kubernetes Engine Serviceは、1つを除いて以下を提供します
1. scts load balancer
2. provide single ip address for pods
3. ha and autoscaler
4. resource manager and scheduler
<details><div>
    答え：4
</div></details>

### Q. あなたの会社は、既存の仮想マシンをGoogle Cloud Platformに移行する必要があります。Compute Engineから選択する基準ではないもの
1. network sotrage requirements
2. operating system requirement
3. google cloud storage required
4. operating system customizations
5. choose between custom vs predefined machine
<details><div>
    答え：3
</div></details>

### Q. グローバルロードバランサーは、1つを除く次のすべての機能をサポートします。
1. inteligent routing
2. vm memory utilizations based routing
3. global scoped network
4. better utilizations og backend service
<details><div>
    答え：2
</div></details>

### Q. 正誤問題：デフォルトモードネットワーク（VPC）では、リソースは設定を変更せずに互いに通信できます。
1. true
2. false
3. 
4. 
<details><div>
    答え：1
</div></details>

### Q. VMネットワークのパフォーマンスは、次のパラメーターに依存します
1. no. of disk attached
2. no. of vcpus
3. network interface attached
4. gbs of memory
<details><div>
    答え：2
</div></details>

