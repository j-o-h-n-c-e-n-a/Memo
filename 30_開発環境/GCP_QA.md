### Q1. 企業は、既存の仮想マシンをGoogle Cloud Platformに移行する必要があります。どのようなオプションがありますか？
1. 既存のパブリックイメージからgcpコンピューティングエンジンを使用し、ソフトウェアを再インストールする
2. オンプレミスvmを計算エンジンに移行してvmを作成します
3. アプリケーションを再作成して、Google App EngineまたはContainer Engineにデプロイできるようにします
4. カスタムイメージをgcpにインストールすることはできません
<details><div>
    答え：２
</div></div>

### Q2. 事前定義されたVM構成を使用する代わりに、カスタム構成を作成すると常に良い?
1. True
2. False
<details><div>
    答え：2
</div></div>

### Q3. 次のうち、Google Cloud Platformで利用できる有効な定義済み仮想マシンタイプではないものはどれですか？
1. High Memory
2. High CPU
3. High Memory and CPU
4. Standard
5. Standard Core
<details><div>
    答え：3
</div></div>

### Q4. 次のうち、Google Compute Engineの有効なカスタムマシンではないものはどれですか？
1. 1 vCPU 1GB RAM
2. 2 vCPU 1.8GB RAM
3. 0.6 vCPU 1GB RAM
4. 32 vCPU 29GB RAM
<details><div>
    答え：3
</div></div>

### Q5. 会社は、バックエンドのビデオ処理要件に高いコンピューティング要件を持っています。どのオプションが事前定義されたマシンに最適ですか？
1. Standard
2. High CPU - Because it contains more CPU over RAM
3. High Memory - Because it contains high RAM over CPU
4. High Memory and CPU - Because it contains more Momory and CPU over
<details><div>
    答え：2
</div></div>

### Q6. Google Compute Engine（VM）に接続できる永続ディスクはいくつですか？
1. 5 per VM
2. 1 per CPU
3. 8 per VM
4. 10 per CPU
<details><div>
    答え：4
</div></div>

### Q7. Google Compute EngineのCPUの高い定義済みマシンに関する有効なステートメントでないものは何ですか？
1. You can only have 0.9 GB of RAM per vCPU
2. You can only have even no of CPU's
3. You can have 64TB of Disk but you need 64 vCPU for machine
4. Suitable for high Compute requirements
<details><div>
    答え：3
</div></div>

### Q8. 会社は既存の仮想マシンをGoogle Cloud Platformに移行する必要がありますが、compute Engineから選択する基準は何ですか？
1. カスタムマシンと定義済みマシンを選択します
2. googleクラウドストレージが必要
3. 必要なオペレーティングシステム
4. オペレーティングシステムのカスタマイズ
5. ネットワークストレージ要件
<details><div>
    答え：2
</div></div>

### Q9. Google Compute Engineのパフォーマンスの考慮事項、どれが考慮すべき有効なパラメーターではありませんか？
1. VMがホストされているハードウェア
2. ネットワークパフォーマンス
3. Disk IOPS
4. vcpuのない
5. ギガバイトRAM
<details><div>
    答え：１
</div></div>

### Q10. Google Compute Engine（VM）に接続することに関して間違っているものはどれですか？
1. rdpを使用してWindows VMに接続できます
2. サードパーティのsshクライアントを使用してLinux VMに接続することはできません
3. sshを使用してlinux vmに接続できます
4. クラウドコンソールからrdpまたはsshを使用して接続できます
5. クラウドシェルを使用してvmを接続できます
<details><div>
    答え：２
</div></div>

### Q11. ファイアウォールは、サードパーティクライアントからのSSH接続用にGoogle Compute Engineに対してデフォルトで開かれています。
1. True
2. False
<details><div>
    答え：２
</div></div>

### Q12. 外部IPアドレスは、Google Cloud Compute Engine内に表示されます。
1. True
2. False
<details><div>
    答え：１
</div></div>

### Q13. Compute Engineから外部IPアドレスを確認するには、どのコマンドを使用できますか？
1. gcloud
2. ipconfig
3. ipaddress external
4. gsutil
<details><div>
    答え：1
</div></div>

### Q14. 次のマシンタイプにはGPUを接続できません
1. Shared Core
2. Custom machine
3. Standard
4. High Memory
5. High CPU
<details><div>
    答え：1
</div></div>

### Q15. VMネットワークのパフォーマンスは、次のパラメーターに依存します
1. vCPU数
2. RAM容量
3. 接続ディスク数
4. 接続ネットワーク数
<details><div>
    答え：１
</div></div>

### Q16. ローカルSSDを選択する際の考慮事項ではないものは何ですか？
1. ローカルssdは一時的です
2. ローカルssdを持つvmは、ローカルssdに保存されたデータを使用してライブ移行できません
3. ローカルssdは3 TBまで可能
4. vmごとに1つのローカルディスクのみを使用できます
5. ローカルディスクサイズは固定サイズです
<details><div>
    答え：４
</div></div>

### Q17. カスタムVMは、同等の定義済みVMよりもコストが高くなる場合があります。
1. TRUE
2. FALSE
<details><div>
    答え：１
</div></div>

### Q18. Google Compute EngineのvCPUの数は、CPUプラットフォームに依存しています。
1. TRUE
2. FALSE
<details><div>
    答え：１
</div></div>

### Q19. GCEには、マネージドインスタンスグループとアンマネージドインスタンスグループがあります。
1. TRUE
2. FALSE
<details><div>
    答え：1
</div></div>

### Q20. アンマネージドインスタンスグループでは自動スケーリングできません。
1. TRUE
2. FALSE
<details><div>
    答え：１
</div></div>

### Q21. GCEのアンマネージドインスタンスグループについて正解はどれですか？
1. 自動スケーリングに使用
2. 負荷分散に使用
3. 異なるリソースを持つインスタンスを持つことはできません
4. ローリング更新を行うことができます
<details><div>
    答え：２
</div></div>

### Q22. マネージドインスタンスグループは次の目的には使用されません
1. ローリング更新
2. 負荷分散
3. 自動スケーリング
4. 異種リソースの管理
<details><div>
    答え：４
</div></div>

### Q23. HTTPロードバランサーのスコープは
1. リージョナル
2. ゾーン
3. 内部
4. グローバル
<details><div>
    答え：４
</div></div>

### Q24. HTTPロードバランサーは、内部通信でIPV4のみをサポートします
1. TRUE
2. FALSE
<details><div>
    答え：１
</div></div>

### Q25. HTTPロードバランサーに関して誤っているステートメントは何ですか？
1. httpロードバランサーはコンテンツに対応していません
2. 複数の地域間で負荷を分散できます
3. 
4. リクエストはクローズドサービングインスタンスにルーティングされます
<details><div>
    答え：１
</div></div>

### Q26. ヘルスチェックは、HTTPロードバランサーの不可欠な部分です。
1. TRUE
2. FALSE
<details><div>
    答え：１
</div></div>

### Q27. HTTPロードバランサーは、常にトラフィックを正常性インスタンスにルーティングします。
1. TRUE
2. FALSE
<details><div>
    答え：１
</div></div>

### Q28. ロードバランサーは、次の負荷分散アルゴリズムを使用して、インスタンスがビジーかどうかを確認します
1. CPU と RAMの利用
2. RAMの利用
3. CPUの利用
4. リクエスト数（RPS） と CPUの利用
<details><div>
    答え：４
</div></div>

### Q29. GAEには、1つを除く以下の機能があります
1. トラフィック分割
2. アプリケーションバージョニング
3. 標準とフレキシブルな環境
4. モニタリング、ロギング、エラーレポート
5. DNS
<details><div>
    答え：５
</div></div>

### Q30. GAEは、VMを管理し、GCPが下線のハードウェアとネットワークを管理するマネージドサービスです。
1. TRUE
2. FALSE
<details><div>
    答え：２
</div></div>

### Q31. GAEはコンテナオーケストレーションを提供します。
1. TRUE
2. FALSE
<details><div>
    答え：２
</div></div>

### Q32. 1つを除く次のスケーリングを構成できます。
1. 手動
2. 自動
3. ハイブリッド
4. 内容に沿って
<details><div>
    答え：3
</div></div>

### Q33. 1つを除くGAEの次の構成を選択できます。
1. 別のマシンを選択する
2. スケーリングを設定する
3. カスタムVMを選択する
4. インスタンス数
<details><div>
    答え：４
</div></div>

### Q34. GAE標準環境に当てはまらないものは何ですか？
1. Dockerコンテナのサポート
2. 事前構成済みのサンドボックス
3. 標準環境のためのGoogle SDK
4. 
<details><div>
    答え：１
</div></div>

### Q35. GAE Flexible Envに当てはまらないこと
1. サンドボックスランタイムを事前設定します
2. CPUとメモリを設定できます
3. dockerfileでenvをカスタマイズできます
4. VMへのルートアクセスがあります
<details><div>
    答え：１
</div></div>

### Q36. GAEは、1つを除くすべてに基づいて請求されます
1. 使用されるマシンインスタンスのタイプ
2. ネットワーク出口
3. 要件に基づいて使用されるその他のサービス
4. ネットワーク入口
<details><div>
    答え：４
</div></div>

### Q37. 
1. 
2. 
3. 
4. 
<details><div>
    答え：
</div></div>
