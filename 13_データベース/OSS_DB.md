# 参照
* [サンプル問題](https://oss-db.jp/sample)
* [OSS-DB入門](https://oss-db.jp/dojo#dojo_nyumon)
* [オススメ！OSS-DB情報](https://oss-db.jp/dojo#dojo_column)

# OSS-DB Silver
## 一般知識（16％）
### OSS-DBの一般的特徴　【重要度：4】
    PostgreSQLの機能概要、ライセンス、OSSのコミュニティの役割などに関する理解を問う
#### 主要な知識範囲：
* PostgreSQLの機能全般、OSS-DBおよびOSS一般のライセンス、OSS-DBのコミュニティ、活動内容、参加方法など
* 【追加】メジャーバージョン / マイナーバージョン
    + バージョン：x.y
    + メジャーバージョン(x)：機能追加を含んだもの
    + マイナーバージョン(y)：セキュリティやバグ対応
* 【追加】リリースサイクル / サポートポリシー / バグ報告

### リレーショナルデータベースに関する一般知識　【重要度：4】
    リレーショナルデータベースの基本概念、一般的知識を問う
#### 主要な知識範囲：
* リレーショナルデータモデルの基本概念
* データベース管理システムの役割
* SQL に関する一般知識
    + 最新の標準規格：SQL:2016
    + Postgresの対応状況：SQL:2011の一部まで（SQL:2008には完全準拠）
* SQLの 分類 (DDL / DML / DCL)
    + DDL（CREATE TEBLE）
    + DML（UPDATE/DELETE/INSERT）
* データベースの設計と正規化


## 運用管理（52％）
### インストール方法　【重要度：2】
    PostgreSQLのインストール方法、データベースクラスタの作成方法などに関する理解を問う
* データベースクラスタ：1つ以上のデータベースと、管理情報・設定ファイルが集まったもの 
    + PostgreSQLは、データベースクラスタ単位で起動・停止を行う 
    + 実体は構築時に指定するPostgreSQL関連の最上位のディレクトリ
       (ディレクトリを指す場合は、「データディレクトリ」と記載される) 
    + 環境変数$PGDATAにデータディレクトリのパスを設定しておく
#### 主要な知識範囲：
* initdbコマンドの使い方
* データベースクラスタの概念と構造
* テンプレートデータベース
#### 重要な用語、コマンド、パラメータなど：
* initdb：データベースクラスタの初期化 
* pg_ctl initdb
* PGDATA
* template0
* template1

### 標準付属ツールの使い方 【重要度：5】
    Sのコマンドプロンプトから実行できる管理用ツールの使い方を問う
#### 主要な知識範囲：
* データベース管理用コマンドの使い方
#### 重要な用語、コマンド、パラメータなど：
* pg_ctl：データベースの起動・停止
* createuser：データベースユーザの作成
    + 初期ユーザ(一般にpostgresユーザと表記される)はスーパーユーザ
    + ログイン属性を持つユーザを作成 
        - (SQL)CREATE ROLE文
* dropuser
* createdb：データベースの作成
* dropdb：データベースの削除
* psql：データベースに接続、SQL発行
* メタコマンド

### 設定ファイル 【重要度：5】
    設定ファイルの使い方、基本的な設定パラメータに関する知識を問う
#### 主要な知識範囲：
* postgresql.confに関する以下の4項目
    +  記述方法
    +  接続と認証
    +  クライアント接続デフォルト
    +  エラー報告とログ取得
* pg_hba.confの設定方法
* SET/SHOWの使い方
#### 重要な用語、コマンド、パラメータなど：
* postgresql.conf
* pg_hba.conf
* pg_ctl reload/restart
* 【追加】pg_settings

### バックアップ方法 【重要度：7】
    PostgreSQLのバックアップ方法に関する理解を問う
#### 主要な知識範囲：
* 各種バックアップコマンドの使い方
* ファイルシステムレベルのバックアップとリストア
* ポイントインタイムリカバリ(PITR)の概念と手順
* 【追加】トランザクションログ(WAL)とWALアーカイブ
* 【追加】pg_start_backup() / pg_stop_backup()
* COPY文(SQL)、¥copyコマンド(psql)の使い方
#### 重要な用語、コマンド、パラメータなど：
* pg_dump：論理バックアップの取得
* pg_dumpall
* pg_restore：論理バックアップを利用したリストア
* psql
* pg_basebackup：物理バックアップの取得
* PITR
* 【追加】recovery.conf
* COPY
* ¥copy

### 基本的な運用管理作業 【重要度：7】
    データベース管理者として実行する基本的な運用管理コマンドに関する知識を問う
#### 主要な知識範囲：
* 【追加】PostgreSQLの起動・停止方法
* 【追加】データベースロール / ユーザの概念
* 【変更】データベースロール / ユーザの追加・削除・変更方法
* VACUUM、ANALYZEの目的と使い方 
    + 1行の更新であっても、繰り返すことでデータが肥大化していく 
    + 不要な行を定期的に削除するVACUUM処理が必要
* 自動バキュームの概念と動作
    + VACUUMは通常の更新を妨げないよう、該当行にのみ弱いロックを必要とする 
        - VACUUMと競合する処理が明示された場合、VACUUMがキャンセルされる 
        - VACUUMのオプションとして、ロック強度が強く、効果が高いコマンドも存在 
* システム情報関数
* 情報スキーマとシステムカタログ
* テーブル単位の権限（GRANT/REVOKE）
#### 重要な用語、コマンド、パラメータなど：
* 【追加】pg_ctl start / stop
* 【変更】CREATE/ALTER/DROP ROLE/USER
* VACUUM
    + FULLオプション：FULLオプションを指定すると、postgresqlは、更新/削除された行の切り詰めを行う。
* ANALYZE
* vacuumdb
* 【追加】autovacuum
* current_user
* version
* information_schema
* GRANT
* REVOKE


## 開発/SQL（32％）
### SQL コマンド 【重要度： 13】
    基本的なSQL文およびデータベースの構成要素に関する知識を問う
#### 主要な知識範囲：
* SELECT 文
* INSERT 文
* UPDATE 文
* DELETE 文
* データ型
* テーブル定義
* インデックス
* ビュー
* 【追加】マテリアライズドビュー
* ルール
* トリガー
* シーケンス
* スキーマ
* 【追加】テーブルスペース
* 【追加】パーティション
* 関数定義 / 【追加】プロシージャ定義
* PL/pgSQL
#### 重要な用語、コマンド、パラメータなど：
* SELECT/INSERT/UPDATE/DELETE
* FROM
* JOIN
* WHERE
* INTO
* VALUES
* SET
* LIMIT
* OFFSET
* ORDER BY
* DISTINCT
* GROUP BY
* HAVING
* EXISTS
* IN
* NOT
* INTEGER
* SMALLINT
* BIGINT
* NUMERIC
* DECIMAL
* REAL
* DOUBLE PRECISION
* CHAR
* CHARACTER
* VARCHAR
* CHARACTER VARYING
* TEXT
* BOOLEAN
* DATE
* TIME
* TIMESTAMP
* INTERVAL
* SERIAL
* BIGSERIAL
* 【追加】BYTEA
* NULL
* CREATE/ALTER/DROP TABLE
* PRIMARY KEY
* FOREIGN KEY
* REFERENCES
* UNIQUE
* NOT NULL
* CHECK
* DEFAULT
* 【追加】CREATE/ALTER/DROP INDEX/VIEW/MATERIALIZED VIEW/RULE/TRIGGER/SCHEMA/SEQUENCE/TABLESPACE/FUNCTION/PROCEDURE
* 【追加】CREATE TABLE PARTITION BY/OF
* 【追加】ALTER TABLE ATTACH/DETACH PARTITION

### 組み込み関数 【重要度：2】
    データベースで標準的に利用できる関数および演算子に関する知識を問う
#### 主要な知識範囲：
* 集約関数
* 算術関数
* 演算子
* 文字列関数
* 文字列演算子 / 述語
* 時間関数
#### 重要な用語、コマンド、パラメータなど：
* count
* sum
* avg
* max
* min
* char(character)_length
* lower
* upper
* substring
* replace
* trim
* ||
* ~
* LIKE
* SIMILAR TO
* age
* now
* current_date
* current_timestamp / 【追加】statement_timestamp / 【追加】clock_timestamp
* current_time
* extract
* to_char

### トランザクションの概念 【重要度：1】
    トランザクション機能に関する知識を問う
* 現実の処理をコンピュータで扱うための考え方 
* 適切なロックを獲得する（獲得できない場合は待機する）ことで、同時に同じデータ が複数人から更新されることを防ぎ、また、同時に反映されるべきある一連の更新は、 読み取り一貫性により他者から途中の段階を見られることは無い。 
#### 主要な知識範囲：
* トランザクションの構文
* 【変更】トランザクション分離レベル(リードコミッティド、リピータブルリード、シリアライザブル)
* LOCK 文
* 行ロックとテーブルロック
    + 同じ行に対する更新を防ぐ仕組み 
    + DMLの対象行はロックされ、別トランザクションの操作を待機させる
* 【追加】デッドロック
    + 2つのトランザクションがロックを取り合う状態 
        - 片方がエラーになりトランザクション失敗 
        - 他方はロック待ちが終わり成功
#### 重要な用語、コマンド、パラメータなど：
* BEGIN
* COMMIT
* ROLLBACK
* SAVEPOINT
* SET TRANSACTION
* LOCK TABLE
* 【追加】SELECT FOR UPDATE / SHARE

## その他
### メモリ領域
#### 共有メモリ 
    共有メモリとはすべてのプロセスで共有する領域。
    大きく分けて共有バッファとWALバッファが存在する。
* 共有バッファ 
    + ディスクから読み取ったデータをキャッシュして、以降のユーザ要求に高速に応答 
* WALバッファ 
    + ログ先行書き込み(Write Ahead Logging) 
    + 耐障害性とパフォーマンスを両立するための仕組み 
#### セッションメモリ 
    セッション毎に確保される領域 
* ワークメモリ 
    + ソートやハッシュの一時領域 
* メンテナンスワークメモリ 
    + メンテナンス操作

### プロセス
    PostgreSQLではマルチプロセスモデルを採用。
    プロセスは大きく分けてマスタサーバプロセス、バックグラウンドプロセス、バックエンドプロセスが存在する。
#### 必須プロセス 
* postgres(postmaster)、postgres backend 
    + クライアントからの接続を待ち受ける、すべてのプロセスの親プロセス 
    + postgresプロセスによって起動され、クライアントからの処理を担当 
* writer 
    + 共有バッファのデータをディスクに書き込むプロセス 
    + チェックポイントやダーティバッファの書き込み 
* wal writer 
    + データの変更履歴をWALファイルに書き込む
#### パラメータ設定により起動するプロセス 
* logger 
    + PostgreSQLサーバ実行時のログを記録するプロセス 
    + パラメータ設定により有効化し、何をどこに保存するか指定できる 
* archive 
    + チェックポイント以前の不要なWALをPITRのために別のディスクに退避 
* autovacuum launcher/worker 
    + 自動VACUUMを実行 
* stats collector 
    + 実行時統計情報を収集する


# OSS-DB Gold
## 運用管理（30％）
### データベースサーバ構築 【重要度：2】
    サーバ構築における容量見積もり、およびデータベースセキュリティに関する知識を問う
#### 主要な知識範囲：
* テーブル・インデックス容量見積もり
* セキュリティ
    + 通信経路暗号化（SSL)
    + データ暗号化
    + クライアント認証
    + 監査ログ
* データ型のサイズ
* ユーザ・データベース単位のパラメータ設定
#### 重要な用語、コマンド、パラメータなど：
* チェックサム
* 【変更】pg_xact
* pg_multixact
* pg_notify
* pg_serial
* pg_snapshots
* pg_stat_tmp
* pg_subtrans
* pg_tblspc
* pg_twophase
* 【追加】ssl
* 【追加】pg_stat_ssl
* 【追加】pgcrypto
* ALTER ROLE
* ALTER DATABASE
* initdb -data-checksums (-k)
* log_statement
* track_functions
* track_activities

### 運用管理用コマンド全般 【重要度：4】
    データベースの運用管理に関する高度な知識を問う
#### 主要な知識範囲：
* バックアップ、PITR
* VACUUM、ANALYZE、REINDEX
* 自動バキューム
* 【追加】チェックポイント
* サーバログ管理
* ディスク容量監視
* 自動VACUUMと手動VACUUM/ANALYZEの違い
#### 重要な用語、コマンド、パラメータなど：
* ALTER SYSTEM
* ANALYZE
* CLUSTER
* REINDEX
* VACUUM
* 【追加】CHECKPOINT
* PITR
* WAL
* pg_dump 
* pg_dumpall
* pg_basebackup
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
* log_duration
 
### データベースの構造 【重要度：2】
    データベースの物理的な構造に関する知識を問う
#### 主要な知識範囲：
* データベースクラスタの構造
* プロセス構造
* データの格納方法
#### 重要な用語、コマンド、パラメータなど：
* autovacuum
* TOAST
* FILLFACTOR
* アーカイブログ
* ページヘッダ
* タプルヘッダ
* postmasterプロセス
* postgresプロセス
* バックグラウンドプロセス
* SQL実行のキャンセル
* シグナル(TERM/INT/HUP)によるサーバプロセスへの影響

### ホット・スタンバイ運用 【重要度：1】
    レプリケーション構成を組むための設定や構築手順、およびレプリケーションの仕組み(プロセスやフロー)、状態の監視などに関する知識を問う
#### 主要な知識範囲：
* 【変更】ストリーミングレプリケーション機能とロジカルレプリケーション機能の概要
* 【変更】同期レプリケーションと非同期レプリケーション
* postgresql.conf、recovery.confの設定
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
* 【変更】walsenderプロセス
* 【変更】walreceiverプロセス
* 【変更】pg_receivewal
* トランザクションログ(WAL)
* スタンバイへ伝搬される処理とされない処理
* 【追加】スタンバイで実行可能な問い合わせ
* 【追加】ロジカルレプリケーションのサブスクライバ―へ伝搬される処理とされない処理

## 性能監視（30％）
### アクセス統計情報 【重要度：3】 
    データベースの利用状況を示す稼働統計情報の内容や見方、収集方法に関する知識を問う
#### 主要な知識範囲：
* pg_locks
* pg_stat_activity、pg_stat_database
* pg_stat_all_tables 等、行レベル統計情報
* pg_statio_all_tables 等、ブロックレベル統計情報
#### 重要な用語、コマンド、パラメータなど：
* pg_stat_archiver
* pg_stat_bgwriter
* 【追加】待機イベント(pg_stat_activity.wait_event)
* 【追加】pg_stat_progress_vacuum

 
### テーブル / カラム統計情報 【重要度：2】
    プランナが利用するテーブル・カラムの統計情報についての理解を問う
#### 主要な知識範囲：
* pg_class
* pg_stats
* テーブル・インデックスの実ファイルとパス
* 実行計画時に利用される統計情報やパラメータ
#### 重要な用語、コマンド、パラメータなど：
* pg_statistic
* pg_stats
* null_frac
* n_distinct
* most_common_freqs
* histogram_bounds
* correlation
* default_statistics_target
* effective_cache_size

 
### クエリ実行計画 【重要度：3】
    EXPLAINが出力する実行計画を読み取り、チューニングを行う。
#### 主要な知識範囲：
* EXPLAIN / EXPLAIN ANALYZE 出力
* 計画型
* EXPLAINからのチューニング
* 結合の種類(Nested Loop、Hash、Merge)と性能特性
* SQL構文(JOIN/GROUP BY/ORDER BY/LIMIT)に対応する実行計画
* 集約関数(sum/count)を伴うSQLに対応する実行計画
* 【追加】パーティションに対するSQLの実行計画
* 【追加】パラレルクエリに対応する実行計画
* 【追加】ウィンドウ関数(row_number/rankなど)のSQLに対応する実行計画
#### 重要な用語、コマンド、パラメータなど：
* 【追加】EXPLAIN / EXPLAIN ANALYZE

 
### その他の性能監視 【重要度：1】
    性能監視に関するその他の手法
#### 主要な知識範囲：
* スロークエリの検出
* 付属ツールによる解析
* 性能劣化要因(リソース枯渇、ロック競合)
#### 重要な用語、コマンド、パラメータなど：
* shared_preload_libraries
* auto_explain
* auto_explain.*
* log_min_duration_statement
* pg_stat_statements
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
* ロック管理 (LOCK MANAGEMENT)
* 軽量ロックと重量ロック
#### 重要な用語、コマンド、パラメータなど：
* shared_buffers
* 【追加】huge_pages
* effective_cache_size
* work_mem
* 【追加】maintenance_work_mem
* 【追加】autovacuum_work_mem
* 【追加】wal_level
* fsync
* synchronous_commit
* 【追加】checkpoint_timeout
* 【追加】checkpoint_completion_target
* deadlock_timeout


### チューニングの実施 【重要度：2】
    データベース、およびSQLのチューニングに関する理解を問う
#### 主要な知識範囲：
* パラメータのチューニング
    + CPU
    + メモリ
    + 共有メモリ
    + ディスク
* 実行計画のチューニング
* SQL のチューニング
* 【追加】テーブル構成のチューニング
* ディスクI/Oの分散
* パラメータの反映方法(パラメータ有効化のために必要なアクション)
* インデックスがSQLの性能に与える影響
* Index Only Scan とVisibility Map
#### 重要な用語、コマンド、パラメータなど：
* Index Only Scan


## 障害対応（20％）
### 起こりうる障害のパターン 【重要度：3】 
    データベースでのSQL実行タイムアウトやサーバダウン、動作不良、データ消失、OSリソース枯渇などの故障が発生した場合について、エラーメッセージの内容から原因を特定し、適切な対応ができるかを問う
#### 主要な知識範囲：
* サーバダウン、動作不良、データ消失への対処
* OS リソース枯渇
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
* 【追加】トランザクションログ復旧
* システムテーブルのインデックス復旧
* 開発者向けオプション
* テーブル・インデックスの実ファイルとパス
* Relfilenode と OID
* インデックス破損とREINDEXによる復旧
* チェックサムによる破損検知と復旧
* トランザクションIDの周回エラー
#### 重要な用語、コマンド、パラメータなど：
* 【追加】PITR
* pg_resetwal
* ignore_system_indexes
* ignore_checksum_failure
* コミットログ(pg_xact)
* シングルユーザモード
* 【追加】VACUUM FREEZE


### ホット・スタンバイ復旧 【重要度：1】
    レプリケーション構成でプライマリ側やスタンバイ側のPostgreSQLが停止・故障した場合について、適切な対応ができるかを問う
#### 主要な知識範囲：
* ストリーミングレプリケーションとロジカルレプリケーション
    + ストリーミングレプリケーション
        - マスタースレーブ構成において、プライマリの更新内容ごとに（WALレコードごとに）スタンバイへと送る機能
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
