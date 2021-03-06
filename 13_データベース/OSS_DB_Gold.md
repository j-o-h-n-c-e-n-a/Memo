
# OSS-DB Gold
## 運用管理（30％）
### データベースサーバ構築 【重要度：2】
    サーバ構築における容量見積もり、およびデータベースセキュリティに関する知識を問う
#### 主要な知識範囲：
##### テーブル・インデックス容量見積もり [!]
    PostgreSQLのデータ容量を見積もるにはテーブル・インデックス・WAL・アーカイブログ・ログファイルの容量を見積もる必要があります。次のクエリで容量を確認することができます。
* postgres=# select pg_column_size(any);
    + 特定の値を格納するのに使用されるバイト数
* postgres=# select pg_tablespace_size(oid or name);
    + 指定されたテーブルスペースで使用されたディスク領域
* postgres=# select pg_database_size(oid or name);
    + 指定されたデータベースで使用されたディスク領域
* postgres=# select pg_relation_size(oid or text);
    + 指定されたテーブルまたはインデックスで使用されたディスク領域
* postgres=# select pg_total_relation_size(oid or text)
    + 指定されたテーブルで使用されるディスク領域(インデックスとtoast含む)
* postgres=# select pg_size_pretty(bigint)
    + 容量単位の形式に変換したバイト数表示
###### テーブル容量計算
* 1行のサイズ = 28(行)　+ 各フィールドのサイズ
* 必要ブロック数　= 行数　/ 1ブロック
* 実容量　＝ 必要ブロック × 8192(ブロックサイズ)
###### インデックス容量見積もり
* ノード = 12(管理ヘッダ) + インデックスデータ
* ノード数 =｛8192(ブロックサイズ) * fillfactor – 40(ブロックヘッダ)｝ / ノード
* 必要ブロック数 = 10000(行数)　/ ブロックノード数
* 容量 = 必要ブロック数 × 8192(ブロックサイズ) / 1024(KB計算)
###### WAL領域
    WAL領域を見積もるには次のように計算で見積もれます
* 1つのWALセグメントのサイズは16MB
```
16MB * (postgres.confのcheckpoint_segments * 3 + 1)
```
* 大量の更新などが発生すると上記で計算した容量を超える場合があります
##### セキュリティ [!]
###### クライアント認証
    クライアントからPostgresに通信するときに誰もがアクセスできてしまうと不正な人物がアクセスされ情報漏えいやデータ破損などの恐れがあります。
    クライアント毎に認証を設定することでその対策が行えます。
    データベースクラスタ(/var/lib/pgsql/9.6/data)内のpg_hba.confがクライアント認証の設定ファイルです。設定方法は、TYPE、DATABASE、USER、ADDRESS、METHODを区切って記載します。
* TYPE
    + local：Unixドメインのソケット通信
    + host：平分またはSSLでの通信
    + hostssl：SSLオンリー通信
    + hostnossl：平分オンリー通信
* DATABASE
    + all：全てのデータベース
    + sameuser：接続ユーザと同じ名前のデータベース
    + samerole：接続ロールと同じ名前のデータベース
    + replication：レプリケーション専用
    + データベース名：指定したデータベース
* USER
    + all：全てのユーザ
    + ロール名またはグループ名：指定したロールまたはグループ名(+またはカンマで区切って複数設定可能)
* ADDRESS
    + IPv4またはIPv6アドレス：接続元のIPアドレスを指定します。(prefix長での範囲指定可能) 
* METHOD
    + trust：無条件で許可
    + reject：無条件で拒否
    + md5：パスワード認証(md5ハッシュで比較)
    + password：パスワード認証(平文)
    + cert：SSL証明書にて認証
    + 認証方式：idnent,ldap、radius、sspi、gss、pam、peerなどの外部認証
###### 通信経路暗号化（SSL)
    クライアントからPostgresにはTCPで通信しますが、標準の設定では通信は平文のためデータが傍受されてしまうと 情報漏えいが発生いたします。
    PostgreSQLにはSSLを利用して暗号化した通信を行うことで対策になります。
    ※SSLで通信する場合、クライアント・サーバのOSに事前にOpenSSLが必要になります。
    インストール後もPostgresの設定で、SSLのサポートを有効にする必要があります。
    また、SSLを利用する場合、SSL証明証が必要になります。
* サーバ証明書：データベースクラスタ(/var/lib/pgsql/9.6/data)/server.crt
* サーバ秘密鍵：データベースクラスタ(/var/lib/pgsql/9.6/data)/server.key
* SSL証明書の利用
    + Postgresの設定ファイルを次のように修正します。
```
[postgresql.conf]
⇒ssl = on
[pg_hba.conf]
hostssl all all 0.0.0.0/0 md5
```
* 証明書の作成方法
1. データベースクラスタに移動
```
# cd /var/lib/pgsql/9.6/data
```
2. OpenSSLでRSAの秘密鍵を作成
```
# openssl genrsa 2048 > server.key
※2048はビット数
```
3. OpenSSLでCSRを作成
```
# openssl req -new -key server.key > server.csr
```
4. OpenSSLで証明書を作成
```
# openssl x509 -days 36500 -req -signkey server.key < server.csr > server.crt
※36500は有効期限（この場合100年）
```
5. 作成したファイルの所有権・グループを変更
```
# chown postgres:postgres server.*
```
6. server.keyのアクセス権限変更
```
# chmod 600 server.key
```
###### データ暗号化
    データベース内のデータを暗号化するにはcontribモジュールの1つであるpgcryptoを利用することで対応可能です。
###### 監査ログ
* ログの書込有無の設定
    + ログの書込有無の設定として、log_statementがありますが、設定値を次に記載いたします。
        - none：ログを記録しない
        - ddl：CREATE、ALTERなどddlのクエリログを記録
        - mod：ddl文に加え、INSERT、UPDATE、DELETE、TRUNCATE、COPYなど更新系のクエリログを記録
        - all：全てのクエリログに記録
* 接続/切断のログ
    + postgres.confに次を記載することで取得できます。
```
log_connections = on
log_disconnections = on
```
* テーブルの値に変更が発生した場合、ログ出力を行いたい場合はトリガプロシージャを利用すれば対応可能

##### データ型のサイズ
    Silverのデータ型参照
##### ユーザ・データベース単位のパラメータ設定

#### 重要な用語、コマンド、パラメータなど：
##### チェックサム
    利用するとPostgreSQLのデータブロックで破損した場合、検出します
* データベースクラスタ作成時のコマンドであるinitdbにオプションを付けるとデータチェックサムが有効になります。
* チェックサムはデータベースクラスタ全体ではなく、データをブロックに書き出す時に行います。
##### 【変更】pg_xact
    トランザクションのコミット状態のデータが保有されるディレクトリ
##### pg_multixact
    マルチトランザクション状態のデータを保有するサブディレクトリ（共有行ロックで使用されます）
##### pg_notify
    Listen/Notifyコマンド用ディレクトリ
* 通知を送信するために関数pg_notify(text,text)を使用することもできます。
* この関数は第1引数としてチャネル名、第2引数としてペイロードを取ります。
* 不定のチャネル名、ペイロードで作業しなければならない場合は、NOTIFYコマンドよりこの関数を使用する方がかなり簡単です。
##### pg_serial
    シリアル型の管理用ディレクトリ
##### pg_snapshots
    エクスポートされたスナップショットを保有するサブディレクトリ
    select pg_export_snapshot();でスナップショットを作成した場合にファイルが発生
##### pg_stat_tmp
    統計情報コレクタがバックエンドプロセスと必要な情報をやり取りするための一時ファイルが格納される
##### pg_subtrans
    サブトランザクション用ディレクトリ
##### pg_tblspc
    テーブル空間への[シンボリックリンク]が保有される
* テーブル空間の利用により、データベースクラスタとは別ディレクトリへのデータ格納が可能となるため、テーブルを複数のディスク装置に分散配置し、I/O性能の向上を図ることができます
##### pg_twophase
    2相コミット利用時のデータ
##### 【追加】ssl

##### 【追加】pg_stat_ssl
    接続（通常およびレプリケーション）あたり1行の形式で、接続に使われるSSLの情報を表示します。
##### 【追加】pgcrypto [●]
    データベース内のデータを暗号化する
##### ALTER ROLE
    ロールの属性を変更します
```
ALTER ROLE name [ [ WITH ] option [ オプション名 ] ]
```
##### ALTER DATABASE
    データベースの属性を変更します
```
ALTER DATABASE name [ [ WITH ] option [ オプション名 ] ]
```
##### initdb -data-checksums (-k)

##### log_statement
    実行したSQLのうち、どの種別のものをログ出力するかについて設定する
* オプション：none, ddl, mod, all
##### log_destination
    エラーログの書き込み方法
##### log_line_prefix
    ログの出力内容
* %a アプリケーション名
* %u ユーザ名
* %d データベース名
* %r 遠隔ホスト名、またはIPアドレス、およびポート番号
* %h 遠隔ホスト名、またはIPアドレス
* %p プロセス識別子
* %t ミリ秒無しのタイムスタンプ
* %m ミリ秒付きタイムスタンプ
* %i コマンドタグ
* %e SQLSTATE エラーコード
* %c セッションID
* %l 各セッションまたは各プロセスのログ行の番号
* %s プロセスの開始タイムスタンプ
* %v 仮想トランザクションID（backendID/localXID）
* %x トランザクションID （未割り当ての場合は0）
* %q 出力停止
* %% %文字そのもの
##### log_min_error_statement
    指定レベルのエラーが発生したときにクエリもログ出力します。
##### track_functions
    利用しないなら、noneで、手続き言語だけならplにし、c言語などを利用する場合はallを設定
##### track_activities
    現在実行されているコマンドに関する情報を取得する

### 運用管理用コマンド全般 【重要度：4】
    データベースの運用管理に関する高度な知識を問う
#### 主要な知識範囲：
##### バックアップ、PITR
    Silverのバックアップ参照
##### VACUUM、ANALYZE、REINDEX [!]
    VACUUM、ANALYZEは、Silverを参照
##### 自動バキューム [!]
    SilverのVACUUM参照
##### 【追加】チェックポイント

##### サーバログ管理
###### pg_clog
    トランザクションがコミットしたかロールバックしたかを管理するログ
###### pgstartup.log
    postgresql起動時ログ
    FATAL: 秘密キーファイル"server.key"をロードできませんでした: 許可がありません
###### pg_log
    基本的なログ(稼働時・スロークエリなど)

##### ディスク容量監視 [!]

##### 自動VACUUMと手動VACUUM/ANALYZEの違い
    自動バキュームデーモンはVACUUMだけではなくANALYZEも実行する場合があります。

#### 重要な用語、コマンド、パラメータなど：
##### ALTER SYSTEM
    サーバの設定(postgres.confで設定した一部の内容)を変更できます（スーパーユーザのみ）
* postgresサービスの再起動または設定再読み込み時にpostgresql.confに加えて読み込まれます
##### ANALYZE [●]
    ANALYZEでは、SHARE UPDATE EXCLUSIVEロックが取得されます。ANALYZEによって、SELECT文やINSERT文などの処理が阻害されることはありません。
##### CLUSTER
    インデックスに従ってテーブルをクラスタ化します
* テーブルデータが物理的に再編成され、読み込み性能が向上する可能性がある
* 実行されているテーブルに対する読み込みは待機される
* PRIMARY KEYが存在しなくても問題がなく、テーブルおよびインデックスサイズ少なくすることと性能が改善する可能性があります
* maintenance_work_memの値を大きくするとCLUSTERコマンドの性能が向上する可能性がある
* テーブルおよびインデックスサイズを削減できる可能性がある
##### REINDEX [●]
    インデックスの再構築・破損インデックスの修復・インデックス利用時の速度改善などで利用
* インデックス利用で遅い場合は、postgres.confのパラメータでrandom_page_costの値が小さく設定し・effective_cache_sizeを大きく設定すると改善されるケースもある
* pg_classのrelpages列、reltuples列でページ数・行数を確認して行数に比べてページ数が想定以上に多くなっている場合に実行する必要がある可能性がある
##### VACUUM [●]
* 対象テーブルの末尾が空ページで、排他ロックが取得できる場合、その領域をOSに返還する場合がある
###### VERBOSEオプション
    VERBOSEオプションを付加すると、VACUUM処理の進行状況などの詳細な情報が出力されます
###### ANALYZEオプション
    ANALYZEオプションを付加すると、VACUUM処理後に統計情報も更新されます
##### 【追加】CHECKPOINT

##### PITR [●]

##### WAL

##### pg_dump 

##### pg_dumpall

##### pg_basebackup [●]
* 別サーバで動作しているPostgreSQLデータベースクラスタのベースバックアップを取得できる
* fetch方式の場合、max_wal_sendersパラメータを少なくとも1以上に設定する必要がある
* オプションを明示的に指定しないで実行した場合は、WALはバックアップに含まれない
##### 【追加】pg_start_backup()

##### 【追加】pg_stop_backup()

##### postgresql.conf

##### recovery.conf

##### vacuumdb 

##### pgstattuple
    ユーザが確認するための集計済みのタプルレベルの統計情報が取得できます
* リレーションの物理長、不要なタプルの割合を確認して、VACUUMが必要かどうかを判断する
##### pg_cancel_backend()

##### pg_terminate_backend()

##### pg_isready
    サーバプロセスの状態を確認する
##### log_connections
    postgresql.conf：接続ログを取りたい場合に設定します
##### log_disconnections
    postgresql.conf：切断ログを取りたい場合に設定します
##### log_duration [●]
    true/falseの論理値を設定し、trueに設定するとSQL文の実行に要した時間を出力する
 
### データベースの構造 【重要度：2】
    データベースの物理的な構造に関する知識を問う
#### 主要な知識範囲：
##### データベースクラスタの構造 [!]
###### base
    データベース群
###### pg_log
    基本ログ
###### pg_stat
    統計情報の永続ファイルを保有するサブディレクトリ 
###### pg_stat_tmp
    統計情報の一時ファイルを保有するサブディレクトリ
###### pg_xlog(pg_wal)
    WALファイルを格納するファイル
###### global
    グローバルデータ
###### pg_multixact
    マルチトランザクション状態のデータ
###### pg_subtrans
    サブトランザクションの状態のデータ
###### postgresql.conf　
    基本設定ファイル
###### pg_clog(pg_xact)
    コミットログ
###### pg_notify
    通知送信用関数
###### pg_tblspc
    テーブル空間のシンボリックリンク
###### postmaster.opts　
    最後に起動したコマンドラインオプション
###### pg_hba.conf　
    アクセス設定ファイル
###### pg_serial
    コミットされたシリアライザブルトランザクションに関する情報
###### pg_twophase
    プリペアドトランザクション用の状態ファイル
###### postmaster.pid　
    実行中のPID
###### pg_ident.conf　
    クライアント認証方式でidentを利用するときに記述
###### pg_snapshots
    エキスポートされたスナップショット
###### PG_VERSION　
    バージョン番号

##### プロセス構造 [!]
###### Postmaster
    サービス起動時に待ち受けるプロセス
###### Postgres
    接続ごとに起動するプロセス
###### Autovacuum worker
    自動VACCUMを実行するプロセス
###### Autovacuum launcher
    不要領域を監視するプロセス
###### Stats collector
    統計情報を取集するプロセス
###### Logger
    ログをファイルに書き出すプロセス
* postgresql.confのlogging_collectorパラメータが無効だとloggerプロセスは起動しません。
###### Writer
    Shared bufferに書き出すプロセス(ダーティバッファをディスク書出)
###### Wal writer
    WAL書き込みを行うプロセス(トランザクションログ書出)
###### checkpointer
    checkpoint処理を行うプロセス
###### Archiver
    WAL・トランザクションログをアーカイブするプロセス
###### Wal sender
    WALをスタンバイサーバへ転送するプロセス(マスタ側に存在)
###### Wal receiver
    WALをマスターサーバへ受信するプロセス
###### parallel worker
    パラレルクエリを実施するプロセス

##### データの格納方法
#### 重要な用語、コマンド、パラメータなど：
##### autovacuum [●]
以下の計算値以上のレコード更新があった場合、自動的に実行される
```
    autovacuum_vacuum_threshold + autovacuum_vacuum_scale_factor * レコード数 
```
##### TOAST
    一部のデータ型のみがサポートしており、可変長データ型利用時、別の隠しテーブルに可変長のデータ格納PLAINは圧縮や行外の格納を防止します。 さらにvarlena型での単一バイトヘッダの使用を無効にします。 これはTOAST化不可能のデータ型の列に対してのみ取り得る戦略です。EXTENDEDでは、圧縮と行外の格納を許します。 これはほとんどのTOAST可能のデータ型のデフォルトです。 圧縮がまず行われ、それでも行が大き過ぎるのであれば行外に格納します。EXTERNALは非圧縮の行外格納を許します。 EXTERNALを使用すると、textとbytea列全体に対する部分文字列操作が高速化されます。 こうした操作は非圧縮の行外の値から必要な部分を取り出す時に最適化されるためです （格納領域が増加するという欠点があります）。MAINは圧縮を許しますが、行外の格納はできません （実際にはこうした列についても行外の格納は行われます。 しかし、他に行を縮小させページに合わせる方法がない場合の最後の手段としてのみです）。

##### FILLFACTOR

##### アーカイブログ

##### ページヘッダ
    24バイト
| フィールド        | 型     | バイト長        | 説明 |
|:-----------------|-----|---------------:|:---------:|
| pd_lsn | PageXLogRecPtr | 8 バイト | いわゆるLSN(Log Sequence Number)を記録するフィールド。
このページに対する更新内容を XLogInsert(rmid, info, rdata) を使い WAL レコードとして書き出した後に、PageSetLSN(page, lsn) を呼び出して記録する。このフィールドはチェックポインティング処理で参照される。|
| pd_checksum | uint16 | 2 バイト | このページのチェックサムを記録する。|
| pd_flags | uint16 | 2 バイト | フラグビット。 | 
| pd_lower | LocationIndex | 2 バイト | 空き領域の始まりに対するオフセット。 | 
| pd_upper | LocationIndex | 2 バイト | 空き領域の終わりに対するオフセット。 | 
| pd_special | LocationIndex 2 バイト | 特別な空間の始まりに対するオフセット。 | 
| pd_pagesize_version | uint16 | 2 バイト | ページサイズおよびレイアウトのバージョン番号の情報。 | 
| pd_prune_xid | TransactionId | 4 バイト | ページ上でもっとも古い切り詰められていないXMAX。存在しなければゼロ。 | 

##### タプルヘッダ
| フィールド  | 型              | バイト長 | 説明 |
|:-----------|-----------------|---------:|:---------:|
| t_xmin     | TransactionId   | 4バイト  | 挿入XIDスタンプ | 
| t_cmin     | CommandId       | 4バイト  | 挿入CIDスタンプ | 
| t_xmax     | TransactionId   | 4バイト  | 削除XIDスタンプ | 
| t_cmax     | CommandId       | 4バイト  | 削除CIDスタンプ（t_xvacと共有） | 
| t_xvac     | TransactionId   | 4バイト  | 行バージョンを移すVACUUM操作用XID | 
| t_ctid     | ItemPointerData | 6バイト  | この行または最新バージョンの行の現在のTID | 
| t_natts    | int16           | 2バイト  | 属性の数 | 
| t_infomask | uint16          | 2バイト  | 様々なフラグビット | 
| t_hoff     | uint8           | 1バイト  | ユーザデータに対するオフセット | 

##### postmasterプロセス [●]
    PostgreSQLの親プロセス。接続を待ち受ける。
    サービス起動時にデータベースクラスタに対して、postmasterが1つ動作して、postgres・wal writer・checkpointerなどのプロセスが起動します。
##### postgresプロセス
    1接続につき1つのpostgresプロセスが起動します。
##### バックグラウンドプロセス
    PostgreSQLはユーザ提供のコードを別のプロセスとして実行できるように拡張することができます。
    このプロセスはpostgresによって起動、終了、監視され、サーバの状態に密接にリンクした寿命を持つことができます。
    これらのプロセスはPostgreSQLの共有メモリ領域にアタッチしたり、データベースの内部に接続するオプションを持ちます。
    これらはまた、通常のクライアントに接続された実際のサーバプロセスのように複数のトランザクションを連続して実行することができます。
    また、アプリケーションはlibpqとリンクすることにより通常のクライアントアプリケーションのようにサーバに接続して動作することができます。
##### SQL実行のキャンセル

##### シグナル(TERM/INT/HUP)によるサーバプロセスへの影響

##### checkpointer [●]
    チェックポイント処理を行うプロセス


### ホット・スタンバイ運用 【重要度：1】
    レプリケーション構成を組むための設定や構築手順、およびレプリケーションの仕組み(プロセスやフロー)、状態の監視などに関する知識を問う
#### 主要な知識範囲：
##### 【変更】ストリーミングレプリケーション機能とロジカルレプリケーション機能の概要 [!]
    ストリーミングレプリケーションを行うための最低限の設定を示します。
    なお、外部からの接続を受け付けるための設定(listen_addressesなど)は割愛しています。
* プライマリサーバでの設定
    + postgresql.confのmax_wal_sendersに十分大きな値を設定
    + postgresql.confのwal_levelをarchiveに設定
    + postgresql.confのarchive_modeをonに設定
    + postgresql.confのarchive_commandでWALのアーカイブ先を設定
    + pg_hba.confに、データベースフィールドを"replication"と指定した項目を設定
* スタンバイサーバでの設定
    + recovery.confのstandby_modeをonに設定
    + recovery.confのprimary_conninfoにプライマリサーバへの接続情報(libpq接続文字列)を設定
    + recovery.confのrestore_commandでアーカイブWALの取得元を設定
##### ホットスタンバイのための設定
    上記ストリーミングレプリケーションの設定を以下のように修正・追加し、ストリーミングレプリケーションでホットスタンバイを行えます。
* プライマリサーバでの設定
    + postgresql.confのwal_levelをhot_standbyに設定
* スタンバイサーバでの設定
    + postgresql.confのhot_standbyをonに設定
##### 【変更】同期レプリケーションと非同期レプリケーション
    同期方式と非同期方式があり、同期方式ではスタンバイ側が停止するとレプリケーションが停止し、復旧するまで更新処理も行えなくなります。また、同期・非同期に関わらず、レプリケーション停止してもマスタサーバ及びスタンバイサーバでの参照系クエリは実行可能です。
##### postgresql.conf、recovery.confの設定
    スレーブ側でrecovery.confのtrigger_fileパラメータで設定したトリガファイルを作成
##### 【追加】パブリケーションとサブスクリプションの定義

#### 重要な用語、コマンド、パラメータなど：
##### 【追加】wal_level
    マスタ側のpostgresql.conf設定：スタンバイでもselect等の参照可能に設定します。（hot_standby）
##### 【追加】max_wal_senders
    マスタ側のpostgresql.conf設定：スタンバイDBの数 + 1（2）
##### 【追加】wal_sender_timeout
    postgresql.conf：レプリケーション接続のタイムアウトを設定します
##### 【追加】wal_receiver_timeout
    postgresql.conf：レプリケーション接続のタイムアウトを設定します。
##### 【追加】synchronous_standby_names
    postgresql.conf：同期レプリケーション時のスタンバイ側の名称を設定します。
##### 【追加】synchronous_commit
    postgresql.conf：同期方式を設定します。
##### 【追加】max_logical_replication_workers

##### 【追加】CREATE/ALTER/DROP PUBLICATION/SUBSCRIPTION

##### 【追加】pg_stat_replication
    レプリケーションの詳細情報を確認できます
##### 【追加】pg_stat_wal_receiver
    １行の形式で、受信サーバが接続したサーバからWALレシーバに関する統計情報を表示します。
##### recovery_min_apply_delay
    誤操作防止などの理由で、レプリケーションを遅延させたい場合、recovery.confにrecovery_min_apply_delayを設定すると遅延できます
##### 【追加】スタンバイでの問い合わせのコンフリクト(衝突)

##### 【追加】hot_standby_feedback
    postgresql.conf：スタンバイ上で現在処理を行っている問い合わせについて、フィードバックするか設定します。
##### max_standby_streaming_delay
    スレーブ側のpostgresql.conf設定：WALエントリと衝突するスタンバイサーバの問い合わせをキャンセルするにはどれだけ待機しなければならないかを設定します。（30s）
##### pg_wal_replay_pause()

##### pg_wal_replay_resume()

##### 【変更】wal sender プロセス [●]

##### 【変更】wal receiver プロセス [●]

##### 【変更】pg_receivewal

##### トランザクションログ(WAL)

##### スタンバイへ伝搬される処理とされない処理

##### 【追加】スタンバイで実行可能な問い合わせ

##### 【追加】ロジカルレプリケーションのサブスクライバ―へ伝搬される処理とされない処理


## 性能監視（30％）
### アクセス統計情報 【重要度：3】 
    データベースの利用状況を示す稼働統計情報の内容や見方、収集方法に関する知識を問う
#### 主要な知識範囲：
##### リセットコマンド
###### pg_stat_reset()
    現在のデータベースに関する統計カウンタすべてをゼロにリセットします。（スーパーユーザ権限必要）
###### pg_stat_reset_shared(text)
    クラスタ全体の統計情報カウンタの一部をゼロに戻します。
###### pg_stat_reset_shared('bgwriter')
    pg_stat_bgwriterビューで示される値すべてがゼロになります。
###### pg_stat_reset_shared('archiver')
    pg_stat_archiverビューで示される値すべてがゼロになります。
###### pg_stat_reset_single_table_counters(oid)
    データベース内のテーブルあるいはインデックスの統計情報をゼロにリセットします。（スーパーユーザ権限必要）
###### pg_stat_reset_single_function_counters(oid) 
    データベース内の関数の統計情報をゼロにリセットします。（スーパーユーザ権限必要）

##### pg_locks
    ロック待ちとなっているトランザクションや対象のテーブルを確認する
* ロック対象となるオブジェクト（locktype列）
    + [relation]、 extend、 page、 [tuple]、 transactionid、 virtualxid、 object、userlock、 advisory
##### pg_stat_activity [!]
    サーバプロセス毎にプロセスの活動に関する情報を表示する
* query_startカラム：現在の問い合わせの実行開始時刻
* xact_startカラム：トランザクションの開始時刻
##### pg_stat_database [!]
    データベース毎あたり1行の形式でデータベース全体の情報を表示する
* blks_read：ディスクから読み込んだブロック数が格納されます
* 稼働統計情報を収集するにはtrack_countsパラメータがonである必要がある（デフォルトはon）
* tup_fetched：読み取られた行数
##### pg_stat_all_tables 等、行レベル統計情報 [!]
###### pg_stat_all_tables
    現在のデータベースの各テーブルごとに1行の形で、テーブルへのアクセス統計情報を表示する
* blks_readカラム：ディスクから読み込んだブロック数が格納される
##### pg_statio_all_tables 等、ブロックレベル統計情報 [!]
###### pg_statio_all_tables
    現在のデータベース内のテーブルごとに１行の形で、特定のテーブルに対するI/Oに関する統計情報を示します。
* toast_blks_readカラム：TOASTテーブルから読み取られたディスクブロック数
* heap_blks_hitカラム：対象テーブルのバッファヒット数

#### 重要な用語、コマンド、パラメータなど：
##### pg_stat_archiver
    WALアーカイバプロセスの活動状況に関する統計情報を１行のみで表示します 
##### pg_stat_bgwriter [●]
    バックグラウンドライタに関する情報(buffers_backend、buffers_clean)を表示する
##### 【追加】待機イベント(pg_stat_activity.wait_event)

##### 【追加】pg_stat_progress_vacuum
    VACUUMを実行している（自動バキュームワーカプロセスを含んだ）それぞれのバックエンドごとに１行の形で、現在の進捗を示します

### テーブル / カラム統計情報 【重要度：2】
    プランナが利用するテーブル・カラムの統計情報についての理解を問う
#### 主要な知識範囲：
##### pg_class [!]
    システムカタログで、名称・所有者・テーブル空間といった多くの列を保有している
* relpages列にはテーブル内のページ数が格納されている
* reltuples列にはテーブル内の行数が格納されている
* 格納されている統計情報は推測値であり、VACUUMやANALYZEおよびCREATE INDEXなどにより更新される
##### pg_stats
    システムカタログであるpg_statisticの情報にアクセスするためのビュー
##### テーブル・インデックスの実ファイルとパス
* テーブルファイル：テーブルごとの実データを管理する
* インデックスファイル：インデックスの情報を管理する
* 8192バイトの「ページ」単位で構成され最大1Gバイト
    + 1Gバイトを超えると「ファイルノード番号.連番」の命名規則に則って分割管理される
* ライタプロセスやチェックポインタによって共有バッファのデータが書き込まれる
##### 実行計画時に利用される統計情報やパラメータ

#### 重要な用語、コマンド、パラメータなど：
##### pg_attribute
    テーブルの列情報
##### pg_statistic
    カラムに関する統計情報を扱う
* 実データの一部が格納されることになるため、一般ユーザは参照できない
##### pg_stats
    pg_statisticのかわりに一般ユーザが参照しても問題ない範囲に限定したビュー
##### null_frac
    NULLとなっている列項目の割合
##### n_distinct
    ゼロより大きい値は列内の個別値の推定数
##### most_common_freqs
    最も一般的な値の出現頻度のリストで、つまり行の総数で出現数を割算した数字
##### histogram_bounds
    列の値を満遍なく似たような数でグループに分配した値のリスト
##### correlation
    物理的な[訳注：ディスク上の]行の並び順と論理的な列の値の並び順に関する統計的相関
##### default_statistics_target
    default_statistics_targetの値を大きくすると、ANALYZEの所要時間は長くなり、プランナの予測の品質は向上します。
##### effective_cache_size
    プランナが単一の問合せで利用するOSのディスクキャッシュ容量に対する参考値を設定します。
##### track_counts(boolean)
    データベースの活動についての統計情報の収集を有効にします。
    offの場合、analyzeによる統計情報は更新されない。 収集される情報を自動バキュームデーモンが必要とします。
##### track_activities(boolean)
    各セッションで実行中のコマンドに関する情報とそのコマンドの実行開始時刻の収集を有効にします。
##### stats_temp_directory(string)
    統計情報データを一時的に格納するディレクトリを設定します。
    これをデータディレクトリからの相対パスとすることも絶対パスとすることもできます。 
    一時ファイルの格納場所としてRPMベースのファイルシステムを指定することで物理IOの要求が減らせます。
##### pg_settings
    サーバの実行時パラメータへのアクセスを提供します。

### クエリ実行計画 【重要度：3】
    EXPLAINが出力する実行計画を読み取り、チューニングを行う。
#### 主要な知識範囲：
##### EXPLAIN / EXPLAIN ANALYZE 出力 [!]
    ANALYZE オプションを付けて実行すると、SQLは実際に実行される。
* 出力フォーマット
    + TEXT（デフォルト）
    + XML
    + JSON
    + YAML
* SQLコマンド
    + SELECT、INSERT、UPDATE、DELETE、VALUES、EXECUTE、DECLARE、CREATE TABLE AS、CREATE MATERIARIZED VIEW、REFRESH MATERIALIZED VIEW
* cost：処理を行う際の推定の初期コスト、全体コスト（時間単位）
    + rows：それぞれの計画ノードを実行した際の推定の処理行数
* actual time：問い合わせ実行時の実測値（ミリ秒）
    + rows：問い合わせ実行時の処理行数
* width：統計情報を基に推測される１行辺りの平均のバイトサイズ
* Total runtime：結果行を操作するための時間の他に、エクゼキュータの起動、停止時間も含まれています
##### 計画型

##### EXPLAINからのチューニング

##### 結合の種類(Nested Loop、Hash、Merge)と性能特性 [!]

##### SQL構文(JOIN/GROUP BY/ORDER BY/LIMIT)に対応する実行計画 [!]

##### 集約関数(sum/count)を伴うSQLに対応する実行計画

##### 【追加】パーティションに対するSQLの実行計画

##### 【追加】パラレルクエリに対応する実行計画

##### 【追加】ウィンドウ関数(row_number/rankなど)のSQLに対応する実行計画

#### 重要な用語、コマンド、パラメータなど：
##### 【追加】EXPLAIN / EXPLAIN ANALYZE
 

### その他の性能監視 【重要度：1】
    性能監視に関するその他の手法
#### 主要な知識範囲：
##### スロークエリの検出 [!]
    長時間発生したクエリのこと
##### 付属ツールによる解析
    pg_stat_statements、pgbench、auto_explainを利用して性能の解析が行えます
##### 性能劣化要因(リソース枯渇、ロック競合)
1. メモリ不足によるディスク利用による性能低下
2. データ量増加による処理遅延
    + 大量のINSERTを発行するとWALファイルへの書込で競合が発生することによる影響
3. ロック競合による処理遅延
4. チェックポイント多発による性能低下
5. 不要領域が増加による性能低下
6. ディスク領域枯渇による性能低下
7. postgresql.confの誤った設定による性能低下
    + shared_buffersの値を大きくすると、チェックポイント中のデータ増大による影響
    + maintenance_work_memの値を大きくしすぎてVACUUMプロセスが多重実行によるメモリ消費

#### 重要な用語、コマンド、パラメータなど：
##### shared_preload_libraries
    postgresql.confのパラメータ
```
shared_preload_libraries = 'pg_stat_statements'
```
##### auto_explain
    スロークエリの実行計画を自動的にログに書き出します。
    スロークエリだけではクエリ文だったのに対してauto_explainでは実行計画を書き出します。
    その時の実行計画を得ることにより、vaccumの周期・設定のメモリ不足(ソート時にメモリが利用されていないことにより)などが判断できます。
##### auto_explain.*
    postgresql.confのパラメータ
```
    shared_preload_libraries = 'auto_explain'
    auto_explain.log_min_duration = 200
    #基本はスロークエリのlog_min_durationと同じ設定
```
##### log_min_duration_statement
    SQL文の実行に指定した時間以上かかった場合、それぞれのSQL文の実行に要した時間を記録する
* 整数値を設定し、指定したミリ秒以上を要したSQL文と実行時間を出力する
* 0に設定すれば、すべてのSQL文について出力される [●]
* -1に設定すると、出力しない
* インデックスを張るなどの対策を検討する
##### pg_stat_statements
    実行された全てのSQL文の実行時の統計情報を記録する
* スロークエリの解析に利用
##### 【追加】log_autovacuum_min_duration
    postgresql.conf：ログに記録する実行時の最小値を設定します。
##### 【追加】log_lock_waits
    postgresql.conf：deadlock_timeoutよりも時間がかかった場合にログに記録するか設定します。
##### 【追加】log_checkpoints
    postgresql.conf：チェックポイントまたはリスタートポイントをログに記録するか設定します。
##### 【追加】log_temp_files
    一時ファイルでメモリを利用しない場合、log_temp_filesの設定を大きくすることでメモリを利用して性能が向上することが考えられます。

## パフォーマンスチューニング（20％）
### 性能に関係するパラメータ 【重要度：4】 
    データベースの設定パラメータで、特にパフォーマンスに影響を与えるもの、パフォーマンスチューニングの参考になるものに関する理解を問う
#### 主要な知識範囲：
##### 資源の消費 (RESOURCE USAGE)
###### ディスクフル
    ログが溜まりすぎるとディスクフルとなるので、定期的に削除するような運用をおこなう。
###### サーバーへの接続数の超過
    max_connections - superuser_reserved_connections　を超過すると、エラーメッセージが表示される。
###### データベースに大量データを投入する際の時間短縮手段
    一般的には、一時的に設定値を変更したり、主に制約になるような設定を解除したりして、性能を向上させます
* 自動コミットをオフにする
* インデックスや外部キー制約を削除する
* maintenance_work_memを増やす
* checkpoint_segmentsを増やす
##### ログ先行書き込み (WRITE AHEAD LOG)
    更新処理が遅い場合、WALの頻繁な書き込みがネックになっている可能性がある。wal_buffers パラメータを引き上げることでWAL書き込みの頻度を下げることができる。
##### 問い合わせ計画 (QUERY TUNING)
 
##### 実行時統計情報 (RUNTIME STATISTICS)
    パラメータ設定やANALYZEが適切に行われていないと、インデックスがあるのに検索が遅いといった現象となる。
##### ロック管理 (LOCK MANAGEMENT) [!]
    deadlock_timeout は、ロック待ちの状態になったときにデッドロックの検出処理を開始するまでの待ち時間を指定します。デフォルト値は 1s、つまり1秒です。
    あくまでも、この指定時間の経過後に検出処理を開始する、というだけですから、この場合に必ずしもデッドロックが発生しているとは限りません。
    値を小さくすると、デッドロックの検出は早くなりますが、実際にはデッドロックが発生していないのに検出処理が動くということも多くなります。
    値を大きくすると、この反対に、無駄なデッドロック検出処理の回数は減りますが、デッドロックが実際に発生したときに、それが検出されるまでに待たされる時間は長くなります。
    デッドロックの検出はそれ自体が CPU 負荷の高い処理なので、できる限り実行しないで済むようにすべきです。
    デッドロックが頻繁に発生するような環境では、deadlock_timeout を小さくすることで、デッドロックを早く解決できるかもしれませんが、なるべくデッドロックが発生しないようにアプリケーション側で工夫し、CPU 負荷の高いデッドロック検出処理が不必要に実行されないように deadlock_timeout を大きくする、というのが正しいやり方です。
##### 軽量ロックと重量ロック
    ロックには重量ロックと軽量ロックがあります。
    Postgresqlでのロックはテーブルのみです。
    自身のプロセスでのロックでは競合を起こしません。
    デッドロックが重量ロックに辺り、次のテーブルレベルロックモードがあります。
    軽量ロックは，内部的な共有管理リソースアクセスで使用されます。
    SHAREDとEXCLUSIVEのテーブルレベルロックモードがあり、対象リソースに対する処理が完了後開放されます。
    開発モードのパラメータ設定でログ出力可能です。

#### 重要な用語、コマンド、パラメータなど：
##### shared_buffers
    共有バッファのサイズを設定。推奨値はサーバ実メモリの25%
* shared_buffersの値を大きくすると、チェックポイント中にディスクに書き出されるデータが増大し、一時的に性能が低下する恐れがあります
##### wal_bufferes
    WALバッファのサイズを設定
* wal_buffersを数キロバイトの小さなデフォルトより増加させることは書き込みが激しいシステムで役に立ちます。 ベンチマークでは通常、多少大規模なシステムでは1MBまで増やすだけで十分であると提案します。 またWALセグメント全体（16MB、ここでは有用な上限）を割り当てる最近のサーバでメモリを提供することが合理的です。 wal_buffersの変更はデータベースの再起動が必要です。 
* PostgreSQL 9.1から、wal_buffersはデフォルトでshared_buffersの容量の1/32になり、また上限は16MB（shared_buffersが512MBの時に達する値）になりました。
##### 【追加】huge_pages
    huge pageを使うと、ページテーブルが小さくなり、メモリ管理に使用されるCPU時間が少なくなり、性能が向上します。Linuxのみサポートされており、メモリの大きな連続チャンクを使用するときにhuge pagesを使用すると、オーバーヘッドが減少します。
##### effective_cache_size [●]
* オペレーティングシステム自体と他のアプリケーションが使用するメモリを考慮した後に、OSおよびデータベース自体の内部でディスクキャッシュとして利用可能なメモリ量の推定値に設定されなければなりません
* この値はPostgreSQL問い合わせプランナが生成した計画の内いずれがメモリに合うかどうかを推定するためだけに使用されます。
* この設定が小さすぎると、インデックスの利用を想定している問い合わせを実行する時に、インデックスが使用されない可能性があります。 shared_buffersの設定はここでは考慮されません。効率的なcache_size_valueのみです。データベースに占有されるメモリを含めなければなりません。 
* effective_cache_sizeを全メモリの1/2に設定することが通常の保守的な設定です。 メモリの3/4はより積極的ですが、まだ合理的な値です。
##### work_mem [●]
    問い合わせ時のソートやハッシュデータ格納時に使用するメモリのサイズ
* 複雑なソート処理を多く実行し、かつ大量のメモリがあるのであれば、work_memパラメータを増やすことによりPostgreSQLはメモリ内で大規模なソートを行うことができるようになります。
##### 【追加】maintenance_work_mem
    Vacuum文やALTER TABLEなどのメンテナンス操作時に使用するメモリのサイズ
* maintenance_work_memを大きくするとVACUUMの性能が向上します
* VACUUMプロセスが多重実行されると多重数分のメモリが消費されることに注意
* 基本的にバキュームが始まる時にそのメモリを確保する必要がありますので、より有用な目的で使用できなくなります。 体験に基づくものですが、256MB程度で十分な大きさです。 
##### 【追加】autovacuum_work_mem
    自動VACUUMで使用するメモリ量
##### 【追加】wal_level
    postgresql.conf：どれだけの情報がWALに書かれるかを設定します。
##### fsync
    postgresql.conf：ディスクへの同期書き込みの有効無効を設定します。
##### synchronous_commit
    レプリケーション構成における同期レベルを制御する
###### remote_apply
    同期レベルが最も高い設定値です。この設定の場合、プライマリ機でのトランザクションのコミットを実行してから、コミット成功となるまでの流れは以下の通りです。
1. ユーザが、プライマリ機でコミットを実行する
2. プライマリ機が、WALをプライマリ機のディスクに保存する
3. プライマリ機が、WALをスタンバイ機に送信し、スタンバイ機がWALを受取る
4. スタンバイ機が、WALをオペレーションシステムのバッファキャッシュに保存する
5. スタンバイ機が、バッファキャッシュに保存されたWALをディスクに保存する
6. スタンバイ機が、WALの記述内容に従って、データベースを更新する（ここでSELECTクエリを実行すると更新された状態になる）。
7. プライマリ機が、スタンバイ機からの報告を受取る
8. プライマリ機が、コミットを成功と判定する
###### on
デフォルトの同期設定です。remote_applyと比べて、STEP 6. の完了を待たずに STEP 7. に進みます。この設定では、プライマリ機およびすべてのスタンバイ機がデータベース記憶装置の故障を被った場合を除いて、トランザクションが失われないことが保証されます。
###### remote_write
同期レベルが準同期の設定です。remote_applyと比べて、STEP 5., STEP 6. の完了を待たずに STEP 7. に進みます。
この設定の特徴として、プライマリ機のWAL書き込み処理の待ち時間が短縮されることにより、「on」よりも性能がやや向上します。また、スタンバイ機のPostgreSQLサーバがクラッシュしたとしても、データの保護を保証できます。ただし、スタンバイ機がOSレベルでクラッシュした場合は、システムのバッファが失われる可能性があるため、データ保護を保証できません。
###### local
非同期の設定です。remote_applyと比べて、STEP 4.〜 STEP 7.の完了を待たずに STEP 8. に進みます。この設定は、同期レプリケーション構成では望ましい設定ではありません。
###### off
完全非同期の設定です。remote_applyと比べて、STEP 2.〜 STEP 7. の完了を待たずに STEP 8. に進みます。
プライマリ機でのトランザクションのコミット時、WALレコードがプライマリ機およびスタンバイ機に書き込まれたかどうかを待たずにコミット成功とするため、性能が向上します。一方で、OSやPostgreSQLサーバのクラッシュ時にトランザクションが失われる可能性があります。
##### 【追加】checkpoint_timeout
    チェックポインタの動作周期
* 閾値に達すると、共有バッファの情報がデータファイルへ書き込まれる。
* 書き込み処理の間はI/O負荷が高くなり問い合わせ性能に影響を及ぼす。
* 適切な値を設定し書き込みの周期や上限を設定する。
##### 【追加】checkpoint_completion_target
* PostgreSQLはデータベースにおける新しいトランザクションをWALセグメントという名前の16MBサイズのファイルに書き出します。 checkpoint_segments個のファイルが書き出される度（デフォルトは3）に、チェックポイントが発生します。 チェックポイントはリソースを激しく消費することがあり得ます。 最近のシステムでは48MBごとにこれを行うと、性能上深刻なボトルネックとなります。 checkpoint_segmentsをより大きく設定することでこれを改善することができます。 非常に小規模な設定で実行していない限り、最低10に設定することで確実に改善されます。 これにより通常目標の完成度を増大させます。
##### deadlock_timeout
    deadlock_timeoutを大きくすることで検出を減らして(CPU負荷軽減)性能が向上することが考えられます。
##### buffers_backend
    新しいバッファを割り当てるためにバックエンドプロセスにより書き出されたdirtyバッファ数を表示する。
* 新しいバッファを割り当てようとして空きがない場合に、バックエンドプロセスが書き出しを行うことで増加
* pg_stat_bgwriterビューによって表示される
* buffers_backendの値がbuffers_allocに対して大きい場合は、shared_buffersの値のチューニングを検討する必要がある
##### buffers_checkpoint
    チェックポイントによる書き出しの際に増加
##### buffers_alloc
    割り当てられたバッファ数
##### buffers_clean
    バックグラウンドライタによる書き出しの際に増加
##### random_page_cost / seq_page_cost
    random_page_costの値をseq_page_costと比較して小さく設定すると、プランナはよりインデックススキャンを使用するようになります
##### full_page_writes
    full_page_writesがONの場合は、チェックポイント後に各ページに対して最初の更新処理が行われる際に、更新対象のページ全ての内容をWALに書き込むように動作します。
    OFFの場合は更新分のデータのみがWALに書き込まれるようになるため、その分応答性能が向上し、WALの書き込み量が低減します。
* OFFの場合、ページ書き込みが途中までしか終わっていない状態でシステムがクラッシュすると、回復不可能なデータ破損が発生する可能性があります
* OFFの場合であっても、ポイントインタイムリカバリに利用できるベースバックアップやWALを問題なく取得できます。ただし、pg_start_backupを実行してからpg_stop_backupを実行するまでの間は、一時的にfull_page_writes=on相当の挙動をとるため、データ更新時の応答性能劣化に注意が必要となります。


### チューニングの実施 【重要度：2】
    データベース、およびSQLのチューニングに関する理解を問う
#### 主要な知識範囲：
##### パラメータのチューニング [!]
* CPU
* メモリ
* 共有メモリ
* ディスク
##### 実行計画のチューニング [!]
* enable_seqscan をoffにする
    + Total runtimeが大きくなる可能性としては、本来はシーケンシャルスキャンを利用すべきクエリなのに、他の効率の悪い方式が利用されてしまうケースが考えられます
    + Total runtimeが小さくなる可能性としては、統計情報の精度が足りない等の理由で、本来はシーケンシャルスキャンを利用すべきではないのに選択されてしまっていたケースが考えられます。
    この場合、enable_seqscanをoffにすることで、他の効率の良い方式が利用されるようになる可能性があります。
    + シーケンシャルスキャンが絶対に必須のクエリの場合は、enable_seqscanがoffであっても、シーケンシャルスキャンが選択されることになります
    + 
    + そもそもenable_seqscanがonの状態でもシーケンシャルスキャンがもともと選択されていないクエリの場合は、enable_seqscanをoffにしても全く同一の実行計画が選択される可能性があります。
##### SQL のチューニング

##### 【追加】テーブル構成のチューニング

##### ディスクI/Oの分散 [!]
    テーブルスペース機能で、複数のディスクをりようさせることで、データ読み書きの性能が向上することが考えられます。
##### パラメータの反映方法(パラメータ有効化のために必要なアクション)
    問い合わせ等の処理全般が一時的に遅くなる原因として推測されるのは、チェックポイントまたはVACUUM処理との競合です。
* チェックポイントとの競合の場合は、チェックポイント処理を負荷分散させる対策が有効です。
* VACUUM処理との競合では、VACUUM関連のパラメータを調整しVACUUM処理の負荷分散を図ることが有効な対策となります。
##### インデックスがSQLの性能に与える影響
* CONCURRENTLYパラメータ
    + 指定された場合、対象テーブルに対する書き込みをロックせずにインデックスを作成するが、通常の方式より作成時間が長くなる
    + 同時挿入、更新、削除と競合するロックを獲得せずにインデックスを作成できる
* インデックスの定義で使用される関数と演算子は、immutableでなければならない
* 定期的にインデックスの再作成を行うことで、インデックスの肥大化を抑止できる

##### Index Only Scan と Visibility Map
    インデックスのみを利用して必要行必要行を検索します。
    Visibility Mapを参照します。
    Visibility Mapが更新されるときは、バキューム処理とcreate indexなどの一部のDDL実行時です。
    バキュームフル実行時は、Filenodeが変更されて、vmファイルがなくなることを確認しています。

#### 重要な用語、コマンド、パラメータなど：
##### Index Only Scan
##### enable_seqscan [●]

##### enable_indexscan [●]
    enable_indexscanを無効にすると、プランナはインデックススキャンを選択しないようになります


## 障害対応（20％）
### 起こりうる障害のパターン 【重要度：3】 
    データベースでのSQL実行タイムアウトやサーバダウン、動作不良、データ消失、OSリソース枯渇などの故障が発生した場合について、エラーメッセージの内容から原因を特定し、適切な対応ができるかを問う
#### 主要な知識範囲：
##### サーバダウン、動作不良、データ消失への対処 [!]
###### ERROR: invalid page header in block 0 of relation base/16408/16421
    該当のテーブルファイルのヘッダ情報が破損していることを示しています
* ヘッダ情報が破損している場合、該当のテーブルに対して全てのページをスキャンする必要のあるSQLコマンドを実行することができない
* zero_damaged_pages を on に設定して再度テーブルを参照することで、破損があると判断されるページを０埋めして動作を継続する。このとき当該のページに含まれるデータは消失する。
##### OS リソース枯渇 [!]
###### メモリ不足
    サーバを再起動する
    また、postgresql.confのメモリ設定を少なくして起動を試します
##### OSのパラメータ
###### FATAL: sorry, too many clients already
    スーパーユーザの場合に同時接続数がmax_connectionsに設定した値を超えた
###### FATAL: remaining connection slots are reserved for non-replication superuser connections
    一般ユーザの場合に同時接続数が（max_connections - superuser_reserved_connections）の値を超えた
##### サーバプロセスの状態(idle、idle in transaction、active)

##### シグナル(TERM/INT/HUP)によるサーバプロセスへの影響
    データベースサーバをシャットダウンする方法は複数あります。 
    マスターpostgresプロセスに異なるシグナルを送ることで、シャットダウンの方法を制御します。

##### サーバプロセスのクラッシュ(セグメンテーションフォルトなど)と影響範囲

#### 重要な用語、コマンド、パラメータなど：
##### 【追加】statement_timeout
    postgresql.conf：クライアントからサーバに届いたコマンドが停止されるまでのタイムアウトを設定します。
##### 【追加】lock_timeout
    postgresql.conf：ロック時のタイムアウトを設定します。
##### 【追加】idle_in_transaction_session_timeout
    postgresql.conf：開いたトランザクションが、指定された時間（単位はミリ秒）を超えてアイドルだった場合のタイムアウトを設定します。
##### 【追加】スタンバイでの問い合わせのコンフリクト(衝突)

##### 【追加】hot_standby_feedback
    postgresql.conf：スタンバイ上で現在処理を行っている問い合わせについて、フィードバックするか設定します。
##### vacuum_defer_cleanup_age
    postgresql.conf：VACUUM および HOT更新が不要行バージョンの回収を決めるのを延期するトランザクションの数を設定します。
##### max_standby_archive_delay
    postgresql.conf：スタンバイがアーカイブ処理しているときにクエリをキャンセルするまでの最大遅延間隔を設定します。
##### max_standby_streaming_delay
    postgresql.conf：スタンバイがストリームされた処理しているときにクエリをキャンセルするまでの最大遅延間隔を設定します。
##### fsync
    postgresql.conf：ディスクへの同期書き込みの有効無効を設定します。
##### 【追加】synchronous_commit
    postgresql.conf：同期方式を設定します。
##### 【追加】restart_after_crash
    postgresql.conf：PostgreSQLがバックエンドのクラッシュ時に自動的に再初期化するか設定します。
##### pg_cancel_backend()
    ユーザ要求によりクエリがキャンセルされる場合、発行される関数。(SIGINTと同等)
##### pg_terminate_backend()
    セッションを終了させます。(SIGTERMと同等)
##### pg_ctl kill

##### max_locks_per_transaction
    共有ロックテーブルは、max_locks_per_transaction * （max_connections + max_prepared_transactions）オブジェクト（例えばテーブル）上のロック追跡します。 したがって、ある時点でこの数以上の個々のオブジェクトをロックすることはできません。 このパラメータは各トランザクションで割り当てられるオブジェクトロックの平均値を制御します。 個々のトランザクションでは、このロックテーブルにすべてのトランザクションのロックが収まる限りオブジェクトのロックを獲得できます。 これは、ロックできる行数ではありません。この値には制限がありません。 デフォルトの64は、経験的に十分であると証明されていますが、単一のトランザクションで数多くの異なるテーブルをいじるクライアントがいる場合、この値を大きくする必要があるかも知れません。 このパラメータはサーバ起動時のみ設定されます。
##### max_files_per_process
    カーネルは個々のプロセスがシステムが実際にサポートできるファイル数より多くを開くことを許しています。 "Too many open files"エラーが発生した場合は小さく設定する必要があります。
##### SIGTERM
    スマートシャットダウンモードです。
    新しい接続を禁止しますが、既に存在するセッションは通常通り動作させます。 
    全てのセッションが通常に終了するまではシャットダウンしません。
    バックアップは待ちますので、正常に完了します。
    pg_ctlのモードはsmart
##### SIGINT
    高速シャットダウンモードです。 サーバは新しい接続を禁止し全ての存在するサーバプロセスにSIGTERMを送り、この結果サーバプロセスは現在のトランザクションをアボートし、即座に終了します。 そして サーバはサーバプロセスの終了を待って、最後にシャットダウンします。 オンラインバックアップモードも終了させる。
    pg_ctlのモードはfast
##### SIGQUIT
    即時シャットダウンです。 マスターpostgresプロセスは、全ての子プロセスに SIGQUITを送り、即座に終了します。
    子プロセスは同様にSIGQUITを受け取ると即座に終了します。
    次回起動時に（WALログを再実行することで）リカバリをすることになります。 
    pg_ctlのモードはimmadiate
##### SIGSEGV
    ユーザ定義関数等で誤ったメモリ操作を行いセグメンテーション違反が発生した際にログ出力される


### 破損クラスタ復旧 【重要度：2】
    データファイルやトランザクションログファイルが破損した場合について、エラーメッセージの内容から原因を特定し、適切な対応ができるかを問う
#### 主要な知識範囲：
##### 【追加】トランザクションログ復旧 [!]
    データベースクラスタの内容が壊れている場合は、pg_restxlogを実行します
##### システムテーブルのインデックス復旧 [!]
    システムカタログのインデックスが破損している場合、サーバプロセスが起動時に強制終了する可能性があります。
##### 開発者向けオプション

##### テーブル・インデックスの実ファイルとパス

##### Relfilenode と OID

##### インデックス破損とREINDEXによる復旧
###### REINDEX SYSTEM
    共有システムカタログも含めたシステムカタログに対する全てのインデックスが再作成されます。
##### チェックサムによる破損検知と復旧
    読み込み過程でチェックサム障害が検出されると、通常PostgreSQLはエラーを報告し、現時点のトランザクションを停止します。
    開発者向けオプションとして、ignore_checksum_failureを有効にするとエラーを無視します。
##### トランザクションIDの周回エラー

#### 重要な用語、コマンド、パラメータなど：
##### 【追加】PITR
* 任意のリストアポイント(特定の文字列で作成される)まで
* 任意のトランザクションIDまで
* 最後のWALログ位置まで
* 任意の時刻まで
##### pg_resetwal
* PostgreSQLを停止して実行する（管理者のみ実行可能）
* -x オプション
    + トランザクションIDを指定する場合は、pg_clogディレクトリ内のファイル名で最も大きな数字に1を加えて、1048576で乗算した値を用いる
* pg_resetxlog
    + データベースクラスタのトランザクションログやその他の制御情報を初期化します。
##### ignore_system_indexes
    GUCパラメータのignore_system_indexesをONにすると、システムカタログの読み込み時にインデックスが読み込まれないようになります。このパラメータはinitdb時に作成されるpostgresql.confには記載されていないため、新たに追記する必要があります。
##### ignore_checksum_failure

##### コミットログ(pg_xact)

##### シングルユーザモード

##### 【追加】VACUUM FREEZE


### ホット・スタンバイ復旧 【重要度：1】
    レプリケーション構成でプライマリ側やスタンバイ側のPostgreSQLが停止・故障した場合について、適切な対応ができるかを問う
#### 主要な知識範囲：
##### ストリーミングレプリケーションとロジカルレプリケーション
* ストリーミングレプリケーション：マスタースレーブ構成において、プライマリの更新内容ごとに（WALレコードごとに）スタンバイへと送る機能
    + スタンバイでは送られてきたWALを実行することで、プライマリと同じ状態を保つことができる。
	+ 実際にはプライマリ側のwalsenderプロセスと、スタンバイ側のwalreceiverプロセスでやりとりを行う
##### ログファイル内のエラーメッセージ
###### LOG: checkpoints are occurring too frequently
    本エラーが多発している場合、チェックポイントがmax_wal_sizeのチューニングが必要です。
###### LOG: archive command failed with exit code 1
    archiveコマンドが失敗しているため、ディスク容量の確認またはコマンドの確認または権限の確認が必要です。
###### LOG: number of page slots needed (12345) exceeds max_fsm_pages (20000)
    max_fsm_pagesが不足しているため、チューニングが必要です。
###### LOG: server process (PID 12345) was terminated by signal 9: Killed
	Out of Memory KillerによりSIGKILLが発生しました。
###### LOG: server process (PID 12345) was terminated by signal 11: Segmentation fault
	該当のPIDに対して、ユーザ定義関数がに誤りがあるため問題が発生しました。
###### LOG: redirecting log output to logging collector process
	ログを出力しました。
###### LOG: database system is ready to accept connections
	データベースが接続できるようになりました。
###### LOG: standby "db2" is now a synchronous standby with priority 1
	優先順位1で、同期スタンバイになりました。
###### LOG: database system was interrupted; last known up at 2019-02-03 08:40:51.794 JST
	2019-02-03 08:40:51.794以降にデータベースシステムが中断しました。
###### FATAL: sorry, too many clients already
	すべてのユーザで接続数を超過しましたので、ユーザ数のチューニングが必要です。
###### FATAL: remaining connection slots are reserved for non-replication superuser connections
	スーパーユーザ以外のユーザで接続数を超過しましたので、max_connectionsのチューニングが必要です。
###### FATAL: connection limit exceeded for non-superusers
	スーパーユーザ以外のユーザで接続数を超過しましたので、max_connectionsのチューニングが必要です。
###### FATAL: incorrect checksum in control file
	32bitと64bitなどOS違いなどで起動した可能性があります。データの再移設を検討する必要があります。
    pg_controlの異常のため、pg_resetxlogで修復できる可能性があります。
###### FATAL: terminating connection due to administrator
	pg_terminate_backend関数が発行されました。
###### FATAL: could not open lock file "1234": Permission denied
	ファイルへのアクセス権限がありません。対象のファイルにアクセス権を与えます。
###### FATAL: could not open file "aaa": Too many open files in system
	OSで開けるファイルをオーバーしています。max_files_per_processのチューニングが必要です。
###### FATAL: lock file "postmaster.pid" already exists
	サーバが起動中または、前回の停止時にpostmaster.pidが残ってます。停止中の場合、postmaster.pid削除してから再起動してください。
###### FATAL: terminating connection due to conflict with recovery
    リカバリーとの競合でキャンセイルしているため、キャンセルいないようにvacuum_defer_cleanup_age・max_standby_streaming_delay・hot_standby_feedbackを設定します。
###### FATAL: could not map anonymous shared memory: Cannot allocate memory
	カーネルで取得できるshared memoryの量が不足しています。
###### ERROR: canceling statement due to user request
	ユーザの要求で、クエリがキャンセル(pg_cancel_backend)されました。
###### ERROR: invalid page header in block 0 of relation base/12345/23456
	base/12345/23456のテーブルが破損しています。zero_damaged_pagesをonにに設定することでテーブルが参照できる可能性がございます。
###### ERROR: out of shared memory
	ロックのための共有メモリの不足しています。max_locks_per_transactionのチューニングが必要です。
###### ERROR: canceling statement due to conflict with recovery
    リカバリーとの競合でキャンセイルしているため、キャンセルいないようにmax_standby_streaming_delay・hot_standby_feedbackを設定します。
###### PANIC: could not locate a valid checkpoint recor
	WALファイルが破損しています。pg_resetxlogで修復する必要があります。
###### PANIC: could not access status of transaction 12345
	管理用ファイルが破損している可能性が高いです。OSのDDコマンドなどでの修復する必要があります。

##### スタンバイへ伝搬される処理とされない処理
* レプリケーションの方式が同期か非同期かにかかわらず、通信が遮断中でも、マスタおよびスタンバイサーバのいずれでも、参照系クエリは実行可能
* 同期レプリケーションの場合は、更新系クエリの内容がスタンバイサーバに反映されるまで待機させられることになります
* 非同期レプリケーションの場合は、更新系のクエリであっても待機せずにマスタサーバで実行可能
##### プライマリ側PostgreSQLの停止・故障と再開(再起動)の方法
* 通信が遮断してから大量の更新がマスタサーバ側で行われ、その後に通信が復旧した場合、再同期処理に必要なWALが既にアーカイブ化されている可能性があります。このような場合は再同期処理にアーカイブWALが必要となりますが、更新量が少なく、アーカイブ化されていないWALのみで再同期処理が完了する場合は、必ずしもアーカイブWALは必須とはなりません。
##### スタンバイ側PostgreSQLの停止・故障と再開(再起動)の方法
##### 【追加】ロジカルレプリケーションのサブスクライバ―へ伝搬される処理とされない処理
    対象：DMLのINSERT/UPDATE/DELETE、ただし、UPDATE/DELETEはREPLACA IDENTITYを事前に設定する必要がある
    対象外：DDL、シーケンス、TRUNCATE
##### 【追加】ロジカルレプリケーションのサブスクライバ―でのコンフリクト
    PostgreSQLはSELECTでもロックを取ります。 なのでSELECT中にプライマリ側で対象行に更新があるとロック競合してWALの反映が待たされます。 するとWALがいつまで経っても反映されないのでmax_standby_streaming_delayの時間（Default 30秒）が過ぎてWALの更新が待たされてる場合にクエリが殺されます
#### 重要な用語、コマンド、パラメータなど：
##### pg_ctl promote
    指定したデータディレクトリで稼動中のスタンバイサーバにリカバリを終了し読み書き操作を始めるようコマンドを送ります。
##### 【変更】pg_receivewal

##### 【追加】pg_rewind

##### REPLACA IDENTITY
* DEFAULT：主キー
* USING INDEX：指定したインデックス
* FULL：行全体
* NOTHING：キー指定なし


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
##### IPv6の無効化
#### 関数
##### generate_series
#### contrib 
    contrib モジュール (追加で提供されるモジュール) を紹介します。
##### oid2name [●]
* [詳細](http://www.postgresql.jp/document/10/html/oid2name.html)
* -d <データベース名>：対象のデータベースクラスタ内に存在するすべてのデータベースのOIDを取得
* -i -d <データベース名>：対象のデータベースに含まれるインデックス、シーケンスのファイルノード番号も取得
* -s：対象のデータベースクラスタに作成されているテーブル空間のOIDを取得
* -H <ホスト情報> -p <ポート番号>：
##### dblink
    他の PostgreSQL データベースを SQL から直接操作できるモジュールである "dblink" の使い方を紹介します。dblink を使うと、分散環境で複数のデータベースをまたがる処理を行ったり、同じサーバ内の別のデータベースを操作することができます。
##### pgbench
    pgbenchはPostgreSQLに同梱されているシンプルなベンチマークツールです。 pgbenchを利用することにより、自分の使っているPostgreSQLの性能を数値で把握することができるようになり、チューニングの結果を確認したり、ハードウェアをアップグレードしたときの効果を客観的に見ることが可能です。
##### pgcrypto [●]
    contribモジュールのpgcryptoを使うとデータベース内のデータを暗号化できます。特定のカラムごとに暗号化でき、ディスクの盗難だけでなく、データベースにログインされてしまった場合にも機密データを守ることができます。
##### pg_upgrade [●]
    PostgreSQLのアップグレードを容易に実施可能とするサポートツール「pg_upgrade」がPostgreSQL9.0のcontribモジュールとして開発されました。どのようにアップグレードをサポートしてくれるのかを紹介します。
##### file_fdw  
    file_fdwは、PostgreSQL 9.1のSQL/MED機能を利用し、外部のタブ区切りまたはCSVファイルを直接テーブルの形で参照するためのモジュールです。COPYコマンドに似ていますが、データの複製を避けたり、加工しながら取り込む場合に便利です。
##### passwordcheck 
    passwordcheckは、PostgreSQLのユーザやロールに指定するパスワードに対して検査を行い、弱い(推測されやすい)文字列を弾く仕組みを提供するcontribモジュールです。本記事では、passwordcheckモジュールの概要と使い方、およびその拡張について解説します。
