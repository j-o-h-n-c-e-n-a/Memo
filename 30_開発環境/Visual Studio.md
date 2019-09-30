# Visual Studio 2015　での開発実施について
	残念ながら、VS2017を検証した結果、本格的には開発に利用できそうにないため
	本活動においては採用を見送り、Visual Studio 2015で取りあえず開発をスタートすることとした。
	採用するコア技術としては、「ASP.net MVC 5」となる。

## HTMLヘルパーの使い所
	将来のHTML5への移行を考えると、サーバーサイドでHTMLを生成するような処理を多く組み込むことは控えたい。
	特にモデルから画面を生成した場合、「Html.EditorFor」は非常に強力なヘルパーとなり、
	モデルの内容によって自在にその形を変化させてくれる。
	その結果、デザインの自由がきかなくなってしまうデメリットがあり、
	このことが将来のHTML5への移行の妨げとなるからである。
	よって、HTMLヘルパーは極力使用しない方向で考えたい。
* [参考リンク](：http://www.buildinsider.net/web/bookaspmvc5/040401)

## 取りあえず何から始める？
* モデルから（モデルファースト）
	+ 「Entity Framework」を使う。
	+ 「PostgreSQL」がDBの場合、「Npgsql」が必要。
		-	「Npgsql」は「Nuget」より取得する。
	+ 今回は、「Npgsql」の利用が上手くいかず、時間もない為、使わない。
* データベースから（データベースファースト）
	+ 「ODBC」を利用した、Excelマクロからデータベースの内容を取得。コードを生成する。
		-	部門システムのバージョンアップの際に採用した手法。
		-	今回もこの手法にて製作をしている。
* コードから（コードファースト）
	+ 最初からDTOクラスなどを手入力で作成してしまう。
		-	リレーションを考慮しないと後々ビュー作成が上手くできないので、注意すること。
		-	ある程度「ASP.net MVC」に慣れないと、難しい。

## パッケージについて
	下記のパッケージを追加している。
*	[bootstrap-treeview](http://jonmiles.github.io/bootstrap-treeview/)

## 今後の計画
	今後、VS2017に切り替えることとする。

### 切替に当たり、将来的にバージョンアップされるであろうパッケージ
* bootstrap
	+ 3.x ⇒ 4.x
	+ 4系統に変わることで、レイアウトの作成方法が大幅に変更となるので作業負担は大きい。
	+ メリット①：IE8系が切り捨てられ、応答速度が改善している。
* .net Framework
	+ 4.6 ⇒ core
	+ core になることで、MVCの作成方法が大幅に変更となるので作業負担は大きい。
	+ メリット①：IE8系が切り捨てられ、応答速度が改善している。
	+ メリット②：IISのみ動作可能となっていたWebサーバーが、Linux系でも動作可能となる。これにより、Window Serverが不要となる。
* typeScript
	下記対象のライブラリが置き換え出来る模様。（作業負担はそうでもない思われる）
	+ Bootstrap
	+ jquery
	+ jquery-validation
	+ knockoutJS
	+ modernizr

# Visual Studio 2017 検証（仮）
	まだRC版なので機能がかなり不足しているが、今後を見据えて導入し、開発利用に関して検証した。
## 「asp.net MVC(VB)」プロジェクトの作成
	-	「新しいプロジェクト」より、「テンプレート」→「Visual Basic」→「Web」→「MVC」と選択する。
		この場合、.net Frameworkはver.4.6.2、ASP.NET MVCはver.5.xとなり、.net Core 1.x とは異なるバージョンとなる。
	-	.net Core のテンプレートを利用したい場合、「Visual C#」を選択する必要がある。
		（VBはそのうち対応との事。正式版ができる頃には対応済になっている？）

## 「asp.net MVC(VB)」アプリケーションの初期配置
### 解説
*	App_Start フォルダ
	-	アプリケーション起動時の動作を記述。
	+	BundleConfig.vb
		-	ここで設定した複数のJS等のファイルを1つにまとめる作業を半自動的に行ってくれる。
	+	FilterConfig.vb
		-	アクセスされたURLに対して、実行されるアクションメソッドについて、
			認証・例外などの処理を追加する。
	+	IdentityConfig.vb
		-	ユーザー情報の初期化とセッションへの格納を担当。
	+	RouteConfig.vb
		-	アクセスされたURLに対して、どのようにコントローラを割り当てるかを定義。
	+	StartupAuth.vb
		-	ユーザー認証情報の初期化。
*	Content フォルダ
	-	主に「CSS」ファイルを配置。
	+	bootstrap
		-	画面デザイン用フレームワーク。
	+	Site
		-	システム独自設定用CSS。
*	Controllers フォルダ
	-	MVCの「Controller」を担当。
		ここに画面遷移（ビューの表示）や業務ロジック（モデル）呼び出し処理を配置。
*	fonts フォルダ
	-	各画面のフォントを配置。
		何故かこれだけ「Content」フォルダから外に出ている。
*	Models フォルダ
	-	MVCの「Model」を担当。
		ここに業務ロジックを配置する。
*	Scripts フォルダ
	-	システムで使用するScriptファイルを配置。
	+	bootstrap : version-3.0.0
		-	画面デザイン用フレームワークのScript部分。
	+	jquery : version-1.10.2
		-	javascriptのフレームワーク。
	+	jquery.validate
		-	javascriptで入力判定を支援する、ライブラリ。
	+	modemizr : version-2.6.2
		-	ブラウザ毎のScript処理の違いを判定してくれる、ライブラリ。
	+	respond
		-	IE８以下のブラウザでレスポンシブWEBデザインを実現してくれる、ライブラリ。
*	Views フォルダ
	-	MVCの「View」を担当。ここに各画面を配置。
	*	Account フォルダ
		-	ログイン画面やパスワード再設定などを行う画面を配置。
	*	Home フォルダ
		-	初期画面の機能を配置。「Index.vbhtml」以外は、利用せず。
		+	Index.vbhtml
			-	初期画面として使用。
	*	Manage フォルダ
		-	ユーザー情報の管理画面を配置。
	*	Shared フォルダ
		-	ビューにて使用する、共通部品を配置。
		+	_Layout.vbhtml
			-	画面の大枠を決めるテンプレート。
		+	Error.vbhtml
			-	システムエラー発生時の共通画面。
*	その他
### 実現したいこと
#### 機能
* ログイン
	- ASP.NET Identity
* アクセス認可
	- 独自設計
* ログ出力
	- log4net
* データベース接続
	- EntityFramework
* EXCEL出力
	- OpenXML, EPPLUS
* PDF出力
	- wkhtmltopdf(WebKit), TuesPechkin
* 申請と承認
	- 

## 標準環境プログラムを設置後
### 解説（追加分のみ）
*	CommonClassLibrary プロジェクト
	-	旧環境にて使用していた、DBAccessやLogging、Mail送信等の共通処理のライブラリ。
*	Models フォルダ
	-	MVCの「Model」を担当。
		ここに業務ロジックを配置する。
	+	Common
		-	「CommonClassLibrary」からの共通処理を配置。
		+	Constants
			-	固定パラメータ値のオブジェクトクラス（～Symbols）を配置。
		+	DataAccess
			-	データベース処理実行クラスを配置。
		+	Logging
			-	log4netでのログ出力処理実行クラスを配置。
		+	Mail
			-	メール送信処理クラスを配置。
		+	Utility
			-	文字列処理クラス等の共通処理を配置。
		+	ValueObject
			-	メール送信処理の値格納クラス等を配置。
	+	Constants
		-	固定パラメータ値のオブジェクトクラス（～Symbols）を配置。
	+	DataAccess
		-	データベースへの処理クラスを配置。
		+	DAO
			-	SQL文の処理クラスを配置。
		+	DTO
			-	SQL実行パラメータと結果の格納クラスを配置。
	+	Repositories
		-	「Services」から呼び出される、業務ロジックを配置。
	+	Services
		-	「Controller」から呼び出され、業務ロジックを順に呼び出す処理を配置。
	+	Validation
		-	システム共通の判定処理を担当。

## 今回利用環境
### 解説（追加分のみ）
*	参照設定
	-	パッケージの更新により、「参照」の設定に変更がある。（詳細は別途）
*	Scripts　フォルダ
	-	パッケージの更新により、「Scripts」に変更がある。（詳細は別途）

## パッケージについて
*	Nuget によりプレリリースを含めた最新バージョンを取得する。以下は、最新バージョンへの更新方法。
	1.1.	「ツール」メニュー　→「Nugetパッケージ　マネージャ」　→　「ソリューションのNugetパッケージ　の管理」　を開く。
	2.2.	「更新プログラム」タブにて、「プレリリースを含める」をチェックして検索。
	3.3.	パッケージをいくつかチェックして更新。（すべて選択しても上手くいかないことが多い）


## 拡張機能について
*	[Web Extension Pack 2017](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.WebExtensionPack2017)
	-	WEB開発用の便利機能の追加。
	-	開発は、Microsoft Web Platforms&ToolsチームのシニアプログラムマネージャーのMads Kristensen氏。
*	[Productivity Power Tools](http://forest.watch.impress.co.jp/docs/news/749356.html)
	-	主にエディタ関連の便利機能の追加。
	-	VS2017用はまだ。
	-	開発がMicrosoftからOSSへ移行した。
*	AnkhSVN
	-	Subversion をVisualStudioで利用するための拡張機能。


## 今後について
*	.net Core
	-	今回の検証では、VB.NETを使用したので .net Coreを利用できなかった。
		今後、最新環境への更新を考えると.net Coreへと置き換えたいが、互換性がないため簡単に移行できるのかは再度検証を要する。
