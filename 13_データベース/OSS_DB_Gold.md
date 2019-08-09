
# OSS-DB Gold
## 運用管理（30％）
### データベースサーバ構築 【重要度：2】
    サーバ構築における容量見積もり、およびデータベースセキュリティに関する知識を問う
#### 主要な知識範囲：
* テーブル・インデックス容量見積もり [!]
* セキュリティ [!]
    + 通信経路暗号化（SSL)
    + データ暗号化
        - crypt関数：パスワードのハッシュ処理を行う
    + クライアント認証
    + 監査ログ
* データ型のサイズ
* ユーザ・データベース単位のパラメータ設定
#### 重要な用語、コマンド、パラメータなど：
* チェックサム
* 【変更】pg_xact：トランザクションのコミット状態のデータが保有される
* pg_multixact
* pg_notify
* pg_serial
* pg_snapshots
* pg_stat_tmp：統計情報コレクタがバックエンドプロセスと必要な情報をやり取りするための一時ファイルが格納される
* pg_subtrans
* pg_tblspc：テーブル空間へのシンボリックリンクが保有される
	+ テーブル空間の利用により、データベースクラスタとは別ディレクトリへのデータ格納が可能となるため、テーブルを複数のディスク装置に分散配置し、I/O性能の向上を図ることができます
* pg_twophase
* 【追加】ssl
* 【追加】pg_stat_ssl
* 【追加】pgcrypto [●]
* ALTER ROLE
* ALTER DATABASE
* initdb -data-checksums (-k)
* log_statement
    + 実行したSQLのうち、どの種別のものをログ出力するかについて設定する
        - none, ddl, mod, all
* track_functions
* track_activities

### 運用管理用コマンド全般 【重要度：4】
    データベースの運用管理に関する高度な知識を問う
#### 主要な知識範囲：
* バックアップ、PITR
* VACUUM、ANALYZE、REINDEX [!]
* 自動バキューム [!]
* 【追加】チェックポイント
* サーバログ管理
* ディスク容量監視 [!]
* 自動VACUUMと手動VACUUM/ANALYZEの違い
    + 自動バキュームデーモンはVACUUMだけではなくANALYZEも実行する場合があります。
#### 重要な用語、コマンド、パラメータなど：
* ALTER SYSTEM
* ANALYZE [●]
    + ANALYZEでは、SHARE UPDATE EXCLUSIVEロックが取得されます。ANALYZEによって、SELECT文やINSERT文などの処理が阻害されることはありません。
* CLUSTER
    + テーブルデータが物理的に再編成され、読み込み性能が向上する可能性がある
    + 実行されているテーブルに対する読み込みは待機される
    + maintenance_work_memの値を大きくするとCLUSTERコマンドの性能が向上する可能性がある
    + テーブルおよびインデックスサイズを削減できる可能性がある
* REINDEX [●]
* VACUUM [●]
    + VERBOSEオプションを付加すると、VACUUM処理の進行状況などの詳細な情報が出力されます
    + ANALYZEオプションを付加すると、VACUUM処理後に統計情報も更新されます
* 【追加】CHECKPOINT
* PITR [●]
* WAL
* pg_dump 
* pg_dumpall
* pg_basebackup [●]
    + 別サーバで動作しているPostgreSQLデータベースクラスタのベースバックアップを取得できる
    + fetch方式の場合、max_wal_sendersパラメータを少なくとも1以上に設定する必要がある
    + オプションを明示的に指定しないで実行した場合は、WALはバックアップに含まれない
* 【追加】pg_start_backup()
* 【追加】pg_stop_backup()
* postgresql.conf
* recovery.conf
* vacuumdb 
* pgstattuple
* pg_cancel_backend()
* pg_terminate_backend()
* pg_isready
* log_connections
* log_disconnections
* log_duration [●]
    + true/falseの論理値を設定し、trueに設定するとSQL文の実行に要した時間を出力する
 
### データベースの構造 【重要度：2】
    データベースの物理的な構造に関する知識を問う
#### 主要な知識範囲：
* データベースクラスタの構造 [!]
* プロセス構造 [!]
* データの格納方法
#### 重要な用語、コマンド、パラメータなど：
* autovacuum [●]
* TOAST
* FILLFACTOR
* アーカイブログ
* ページヘッダ
* タプルヘッダ
* postmasterプロセス [●]
    + PostgreSQLの親プロセス。接続を待ち受ける。
* postgresプロセス
* バックグラウンドプロセス
* SQL実行のキャンセル
* シグナル(TERM/INT/HUP)によるサーバプロセスへの影響
* checkpointer [●]
    + チェックポイント処理を行うプロセス

### ホット・スタンバイ運用 【重要度：1】
    レプリケーション構成を組むための設定や構築手順、およびレプリケーションの仕組み(プロセスやフロー)、状態の監視などに関する知識を問う
#### 主要な知識範囲：
* 【変更】ストリーミングレプリケーション機能とロジカルレプリケーション機能の概要 [!]
* 【変更】同期レプリケーションと非同期レプリケーション
* postgresql.conf、recovery.confの設定
    + スレーブ側でrecovery.confのtrigger_fileパラメータで設定したトリガファイルを作成
* 【追加】パブリケーションとサブスクリプションの定義
#### 重要な用語、コマンド、パラメータなど：
* 【追加】wal_level
* 【追加】max_wal_senders
* 【追加】wal_sender_timeout
* 【追加】wal_receiver_timeout
* 【追加】synchronous_standby_names
* 【追加】synchronous_commit
* 【追加】max_logical_replication_workers
* 【追加】CREATE/ALTER/DROP PUBLICATION/SUBSCRIPTION
* 【追加】pg_stat_replication
* 【追加】pg_stat_wal_receiver
* recovery_min_apply_delay
* 【追加】スタンバイでの問い合わせのコンフリクト(衝突)
* 【追加】hot_standby_feedback
* max_standby_streaming_delay
* pg_wal_replay_pause()
* pg_wal_replay_resume()
* 【変更】wal sender プロセス [●]
* 【変更】wal receiver プロセス [●]
* 【変更】pg_receivewal
* トランザクションログ(WAL)
* スタンバイへ伝搬される処理とされない処理
* 【追加】スタンバイで実行可能な問い合わせ
* 【追加】ロジカルレプリケーションのサブスクライバ―へ伝搬される処理とされない処理

## 性能監視（30％）
### アクセス統計情報 【重要度：3】 
    データベースの利用状況を示す稼働統計情報の内容や見方、収集方法に関する知識を問う
#### 主要な知識範囲：
* pg_locks：ロック待ちとなっているトランザクションや対象のテーブルを確認する
	+ relation、 extend、 page、 tuple、 transactionid、 virtualxid、 object、userlock、 advisory
* pg_stat_activity：サーバプロセス毎にプロセスの活動に関する情報を表示する [!]
	+ query_startカラム：現在の問い合わせの実行開始時刻
	+ xact_startカラム：トランザクションの開始時刻
* pg_stat_database：データベースあたり1行の形式でデータベース全体の情報を表示する [!]
* pg_stat_all_tables 等、行レベル統計情報 [!]
	+ pg_stat_all_tables：現在のデータベースの各テーブルごとに1行の形で、テーブルへのアクセス統計情報を表示する
	+ heap_blks_hitカラム：対象テーブルのバッファヒット数
	+ blks_readカラム：ディスクから読み込んだブロック数が格納される
* pg_statio_all_tables 等、ブロックレベル統計情報 [!]
#### 重要な用語、コマンド、パラメータなど：
* pg_stat_archiver
* pg_stat_bgwriter：バックグラウンドライタに関する情報を表示する [●]
* 【追加】待機イベント(pg_stat_activity.wait_event)
* 【追加】pg_stat_progress_vacuum

 
### テーブル / カラム統計情報 【重要度：2】
    プランナが利用するテーブル・カラムの統計情報についての理解を問う
#### 主要な知識範囲：
* pg_class：システムカタログで、名称・所有者・テーブル空間といった多くの列を保有している [!]
	+ relpages列にはテーブル内のページ数が格納されている
	+ reltuples列にはテーブル内の行数が格納されている
	+ 格納されている統計情報は推測値であり、VACUUMやANALYZEおよびCREATE INDEXなどにより更新される
* pg_stats
* テーブル・インデックスの実ファイルとパス
	+ テーブルファイル：テーブルごとの実データを管理する
	+ インデックスファイル：インデックスの情報を管理する
	+ 8192バイトの「ページ」単位で構成され最大1Gバイト
	+ 1Gバイトを超えると「ファイルノード番号.連番」の命名規則に則って分割管理される
	+ ライタプロセスやチェックポインタによって共有バッファのデータが書き込まれる
* 実行計画時に利用される統計情報やパラメータ
#### 重要な用語、コマンド、パラメータなど：
* pg_attribute：テーブルの列情報
* pg_statistic
* pg_stats
* null_frac
* n_distinct
* most_common_freqs
* histogram_bounds
* correlation
* default_statistics_target
    + default_statistics_targetの値を大きくすると、ANALYZEの所要時間は長くなり、プランナの予測の品質は向上します。
* effective_cache_size

 
### クエリ実行計画 【重要度：3】
    EXPLAINが出力する実行計画を読み取り、チューニングを行う。
#### 主要な知識範囲：
* EXPLAIN / EXPLAIN ANALYZE 出力 [!]
	+ 出力フォーマット：TEXT（デフォルト）、XML、JSON、YAML
	+ SQLコマンド：SELECT、INSERT、UPDATE、DELETE、VALUES、EXECUTE、DECLARE、CREATE TABLE AS、CREATE MATERIARIZED VIEW、REFRESH MATERIALIZED VIEW
* 計画型
* EXPLAINからのチューニング
* 結合の種類(Nested Loop、Hash、Merge)と性能特性 [!]
* SQL構文(JOIN/GROUP BY/ORDER BY/LIMIT)に対応する実行計画 [!]
* 集約関数(sum/count)を伴うSQLに対応する実行計画
* 【追加】パーティションに対するSQLの実行計画
* 【追加】パラレルクエリに対応する実行計画
* 【追加】ウィンドウ関数(row_number/rankなど)のSQLに対応する実行計画
#### 重要な用語、コマンド、パラメータなど：
* 【追加】EXPLAIN / EXPLAIN ANALYZE
 
### その他の性能監視 【重要度：1】
    性能監視に関するその他の手法
#### 主要な知識範囲：
* スロークエリの検出 [!]
* 付属ツールによる解析
* 性能劣化要因(リソース枯渇、ロック競合)
#### 重要な用語、コマンド、パラメータなど：
* shared_preload_libraries
* auto_explain
* auto_explain.*
* log_min_duration_statement
    + 整数値を設定し、指定したミリ秒以上を要したSQL文と実行時間を出力する
    + 0に設定すれば、すべてのSQL文について出力される [●]
    + -1に設定すると、出力しない
* pg_stat_statements：実行された全てのSQL文の実行時の統計情報を記録する
* 【追加】log_autovacuum_min_duration
* 【追加】log_lock_waits
* 【追加】log_checkpoints
* 【追加】log_temp_files


## パフォーマンスチューニング（20％）
### 性能に関係するパラメータ 【重要度：4】 
    データベースの設定パラメータで、特にパフォーマンスに影響を与えるもの、パフォーマンスチューニングの参考になるものに関する理解を問う
#### 主要な知識範囲：
* 資源の消費 (RESOURCE USAGE)
* ログ先行書き込み (WRITE AHEAD LOG)
* 問い合わせ計画 (QUERY TUNING)
* 実行時統計情報 (RUNTIME STATISTICS)
* ロック管理 (LOCK MANAGEMENT) [!]
* 軽量ロックと重量ロック
#### 重要な用語、コマンド、パラメータなど：
* shared_buffers：共有バッファのサイズを設定。推奨値はサーバ実メモリの25%
* wal_bufferes：WALバッファのサイズを設定
    + wal_buffersを数キロバイトの小さなデフォルトより増加させることは書き込みが激しいシステムで役に立ちます。 ベンチマークでは通常、多少大規模なシステムでは1MBまで増やすだけで十分であると提案します。 またWALセグメント全体（16MB、ここでは有用な上限）を割り当てる最近のサーバでメモリを提供することが合理的です。 wal_buffersの変更はデータベースの再起動が必要です。 
    + PostgreSQL 9.1から、wal_buffersはデフォルトでshared_buffersの容量の1/32になり、また上限は16MB（shared_buffersが512MBの時に達する値）になりました。
* 【追加】huge_pages
* effective_cache_size [●]
    + オペレーティングシステム自体と他のアプリケーションが使用するメモリを考慮した後に、OSおよびデータベース自体の内部でディスクキャッシュとして利用可能なメモリ量の推定値に設定されなければなりません
    + この値はPostgreSQL問い合わせプランナが生成した計画の内いずれがメモリに合うかどうかを推定するためだけに使用されます。
    + この設定が小さすぎると、インデックスの利用を想定している問い合わせを実行する時に、インデックスが使用されない可能性があります。 shared_buffersの設定はここでは考慮されません。効率的なcache_size_valueのみです。データベースに占有されるメモリを含めなければなりません。 
    + effective_cache_sizeを全メモリの1/2に設定することが通常の保守的な設定です。 メモリの3/4はより積極的ですが、まだ合理的な値です。
* work_mem：問い合わせ時のソートやハッシュデータ格納時に使用するメモリのサイズ [●]
* 【追加】maintenance_work_mem：Vacuum文やALTER TABLEなどのメンテナンス操作時に使用するメモリのサイズ
    + 複雑なソート処理を多く実行し、かつ大量のメモリがあるのであれば、work_memパラメータを増やすことによりPostgreSQLはメモリ内で大規模なソートを行うことができるようになります。
    + 基本的にバキュームが始まる時にそのメモリを確保する必要がありますので、より有用な目的で使用できなくなります。 体験に基づくものですが、256MB程度で十分な大きさです。 
* 【追加】autovacuum_work_mem
* 【追加】wal_level
* fsync
* synchronous_commit
* 【追加】checkpoint_timeout：チェックポインタの動作周期
	+ 閾値に達すると、共有バッファの情報がデータファイルへ書き込まれる。
	+ 書き込み処理の間はI/O負荷が高くなり問い合わせ性能に影響を及ぼす。
	+ 適切な値を設定し書き込みの周期や上限を設定する。
* 【追加】checkpoint_completion_target
    + PostgreSQLはデータベースにおける新しいトランザクションをWALセグメントという名前の16MBサイズのファイルに書き出します。 checkpoint_segments個のファイルが書き出される度（デフォルトは3）に、チェックポイントが発生します。 チェックポイントはリソースを激しく消費することがあり得ます。 最近のシステムでは48MBごとにこれを行うと、性能上深刻なボトルネックとなります。 checkpoint_segmentsをより大きく設定することでこれを改善することができます。 非常に小規模な設定で実行していない限り、最低10に設定することで確実に改善されます。 これにより通常目標の完成度を増大させます。
* deadlock_timeout


### チューニングの実施 【重要度：2】
    データベース、およびSQLのチューニングに関する理解を問う
#### 主要な知識範囲：
* パラメータのチューニング [!]
    + CPU
    + メモリ
    + 共有メモリ
    + ディスク
* 実行計画のチューニング [!]
* SQL のチューニング
* 【追加】テーブル構成のチューニング
* ディスクI/Oの分散 [!]
* パラメータの反映方法(パラメータ有効化のために必要なアクション)
* インデックスがSQLの性能に与える影響
* Index Only Scan と Visibility Map
#### 重要な用語、コマンド、パラメータなど：
* Index Only Scan


## 障害対応（20％）
### 起こりうる障害のパターン 【重要度：3】 
    データベースでのSQL実行タイムアウトやサーバダウン、動作不良、データ消失、OSリソース枯渇などの故障が発生した場合について、エラーメッセージの内容から原因を特定し、適切な対応ができるかを問う
#### 主要な知識範囲：
* サーバダウン、動作不良、データ消失への対処 [!]
* OS リソース枯渇 [!]
* OSのパラメータ
* サーバプロセスの状態(idle、idle in transaction、active)
* シグナル(TERM/INT/HUP)によるサーバプロセスへの影響
* サーバプロセスのクラッシュ(セグメンテーションフォルトなど)と影響範囲
#### 重要な用語、コマンド、パラメータなど：
* 【追加】statement_timeout
* 【追加】lock_timeout
* 【追加】idle_in_transaction_session_timeout
* 【追加】スタンバイでの問い合わせのコンフリクト(衝突)
* 【追加】hot_standby_feedback
* vacuum_defer_cleanup_age
* max_standby_archive_delay
* max_standby_streaming_delay
* fsync
* 【追加】synchronous_commit
* 【追加】restart_after_crash
* pg_cancel_backend()
* pg_terminate_backend()
* pg_ctl kill
* max_locks_per_transaction
* max_files_per_process


### 破損クラスタ復旧 【重要度：2】
    データファイルやトランザクションログファイルが破損した場合について、エラーメッセージの内容から原因を特定し、適切な対応ができるかを問う
#### 主要な知識範囲：
* 【追加】トランザクションログ復旧 [!]
* システムテーブルのインデックス復旧 [!]
* 開発者向けオプション
* テーブル・インデックスの実ファイルとパス
* Relfilenode と OID
* インデックス破損とREINDEXによる復旧
* チェックサムによる破損検知と復旧
* トランザクションIDの周回エラー
#### 重要な用語、コマンド、パラメータなど：
* 【追加】PITR
    + 任意のリストアポイント(特定の文字列で作成される)まで
    + 任意のトランザクションIDまで
    + 最後のWALログ位置まで
    + 任意の時刻まで
* pg_resetwal
    + pg_resetxlog
* ignore_system_indexes
* ignore_checksum_failure
* コミットログ(pg_xact)
* シングルユーザモード
* 【追加】VACUUM FREEZE


### ホット・スタンバイ復旧 【重要度：1】
    レプリケーション構成でプライマリ側やスタンバイ側のPostgreSQLが停止・故障した場合について、適切な対応ができるかを問う
#### 主要な知識範囲：
* ストリーミングレプリケーションとロジカルレプリケーション
    + ストリーミングレプリケーション：マスタースレーブ構成において、プライマリの更新内容ごとに（WALレコードごとに）スタンバイへと送る機能
		- スタンバイでは送られてきたWALを実行することで、プライマリと同じ状態を保つことができる。
		- 実際にはプライマリ側のwalsenderプロセスと、スタンバイ側のwalreceiverプロセスでやりとりを行う
* ログファイル内のエラーメッセージ
* スタンバイへ伝搬される処理とされない処理
* プライマリ側PostgreSQLの停止・故障と再開(再起動)の方法
* スタンバイ側PostgreSQLの停止・故障と再開(再起動)の方法
* 【追加】ロジカルレプリケーションのサブスクライバ―へ伝搬される処理とされない処理
* 【追加】ロジカルレプリケーションのサブスクライバ―でのコンフリクト
#### 重要な用語、コマンド、パラメータなど：
* pg_ctl promote
* 【変更】pg_receivewal
* 【追加】pg_rewind

### おまけ
#### リストアの設計
稼働率
年間停止時間
バックアップとリストアの方針
90％
36.5日間
月に複数回のメンテナンス時間を設けることができる。論理バックアップや物理バックアップとリストアで十分に対応できる
99％
3.65日間
オンプレミスなら予備のマシンが必要になる。大規模なデータの場合はリストアの所要時間の把握などが必要になる
99.9％
8.7時間
法定停電や24時間365日対応などシステム以外の部分にも影響が出る99.99％ 52分間バックアップからのリストアだけでは達成が難しいため，コールドスタンバイなど冗長化のしくみが必要になる
99.999％
5分間
レプリケーションを利用した，すぐに切り替えられる予備サーバ（ホットスタンバイ）やDR（Disaster Recovery）などの専用のしくみが必要になる
99.9999％
32秒間
無停止で運用する専用サーバや，大規模な冗長構成のシステムやハードウェアが必要になり，急激にコストが高くなる
#### ネットワーク接続設定
* IPv6の無効化
#### 関数
* generate_series
#### contrib 
    contrib モジュール (追加で提供されるモジュール) を紹介します。
* dblink  
    + 他の PostgreSQL データベースを SQL から直接操作できるモジュールである "dblink" の使い方を紹介します。dblink を使うと、分散環境で複数のデータベースをまたがる処理を行ったり、同じサーバ内の別のデータベースを操作することができます。
* pgbenchの使いこなし  
    + pgbenchはPostgreSQLに同梱されているシンプルなベンチマークツールです。 pgbenchを利用することにより、自分の使っているPostgreSQLの性能を数値で把握することができるようになり、チューニングの結果を確認したり、ハードウェアをアップグレードしたときの効果を客観的に見ることが可能です。
* pgcrypto [●]
    + contribモジュールのpgcryptoを使うとデータベース内のデータを暗号化できます。特定のカラムごとに暗号化でき、ディスクの盗難だけでなく、データベースにログインされてしまった場合にも機密データを守ることができます。
* pg_upgrade [●]
    + PostgreSQLのアップグレードを容易に実施可能とするサポートツール「pg_upgrade」がPostgreSQL9.0のcontribモジュールとして開発されました。どのようにアップグレードをサポートしてくれるのかを紹介します。
* file_fdw  
    + file_fdwは、PostgreSQL 9.1のSQL/MED機能を利用し、外部のタブ区切りまたはCSVファイルを直接テーブルの形で参照するためのモジュールです。COPYコマンドに似ていますが、データの複製を避けたり、加工しながら取り込む場合に便利です。
* passwordcheck 
    + passwordcheckは、PostgreSQLのユーザやロールに指定するパスワードに対して検査を行い、弱い(推測されやすい)文字列を弾く仕組みを提供するcontribモジュールです。本記事では、passwordcheckモジュールの概要と使い方、およびその拡張について解説します。
