# 練習問題
## Q1. 企業は、既存の仮想マシンをGoogle Cloud Platformに移行する必要があります。どのようなオプションがありますか？
1. 既存のパブリックイメージからgcpコンピューティングエンジンを使用し、ソフトウェアを再インストールする
2. オンプレミスvmを計算エンジンに移行してvmを作成します
3. アプリケーションを再作成して、Google App EngineまたはContainer Engineにデプロイできるようにします
4. カスタムイメージをgcpにインストールすることはできません
<details><div>
    答え：２
</div></details>

## Q2. 事前定義されたVM構成を使用する代わりに、カスタム構成を作成すると常に良い?
1. True
2. False
<details><div>
    答え：2
</div></details>

## Q3. 次のうち、Google Cloud Platformで利用できる有効な定義済み仮想マシンタイプではないものはどれですか？
1. High Memory
2. High CPU
3. High Memory and CPU
4. Standard
5. Standard Core
<details><div>
    答え：3
</div></details>

## Q4. 次のうち、Google Compute Engineの有効なカスタムマシンではないものはどれですか？
1. 1 vCPU 1GB RAM
2. 2 vCPU 1.8GB RAM
3. 0.6 vCPU 1GB RAM
4. 32 vCPU 29GB RAM
<details><div>
    答え：3
</div></details>

## Q5. 会社は、バックエンドのビデオ処理要件に高いコンピューティング要件を持っています。どのオプションが事前定義されたマシンに最適ですか？
1. Standard
2. High CPU - Because it contains more CPU over RAM
3. High Memory - Because it contains high RAM over CPU
4. High Memory and CPU - Because it contains more Momory and CPU over
<details><div>
    答え：2
</div></details>

## Q6. Google Compute Engine（VM）に接続できる永続ディスクはいくつですか？
1. 5 per VM
2. 1 per CPU
3. 8 per VM
4. 10 per CPU
<details><div>
    答え：4
</div></details>

## Q7. Google Compute EngineのCPUの高い定義済みマシンに関する有効なステートメントでないものは何ですか？
1. You can only have 0.9 GB of RAM per vCPU
2. You can only have even no of CPU's
3. You can have 64TB of Disk but you need 64 vCPU for machine
4. Suitable for high Compute requirements
<details><div>
    答え：3
</div></details>

## Q8. 会社は既存の仮想マシンをGoogle Cloud Platformに移行する必要がありますが、compute Engineから選択する基準は何ですか？
1. カスタムマシンと定義済みマシンを選択します
2. googleクラウドストレージが必要
3. 必要なオペレーティングシステム
4. オペレーティングシステムのカスタマイズ
5. ネットワークストレージ要件
<details><div>
    答え：2
</div></details>

## Q9. Google Compute Engineのパフォーマンスの考慮事項、どれが考慮すべき有効なパラメーターではありませんか？
1. VMがホストされているハードウェア
2. ネットワークパフォーマンス
3. Disk IOPS
4. vcpuのない
5. ギガバイトRAM
<details><div>
    答え：１
</div></details>

## Q10. Google Compute Engine（VM）に接続することに関して間違っているものはどれですか？
1. rdpを使用してWindows VMに接続できます
2. サードパーティのsshクライアントを使用してLinux VMに接続することはできません
3. sshを使用してlinux vmに接続できます
4. クラウドコンソールからrdpまたはsshを使用して接続できます
5. クラウドシェルを使用してvmを接続できます
<details><div>
    答え：２
</div></details>

## Q11. ファイアウォールは、サードパーティクライアントからのSSH接続用にGoogle Compute Engineに対してデフォルトで開かれています。
1. True
2. False
<details><div>
    答え：２
</div></details>

## Q12. 外部IPアドレスは、Google Cloud Compute Engine内に表示されます。
1. True
2. False
<details><div>
    答え：１
</div></details>

## Q13. Compute Engineから外部IPアドレスを確認するには、どのコマンドを使用できますか？
1. gcloud
2. ipconfig
3. ipaddress external
4. gsutil
<details><div>
    答え：1
</div></details>

## Q14. 次のマシンタイプにはGPUを接続できません
1. Shared Core
2. Custom machine
3. Standard
4. High Memory
5. High CPU
<details><div>
    答え：1
</div></details>

## Q15. VMネットワークのパフォーマンスは、次のパラメーターに依存します
1. vCPU数
2. RAM容量
3. 接続ディスク数
4. 接続ネットワーク数
<details><div>
    答え：１
</div></details>

## Q16. ローカルSSDを選択する際の考慮事項ではないものは何ですか？
1. ローカルssdは一時的です
2. ローカルssdを持つvmは、ローカルssdに保存されたデータを使用してライブ移行できません
3. ローカルssdは3 TBまで可能
4. vmごとに1つのローカルディスクのみを使用できます
5. ローカルディスクサイズは固定サイズです
<details><div>
    答え：４
</div></details>

## Q17. カスタムVMは、同等の定義済みVMよりもコストが高くなる場合があります。
1. TRUE
2. FALSE
<details><div>
    答え：１
</div></details>

## Q18. Google Compute EngineのvCPUの数は、CPUプラットフォームに依存しています。
1. TRUE
2. FALSE
<details><div>
    答え：１
</div></details>

## Q19. GCEには、マネージドインスタンスグループとアンマネージドインスタンスグループがあります。
1. TRUE
2. FALSE
<details><div>
    答え：1
</div></details>

## Q20. アンマネージドインスタンスグループでは自動スケーリングできません。
1. TRUE
2. FALSE
<details><div>
    答え：１
</div></details>

## Q21. GCEのアンマネージドインスタンスグループについて正解はどれですか？
1. 自動スケーリングに使用
2. 負荷分散に使用
3. 異なるリソースを持つインスタンスを持つことはできません
4. ローリング更新を行うことができます
<details><div>
    答え：２
</div></details>

## Q22. マネージドインスタンスグループは次の目的には使用されません
1. ローリング更新
2. 負荷分散
3. 自動スケーリング
4. 異種リソースの管理
<details><div>
    答え：４
</div></details>

## Q23. HTTPロードバランサーのスコープは
1. リージョナル
2. ゾーン
3. 内部
4. グローバル
<details><div>
    答え：４
</div></details>

## Q24. HTTPロードバランサーは、内部通信でIPV4のみをサポートします
1. TRUE
2. FALSE
<details><div>
    答え：１
</div></details>

## Q25. HTTPロードバランサーに関して誤っているステートメントは何ですか？
1. httpロードバランサーはコンテンツに対応していません
2. 複数の地域間で負荷を分散できます
3. 
4. リクエストはクローズドサービングインスタンスにルーティングされます
<details><div>
    答え：１
</div></details>

## Q26. ヘルスチェックは、HTTPロードバランサーの不可欠な部分です。
1. TRUE
2. FALSE
<details><div>
    答え：１
</div></details>

## Q27. HTTPロードバランサーは、常にトラフィックを正常性インスタンスにルーティングします。
1. TRUE
2. FALSE
<details><div>
    答え：１
</div></details>

## Q28. ロードバランサーは、次の負荷分散アルゴリズムを使用して、インスタンスがビジーかどうかを確認します
1. CPU と RAMの利用
2. RAMの利用
3. CPUの利用
4. リクエスト数（RPS） と CPUの利用
<details><div>
    答え：４
</div></details>

## Q29. GAEには、1つを除く以下の機能があります
1. トラフィック分割
2. アプリケーションバージョニング
3. 標準とフレキシブルな環境
4. モニタリング、ロギング、エラーレポート
5. DNS
<details><div>
    答え：５
</div></details>

## Q30. GAEは、VMを管理し、GCPが下線のハードウェアとネットワークを管理するマネージドサービスです。
1. TRUE
2. FALSE
<details><div>
    答え：２
</div></details>

## Q31. GAEはコンテナオーケストレーションを提供します。
1. TRUE
2. FALSE
<details><div>
    答え：２
</div></details>

## Q32. 1つを除く次のスケーリングを構成できます。
1. 手動
2. 自動
3. ハイブリッド
4. 内容に沿って
<details><div>
    答え：3
</div></details>

## Q33. 1つを除くGAEの次の構成を選択できます。
1. 別のマシンを選択する
2. スケーリングを設定する
3. カスタムVMを選択する
4. インスタンス数
<details><div>
    答え：４
</div></details>

## Q34. GAE標準環境に当てはまらないものは何ですか？
1. Dockerコンテナのサポート
2. 事前構成済みのサンドボックス
3. 標準環境のためのGoogle SDK
4. 
<details><div>
    答え：１
</div></details>

## Q35. GAE Flexible Envに当てはまらないこと
1. サンドボックスランタイムを事前設定します
2. CPUとメモリを設定できます
3. dockerfileでenvをカスタマイズできます
4. VMへのルートアクセスがあります
<details><div>
    答え：１
</div></details>

## Q36. GAEは、1つを除くすべてに基づいて請求されます
1. 使用されるマシンインスタンスのタイプ
2. ネットワーク出口
3. 要件に基づいて使用されるその他のサービス
4. ネットワーク入口
<details><div>
    答え：４
</div></details>

## Q37. GKEは、GCP上のKubernetesの実装であり、Google Cloud Platformのマネージドサービスです。
1. TRUE
2. FALSE
<details><div>
    答え：1
</div></details>

## Q38. コンテナは、特定の状況での仮想化マシン上のリソース消費量が少なくなります。
1. TRUE
2. FALSE
<details><div>
    答え：1
</div></details>

## Q39. コンテナは、仮想マシンよりも少ないリソースを消費するという問題を解決しますが、次の問題を解決します
1. オーケストレーションとライフサイクルの管理
2. 仮想化環境へのインストール
3. コンテナは解決策であり問題です
4. リソース配分
<details><div>
    答え：1
</div></details>

## Q40. GKEは、1つを除く以下の機能をサポートします
1. Auto Scaling
2. Stackdriver Logging
3. Docker Format
4. Cloud IAM integration
5. Preemptible Machine
<details><div>
    答え：5
</div></details>

## Q41. GKWには、1つのマスターと1つ以上のワーカーノードが含まれます。
1. TRUE
2. FALSE
<details><div>
    答え：1
</div></details>

## Q42. GKEマスターノードは、以下を除くすべてを管理します
1. Schedules POD Creation
2. POD Deletion
3. Runs POD
4. Acts as endpoint to GKE cluster
<details><div>
    答え：3
</div></details>

## Q43. ポッドには次のコンポーネントが含まれます
1. Doket Runtime
2. Cloud Service Integration
3. Kubelete Agent
4. Doker Runtime
<details><div>
    答え：2
</div></details>

## Q44. ポッド共有内のコンテナー
1. IP address and Namespace
2. IP address and Port
3. Does not share anything
4. Same application
<details><div>
    答え：1
</div></details>

## Q45. GKEサービスは以下を提供します
1. Acts Load balancer
2. Resource Manager and scheduler
3. Provide single IP adress for pods
4. HA and Autoscaller
<details><div>
    答え：2
</div></details>

## Q46. GKE Deploymentsはどの目的のためのものですか
1. Supports HA and Autoscaller
2. Resource Manager and scheduler
3. For single endpoint to cluster
4. Procides single IP to pods
<details><div>
    答え：1
</div></details>

## Q47. Googleのどのサービスが真のサーバーレス環境として扱われますか？
1. Cloud Compute Engine
2. Google App Engine
3. Google Container Engine
4. Cloud Function
<details><div>
    答え：4
</div></details>

## Q48. GCPのどのコンピューティングサービスをウェブサイトのホスティングに選択しませんか？
1. Cloud Compute Engine
2. Google App Engine
3. Google Container Engine
4. Cloud Function
<details><div>
    答え：4
</div></details>

## Q49. Cloud Functionは、Dockerコンテナーでアプリケーションを実行します。
1. True
2. False
<details><div>
    答え：2
</div></details>

## Q50. 次の文のうち、Cloud Functionに当てはまらないものはどれですか？
1. サーバーレス
2. 実行時にのみ変更
3. イベントドリブン
4. その実行はdocker containerです
<details><div>
    答え：４
</div></details>

## Q51. Cloud Functionは、次のいずれかをのぞく、すべてのトリガーをサポートしています
1. HTTP
2. Cloud Storage
3. Cloud Pub/Sub
4. Firebase
5. Cloud SQL
<details><div>
    答え：5
</div></details>

## Q52. データセンター内の単一マシンで実行されている標準のリレーショナルデータベースをクラウドに移行する必要がある場合、どのデータストレージサービスを選択できますか？
1. Cloud SQL
2. BigQuery
3. Persistent Disk
4. Cloud Storage
<details><div>
    答え：1
</div></details>

## Q53. どのGCPデータストレージサービスがACIDトランザクションを提供し、何千ものノードに拡張できますか？
1. Cloud Storage
2. Cloud CDN
3. Cloud Spanner
4. Cloud SQL
<details><div>
    答え：3
</div></details>

## Q54. どのデータストレージサービスが、データを格納するためのデータウェアハウスサービスを提供し、データを照会するためのインタラクティブなSQLインターフェイスも提供しますか？
1. BigQuery
2. Cloud DataProc
3. Cloud Data lab
4. Cloud SQL
<details><div>
    答え：1
</div></details>

## Q55. 企業はデータを保存用に保存する必要があります。データを低コストで保存するのに最適な方法
1. Cloud Storage with Coldline Storage Class
2. Cloud SQL
3. Virtual Machine
4. Cloud Storage with Regional Storage Class
5. Cloud BigQuery
<details><div>
    答え：1
</div></details>

## Q56. 靴会社は、Google Cloudに靴の多数の画像を保存するためにGCPで最適なストレージソリューションを探しています
1. Google Compute Engine storage
2. Google Container Service
3. Google Cloud Storage
4. Google Cloud data-proc
<details><div>
    答え：3
</div></details>

## Q57. 会社は静的ウェブサイトをクラウドでホストしたいと考えています。管理オーバーヘッドなしで静的ウェブアプリケーションをホストするための最良のソリューションは何ですか
1. Google Container Engine
2. Google Compute Service
3. Google Cloud Storage
4. Google App Engine
5. Google dose not support static hosting
<details><div>
    答え：3
</div></details>

## Q59. 会社は、高可用性と低遅延を必要とし、世界中からアクセスする必要があるWebサイトの画像を保存する必要があります。 最良の選択肢は何ですか
1. Google Cloud SQL
2. Google Cloud Storage
3. Store it in on premises Data Center
4. Google Cloud Virtual Machine
<details><div>
    答え：2
</div></details>

## Q60. 会社は、シンガポール地域でのみアクセスされるビデオファイルを保存する必要があります。 最適なストレージオプションは何ですか
1. Cloud Storage with Regional Storage Class
2. Cloud Virtual Machine from Singapore region
3. Cloud Storage with Multi-regional Storage Class
4. Cloud Function
5. Cloud CDN
<details><div>
    答え：1
</div></details>

## Q61. 企業は、その存続期間中にアクセスされる場合とされない場合があるが、アクセスが必要な場合、迅速かつ容易に利用可能であるべき規制およびコンプライアンスデータのストレージコストを削減したいと考えています。
1. Cloud Storage with Regional Storage Class
2. Cloud Storage with Coldline Storage Class
3. Cloud Storage with Nearline Storage Class
4. Cloud Persistent Disk
5. VMs local SSD
<details><div>
    答え：2
</div></details>

## Q62. すべての部門および事業単位とすべてのバケットで使用されるクラウドストレージは、すべてのアプリケーション/ユーザーにアクセスできます。 コンプライアンス部門は、バケットに保存されている一部の機密情報が保護されていないことに気付きました。 コンプライアンスは、迅速な修正としてバケットへのアクセスを制限できることも発見しました。 リーガルは、実際のファイルへのアクセスを可能にするさまざまなオプションを提案しています。この状況に最適なソリューションは何ですか
1. IAMを使用して個々のオブジェクトへのアクセスを制限し、長期的なソリューションは必要ありません
2. ACLを使用して機密オブジェクトへのアクセスを制限し、長期的には情報の用途と機密性に応じて個別のバケットを作成します
3. 何もする必要はありません-クラウドストレージにはデータを保護するための制限と暗号化があります
4. すべてのアプリケーションへのすべてのバケットへのアクセスを停止し、アプリケーションが問題を解決するためにソリューションを停止して作業できるようにします
<details><div>
    答え：2
</div></details>

## Q63. アプリケーションと用途はファッションデザインにアクセスしており、多くのデザイナーによって継続的に更新されています。これらのデザインはCloud Storageに保存されます。 多くのデザイナーは、個々のデザインに取り組んでおり、誰が更新しているかを追跡するのは難しいです。 この状況に最適なソリューションは何ですか
1. すべての設計者に、それぞれが密接に共同注文するように依頼し、設計の変更をクラウドストレージで行う
2. クラウドストレージは履歴を自動的に追跡するため、誰が変更を行ったかがわかります
3. ここでは有効なユースケースではありません-クラウドストレージのオブジェクトを上書きすることはできません
4. Cloud Storageへのアクセスをすべてのデザイナーに制限し、1人をデザインの共同注文ラインに任命します
5. バージョン管理を有効にして、オブジェクトの変更を追跡できるようにします
<details><div>
    答え：5
</div></details>

## Q64. バケツについて本当のこと
1. 同じ名前で複数のバケットを作成できます
2. バケットをネストして、ディレクトリ構造のようにファイルを保存できます
3. プロジェクトごとに1つのバケットが許可されます
4. 必要なだけ多くのオブジェクトをバケットに書き込むことができます
<details><div>
    答え：4
</div></details>

## Q65. Cloud Storageオブジェクトには読み取りと書き込みの制限があります
1. true
2. false
<details><div>
    答え：1
</div></details>

## Q66. Cloud Storageオブジェクトの最大サイズは何ですか
1. 5kb
2. 5gb
3. 5tb
4. 1kb
5. 制限なし
<details><div>
    答え：３
</div></details>

## Q67. Cloud Storageオブジェクトの最小サイズは何ですか
1. 0byte
2. 5gb
3. 5tb
4. 1kb
<details><div>
    答え：1
</div></details>

## Q69. Cloud Storageバケットのストレージクラスを定義すると、そのバケットのオブジェクトは異なるストレージクラスに保存できません
1. true
2. false
<details><div>
    答え：2
</div></details>

## Q70. Cloud Storage Bucketでオブジェクトを更新する最大頻度は？
1. 1 min
2. 5 second
3. no limit
4. 1 second
5. 1 hour
<details><div>
    答え：4
</div></details>

## Q71. Cloud Storageオブジェクトの更新が1秒に1回未満の場合、どのエラーが発生する可能性がありますか？
1. エラーが発生しない
2. 202 Accepted
3. 500 Internal Server Error
4. 404 Page not found
5. 503 Service Unacailable Error
<details><div>
    答え：5
</div></details>

## Q72. プロジェクトごとのバケット数の制限は何ですか？
1. no limit
2. 2 bucket
3. 10 bucket
4. 100 bucket
5. 500 bucket
<details><div>
    答え：1
</div></details>

## Q73. プロジェクトごとのバケットの作成/削除の制限は何ですか？
1. 2秒ごとにバケットを作成/削除できます
2. 10分ごとにバケットを作成/削除できます
3. 1日ごとにバケットを作成/削除できます
4. 制限はありません
<details><div>
    答え：1
</div></details>

## Q74. Cloud Storageオブジェクトの作成/削除操作のレートはいくらですか？
1. 1秒あたり1つの作成/削除操作
2. 1秒あたり2つの作成/削除操作
3. 1秒あたり10個のオペレーションの作成/削除
4. 制限なし
<details><div>
    答え：4
</div></details>

## Q75. Cloud Storage Bucketのストレージクラスが変更された場合、どうなりますか？
1. 新しいストレージクラスで新しいオブジェクトが作成されます
2. 古いオブジェクトは新しいsotrageクラスに移動されます
3. 新しいsotrageクラスは、サービスの近くにあるため、より高速になります。
4. ストレージ。模倣は10 GBから5TBに増加します。
<details><div>
    答え：1
</div></details>

## Q76. Cloud Storageでどのような操作が最終的に一貫していますか？
1. クラウドストレージオブジェクトの書き込み後に読み取る
2. クラウドストレージオブジェクトの削除後に読み取る
3. オブジェクトのリスト
4. リソースからのアクセスの取り消し
5. リソースへのアクセスの許可
<details><div>
    答え：4
</div></details>

## Q77. Cloud Storage Bucketには2レベルの階層しか作成できませんか？
1. true
2. false
<details><div>
    答え：2
</div></details>

## Q78. 有効にできるのはバージョンのみですが、Cloud Storageオブジェクトのバージョン管理を無効にすることはできません。
1. true
2. false
<details><div>
    答え：2
</div></details>

## Q80. 有効にすると、クラウドストレージはオブジェクトのライブバージョンが上書きまたは削除されるたびに、オブジェクトのアーカイブバージョンとして作成されます。
1. true
2. false
<details><div>
    答え：1
</div></details>

## Q81. オブジェクトの1つのバージョンのみを復元できます。
1. true
2. false
<details><div>
    答え：2
</div></details>

## Q82. Objectのカスタムメタデータを作成できます。
1. true
2. false
<details><div>
    答え：1
</div></details>

## Q83. Cloud Storage Objectのすべてのメタデータアイテムを変更できます。
1. true
2. false
<details><div>
    答え：2
</div></details>

## Q84. 一度設定すると、Cloud Storageオブジェクトのストレージクラスを変更できません。
1. true
2. false
<details><div>
    答え：2
</div></details>

## Q85. Cloud Storage Nearline Storage Classの最小ストレージ期間は？
1. 24 hours
2. no limit
3. 30 days
4. 90 days
5. 1 year
<details><div>
    答え：3
</div></details>

## Q86. Cloud Storage Regional Storage Classの最小ストレージ期間は？
1. 24 hours
2. no limit
3. 30 days
4. 90 days
5. 1 year
<details><div>
    答え：2
</div></details>

## Q87. 6か月に1回アクセスされるレポートを保存するためのデータバックソリューションが必要です。このシナリオに適したストレージクラスは何ですか？
1. Regional Storage Class
2. Multi Regional Storage Class
3. Coldline Storage Class
4. Nearline Storage Class
5. Persistent Disk Storage Class
<details><div>
    答え：4
</div></details>

## Q88. 会社は、AWSからGoogle Cloud Storageにデータを移動したいのですが、どのアプリケーションを使用できますか？
1. Google Cloud Pub/Sub
2. Storage Transfer Service
3. gsutils
4. CLoud SQL
<details><div>
    答え：2
</div></details>

## Q89. Cloud Storage Notificationsの識別に使用できるアプリケーションはどれですか？
1. Cloud pub/sub
2. Cloud Data proc
3. Cloud SQL
4. Cloud Container Engine
<details><div>
    答え：1
</div></details>

## Q90. Google Cloudでアプリケーションをホストしていない場合、Cloud Storageを使用してデータを保存することはできません。
1. true
2. false
<details><div>
    答え：2
</div></details>

## Q91. Google Cloud Applicationsからのみクラウドストレージにアクセスできます。
1. true
2. false
<details><div>
    答え：2
</div></details>

## Q92. 会社がGoogle Cloud Storageに移行し、リレーショナルデータベースをGoogleクラウドに移行する必要があります。マネージドサービスとしてどのようなオプションがありますか？
1. MySQL
2. Oracle
3. Teradata
4. Cloud Storage
<details><div>
    答え：1
</div></details>

## Q93. 会社はCloud SQLを何日も使用していますが、アプリケーションはMYSQLのパフォーマンスの問題に直面しています。 どのオプションを使用できますか？
1. 読み取り操作用の読み取りレプリケーションを作成する
2. mysqlの複数のインスタンスを作成します
3. クラウドコンピューティングエンジンにOracleをインストールしてスケーリングする
4. クラウドストレージへのモードデータ
<details><div>
    答え：1
</div></details>

## Q94. Cloud SQLのオンデマンドバックアップを作成できます。
1. true
2. false
<details><div>
    答え：1
</div></details>

## Q95. ラージインスタンスタイプを作成すると、MYSQLインスタンスを複製できます。
1. true
2. false
<details><div>
    答え：2
</div></details>

## Q96. SSHを使用してCloud SQLマシンインスタンスに接続できます
1. true
2. false
<details><div>
    答え：1
</div></details>

## Q97. Stack-driver監視と統合することはできません
1. true
2. false
<details><div>
    答え：2
</div></details>

## Q98. 障害インスタンスがプライマリになるには、変更を構成する必要があります。
1. true
2. false
<details><div>
    答え：2
</div></details>

## Q99. Cloud SQLは、Googleが提供するMicrosoft SQLサービスです。
1. true
2. false
<details><div>
    答え：2
</div></details>

## Q100. Cloud SQL仮想マシンのセキュリティパッチを監視してインストールする必要があります。
1. true
2. false
<details><div>
    答え：2
</div></details>

## Q101. Cloud SQLはマネージドサービスであり、管理者MYSQLユーザーへのアクセス権はありません。
1. true
2. false
<details><div>
    答え：2
</div></details>

## Q102. Cloud SQL用に仮想マシンをカスタマイズできます
1. true
2. false
<details><div>
    答え：1
</div></details>

## Q103. ディスクのスループットとIOPSは、Cloud SQLインスタンスに接続されたディスクのサイズに依存します。
1. true
2. false
<details><div>
    答え：1
</div></details>

## Q104. CIDRに基づいてCloud SQL接続をブロックまたは有効化できます。
1. true
2. false
<details><div>
    答え：1
</div></details>

## Q105. Googleクラウドプラットフォームでリレーショナル、水平スケーラブル、強力な一貫性、およびPettabyteのスケールを提供するデータベースサービスは何ですか？
1. Cloud SQL
2. Cloud Bigtable
3. Cloud Datastore
4. Cloud Spanner
<details><div>
    答え：4
</div></details>

## Q106. Cloud Spannerは、水平方向にスケーラブルなリレーショナルデータベースです。
1. true
2. false
<details><div>
    答え：1
</div></details>

## Q107. インターライブテーブルは、どのデータベースサービスに実装できますか？
1. Cloud Big table
2. Cloud Datastore
3. Cloud SQL
4. Cloud Spanner
<details><div>
    答え：4
</div></details>

## Q108. Cloud Spannerは、ノードに基づいて課金およびスケーリングされます。
1. true
2. false
<details><div>
    答え：1
</div></details>

## Q109. Cloud Spannerでは、データは保管時に暗号化されません。
1. true
2. false
<details><div>
    答え：2
</div></details>

## Q110. 各クラウドスパナノードによって提供される読み取りQPSとは何ですか？
1. 2k
2. 1 million
3. 1 billion
4. 1 trillion
5. 10 k
<details><div>
    答え：5
</div></details>

## Q111. 各クラウドスパナノードによって提供される書き込みQPSとは何ですか？
1. 2k
2. 1 million
3. 1 billion
4. 1 trillion
5. 10 k
<details><div>
    答え：1
</div></details>

## Q112. 永続ディスクは、仮想マシンで使用可能なネットワーク接続ストレージオプションです。
1. true
2. false
<details><div>
    答え：1
</div></details>

## Q113. どのストレージサービスを使用して、複数の仮想マシンに読み取り専用データを添付できますか？
1. Cloud Storage
2. Persistent Disk
3. Local SSD
<details><div>
    答え：2
</div></details>

## Q114. 次のストレージオプションのどれがブロックストレージとして使用されますか？
1. Local SSD
2. Local Magnetic Disk
3. Persistent Disk
4. Cloud Storage
<details><div>
    答え：3
</div></details>

## Q115. 永続ディスクに使用できる最大サイズは？
1. 16gb
2. 5tb
3. 64tb
4. 1pb
<details><div>
    答え：3
</div></details>

## Q116. 永続ディスクの最大スループットは、ディスクのサイズに依存しません。
1. true
2. false
<details><div>
    答え：2
</div></details>

## Q117. ローカルSSDデータは複数の仮想マシン間で保持されます。
1. true
2. false
<details><div>
    答え：2
</div></details>

## Q118. Google Cloud Platformのネットワーキングの重要な特徴は何ですか？
1. データに「遅延配信」のタグを付けることができ、設定した日時に配信されます
2. 他のクラウドネットワークとは異なり、アクセスリストとファイアウォールルールを使用できます
3. ネットワークトポロジはアドレスレイアウトに依存しません。
4. rfc 1918に準拠するsuppoets ipv4アドレス
<details><div>
    答え：３
</div></details>

## Q119. VM内で解決できるIP
1. 内部IPアドレス
2. セカンダリIPアドレス
3. 外部IPアドレス
4. vm内のIPアドレスを解決できない
<details><div>
    答え：１
</div></details>

## Q120. Cloud VPNを拡張する方法
1. 複数のクラウドVPN
2. クラウドVPNはスケーリングを必要としません
3. スループットを高めるために複数のトンネルを追加します
4. オプションでgoogles cloud cdnを使用できます
<details><div>
    答え：３
</div></details>

## Q121. 1 GBPS接続が必要な場合-どの相互接続がコストを考慮した最も実行可能なオプションです
1. carrier peering
2. direct peering
3. cloud vpn
4. cloud interconnect with paetner integration
<details><div>
    答え：３
</div></details>

## Q122. サーバーが機密情報を処理しています。インターネットから隔離するために外部IPアドレスを削除できます
1. true
2. false
<details><div>
    答え：１
</div></details>

## Q123. ロードバランサーの構成にアクセスするために使用される要塞ホスト
1. true
2. false
<details><div>
    答え：２
  ロードバランサーを使用しない場合に
</div></details>

## Q124. Google Virtual Network Subnetsはリージョンリソースです
1. true
2. false
<details><div>
    答え：１
  グローバル
</div></details>

## Q125. どの相互接続サービスがGCPの下にあるか
1. direct peering
2. cloud vpn
3. cloud interconnect
4. partner peering
<details><div>
    答え：２，３
  ピアリングは違う
</div></details>

## Q126. 企業は、GCPに接続するためにセキュアチャネルを備えた500 Mbps接続を必要とします。低コストを維持するために、次の相互接続のいずれかが適切です
1. cloud cdn
2. cloud vpn
3. cloud dns
4. dedicated interconnect
<details><div>
    答え：２
  Cloud VPNで十分
</div></details>

## Q127. VPNの代わりにクラウドインターコネクトまたはダイレクトピアリングを使用する理由は何ですか？
1. グーグルは、クラウド相互接続およびダイレクトピアリングのSLASのみを提供します
2. vpnはIPアドレスの割り当てとcidrサブネットの制御を提供しませんが、クラウド相互接続と直接ピアリングは制御します
3. クラウド相互接続と直接ピアリングは、使用していないときに簡単にオン/オフできるため、安価です。
4. クラウド相互接続とダイレクトピアリングにより、データ集約型アプリケーションの可用性が向上し、待ち時間が短縮され、コストが削減されます。
<details><div>
    答え：４
</div></details>

## Q128. クラウドCDNは、次のサービス構成のいずれで有効にすることができます
1. app engine
2. virtual machine
3. container engine
4. load balancer
<details><div>
    答え：４
</div></details>

## Q129. FQDNに内部DNSサーバーを使用した内部IPアドレス
1. true
2. false
<details><div>
    答え：１
</div></details>

## Q130. クラウドCDNはバックエンドサービスの負荷を増加させます
1. true
2. false
<details><div>
    答え：２
</div></details>

## Q131. gcloudコマンドを使用して、VM内の外部IPアドレスを解決できます
1. true
2. false
<details><div>
    答え：１
</div></details>

## Q132. 会社は、どのネットワークが適切かSLAとの相互接続を必要としますか？ （2つ選択）
1. cloud interconnect
2. direct peering
3. cloud vpn
4. carrier peering
<details><div>
    答え：１，３
</div></details>

## Q133. 10Gbpsネットワークが必要で、Googleのコロケーション施設に存在する場合、クラウド相互接続を使用してインフラストラクチャをGoogleに接続します
1. true
2. false
<details><div>
    答え：１
</div></details>

## Q134. カスタムイメージ仮想マシンファイアウォールは既にインターネット用に開かれています
1. true
2. false
<details><div>
    答え：１
</div></details>

## Q135. Googleクラウドプロジェクトごとに最大5つのネットワークを作成できます
1. true
2. false
<details><div>
    答え：１
</div></details>

## Q136. カスタムネットワークの真実
1. リソースは互いに通信できます
2. すべてのリージョンに対してサブネットが作成されます
3. ルートはデフォルトでは定義されていません
4. ファイアウォールルールは作成されません
<details><div>
    答え：３，４
</div></details>

## Q137. クラウドルーターの目的は何ですか？それはなぜ重要ですか？
1. トポロジを自動的に検出して共有できる動的vpnを実装し、手動の静的ルートメンテナンスを削減します。
2. クラウドルーターを使用すると、複数のVPNでラウンドロビンスイッチングを実行できるため、帯域幅を組み合わせて、実際に内部で提供されるよりも優れたスループットを得ることができます。
3. 一方のvpnを他方の直接ピアリングに接続します。これはvpn単独よりも高速です。
4. これは、Googleが提供するがgcpでホストされるハードウェアルーターです。
<details><div>
    答え：１
</div></details>

## Q138. 仮想プライベートネットワーク（VPN）の目的は何ですか？
1. VPNはアクセス制御リスト（ACL）とも呼ばれ、ネットワークアクセスを制限します
2. ネットワーク境界のエッジで侵入者を検出する方法です
3. インターネットなどの信頼できない環境を介して2つの信頼できる環境を接続するための安全な通信方法を有効にする
4. 主な目的は、暗号化された形式で保存できるようにデータを暗号化することです
<details><div>
    答え：３
</div></details>

## Q139. クラウドDNSに関する本当の声明は何ですか
1. クラウドDNSは、HTTPロードバランサーのエンドポイントを使用できます
2. クラウドDNS管理サービス
3. クラウドDNSは、プライベートセンターでホストされているサービスと連携できます。
4. クラウドDNSの稼働率は99.9％です
<details><div>
    答え：１，２
  クラウドDNSの稼働率は99.99％です
</div></details>

## Q140. 次の主要な構成に基づくクラウドCDNキャッシュデータ（3つ選択）
1. キャッシュキー
2. クエリ文字列
3. サービスタイプの計算
4. プロトコルとホスト
<details><div>
    答え：１，２，４
</div></details>

## Q141. クラウドルーターは2つのネットワークを安全なチャネルで接続します
1. true
2. false
3. 
4. 
<details><div>
    答え：２
</div></details>

## Q142. NATは転送ルールを使用してトラフィックを内部サーバーに送信します
1. true
2. false
3. 
4. 
<details><div>
    答え：１
</div></details>

## Q. 単一ゾーンに複数のサブネットを作成して、GCPリソースを分離できます
1. true
2. false
3. 
4. 
<details><div>
    答え：１
</div></details>

## Q143. アドレスではなくタグでファイアウォールルールを適用する利点の1つは何ですか？
1. ファイアウォールルールのタグは、vmsが受信する一時IPアドレスを制御します
2. 一致するタグでvmが作成されると、ファイアウォールルールは、割り当てられたIPアドレスに関係なく適用します
3. ネットワークトラフィックのタグは、ネットワークスニッフィングに役立ちます
4. タグは、組織がファイアウォールの請求を追跡するのに役立ちます
<details><div>
    答え：２
</div></details>

## Q144. クラウドルーターはBGPリンクを使用してネットワークの変更をアドバタイズします
1. true
2. false
3. 
4. 
<details><div>
    答え：１
</div></details>

## Q145. クラウド相互接続について本当のこと
1. パブリック相互接続を使用してクラウド相互接続を実装できます
2. クラウドインターコネクトはデフォルトで安全な通信を提供します
3. クラウド相互接続はvpnサービスです
4. パートナー統合を使用して提供されるクラウド相互接続
<details><div>
    答え：４
  プロトコルの暗号化はデフォルトでない
</div></details>

## Q146. クラウドVPNの使用-複数のVPNトンネルでECMPを実行して、より高いスループットを達成できます
1. true
2. false
3. 
4. 
<details><div>
    答え：１
</div></details>

## Q147. Google Cloud Interconnectについて本当のこと
1. 相互接続により出力トラフィックコストを削減
2. 高速で信頼性の高い低遅延ネットワーク
3. ポップでデータをキャッシュするために使用されるクラウド相互接続
4. グーグルポップが利用できない場合にパートナーで使用
<details><div>
    答え：１，２，４
</div></details>

## Q148. クラウドCDNは、コンテンツを配信するための待ち時間を短縮します
1. true
2. false
3. 
4. 
<details><div>
    答え：１
</div></details>

## Q149. Google Cloud Platformで提供される3種類のネットワークとは何ですか？
1. ギガビットネットワーク、10ギガビットネットワーク、および100ギガビットネットワーク
2. デフォルトネットワーク、自動ネットワーク、およびカスタムネットワーク
3. ゾーン、地域、およびグローバル
4. ipv4ユニキャストネットワーク、ipv4マルチキャストネットワーク、ipv6ネットワーク
<details><div>
    答え：２
</div></details>

## Q150. Google Cloud DNSサービスの使用目的
1. 2つのネットワーク間に安全な通信を作成する
2. そのドメイン名サービス
3. ファイアウォールルール
4. その仮想プロバイダークラウド
<details><div>
    答え：２
</div></details>

## Q151. サブネットは複数のリージョンにまたがることができます
1. true
2. false
3. 
4. 
<details><div>
    答え：２
</div></details>

## Q152. クラウドルーターが役立ちます
1. 安全な接続をセットアップするためのクラウド相互接続
2. スループットを向上させるクラウドvpn
3. クラウド相互接続を使用する際の手動ネットワーク構成を削減
4. ネットワークの動的検出を行うクラウドvpn
<details><div>
    答え：３，４
  暗号化通信はデフォルトでない
  スループット向上はロードバランサー
</div></details>

## Q153. ダイレクトピアリングのベストユースケースとは
1. 顧客はGoogle Popへのコロケーションを持っています
2. サービスにはslaが必要です
3. プライベートMPLS回線が必要
4. 顧客は、Googleの他のデータではなくgcpデータのみを交換したい
<details><div>
    答え：４
</div></details>

## Q154. Googleには、クラウドインターコネクトを使用する場合にのみ使用される光ファイバーネットワークがあります
1. true
2. false
3. 
4. 
<details><div>
    答え：２
</div></details>

## Q155. デフォルトVPCと自動VPSは同じです
1. true
2. false
3. 
4. 
<details><div>
    答え：２
</div></details>

## Q156. クラウドVPNについて正しい記述
1. コロケーション施設にある場合にのみ使用
2. 2つのネットワーク間にipsecセキュアトンネルを作成します
3. 出力トラフィックコストを削減する
4. 公共のインターネットで使用できます
<details><div>
    答え：２，４
</div></details>

## Q157. クラウドCDNは、次のシナリオで使用できます
1. ビデオストリーミング
2. 動的なWebコンテンツ
3. 分析データ
4. 静的コンテンツ
5. 画像キャッシュ
<details><div>
    答え：３，５
</div></details>

## Q158. クラウドVPNは、パブリックインターネット経由でデータセンターをGCPに接続するために使用できる唯一のサービスです
1. true
2. false
3. 
4. 
<details><div>
    答え：１
</div></details>

## Q159. クラウドVPNは地域サービスです
1. true
2. false
3. 
4. 
<details><div>
    答え：２
</div></details>

## Q160. キャッシュされたPOPの場所にコンテンツが見つからない場合-Cloud CDNが次にデータを検索する場所
1. 近くのキャッシュ
2. クラウドストレージ
3. クラウドSQL
4. バックエンドサービス
<details><div>
    答え：１
</div></details>

## Q161. すべてのニーズにデフォルトのVPCネットワークを使用するベストプラクティス
1. true
2. false
3. 
4. 
<details><div>
    答え：１
</div></details>

## Q162. 1つのネットワークからVMを接続し、外部IPアドレスを持たない他のネットワークのVMに接続するために使用されるNATインスタンス
1. true
2. false
3. 
4. 
<details><div>
    答え：２
</div></details>

## Q163. VPCの真実
1. vpcはリージョンリソースごと
2. プロジェクトでvpcを作成できます
3. vpcはマネージドサービスです
4. 仮想ネットワークは、データをキャッシュするためのポップロケーションに関連しています
<details><div>
    答え：３
</div></details>

## Q164. デフォルトモードのネットワーク（VPC）では、リソースは設定を変更せずに互いに通信できます
1. true
2. false
3. 
4. 
<details><div>
    答え：１
</div></details>

## Q165. IN GCP-次のルールに基づいてクラウドCDNにデータをキャッシュできます
1. クエリ文字列ブラックリスト
2. ヘルスチェックルール
3. サブネットクエリの検証
4. ファイアウォールルール
<details><div>
    答え：１
</div></details>

## Q166. クラウドDNSは100％の稼働時間を提供します
1. true
2. false
3. 
4. 
<details><div>
    答え：１
</div></details>

## Q. サービス アカウントは手動操作を必要としないシナリオに使用するべきである
1. TRUE
2. FALSE
3. 
4. 
<details><div>
    答え：1
</div></details>

## Q. カスタムのIAMロールに割り当てられている権限を確認する必要があります。どのように対応しますか
1. GCP ConsoleのIAMセクションを使用して情報を表示する
2. gcloud init コマンドを使用して情報を表示する
3. GCP Consoleのセキュリティセクションを使用して情報を表示する
4. GCP ConsoleのAPIセクションを使用して情報を表示する
<details><div>
    答え：1
</div></details>

## Q. １箇所で作成したIAMの役割を、複数のプロジェクトにまたがって使うことができる
1. TRUE
2. FALSE
<details><div>
    答え：1
</div></details>

## Q. IAMの権限管理に関して、管理の手間をなるべく少なくするため、商用環境でも基本の役割を積極的に利用するべきである
1. TRUE
2. FALSE
<details><div>
    答え：2
</div></details>

## Q. プロジェクトのすべてのCompute Engine リソースがeurope-west1リージョンにあります。europe-west1 を gcloud コマンドのデフォルトのリージョンとして設定したい場合、どうすればよいですか
1. europe-west1 リージョン内のリソースに移動してからCloudShellを起動する
2. "gcloud config set compute/region europe-west1" にてgcloudコマンドのデフォルトリージョンを設定
3. "gcloud config set compute/zone europe-west1" にてgcloudコマンドのデフォルトリージョンを設定
4. オンプレミスから europe-west1のサブネットへのVPNを作成し、その接続をgcloudコマンドの実行時に使用する
<details><div>
    答え：2
</div></details>

## Q. 特定のプロジェクトのすべてのリソースを特定のユーザーが表示できるようにする必要があります。Googleが推奨する方法で権限付与を行いたいと考えています。どのように対応しますか
1. 組織に対してプロジェクト閲覧者の役割を全ユーザーに付与する
2. 組織に対してプロジェクト閲覧者の権限を特定ユーザーを含む新しいGoogleグループを作成して付与する
3. 特定プロジェクトに対してプロジェクト閲覧者の権限を特定ユーザーを含む新しいGoogleグループを作成して付与する
4. 特定プロジェクトに対してプロジェクト閲覧者の役割を全ユーザー個別に付与する
<details><div>
    答え：3
</div></details>

## Q. 組織内でmy-projectという名前のプロジェクトに対するオーナーアクセス権を持つユーザーを特定する必要があります。どのよう対応しますか
1. Google Cloud Platform Consoleで組織のIAMページに移動、「Role:Owner」というフィルタを適用する
2. Google Cloud Platform ConsoleでプロジェクトのIAMページに移動、「Role:Owner」というフィルタを適用する
3. ターミナルから”gcloud iam list-grantable-role-project my-project”を実行する
4. プロジェクトページでCloudShellから”gcloud iam list-grantable-role”を実行する
<details><div>
    答え：2
</div></details>

## Q. 組織リソースの中で最も下位のリソースは次の内どれですか
1. フォルダ
2. プロジェクト
3. ファイル
4. VMインスタンス
<details><div>
    答え：2
</div></details>

## Q. Google Cloudおリソースに余剰があれば、プリエンプティブルVMは24時間以上継続して利用できる
1. TRUE
2. FALSE
<details><div>
    答え：2
</div></details>

## Q. コマンドラインからApp Engine アプリケーションをデプロイするには、どのコマンドを使用するべきですか
1. gcloud components app deploy
2. gcloud app deploy
3. gcloud components instances deploy
4. gcloud app instance deploy
<details><div>
    答え：2
</div></details>

## Q. Google Compute Engineのパフォーマンスに関する考察 有効でないパラメータは何ですか？
1. VM がホストされているハードウェア
2. Network Performance
3. Disk IOPS
4. Number of vCPU
<details><div>
    答え：1
</div></details>

## Q. google Compute Engine（VM）への接続について、次の記述のうち誤っているものはどれか。
1. Windows VMへの接続にrdpを使用することができます。
2. サードパーティのsshクライアントはLinuxのVMに接続することはできません。
3. Linux VMへの接続にsshを使用することができます。
4. クラウドコンソールからrdpまたはsshで接続できます。
<details><div>
    答え：2
</div></details>

## Q. Google Compute Engineでは、サードパーティクライアントからのSSH接続のために、デフォルトでファイアウォールが開放されています。
1. true
2. false
<details><div>
    答え：2
</div></details>

## Q. 外部IPアドレスは、Google Cloud Compute Engineの内部で見ることができます。
1. true
2. false
<details><div>
    答え：2
</div></details>

## Q. Compute Engineから外部IPアドレスを確認するには、どのコマンドを使用すればよいですか？
1. gcloud
2. ipconfig
3. ipaddress external
4. gsutil
<details><div>
    答え：1
</div></details>

## Q. 以下のマシンタイプではGPUを取り付けることができません。
1. Shared Core
2. Custom machine
3. Standard
4. High Memory
5. High CPU
<details><div>
    答え：1
</div></details>

## Q. VMのネットワーク性能は、以下のパラメータに依存します。
1. Number of vCPUs
2. GBs of RAM
3. Number of disks attached
4. Network Interface attached
<details><div>
    答え：1
</div></details>

## Q. ローカルSSDを選択する際の注意点は？
1. LocalSSD is ephemeral
2. ローカルSSDを搭載したVMは、ローカルSSDに保存されたデータでライブマイグレーションができない
3. Local SSD can be upto 3TB
4. 1つのVMにつき、1つのローカルディスクしか使用できない
5. Local disk size is fixed size
<details><div>
    答え：4
</div></details>

## Q. カスタムVMは、同等の事前定義されたVMよりもコストが高くなる場合があります。
1. TRUE
2. FALSE
<details><div>
    答え：1
</div></details>

## Q. Google Compute EnginesのvCPU数は、CPUプラットフォームに依存します。
1. TRUE
2. FALSE
<details><div>
    答え：1
</div></details>

## Q. GAEは、次の1つを除くすべての機能を備えています。
1. Traffic Splitting
2. Application Versioning
3. Standard and Flexible env.
4. Monitoring, Logging, Error Reporting
5. DNS
<details><div>
    答え：5
</div></details>

## Q. GAEはVMを管理し、GCPはハードウェアとネットワークを管理するマネージドサービスです。
1. TRUE
2. FALSE
<details><div>
    答え：2
</div></details>

## Q. GAEはコンテナのオーケストレーションを提供します。
1. TRUE
2. FALSE
<details><div>
    答え：
</div></details>

## Q. App Engineは、以下のスケーリング方法のうち、1つを除いたすべての方法を使用します。
1. Manual
2. Automatic
3. Hybrid
4. Basic
<details><div>
    答え：3
</div></details>

## Q. App Engineの構成は、次のうち1つを除いてすべて選択可能です。
1. Choose different machines
2. Configure scalling
3. Choose custom VM
4. Number of Instances
<details><div>
    答え：4
</div></details>

## Q. App Engine standard env.に関する次の記述のうち、誤っているものはどれか。
1. Docker Container Support
2. Preconfigured Sandbox
3. Google supply SDK for standard env.
<details><div>
    答え：1
</div></details>

## Q. App Engine Flexible env. に関する次の記述のうち、正しくないものはどれか。
1. Flexible env. is preconfigured Sandbox runtime
2. You can configure CPU and Memory
3. You can customize env. with dokerfile
4. You have root access to VM
<details><div>
    答え：1
</div></details>

## Q. App Engineは、次の1つを除くすべてのパラメータに基づいて課金されます。
1. Type of machine instance used
2. Network egress
3. Other used service based on requirements
4. Network ingress
<details><div>
    答え：4
</div></details>

## Q. 
1. 
2. 
3. 
4. 
<details><div>
    答え：
</div></details>
