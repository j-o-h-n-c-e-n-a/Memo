# 参照
* [サンプル問題](https://oss-db.jp/sample)
* [OSS-DB入門](https://oss-db.jp/dojo#dojo_nyumon)
* [オススメ！OSS-DB情報](https://oss-db.jp/dojo#dojo_column)

# OSS-DB Silver問題
## １．概要 
### Q．psqlについて正しい記述はどれか。選択せよ。
1. psqlでデータベースに接続する際のデフォルトのユーザー名、データベース名はpostgresである。
2. psqlのメタコマンドの\dSは、シーケンス一覧を表示する。
3. psqlの-Dオプションでデータベースを指定して接続、-Uオプションで接続するユーザー名を指定することが出来る。
4. psqlではSQLコマンドの終わりをセミコロンで判断するが、メタコマンドは改行で終わりを判断する。
<details><summary>詳細 [×●××]</summary>
psqlではSQLコマンドの終わりをセミコロンで判断する為、SQLコマンドは1行が長い場合改行で分けて記述が出来ますが、メタコマンドは必ず1行で入力する必要があります。
</details>

## ２．運用管理（52％）
### Q．データベースクラスタの新規作成について、正しい記述をすべて選びなさい。
* [詳細 [×××●]](https://oss-db.jp/sample/silver_management_03/41_140415)
1. psqlコマンドから、CREATE CLUSTER文を実行することで作成できる。
2. OSのコマンドプロンプトからinitdbコマンドを実行することで作成できる。
3. OSのコマンドプロンプトからpg_ctl initdbコマンドを実行することで作成できる。
4. セキュリティ上の理由から、作成されるファイルはコマンドを実行したユーザ以外には読み取り許可がない。
5. セキュリティ上の理由から、OSの管理者ユーザ(Linuxならroot)が作成すべきである。

### Q．SETコマンドで実行する設定の変更について、正しい記述を2つ選びなさい。
* [詳細 [××●×]](https://oss-db.jp/sample/silver_management_02/27_130213)
1. postgresql.conf で設定するすべてのパラメータについて、SETコマンドで値を変更できる。
2. SETコマンドでパラメータの値を変更した時、それがすぐに有効になるものと、pg_ctl reload などの追加処理をしなければ有効にならないものとがある。
3. SETコマンドでパラメータの値を変更しても、psql のセッションを終了すると、値はすべて元に戻る。
4. SET LOCAL parameter=value; のようにLOCALオプションを指定した場合、その後でCOMMITを実行すると、パラメータの値は元に戻る。
5. SETコマンドによるパラメータ値の変更はシステムに重大な影響があるため、データベースのスーパーユーザだけが実行できる。


## ３．開発/SQL（32％）
### Q．PostgreSQLのバージョン11で追加されたプロシージャ(PROCEDURE)と、従来のバージョンからサポートされている関数(FUNCTION)の違いの説明として適切なものを2つ選びなさい。
* [詳細 [××××]](https://oss-db.jp/sample/silver_development_06/103_190626)
1. PROCEDURE は CREATE PROCEDURE コマンドで、FUNCTION は CREATE FUNCTION コマンドで作成する。
2. PROCEDURE は標準 SQL で定義されているが、FUNCTION は PostgreSQL 独自の拡張機能である。
3. void型の FUNCTION は廃止予定であり、PROCEDURE に置き換えることが推奨されている。
4. FUNCTION は SELECT func_name(arg1, arg2...) のようにして実行するのに対し、PROCEDURE
は CALL proc_name(arg1, arg2...) のようにして実行する。
5. PROCEDUREはデータベース内のデータを更新できるが、FUNCTIONはデータに基づいた計算をするだけで、データの更新はできない。

### Q．テーブルスペース(tablespace)の使用方法として正しいものを３つ選びなさい。
* [詳細 [×××●]](https://oss-db.jp/sample/silver_development_05/99_190423)
1. CREATE DATABASE で作成する新しいデータベースを、デフォルトとは異なるテーブルスペースに配置する。
2. CREATE SCHEMA で作成する新しいスキーマを、デフォルトとは異なるテーブルスペースに配置する。
3. CREATE TABLE で作成する新しいテーブルを、デフォルトとは異なるテーブルスペースに配置する。
4. CREATE VIEW で作成する新しいビューを、元となるテーブルとは異なるテーブルスペースに配置する。
5. CREATE INDEX で作成する新しいインデックスを、元となるテーブルとは異なるテーブルスペースに配置する。

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

### Q．関数定義について適切な記述を2つ選びなさい。
* [詳細 [××●]](https://oss-db.jp/sample/silver_development_03/51_150324)
1. 値を返す関数のプログラムを定義する時はCREATE FUNCTION文を使う。
2. 値を返さない関数のプログラムを定義する時はCREATE PROCEDURE文を使う。
3. 定義済みの関数のプログラムを変更する時は、新しいプログラムをALTER FUNCTION文により設定する。
4. 関数の名前はスキーマ内で一意でなければならない。
5. 関数は必ずしもPL/pgSQLのような手続き言語で作成する必要はなく、SELECT文やUPDATE文などのSQLで記述することもできる。

### Q．PostgreSQLにおけるスキーマについて、適切な記述を2つ選びなさい。
* [詳細 [××●]](https://oss-db.jp/sample/silver_development_03/50_150128)
1. テーブル名の指定などでスキーマ名を省略すると、defaultという名前のスキーマを指定したものとみなされる。
2. あるスキーマにテーブルを新規に作成するには、そのスキーマに対するCREATE権限が必要である。
3. スキーマを新規に作成するには、データベースに対するCREATE権限が必要である。
4. スキーマの所有者はそのスキーマと同じ名前のユーザである。
5. スキーマの下にスキーマを作成することで、最大32階層までのスキーマを作成できる。

### Q．以下のSQL文でテーブルを作成した。このテーブルのid列に一意のインデックスを作成したい。以下のSQL文で適切なものを2つ選びなさい。
```
CREATE TABLE sample (id INTEGER, val TEXT);
```
* [詳細 [××●]](https://oss-db.jp/sample/silver_development_03/46_141001)
1. ALTER TABLE sample ADD UNIQUE INDEX ON id;
2. ALTER TABLE sample ALTER COLUMN id UNIQUE;
3. ALTER TABLE sample ADD UNIQUE(id);
4. CREATE UNIQUE INDEX ON sample(id);
5. CREATE INDEX sample_id_unique ON sample(id);

### Q．PostgreSQLのスキーマについて、最も適切な記述を2つ選びなさい。
* [詳細 [××●]](https://oss-db.jp/sample/silver_development_02/25_130220)
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

### Q．
### Q．