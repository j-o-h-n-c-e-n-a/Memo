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
    コマンドプロンプトから実行できる管理用ツールの使い方を問う
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
    + 更新内容が書かれている「WALレコード」単位で構成され最大16Mバイト
    + WALレコードにはLSN（Log Sequence Number）とよばれる番号が振られている
    + max_wal_size の値によりファイルの総数が決まり、ファイルの総数に達すると、古いファイルから上書かれていく
    + 上書きによるWALの消失を防ぐために、WALアーカイブファイルとして残すこともできる
    + WALライタプロセスによってWALバッファのデータが書き込まれる
* 【追加】pg_start_backup() / pg_stop_backup()
* COPY文(SQL)、¥copyコマンド(psql)の使い方
#### 重要な用語、コマンド、パラメータなど：
* pg_dump：論理バックアップの取得（SQLコマンドが含まれる場合がある）
* pg_dumpall
* pg_restore：論理バックアップを利用したリストア（pg_dumpコマンドと並列実行可能）
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
    + 追記型アーキテクチャ：1行の更新であっても、繰り返すことでデータが肥大化していく 
    + VACUUMの目的：不要な行を定期的に削除するVACUUM処理が必要
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
* ロングトランザクションの弊害
    + ロングトランザクションは長時間にわたりコミットもロールバックも行われないトランザクションを指します。その間、トランザクションの対象となったテーブルはロックされることになり、それが長時間に及ぶとさまざまな弊害が発生します。
    + VACUUMは実行中のトランザクションが参照する可能性のある不要領域を回収できません。
    + トランザクション中に発生しているロックのため、メンテナンス系のコマンドはトランザクション完了まで待たされることになります。
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
    + デフォルト値：shared_buffers = 128MB
    + ディスクから読み取ったデータをキャッシュして、以降のユーザ要求に高速に応答 
    + 実メモリが１GB以上の場合は1/4程度。Winodws上では512MB以内に設定
* WALバッファ 
    + デフォルト値：wal_buffers = -1 は shared_buffers の1/32が自動設定
    + ログ先行書き込み(Write Ahead Logging) 
    + 耐障害性とパフォーマンスを両立するための仕組み 
    + WALファイルのサイズと同じ16MBが最大値
#### セッションメモリ 
    セッション毎に確保される領域 
* ワークメモリ 
    + デフォルト値：work_mem = 4MB
    + ソートやハッシュの一時領域。不足すると一時ファイルを作成して処理する
* メンテナンスワークメモリ 
    + デフォルト値：maintenance_work_mem = 64MB
    + メンテナンス操作(バキュームやインデックス作成)に使用

### プロセス
    PostgreSQLではマルチプロセスモデルを採用。
    プロセスは大きく分けてマスタサーバプロセス、バックグラウンドプロセス、バックエンドプロセスが存在する。
#### 必須プロセス 
* postgres(postmaster)、postgres backend 
    + クライアントからの接続を待ち受ける、writer, wal writer, autovacuum launcher, stats collector などのプロセスの親プロセス 
    + postgresプロセスによって起動され、クライアントからの処理を担当 
    + データベースクラスタ1つに対して、postmaster というプロセス
* writer [●]
    + 共有バッファのデータをディスクに書き込むプロセス 
    + チェックポイントやダーティバッファの書き込み 
* wal writer [●]
    + データの変更履歴をWALファイルに書き込む
#### パラメータ設定により起動するプロセス 
* logger [●]
    + PostgreSQLサーバ実行時のログを記録するプロセス 
    + パラメータ設定により有効化し、何をどこに保存するか指定できる 
* archive [●]
    + チェックポイント以前の不要なWALをPITRのために別のディスクに退避 
* autovacuum launcher/worker [●]
    + 自動VACUUMを実行 
* stats collector [●]
    + 実行時統計情報を収集する
#### チューニング
* writer：ライタプロセスによるテーブルファイルへの書き込みが大量に発生すると、問い合わせ性能がおちる
    + bgwriter_delay：ライタプロセスの動作周期
    + bgwriter_lru_maxpages：一度にライタプロセスが書き込むページ数の上限
    + bgwriter_lru_multiplier：書き込みが必要になったページのうち、どのくらいの割合を書き込むべきか計算する際に使用

### プロセスとメモリとファイルの関係
#### WALバッファ -> WALライタプロセス -> WALファイル
* UPDATEなどの更新処理が発生した場合、まずWALバッファに更新情報が書き込まれる
* COMMITを行った契機でWALバッファの情報がWALライタプロセスによってWALファイルに書き込まれる
#### 共有バッファ -> ライタプロセス（or チェックポインタ） -> テーブルファイル・インデックスファイル
* UPDATEなどの更新処理が発生した場合、まず共有バッファ上のデータが更新される
* この更新された情報（ダーティーページ）はすぐにはデータファイルには反映されない 
    + 随時データファイルへの書き込みを行うとI/Oが頻発してパフォーマンス上よろしくない
* ダーティーページのデータファイルへの書き込みはライタプロセスおよびチェックポインタで行われる 
    + 書き込み時はI/Oが発生するので、問い合わせが遅くなる原因にもなる

