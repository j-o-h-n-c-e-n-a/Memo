# 参照
* [サンプル問題](https://oss-db.jp/sample)
* [OSS-DB入門](https://oss-db.jp/dojo#dojo_nyumon)
* [オススメ！OSS-DB情報](https://oss-db.jp/dojo#dojo_column)

# OSS-DB Silver問題
## １．概要 
### Q．スマートシャットダウン(pg_ctl stop -m smart)の動作について正しい記述はどれか。選択せよ。
1. 既に接続されている接続が全て切断されるのを待った後、正常終了する。
2. 既に接続されている接続が全て切断されるのを待つが、実行中のトランザクションは全てロールバックされる。
3. 既に接続されている接続を強制的に切断し、実行中のトランザクションは全てロールバックされる。 
4. クリーンアップ処理を行なわずに緊急停止する(PostgreSQLがクラッシュしたのと同じ状態になる)。 
<details><summary>詳細 [××●]</summary><div>

* スマートシャットダウンは既存の接続が全て切断されるのを待ってから正常終了をします。
* ちなみに、3は高速シャットダウン(pg_ctl stop -m fast)、4は即時シャットダウン(pg_ctl stop -m immediate)の動作になります。 
</div></details>

### Q．createdb、dropdbコマンドについて適切な記述はどれか。選択せよ。
1. createdbコマンドでデータベースを作成するとき、「-O」オプションで所有者を指定した場合は、その所有者がスーパーユーザー権限やデータベース作成権限を持っていなくても、作成したデータベースの削除が可能となる。
2. createdbコマンドに-Tオプションをつけるとテンプレートデータベースの指定が出来る。指定がないとtemplate0がテンプレートデータベースとなる。
3. dropdbコマンドはデフォルトでデータベースを削除してよいかの確認を削除前に取るようになっている。
4. dropdbコマンドを実行出来るのは、データベースのスーパーユーザーまたはデータベース作成権限を持っているユーザーのみである。
<details><summary>詳細 [×●×]</summary><div>

* 2については、createdbコマンドに-Tオプションの指定がないとtemplate1がテンプレートデータベースとなります。
* 3については、データベースを削除していいかを確認するにはdropuserと同様に-iオプションが必要です。
* 4については、dropdbコマンドを実行出来るのは、データベースのスーパーユーザーまたはデータベースの所有者のみです。 
</div></details>

### Q．psqlについて正しい記述はどれか。選択せよ。
1. psqlでデータベースに接続する際のデフォルトのユーザー名、データベース名はpostgresである。
2. psqlのメタコマンドの\dSは、シーケンス一覧を表示する。
3. psqlの-Dオプションでデータベースを指定して接続、-Uオプションで接続するユーザー名を指定することが出来る。
4. psqlではSQLコマンドの終わりをセミコロンで判断するが、メタコマンドは改行で終わりを判断する。
<details><summary>詳細 [×●×]</summary>
psqlではSQLコマンドの終わりをセミコロンで判断する為、SQLコマンドは1行が長い場合改行で分けて記述が出来ますが、メタコマンドは必ず1行で入力する必要があります。
</details>

### Q．log_destinationの設定で誤っているものはどれか。選択せよ。
1. syslog
2. stderr
3. syslog, stderr
4. csvlog
5. file
<details><summary>詳細 [××●]</summary><div>

* log_destinationは、サーバログの出力先を設定します。
* 出力先は
	+ stderr
	+ csvlog
	+ syslog 

  の3種類の指定が可能で、カンマ(,)区切りで複数設定することができます。
* csvlogを指定する場合は、logging_collectorをonにする必要があります。 
</div></details>

### Q．pg_hba.confのCIDRアドレス指定で誤っているものはどれか。選択せよ。
1. 192.168.16.0/24
2. 192.168.16.8/32
3. 192.168.16.0 255.255.255.0
4. localhost
5. ::1/128
<details><summary>詳細 [××●]</summary>
pg_hba.confのCIDRアドレス部分には、クライアントが所属するサブネットのアドレスをCIDR形式で設定します。また、CIDR形式の代替手段として、IPアドレスとサブネットマスクの形式で設定することも可能ですが、ドメイン名やホスト名は指定できません。 
</details>

### Q．publicスキーマと新しいスキーマ(new_schema)をsearch_pathに登録するSET文はどれか。選択せよ。
1. SET search_path ADD public, new_schema
2. SET search_path TO public, new_schema
3. SET public, new_shcmea TO search_path
4. SET public, new_shcmea ADD search_path
5. SET search_path = DEFAULT
<details><summary>詳細 [××●]</summary>
	SET文は、PostgreSQL起動中に設定値を変更できます。SET文により変更された設定値は、そのSET文を実行したセッションのみに効果があります。（例：SET search_path TO [スキーマ名]）また、設定値としてDEFAULTを指定することでデフォルト値に戻すことができます。 
</details>

### Q．次に挙げるSQLのうち、現在のデータベース名を取得するものでないものを選択せよ。
1. SELECT datname FROM pg_database;
2. SELECT * FROM information_schema.information_schema_catalog_name;
3. SELECT current_catalog;
4. SELECT current_database();
<details><summary>詳細 [××●]</summary><div>

* 現在のデータベース名の情報は、システム情報取得関数のcurrent_catalog, current_database()と情報スキーマのinformation_schema_catalog_nameで取得できます。
* システムカタログpg_databaseは現在のデータベースの情報ではなく、使用可能なデータベースの情報が格納されています。 
</div></details>

### Q．テーブルに対する権限付与について、誤っている説明を選択せよ。
1. GRANT文によってテーブルの権限を付与しないと、テーブルを作成したユーザー以外からの情報の更新ができない。
2. 権限はテーブル単位以外に列単位でも設定できる。
3. すべてのユーザーがテーブルtab1を参照できるようにするための権限付与SQLは以下の通りである。
```
GRANT SELECT ON tab1 TO public;
```
4. ユーザーusr1へテーブルtab1に対するCOPY TOの使用を許可するための権限付与SQLは以下の通りである。
```
GRANT COPY TO ON tab1 TO usr1;
```
<details><summary>詳細 [×●×]</summary><div>

* テーブルに対するアクセス権限はGRANT文により付与し、REVOKE文により剥奪します。
* すべてのユーザーに対して権限を付与する場合は、ユーザー名をpublicに指定します。
* SQLコマンドと権限の関係は、COPY TOはSELECT権限に、COPY FROMはINSERT権限に包含されます。 
</div></details>


## ２．運用管理（52％）
### Q．GRANT/REVOKEによる権限付与について正しい説明を2つ選びなさい。
* [詳細 [×●●]](https://oss-db.jp/sample/silver_management_05/90_181009)
1. テーブルの所有者は、SELECT権限をREVOKEされてもテーブルからデータをSELECTすることができる。
2. スーパーユーザは、SELECT権限をREVOKEされてもテーブルからデータをSELECTすることができる。
3. SELECTとUPDATEなど複数の権限を付与するときに、1つのGRANT文で複数の権限をまとめて指定することができる。
4. テーブルを更新するにはテーブルのデータを読む必要があるので、UPDATE権限をGRANTするだけで、自動的にSELECT権限もGRANTされる。
5. あるテーブルについてINSERT権限がGRANTされているが、SELECT権限がGRANTされていないという場合、他のユーザがINSERTしたデータはSELECTできないが、自分がINSERTしたデータはSELECTできる。

### Q．GRANTにより付与できる権限として、間違っているものを1つ選びなさい。
* [詳細 [××●]](https://oss-db.jp/sample/silver_management_04/70_161205)
1. テーブルの行を検索(SELECT)する権限
2. テーブルの特定の列を更新(UPDATE)する権限
3. テーブルのすべての行を削除(DELETE)する権限
4. テーブルを削除(DROP)する権限
5. テーブルに関する権限を他のユーザに付与(GRANT)する権限

### Q．テンプレートデータベースの説明として適切なものを2つ選びなさい。
* [詳細 [●××]](https://oss-db.jp/sample/silver_management_03/56_150904)
1. テンプレートデータベースtemplate0内には通常のデータベースと同様にテーブルを追加できる。
2. テンプレートデータベースtemplate1内には通常のデータベースと同様にテーブルを追加できる。
3. CREATE DATABASEでデータベースを新規に作成するとき、オプションで指定しなければ、template0がテンプレートデータベースとして使用される。
4. 新規にテンプレートデータベースtemplate2を作成するためには、CREATE DATABASEコマンドの実行時にTEMPLATEオプションを付加する。
5. デフォルトでは、テンプレートデータベースtemplate0には誰も接続できない。

### Q．PostgreSQLのユーザやロールの作成をOSのコマンドラインから実行する場合について、適切な記述を2つ選びなさい。
* [詳細 [××●]](https://oss-db.jp/sample/silver_management_03/42_140519)
1. ユーザの作成にはcreateuser、ロールの作成にはcreateroleコマンドを使う。
2. createuserコマンドを実行するには、CREATEUSER権限が必要である。
3. -d オプション付きで実行すると、新しいユーザにデータベース作成の権限が付与される。
4. -u オプション付きで実行すると、新しいユーザにユーザ作成の権限が付与される。
5. -s オプション付きで実行すると、新しいユーザにスーパユーザ権限が付与される。

### Q．データベースクラスタの新規作成について、正しい記述をすべて選びなさい。
* [詳細 [×××]](https://oss-db.jp/sample/silver_management_03/41_140415)
1. psqlコマンドから、CREATE CLUSTER文を実行することで作成できる。
2. OSのコマンドプロンプトからinitdbコマンドを実行することで作成できる。
3. OSのコマンドプロンプトからpg_ctl initdbコマンドを実行することで作成できる。
4. セキュリティ上の理由から、作成されるファイルはコマンドを実行したユーザ以外には読み取り許可がない。
5. セキュリティ上の理由から、OSの管理者ユーザ(Linuxならroot)が作成すべきである。

### Q．SETコマンドで実行する設定の変更について、正しい記述を2つ選びなさい。
* [詳細 [××●]](https://oss-db.jp/sample/silver_management_02/27_130213)
1. postgresql.conf で設定するすべてのパラメータについて、SETコマンドで値を変更できる。
2. SETコマンドでパラメータの値を変更した時、それがすぐに有効になるものと、pg_ctl reload などの追加処理をしなければ有効にならないものとがある。
3. SETコマンドでパラメータの値を変更しても、psql のセッションを終了すると、値はすべて元に戻る。
4. SET LOCAL parameter=value; のようにLOCALオプションを指定した場合、その後でCOMMITを実行すると、パラメータの値は元に戻る。
5. SETコマンドによるパラメータ値の変更はシステムに重大な影響があるため、データベースのスーパーユーザだけが実行できる。

### Q．postgresql.conf で設定するパラメータについて、正しい説明を2つ選びなさい。
* [詳細 [×××]](https://oss-db.jp/sample/silver_management_01/19_120815)
1. log_destination には、ログ出力先となるファイル名を指定する。
2. logging_collector を on にすることで、標準エラー出力に送られたログメッセージをログファイルにリダイレクトできる。
3. log_connections を on にすることで、クライアントからサーバへの接続試行がログに出力される。
4. log_statement を on にすることで、SQL 文をログに記録できる。
5. log_line_prefix を on にすることで、ログ情報の出力時刻、ユーザ名、プロセスIDなど様々な付加情報がログファイルに出力される。

### Q．データベースクラスタ内のデータベースの一覧を調べたい。適切な方法をすべて選びなさい。なお、$ は OS のコマンドプロンプト、=> は psql のプロンプトである。
* [詳細 [×××]](https://oss-db.jp/sample/silver_management_01/15_120502)
1. $ psql --list
2. $ pg_lsdb
3. => SELECT datname FROM pg_database;
4. => SELECT database_name FROM information_schema.databases;
5. => \list

### Q．psql でデータベースに接続している。テーブル foo の列名および列属性の一覧を表示するための適切な方法はどれか。
* [詳細 [××●]](https://oss-db.jp/sample/silver_management_01/05_110912)
1. desc foo;
2. \d foo
3. \! foo
4. show columns from foo;
5. select * from pg_tables where tablename = 'foo';


## ３．開発/SQL（32％）
### Q．PostgreSQLのバージョン11で追加されたプロシージャ(PROCEDURE)と、従来のバージョンからサポートされている関数(FUNCTION)の違いの説明として適切なものを2つ選びなさい。
* [詳細 [×××]](https://oss-db.jp/sample/silver_development_06/103_190626)
1. PROCEDURE は CREATE PROCEDURE コマンドで、FUNCTION は CREATE FUNCTION コマンドで作成する。
2. PROCEDURE は標準 SQL で定義されているが、FUNCTION は PostgreSQL 独自の拡張機能である。
3. void型の FUNCTION は廃止予定であり、PROCEDURE に置き換えることが推奨されている。
4. FUNCTION は SELECT func_name(arg1, arg2...) のようにして実行するのに対し、PROCEDURE
は CALL proc_name(arg1, arg2...) のようにして実行する。
5. PROCEDUREはデータベース内のデータを更新できるが、FUNCTIONはデータに基づいた計算をするだけで、データの更新はできない。

### Q．テーブルのパーティショニングを使うことで得られる可能性のある利点として、適切なものを選びなさい。
* [詳細 [××●]](https://oss-db.jp/sample/silver_development_05/100_190515)
1. データが占めるディスク容量を削減する。
2. 問い合わせの性能を大幅に向上させる。
3. 頻繁にアクセスする行と、そうでない行を、別のディスク領域に配置する。
4. 頻繁にアクセスする列と、そうでない列を、別のディスク領域に配置する。
5. DELETEの代わりにDROP TABLEを実行して、大量データの一括削除を高速化する。

### Q．テーブルスペース(tablespace)の使用方法として正しいものを３つ選びなさい。
* [詳細 [×××]](https://oss-db.jp/sample/silver_development_05/99_190423)
1. CREATE DATABASE で作成する新しいデータベースを、デフォルトとは異なるテーブルスペースに配置する。
2. CREATE SCHEMA で作成する新しいスキーマを、デフォルトとは異なるテーブルスペースに配置する。
3. CREATE TABLE で作成する新しいテーブルを、デフォルトとは異なるテーブルスペースに配置する。
4. CREATE VIEW で作成する新しいビューを、元となるテーブルとは異なるテーブルスペースに配置する。
5. CREATE INDEX で作成する新しいインデックスを、元となるテーブルとは異なるテーブルスペースに配置する。

### Q．DROP SCHEMA foo の結果として適切なものを１つ選びなさい。
* [詳細 [×●×]](https://oss-db.jp/sample/silver_development_05/83_180129)
1. PostgreSQLには DROP SCHEMA コマンドが存在しないのでエラーになる。スキーマを削除するにはDROP USER foo を実行する。
2. ユーザ foo が存在していたらエラーになる。
3. スキーマ foo 内にオブジェクトが存在していたら、エラーになる。
4. スキーマ foo 内にオブジェクトが存在していたら、自動的に publicに移動される。
5. スキーマ foo と、その中に存在するオブジェクトすべてが削除される。

### Q．以下の一連のSQL文でテーブルを作成し、データを挿入、更新した。最後のSELECT文が返す値は何か。
* [詳細 []](https://oss-db.jp/sample/silver_development_04/76_170703)
```
create table sample (id integer, vali integer, vals text);
insert into sample (id, vali, vals) values (1, null, 'a'), (2, 2, 'b'), (3, 3, 'c'), (4, 4, 'd'), (5, 5, null);
update sample set vali = vali -1;
update sample set vals = 'x' where vali <= 2;
update sample set vali = 10 where vals <> 'x';
select sum(vali) from sample;
```

### Q．更新可能ビューの説明として間違っているものを1つ選びなさい。
* [詳細 [×●]](https://oss-db.jp/sample/silver_development_04/62_160406)
1. 元となるSELECT文のFROM句に複数のテーブルが記述されているビューは更新できない。
2. 元となるSELECT文のFROM句に記述されているテーブルに主キーが定義されていない場合、そのビューは更新できない。
3. 元となるSELECT文がSUMなどの集約関数を使っているビューは更新できない。
4. 元となるSELECT文が複数のSELECT文のUNIONになっているビューは更新できない。
5. ビューにINSERTできた行が、SELECTで参照できるとは限らない。

### Q．インデックスについて間違った説明を1つ選びなさい。
* [詳細 [×●]](https://oss-db.jp/sample/silver_development_04/61_160307)
1. 列にPRIMARY KEYの制約をつけると、自動的にインデックスが作成される。
2. 列にUNIQUEの制約をつけると、自動的にインデックスが作成される。
3. 列にNOT NULLの制約をつけると、自動的にインデックスが作成される。
4. 列にUNIQUEの制約がなくても、インデックスをUNIQUEとして作成することができる。
5. デフォルトではB-treeインデックスが作成される。

### Q．関数定義について適切な記述を2つ選びなさい。
* [詳細 [××]](https://oss-db.jp/sample/silver_development_03/51_150324)
1. 値を返す関数のプログラムを定義する時はCREATE FUNCTION文を使う。
2. 値を返さない関数のプログラムを定義する時はCREATE PROCEDURE文を使う。
3. 定義済みの関数のプログラムを変更する時は、新しいプログラムをALTER FUNCTION文により設定する。
4. 関数の名前はスキーマ内で一意でなければならない。
5. 関数は必ずしもPL/pgSQLのような手続き言語で作成する必要はなく、SELECT文やUPDATE文などのSQLで記述することもできる。

### Q．PostgreSQLにおけるスキーマについて、適切な記述を2つ選びなさい。
* [詳細 [××]](https://oss-db.jp/sample/silver_development_03/50_150128)
1. テーブル名の指定などでスキーマ名を省略すると、defaultという名前のスキーマを指定したものとみなされる。
2. あるスキーマにテーブルを新規に作成するには、そのスキーマに対するCREATE権限が必要である。
3. スキーマを新規に作成するには、データベースに対するCREATE権限が必要である。
4. スキーマの所有者はそのスキーマと同じ名前のユーザである。
5. スキーマの下にスキーマを作成することで、最大32階層までのスキーマを作成できる。

### Q．PostgreSQLのトリガー機能について、適切な記述を2つ選びなさい。
* [詳細 [×●]](https://oss-db.jp/sample/silver_development_03/48_141030)
1. SELECT文やINSERT文の実行の前に、トリガーとして定義したプログラムが実行される。
2. CREATE TRIGGER文の中で、PL/pgSQLを使ってトリガーのコードを定義する。
3. PL/pgSQLに限らず、PL/Perlなど、他の手続き言語でもトリガーを定義できる。
4. ビューにトリガーを定義して、ビューを更新することができる。
5. 1つのテーブルの1つのイベント(例えば、BEFORE INSERT FOR EACH ROW)に定義できるトリガーは1つだけである。

### Q．ビュー(view)に関する説明として最も適切なものを2つ選びなさい。
* [詳細 [×●]](https://oss-db.jp/sample/silver_development_03/47_141030)
1. ビューに対するSELECT権限があっても、そのビューを構成するテーブルに対するSELECT権限がなければ、ビューからデータをSELECTすることはできない。
2. ビューを作成するには、そのビューを構成するテーブルあるいはテーブルの列に対するCREATE VIEW権限が必要である。
3. 既存のテーブルと同じ名前のビューを作ることはできない。
4. PostgreSQLの以前のバージョンでは、ビューの更新にはトリガー(trigger)あるいはルール(rule)を定義する必要があったが、バージョン9.3以降では、(ビューの定義によっては)トリガーやルールが定義されていないくても更新が可能である。
5. ビューからの検索を高速にするために、ビューに対してインデックスを作成することができる。

### Q．以下のSQL文でテーブルを作成した。このテーブルのid列に一意のインデックスを作成したい。以下のSQL文で適切なものを2つ選びなさい。
```
CREATE TABLE sample (id INTEGER, val TEXT);
```
* [詳細 [××]](https://oss-db.jp/sample/silver_development_03/46_141001)
1. ALTER TABLE sample ADD UNIQUE INDEX ON id;
2. ALTER TABLE sample ALTER COLUMN id UNIQUE;
3. ALTER TABLE sample ADD UNIQUE(id);
4. CREATE UNIQUE INDEX ON sample(id);
5. CREATE INDEX sample_id_unique ON sample(id);

### Q．テーブルに関する以下の説明について正しいものを2つ選びなさい。
* [詳細 [×●]](https://oss-db.jp/sample/silver_development_02/28_130227)
1. テーブルを新しく作成するにはCREATETABLE権限が必要である。
2. ALTER TABLEでテーブルにUNIQUE制約を追加することはできるが、PRIMARY KEY制約を追加することはできない。
3. ALTER TABLEでテーブルの列にデフォルト値(DEFAULT)を設定あるいは変更することができるが、これにより既存のデータの列の値が変更されることはない。
4. テーブルの作成先のスキーマが何であろうと、テーブルを作成したユーザ、つまりCREATE TABLEを実行したユーザが、そのテーブルの所有者となる。
5. テーブルの所有者はそのテーブルに関するすべての権限を有しているので、自分自身についてテーブルのSELECT権を剥奪(REVOKE)しても、引き続き、そのテーブルからSELECTすることができる。

### Q．PostgreSQLのデータ型について正しい説明を2つ選びなさい。
* [詳細 [●×]](https://oss-db.jp/sample/silver_development_02/27_130227)
1. 整数型には2バイトのSHORT、4バイトのINT、8バイトのLONGがある。
2. 整数あるいは小数を10進数で表すには、NUMBER型あるいはNUMERIC型を利用できる。
3. 可変長の文字列を表すVARCHAR型およびCHARACTER VARYING型では、その最大長をバイト単位で指定する。
4. 日付を表すDATE型には時刻の情報が含まれない。時刻を表すTIME型には日付の情報が含まれない。TIMESTAMP型には日付と時刻の両方の情報が含まれる。
5. 論理値型のBOOLEANでは真偽を表すのにTRUE、FALSEというキーワードを利用できるほか、'y', 'n', 't', 'f', '1', '0' といった文字列も利用できる。

### Q．PostgreSQLのスキーマについて、最も適切な記述を2つ選びなさい。
* [詳細 [××]](https://oss-db.jp/sample/silver_development_02/25_130220)
1. すべてのテーブルはいずれかのスキーマに所属する。
2. スキーマは階層化できるので、SELECT * FROM schemax.subschema1.subschema2.tablename;のように深いスキーマのテーブルからSELECTすることもあり得る。
3. SELECT * FROM tablename; のようにスキーマ名を指定せずにテーブル名を指定すると、publicスキーマを指定したものと見なされる。
4. SELECT * FROM tablename; のようにスキーマ名を指定せずにテーブル名を指定すると、ユーザ名と同じ名前のスキーマを指定したものと見なされる。
5. ALTER SCHEMA文でスキーマの名前や所有者を変更することができる。

### Q．次のような2つのテーブル t1 と t2 がある。いずれも、id列はINTEGER型、val列はTEXT型である。
```
=> select * from t1;

id	|	val
----	+	-----
1	|	aaa
2	|	bbb
(2 行)
=> select * from t2;

id	|	val
----	+	-----
1	|	xxx
1	|	yyy
3	|	zzz
(3 行)
```
次のSELECT文を実行した時に返される行数はいくつか。
```
select * from t1 full join t2 using (id);
```
* [詳細 [×●]](https://oss-db.jp/sample/silver_development_02/24_130124)
1. 1行
2. 2行
3. 3行
4. 4行
5. 5行

### Q．次のSQL文で表を作成した後、多数の行をINSERTした。この表で val 列の2文字目と3文字目がいずれも A である行をすべて検索したい。誤っているものを1つ選びなさい。
```
CREATE TABLE foo (id INTEGER, val VARCHAR(50));
```
* [詳細 [×●]](https://oss-db.jp/sample/silver_development_01/06_111005)
1. SELECT * FROM foo WHERE val LIKE '_AA%';
2. SELECT * FROM foo WHERE val ~ '^.AA';
3. SELECT * FROM foo WHERE substring(val, 2, 2) = 'AA';
4. SELECT * FROM foo WHERE substring(val from 2 for 2) = 'AA';
5. SELECT * FROM foo WHERE position('AA' in val) = 2;

### Q．
### Q．
### Q．