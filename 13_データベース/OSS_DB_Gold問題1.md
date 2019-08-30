# 参照
* [サンプル問題](https://oss-db.jp/sample)
* [内部構造から学ぶPostgreSQL 設計・運用計画の鉄則]()
    + NTTテクノクロス株式会社　河原 翔
    + NTTテクノクロス株式会社　勝俣 智成
    + NTTテクノクロス株式会社　佐伯 昌樹
    + NTTテクノクロス株式会社　原田 登志
* 株式会社メトロシステムズ　岡野 慎也
* 株式会社メトロシステムズ　佐藤 千佳
* 株式会社デージーネット OSS研究室 奥原 章太
* 株式会社デージーネット OSS研究室 大野 公善
* [勝手に学習 OSS-DB Gold](https://www.r-izm.com/oss_g/)

# OSS-DB Gold問題
## １．運用管理（30％）
### Q.レプリケーション構成において、フェールオーバを実施する方法として正しいものは次のうちどれか。
* [詳細 [××]](https://oss-db.jp/sample/gold_management_01/20_190515)
1. スレーブ側でrecovery.confのtrigger_fileパラメータで設定したトリガファイルを作成する
2. マスタ側でrecovery.confのtrigger_fileパラメータで設定したトリガファイルを作成する
3. postgresql.confで自動フェールオーバの設定をする
4. pg_ctl promoteコマンドを実行する
5. pg_hba.confの第2列目に、下記のようにレプリケーションの設定をする
```
host    replication    postgres    192.168.1.2/32    trust
```
### Q．バックアップに関して正しいものをすべて選択しなさい。
* [詳細 [××]](https://oss-db.jp/sample/gold_management_01/16_170313)
1. 通常はフルバックアップを取得するよりも、pg_basebackupによって更新差分を取得する方が処理時間は短い。
2. recovery_target_timelineをデフォルト値で使用すると、ベースバックアップが取得された際のタイムラインへ回復する。
3. pg_dumpコマンドによってpsqlコマンドでリストア可能な形式 として出力したバックアップファイルには、データベースを作成する SQLコマンドが含まれる場合がある。
4. pg_dumpコマンドも、pg_restoreコマンドも並列実行することが可能であり、複数のデータベースのバックアップ・リストア処理を行う際は高速化が図れる。
5. pg_restoreコマンドで--encodingオプションを使用すると、sjisで作成したダンプファイルをUTF8でリストアすることができる。

### Q．pg_basebackupコマンドに関する説明として、適切でないものを2つ選びなさい。
* [詳細 [××]](https://oss-db.jp/sample/gold_management_01/11_150123)
1. 別サーバで動作しているPostgreSQLデータベースクラスタのベースバックアップを取得できる
2. pg_basebackupコマンドの実行前にpg_start_backupコマンドを実行する必要がある
3. fetch方式の場合、max_wal_sendersパラメータを少なくとも1以上に設定する必要がある
4. オプションを明示的に指定しないで実行した場合は、WALはバックアップに含まれない
5. テーブル空間が追加で作成されている場合は、テーブル空間内のデータはバックアップに含まれない

### Q．VACUUMに関して正しいものを全て選択しなさい。
* [詳細 [××]](https://oss-db.jp/sample/gold_management_01/10_141027)
1. FULLオプションを付加すると、データベース全体の不要領域が回収される。
2. VERBOSEオプションを付加すると、VACUUM処理の詳細な情報を取得することができる。
3. AUTOオプションを付加すると、autovacuumの設定を用いてVACUUMが行われる。
4. ANALYZEオプションを付加すると、統計情報の更新も行われる。
5. 一つのVACUUMコマンドに複数のテーブルを指定して実行することができる。

### Q．VACUUMに関して正しいものを全て選択しなさい。
* [詳細 [×●]](https://oss-db.jp/sample/gold_management_01/08_140702)
1. VACUUMを実行するユーザが対象テーブルに対するVACUUMの実行権限を持っていない場合はエラーとなる。
2. トランザクションブロック内でVACUUMを実施すれば、ROLLBACKによって処理を取り消すことができる。
3. オプションが指定されていない通常のVACUUMでも、不要領域をOSに返還することがある。
4. 多数の行を追加または削除した場合は、VACUUM ANALYZEを実施すべきである。

### Q．ANALYZEに関して正しいものを全て選択しなさい。
* [詳細 [×●]](https://oss-db.jp/sample/gold_management_01/07_140307)
1. 整列されたデータを昇順にロードした場合、ANALYZEを実施しなくとも最適なプランが作成される。
2. 自動バキュームデーモンがANALYZEを実施する場合がある。
3. default_statistics_targetの値を大きくすると、ANALYZEの所要時間は短くなるがプランナの予測の品質は低下する。
4. 対象とするテーブルへのSHARE UPDATE EXCLUSIVEロックが取得される。
5. PostgreSQLのANALYZE文は、標準SQLに準拠している。

### Q．2台のサーバ(プライマリサーバ、スタンバイサーバ)でストリーミングレプリケーションを行い、スタンバイサーバをホットスタンバイとして運用する。 この環境を構築する際に各サーバで設定するパラメータとして誤っているものを1つ選びなさい。
* [詳細 [×●]](https://oss-db.jp/sample/gold_management_01/06_130619)
1. プライマリサーバのpg_hba.confに、データベースフィールドを"replication"と指定した項目を設定する
2. プライマリサーバのpostgresql.confに、"wal_level = hot_standby"を設定する
3. スタンバイサーバのpostgresql.confに、"hot_standby = on"を設定する
4. スタンバイサーバのpostgresql.confに、"standby_mode = 'on'"を設定する
5. スタンバイサーバのrecovery.confの"primary_conninfo"に、プライマリサーバへの接続情報(libpq接続文字列)を設定する

### Q．データベースクラスタ配下の各サブディレクトリに保有されるデータの説明として、適切ではないものを1つ選びなさい。
* [詳細 [××]](https://oss-db.jp/sample/gold_management_01/05_130510)
1. globalディレクトリにはデータベースクラスタ全体で共有するテーブルが保有される。
2. pg_tblspcディレクトリにはテーブル空間により管理されるテーブルが保有される。
3. pg_xactディレクトリにはトランザクションのコミット状態のデータが保有される。
4. pg_walディレクトリにはWALファイルが保有される。
5. pg_stat_tmpディレクトリには統計情報コレクタがバックエンドプロセスと必要な情報をやり取りするための一時ファイルが格納される。

### Q．以下のSQL文でインデックスを定義し、100万行を挿入する。ここで、team_idのデータ型はINTEGER、birthdayのデータ型はDATE、いずれもNOT NULL制約が付いているものとする。インデックスのファイルサイズ見積りとして最も適切なものを1つ選びなさい。なお、1ブロックは8192バイトとし、FILLFACTORは90%とする。
* [詳細 [●]](https://oss-db.jp/sample/gold_management_01/04_130401)
```
CREATE INDEX member_index ON member_table (team_id, birthday);
```
1. 9メガバイト
2. 13メガバイト
3. 19メガバイト
4. 23メガバイト
5. 29メガバイト

### Q．PostgreSQL のプロセス構造について、適切なものをすべて選びなさい。
* [詳細 [●×]](https://oss-db.jp/sample/gold_management_01/02_111130)
1. データベースに接続するクライアント一つ一つについて、別々のサーバプロセスが起動する。
2. データベースクラスタ内のそれぞれのデータベースについて、別々のサーバプロセスが起動する。
3. WAL ライタ、自動バキュームランチャ、統計情報コレクタなどいくつかのプロセスが動作しているが、いずれも postgres という同一の実行ファイルから作られるプロセスである。
4. クライアントが接続していないときは、通常は postmaster というプロセスだけが動作している。
5. データベースクラスタ1つに対して、postmaster というプロセスが1つ動作している。

### Q．以下のSQL分でテーブルを定義し、50万行を挿入する。テーブルのファイルサイズ見積りとして最も適切なものを1つ選びなさい。1ブロックは8192バイトとし、インデックスのファイルサイズは含めないものとする。
```
CREATE TABLE registration (
  id BIGINT PRIMARY KEY,
  reg_event INTEGER NOT NULL,
  reg_client INTEGER NOT NULL,
  reg_date TIMESTAMP NOT NULL
);
```
* [詳細 [●]](https://oss-db.jp/sample/gold_management_01/01_120210)
1. 5メガバイト
2. 15メガバイト
3. 25メガバイト
4. 40メガバイト
5. 60メガバイト


## ２．性能監視（30％）
### Q．下記のEXPLAINの実行結果について、正しい記述を３つ選んでください。
```
postgres=# EXPLAIN SELECT relname,nspname FROM pg_class left join pg_namespace ON (pg_class.relnamespace = pg_namespace.oid);
                               QUERY PLAN
-------------------------------------------------------------------------
 Hash Left Join  (cost=1.14..15.97 rows=288 width=128)
   Hash Cond: (pg_class.relnamespace = pg_namespace.oid)
   ->  Seq Scan on pg_class  (cost=0.00..10.88 rows=288 width=68)
   ->  Hash  (cost=1.06..1.06 rows=6 width=68)
         ->  Seq Scan on pg_namespace  (cost=0.00..1.06 rows=6 width=68)
(5 行)
```
* [詳細 [●]](https://oss-db.jp/sample/gold_monitoring_01/16_190626)
1. このEXPLAINコマンドを実行すると、引数に指定したSQL文が実際に実行される
2. 計画ノードの「Hash Left Join」、「Seq Scan on pg_class」、「Seq Scan on pg_namespace」の記述
3. 「cost=〜」の部分は、処理にかかる実際の時間を示している
4. 「rows=〜」の部分は、それぞれの計画ノードを実行した際の推定の処理行数を示している
5. 「width=〜」の部分は、統計情報をもとに推測される1行あたりの平均のバイトサイズを示している

### Q．pg_stat_statementsの説明として正しいものは次のうちどれか。
* [詳細 [●×]](https://oss-db.jp/sample/gold_monitoring_01/15_190529)
1. SQL文の実行に指定した時間以上かかった場合、それぞれのSQL文の実行に要した時間を記録する
2. ロック待ちとなっているトランザクションや対象のテーブルを確認する
3. 実行された全てのSQL文の実行時の統計情報を記録する
4. データベースあたり1行の形式でデータベース全体の情報を表示する
5. 現在のデータベースの各テーブルごとに1行の形で、テーブルへのアクセス統計情報を表示する

### Q．
```
EXPLAIN ANALYZE SELECT * FROM pgbench_accounts a
JOIN pgbench_branches b ON (a.bid = b.bid) WHERE a.aid = 10000;
```
上記問い合わせの実行計画(EXPLAIN ANALYZE)を確認したところ、下記の出力であった。
```
QUERY PLAN
----------------------------------------------------------------------------------------------
Nested Loop (cost=0.00..2891.02 rows=1 width=461) (actual time=4.589..64.393 rows=1 loops=1)
   Join Filter: (a.bid = b.bid)
   -> Seq Scan on pgbench_accounts a (cost=0.00..2890.00 rows=1 width=97) (actual time=4.555..64.356 rows=1 loops=1)
         Filter: (aid = 10000)
         Rows Removed by Filter: 99999
   -> Seq Scan on pgbench_branches b (cost=0.00..1.01 rows=1 width=364) (actual time=0.007..0.008 rows=1 loops=1)
Total runtime: 64.557 ms
(7 rows)
```
上記問い合わせをより高速にするために行うこととして最も適切なものをひとつ選びなさい。
なお、各テーブルの構成は下記のようになっている。
----------------------------------------------------
Table "public.pgbench_accounts"
| Column   | Type          | Modifiers |
|:---------|--------------:|:---------:|
| aid      | integer       | not null  |
| bid      | integer       |           |
| abalance | integer       |           |
| filler   | character(84) |           |
----------------------------------------------------
----------------------------------------------------
Table "public.pgbench_branches"
| Column   | Type          | Modifiers |
|:---------|--------------:|:---------:|
| bid      | integer       | not null  |
| bbalance | integer       |           |
| filler   | character(88) |           |

Indexes:
    "pgbench_branches_pkey" PRIMARY KEY, btree (bid)
----------------------------------------------------
* [詳細 [●]](https://oss-db.jp/sample/gold_monitoring_01/11_150324)
1. pgbench_accountsのabalance列にインデックスを作成する
2. pgbench_branchesのbid列にインデックスを作成する
3. pgbench_accountsを対象にANALYZEを実行する
4. pgbench_accountsのaid列にインデックスを作成する
5. pgbench_branchesを対象にANALYZEを実行する

### Q．EXPLAINコマンドで指定可能な出力形式のうち誤っているものを全て選択しなさい。
* [詳細 [×●]](https://oss-db.jp/sample/gold_monitoring_01/10_140812)
1. JSON
2. HTML
3. CSV
4. YAML
5. XML

### Q．標準統計情報ビューに関して正しいものを全て選択しなさい。
* [詳細 [●●]](https://oss-db.jp/sample/gold_monitoring_01/08_140530)
1. pg_stat_all_tablesから、TOASTテーブルから読み取られたディスクブロック数を取得することができる。
2. pg_stat_activityから、現在の問い合わせの実行開始時刻を取得することができる。
3. pg_stat_databaseから、対象データベースのエラー発生数を取得することができる。
4. pg_statio_all_tablesから、対象テーブルのバッファヒット数を取得することができる。

### Q．pg_stat_databaseに関する記述で誤っているものを全て選択しなさい。
* [詳細 [××]](https://oss-db.jp/sample/gold_monitoring_01/07_140417)
1. データベースクラスタ全体の稼働統計情報が1行だけ格納される。
2. blks_hitはバッファキャッシュにヒットしたブロック数が格納される。
3. blks_readはディスクから読み込んだブロック数とバッファキャッシュから読み込んだブロック数の合計である。
4. デフォルトではtrack_countsパラメータがoffであるため、稼働統計情報が収集されない。
5. tup_fetchedはインデックススキャンを使用して読み取った行数が格納される。

### Q．EXPLAINコマンドを用いて問い合わせを実行させ、結果が出力された。
```
EXPLAIN ANALYZE SELECT *
FROM table1 t1, table2 t2
WHERE t1.unique1 < 100 AND t1.unique2 = t2.unique2;
```
```
QUERY PLAN
-----------------------------------------------------------------------------------------------
Nested Loop (cost=0.00..352.17 rows=97 width=16) (actual time=0.033..1.875 rows=100 loops=1)
   -> Index Scan using table1_i1 on table1 t1 (cost=0.00..24.05 rows=97 width=8) (actual time=0.016..0.218 rows=100 loops=1)
         Index Cond: (unique1 < 100)
   -> Index Scan using table2_i2 on table2 t2 (cost=0.00..3.27 rows=1 width=8) (actual time=0.004..0.006 rows=1 loops=100)
         Index Cond: (t2.unique2 = t1.unique2)
Total runtime: 2.065 ms
```
この結果言えることとして、誤っているものを2つ選択せよ。
* [詳細 [××]](https://oss-db.jp/sample/gold_monitoring_01/02_130402)
1. この問い合わせにより出力される行数は97行であった。
2. Total runtime には、結果行を操作するための時間の他に、エクゼキュータの起動、停止時間も含まれている。
3. table2_i2 という名前のインデックスを用いて検索をしている。
4. Nested Loop の cost と actual time の値が大きく異なっているので、統計情報の再収集が必要である。
5. table1 が外側、table2 が内側になるネステッドループで結合をしている。

### Q．


## ３．パフォーマンスチューニング（20％）
### Q．問い合わせ計画に関する以下の内容のうち、正しいものを全て選択しなさい。
* [詳細 [××]](https://oss-db.jp/sample/gold_performance_01/13_171016)
1. enable_indexscanを無効に設定すると、インデックススキャンは完全に行われなくなる。
2. enable_seqscanを無効に設定すると、シーケンシャルスキャンは完全に行われなくなる。
3. random_page_costをseq_page_costと比較して小さく設定すると、よりインデックススキャンが使用されるようになる。
4. random_page_costをseq_page_costと比較して大きく設定すると、よりインデックススキャンが使用されるようになる。
5. default_statistics_targetをより小さく設定すると、より細かく統計情報を収集するようになるため、プランナの予測の品質が向上する。 

### Q．work_memをチューニングすることによって、性能が向上すると考えられる処理を全て選択しなさい。
* [詳細 [×●]](https://oss-db.jp/sample/gold_performance_01/12_170403)
1. ORDER BY
2. CREATE INDEX
3. マージ結合
4. VACUUM
5. 自動VACUUM

### Q．インデックスの作成に関する説明として、適切なものを2つ選びなさい。
* [詳細 [××]](https://oss-db.jp/sample/gold_performance_01/11_151116)
1. FILLFACTORの指定が省略された場合、デフォルト値として対象テーブルのFILLFACTORと同じ値が設定される
2. UNLOGGEDパラメータが指定された場合、インデックスの更新時にWALログが取られなくなり、更新処理が高速化する
3. PARALLELパラメータが指定された場合、複数のプロセスによりインデックスが作成され、作成時間が短縮する
4. CONCURRENTLYパラメータが指定された場合、対象テーブルに対する書き込みをロックせずにインデックスを作成するが、通常の方式より作成時間が長くなる
5. インデックスの定義で使用される関数と演算子は、immutableでなければならない 

### Q．GUCパラメータのenable_seqscanをonからoffに変更する前後で、同一のクエリに対してEXPLAIN ANALYZE文で実行計画を取得する。実行計画の変化の説明として、最も適切ではないものを１つ選びなさい。この時、enable_seqscan以外の条件はすべて同一とする。
* [詳細 [××]](https://oss-db.jp/sample/gold_performance_01/10_150421)
1. Total runtimeの値が大きくなる可能性がある
2. Total runtimeの値が小さくなる可能性がある
3. 最上位ノードの全体推定コストが大きくなる可能性がある
4. 最上位ノードの全体推定コストが小さくなる可能性がある
5. 全く同一の実行計画が選択される可能性がある

### Q．インデックスの再作成について正しい記述を2つ選びなさい。
* [詳細 [×●]](https://oss-db.jp/sample/gold_performance_01/09_150205)
1. インデックスの再作成はサービスを停止して行う必要がある。
2. REINDEXはインデックスの元となるテーブルの読み込みをロックしないため、サービス稼働中に実行しても参照処理への影響はない。
3. CREATE INDEX CONCURRENTLYは、同時挿入、更新、削除と競合するロックを獲得せずにインデックスを作成できる。
4. CREATE INDEX CONCURRENTLYでは、プライマリキーの作成も可能である。
5. 定期的にインデックスの再作成を行うことで、インデックスの肥大化を抑止できる。

### Q．性能低下の原因に関して正しいものをすべて選択しなさい。
* [詳細 [××]](https://oss-db.jp/sample/gold_performance_01/06_141027)
1. shared_buffersの値を大きく設定しすぎたことによって、チェックポイント中の問い合わせの性能が低下した。
2. maintenance_work_memをwork_memよりも大きく設定したことによって、VACUUM処理の性能が低下した。
3. 複数のセッションが多量のINSERTを発行したことによって、WALファイルへの書き込みで競合が発生し、INSERTの性能が低下した。
4. pgstattupleを用いて定期的にタプルレベルの統計情報を取得しなかったため、PostgreSQLが最適な実行計画を作成できずに問い合わせの性能が低下した。

### Q．データベースに大量データを投入する際の性能を向上させるために、一時的に講じることとして、適切とは言えないものを2つ選びなさい。
* [詳細 [××]](https://oss-db.jp/sample/gold_performance_01/03_130704)
1. 自動コミットをオフにする
2. インデックスや外部キー制約を削除する
3. maintenance_work_memを増やす
4. checkpoint_segmentsを減らす
5. checkpoint_timeoutを増やす

### Q．デッドロックに関する GUC パラメータ deadlock_timeout の説明として、正しいものをすべて選びなさい。
* [詳細 [×●]](https://oss-db.jp/sample/gold_performance_01/02_111115)
1. deadlock_timeout で指定された時間を経過してもロックが獲得できなければ、デッドロックが発生していると判断される。
2. deadlock_timeout の値を調整することで、デッドロックの発生を回避できる。
3. deadlock_timeout の値を小さくすると、ロック待ちのプロセスが減るので、結果的にCPU負荷を小さくすることができると考えられる。
4. デッドロックはアプリケーションの作り方を工夫することで回避すべきであり、deadlock_timeout の値はなるべく大きくすることが望ましい。
5. deadlock_timeout のデフォルトの設定では、デッドロックの検出は自動的には実行されない。

### Q．シーケンシャルスキャンのみ行われていた選択クエリ高速化のためにインデックスを付与したが、その後のクエリが逆に遅くなってしまった。推測できる原因として適切なものを2つ選びなさい。
* 1. random_page_costの値が適切な値より小さく設定されているため
* 2. maintenance_work_memの値が適切な値より小さく設定されているため
* 3. effetive_cache_sizeの値が適切な値より小さく設定されているため
* 4. seq_page_costの値が適切な値より小さく設定されているため
* 5. 統計情報の精度が低く、適切な実行計画が作成されていないため
<details><div>
    A．1,5

* インデックスを付与したことによりクエリが遅くなったということは、「オプティマイザはインデックスを利用したほうがクエリが高速化すると判断したが、その判断に誤りがあった」ということになる。
* 1. 「random_page_costの値が適切な値より小さい」場合、「オプティマイザは実際よりもインデックスアクセスが高速である」と判断することになるため、適切。
* 2. maintenance_work_memの値は、コスト計算とは無関係であるため、不適切
* 3. 「effetive_cache_sizeの値が適切な値より小さい」場合は、「オプティマイザは実際よりもインデックスアクセスが低速である」と判断することになるため、不適切。
* 4. 「seq_page_costの値が適切な値より小さい」場合は、「オプティマイザは実際よりもシーケンシャルアクセスが高速である」と判断することになるため、不適切。
* 5. 統計情報の精度が低異場合は、適切な実行計画が作成されないため、適切
</div></details>

### Q．CLUSTERコマンドに関する説明として適切ではないものを２つ選びなさい。
* 1. CLUSTERコマンドの実行後は、該当のインデックスを利用した検索クエリの性能が向上する可能性がある
* 2. CLUSTERコマンドの実行後は、該当のテーブル更新時にインデックス情報に基づいた処理が行われるため、更新性能が低下する可能性がある
* 3. 単一のテーブルに対して複数のインデックスが存在する場合、それぞれのインデックスに対して同時に最適化させるためのCLUSTERコマンドを発行することができない
* 4. CLUSTERコマンドはACCESS EXCLUSIVEロックを獲得するため、クラスタ化が終われまで、そのテーブルに対する読み込みが待機される
* 5. correlationの値が負数の場合は相関率が低いため、CLUSTERコマンドの実行を検討すべきである
<details>A．2,5</details>

### Q．ロックに関する以下の記述で適切ではないものを２つ選びなさい。
* 1. pg_locksビューのcurrent_query列には、ロックを保持しているクエリが表示される
* 2. pg_locksビューには行ロックを保持しているトランザクションは表示されない
* 3. deadlock_timeoutの値を大きくすると、デッドロックが検出されるまでの時間が長くなる
* 4. deadlock_timeoutの値を大きくすると、デッドロックの誤検知の発生確率が高くなる
* 5. トランザクションが並列実行される状態において、パラメータチューニングによりデッドロックの発生を防止する方法はない
<details>A．1,5</details>

## ４．障害対応（20％）
### Q．操作ミスによってリレーションが消失することを想定した対策または復旧を行う際に、実施すべき内容として正しいものを全て選択しなさい。
* [詳細 [××]](https://oss-db.jp/sample/gold_trouble_01/07_171031)
1. ミラーリングによって、ディスクの複製を作成しておく。
2. pg_basebackupによって、定期的に論理バックアップを取得しておく。
3. PITRによって、操作ミス直前の時間まで巻き戻しを行う。
4. pg_dumpallによって、操作ミス直前の時間まで巻き戻しを行う。
5. wal_levelをminimalからhot_standbyに変更しておく。

### Q．2台のサーバでレプリケーションを行い、スタンバイサーバをホットスタンバイとして稼動させる。サーバ間の通信が一時的に遮断し、その後に復旧した場合の説明として、適切ではないものを2つ選びなさい。
* [詳細 [××]](https://oss-db.jp/sample/gold_trouble_01/05_150612)
1. レプリケーションの方式が同期か非同期かにかかわらず、通信が遮断中でも、マスタサーバでの参照系クエリは実行可能である
2. レプリケーションの方式が同期か非同期かにかかわらず、通信が遮断中でも、スタンバイサーバでの参照系クエリは実行可能である
3. 同期レプリケーションの場合は、通信が遮断中は、マスタサーバでの更新系クエリは待機させられる
4. 通信復旧後のデータの再同期処理には、アーカイブWALが必須となる
5. 通信復旧後のデータの再同期処理に、アーカイブWALが利用される際は、マスタサーバのGUCパラメータrestore_commandが実行され、スタンバイサーバにアーカイブWALが転送される

### Q．あるユーザテーブルの参照時に、以下のエラーメッセージが出力された。この時の対処として最も適切なものを1つ選びなさい。
```
「ERROR: invalid page header in block 0 of relation base/16408/16421」
```
* [詳細 [×●]](https://oss-db.jp/sample/gold_trouble_01/03_130910)
1. データベース全体に対してVACUUMを実行する
2. 該当のテーブルファイルを削除し、PostgreSQLを再起動する
3. zero_damaged_pages を on に設定して再度テーブルを参照する
4. 該当のシステムテーブルに対してCLUSTERを実行する
5. PostgreSQLをシングルユーザ状態で起動し、該当のテーブルに定義されたインデックスに対してREINDEX INDEXを実行する

