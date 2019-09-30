# 参照
* [サンプル問題](https://oss-db.jp/sample)
* [OSS-DB入門](https://oss-db.jp/dojo#dojo_nyumon)
* [オススメ！OSS-DB情報](https://oss-db.jp/dojo#dojo_column)

# OSS-DB Silver問題
## １．概要 

## ２．運用管理（52％）

## ３．開発/SQL（32％）
### Q．PostgreSQLのバージョン11で追加されたプロシージャ(PROCEDURE)と、従来のバージョンからサポートされている関数(FUNCTION)の違いの説明として適切なものを2つ選びなさい。
* [詳細 [××××]](https://oss-db.jp/sample/silver_development_06/103_190626)
1. PROCEDURE は CREATE PROCEDURE コマンドで、FUNCTION は CREATE FUNCTION コマンドで作成する。
2. PROCEDURE は標準 SQL で定義されているが、FUNCTION は PostgreSQL 独自の拡張機能である。
3. void型の FUNCTION は廃止予定であり、PROCEDURE に置き換えることが推奨されている。
4. FUNCTION は SELECT func_name(arg1, arg2...) のようにして実行するのに対し、PROCEDURE
は CALL proc_name(arg1, arg2...) のようにして実行する。
5. PROCEDUREはデータベース内のデータを更新できるが、FUNCTIONはデータに基づいた計算をするだけで、データの更新はできない。

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
* [詳細 [××●×]](https://oss-db.jp/sample/silver_development_03/51_150324)
1. 値を返す関数のプログラムを定義する時はCREATE FUNCTION文を使う。
2. 値を返さない関数のプログラムを定義する時はCREATE PROCEDURE文を使う。
3. 定義済みの関数のプログラムを変更する時は、新しいプログラムをALTER FUNCTION文により設定する。
4. 関数の名前はスキーマ内で一意でなければならない。
5. 関数は必ずしもPL/pgSQLのような手続き言語で作成する必要はなく、SELECT文やUPDATE文などのSQLで記述することもできる。

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