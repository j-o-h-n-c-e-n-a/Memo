## 概要 
### データモデリングの一般的な手順はどれか
	データモデリングは、はじめに対象世界を抽象化して概念データモデルを作成します。
	次に概念データモデルを変換して論理データモデルを作成します。 
1. ［対象世界］→＜変換＞→［論理データモデル］→＜抽象化＞→［概念データモデル］
2. ［対象世界］→＜抽象化＞→［論理データモデル］→＜変換＞→［概念データモデル］
3. ［対象世界］→＜変換＞→［概念データモデル］→＜抽象化＞→［論理データモデル］
4. ［対象世界］→＜抽象化＞→［概念データモデル］→＜変換＞→［論理データモデル］

### 関係モデルについて述べたもののうち、誤っているものはどれか。
	選択肢1,2,4は関係モデルについて述べたものです。
	関係と関係とを関連づけることでデータ構造を表現しますので選択肢3が誤っています。
	選択肢3は階層モデルの説明です。 
1. 行と列とからなる表構造でデータを表現する。
2. 一般的に複数の表構造によりモデルが定義される。
3. 親子関係を持たせることでデータ構造を表現する。
4. リレーショナルデータベースには関係モデルが使われる。

### テーブルのインデックス作成、変更、削除などを行う命令が含まれるものはどれか。
	DML(Data Manipulation Language)はデータ操作言語で、データの参照や追加更新を行います。
	DDL(Data Definition Language)はデータ定義言語で、テーブルやインデックスの作成、変更、削除などを行いますので選択肢2が正解です。
	DCL(Data Control Language)はデータ制御言語で、権限の付与や剥奪、データ操作の確定やキャンセルなどを行います。
	DLL(Dynamic Link Library)はSQLではありません。 
1. DML
2. DLL
3. DDL
4. DCL

### 概念データモデルから論理データモデルに変換する主な作業手順として正しいものはどれか。
	選択肢1は、概念データモデルの作成手順です。
	選択肢2は、概念データモデルから論理データモデルへの変換手順ですので正解です。
	選択肢3は、関係の候補キーと主キーの選択手順です。
	選択肢4は、正規化の手順です。 
1. 管理対象とするデータを抽出し、エンティティとして定義し、主な属性を明確にし、エンティティ間の関係を明確にする。
2. 多対多の関係を解消し、属性や属性のデータ型やサイズを明確にし、正規化を行う。
3. 候補キーを明確にし、候補キーの中から主キーを1つ選択する。
4. 繰返し項目を解消し、導出項目を削除し、部分関数従属を解消し、推移関数従属を解消する。

### 関数従属について正しい説明はどれか。
	1.は「属性Yは属性Xに関数従属する」というのが正しく、記述が逆になっています。
	2.の完全関数従属とはXの真部分集合X'について、YがX'に関数従属しない場合のことをいうため誤りです。
	3.は正しいです。
	4.は推移関数従属の説明は正しいですが、第二正規形でではなく、第三正規形で取り除かれます。 
1. ある属性Xの値を決定すれば別の属性Yの値が一つに決まる場合、「属性Xは属性Yに関数従属する」という。
2. 属性Yが属性Xに完全関数従属する場合、Xの部分集合X'についてもYがX'に関数従属することになる。
3. 候補キーの一部の属性に候補キー以外の属性が関数従属することを部分関数従属という。
4. 推移関数従属とは、候補キーの属性Xが決まると属性Yが決まり、属性Yが決まると属性Zが決まる場合に、属性Zは属性Xに対して推移関数従属するという。第二正規形にする際に取り除かれる。

### PostgreSQLのデータベースクラスタの説明に関して間違っているものはどれか。選択せよ。
	initdbコマンドによって作成されたデータベースの格納領域をデータベースクラスタと呼びます。
	データベースクラスタの実体は、ファイルシステム上の1つのディレクトリであり、initdbコマンドのオプションでディレクトリを指定するが出来ます。データベースクラスタを複数のマシンに分散することはできません。
	データベースクラスタの管理はデータベースサーバの1つのインスタンスを通して行います。
	複数のデータベースクラスタを作成した場合、それぞれのデータベースクラスタの管理は、異なるインスタンスを通して行います。 
1. データベースクラスタとPostgreSQLサーバは1対1で対応する。
2. データベースクラスタの実体はファイルシステム上のディレクトリである。
3. 1台のマシン上に複数のデータベースクラスタを作成することができる。
4. データベースクラスタは複数のマシン上に分散して配置することができる。
5. データベースクラスタは任意のディレクトリに作成することができる。

### PostgreSQLのデータベースクラスタ($PGDATA)の主なディレクトリとファイルの記述として、間違っているものはどれか。選択せよ。
	postgresql.confは、PostgreSQLのパラメータを設定するファイルです。なお、クライアントの認証方法はpg_hba.confファイルで設定します。
1. baseディレクトリには、データベースのデータが格納される。
2. pg_xlogディレクトリには、トランザクションログ(WAL)が格納される。
3. postgresql.confファイルには、クライアントの認証方法が設定される。
4. globalディレクトリには、ユーザー情報などデータベース間で共通のデータが格納される。

### PostgreSQLにおけるデータベースの説明として間違っているものはどれか。選択せよ。
	initdbコマンドはデータベースクラスタの作成を行うためのコマンドであり、テンプレートおよびPostgresデータベースのみ作成されます。任意の名称のデータベースは作成できないため誤りです。
	データベース作成および初期化は、createdbコマンド、またはSQLのCREATE DATABASEを実行することで行います。
	作成したデータベースの実体は、$PGDATA/base以下のディレクトリとして作成され、テーブルやインデックスのデータはデータベース毎に格納されます。 
1. データベースは、テーブルやインデックスなどのデータベースオブジェクトの集合である。
2. データベースの実体はファイルシステム上のディレクトリである。
3. データベースクラスタには複数のデータベースを作成することができる。
4. initdbコマンドにより任意の名称のデータベースを作成し、データベースを利用できる。

### PostgreSQLのデータベースクラスタ作成時に定義されるテンプレートデータベース「template0」、「template1」について適切な記述はどれか。選択せよ。
	データベースクラスタ作成直後はtemplate0とtemplate1は同じ内容のテンプレートデータベースです。
	デフォルトでは、template1が新しいデータベースのテンプレートとして使われます。template1にはオブジェクトを追加登録することができるため、多くのデータベースで利用するオブジェクトをtemplate1に事前登録することでデータベース作成後の手順を簡略化することができます。
	template0にはオブジェクトの追加登録はできず、template1に追加登録されたオブジェクトも反映されません。template1に追加登録されたオブジェクトを利用したくない場合、template0を指定してデータベースを作成します。

* 次の例ではテンプレートデータベースであるtemplate0を指定してデータベースtest1を作成しています。
```
CREATE DATABASE test1 TEMPLATE template0;
```
1. データベースクラスタ作成直後はtemplate0とtemplate1は同じ内容のテンプレートデータベースである。
2. template1にオブジェクトが追加登録されるたびにtemplate0にも同じオブジェクトが追加登録される。
3. 指定しない限り、template0が新しいデータベースのテンプレートとして使われる。
4. template0にデータベースオブジェクトの登録などの内容の変更が可能である。

### PostgreSQLにおけるロケールに関する記述について、適切なものはどれか。選択せよ。
	データベースへのロケール設定は、必須ではありません。参考までに、日本（日本語）ではロケールは無効にすることが推奨されています。
	ロケールはクライアント側で使用されているロケールと異なるロケールをデータベースに設定でき、データベース単位でロケールを設定することもできます。
	データベースのデフォルトのロケールはinitdbで指定した値になります。
	initdbコマンドで指定したロケールと異なるロケールのデータベースを作成するには、template0をテンプレートに指定した上で、データベース作成時にロケールを指定します。

* 次の例ではPostgreSQLの標準ツールであるcreatedbを利用して、ロケールに日本語が設定されたデータベースtest1を作成しています。
```
createdb test1 --locale=japanese --template=template0
```
1. データベースに、ロケールは必ず設定しなければならない。
2. initdbコマンドで指定したロケールと異なるロケールのデータベースを作成することはできない。
3. ロケールはデータベース単位で指定することができる。
4. クライアント側で使用されているロケールと同じロケールをデータベースに設定する必要がある。

### PostgreSQLにおけるエンコーディングの設定では、データベースとクライアントについて個別のエンコーディングを指定することが出来る。次のうち指定できない文字セットの組み合わせを選択せよ。
	PostgreSQLでは、データベースエンコーディングにSJISを指定することは出来ません。
	文字セットとしてSJISを利用したい場合には、データベースエンコーディングにUTF-8またはEUC-JPを指定し、クライアントエンコーディングにSJISを指定します。
	データベースエンコーディングと異なるクライアントエンコーディングを用いる場合には、クライアントエンコーディングをデータベースに通知する必要が有ります。
	主な方法を以下に示します。

* psqlで\encodingコマンドを利用する。
* libpqが提供する関数を利用する。
* SQLコマンドの”SET CLIENT_ENCODING TO 'value'”を利用する。
* クライアントの環境でPGCLIENTENCODING環境変数を設定する。
* PostgreSQLのパラメータを設定するファイル(postgresql.conf)にclient_encodingを設定する。 

1. データベースエンコーディングがSJIS。
	クライアントエンコーディングがSJIS。
2. データベースエンコーディングがUTF-8。
	クライアントエンコーディングがSJIS。
3. データベースエンコーディングがEUC-JP。
	クライアントエンコーディングがSJIS。
4. データベースエンコーディングがUTF-8。
	クライアントエンコーディングがEUC-JP。
5. データベースエンコーディングがEUC-JP。
	クライアントエンコーディングがUTF-8。

### スマートシャットダウン(pg_ctl stop -m smart)の動作について正しい記述はどれか。選択せよ。
	スマートシャットダウンは既存の接続が全て切断されるのを待ってから正常終了をします。
	ちなみに、3は高速シャットダウン(pg_ctl stop -m fast)、4は即時シャットダウン(pg_ctl stop -m immediate)の動作になります。 

1. 既に接続されている接続が全て切断されるのを待った後、正常終了する。
2. 既に接続されている接続が全て切断されるのを待つが、実行中のトランザクションは全てロールバックされる。
3. 既に接続されている接続を強制的に切断し、実行中のトランザクションは全てロールバックされる。 
4. クリーンアップ処理を行なわずに緊急停止する(PostgreSQLがクラッシュしたのと同じ状態になる)。 

### pg_ctlについて適切な記述はどれか。選択せよ。
	pg_ctl initdbとinitdbは同じ処理内容です。pg_ctl initdbで主に使用するオプションには-D(--pgdata=)と-oがあります。-Dではデータベースクラスタを指定し、-oでは内部的に呼び出すinitdbに渡すオプションが指定出来ます。 

1. postgresql.confの設定値を変更した後にpg_ctl reload を実行すると全ての変更箇所が反映される。
2. pg_ctl startにおいて-Wオプションをつけると、PostgreSQLが起動完了するまで待つ。
3. pg_ctlはPostgreSQLが実際稼働していないホストからのリモート実行が可能であり、実行するユーザーはPostgreSQLの管理ユーザーでなければならない。
4. pg_ctl initdbとinitdbの処理内容は同じであり、どちらをデータベースクラスタの作成に使っても問題ない。

### dropdbを使用して、スーパユーザーuser1で、ホストhost1、ポート10000で動作しているデータベースクラスタからdb1データベースを削除する。このとき正しいコマンドを示すのはどれか。選択せよ。
	dropdbのオプションは以下になります。
	```
	dropdb [option] dbname
	```
	dbname: 削除するデータベース名を指定

	[option]
	-h: ホスト名を指定
	-p: ポート番号を指定
	-U: ユーザー名を指定
	-W: パスワードの入力を強制
	-e: dropdbが生成し、バックエンドに送信する問い合わせを表示
	-q: メッセージを表示しない
	-i: dropdbを実行する前に確認を促す

1. $ dropdb user1 host1 10000 db1
2. $ dropdb -U user1 host1:10000:db1
3. $ dropdb -U user1 -p 10000 host1:db1
4. $ dropdb -U user1 -p 10000 -h host1 db1
5. $ dropdb -U user1 -p 10000 -h host1 -D db1

### createdb、dropdbコマンドについて適切な記述はどれか。選択せよ。
	2については、createdbコマンドに-Tオプションの指定がないとtemplate1がテンプレートデータベースとなります。
	3については、データベースを削除していいかを確認するにはdropuserと同様に-iオプションが必要です。
	4については、dropdbコマンドを実行出来るのは、データベースのスーパーユーザーまたはデータベースの所有者のみです。 

1. createdbコマンドでデータベースを作成するとき、「-O」オプションで所有者を指定した場合は、その所有者がスーパーユーザー権限やデータベース作成権限を持っていなくても、作成したデータベースの削除が可能となる。
2. createdbコマンドに-Tオプションをつけるとテンプレートデータベースの指定が出来る。指定がないとtemplate0がテンプレートデータベースとなる。
3. dropdbコマンドはデフォルトでデータベースを削除してよいかの確認を削除前に取るようになっている。
4. dropdbコマンドを実行出来るのは、データベースのスーパーユーザーまたはデータベース作成権限を持っているユーザーのみである。

### PostgreSQLにおいての手続き言語の登録と削除について適切な記述はどれか。選択せよ。
	手続き言語は手続き言語を使用するデータベースに登録されている必要があり、登録にはcreatelangコマンドを使用します。反対に登録されている手続き言語を削除する場合はdroplangコマンドを使用します。

1. 手続き言語は手続き言語を使用するデータベースに登録されている必要があり、登録にはcreatelangコマンドを使用する。
2. 手続き言語を登録出来るのはスーパーユーザーのみである。
3. 手続き言語の登録と削除はデータベース単位で指定することは出来ない。
4. テンプレートデータベースに手続き言語を登録した場合でも、以降そのテンプレートデータベースを利用して新しくデータベースを作成した時に自動的に手続き言語が登録されることはない。

### psqlについて正しい記述はどれか。選択せよ。
	psqlではSQLコマンドの終わりをセミコロンで判断する為、SQLコマンドは1行が長い場合改行で分けて記述が出来ますが、メタコマンドは必ず1行で入力する必要があります。

1. psqlでデータベースに接続する際のデフォルトのユーザー名、データベース名はpostgresである。
2. psqlのメタコマンドの\dSは、シーケンス一覧を表示する。
3. psqlの-Dオプションでデータベースを指定して接続、-Uオプションで接続するユーザー名を指定することが出来る。
4. psqlではSQLコマンドの終わりをセミコロンで判断するが、メタコマンドは改行で終わりを判断する。

### log_rotation_ageの指定として1日を設定する場合、誤っているものはどれか。選択せよ。
	時間の設定値には次のような単位を指定できます。
* ms：ミリ秒
* s：秒
* min：分
* h：時間
* d：日
	単位を省略した場合、log_rotation_ageは'分'として扱われます。 
1. 1d
2. 24h
3. 1440m
4. 1440
5. 86400s

### listen_addressesの説明で適切なものはどれか。選択せよ。
	listen_addressesには、クライアントからの接続を監視するPostgreSQL側のIPアドレスもしくはホスト名を指定します。複数のアドレスを指定する場合はカンマ(,)区切って指定します。また、アスタリスク(*)を指定した場合は、PostgreSQL側で利用可能な全てのアドレスに対して接続を監視します。
	設定の変更にはPostgreSQLの再起動が必要です。
	クライアントのアクセス権限はph_hba.conf で設定します。 

1. 接続予定のクライアントのIPアドレスを指定することで、該当のクライアントの接続を監視する。
2. 複数のIPアドレスを指定することはできない。
3. 変更内容はpg_ctl reloadで有効にすることができる。
4. '*'を指定することで、利用可能な全てのIPアドレスの接続を監視する。
5. 接続予定のクライアントのホスト名をカンマ区切りで複数指定することで、該当のクライアントの接続を監視する。

### log_destinationの設定で誤っているものはどれか。選択せよ。
	log_destinationは、サーバログの出力先を設定します。出力先は
* stderr
* csvlog
* syslog
	の3種類の指定が可能で、カンマ(,)区切りで複数設定することができます。
	csvlogを指定する場合は、logging_collectorをonにする必要があります。 

1. syslog
2. stderr
3. syslog, stderr
4. csvlog
5. file

### 起動中のPostgreSQLに、max_connectionsの設定を反映する方法のうち、適切なものはどれか。選択せよ。
	max_connectionsの設定変更を反映するためには、PostgreSQLの再起動が必要であり、以下のどちらかを行う必要があります。
* pg_ctl stop および pg_ctl start
* pg_ctl restart
	同様に設定反映のためにPostgreSQLの再起動が必要なものは、postgresql.confに'# (change requires restart)' というコメントが付いています。 

1. pg_ctl reloadを実行する。
2. pg_ctl stopを実行する。
3. pg_ctl restartを実行する。
4. pg_ctl statusを実行する。
5. pg_ctl startを実行する。

### pg_hba.confのCIDRアドレス指定で誤っているものはどれか。選択せよ。
	pg_hba.confのCIDRアドレス部分には、クライアントが所属するサブネットのアドレスをCIDR形式で設定します。また、CIDR形式の代替手段として、IPアドレスとサブネットマスクの形式で設定することも可能ですが、ドメイン名やホスト名は指定できません。 

1. 192.168.16.0/24
2. 192.168.16.8/32
3. 192.168.16.0 255.255.255.0
4. localhost
5. ::1/128

### publicスキーマと新しいスキーマ(new_schema)をsearch_pathに登録するSET文はどれか。選択せよ。
	SET文は、PostgreSQL起動中に設定値を変更できます。SET文により変更された設定値は、そのSET文を実行したセッションのみに効果があります。また、設定値としてDEFAULTを指定することでデフォルト値に戻すことができます。 

1. SET search_path ADD public, new_schema
2. SET search_path TO public, new_schema
3. SET public, new_shcmea TO search_path
4. SET public, new_shcmea ADD search_path
5. SET search_path = DEFAULT

### PostgreSQLのデータベースクラスタ全体をバックアップ(スクリプトファイルへ抽出)する際に使用するコマンドはどれか。選択せよ。
	PostgreSQL全体をバックアップするコマンドは、pg_dumpallコマンドを用います。 

1. pg_dump --full
2. pg_dumpall
3. pg_dumpfull
4. psql dumpall
5. pg_dump all

### pg_dump/pg_dumpallコマンドによるバックアップに関して、テキスト形式にならないコマンドはどれか。選択せよ。
	pg_dumpコマンドの-Fオプションにtを指定すると、tar形式のバックアップを取得します。

1. pg_dump -Ft
2. pg_dump
3. pg_dump -Fp
4. pg_dumpall

### pg_dump/pg_dumpallコマンドで取得したテキスト形式のバックアップファイル(bkup.dmp)をリストアする際に使用するコマンドはどれか。選択せよ。
	テキスト形式のバックアップをリストアする際には、psqlコマンドを利用します。その際、-fオプションで対象のバックアップファイルを指定します。 
	
1. psql bkup.dmp
2. pg_restore -Fp bkup.dmp
3. psql -Fp bkup.dmp
4. pg_restore -f bkup.dmp
5. psql -f bkup.dmp

### ディレクトリコピーによるバックアップ(コールドバックアップ)に関して正しい記述はどれか。選択せよ。
	コールドバックアップではデータベースクラスタ全体を取得する必要があります。 

1. テーブル単位で取得する。
2. データベースクラスタ単位で取得する。
3. データベース単位で取得する。
4. スキーマ単位で取得する。

### psqlの\copyコマンドの説明に関して、正しいものはどれか。選択せよ。
	\copyコマンドは、クライアント側のファイルとサーバ側のテーブル間でデータのコピーを行うコマンドです。

1. サーバ側のファイルをテーブルにコピーする。
2. ファイル名は絶対パスのみ指定可能である。
3. スーパーユーザーで実行する必要がある。
4. クライアントとサーバ間でデータの送受信がなされる。

### 自動バキュームについて誤った記述を選択せよ。
	自動バキューム機能の設定はpostgresql.confで設定します。
	自動バキュームの実行には自動バキュームデーモンの起動有無を表すパラメータautovacuumと統計情報の収集有無を表すパラメータtrack_countsがいずれも有効になっている必要があります。
	PostgreSQL 9.0ではどちらのパラメータもデフォルトで有効となっています。

	自動バキュームは、それぞれのテーブルの更新量が閾値以上になった時にテーブル単位でVACUUMとANALYZEが自動実行されます。 

1. 自動バキューム機能は、postgresql.confで設定する。
2. 自動バキューム機能をONにした場合、一定間隔でVACUUMとANALYZEを実行する。
3. PostgreSQL9.0では自動バキューム機能の設定値はデフォルトで有効となっている。
4. 自動バキューム機能を動作させるにはpostgresql.confのautovacuumパラメータ,track_countsパラメータのいずれも有効になっている必要がある。

### データベースのユーザー管理について、適切な記述を選択せよ。
	CREATE USER文、あるいはALTER USER文ではVALID UNTILオプションを使ってパスワードの有効期限を設定することができます。 
1. ユーザーに設定する権限はあとから変更することができないので慎重にユーザーを作成する必要がある。
2. DROP USER文でユーザーの削除を行うことができるのは、スーパーユーザー権限を持ったユーザーとDROP USER権限を持ったユーザーのみである。
3. 以下のSQL文を実行してユーザーを作成した。
```
CREATE USER user1 WITH PASSWORD 'password';
```
作成したユーザーuser1は、ALTER USER文でログイン権限を付与するまでPostgreSQLにログインできない。
4. ユーザーを作成する際、対象ユーザーのパスワード有効期限を設定することができる。

### 次に挙げるSQLのうち、現在のデータベース名を取得するものでないものを選択せよ。
	現在のデータベース名の情報は、システム情報取得関数のcurrent_catalog,current_database()と情報スキーマのinformation_schema_catalog_nameで取得できます。
	システムカタログpg_databaseは現在のデータベースの情報ではなく、使用可能なデータベースの情報が格納されています。 

1. SELECT datname FROM pg_database;
2. SELECT * FROM information_schema.information_schema_catalog_name;
3. SELECT current_catalog;
4. SELECT current_database();

### 次に上げる情報のうち、情報スキーマから取得できないものを選択せよ。
	情報スキーマは、現在のデータベースで定義されたオブジェクトについての情報を持つビューの集合から構成され、標準SQLで定義されています。

	PostgreSQL固有の機能についての情報は情報スキーマには含まれていません。PostgreSQL固有の情報はシステムカタログやPostgreSQL独自関数により取得できます。 

1. データベース上に定義されているユーザー
2. PostgreSQLのバージョン
3. データベース上に定義されているテーブル
4. データベース上に定義されたテーブルへのアクセス権限

### \dpコマンドでテーブルの権限を確認したところ、NameがtesttableのレコードのAccess privilegesが以下のような値だった。
```
test=arwdDxt/test+
test2=rwD/test
```
このときの説明として正しいものを選択せよ。
	\dpコマンド、もしくは\zコマンドを使うとテーブルに付与された権限を確認することができます。
	\dpコマンドで表示される権限情報の書式は以下の通りです。
```
<ユーザー名>=<権限情報>/権限付与したユーザー
```
ユーザー名の部分が空白で、=からはじまっている場合、すべてのユーザー(PUBLIC)へ付与された権限内容を表します。
権限情報の内容は以下の通りです。
　r：SELECT権限
　w：UPDATE権限
　a：INSERT権限
　d：DELETE権限
　D：TRUNCATE権限
　x：外部キー制約権限
　t：TRIGGER権限 

1. ユーザーtest2はテーブルtesttableに対してINSERT権限を持つ。
2. ユーザーtest2はテーブルtesttableに対してCOPY TOを使用することができない。
3. ユーザーtest2は、テーブルtesttableに対するSELECT権限を他のユーザーtest3に付与することができる。
4. このような権限を付与するためのGRANT文は以下の通りである。
```
GRANT SELECT,UPDATE,TRUNCATE ON testtable TO test2;
```
5. このような権限を付与するためのGRANT文は以下の通りである。
```
GRANT SELECT,UPDATE,DELETE ON testtable TO test2;
```

### テーブルに対する権限付与について、誤っている説明を選択せよ。
	テーブルに対するアクセス権限はGRANT文により付与し、REVOKE文により剥奪します。
	すべてのユーザーに対して権限を付与する場合は、ユーザー名をpublicに指定します。
	SQLコマンドと権限の関係は、COPY TOはSELECT権限に、COPY FROMはINSERT権限に包含されます。 

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

### 集合演算子であるUNION、EXCEPT、INTERSECTの処理には優先順位が定められている。次の選択肢のうち、正しいものはどれか。
	標準SQLではUNIONとEXCEPTに対して、INTERSECTのほうが先に実行されるよう定められています。
	UNIONとEXCEPTの処理の優先順位は同じです。 

1. UNION < EXCEPT
	EXCEPT < INTERSECT
2. UNION = EXCEPT
	EXCEPT < INTERSECT
3. UNION = EXCEPT
	UNION > INTERSECT
4. UNION > EXCEPT
	EXCEPT > INTERSECT

### 以下のうち、boolean型の表現として使用できないものはどれか。
	boolean型の指定として整数の1と0は使用できません。指定する場合は'1','0'と文字列として指定する必要があります。 

1. 't'
2. 'y'
3. 'on'
4. 1

### 以下(A)～(D)のうち、ALTER TABLEで行えないものはどれか。

(A)テーブル名の変更
(B)列名の変更
(C)列の削除
(D)列のデータ型の変更
 
1. (A)テーブル名の変更
2. (B)列名の変更
3. (C)列の削除
4. (D)列のデータ型の変更
5. すべて可能

### 以下のようなテーブルnumberが与えられている。
```
CREATE TABLE number ( code VARCHAR(10) , no INTEGER);
INSERT INTO number(code , no) VALUES('one' , 1);
INSERT INTO number(code , no) VALUES('one' , 2);
INSERT INTO number(code , no) VALUES('two' , 1);
INSERT INTO number(code , no) VALUES('two' , 2);
INSERT INTO number(code , no) VALUES('two' , 3);
INSERT INTO number(code , no) VALUES('three' , 1);
INSERT INTO number(code , no) VALUES('three' , 2);
INSERT INTO number(code) VALUES('four');
```
このとき、以下のSQLの出力結果として適切なものはどれか。選択せよ。
```
SELECT * FROM number WHERE no > (SELECT MIN(no) FROM number WHERE code = 'five');
```
 
1. 7行の検索結果が返る。
2. 8行の検索結果が返る。
3. 0行の検索結果が返る。
4. シンタックスエラーとなる。

### トランザクションのもつ特性について誤った記述はどれか。選択せよ。
* Correctness(正当性)は、ACID属性には含まれていません。
* トランザクションのACID特性は、Atomicity(原子性)、Consistency(整合性)、Isolation(分離性)、Durability（持続性）の頭文字をとって名づけられました。
* Consistency(整合性)は、トランザクションの開始と終了時には、データベースは整合性を保った状態となっていることを保証します。 

1. トランザクションは実行が完了するか、あるいはまったく実行されないかのどちらかとなることを、トランザクションのAtomicity(原子性)という。
2. トランザクションのACID特性は、Atomicity(原子性)、Correctness(正当性)、Isolation(分離性)、Durability（持続性）の頭文字をとって名づけられた。
3. トランザクションは別のトランザクションによる処理の影響を受けないことを、トランザクションのIsolation(分離性)という。
4. トランザクションにより変更されたデータは確実に保持されることを、トランザクションのDurability(持続性)という。

### SAVEPOINTの記述として正しいものはどれか。選択せよ。
* トランザクション内で同じセーブポイント名を設定した場合、一時的に古い方を上書きします。
* SAVEPOINT sp1; の場所へ戻るときのコマンドは ROLLBACK TO sp1; です。
* COMMITでトランザクション処理を確定した後は、COMMIT前の状態に戻ることはできません。
* トランザクション内でエラーが発生した場合、設定した任意のSAVEPOINTまで戻って処理を続けることが可能です。 
1. SAVEPOINT sp1; で作成したポイントへ戻りたいときは、ROLLBACK sp1; を発行する。
2. COMMIT発行後もCOMMIT発行前のSAVEPOINTへROLLBACKすることができる。
3. 1つのトランザクションの中に、同じ名前のSAVEPOINTを設定することができる。
4. トランザクション内でエラーが起こった場合、それまでに設定したSAVEPOINTは無効になる。

## 運用管理（52％）
### テンプレートデータベースの説明として適切なものを2つ選びなさい。
	https://oss-db.jp/sample/silver_management_05/93_190212
1. テンプレートデータベースを新たに作成するには CREATE TEMPLATE DATABASE コマンドを実行する。
2. 作成済みの通常のデータベースを ALTER DATABASE コマンドでテンプレートデータベースに変更することができる。
3. テンプレートデータベースに、テーブルやビューを新たに追加することはできるが、データをINSERTにより追加することはできない。
4. テンプレートデータベースは、DROP DATABASEで削除できない。
5. テンプレートデータベースの所有者が誰であっても、CREATEDB権限のあるユーザはそれを複製できる。

### GRANT/REVOKEによる権限付与について正しい説明を2つ選びなさい。
	https://oss-db.jp/sample/silver_management_05/90_181009
1. テーブルの所有者は、SELECT権限をREVOKEされてもテーブルからデータをSELECTすることができる。
2. スーパーユーザは、SELECT権限をREVOKEされてもテーブルからデータをSELECTすることができる。
3. SELECTとUPDATEなど複数の権限を付与するときに、1つのGRANT文で複数の権限をまとめて指定することができる。
4. テーブルを更新するにはテーブルのデータを読む必要があるので、UPDATE権限をGRANTするだけで、自動的にSELECT権限もGRANTされる。
5. あるテーブルについてINSERT権限がGRANTされているが、SELECT権限がGRANTされていないという場合、他のユーザがINSERTしたデータはSELECTできないが、自分がINSERTしたデータはSELECTできる。

### 自動バキュームの説明として正しいものを3つ選びなさい。
	https://oss-db.jp/sample/silver_management_05/88_180807
1. 削除済みのタプル領域を回収する。
2. テーブルの統計情報を取得する。
3. 大量のタプルの挿入・削除・更新が行われたテーブルを検査する。
4. データベースの負荷が小さくなったときに自動的に起動する。
5. データベースの負荷が大きいときは起動が抑制される。

### ALTER USERコマンドで変更できないユーザ属性はどれか。1つ選びなさい。
	https://oss-db.jp/sample/silver_management_05/86_180611
1. ユーザのパスワード
2. ユーザのパスワードが無効になる日時
3. 新しいユーザを作成する権限の有無
4. データベースクラスタに接続する権限の有無
5. データベース内に新しいテーブルを作成する権限の有無

### ファイルシステムレベルの物理的なバックアップとリストアを行う手順について適切なものを2つ選びなさい。
	https://oss-db.jp/sample/silver_management_05/83_180313
1. ファイルのコピーなどでバックアップを作成する前に、必ずデータベースを停止する必要がある。
2. ログアーカイブの運用をしているのであれば、バックアップ作成時に、データベースは停止してもしなくても良い。
3. ファイルシステムのレイアウトを正確に理解すれば、テーブル単位でバックアップとリストアを実行できる。
4. ファイルシステムのレイアウトを正確に理解すれば、データベース単位でバックアップとリストアを実行できる。
5. テーブルやデータベース単位でバックアップすることはできず、必ずデータベースクラスタ全体のバックアップとリストアを実行することになる。

### SQLのSETコマンドの説明として適切なものを２つ選びなさい。
	https://oss-db.jp/sample/silver_management_05/81_180115
1. 変数の値を設定し、SQLから変数値を参照することができる。
2. スキーマ検索パスや時間帯などの実行時パラメータを変更することができる。
3. 設定した値は、デフォルトでは、そのユーザにとって永続的に有効である。
4. 設定した値は、デフォルトでは、そのセッション内でのみ有効である。
5. 設定した値は、デフォルトでは、そのトランザクション内でのみ有効である

### データベースのパフォーマンスについて調べるため、SQL文とその実行に要した時間をログ出力したい。適切な方法を１つ選びなさい。
	https://oss-db.jp/sample/silver_management_04/79_171113
1. log_durationをtrueに設定すれば、SQL文と実行に要した時間がログ出力される。
2. log_min_duration_statementを0に設定すれば、SQL文と実行に要した時間がログ出力される。
3. log_statementをallに設定すれば、SQL文と実行に要した時間がログ出力される。
4. log_statement_durationをtrueに設定すれば、SQL文と実行に要した時間がログ出力される。

### パラメータ search_path の説明として適切なものを1つ選びなさい。
	https://oss-db.jp/sample/silver_management_04/78_171016
1. コマンドが検索されるディレクトリを設定する。
2. テーブルが作成されるスキーマを設定する。
3. ビューが作成されるテーブル空間を設定する。
4. インデックスが検索されるテーブル空間を設定する。
5. ストアドファンクションが検索されるデータベースを設定する。

### createuserコマンドで新規にユーザを作成するときについて、正しい説明を2つ選びなさい。
	https://oss-db.jp/sample/silver_management_04/75_170714
1. データベースのサーバプロセスを実行中のユーザと同じユーザアカウントで実行する必要がある。
2. データベースのサーバプロセスが実行されているのと同じサーバ上のユーザアカウントで実行する必要がある。
3. データベース上でCREATEROLE権限を持っているユーザに接続可能なユーザアカウントで実行する必要がある。
4. 新規に作成されるユーザ名は、OS上に存在するユーザアカウント名と同じにする必要がある。
5. 新規に作成されるユーザ名は、OS上のユーザアカウント名とは無関係に決めて良い。

### pg_ctlコマンドの説明として、正しいものを3つ選びなさい。
	https://oss-db.jp/sample/silver_management_04/74_170619
1. データベースクラスタを新規作成するには pg_ctl initdb を実行する。
2. データベースを停止するには pg_ctl shutdown を実行する。
3. データベースを再起動するには pg_ctl restart を実行する。
4. 起動や停止の対象となるデータベース名を -D オプションで指定する。
5. 停止時にデータベース接続中のセッションの処理をどうするかを -m オプションで指定する。

### PostgreSQLのデータベースクラスタについて、適切な説明を2つ選びなさい。
	https://oss-db.jp/sample/silver_management_04/72_170417
1. デフォルトでは、template0とpostgresの2つのデータベースが存在している。
2. デフォルトでは、template0とtemplate1の2つのデータベースが存在している。
3. デフォルトでは、template0とtemplate1とpostgresの3つのデータベースが存在している。
4. データベースtemplate0は削除できない。
5. データベースpostgresは削除できない。

### initdbコマンドに関する説明として適切なものを3つ選びなさい。
	https://oss-db.jp/sample/silver_management_04/71_170313
1. Linux/Unixではrootユーザで実行する。
2. 指定のディレクトリにデータベースクラスタが存在していたら、初期化されてしまうので、注意して実行する必要がある。
3. データベースのデフォルトの文字セットが指定できる。
4. データベースのデフォルトのロケールが指定できる。
5. データベースのスーパーユーザのパスワードが設定できる。

### GRANTにより付与できる権限として、間違っているものを1つ選びなさい。
	https://oss-db.jp/sample/silver_management_04/70_161205
1. テーブルの行を検索(SELECT)する権限
2. テーブルの特定の列を更新(UPDATE)する権限
3. テーブルのすべての行を削除(DELETE)する権限
4. テーブルを削除(DROP)する権限
5. テーブルに関する権限を他のユーザに付与(GRANT)する権限

### データベース内のテーブルと列に関する情報を格納するシステムカタログについて、正しい説明を1つ選びなさい。
	https://oss-db.jp/sample/silver_management_04/69_161031
1. テーブルの情報はpg_tables、列の情報はpg_columnsに格納されている。
2. テーブルの情報はpg_relations、列の情報はpg_relcolumnsに格納されている。
3. テーブルの情報はpg_class、列の情報はpg_attributeに格納されている。
4. テーブルの情報はpg_table_info、列の情報はpg_table_columnsに格納されている。
5. テーブルの情報はpg_rel_info、列の情報はpg_col_infoに格納されている。

### 自動バキュームの説明として適切なものを2つ選びなさい。
	https://oss-db.jp/sample/silver_management_04/67_160905
1. 一定時間ごとに自動的にバキュームが実行される。
2. システムの負荷が低い時に自動的にバキュームが実行される。
3. 大量のデータの挿入・更新・削除があったテーブルに対して、自動的にバキュームが実行される。
4. トランザクションIDの周回問題を回避するために、自動的にバキュームが実行される。
5. バキュームが実行されるタイミングが予測できないため、デフォルトでは実行されないようになっている。

### データベースを作成する権限のあるユーザfooを追加する方法として適切なものを2つ選びなさい。なお、以下の選択肢で、$はOSのコマンドプロンプト、=>はpsqlのコマンドプロンプトであり、コマンドを実行しているユーザには必要な権限が与えられているものとする。
	https://oss-db.jp/sample/silver_management_04/65_160711
1. $ createuser -c foo
2. $ createuser -d foo
3. $ createuser -D foo
4. => create user foo with db;
5. => create user foo createdb;

### データベースを構成するファイルシステムを物理的にコピーすることでバックアップを作成したい。最も適切な記述を1つ選びなさい。
	https://oss-db.jp/sample/silver_management_04/62_160322
1. データベースファイルは上位互換性があるので、PostgreSQL 10の環境でコピーしたファイルをPostgreSQL 11の環境にリストアして使用できる。
2. 例えば、testというテーブルを構成する物理ファイルの名前が10001だったとすると、このファイルを別のデータベース環境にコピーすれば、同じテーブルを使用できる。
3. pg_dumpで取得する論理バックアップに比べると、ファイルシステムのコピーによるバックアップは一般的に高速である。
4. pg_dumpで取得する論理バックアップに比べると、ファイルシステムのコピーによるバックアップは一般的にサイズが小さくなる。
5. バックアップの取得時、データベースは稼働中のままで良い。

### 次のコマンドについて正しい説明を2つ選びなさい。
```
	pg_dump -s -U abc -f def ghi
```
	https://oss-db.jp/sample/silver_management_04/61_160222
1. スーパーユーザーabcでデータベースに接続する。データベースファイルは上位互換性があるので、PostgreSQL 10の環境でコピーしたファイルをPostgreSQL 11の環境にリストアして使用できる。
2. データベース内のデータはダンプされない。
3. ダンプは標準出力に出力される。
4. テーブルdefがダンプされる。
5. データベースghiに接続する。

### テンプレートデータベースの説明として適切なものを2つ選びなさい。
	https://oss-db.jp/sample/silver_management_03/56_150904
1. テンプレートデータベースtemplate0内には通常のデータベースと同様にテーブルを追加できる。
2. テンプレートデータベースtemplate1内には通常のデータベースと同様にテーブルを追加できる。
3. CREATE DATABASEでデータベースを新規に作成するとき、オプションで指定しなければ、template0がテンプレートデータベースとして使用される。
4. 新規にテンプレートデータベースtemplate2を作成するためには、CREATE DATABASEコマンドの実行時にTEMPLATEオプションを付加する。
5. デフォルトでは、テンプレートデータベースtemplate0には誰も接続できない。

### Linux上でinitdbコマンドでデータベースクラスタを作成する際の注意事項として、適切なものを2つ選びなさい。
	https://oss-db.jp/sample/silver_management_03/55_150724
1. initdbは管理者ユーザで実行する必要があるので、rootユーザで実行する。
2. データベースクラスタのディレクトリは、新規のディレクトリか、既存の空のディレクトリか、のいずれかを指定する。
3. データベースクラスタのディレクトリに既存のファイルがあると、削除されてしまう。
4. データベースクラスタのディレクトリは、initdbのコマンドライン引数、あるいは環境変数PGDATAを使って指定する。
5. initdbで指定する文字セットは、クラスタ内のすべてのデータベースで共通となる。

### テーブルtestを作成した後、次の操作を行った。
```
GRANT SELECT ON test TO PUBLIC;
GRANT UPDATE ON test TO foo;
REVOKE SELECT ON test FROM foo;
```
ユーザfooがテーブルtestに関して操作する権限について適切なものを1つ選びなさい。
	https://oss-db.jp/sample/silver_management_03

1. テーブルtestを更新できるが、参照することはできない。
2. テーブルtestを参照することも更新することもできない。
3. テーブルtestを参照することはできるが、更新することはできない。
4. テーブルtestを参照することも更新することもできる。

### ANALYZEに関する記述として適切なものを2つ選びなさい。
	https://oss-db.jp/sample/silver_management_03/50_150128
1. テーブルの全データを解析するので、テーブルが大きいと時間が掛かる。
2. テーブルの排他ロックを取得するため、実行中はデータへのアクセスができなくなる。
3. ANALYZEコマンドあるいはVACUUMコマンドにより実行する。
4. 一般的に、各テーブルについて1度だけ実行すれば十分である。
5. オプション指定により、対象を、データベース内の全テーブル、あるいは、データベース内の特定のテーブルのみ、特定のテーブルの特定の列のみ、などに制限できる。

### SQLのCOPY文について、最も適切な記述を2つ選びなさい。
	https://oss-db.jp/sample/silver_management_03/48_141119
1. 標準SQLで定義されており、PostgreSQLをはじめとして、多くのRDBMSで利用できる。
2. psqlの\copyメタコマンドは、内部的にSQLのCOPY文を実行する。
3. COPY文を実行するには、データベースの管理者権限が必ず必要となる。
4. デフォルトではCSV(カンマ区切り)形式のファイルを入出力する。
5. pg_dumpコマンドで作成したテキスト形式のバックアップからリストアするとき、デフォルトではCOPY文が利用される。

### pg_dumpを使ったバックアップについて、適切な説明を2つ選びなさい。
	https://oss-db.jp/sample/silver_management_03/45_140903
1. pg_dumpの実行にはデータベースのスーパーユーザー権限が必要である。
2. テーブルのデータだけでなく、CREATE USERやCREATE ROLEで作成したユーザやロールのデータもバックアップできる。
3. テーブルのデータだけでなく、GRANTやREVOKEで付与・剥奪したテーブルへのアクセス権限もバックアップできる。
4. データはダンプせず、CREATE TABLEなどのテーブル定義だけをバックアップすることができる。
5. バイナリ形式でバックアップを作成した場合、データのリストア先は同じアーキテクチャのサーバに制限される。

### postgresql.confで設定する以下のパラメータのうち、変更を反映させるためにサーバの再起動が必要となるものを2つ選びなさい。
	https://oss-db.jp/sample/silver_management_03/43_140703
1. port
2. max_connections
3. log_connections
4. log_line_prefix
5. search_path

### PostgreSQLのユーザやロールの作成をOSのコマンドラインから実行する場合について、適切な記述を2つ選びなさい。
	https://oss-db.jp/sample/silver_management_03/42_140519
1. ユーザの作成にはcreateuser、ロールの作成にはcreateroleコマンドを使う。
2. createuserコマンドを実行するには、CREATEUSER権限が必要である。
3. -d オプション付きで実行すると、新しいユーザにデータベース作成の権限が付与される。
4. -u オプション付きで実行すると、新しいユーザにユーザ作成の権限が付与される。
5. -s オプション付きで実行すると、新しいユーザにスーパユーザ権限が付与される。

### データベースクラスタの新規作成について、正しい記述をすべて選びなさい。
	https://oss-db.jp/sample/silver_management_03/41_140415
1. psqlコマンドから、CREATE CLUSTER文を実行することで作成できる。
2. OSのコマンドプロンプトからinitdbコマンドを実行することで作成できる。
3. OSのコマンドプロンプトからpg_ctl initdbコマンドを実行することで作成できる。
4. セキュリティ上の理由から、作成されるファイルはコマンドを実行したユーザ以外には読み取り許可がない。
5. セキュリティ上の理由から、OSの管理者ユーザ(Linuxならroot)が作成すべきである。

### テーブルのアクセス権について最も適切な説明を1つ選びなさい。
	https://oss-db.jp/sample/silver_management_02/40_140414
1. CREATE TABLEで作成された直後のテーブルにアクセス権があるのは、テーブルの所有者、つまりCREATE TABLEを実行したユーザだけである。
2. テーブルのアクセス権をユーザに付与するにはALTER TABLE文を使う。
3. テーブルのアクセス権をユーザに付与できるのはテーブルの所有者だけである。
4. テーブルの所有者は、そのテーブルに基づくビューを作成する権限を各ユーザに付与、あるいは剥奪することができる。
5. テーブルの所有者であるにも関わらず、そのテーブルへのアクセス権がなく、SELECTできない、ということもあり得る。

### pg_basebackupコマンドによるバックアップについて述べたものから、適切なものを2つ選びなさい。
	https://oss-db.jp/sample/silver_management_02/37_140120
1. リストアするにはpg_restoreコマンドを利用する。
2. バックアップ作成前にデータベースを停止する。
3. ポイントインタイムリカバリ(PITR)用のベースバックアップとして利用できる。
4. レプリケーション用のベースバックアップとして利用できる。
5. データベース単位でのバックアップを取得できる。

### ANALYZEについて適切な記述を2つ選びなさい。
	https://oss-db.jp/sample/silver_management_02/32_130806
1. データベース全体を ANALYZE するには、OSのコマンドラインから pg_analyze コマンドを実行する。
2. テーブル foo について ANALYZE するには、データベースに接続して以下のコマンドを実行する。
3. ALTER TABLE foo ANALYZE;
4. OSのコマンドラインから vacuumdb コマンドを実行することでデータベース全体をANALYZEすることができる。
5. ANALYZEはテーブル内にどのようなデータが入っているかを調べる。
6. ANALYZEはテーブルが何回SELECTされ、何回UPDATEされたか、といったアクセス頻度の情報を調べる。

### pg_dumpコマンドによるデータベースのバックアップについて、誤っているものを1つ選びなさい。
	https://oss-db.jp/sample/silver_management_02/30_130422
1. データベースクラスタ内の1つのデータベースのバックアップを取得できるが、データベースクラスタ全体のバックアップは取得できない。
2. テーブルの定義だけ、テーブル内のデータだけ、テーブル定義とデータの両方、などバックアップの内容をオプションで指定できる。
3. バックアップファイルのフォーマットはテキスト形式とバイナリ形式があり、バイナリ形式にもTAR形式や圧縮アーカイブ形式など複数種類がある。
4. テキスト形式のバックアップファイルには、CREATE TABLE、GRANT、COPYといったSQL文が記述されている。
5. pg_dumpで作成したバックアップファイルからリストアするには、ファイル形式に関わらずpg_restoreコマンドを使う。

### SETコマンドで実行する設定の変更について、正しい記述を2つ選びなさい。
	https://oss-db.jp/sample/silver_management_02/27_130213
1. postgresql.conf で設定するすべてのパラメータについて、SETコマンドで値を変更できる。
2. SETコマンドでパラメータの値を変更した時、それがすぐに有効になるものと、pg_ctl reload などの追加処理をしなければ有効にならないものとがある。
3. SETコマンドでパラメータの値を変更しても、psql のセッションを終了すると、値はすべて元に戻る。
4. SET LOCAL parameter=value; のようにLOCALオプションを指定した場合、その後でCOMMITを実行すると、パラメータの値は元に戻る。
5. SETコマンドによるパラメータ値の変更はシステムに重大な影響があるため、データベースのスーパーユーザだけが実行できる。

### ポイントインタイムリカバリ(PITR)のベースバックアップの取得方法について正しいものを1つ選びなさい。
	https://oss-db.jp/sample/silver_management_02/26_130130
1. pg_dump コマンドを実行する
2. pg_dumpall コマンドを実行する
3. psql でデータベースに接続し、COPY コマンドを実行する
4. データベースを停止して、データベースクラスタ全体を tar コマンドなど OS 付属のコマンドを使ってコピーする
5. データベースを停止せずに、データベースクラスタ全体を tar コマンドなど OS 付属のコマンドを使ってコピーする

### データベースの終了方法について適切なものを2つ選びなさい。
	https://oss-db.jp/sample/silver_management_02/24_121220
1. コマンドラインから pg_ctl shutdown を実行することによりデータベースを終了できる
2. コマンドラインから pg_ctl stop を実行することによりデータベースを終了できる
3. psql でデータベースに接続し、\shutdown メタコマンドを実行することにより、データベースを終了できる
4. 終了時にオプションでsmartを指定すると、データベースに接続中のクライアントは自動的に切断され、実行中のトランザクションはロールバックされる
5. データベースの終了は、データベースの管理者ユーザ(多くの環境ではpostgres)のみが実行可能で、OSの管理者ユーザ(Linuxのroot)の権限では実行できない

### postgresql.conf で設定するパラメータについて、正しい説明を2つ選びなさい。
	https://oss-db.jp/sample/silver_management_01/19_120815
1. log_destination には、ログ出力先となるファイル名を指定する。
2. logging_collector を on にすることで、標準エラー出力に送られたログメッセージをログファイルにリダイレクトできる。
3. log_connections を on にすることで、クライアントからサーバへの接続試行がログに出力される。
4. log_statement を on にすることで、SQL 文をログに記録できる。
5. log_line_prefix を on にすることで、ログ情報の出力時刻、ユーザ名、プロセスIDなど様々な付加情報がログファイルに出力される。

### データベースクラスタ内のデータベースの一覧を調べたい。適切な方法をすべて選びなさい。なお、$ は OS のコマンドプロンプト、=> は psql のプロンプトである。
	https://oss-db.jp/sample/silver_management_01/15_120502
1. $ psql --list
2. $ pg_lsdb
3. => SELECT datname FROM pg_database;
4. => SELECT database_name FROM information_schema.databases;
5. => \list

### PostgreSQLサーバはIPアドレス 192.168.1.10 のサーバで動作しており、 pg_hba.conf の内容が以下である。
	https://oss-db.jp/sample/silver_management_01/14_120418
```
local all all ident
host all all 127.0.0.1/32 ident
host foo bar 192.168.1.0/24 md5
host all bar 192.168.1.0/24 reject
host foo all 192.168.1.0/24 trust
```
* IPアドレスが 192.168.1.11 のクライアントからこのデータベースに接続するときの記述について、選択肢の中から正しいものをすべて選びなさい。
1. ユーザ foo がデータベース bar にアクセスするときはパスワードを入力する必要がある
2. ユーザ bar がデータベース foo にアクセスするときはパスワードを入力する必要がある
3. ユーザ foo はデータベース foo にはアクセスできない
4. ユーザ bar はデータベース bar にはアクセスできない
5. ユーザ hoge はデータベース foo にパスワードなしでアクセスできる

### バキューム(VACUUM)機能に関する説明について、正しいものを2つ選びなさい。
	https://oss-db.jp/sample/silver_management_01/12_120215
1. バキュームを実行するには、コマンドラインから vacuumdb コマンドを実行する
2. 自動バキュームを実行するには、コマンドラインから autovacuumdb コマンドを実行する
3. バキュームにより削除領域が回収されると、通常はデータベースファイルのサイズが小さくなる
4. psql でデータベースに接続して VACUUM 文を実行する際、テーブル単位あるいはデータベース単位でバキュームを実行することができる
5. 自動バキュームでは、指定した時間おきに、すべてのテーブルに対してバキュームを実行する

### データベースの管理者ユーザ postgres のパスワードを忘れてしまったため、postgres ユーザでデータベースに接続できなくなった。postgres ユーザのパスワードを再設定したいがどうしたら良いか。
	https://oss-db.jp/sample/silver_management_01/10_111222
1. そのような手段はないので、データベースを新規に作成するしかない。
2. データベースの実行ファイルを再インストールすれば、パスワードはデフォルト値に戻る。
3. OS の管理者ユーザ(root)であれば、パスワードなしに postgres として接続できるので、接続後にパスワードを再設定すれば良い。
postgresql.conf の先頭に
no_password = 1
という設定を追加すれば、パスワードなしに postgres として接続できるので、接続後にパスワードを再設定すれば良い。
4. pg_hba.conf の先頭に
local all postgres ident
という設定を追加すれば、パスワードなしに postgres として接続できるので、接続後にパスワードを再設定すれば良い。

### PostgreSQL のバックアップ方法について適切なものを2つ選びなさい。
	https://oss-db.jp/sample/silver_management_01/06_110928
1. pg_dumpall コマンドで作成したバックアップファイルは、pg_restore コマンドでリストアできる。
2. pg_dump コマンドで作成したバックアップをリストアするときに使うコマンドは、バックアップ作成時のオプションによって異なる。
3. pg_dumpall コマンドでバックアップを作成する前に、データベースサーバを停止する必要がある。
4. pg_dump コマンドでバックアップを作成する際は、データベースサーバを停止する必要はない。
5. ポイントインタイムリカバリ(PITR)で使用するバックアップを作成するには、データベースサーバを停止する必要がある。

### psql でデータベースに接続している。テーブル foo の列名および列属性の一覧を表示するための適切な方法はどれか。
	https://oss-db.jp/sample/silver_management_01/05_110912
1. desc foo;
2. \d foo
3. \! foo
4. show columns from foo;
5. select * from pg_tables where tablename = 'foo';

### データベースlpijapanのバックアップをテキスト形式でbackup.sqlに取得したい。適切なコマンドを2つ選びなさい。ただし、postgresはデータベースの管理者ユーザである。
	https://oss-db.jp/sample/silver_management_01/02_120210
1. pg_dump -U postgres lpijapan > backup.sql
2. pg_dump -U postgres -f backup.sql lpijapan
3. pg_dump -U postgres -Ft lpijapan > backup.sql
4. psql -U postgres lpijapan > backup.sql
5. psql -U postgres --dump lpijapan > backup.sql

## 開発/SQL（32％）
### PostgreSQLのバージョン10からサポートされた宣言的パーティショニングと、従来のバージョンからサポートされている継承を利用したパーティショニングの説明として、適切なものを３つ選びなさい。なお、親テーブルの名前は parent、パーティションの名前は partition1, partition2, partition3… だとします。
	https://oss-db.jp/sample/silver_development_06/105_190731
1. どちらの方法でも、親テーブルの作成は通常の CREATE TABLE parent… で行い、パーティションを使うための特別なオプション指定は必要ない。
2. パーティションを作成するときのコマンドは、宣言的パーティショニングでは CREATE TABLE partition1 PARTITION OF parent… 継承を利用する場合は CREATE TABLE partition1 () INHERITS (parent) で、どちらもCREATE TABLEを使用する。
3. どちらの方法でも、INSERT文の実行時にデータの格納先となるパーティションが自動的に作成することはなく、事前にパーティションを作成しておく必要がある。
4. どちらの方法でも、親テーブルとパーティションを適切なCREATEコマンドで作成しておけば、 INSERT INTO parent… で挿入するデータは自動的に適切なパーティションに格納される。
5. 宣言的パーティショニングではすべてのパーティションは同じ列を持っていて、異なる列を追加できないが、継承を利用したパーティショニングでは、パーティションごとに異なる列を追加できる。

### PostgreSQLのバージョン11で追加されたプロシージャ(PROCEDURE)と、従来のバージョンからサポートされている関数(FUNCTION)の違いの説明として適切なものを2つ選びなさい。
	https://oss-db.jp/sample/silver_development_06/103_190626
1. PROCEDURE は CREATE PROCEDURE コマンドで、FUNCTION は CREATE FUNCTION コマンドで作成する。
2. PROCEDURE は標準 SQL で定義されているが、FUNCTION は PostgreSQL 独自の拡張機能である。
3. void型の FUNCTION は廃止予定であり、PROCEDURE に置き換えることが推奨されている。
4. FUNCTION は SELECT func_name(arg1, arg2...) のようにして実行するのに対し、PROCEDURE
は CALL proc_name(arg1, arg2...) のようにして実行する。
5. PROCEDUREはデータベース内のデータを更新できるが、FUNCTIONはデータに基づいた計算をするだけで、データの更新はできない。

### 現在時刻を返す関数 current_timestamp の select を以下のように連続して2回実行した。
```
select current_timestamp;
select current_timestamp;
```
* このとき、2回とも同じ値が返った。考えられる理由として最も適切なものを選びなさい。
	https://oss-db.jp/sample/silver_development_06/102_190612
1. サーバマシンのハードウェアクロックが故障している。
2. サーバマシンで timed を実行していないため、時刻が正確に保たれていない。
3. 2つのSELECT文を間を空けず、連続して素早く実行したため、同じ時刻が返った。
4. これらのSELECTを実行する直前に BEGIN コマンドを実行していた。
5. 同じセッション内から実行すれば、current_timestamp は必ず同じ値を返す。

### 
	https://oss-db.jp/sample/silver_development_06/101_190529
```
CREATE TABLE table1(列定義)  PARTITION BY…
CREATE TABLE partition1 PARTITION OF table1 FOR VALUES…
CREATE TABLE partition2 PARTITION OF table1 FOR VALUES…
…
```
の手順でパーティションテーブルを作成した。このときの動作として正しいものを1つ選びなさい。

1. テーブルへのINSERTで適切な挿入先となるパーティションが作成されていない場合、自動的に新しいパーティションが作成され、そこにデータが挿入される。
2. UPDATEの結果、そのデータが別のパーティションに移ることになる場合は、エラーとなって実行されない。
3. table1にインデックスを作成すれば、それがすべてのパーティションに適用される。
4. table1に行トリガーを作成すれば、それがすべてのパーティションに適用される。
5. 一旦作成したパーティションpartition1は、パーティションが空でなければ削除できない。

### テーブルのパーティショニングを使うことで得られる可能性のある利点として、適切なものを選びなさい。
	https://oss-db.jp/sample/silver_development_05/100_190515
1. データが占めるディスク容量を削減する。
2. 問い合わせの性能を大幅に向上させる。
3. 頻繁にアクセスする行と、そうでない行を、別のディスク領域に配置する。
4. 頻繁にアクセスする列と、そうでない列を、別のディスク領域に配置する。
5. DELETEの代わりにDROP TABLEを実行して、大量データの一括削除を高速化する。

### テーブルスペース(tablespace)の使用方法として正しいものを３つ選びなさい。
	https://oss-db.jp/sample/silver_development_05/99_190423
1. CREATE DATABASE で作成する新しいデータベースを、デフォルトとは異なるテーブルスペースに配置する。
2. CREATE SCHEMA で作成する新しいスキーマを、デフォルトとは異なるテーブルスペースに配置する。
3. CREATE TABLE で作成する新しいテーブルを、デフォルトとは異なるテーブルスペースに配置する。
4. CREATE VIEW で作成する新しいビューを、元となるテーブルとは異なるテーブルスペースに配置する。
5. CREATE INDEX で作成する新しいインデックスを、元となるテーブルとは異なるテーブルスペースに配置する。

### テーブルxxxの主キー列はinteger型のid、テーブルyyyの主キー列はinteger型のidである。xxxとyyyの両方に同じidの行がある場合に、それらの行をすべてxxxから削除したい。例えば、select id from xxx  が1と2と3、select id from yyy が2と3と4を返したとして、idが2の行と3の行をxxxから削除する。これを実現するSQLはどれか。
	https://oss-db.jp/sample/silver_development_05/97_190328
1. DELETE FROM xxx, yyy WHERE xxx.id = yyy.id;
2. DELETE FROM xxx, yyy WHERE xxx.id IN (yyy.id);
3. DELETE FROM xxx JOIN yyy USING xxx.id = yyy.id;
4. DELETE FROM xxx WHERE id IN (SELECT id FROM yyy);
5. DELETE FROM xxx WHERE EXISTS (SELECT id FROM yyy);

### 以下のSQLを順次実行した。
	https://oss-db.jp/sample/silver_development_05/95_190129
```
CREATE TABLE foo (id INTEGER PRIMARY KEY, val VARCHAR);
INSERT INTO foo (id, val) VALUES (1, 'a'), (2, 'b'), (3, 'c');
INSERT INTO foo (id, val) VALUES (3, 'x'), (4, 'y'), (5, 'z');
```
* このとき、テーブルfooには何行のデータが含まれるか。

### トランザクション内でLOCK TABLE sample;を実行し、テーブルsampleの排他ロックを取得した。このロックが解放されるのはどういう場合か。正しいものを3つ選びなさい。
	https://oss-db.jp/sample/silver_development_05/91_180925
1. COMMIT; を実行したとき。
2. RELEASE TABLE sample; を実行したとき。
3. ROLLBACK; を実行したとき。
4. UNLOCK TABLE sample; を実行したとき。
5. Ctrl+Dあるいは \q を入力して psql のセッションを終了したとき。

### 反復不能読み取り(nonrepeatable read)の説明として適切なものを2つ選びなさい。
	https://oss-db.jp/sample/silver_development_05/90_180828
1. 他のトランザクションがまだコミットしていないデータを読み取る。
2. 同じ問い合わせを繰り返し実行したときに、返される行の数が前と異なる。
3. 同じデータを繰り返し読んだときに、データの内容が前と異なる。
4. トランザクション分離レベルをシリアライザブル(serializable)にしたら発生しない。
5. トランザクション分離レベルをリードコミッティド(read committed)にしたら発生しない。

### トランザクションの開始、終了に使用される文として間違っているものを1つ選びなさい。
	https://oss-db.jp/sample/silver_development_05/89_180724
1. BEGIN
2. COMMIT
3. ROLLBACK
4. START TRANSACTION
5. STOP TRANSACTION

### テーブルxxの文字列型の列aaの3文字目から6文字目までの4文字を取得するSQL文として適切なものをすべて選びなさい。
	https://oss-db.jp/sample/silver_development_05/87_180528
1. SELECT substring(aa, 3, 4) FROM xx;
2. SELECT substring(aa, 3, 6) FROM xx;
3. SELECT substring(aa from 3 to 6) FROM xx;
4. SELECT substring(aa from 3 for 4) FROM xx;
5. SELECT substring(aa, 4 from 3) FROM xx;

### 次のPL/pgSQLの関数は、テーブルtestのsome_columnの値が引数valより大きい行の数を返すものである。空欄（ _____ ）に入るキーワードは何か。
	https://oss-db.jp/sample/silver_development_05/84_180226
```
CREATE FUNCTION count_test(val INTEGER) RETURNS INTEGER AS
DECLARE
rtest RECORD;
cnt INTEGER;
BEGIN
cnt := 0;
FOR rtest IN SELECT * FROM test WHERE some_column > val LOOP
cnt := cnt + 1;
（ ________ ）;
RETURN cnt;
END;
LANGUAGE plpgsql;
```

### DROP SCHEMA foo の結果として適切なものを１つ選びなさい。
	https://oss-db.jp/sample/silver_development_05/83_180129
1. PostgreSQLには DROP SCHEMA コマンドが存在しないのでエラーになる。スキーマを削除するにはDROP USER foo を実行する。
2. ユーザ foo が存在していたらエラーになる。
3. スキーマ foo 内にオブジェクトが存在していたら、エラーになる。
4. スキーマ foo 内にオブジェクトが存在していたら、自動的に publicに移動される。
5. スキーマ foo と、その中に存在するオブジェクトすべてが削除される。

### 以下のSQL文を実行した。CREATE TABLE test (id SERIAL, val TEXT); これについて正しい説明をすべて選びなさい。
	https://oss-db.jp/sample/silver_development_05/82_171225
1. id列には自動的にNOT NULL制約が付与される。
2. id列には自動的にUNIQUE制約が付与される。
3. id列には自動的にインデックスが作成される。
4. id列の値をUPDATE文で更新することはできない。
5. INSERT文でid列の値をNULLと指定するとエラーになる。

### あるテーブルに、文レベルのBEFORE INSERTトリガーを2つ定義した。この場合の動作について正しいものを選びなさい。
	https://oss-db.jp/sample/silver_development_05/81_171127
1. 1つ目のトリガーのみが実行される。
2. 2つ目のトリガーのみが実行される。
3. 1つ目のトリガー、2つ目のトリガーの順で両方が実行される。
4. 2つ目のトリガー、1つ目のトリガーの順で両方が実行される。
5. 両方のトリガーが実行されるが、どちらが先かは場合による。

### id列を主キーとするテーブルを作成する正しい方法を2つ選びなさい。
	https://oss-db.jp/sample/silver_development_04/79_171002
1. CREATE TABLE test (PRIMARY KEY id INTEGER, value TEXT);
2. CREATE TABLE test (id INTEGER PRIMARY KEY, value TEXT);
3. CREATE TABLE test (id INTEGER, value TEXT, PRIMARY KEY=id);
4. CREATE TABLE test (id INTEGER, value TEXT, PRIMARY KEY id);
4. CREATE TABLE test (id INTEGER, value TEXT, PRIMARY KEY (id));

### 以下の一連のSQL文でテーブルを作成し、データを挿入、更新した。
```
create table sample (id integer, vali integer, vals text);
insert into sample (id, vali, vals) values (1, null, 'a'), (2, 2, 'b'), (3, 3, 'c'), (4, 4, 'd'), (5, 5, null);
update sample set vali = vali -1;
update sample set vals = 'x' where vali <= 2;
update sample set vali = 10 where vals <> 'x';
select sum(vali) from sample;
```
* 最後のSELECT文が返す値は何か。

### PostgreSQLのトランザクション分離レベルの説明として、適切なものを2つ選びなさい。
	https://oss-db.jp/sample/silver_development_04/73_170403
1. Read Uncommittedでは、他のトランザクションが更新した後、まだcommitしていないデータを読めてしまう。
2. Read Committedでは、トランザクション内で同じSELECT文を2回続けて実行しても、異なる結果が返されることがある。
3. Repeatable Readでは、トランザクション内で同じSELECT文を2回続けて実行したら、必ず同じ結果が返される。
4. Serializableは読み取りトランザクション専用の分離レベルである。

### テーブルtblの列str1とstr2はいずれもTEXT型である。str1の先頭の1文字とstr2を結合する、例えばstr1が’ABC’、str2が’XYZ’なら’AXYZ’という文字列を取得するには、次のSQLの空欄に何を入れれば良いか。
```
SELECT ________ FROM tbl;
```
* 適切なものを2つ選びなさい。
1. substring(str1,1,1) + str2
2. substring(str1,1) || str2
3. concat(substring(str1 from 1 for 1), str2)
4. substring(str1 from 1) + str2
5. concat(substring(str1 for 1), str2)

### 10を3で割り算した時の剰余(余り、この場合は1になる)を求めるものとして、適切なものをすべて選びなさい。
	https://oss-db.jp/sample/silver_development_04/68_161017
1. select 10 mod 3;
2. select mod(10, 3);
3. select 10 % 3;
4. select %(10, 3);

### 以下の一連のSQL文を実行した。
	https://oss-db.jp/sample/silver_development_04/67_160920
```
CREATE TABLE test (x INTEGER);
INSERT INTO test(x) VALUES (null), (1), (2), (3);
SELECT sum(2) FROM test;
```
* 最後のSELECT文が返す値は何か。数値を答えよ。

### 次のコマンドで新しいシーケンスを作成した。
	https://oss-db.jp/sample/silver_development_04/64_160627
```
CREATE SEQUENCE seq_test MINVALUE 1;
```
* ここで、次のSELECT文を実行したら何が起きるか。
```
SELECT * FROM seq_test;
```
* 適切なものを1つ選びなさい。
1. seq_testはテーブルではなくてシーケンスなので、エラーとなる。
2. 既存のテーブルseq_testが存在すればその内容が表示され、なければテーブルが見つからないというエラーになる。
3. シーケンスseq_testの現在値である1が返される。
4. シーケンスseq_testに関する様々な属性値が返される。

### INSERT INTO foo (n) VALUES (3);というINSERT文が実行された時に、テーブルfooではなく、テーブルbarにINSERTされる、つまり内部的に　INSERT INTO bar (n) VALUES (3);が実行されるようにしたい。CREATE RULE foobar AS ON INSERT TO foo DO INSTEAD INSERT INTO bar (n) VALUES (___.n);というルールを作成することで、これが実現できるが、下線部に入る文字列は何か。
	https://oss-db.jp/sample/silver_development_04/63_160516

### 更新可能ビューの説明として間違っているものを1つ選びなさい。
	https://oss-db.jp/sample/silver_development_04/62_160406
1. 元となるSELECT文のFROM句に複数のテーブルが記述されているビューは更新できない。
2. 元となるSELECT文のFROM句に記述されているテーブルに主キーが定義されていない場合、そのビューは更新できない。
3. 元となるSELECT文がSUMなどの集約関数を使っているビューは更新できない。
4. 元となるSELECT文が複数のSELECT文のUNIONになっているビューは更新できない。
5. ビューにINSERTできた行が、SELECTで参照できるとは限らない。

### インデックスについて間違った説明を1つ選びなさい。
	https://oss-db.jp/sample/silver_development_04/61_160307
1. 列にPRIMARY KEYの制約をつけると、自動的にインデックスが作成される。
2. 列にUNIQUEの制約をつけると、自動的にインデックスが作成される。
3. 列にNOT NULLの制約をつけると、自動的にインデックスが作成される。
4. 列にUNIQUEの制約がなくても、インデックスをUNIQUEとして作成することができる。
5. デフォルトではB-treeインデックスが作成される。

### 行やテーブルのロックに関して、適切な記述を1つ選びなさい。
	https://oss-db.jp/sample/silver_development_03/57_151029
1. トランザクションブロック内でUPDATE文を実行すると、更新対象の行は自動的にロックされる。
2. トランザクションブロック内で、テーブル内のすべての行を更新するUPDATE文を実行すると、自動的にテーブルロックがかかる。
3. テーブルロックは行ロックより優先するので、別のユーザがテーブル内のデータに行ロックをしていても、LOCK TABLEでテーブル全体をロックすることができる。
4. ACCESS EXCLUSIVEモード(LOCK TABLEのデフォルト)でテーブルロックが掛かっている場合、そのテーブルをUPDATE文で更新できるのは、データベースの管理者ユーザに限られる。
5. 2人のユーザが同じテーブルの同じ行を同時に更新しようとすると、デッドロックが発生する。

### テーブルhumanの列heightには身長、weightには体重がそれぞれNUMERIC型で入っている。 それぞれの行のデータについてBMIを求めるSELECT文として正しいものをすべて選びなさい。なお、BMIは体重を身長の2乗で割ったものです。
	https://oss-db.jp/sample/silver_development_03/53_150612
1. SELECT weight / height / height FROM human;
2. SELECT weght / height * height FROM human;
3. SELECT weight / height ^ 2 FROM human;
4. SELECT weight / height ** 2 FROM human;
5. SELECT weight / power(height, 2) FROM human;

### 関数定義について適切な記述を2つ選びなさい。
	https://oss-db.jp/sample/silver_development_03/51_150324
1. 値を返す関数のプログラムを定義する時はCREATE FUNCTION文を使う。
2. 値を返さない関数のプログラムを定義する時はCREATE PROCEDURE文を使う。
3. 定義済みの関数のプログラムを変更する時は、新しいプログラムをALTER FUNCTION文により設定する。
4. 関数の名前はスキーマ内で一意でなければならない。
5. 関数は必ずしもPL/pgSQLのような手続き言語で作成する必要はなく、SELECT文やUPDATE文などのSQLで記述することもできる。

### PostgreSQLにおけるスキーマについて、適切な記述を2つ選びなさい。
	https://oss-db.jp/sample/silver_development_03/50_150128
1. テーブル名の指定などでスキーマ名を省略すると、defaultという名前のスキーマを指定したものとみなされる。
2. あるスキーマにテーブルを新規に作成するには、そのスキーマに対するCREATE権限が必要である。
3. スキーマを新規に作成するには、データベースに対するCREATE権限が必要である。
4. スキーマの所有者はそのスキーマと同じ名前のユーザである。
5. スキーマの下にスキーマを作成することで、最大32階層までのスキーマを作成できる。

### PostgreSQLのトリガー機能について、適切な記述を2つ選びなさい。
	https://oss-db.jp/sample/silver_development_03/48_141030
1. SELECT文やINSERT文の実行の前に、トリガーとして定義したプログラムが実行される。
2. CREATE TRIGGER文の中で、PL/pgSQLを使ってトリガーのコードを定義する。
3. PL/pgSQLに限らず、PL/Perlなど、他の手続き言語でもトリガーを定義できる。
4. ビューにトリガーを定義して、ビューを更新することができる。
5. 1つのテーブルの1つのイベント(例えば、BEFORE INSERT FOR EACH ROW)に定義できるトリガーは1つだけである。

### ビュー(view)に関する説明として最も適切なものを2つ選びなさい。
	https://oss-db.jp/sample/silver_development_03/47_141030
1. ビューに対するSELECT権限があっても、そのビューを構成するテーブルに対するSELECT権限がなければ、ビューからデータをSELECTすることはできない。
2. ビューを作成するには、そのビューを構成するテーブルあるいはテーブルの列に対するCREATE VIEW権限が必要である。
3. 既存のテーブルと同じ名前のビューを作ることはできない。
4. PostgreSQLの以前のバージョンでは、ビューの更新にはトリガー(trigger)あるいはルール(rule)を定義する必要があったが、バージョン9.3以降では、(ビューの定義によっては)トリガーやルールが定義されていないくても更新が可能である。
5. ビューからの検索を高速にするために、ビューに対してインデックスを作成することができる。

### 以下のSQL文でテーブルを作成した。
```
CREATE TABLE sample (id INTEGER, val TEXT);
```
* このテーブルのid列に一意のインデックスを作成したい。以下のSQL文で適切なものを2つ選びなさい。
	https://oss-db.jp/sample/silver_development_03/46_141001
1. ALTER TABLE sample ADD UNIQUE INDEX ON id;
2. ALTER TABLE sample ALTER COLUMN id UNIQUE;
3. ALTER TABLE sample ADD UNIQUE(id);
4. CREATE UNIQUE INDEX ON sample(id);
5. CREATE INDEX sample_id_unique ON sample(id);

### 論理値型(BOOLEAN型)に関する適切な記述を2つ選びなさい。
	https://oss-db.jp/sample/silver_development_03/44_140812
1. 論理値型の列の値としては、キーワードのTRUEとFALSEの他に、文字列の’YES’と’NO’、整数の1と0などを設定することができる。
2. FALSEとNULLは同等である。
3. SELECT文で値を表示すると、INSERTやUPDATEでの設定で使った値に関わらず、tあるいはfと表示される。
4. 実体は整数型の列で代用されているので、0以外の値は何を設定しても真であるとみなされる。
5. bo が論理値型の列だとして、それが真である行を検索する場合、
SELECT * FROM table_name WHERE bo;
と書けば良い。

### 次のDDLでテーブルtestを作成した。このテーブルのval列についての説明から適切なものを1つ選びなさい。
	https://oss-db.jp/sample/silver_development_02/33_131008
```
CREATE TABLE test(id INTEGER, val VARCHAR(10));
```
1. INSERT INTO test(val) VALUES(‘ABCDEFG’);
を実行したが、7文字しかないので空白3文字が自動的に追加され、val列には’ABCDEFG ‘という値が保存された。
2. INSERT INTO test(val) VALUES(’ABCDEFGHIJKL’);
を実行したが、11文字目以降は自動的に切り捨てられ、val列には’ABCDEFGHIJ’という値が保存された。
3. INSERT INTO test(val) VALUES(’あいうえお’);
を実行したが、サーバの文字コードがUTF8であり、これは15バイトの長さだったため、val列には’あいう’(9バイト)という値が保存された。
4. INSERT INTO test(val) VALUES(123); を実行したら、val列には’123’という文字列が保存された。
5. UPDATE test SET val = id; を実行したが、文法エラーとなった。

### 以下の一連のSQL文を実行した。
	https://oss-db.jp/sample/silver_development_02/29_130227
```
CREATE TABLE test(id INTEGER, val TEXT);
INSERT INTO test VALUES (1, ‘あいうえお’);
SELECT char_length(val) FROM test WHERE id = 1;
```
* 最後のSELECT文が返すデータについて、以下の説明から正しいものを1つ選びなさい。
1. 関数の使い方が正しくないのでエラーになる。
2. WHERE条件にマッチする行がないので、何も返らない。
3. char_length関数は文字数を返すので5が返る。
4. char_length関数はサーバー側の文字列のバイト数を返すので、サーバーの文字セットがEUCであれば10が、UTF8であれば15が返る。
5. char_length関数はクライアント側の文字列のバイト数を返すので、クライアントの文字セットがEUCやSJISであれば10が、UTF8であれば15が返る。

### テーブルに関する以下の説明について正しいものを2つ選びなさい。
	https://oss-db.jp/sample/silver_development_02/28_130227
1. テーブルを新しく作成するにはCREATETABLE権限が必要である。
2. ALTER TABLEでテーブルにUNIQUE制約を追加することはできるが、PRIMARY KEY制約を追加することはできない。
3. ALTER TABLEでテーブルの列にデフォルト値(DEFAULT)を設定あるいは変更することができるが、これにより既存のデータの列の値が変更されることはない。
4. テーブルの作成先のスキーマが何であろうと、テーブルを作成したユーザ、つまりCREATE TABLEを実行したユーザが、そのテーブルの所有者となる。
5. テーブルの所有者はそのテーブルに関するすべての権限を有しているので、自分自身についてテーブルのSELECT権を剥奪(REVOKE)しても、引き続き、そのテーブルからSELECTすることができる。

### PostgreSQLのデータ型について正しい説明を2つ選びなさい。
	https://oss-db.jp/sample/silver_development_02/27_130227
1. 整数型には2バイトのSHORT、4バイトのINT、8バイトのLONGがある。
2. 整数あるいは小数を10進数で表すには、NUMBER型あるいはNUMERIC型を利用できる。
3. 可変長の文字列を表すVARCHAR型およびCHARACTER VARYING型では、その最大長をバイト単位で指定する。
4. 日付を表すDATE型には時刻の情報が含まれない。時刻を表すTIME型には日付の情報が含まれない。TIMESTAMP型には日付と時刻の両方の情報が含まれる。
5. 論理値型のBOOLEANでは真偽を表すのにTRUE、FALSEというキーワードを利用できるほか、'y', 'n', 't', 'f', '1', '0' といった文字列も利用できる。

### PostgreSQLのスキーマについて、最も適切な記述を2つ選びなさい。
	https://oss-db.jp/sample/silver_development_02/25_130220
1. すべてのテーブルはいずれかのスキーマに所属する。
2. スキーマは階層化できるので、SELECT * FROM schemax.subschema1.subschema2.tablename;のように深いスキーマのテーブルからSELECTすることもあり得る。
3. SELECT * FROM tablename; のようにスキーマ名を指定せずにテーブル名を指定すると、publicスキーマを指定したものと見なされる。
4. SELECT * FROM tablename; のようにスキーマ名を指定せずにテーブル名を指定すると、ユーザ名と同じ名前のスキーマを指定したものと見なされる。
5. ALTER SCHEMA文でスキーマの名前や所有者を変更することができる。

### 次のような2つのテーブル t1 と t2 がある。
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
いずれも、id列はINTEGER型、val列はTEXT型である。
次のSELECT文を実行した時に返される行数はいくつか。

select * from t1 full join t2 using (id);
```
	https://oss-db.jp/sample/silver_development_02/24_130124
1. 1行
2. 2行
3. 3行
4. 4行
5. 5行

### psqlでデータベースに接続し、次の一連のSQLを実行した。
	https://oss-db.jp/sample/silver_development_02/23_130110
```
CREATE TABLE test (id INTEGER, val TEXT);
START TRANSACTION;
INSERT INTO test (id, val) VALUES (1, ‘abc’);
INSERT INTO test (idd, val) VALUES (2, ‘pqr’);
INSERT INTO test (id, val) VALUES (3, ‘xyz’);
COMMIT;

2つ目のINSERTで、id とすべきところを間違って idd としてしまったため、エラーになった。最後のCOMMITを実行した後の状態について正しく述べているものを2つ選びなさい。
```
1. test表にはデータが1行もない
2. test表にはデータが1行だけある
3. test表にはデータが2行ある
4. COMMITはエラーを起こす
5. COMMITは正常終了する

### 2つのクライアント(AとBとします)が同じテーブルTを更新するためにロックを取得しようとしています。以下の記述から正しいものを2つ選択しなさい。
	https://oss-db.jp/sample/silver_development_01/19_121011
1. クライアントAは行Xを更新するために行ロックを取得した。クライアントBも同じ行Xを更新したいが、行ロックを取得できないのでクライアントAの処理が終わるまで待たされる。
2. クライアントAは行Xを更新するために行ロックを取得した。クライアントBはこれと異なる行Yを更新したいが、YがたまたまXと同じデータブロックにあったので、行ロックは取得できず、クライアントAの処理が終わるまで待たされた。log_connections を on にすることで、クライアントからサーバへの接続試行がログに出力される。
3. クライアントAはテーブルTの50％の行を更新するために、それらの行のロックを取得したところ、ロックエスカレーションが発生して自動的にテーブルロックに移行した。このためクライアントBは同じテーブルTのどの行も更新できなくなった。
4. クライアントAはテーブルTのすべての行を独占的に更新するため LOCK TABLE T;により、ACCESS EXCLUSIVEモードでのロックを取得した。このロックが解放されるまで、クライアントBはテーブルTを更新できないが、SELECTだけなら実行できる。
5. クライアントAはテーブルTの行Xを更新するためにロックを取得した。クライアントBは同じテーブルTのテーブルロックを取得するために LOCK TABLE T; を実行したが、これはAが取得した行ロックが解放されるまで待たされる。

### あるクライアントで次の一連のSQLを実行する。
	https://oss-db.jp/sample/silver_development_01/15_120405
```
BEGIN;
UPDATE table1 SET val1 = 100 WHERE id1 = 1;
UPDATE table1 SET val1 = 200 WHERE id1 = 2;
UPDATE table2 SET val2 = 300 WHERE id2 = 3;
COMMIT;

別のクライアントから、これとほぼ同時に実行したときに、デッドロックが発生する可能性のあるトランザクションはどれか。A～Eの選択肢から2つ選択せよ。
```
1. 
```
BEGIN;
INSERT INTO table2 (id2, val2) VALUES (4, 40);
UPDATE table1 SET val1 = 1000 WHERE id1 = 1;
COMMIT;
```
2. 
```
BEGIN;
UPDATE table1 SET val1 = 1000 WHERE id1 = 1;
UPDATE table2 SET val2 = 3000 WHERE id2 = 3;
COMMIT;
```
3. 
```
BEGIN;
UPDATE table2 SET val2 = 3000 WHERE id2 = 3;
UPDATE table1 SET val1 = 1000 WHERE id1 = 1;
COMMIT;
```
4. 
```
BEGIN;
UPDATE table1 SET val1 = 1000 WHERE id1 = 1;
UPDATE table1 SET val1 = 2000 WHERE id1 = 2;
COMMIT;
```
5. 
```
BEGIN;
UPDATE table1 SET val1 = 2000 WHERE id1 = 2;
DELETE FROM table1 WHERE id1 = 1;
COMMIT;
```

### 次の SQL 文のうち、エラーにならないものを2つ選びなさい。
	https://oss-db.jp/sample/silver_development_01/14_120223
1. SELECT current_date();
2. SELECT current_time();
3. SELECT current_time(2);
4. SELECT current_timestamp();
5. SELECT now();

### 以下の SQL 文でテーブルを作成し、多数の行を挿入した。
	https://oss-db.jp/sample/silver_development_01/09_111125
```
CREATE TABLE table1 (id INTEGER, name VARCHAR(20), sales INTEGER);

ここで、id が 30 以下のすべてのデータについて、sales の値を NULL にしたい。
正しい SQL 文を選びなさい。
```
1. SELECT sales = NULL FROM table1 WHERE id <= 30;
2. UPDATE sales = NULL FROM table1 WHERE id < 31;
3. DELETE sales FROM table1 WHERE id <= 30;
4. UPDATE table1 SET sales = NULL WHERE id < 31;
5. UPDATE table1.sales = NULL WHERE id <= 30;

### 次のSQL文で表を作成した後、多数の行をINSERTした。
	https://oss-db.jp/sample/silver_development_01/06_111005
```
CREATE TABLE foo (id INTEGER, val VARCHAR(50));

この表で val 列の2文字目と3文字目がいずれも A である行をすべて検索したい。
誤っているものを1つ選びなさい。
```
1. SELECT * FROM foo WHERE val LIKE '_AA%';
2. SELECT * FROM foo WHERE val ~ '^.AA';
3. SELECT * FROM foo WHERE substring(val, 2, 2) = 'AA';
4. SELECT * FROM foo WHERE substring(val from 2 for 2) = 'AA';
5. SELECT * FROM foo WHERE position('AA' in val) = 2;

### 
### 
### 