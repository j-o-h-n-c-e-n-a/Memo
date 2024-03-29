# 設計
## ”Web API Design - Crafting Interfaces that Developers Love”
	http://apigee.com/
### 開発者視点
	API の目的はアプリケーション開発者 (API 利用者) が可能な限り成功すること. 開発者の視点で設計すること. 本書ではそのような API を実現する tips を紹介する.
#### Pragmatic REST
* REST 原理主義はよくない. RESTafarian たるべからず
* アプリ開発者の利便性が一番大事. 実利的な REST 設計が求められる
* それを本書では Pragramatic REST とよぶ
#### URL
* 動詞ではなく名詞 
	+ リソースを名詞であらわす. Collection: `/dogs/`, Specific element: `/dogs/1234`
	+ HTTP メソッドをリソースの操作とする. POST は create, GET は read, PUT は update, DELETE は delete
* 単数形よりも複数形をつかう
* URL の階層を浅く保つ 
	+ リソースの関係を表したい場合. 例えばオーナー 5678 が飼っている犬をあらわす URL は `/owners/5678/dogs`
	+ 目安として `/resource/identifier/resource` 以上に URL を深くすべきでない
	+ URL は浅く保ち, 複雑さはクエリパラメーターに押しこむ
#### エラーハンドリング
	HTTP ステータスコードをつかう 
* たかだか 10 程度のステータスコードで十分 
	+ Success: 200, 201
	+ クライアントエラー: 400, 401, 403, 404
	+ サーバエラー: 500
	+ 304
* レスポンスボディはエラーコード, エラーメッセージ, エラー詳細へのリンクを返す

### バージョニング
	必ずバージョンをつけること
* v と整数のバージョン番号を URL のトップレベルにつける. e.g. `/v1/dogs` 
* バージョン番号にドット (マイナーバージョン) は不要. API はインタフェースであり実装ではない. マイナーバージョンは粒度が細かい.
#### バージョンは URL にいれるべきか, HTTP ヘッダにいれるべきか 
	ブラウザからの開発しやすさを考えて URL にバージョンをいれるべき
* パラメータを URL とヘッダどちらに入るかは次のルールにしたがう 
	+ API のレスポンスをハンドルするロジックが変わる場合, URL にいれる
	+ そうでない場合 (例えば OAuth の情報) ヘッダに入れる
#### Partial response と Pagination
	いずれも一部の必要なデータだけをクライアント側に返す戦略. Partial response は利用者が指定したフィールドだけを返す. Pagination は返す件数を制御する方法.
* Partial response 
	+ `fields` パラメータにカンマ区切りで指定
	+ e.g. `/dogs?fields=name,color,location`
* Pagination 
	+ `limit` と `offset` パラメータで指定する. offse 番目から limit 件取得
	+ e.g. `/dogs?limit=25&offset=50`
* 全レコード件数を metadata としてレスポンスに含めてあげる
* 省略時のデフォルト件数はデータサイズやアプリケーションによって決める
### リソース操作ではない API のデザイン
	計算・翻訳・変換など, ドメインによってはリソース操作でない API も存在しうる
* その場合名詞でなく動詞をつかう 
	+ e.g. `/convert?from=EUR&to=CNY&amount=100`
* ドキュメントには特殊なケースだということを明記しておくこと 
* 動詞の API はデータベースの値を返すのではなく, ロジックで計算した結果を返しているということをクリアにしておく
* 複数フォーマットのサポート
	+ フォーマットを拡張子のように指定する 
		- e.g. `/dogs.json`, `/dogs/1234.json`
* デフォルトのフォーマットは json がベター
### 属性名
	JavaScript の規約にあわせる 
	先頭小文字のキャメルケース
* 検索のための tips
* 検索は複雑なクエリが想定されるので, Google にならって動詞の URL にするのがよい
	+ `/search?q=fluffy+fur` 
	+ `q` に検索クエリを指定
* 検索のスコープを絞る場合は search の前にスコープをつける 
	+ `/owners/5678/dogs?q=fluffy+fur`
* 結果のフォーマットは拡張子ふうに指定 
	+ `/search.xml?q=fluffy+fur`
* API リクエスト先をひとつの subdomain にまとめる
	+ Facebook や Twitter は種類によってサブドメインがわかれているが, ひとつのまとまっている方がよい
	+ 開発者ポータルも `developers.example.com` に作るとよい
* WebAPI パラメータ例 
	+ limit
		- 1 回のリクエストにて返却されるデータ件数を指定する。(「per_page」とする場合もあるが、 「limit」の記述を推奨) 
	+ offset
		- 返却するデータの中で、先頭から「offset」で書かれた件数のデータを返却しないことを指定する。 
	+ page 
		- 返却してほしいデータの開始位置を指定する。 「limit」と合わせて用いることが多い。 
	+ since 
		- 指定された日付以降のデータを返却する。 
	+ until 
		- 指定された日付以前のデータを返却する。 
	+ sort 
		- 指定された条件を元に並び替えて結果を返却する。 
	+ encode 
		- 文字コードを指定する。 
	+ fields 
		- 指定した項目のみを返却する。 
	+ type 
		- 返却されるフォーマットを指定する。URI にて指定することを推奨する。 
* レスポンスデータに含める代表的なメタデータ 
	+ status:◯
		- 処理に成功したときに success、失敗したときに fail を表示する。 
	+ title 
		- WebAPI の名称を表示する。 
	+ detail:◯
		- status に係る詳細なログ情報を表示する。 
	+ type 
		- API に関するドキュメントの URL を表示する 
	+ parameter 
		- WebAPI プログラムに渡されたパラメータを列挙する。 
	+ resultset 
		- 全データ件数、返却しなかった件数、返却したデータ件数など、結果セットについてのメタ情報を表示する。 
	+ results:◯
		- 結果データを表示する
* データ型
	+ 表示のみの場合は気にしなくとも良いが、登録・更新を伴う場合は型を守った方が良さそう。
	+ Date型：×
		- 日付データの形式にはRFC 3339を用います。また、時差対応しやすくするためUTCで返すことを原則とします。
		- 例：2014-08-30T20:00:00Z
	+ boolean型：×
		- true、falseを返します。
	+ 数値型：×
		- 文字列に変換するのではなく、数値のままで返すようにします。
		- ただし金額の場合、金額の値については文字列として表現(“1000”)します。
	+ 文字列：◯
		- ““で囲んで文字列を返します。
		- タブや改行など、いくつかの特殊な文字はエスケープする必要があります。
	+ null扱い：×
		- nullとして値がセットされていた場合、空文字などに変換せずそのまま返します。
### 例外的な動作への tips
	クライアントが HTTP エラーコードをインターセプトする場合
	たとえば Flash は HTTP のエラーレスポンスを受け取ると, エンドユーザのアプリにエラーコードを表示する
	これを避けるために `suppress_response_codes=true` というクエリパラメータを提供する 
	これが指定されていると HTTP レスポンスコードが常に 200 になるようにする
* レスポンスボディは通常通りのエラーコードやメッセージを返す. クライアントアプリはこれを見てハンドリングする
#### 限られた HTTP メソッドしかサポートしないクライアントへの対応
	例えば PUT, DELETE をサポートしないクライアントへの対応
	`method` クエリパラメータで指定するようにする 
	`/dogs?method=post` (create), `/dogs` (read), `/dogs/1234?method=put&location=park` (update), `/dogs/1234?method=delete` (delete)
### 認証
	OAuth 2.0 を使う
	OAuth に似た独自方式にしないこと. 既存の OAuth ライブラリが使えないと開発者は不便を感じる
#### Chatty APIs
	Chatty API (おしゃべりな API, つまり情報が少なく何度も呼び出さないといけないもの) をいかに避けるか
1. まず RESTful に設計し, そのごショートカットを追加する 
* 複数の API 呼び出しを組み合わせないと実現できない使い方を, 一度の呼び出しで実現できる API を追加してあげる
* 先にショートカットを作ってはいけない. まずは RESTful なデザインで, 必要に応じてショートカットを追加する
* partial response にドット演算子を導入して, 別のリソースのフィールドを参照できるようにする 
	+ `/owners/5678?fields=name,dogs.name`
### SDK
	API がよく設計されドキュメントも整っていれば SDK は不要
	一方で API をつかうためにドメインの知識が必要な場合, SDK を提供するという手がある
	API を改修するのではなく SDK を提供することで API をクリーンに保てるなどいくつかのメリットがある
### API Facade Pattern
	システムのフロント (API) とバックエンド (システム本体や DB など) のつなぎかた. Facade Pattern をつかう
	フロントとバックエンドの間に抽象的なレイヤーを一枚はさむ
#### 設計のしかた 
	まず理想的な API インタフェースを設計する
	stub を用意して上記のインタフェースを実装する
	facade と実際のシステムをつなぐ

## GraphQL

## エラー処理
## ログ出力
* 端末識別番号
	+ IMEI
## ユーザ認証
* アクセストークン

## OpenAPI


## Swagger
* [NSwag](https://tech-blog.cloud-config.jp/2020-12-15-net-core-3-1-web-api-nswag/)


## PDF		
### PDF出力ツール	
#### iTextSharp	
		枯れたツールなので、信頼性はある
		ライセンスに注意が必要とのことで使用しない
		https://hnys.jp/develop/itextsharp/
		https://codezine.jp/article/detail/462
#### PDFSharp	
		上記のライセンス問題を解消
* [](http://2ndgd.blogspot.com/2018/07/pdfsharp-migradoc-cpdf.html)
* [](www.pdfsharp.net/wiki/MainPage.ashx?AspxAutoDetectCookieSupport=1)
#### PDF.js
	https://www.weblab.co.jp/staff/html/7914.html

### PDF編集ツール	
#### MigraDoc	
	上記PDFSharpと組み合わせて使用
### 他	
* http://www.subarunari.com/entry/2017/10/11/003225

#### PanDoc	
* [](https://pandoc.org/)
		クリスタルレポート	
			[ダウンロード](https://www.crystalreports.com/crystal-reports-visual-studio/)
			[ライセンス](https://crystalreports.jp/sap-crystal-solutions/licence)
			[開発者ページ](https://help.sap.com/viewer/product/SAP_CRYSTAL_REPORTS,_DEVELOPER_VERSION_FOR_MICROSOFT_VISUAL_STUDIO/SP21/ja-JP)
			
			
	・	PDFビューア	
		https://www.nedia.ne.jp/blog/2019/04/23/14048	
		【推奨】AndroidのChromeでは開けないので、Acrobatをインストールする	
		【非推奨】Cordova-Plugin-Documant-Viewer を使う	
			https://www.npmjs.com/package/cordova-plugin-document-viewer
		【非推奨】PDF.JS を使う	
			https://mozilla.github.io/pdf.js/


# 参考URL
* [](http://smsurf.app-rox.com/api/)
* [共通語彙基盤](https://imi.go.jp/)
* [Postman](http://kageura.hatenadiary.jp/entry/hazimetepostman)

# 外部ＡＰＩ
## 地図
### google map
## 天気
### 
## 防災
### AED
## 鉄道
## 航空
## 観光
## ショッピング
## 動画
## 写真/画像
## クラウドストレージ
### google drive
### dropbox
## 健康
## 分析
* モバイル空間統計
### Watson API
## 音声認識
## 文字認識

# ローレベルAPI
## IndexedDB
## Web Authentication
### Windows Hello
