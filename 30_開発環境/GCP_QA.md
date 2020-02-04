## 練習問題
### Q1. 企業は、既存の仮想マシンをGoogle Cloud Platformに移行する必要があります。どのようなオプションがありますか？
1. 既存のパブリックイメージからgcpコンピューティングエンジンを使用し、ソフトウェアを再インストールする
2. オンプレミスvmを計算エンジンに移行してvmを作成します
3. アプリケーションを再作成して、Google App EngineまたはContainer Engineにデプロイできるようにします
4. カスタムイメージをgcpにインストールすることはできません
<details><div>
    答え：２
</div></details>

### Q2. 事前定義されたVM構成を使用する代わりに、カスタム構成を作成すると常に良い?
1. True
2. False
<details><div>
    答え：2
</div></details>

### Q3. 次のうち、Google Cloud Platformで利用できる有効な定義済み仮想マシンタイプではないものはどれですか？
1. High Memory
2. High CPU
3. High Memory and CPU
4. Standard
5. Standard Core
<details><div>
    答え：3
</div></details>

### Q4. 次のうち、Google Compute Engineの有効なカスタムマシンではないものはどれですか？
1. 1 vCPU 1GB RAM
2. 2 vCPU 1.8GB RAM
3. 0.6 vCPU 1GB RAM
4. 32 vCPU 29GB RAM
<details><div>
    答え：3
</div></details>

### Q5. 会社は、バックエンドのビデオ処理要件に高いコンピューティング要件を持っています。どのオプションが事前定義されたマシンに最適ですか？
1. Standard
2. High CPU - Because it contains more CPU over RAM
3. High Memory - Because it contains high RAM over CPU
4. High Memory and CPU - Because it contains more Momory and CPU over
<details><div>
    答え：2
</div></details>

### Q6. Google Compute Engine（VM）に接続できる永続ディスクはいくつですか？
1. 5 per VM
2. 1 per CPU
3. 8 per VM
4. 10 per CPU
<details><div>
    答え：4
</div></details>

### Q7. Google Compute EngineのCPUの高い定義済みマシンに関する有効なステートメントでないものは何ですか？
1. You can only have 0.9 GB of RAM per vCPU
2. You can only have even no of CPU's
3. You can have 64TB of Disk but you need 64 vCPU for machine
4. Suitable for high Compute requirements
<details><div>
    答え：3
</div></details>

### Q8. 会社は既存の仮想マシンをGoogle Cloud Platformに移行する必要がありますが、compute Engineから選択する基準は何ですか？
1. カスタムマシンと定義済みマシンを選択します
2. googleクラウドストレージが必要
3. 必要なオペレーティングシステム
4. オペレーティングシステムのカスタマイズ
5. ネットワークストレージ要件
<details><div>
    答え：2
</div></details>

### Q9. Google Compute Engineのパフォーマンスの考慮事項、どれが考慮すべき有効なパラメーターではありませんか？
1. VMがホストされているハードウェア
2. ネットワークパフォーマンス
3. Disk IOPS
4. vcpuのない
5. ギガバイトRAM
<details><div>
    答え：１
</div></details>

### Q10. Google Compute Engine（VM）に接続することに関して間違っているものはどれですか？
1. rdpを使用してWindows VMに接続できます
2. サードパーティのsshクライアントを使用してLinux VMに接続することはできません
3. sshを使用してlinux vmに接続できます
4. クラウドコンソールからrdpまたはsshを使用して接続できます
5. クラウドシェルを使用してvmを接続できます
<details><div>
    答え：２
</div></details>

### Q11. ファイアウォールは、サードパーティクライアントからのSSH接続用にGoogle Compute Engineに対してデフォルトで開かれています。
1. True
2. False
<details><div>
    答え：２
</div></details>

### Q12. 外部IPアドレスは、Google Cloud Compute Engine内に表示されます。
1. True
2. False
<details><div>
    答え：１
</div></details>

### Q13. Compute Engineから外部IPアドレスを確認するには、どのコマンドを使用できますか？
1. gcloud
2. ipconfig
3. ipaddress external
4. gsutil
<details><div>
    答え：1
</div></details>

### Q14. 次のマシンタイプにはGPUを接続できません
1. Shared Core
2. Custom machine
3. Standard
4. High Memory
5. High CPU
<details><div>
    答え：1
</div></details>

### Q15. VMネットワークのパフォーマンスは、次のパラメーターに依存します
1. vCPU数
2. RAM容量
3. 接続ディスク数
4. 接続ネットワーク数
<details><div>
    答え：１
</div></details>

### Q16. ローカルSSDを選択する際の考慮事項ではないものは何ですか？
1. ローカルssdは一時的です
2. ローカルssdを持つvmは、ローカルssdに保存されたデータを使用してライブ移行できません
3. ローカルssdは3 TBまで可能
4. vmごとに1つのローカルディスクのみを使用できます
5. ローカルディスクサイズは固定サイズです
<details><div>
    答え：４
</div></details>

### Q17. カスタムVMは、同等の定義済みVMよりもコストが高くなる場合があります。
1. TRUE
2. FALSE
<details><div>
    答え：１
</div></details>

### Q18. Google Compute EngineのvCPUの数は、CPUプラットフォームに依存しています。
1. TRUE
2. FALSE
<details><div>
    答え：１
</div></details>

### Q19. GCEには、マネージドインスタンスグループとアンマネージドインスタンスグループがあります。
1. TRUE
2. FALSE
<details><div>
    答え：1
</div></details>

### Q20. アンマネージドインスタンスグループでは自動スケーリングできません。
1. TRUE
2. FALSE
<details><div>
    答え：１
</div></details>

### Q21. GCEのアンマネージドインスタンスグループについて正解はどれですか？
1. 自動スケーリングに使用
2. 負荷分散に使用
3. 異なるリソースを持つインスタンスを持つことはできません
4. ローリング更新を行うことができます
<details><div>
    答え：２
</div></details>

### Q22. マネージドインスタンスグループは次の目的には使用されません
1. ローリング更新
2. 負荷分散
3. 自動スケーリング
4. 異種リソースの管理
<details><div>
    答え：４
</div></details>

### Q23. HTTPロードバランサーのスコープは
1. リージョナル
2. ゾーン
3. 内部
4. グローバル
<details><div>
    答え：４
</div></details>

### Q24. HTTPロードバランサーは、内部通信でIPV4のみをサポートします
1. TRUE
2. FALSE
<details><div>
    答え：１
</div></details>

### Q25. HTTPロードバランサーに関して誤っているステートメントは何ですか？
1. httpロードバランサーはコンテンツに対応していません
2. 複数の地域間で負荷を分散できます
3. 
4. リクエストはクローズドサービングインスタンスにルーティングされます
<details><div>
    答え：１
</div></details>

### Q26. ヘルスチェックは、HTTPロードバランサーの不可欠な部分です。
1. TRUE
2. FALSE
<details><div>
    答え：１
</div></details>

### Q27. HTTPロードバランサーは、常にトラフィックを正常性インスタンスにルーティングします。
1. TRUE
2. FALSE
<details><div>
    答え：１
</div></details>

### Q28. ロードバランサーは、次の負荷分散アルゴリズムを使用して、インスタンスがビジーかどうかを確認します
1. CPU と RAMの利用
2. RAMの利用
3. CPUの利用
4. リクエスト数（RPS） と CPUの利用
<details><div>
    答え：４
</div></details>

### Q29. GAEには、1つを除く以下の機能があります
1. トラフィック分割
2. アプリケーションバージョニング
3. 標準とフレキシブルな環境
4. モニタリング、ロギング、エラーレポート
5. DNS
<details><div>
    答え：５
</div></details>

### Q30. GAEは、VMを管理し、GCPが下線のハードウェアとネットワークを管理するマネージドサービスです。
1. TRUE
2. FALSE
<details><div>
    答え：２
</div></details>

### Q31. GAEはコンテナオーケストレーションを提供します。
1. TRUE
2. FALSE
<details><div>
    答え：２
</div></details>

### Q32. 1つを除く次のスケーリングを構成できます。
1. 手動
2. 自動
3. ハイブリッド
4. 内容に沿って
<details><div>
    答え：3
</div></details>

### Q33. 1つを除くGAEの次の構成を選択できます。
1. 別のマシンを選択する
2. スケーリングを設定する
3. カスタムVMを選択する
4. インスタンス数
<details><div>
    答え：４
</div></details>

### Q34. GAE標準環境に当てはまらないものは何ですか？
1. Dockerコンテナのサポート
2. 事前構成済みのサンドボックス
3. 標準環境のためのGoogle SDK
4. 
<details><div>
    答え：１
</div></details>

### Q35. GAE Flexible Envに当てはまらないこと
1. サンドボックスランタイムを事前設定します
2. CPUとメモリを設定できます
3. dockerfileでenvをカスタマイズできます
4. VMへのルートアクセスがあります
<details><div>
    答え：１
</div></details>

### Q36. GAEは、1つを除くすべてに基づいて請求されます
1. 使用されるマシンインスタンスのタイプ
2. ネットワーク出口
3. 要件に基づいて使用されるその他のサービス
4. ネットワーク入口
<details><div>
    答え：４
</div></details>

### Q37. GKEは、GCP上のKubernetesの実装であり、Google Cloud Platformのマネージドサービスです。
1. TRUE
2. FALSE
<details><div>
    答え：1
</div></details>

### Q38. コンテナは、特定の状況での仮想化マシン上のリソース消費量が少なくなります。
1. TRUE
2. FALSE
<details><div>
    答え：1
</div></details>

### Q39. コンテナは、仮想マシンよりも少ないリソースを消費するという問題を解決しますが、次の問題を解決します
1. オーケストレーションとライフサイクルの管理
2. 仮想化環境へのインストール
3. コンテナは解決策であり問題です
4. リソース配分
<details><div>
    答え：1
</div></details>

### Q40. GKEは、1つを除く以下の機能をサポートします
1. Auto Scaling
2. Stackdriver Logging
3. Docker Format
4. Cloud IAM integration
5. Preemptible Machine
<details><div>
    答え：5
</div></details>

### Q41. GKWには、1つのマスターと1つ以上のワーカーノードが含まれます。
1. TRUE
2. FALSE
<details><div>
    答え：1
</div></details>

### Q42. GKEマスターノードは、以下を除くすべてを管理します
1. Schedules POD Creation
2. POD Deletion
3. Runs POD
4. Acts as endpoint to GKE cluster
<details><div>
    答え：3
</div></details>

### Q43. ポッドには次のコンポーネントが含まれます
1. Doket Runtime
2. Cloud Service Integration
3. Kubelete Agent
4. Doker Runtime
<details><div>
    答え：2
</div></details>

### Q44. ポッド共有内のコンテナー
1. IP address and Namespace
2. IP address and Port
3. Does not share anything
4. Same application
<details><div>
    答え：1
</div></details>

### Q45. GKEサービスは以下を提供します
1. Acts Load balancer
2. Resource Manager and scheduler
3. Provide single IP adress for pods
4. HA and Autoscaller
<details><div>
    答え：2
</div></details>

### Q46. GKE Deploymentsはどの目的のためのものですか
1. Supports HA and Autoscaller
2. Resource Manager and scheduler
3. For single endpoint to cluster
4. Procides single IP to pods
<details><div>
    答え：1
</div></details>

### Q47. Googleのどのサービスが真のサーバーレス環境として扱われますか？
1. Cloud Compute Engine
2. Google App Engine
3. Google Container Engine
4. Cloud Function
<details><div>
    答え：4
</div></details>

### Q48. GCPのどのコンピューティングサービスをウェブサイトのホスティングに選択しませんか？
1. Cloud Compute Engine
2. Google App Engine
3. Google Container Engine
4. Cloud Function
<details><div>
    答え：4
</div></details>

### Q49. Cloud Functionは、Dockerコンテナーでアプリケーションを実行します。
1. True
2. False
<details><div>
    答え：2
</div></details>

### Q50. 次の文のうち、Cloud Functionに当てはまらないものはどれですか？
1. サーバーレス
2. 実行時にのみ変更
3. イベントドリブン
4. その実行はdocker containerです
<details><div>
    答え：４
</div></details>

### Q51. Cloud Functionは、次のいずれかをのぞく、すべてのトリガーをサポートしています
1. HTTP
2. Cloud Storage
3. Cloud Pub/Sub
4. Firebase
5. Cloud SQL
<details><div>
    答え：5
</div></details>

### Q. データセンター内の単一マシンで実行されている標準のリレーショナルデータベースをクラウドに移行する必要がある場合、どのデータストレージサービスを選択できますか？
1. Cloud SQL
2. BigQuery
3. Persistent Disk
4. Cloud Storage
<details><div>
    答え：1
</div></details>

### Q. どのGCPデータストレージサービスがACIDトランザクションを提供し、何千ものノードに拡張できますか？
1. Cloud Storage
2. Cloud CDN
3. Cloud Spanner
4. Cloud SQL
<details><div>
    答え：3
</div></details>

### Q. どのデータストレージサービスが、データを格納するためのデータウェアハウスサービスを提供し、データを照会するためのインタラクティブなSQLインターフェイスも提供しますか？
1. BigQuery
2. Cloud DataProc
3. Cloud Data lab
4. Cloud SQL
<details><div>
    答え：1
</div></details>

### Q. 企業はデータを保存用に保存する必要があります。データを低コストで保存するのに最適な方法
1. Cloud Storage with Coldline Storage Class
2. Cloud SQL
3. Virtual Machine
4. Cloud Storage with Regional Storage Class
5. Cloud BigQuery
<details><div>
    答え：1
</div></details>

### Q. 靴会社は、Google Cloudに靴の多数の画像を保存するためにGCPで最適なストレージソリューションを探しています
1. Google Compute Engine storage
2. Google Container Service
3. Google Cloud Storage
4. Google Cloud data-proc
<details><div>
    答え：3
</div></details>

### Q. 会社は静的ウェブサイトをクラウドでホストしたいと考えています。管理オーバーヘッドなしで静的ウェブアプリケーションをホストするための最良のソリューションは何ですか
1. Google Container Engine
2. Google Compute Service
3. Google Cloud Storage
4. Google App Engine
5. Google dose not support static hosting
<details><div>
    答え：3
</div></details>

### Q. 会社は、高可用性と低遅延を必要とし、世界中からアクセスする必要があるWebサイトの画像を保存する必要があります。 最良の選択肢は何ですか
1. Google Cloud SQL
2. Google Cloud Storage
3. Store it in on premises Data Center
4. Google Cloud Virtual Machine
<details><div>
    答え：2
</div></details>

### Q. 会社は、シンガポール地域でのみアクセスされるビデオファイルを保存する必要があります。 最適なストレージオプションは何ですか
1. Cloud Storage with Regional Storage Class
2. Cloud Virtual Machine from Singapore region
3. Cloud Storage with Multi-regional Storage Class
4. Cloud Function
5. Cloud CDN
<details><div>
    答え：1
</div></details>

### Q. 企業は、その存続期間中にアクセスされる場合とされない場合があるが、アクセスが必要な場合、迅速かつ容易に利用可能であるべき規制およびコンプライアンスデータのストレージコストを削減したいと考えています。
1. Cloud Storage with Regional Storage Class
2. Cloud Storage with Coldline Storage Class
3. Cloud Storage with Nearline Storage Class
4. Cloud Persistent Disk
5. VMs local SSD
<details><div>
    答え：2
</div></details>

### Q. すべての部門および事業単位とすべてのバケットで使用されるクラウドストレージは、すべてのアプリケーション/ユーザーにアクセスできます。 コンプライアンス部門は、バケットに保存されている一部の機密情報が保護されていないことに気付きました。 コンプライアンスは、迅速な修正としてバケットへのアクセスを制限できることも発見しました。 リーガルは、実際のファイルへのアクセスを可能にするさまざまなオプションを提案しています。この状況に最適なソリューションは何ですか
1. IAMを使用して個々のオブジェクトへのアクセスを制限し、長期的なソリューションは必要ありません
2. ACLを使用して機密オブジェクトへのアクセスを制限し、長期的には情報の用途と機密性に応じて個別のバケットを作成します
3. 何もする必要はありません-クラウドストレージにはデータを保護するための制限と暗号化があります
4. すべてのアプリケーションへのすべてのバケットへのアクセスを停止し、アプリケーションが問題を解決するためにソリューションを停止して作業できるようにします
<details><div>
    答え：2
</div></details>

### Q. アプリケーションと用途はファッションデザインにアクセスしており、多くのデザイナーによって継続的に更新されています。これらのデザインはCloud Storageに保存されます。 多くのデザイナーは、個々のデザインに取り組んでおり、誰が更新しているかを追跡するのは難しいです。 この状況に最適なソリューションは何ですか
1. すべての設計者に、それぞれが密接に共同注文するように依頼し、設計の変更をクラウドストレージで行う
2. クラウドストレージは履歴を自動的に追跡するため、誰が変更を行ったかがわかります
3. ここでは有効なユースケースではありません-クラウドストレージのオブジェクトを上書きすることはできません
4. Cloud Storageへのアクセスをすべてのデザイナーに制限し、1人をデザインの共同注文ラインに任命します
5. バージョン管理を有効にして、オブジェクトの変更を追跡できるようにします
<details><div>
    答え：5
</div></details>

### Q. バケツについて本当のこと
1. 同じ名前で複数のバケットを作成できます
2. バケットをネストして、ディレクトリ構造のようにファイルを保存できます
3. プロジェクトごとに1つのバケットが許可されます
4. 必要なだけ多くのオブジェクトをバケットに書き込むことができます
<details><div>
    答え：4
</div></details>

### Q. Cloud Storageオブジェクトには読み取りと書き込みの制限があります
1. true
2. false
<details><div>
    答え：1
</div></details>

### Q. Cloud Storageオブジェクトの最大サイズは何ですか
1. 5kb
2. 5gb
3. 5tb
4. 1kb
5. 制限なし
<details><div>
    答え：３
</div></details>

### Q. Cloud Storageオブジェクトの最小サイズは何ですか
1. 0byte
2. 5gb
3. 5tb
4. 1kb
<details><div>
    答え：1
</div></details>

### Q. Cloud Storageバケットのストレージクラスを定義すると、そのバケットのオブジェクトは異なるストレージクラスに保存できません
1. true
2. false
<details><div>
    答え：2
</div></details>

### Q. Cloud Storage Bucketでオブジェクトを更新する最大頻度は？
1. 1 min
2. 5 second
3. no limit
4. 1 second
5. 1 hour
<details><div>
    答え：4
</div></details>

### Q. Cloud Storageオブジェクトの更新が1秒に1回未満の場合、どのエラーが発生する可能性がありますか？
1. エラーが発生しない
2. 202 Accepted
3. 500 Internal Server Error
4. 404 Page not found
5. 503 Service Unacailable Error
<details><div>
    答え：5
</div></details>

### Q. プロジェクトごとのバケット数の制限は何ですか？
1. no limit
2. 2 bucket
3. 10 bucket
4. 100 bucket
5. 500 bucket
<details><div>
    答え：1
</div></details>

### Q. プロジェクトごとのバケットの作成/削除の制限は何ですか？
1. 2秒ごとにバケットを作成/削除できます
2. 10分ごとにバケットを作成/削除できます
3. 1日ごとにバケットを作成/削除できます
4. 制限はありません
<details><div>
    答え：1
</div></details>

### Q. Cloud Storageオブジェクトの作成/削除操作のレートはいくらですか？
1. 1秒あたり1つの作成/削除操作
2. 1秒あたり2つの作成/削除操作
3. 1秒あたり10個のオペレーションの作成/削除
4. 制限なし
<details><div>
    答え：4
</div></details>

### Q. Cloud Storage Bucketのストレージクラスが変更された場合、どうなりますか？
1. 新しいストレージクラスで新しいオブジェクトが作成されます
2. 古いオブジェクトは新しいsotrageクラスに移動されます
3. 新しいsotrageクラスは、サービスの近くにあるため、より高速になります。
4. ストレージ。模倣は10 GBから5TBに増加します。
<details><div>
    答え：1
</div></details>

### Q. Cloud Storageでどのような操作が最終的に一貫していますか？
1. クラウドストレージオブジェクトの書き込み後に読み取る
2. クラウドストレージオブジェクトの削除後に読み取る
3. オブジェクトのリスト
4. リソースからのアクセスの取り消し
5. リソースへのアクセスの許可
<details><div>
    答え：4
</div></details>

### Q. Cloud Storage Bucketには2レベルの階層しか作成できませんか？
1. true
2. false
<details><div>
    答え：2
</div></details>

### Q. 有効にできるのはバージョンのみですが、Cloud Storageオブジェクトのバージョン管理を無効にすることはできません。
1. true
2. false
<details><div>
    答え：2
</div></details>

### Q. 有効にすると、クラウドストレージはオブジェクトのライブバージョンが上書きまたは削除されるたびに、オブジェクトのアーカイブバージョンとして作成されます。
1. true
2. false
<details><div>
    答え：1
</div></details>

### Q. オブジェクトの1つのバージョンのみを復元できます。
1. true
2. false
<details><div>
    答え：2
</div></details>

### Q. Objectのカスタムメタデータを作成できます。
1. true
2. false
<details><div>
    答え：1
</div></details>

### Q. Cloud Storage Objectのすべてのメタデータアイテムを変更できます。
1. true
2. false
<details><div>
    答え：2
</div></details>

### Q. 一度設定すると、Cloud Storageオブジェクトのストレージクラスを変更できません。
1. true
2. false
<details><div>
    答え：2
</div></details>

### Q. Cloud Storage Nearline Storage Classの最小ストレージ期間は？
1. 24 hours
2. no limit
3. 30 days
4. 90 days
5. 1 year
<details><div>
    答え：3
</div></details>

### Q. Cloud Storage Regional Storage Classの最小ストレージ期間は？
1. 24 hours
2. no limit
3. 30 days
4. 90 days
5. 1 year
<details><div>
    答え：2
</div></details>

### Q. 6か月に1回アクセスされるレポートを保存するためのデータバックソリューションが必要です。このシナリオに適したストレージクラスは何ですか？
1. Regional Storage Class
2. Multi Regional Storage Class
3. Coldline Storage Class
4. Nearline Storage Class
5. Persistent Disk Storage Class
<details><div>
    答え：4
</div></details>

### Q. 会社は、AWSからGoogle Cloud Storageにデータを移動したいのですが、どのアプリケーションを使用できますか？
1. Google Cloud Pub/Sub
2. Storage Transfer Service
3. gsutils
4. CLoud SQL
<details><div>
    答え：2
</div></details>

### Q. Cloud Storage Notificationsの識別に使用できるアプリケーションはどれですか？
1. Cloud pub/sub
2. Cloud Data proc
3. Cloud SQL
4. Cloud Container Engine
<details><div>
    答え：1
</div></details>

### Q. Google Cloudでアプリケーションをホストしていない場合、Cloud Storageを使用してデータを保存することはできません。
1. true
2. false
<details><div>
    答え：2
</div></details>

### Q. Google Cloud Applicationsからのみクラウドストレージにアクセスできます。
1. true
2. false
<details><div>
    答え：2
</div></details>

### Q. 会社がGoogle Cloud Storageに移行し、リレーショナルデータベースをGoogleクラウドに移行する必要があります。マネージドサービスとしてどのようなオプションがありますか？
1. MySQL
2. Oracle
3. Teradata
4. Cloud Storage
<details><div>
    答え：1
</div></details>

### Q. 会社はCloud SQLを何日も使用していますが、アプリケーションはMYSQLのパフォーマンスの問題に直面しています。 どのオプションを使用できますか？
1. 読み取り操作用の読み取りレプリケーションを作成する
2. mysqlの複数のインスタンスを作成します
3. クラウドコンピューティングエンジンにOracleをインストールしてスケーリングする
4. クラウドストレージへのモードデータ
<details><div>
    答え：1
</div></details>

### Q. Cloud SQLのオンデマンドバックアップを作成できます。
1. true
2. false
<details><div>
    答え：1
</div></details>

### Q. ラージインスタンスタイプを作成すると、MYSQLインスタンスを複製できます。
1. true
2. false
<details><div>
    答え：2
</div></details>

### Q. SSHを使用してCloud SQLマシンインスタンスに接続できます
1. true
2. false
<details><div>
    答え：1
</div></details>

### Q. Stack-driver監視と統合することはできません
1. true
2. false
<details><div>
    答え：2
</div></details>

### Q. 障害インスタンスがプライマリになるには、変更を構成する必要があります。
1. true
2. false
<details><div>
    答え：2
</div></details>

### Q. Cloud SQLは、Googleが提供するMicrosoft SQLサービスです。
1. true
2. false
<details><div>
    答え：2
</div></details>

### Q. Cloud SQL仮想マシンのセキュリティパッチを監視してインストールする必要があります。
1. true
2. false
<details><div>
    答え：2
</div></details>

### Q. Cloud SQLはマネージドサービスであり、管理者MYSQLユーザーへのアクセス権はありません。
1. true
2. false
<details><div>
    答え：2
</div></details>

### Q. Cloud SQL用に仮想マシンをカスタマイズできます
1. true
2. false
<details><div>
    答え：1
</div></details>

### Q. ディスクのスループットとIOPSは、Cloud SQLインスタンスに接続されたディスクのサイズに依存します。
1. true
2. false
<details><div>
    答え：1
</div></details>

### Q. CIDRに基づいてCloud SQL接続をブロックまたは有効化できます。
1. true
2. false
<details><div>
    答え：1
</div></details>

### Q. Googleクラウドプラットフォームでリレーショナル、水平スケーラブル、強力な一貫性、およびPettabyteのスケールを提供するデータベースサービスは何ですか？
1. Cloud SQL
2. Cloud Bigtable
3. Cloud Datastore
4. Cloud Spanner
<details><div>
    答え：4
</div></details>

### Q. Cloud Spannerは、水平方向にスケーラブルなリレーショナルデータベースです。
1. true
2. false
<details><div>
    答え：1
</div></details>

### Q. インターライブテーブルは、どのデータベースサービスに実装できますか？
1. Cloud Big table
2. Cloud Datastore
3. Cloud SQL
4. Cloud Spanner
<details><div>
    答え：4
</div></details>

### Q. Cloud Spannerは、ノードに基づいて課金およびスケーリングされます。
1. true
2. false
<details><div>
    答え：1
</div></details>

### Q. Cloud Spannerでは、データは保管時に暗号化されません。
1. true
2. false
<details><div>
    答え：2
</div></details>

### Q. 各クラウドスパナノードによって提供される読み取りQPSとは何ですか？
1. 2k
2. 1 million
3. 1 billion
4. 1 trillion
5. 10 k
<details><div>
    答え：5
</div></details>

### Q. 各クラウドスパナノードによって提供される書き込みQPSとは何ですか？
1. 2k
2. 1 million
3. 1 billion
4. 1 trillion
5. 10 k
<details><div>
    答え：1
</div></details>

### Q. 永続ディスクは、仮想マシンで使用可能なネットワーク接続ストレージオプションです。
1. true
2. false
<details><div>
    答え：1
</div></details>

### Q. どのストレージサービスを使用して、複数の仮想マシンに読み取り専用データを添付できますか？
1. Cloud Storage
2. Persistent Disk
3. Local SSD
<details><div>
    答え：2
</div></details>

### Q. 次のストレージオプションのどれがブロックストレージとして使用されますか？
1. Local SSD
2. Local Magnetic Disk
3. Persistent Disk
4. Cloud Storage
<details><div>
    答え：3
</div></details>

### Q. 永続ディスクに使用できる最大サイズは？
1. 16gb
2. 5tb
3. 64tb
4. 1pb
<details><div>
    答え：3
</div></details>

### Q. 永続ディスクの最大スループットは、ディスクのサイズに依存しません。
1. true
2. false
<details><div>
    答え：2
</div></details>

### Q. ローカルSSDデータは複数の仮想マシン間で保持されます。
1. true
2. false
<details><div>
    答え：2
</div></details>

### Q. Google Cloud Platformのネットワーキングの重要な特徴は何ですか？
1. データに「遅延配信」のタグを付けることができ、設定した日時に配信されます
2. 他のクラウドネットワークとは異なり、アクセスリストとファイアウォールルールを使用できます
3. ネットワークトポロジはアドレスレイアウトに依存しません。
4. rfc 1918に準拠するsuppoets ipv4アドレス
<details><div>
    答え：３
</div></details>

### Q. VM内で解決できるIP
1. 内部IPアドレス
2. セカンダリIPアドレス
3. 外部IPアドレス
4. vm内のIPアドレスを解決できない
<details><div>
    答え：１
</div></details>

### Q. Cloud VPNを拡張する方法
1. 複数のクラウドVPN
2. クラウドVPNはスケーリングを必要としません
3. スループットを高めるために複数のトンネルを追加します
4. オプションでgoogles cloud cdnを使用できます
<details><div>
    答え：３
</div></details>

### Q. 1 GBPS接続が必要な場合-どの相互接続がコストを考慮した最も実行可能なオプションです
1. carrier peering
2. direct peering
3. cloud vpn
4. cloud interconnect with paetner integration
<details><div>
    答え：３
</div></details>

### Q. サーバーが機密情報を処理しています。インターネットから隔離するために外部IPアドレスを削除できます
1. true
2. false
<details><div>
    答え：１
</div></details>

### Q. ロードバランサーの構成にアクセスするために使用される要塞ホスト
1. true
2. false
<details><div>
    答え：２
  ロードバランサーを使用しない場合に
</div></details>

### Q. Google Virtual Network Subnetsはリージョンリソースです
1. true
2. false
<details><div>
    答え：１
  グローバル
</div></details>

### Q. どの相互接続サービスがGCPの下にあるか
1. direct peering
2. cloud vpn
3. cloud interconnect
4. partner peering
<details><div>
    答え：２，３
  ピアリングは違う
</div></details>

### Q. 企業は、GCPに接続するためにセキュアチャネルを備えた500 Mbps接続を必要とします。低コストを維持するために、次の相互接続のいずれかが適切です
1. cloud cdn
2. cloud vpn
3. cloud dns
4. dedicated interconnect
<details><div>
    答え：２
  Cloud VPNで十分
</div></details>

### Q. VPNの代わりにクラウドインターコネクトまたはダイレクトピアリングを使用する理由は何ですか？
1. グーグルは、クラウド相互接続およびダイレクトピアリングのSLASのみを提供します
2. vpnはIPアドレスの割り当てとcidrサブネットの制御を提供しませんが、クラウド相互接続と直接ピアリングは制御します
3. クラウド相互接続と直接ピアリングは、使用していないときに簡単にオン/オフできるため、安価です。
4. クラウド相互接続とダイレクトピアリングにより、データ集約型アプリケーションの可用性が向上し、待ち時間が短縮され、コストが削減されます。
<details><div>
    答え：４
</div></details>

### Q. クラウドCDNは、次のサービス構成のいずれで有効にすることができます
1. app engine
2. virtual machine
3. container engine
4. load balancer
<details><div>
    答え：４
</div></details>

### Q. FQDNに内部DNSサーバーを使用した内部IPアドレス
1. true
2. false
<details><div>
    答え：１
</div></details>

### Q. クラウドCDNはバックエンドサービスの負荷を増加させます
1. true
2. false
<details><div>
    答え：２
</div></details>

### Q. gcloudコマンドを使用して、VM内の外部IPアドレスを解決できます
1. true
2. false
<details><div>
    答え：１
</div></details>

### Q. 会社は、どのネットワークが適切かSLAとの相互接続を必要としますか？ （2つ選択）
1. cloud interconnect
2. direct peering
3. cloud vpn
4. carrier peering
<details><div>
    答え：１，３
</div></details>

### Q. 10Gbpsネットワークが必要で、Googleのコロケーション施設に存在する場合、クラウド相互接続を使用してインフラストラクチャをGoogleに接続します
1. true
2. false
<details><div>
    答え：１
</div></details>

### Q. カスタムイメージ仮想マシンファイアウォールは既にインターネット用に開かれています
1. true
2. false
<details><div>
    答え：１
</div></details>

### Q. Googleクラウドプロジェクトごとに最大5つのネットワークを作成できます
1. true
2. false
<details><div>
    答え：１
</div></details>

### Q. カスタムネットワークの真実
1. リソースは互いに通信できます
2. すべてのリージョンに対してサブネットが作成されます
3. ルートはデフォルトでは定義されていません
4. ファイアウォールルールは作成されません
<details><div>
    答え：３，４
</div></details>

### Q. クラウドルーターの目的は何ですか？それはなぜ重要ですか？
1. トポロジを自動的に検出して共有できる動的vpnを実装し、手動の静的ルートメンテナンスを削減します。
2. クラウドルーターを使用すると、複数のVPNでラウンドロビンスイッチングを実行できるため、帯域幅を組み合わせて、実際に内部で提供されるよりも優れたスループットを得ることができます。
3. 一方のvpnを他方の直接ピアリングに接続します。これはvpn単独よりも高速です。
4. これは、Googleが提供するがgcpでホストされるハードウェアルーターです。
<details><div>
    答え：１
</div></details>

### Q. 仮想プライベートネットワーク（VPN）の目的は何ですか？
1. VPNはアクセス制御リスト（ACL）とも呼ばれ、ネットワークアクセスを制限します
2. ネットワーク境界のエッジで侵入者を検出する方法です
3. インターネットなどの信頼できない環境を介して2つの信頼できる環境を接続するための安全な通信方法を有効にする
4. 主な目的は、暗号化された形式で保存できるようにデータを暗号化することです
<details><div>
    答え：３
</div></details>

### Q. クラウドDNSに関する本当の声明は何ですか
1. クラウドDNSは、HTTPロードバランサーのエンドポイントを使用できます
2. クラウドDNS管理サービス
3. クラウドDNSは、プライベートセンターでホストされているサービスと連携できます。
4. クラウドDNSの稼働率は99.9％です
<details><div>
    答え：１，２
  クラウドDNSの稼働率は99.99％です
</div></details>

### Q. 次の主要な構成に基づくクラウドCDNキャッシュデータ（3つ選択）
1. キャッシュキー
2. クエリ文字列
3. サービスタイプの計算
4. プロトコルとホスト
<details><div>
    答え：１，２，４
</div></details>

### Q. クラウドルーターは2つのネットワークを安全なチャネルで接続します
1. true
2. false
3. 
4. 
<details><div>
    答え：２
</div></details>

### Q. NATは転送ルールを使用してトラフィックを内部サーバーに送信します
1. true
2. false
3. 
4. 
<details><div>
    答え：１
</div></details>

### Q. 単一ゾーンに複数のサブネットを作成して、GCPリソースを分離できます
1. true
2. false
3. 
4. 
<details><div>
    答え：１
</div></details>

### Q. アドレスではなくタグでファイアウォールルールを適用する利点の1つは何ですか？
1. ファイアウォールルールのタグは、vmsが受信する一時IPアドレスを制御します
2. 一致するタグでvmが作成されると、ファイアウォールルールは、割り当てられたIPアドレスに関係なく適用します
3. ネットワークトラフィックのタグは、ネットワークスニッフィングに役立ちます
4. タグは、組織がファイアウォールの請求を追跡するのに役立ちます
<details><div>
    答え：２
</div></details>

### Q. クラウドルーターはBGPリンクを使用してネットワークの変更をアドバタイズします
1. true
2. false
3. 
4. 
<details><div>
    答え：１
</div></details>

### Q. クラウド相互接続について本当のこと
1. パブリック相互接続を使用してクラウド相互接続を実装できます
2. クラウドインターコネクトはデフォルトで安全な通信を提供します
3. クラウド相互接続はvpnサービスです
4. パートナー統合を使用して提供されるクラウド相互接続
<details><div>
    答え：４
  プロトコルの暗号化はデフォルトでない
</div></details>

### Q. クラウドVPNの使用-複数のVPNトンネルでECMPを実行して、より高いスループットを達成できます
1. true
2. false
3. 
4. 
<details><div>
    答え：１
</div></details>

### Q. Google Cloud Interconnectについて本当のこと
1. 相互接続により出力トラフィックコストを削減
2. 高速で信頼性の高い低遅延ネットワーク
3. ポップでデータをキャッシュするために使用されるクラウド相互接続
4. グーグルポップが利用できない場合にパートナーで使用
<details><div>
    答え：１，２，４
</div></details>

### Q. クラウドCDNは、コンテンツを配信するための待ち時間を短縮します
1. true
2. false
3. 
4. 
<details><div>
    答え：１
</div></details>

### Q. Google Cloud Platformで提供される3種類のネットワークとは何ですか？
1. ギガビットネットワーク、10ギガビットネットワーク、および100ギガビットネットワーク
2. デフォルトネットワーク、自動ネットワーク、およびカスタムネットワーク
3. ゾーン、地域、およびグローバル
4. ipv4ユニキャストネットワーク、ipv4マルチキャストネットワーク、ipv6ネットワーク
<details><div>
    答え：２
</div></details>

### Q. Google Cloud DNSサービスの使用目的
1. 2つのネットワーク間に安全な通信を作成する
2. そのドメイン名サービス
3. ファイアウォールルール
4. その仮想プロバイダークラウド
<details><div>
    答え：２
</div></details>

### Q. サブネットは複数のリージョンにまたがることができます
1. true
2. false
3. 
4. 
<details><div>
    答え：２
</div></details>

### Q. クラウドルーターが役立ちます
1. 安全な接続をセットアップするためのクラウド相互接続
2. スループットを向上させるクラウドvpn
3. クラウド相互接続を使用する際の手動ネットワーク構成を削減
4. ネットワークの動的検出を行うクラウドvpn
<details><div>
    答え：３，４
  暗号化通信はデフォルトでない
  スループット向上はロードバランサー
</div></details>

### Q. ダイレクトピアリングのベストユースケースとは
1. 顧客はGoogle Popへのコロケーションを持っています
2. サービスにはslaが必要です
3. プライベートMPLS回線が必要
4. 顧客は、Googleの他のデータではなくgcpデータのみを交換したい
<details><div>
    答え：４
</div></details>

### Q. Googleには、クラウドインターコネクトを使用する場合にのみ使用される光ファイバーネットワークがあります
1. true
2. false
3. 
4. 
<details><div>
    答え：２
</div></details>

### Q. デフォルトVPCと自動VPSは同じです
1. true
2. false
3. 
4. 
<details><div>
    答え：２
</div></details>

### Q. クラウドVPNについて正しい記述
1. コロケーション施設にある場合にのみ使用
2. 2つのネットワーク間にipsecセキュアトンネルを作成します
3. 出力トラフィックコストを削減する
4. 公共のインターネットで使用できます
<details><div>
    答え：２，４
</div></details>

### Q. クラウドCDNは、次のシナリオで使用できます
1. ビデオストリーミング
2. 動的なWebコンテンツ
3. 分析データ
4. 静的コンテンツ
5. 画像キャッシュ
<details><div>
    答え：３，５
</div></details>

### Q. クラウドVPNは、パブリックインターネット経由でデータセンターをGCPに接続するために使用できる唯一のサービスです
1. true
2. false
3. 
4. 
<details><div>
    答え：１
</div></details>

### Q. クラウドVPNは地域サービスです
1. true
2. false
3. 
4. 
<details><div>
    答え：２
</div></details>

### Q. キャッシュされたPOPの場所にコンテンツが見つからない場合-Cloud CDNが次にデータを検索する場所
1. 近くのキャッシュ
2. クラウドストレージ
3. クラウドSQL
4. バックエンドサービス
<details><div>
    答え：１
</div></details>

### Q. すべてのニーズにデフォルトのVPCネットワークを使用するベストプラクティス
1. true
2. false
3. 
4. 
<details><div>
    答え：１
</div></details>

### Q. つのネットワークからVMを接続し、外部IPアドレスを持たない他のネットワークのVMに接続するために使用されるNATインスタンス
1. true
2. false
3. 
4. 
<details><div>
    答え：２
</div></details>

### Q. VPCの真実
1. vpcはリージョンリソースごと
2. プロジェクトでvpcを作成できます
3. vpcはマネージドサービスです
4. 仮想ネットワークは、データをキャッシュするためのポップロケーションに関連しています
<details><div>
    答え：３
</div></details>

### Q. デフォルトモードのネットワーク（VPC）では、リソースは設定を変更せずに互いに通信できます
1. true
2. false
3. 
4. 
<details><div>
    答え：１
</div></details>

### Q. IN GCP-次のルールに基づいてクラウドCDNにデータをキャッシュできます
1. クエリ文字列ブラックリスト
2. ヘルスチェックルール
3. サブネットクエリの検証
4. ファイアウォールルール
<details><div>
    答え：１
</div></details>

### Q. クラウドDNSは100％の稼働時間を提供します
1. true
2. false
3. 
4. 
<details><div>
    答え：１
</div></details>

## 本テスト
### Q. TerramEarthのケーススタディを参照して、次の質問に答えてください。 TerramEarthはFTPファイルアップロードプロセスのパフォーマンスを向上させたいと考えていますが、次のオプションのうちどれを使用できますか？
1. 安全な通信を使用する-ftpではなくsftp
2. アップロードする前にcsvファイルをバイナリファイルに変換します
3. ファイル形式のためにcsvファイルをxml jsonに変換する
4. ストリームを使用してイベントをアップロードする
<details><div>
    答え：4
</div></details>

### Q. 正誤問題：永続ディスクは、仮想マシンで利用可能なネットワーク接続ストレージオプション
1. true
2. false
3. 
4. 
<details><div>
    答え：1
</div></details>

### Q. TerramEarthのケーススタディを参照して、次の質問に答えてください。 TerramEarthは、分析を使用して顧客をどのように支援できますか？
1. データを機械学習に取り込み、予測分析を使用して障害を理解する
2. 現在の顧客の要件を満たすために既存のロジックを改善する
3. データをbigtableにロードし、分析を行うために独自のSQLを設計できます
4. データをbigqueryに取り込み、独自のカスタムロジックを記述して、事前に障害を特定する予測分析を行うことができます。
<details><div>
    答え：4
  １？
</div></details>

### Q. 次の質問に回答するには、Mountkirk Gamesのケーススタディを参照してください。 Mountkirk Gamesは、カスタムOS要件のゲームバックエンドをホストしたいと考えています。ゲームバックエンドに最適なCompute Serviceは何ですか？
1. cloud function
2. google container engine
3. google compute engine
4. cloud pub/sub
<details><div>
    答え：3
</div></details>

### Q. プライベートデータセンターで実行されているリレーショナルデータベースをGoogle Cloud Platformに移行するタスクがあります。次のデータベースとストレージサービスのどれを選択しますか？
1. persistent disk
2. cloud storage
3. cloud sql
4. big query
<details><div>
    答え：3
</div></details>

### Q. Google Compute Engineで有効なカスタムマシンは次のうちどれですか？
1. 32 vcpu & 30gb ram
2. 3vspu & 3gb ram
3. 0.6 vcpu & 1gb ram
4. 1 vcpu & 0.9 gb ram 
<details><div>
    答え：1
</div></details>

### Q. GAEは、1つを除くすべてに基づいて請求されます
1. 要件に基づいたその他の使用済みサービス
2. ネットワークの進入
3. 使用されるマシンインスタンスのタイプ
4. ネットワーク出口
<details><div>
    答え：2
</div></details>

### Q. 次の質問に回答するには、Dress4winのケーススタディを参照してください。 同社は、MQシリーズに基づいた統合フレームワークを移行する必要があります。どのGCPサービスを利用できますか？
1. cloud pub/sub
2. cloud function
3. cloud dataproc
4. cloud sql
<details><div>
    答え：1
</div></details>

### Q. GCEのアンマネージドインスタンスグループについて正しいこと
1. 異なるリソースを持つインスタンスを持つことはできません
2. 負荷分散に使用
3. 使用されたgor自動スケーリング
4. ローリング更新を行うことができます
<details><div>
    答え：2
</div></details>

### Q. GCEには、マネージドインスタンスグループとアンマネージドインスタンスグループがあります
1. true
2. false
3. 
4. 
<details><div>
    答え：1
</div></details>

### Q. Google Cloud Storageに移行する企業は、リレーショナルデータベースをGoogleクラウドに移行する必要がありますが、どのようなオプションがありますか？
1. cloud sql
2. cloud bigtable
3. cloud compute service
4. bigquery
<details><div>
    答え：1
</div></details>

### Q. 正誤問題：Google Cloud Platformの次のルールに基づいてCloud CDNにデータをキャッシュできる
1. subnet query validation
2. firewall rules
3. health check rules
4. query string blacklists
<details><div>
    答え：4
</div></details>

### Q. コンテナは、特定の状況で仮想化マシンよりも少ないリソースを消費します
1. true
2. false
3. 
4. 
<details><div>
    答え：1
</div></details>

### Q. Google Cloudインターコネクトに関する本当の声明は何ですか？
1. 相互接続により出力トラフィックコストを削減
2. Googleポップが使用できない場合にパートナーで使用
3. ポップでデータをキャッシュするために使用されるクラウド相互接続
4. 高速で信頼性の高い低遅延ネットワーク
<details><div>
    答え：1,2,4
</div></details>

### Q. 正誤問題：クラウドルーターはBGPリンクを使用してネットワークの変更をアドバタイズします。
1. true
2. false
3. 
4. 
<details><div>
    答え：1
</div></details>

### Q. 次のうち、Google Compute Engineの有効なカスタムマシンではないものはどれですか？
1. 1 vcpu 1gb ram
2. 32 vcpu & 29gb ram
3. 2 vcpu 1.8gb ram
4. 0.6 vcpu & 1gb ram
<details><div>
    答え：4
</div></details>

### Q. Cloud Storage Bucketのストレージクラスを定義すると、オブジェクトを別のストレージクラスに保存することはできません。
1. true
2. false
3. 
4. 
<details><div>
    答え：2
</div></details>

### Q. 会社は既存の仮想マシンをGoogle Cloud Platformに移行する必要がありますが、どのオプションを選択しますか？
1. オンプレミスvm計算エンジンを移行してvmを作成します
2. 既存のパブリックイメージを使用したgcp計算エンジンとソフトウェアの再インストール
3. アプリケーションを再作成して、Google App EngineまたはContainer Engineにデプロイできるようにします
4. カスタムイメージをgcpにインストールできません
<details><div>
    答え：1
</div></details>

### Q. アンマネージドインスタンスグループではオートスケーラーはできません
1. true
2. false
3. 
4. 
<details><div>
    答え：2
</div></details>

### Q. TerramEarthのケーススタディを参照して、次の質問に答えてください。 TerramEarthは、顧客が燃料効率を改善するためにさまざまな運用パラメーターを推奨できるように支援したいと考えています。プロセスをセットアップするにはどのツールを推奨しますか？
1. クラウドSQLを使用して、クラウドデータラボを使用して分析を行う
2. クラウドマシンラーニングを使用してモデルをトレーニングし、推奨事項を生成して構成パラメーターを提示します
3. 集約されたデータを永続ディスク-ssdに保存し、仮想マシンを使用してカスタムプログラムを展開して分析を行う
4. 分析と集約にbigtableを使用して、燃料効率に必要なパラメーターを考え出す
<details><div>
    答え：2
</div></details>

### Q. 次の質問に回答するには、Mountkirk Gamesのケーススタディを参照してください。 静的コンテンツを送信してバックエンドサーバーで処理された画像に基づいてゲームデバイスに配信するときに、遅延の問題に直面している会社。 これらの画像は特定のゲーマー向けに作成されたものであり、すべての人向けではありません。 適切なサービスと費用対効果の高いものは何でしょうか？
1. イメージを作成し、クラウド機能を使用して、要件に基づいてイメージで応答します
2. イメージを生成してクラウドストレージに保存し、数日後にイメージを削除するライフサイクルポリシーを設計する
3. 仮想マシンを使用して、cdnがこれらのイメージを顧客に配信できるようにします
4. 画像配信にクラウドCDNを使用する
<details><div>
    答え：2
</div></details>

### Q. TerramEarthのケーススタディを参照して、次の質問に答えてください。 TerramEarthは、既存のETL処理ロジックを変更して、マネージドサービスとしてGoogle Cloud Platformを活用したいと考えています。最適なサービスは何ですか？
1. 永続ディスクへのデータへのpub / subのクラウド
2. etl処理のためにGoogle仮想マシンにApacheビームをインストールする
3. データウェアハウスへの変換とロードにGoogleクラウドデータフローを使用する
4. Google Compute Engineに独自のetlツールをインストールし、データウェアハウスへの変換とロードに使用します
<details><div>
    答え：3
</div></details>

### Q. 会社はCloud SQLを何日も使用していますが、アプリケーションはMYSQLのパフォーマンスの問題に直面しています。 どのオプションを使用できますか？
1. クラウドストレージのマルチリージョンデータベースにデータを転送する
2. mysqlの複数のインスタンスを作成します
3. クラウドコンピューティングエンジンにOracleをインストールしてスケーリングする
4. 読み取り操作用の読み取りレプリケーションを作成する
<details><div>
    答え：4
</div></details>

### Q. Cloud Storageオブジェクトを1秒に1回未満更新した場合、どのエラーを取得できますか？！
1. 202 accepted
2. you dont get errors
3. 500 internal server error
4. 503 service unavaliale error
5. 404 page not found
<details><div>
    答え：4
</div></details>

### Q. ダイレクトピアリングの最適なユースケースは何ですか
1. 顧客はサービスにslaを必要とします
2. 顧客はgcpデータのみを交換し、Googleの他のデータは交換したくない
3. 顧客はGoogle Popと同じ場所にいる
4. プライベートmpls回線が必要
<details><div>
    答え：2
</div></details>

### Q. GAE Flexible Envについてどのステートメントが当てはまらないか。
1. gaeは事前に構成されたサンドボックスランタイムです
2. dockerfileでenvをカスタマイズできます
3. 常にvmにアクセスする必要があります
4. CPUとメモリを構成できます
<details><div>
    答え：1
</div></details>

### Q. 次のGoogle Cloud PlatformのデータベースおよびストレージサービスのどれがACIDトランザクションを提供し、世界中の数百のノードに水平に拡張できます。
1. cloud spanner
2. cloud cdn
3. cloud storage
4. cloud sql
<details><div>
    答え：1
</div></details>

### Q. コンテナは、仮想マシンよりも少ないリソースを消費するという問題を解決しますが、次の問題のいずれかを追加します
1. リソースの分配
2. 仮想化環境へのインストール
3. コンテナは解決策と問題
4. オーケストレーションとライフサイクルの管理
<details><div>
    答え：4
</div></details>

### Q. どのデータベースサービスが、構造化データを保存するためのデータウェアハウス機能を提供し、インフラストラクチャを管理せずにデータセットをクエリするための対話型SQLインターフェイスを提供しますか？
1. bigquery
2. cloud dataproc
3. cloud sql
4. cloud data lab
<details><div>
    答え：1
</div></details>

### Q. 次の質問に回答するには、Dress4winのケーススタディを参照してください。 同社は、Google Cloud Platformにキャッシュ（Redisオンプレミス）の実装を取り入れたいと考えています。 Google Cloud Platformにキャッシングをデプロイするために選択できるオプションは何ですか？
1. 仮想マシンを使用してredisをインストールする
2. 永続ディスクを使用する
3. クラウドSQLを使用する
4. クラウドキャッシュを使用する
<details><div>
    答え：1
</div></details>

### Q. 正誤問題：Cloud SQLのオンデマンドバックアップを作成できる
1. true
2. false
3. 
4. 
<details><div>
    答え：1
</div></details>

### Q. Cloud Storage Bucketでオブジェクトを更新する最大頻度は何ですか？
1. 5 second
2. no limit
3. 1 second
4. hourly
5. 1 min
<details><div>
    答え：3
</div></details>

### Q. 正誤問題：クラウドVPNは地域サービスです。
1. true
2. false
3. 
4. 
<details><div>
    答え：2
</div></details>

### Q. Googleのどのサービスが真のサーバーレス環境として扱われるか
1. cloud function
2. google container engine
3. google app engine
4. cloud compute engine
<details><div>
    答え：1
</div></details>

### Q. 次の質問に回答するには、Mountkirk Gamesのケーススタディを参照してください。 同社は、Google Cloud Platformでバックエンドを使用し、仮想マシンインスタンス以外の場所にゲームの状態を保存するストレージソリューションを特定することを決定しました。インスタンスはスケーリング要件に基づいて出入りできるからです。 ゲームの状態を保存する最善の解決策は何ですか？
1. cloud storage
2. cloud datastore
3. virtual machine persistent disk
4. cloud sql
<details><div>
    答え：2
</div></details>

### Q. 他のクラウドと異なる主要なGCPネットワーキングの特徴は何ですか？
1. rfc 1918に準拠するアドレス指定されたipv4をサポート
2. ネットワークトポロジはアドレスレイアウトに依存しません
3. 他のクラウドネットワークとは異なり、アクセスリストとファイアウォールルールが利用可能
4. データに「遅延配信」のタグを付けることができ、設定した日時に配信されます
<details><div>
    答え：2
</div></details>

### Q. Google Cloud DNSサービスの目的は何ですか？
1. 2つのネットワーク間に安全な通信を作成する
2. ファイアウォールルール
3. そのドメイン名サービス
4. その仮想プライベートクラウド
<details><div>
    答え：3
</div></details>

### Q. 次の質問に回答するには、Dress4winのケーススタディを参照してください。 会社は、Apache BeamをGoogle Cloud Platformに移行する必要がありますが、どのようなオプションがありますか？
1. DataFlow Managed Service を使用する
2. bigquery etlエンジンを使用する
3. dataprocを使用する
4. 仮想マシンにApache Beamをインストールし、必要に応じて自動スケーリングベースを使用します
<details><div>
    答え：1
</div></details>

### Q. Google Cloud Platformで提供される3種類のネットワークとは何ですか？
1. ipv4ユニキャストネットワーク、ipv4マルチキャストネットワーク、ipv6ネットワーク
2. デフォルトネットワーク、自動ネットワーク、およびカスタムネットワーク
3. ゾーン、地域、およびグローバル
4. ギガビットネットワーク、10ギガビットネットワーク、および100ギガビットネットワーク
<details><div>
    答え：2
</div></details>

### Q. 正誤問題：クラウドVPNは、パブリックインターネット経由でデータセンターをGCPに接続するために使用できる唯一のサービスです
1. true
2. false
3. 
4. 
<details><div>
    答え：1
</div></details>

### Q. Cloud Storageオブジェクトの最大サイズは何ですか
1. 5tb
2. 5kb
3. 1kb
4. there is no limit
5. 5gb
<details><div>
    答え：1
</div></details>

### Q. 次のうち、Google Compute Engineで利用できる有効な定義済み仮想マシンではないものはどれですか？
1. high cpu
2. standard
3. shared core
4. high memory
5. high cpu & high memory
<details><div>
    答え：5
</div></details>

### Q. 事前定義されたvm構成ではなく、カスタム構成を作成することをお勧めします
1. true
2. false
3. 
4. 
<details><div>
    答え：2
</div></details>

### Q. 正誤問題：クラウドVPNの使用-複数のVPNトンネルでECMPを実行して、より高いスループットを実現できます。
1. true
2. false
3. 
4. 
<details><div>
    答え：1
</div></details>

### Q. 各Cloud Spanner ノードによって提供される適切なQPSとは
1. 2k
2. 1 billion
3. 1 million
4. 1 trillion
5. 10k
<details><div>
    答え：1
</div></details>

### Q. 複数の仮想マシン間で読み取り専用データを共有するためにどのストレージサービスを使用しますか？
1. local ssd
2. cloud storage
3. persistent disk
4. 
<details><div>
    答え：3
</div></details>

### Q. 正誤問題：Google CloudアプリケーションからのみCloud Storageにアクセスできる
1. true
2. false
3. 
4. 
<details><div>
    答え：2
</div></details>

### Q. 正誤問題：クラウドDNSは100％の稼働時間を提供する
1. true
2. false
3. 
4. 
<details><div>
    答え：1
</div></details>

### Q. 次の質問に回答するには、Dress4winのケーススタディを参照してください。 Dre4winは、Google Cloud PlatformのDRサイトを検討していますが、VPN接続速度について懸念しています。 クラウドアーキテクトとして、どのソリューションをお勧めしますか？
1. 企業はGoogleダイレクトピアリングを利用できます
2. 企業は、スループットを高めるために複数のVPNトンネルを追加できます
3. 会社は、バックアップネットワークとしてパブリックインターネットを使用できます。
4. クラウドVPNは管理されたサービスであり、ネットワークスループットには問題ありません
<details><div>
    答え：2
</div></details>

### Q. Google Cloud Platformに移行する企業は、リレーショナルデータベースをGoogleクラウドに移行する必要があります。マネージドサービスとしてどのようなオプションがありますか？
1. oracle
2. cloud storage
3. mysql
4. teradata
<details><div>
    答え：3
</div></details>

### Q. 
1. 
2. 
3. 
4. 
<details><div>
    答え：
</div></details>
