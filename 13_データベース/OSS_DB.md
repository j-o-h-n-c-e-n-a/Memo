## 参照
* [サンプル問題](https://oss-db.jp/sample)
* [OSS-DB入門](https://oss-db.jp/dojo#dojo_nyumon)
* [オススメ！OSS-DB情報](https://oss-db.jp/dojo#dojo_column)


## 一般知識（16％）
### OSS-DBの一般的特徴　【重要度：4】
    PostgreSQLの機能概要、ライセンス、OSSのコミュニティの役割などに関する理解を問う
#### 主要な知識範囲：
* PostgreSQLの機能全般、OSS-DBおよびOSS一般のライセンス、OSS-DBのコミュニティ、活動内容、参加方法など
* 【追加】メジャーバージョン / マイナーバージョン
* 【追加】リリースサイクル / サポートポリシー / バグ報告
### リレーショナルデータベースに関する一般知識　【重要度：4】
    リレーショナルデータベースの基本概念、一般的知識を問う
#### 主要な知識範囲：
* リレーショナルデータモデルの基本概念
* データベース管理システムの役割
* SQL に関する一般知識
* SQLの 分類 (DDL / DML / DCL)
* データベースの設計と正規化


## 運用管理（52％）
### インストール方法　【重要度：2】
    PostgreSQLのインストール方法、データベースクラスタの作成方法などに関する理解を問う
#### 主要な知識範囲：
* initdbコマンドの使い方
* データベースクラスタの概念と構造
* テンプレートデータベース
#### 重要な用語、コマンド、パラメータなど：
* initdb
* pg_ctl initdb
* PGDATA
* template0
* template1
### 標準付属ツールの使い方 【重要度：5】
    Sのコマンドプロンプトから実行できる管理用ツールの使い方を問う
#### 主要な知識範囲：
* データベース管理用コマンドの使い方
#### 重要な用語、コマンド、パラメータなど：
* pg_ctl
* createuser
* dropuser
* createdb
* dropdb
* psql
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
* pg_dump
* pg_dumpall
* pg_restore
* psql
* pg_basebackup
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
* 自動バキュームの概念と動作
* システム情報関数
* 情報スキーマとシステムカタログ
* テーブル単位の権限（GRANT/REVOKE）
#### 重要な用語、コマンド、パラメータなど：
* 【追加】pg_ctl start / stop
* 【変更】CREATE/ALTER/DROP ROLE/USER
* VACUUM
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
#### 主要な知識範囲：
* トランザクションの構文
* 【変更】トランザクション分離レベル(リードコミッティド、リピータブルリード、シリアライザブル)
* LOCK 文
* 行ロックとテーブルロック
* 【追加】デッドロック
#### 重要な用語、コマンド、パラメータなど：
* BEGIN
* COMMIT
* ROLLBACK
* SAVEPOINT
* SET TRANSACTION
* LOCK TABLE
* 【追加】SELECT FOR UPDATE / SHARE
