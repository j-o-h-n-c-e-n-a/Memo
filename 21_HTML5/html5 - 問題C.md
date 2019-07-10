::問題::{
	~ 
}

1. リクエストメソッドとその説明の組み合わせとして、正しいものを３つ選びなさい。（×）
~PUT：リソースの送信
=HEAD:リソースの要求
=GET：リソースの要求
~POST：リソースの更新
=DELETE：リソースの削除

2. サーバ側でエラーが発生した際に返されるステータスコードとして、正しいものを選びなさい。（×）
=500
~304
~401
~403
~307

3. 以下のURLの説明として、正しいものを３つ選びなさい。（◯）
	https://www.example.com/sch/product.html?q=HTML

~既定のポート番号として、８０番が使われる
=既定のポート番号として、443番が使われる
~Digest認証によって通信が暗号化される
=SSL/TLSで通信が暗号化される
=FQDN形式のURLである

4. Webの認証の説明として、誤っているものを２つ選びなさい。（×）
~Basic認証は盗聴・改ざんの危険性がある
~Basic認証においてユーザ名・パスワードはAutorizationヘッダに付加される
=Basic認証ではHTTPS通信が必須である
~Digest認証ではユーザ名・パスワードをハッシュ化してサーバへ送信する
=Digest認証ではパスワードのみハッシュ化してサーバへ送信する

5. ヘッダフィールド名とその説明の組み合わせとして、正しいものを２つ選びなさい。（◯）
~Content-Encoding：ブラウザが受け入れ可能な言語
~Accept：認証情報
=Expires：リソースの有効期限
=User-Agent：リクエストしたブラウザを表す文字列
~Content-Type:ブラウザが受入可能なアルゴリズム

6. 以下のセッションの説明文の空欄に当てはまるものを選びなさい。
　 クライアント・サーバ間のセッション管理において、クライアントでセッションIDを保持するには「」を使用する。（◯）
~sessionStorage
=HTTPクッキー
~localstorage
~Indexed Database API
~Web SQL

7. HTML5の文書型宣言として、正しいものをすべて選びなさい。（◯）
=<!doctype HTML>
=<!DOCTYPE html>
~<!DOCTYPE HTML5>
~<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
~<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitonal//EN" "http://www.w3.org/TR/html4/loose.dtd">

8. 多言語に対応した文字コードとして、正しいものを選びなさい。（◯）
=UTF-8
~CP932
~ISO-2022-JP
~Shift_JIS
~EUC-JP

9. 半角スペースを表す文字実体参照を記述しなさい（◯）
&nbsp;

10. PNGの説明として、正しいものを３つ選びなさい。（◯）
=可逆圧縮であり、GIFよりも圧縮率が良く、劣化もない
~アニメーション機能を扱うことができる
=インタレースに対応している
~半透明には対応していない
=W3Cにより推奨されている

11. Ajaxの実現に使用するものを２つ選びなさい。（×）
~Websocket
=XMLHttpRequest
~Data URI スキーム
~Digest認証
=JSON

12. ペンダプレフィックスとして、誤っているものを選びなさい。（×）
~ -moz-
~ -ms-
~ -webkit-
= -chrome-
~ -o-

13. HTML文書にスタイルを適用する方法についての説明として、正しいものを２つ選びなさい。（×）
~１つのHTMLファイルに複数のCSSファイルを読み込むことはできない
~CSSファイルを読み込む場合、link要素のtype属性は省略できない
~link要素とstyle要素を１つのHTMLファイル内で併用できない
=style属性はすべての要素において記述できる
=@importはCSSファイル内だけでなく、style要素にも記述できる

14. 以下のWebページの「新入社員向け研修の申し込みを開始しました」にスタイルを適用しないセレクタを２つ選びなさい。（◯）
	<div class="news">
		<h4>NEWS</h4>
		<p>新入社員向け研修の申し込みを開始しました</p>
		<p>無償セミナーの日程を追加しました</p>
	</div>
~ div > p
= div + p
= h4 > p
~ h4 + p
~ h4 ~ p

15. 以下のWebページの「B」にスタイルを適用するセレクタをすべて選びなさい。（×）
	<div class="sample">
		<p class="sampleA">A</p>
		<span>X</span>
		<p id="sampleB" class="sampleB">B</p>
		<p class="sampleC">C</p>
	</div>
~ p:nth-child(2)
~ p:first-of-type
= p:nth-of-type(2)
= .sampleB
= #sampleB

16. リンクにマウスカーソルを合わせたときにスタイルを適用する場合、空欄に当てはまるキーワードを記述しなさい。（×）
	a:「hover」 { background: #e0ffff; }

17. 以下の説明文の①、②、③に当てはまるキーワードの組み合わせとして、正しいものを選びなさい。（◯）
	word-spacing プロパティは①の間のスペースを指定するプロパティ、letter-spacingプロパティは②間のスペースを指定するプロパティです。また、line-heightプロパティは③間のスペースを指定するプロパティです。

=①単語	②文字	③行
~①単語	②行	③文字
~①文字	②単語	③行
~①文字	②行	③単語
~①行	②単語	③文字

18. 以下のCSSを設定した場合の説明として、正しいものを２つ選びなさい。（×）
	.box {
		text-align: right;
		width: 250px;
		margin-left: auto;
		margin-right: auto;
		padding: 0px;
		border: 2px solid black;
		background-color: rgba(255, 0, 0, 0.5);
	}

~ボックスはブラウザの右側に表示される
~ボックスの枠線は破線である
=ボックスの背景色は半透明である
=マージンを含まなボックスの幅は２５４pxである
~ボックスのサイズは画面サイズいっぱいに調整される

19. 以下のCSSを設定した場合、要素が占める幅（マージン含む）として、正しいものを選びなさい。（×）
	.box {
		width: 250px;
		padding: 2px;
		margin: 5px 5px 5px 10px;
		border: 2px solid black;
		box-sizing: content-box;
	}
~ 250px;
~ 265px;
~ 268px;
= 273px;
~ 278px;

20. 可変レイアウトボックスを指定する場合のdisplayプロパティの値として、正しいものを選びなさい。（◯）
=flex
~none
~list-item
~block
~table

21. 要素を移動、回転、拡大/縮小、傾斜できるプロパティとして、正しいものを選びなさい。（◯）
~animation
~radial-gradient
~float
=transform
~transition

22. 以下のCSSを適用した場合の説明として、正しいものを選びなさい。（×）
	div.transitionbox {
		width: 100px;
		transition: width 3s ease-in;
	}

	div.transitionbox: hover {
		width: 200px;
		background-color: gray;
	}
=ボックスにマウスカーソルを合わせているとき、アニメーションが実行される
~アニメーションでは、ボックス幅が２００pxから１００pxに変化する
~アニメーションでは、ボックスの色がグレーに変化する
~アニメーションは、３秒遅延時間の後に開始される
~アニメーションは、等速で実行される

23. 以下のCSSを適用した場合の説明として、正しいものを３つ選びなさい。（×）
	div.animationbox {
		width: 50px;
		height: 50px;
		background: red;
		animation: rotation linear 3s 0.5s intinite;
	}

	@keyframes rotation {
		50% {
			transform: rotate(-90deg);
			background: green;
		}
		100% {
			transform: rotate(90deg);
			background: blue;
		}
	}

~ボックスにマウスカーソルを合わせているとき、アニメーションが実行される
=アニメーションは繰り返し実行される
=アニメーションは０．５秒の遅延時間の後に開始される
=アニメーションは等速で実行される
~アニメーションでは、３秒かけて緑に変化し、３秒かけて青に変化する

24. ボックスに楕円状のグラデーションをかける場合、空欄に当てはまるキーワードの組み合わせとして、正しいものを選びなさい。（◯）
	①-image;　②-gradient(lightblue,royalblue);
~①border	②liner
~①border	②radial
~①background	②liner
=①background	②radial
~①background	②circle

25. 以下のHTMLにCSSを適用した場合の説明として、正しいものを選びなさい。（◯）
	【HTML】
		<div class="wrap clearfix">
			<section>A</section>
			<section>B</section>
		</div>

	【CSS】
	.wrap > section {
		width: 300px;
		margin: 10px 20px;
		border: 3px solid black;
		text-align: center;
		float: left;
	}
	.clearfix::after {
		content: "";
		display: block;
		clear: both;
	}

~「A」のボックスのみ表示される
~「B」のボックスのみ表示される
=「A」の右隣に「B」が表示される
~「A」の左隣に「B」が表示される
~「A」の下に「B」が表示される

26. 以下のHTMLにCSSを適用した場合、p要素の文字色と背景色の組み合わせとして正しいものを選びなさい。（◯）
	【HTML】
		<div>
			<p class="color" style="color: black; background-color: yellow">
			HTML5exam
			</p>
		</div>

	【CSS】
	.color {
		color: green !impotant;
		background-color: blue;
	}
	#new {
		color: yellow;
		background-color: blue;
	}
	p {
		color: red;
		background-color: blue;
	}

~文字色：黒	背景色：黄
~文字色：黒	背景色：青
=文字色：緑	背景色：黄
~文字色：緑	背景色：青
~文字色：赤	背景色：青

27. 以下のCSSのうち、最も優先順位が高いものを選びなさい。（◯）
~ a.flm:hover
~ p.news
~ .price::after
~ body p#cat
= #cat #tail

28. セクショニングコンテンツに分類される要素として、正しいものをすべて選びなさい。（×）
~title
=article
=aside
~h1
=nav

29. 以下の説明文の空欄に当てはまる要素名を記述しなさい（◯）
「main」要素は、そのドキュメントに固有であり中心的なコンテンツを表す要素です。
「main」要素は、フローコンテンツであり、ドキュメントのアウトラインには影響を与えません。

30. 以下のHTMLのbody要素が構成するアウトラインとして、正しいものを選びなさい。（×）
【HTML】
	<body>
		<h1>eラーニング</h1>
		<section>
			<h1>e講義動画</h1>
			<h2>e講義動画ライブラリ</h2>
			<blockquote>
				<h1>集合研修</h1>
			</blockquote>
		</section>
	</body>

= 1.eラーニング
	1.e講義動画
		1.e講義動画ライブラリ
~ 1.eラーニング
	1.e講義動画
		1.e講義動画ライブラリ
	1.集合研修
~ 1.eラーニング
	1.e講義動画
	2.e講義動画ライブラリ
~ 1.eラーニング
	1.e講義動画
	2.e講義動画ライブラリ
	1.集合研修
~ 1.eラーニング
	1.e講義動画
	2.e講義動画ライブラリ
  1.集合研修

31. HTML5で廃止された要素として、正しいものを２つ選びなさい。（×）
=center
~strong
=big
~b
~small

32. u要素が表すセマンティクスとして、正しいものを選びなさい。（×）
~アンダーラインを表示するテキスト
=ドキュメント内の伝わりにくいテキスト
~正確ではないか関連性が無くなったテキスト
~他の情報源からの引用
~見出しや段落中の重要な箇所や緊急の通知や警告

33. 以下のようにルビを表示する場合、コードの①、②に当てはまる要素の組み合わせとして、正しいものを選びなさい。ただし、ruby要素をサポートしないブラウザでは「心太（ところてん）」とふりがなの代替テキストを表示するものとする。（×）

【コード】
	<ruby>心太<①>(<①/><②>ところてん</②><①>)</①></ruby>

~ ①rb	②rt
~ ①rb	②rp
~ ①rp	②rb
= ①rp	②rt
~ ①rt	②rp

34. 以下のようにリストを表示する場合、コードの①～④に当てはまる要素の組み合わせとして、正しいものを選びなさい。（×）
【表示】
事業内容
・人材育成・研修サービス
	1.人材育成コンサルティング
	2.学習管理サービス
	3.講習会・サテライト講習会・e講義動画・eラーニング
	4.ｅラーニングコンテンツ受託開発・ドキュメント製作と活用・webサイト製作と運用サービス
・個人のお客様向けパソコン教室
【コード】
<h3>事業内容</h3>
<①>
	<②>
		人材育成・研修サービス
		<③>
			<li>人材育成コンサルティング</li>
			<li>学習管理サービス</li>
			<li>講習会・サテライト講習会・e講義動画・eラーニング</li>
			<li>ｅラーニングコンテンツ受託開発・ドキュメント製作と活用・webサイト製作と運用サービス</li>
		</③>
	</②>
	<④>
		個人のお客様向けパソコン教室
	</④>
</①>

~①ul	②li	③ol	④ul
=①ul	②li	③ol	④li
~①li	②ul	③ol	④ul
~①li	②ul	③ol	④li
~①ol	②li	③ul	④li

35. time要素の記述として、誤っているものを２つ選びなさい。（×）
=<time>正月</time>
=<time>2018年1月1日</time>
~<time>2018-01-01T13:26:05</time>
~<time datetime="2018-01-01">正月</time>
~<time datetime="2018-01-01 13:26:05">正月</time>

36. 以下のコードの説明として、誤っているものを選びなさい。
【コード】
<video controls autoplay loop poster="~images/top.jpg">
	<source src="movies/top.mp4">
	<source src="movies/top.webm">
	<source src="movies/top.ogv">
	お使いのブラウザは動画再生に対応していません。
</video>

~動画は繰り返し再生される
~動画は自動再生される
~source要素に指定された動画ファイルの中にブラウザが対応する形式のファイルがない場合、video要素のposter属性に指定した画像が表示される
~ブラウザが「.mp4」ファイルにのみ対応している場合、「top.mp4」が再生される
=ブラウザが「.mp4」ファイルと「.webm」ファイルの両方に対応している場合、「top.mp4」の後に「top.webm」が再生される

37. ブラウザで再生する音声の音量を０にする場合、audio要素に指定する属性として、正しいものを選びなさい。（◯）
~ controls
~ preload
~ autoplay
~ loop
= muted

38. ビデオコーデックとして、正しいものを３つ選びなさい。（◯）
=H.264
~MP3
~AAC
=MPEG-2
=MPEG-4

39. ハイパーリンクを作成する以下のコードの空欄に当てはまるキーワードを記述しなさい。（×）
<a [href]="guide.html">学習ガイド</a>

40. 以下のコードの説明として、正しいものを選びなさい。（◯）
	<label>ID: <input type="number" required></label>

~小数値を入力できる
=入力が必須である
~入力内容を助言するメッセージとしてID:が入力部品内に表示される
~入力できる最大値は100である
~入力できる最小値は0である

41. 以下のようにセレクトボックスを表示する場合、コードの①と②に当てはまる要素の組み合わせとして、正しいものを選びなさい。（◯）
	<① name="select">
		<② value="yes">そう思う</②>
		<② value="neithor">どちらともいえない</②>
		<② value="no">そう思わない</②>
	</①>

~ ①select	②summary
~ ①select	②legend
= ①select	②option
~ ①fieldset	②option
~ ①fieldset	②legend

42. Webページ内に別のhtmlファイルの内容を挿入する場合に使用するHTML5の要素として、正しいものを選びなさい。（◯）

~frame
~frameset
~noframes
=iframe
~canvas

43. ディスクロージャーウィジェットを表示する場合、コード①と②に当てはまる要素の組み合わせとして、正しいものを選びなさい。（×）
	<①>
		<②>はじめてのHTML</②>
		<p>
		</p>
	</①>

~ ①dl	②dt
~ ①menuitem	②menu
~ ①menu	②menuitem
~ ①summary	②details
= ①details	②summary

44. テーブルを作成する要素についての説明として、誤っているものを選びなさい。（◯）

~table要素のborder属性の値は、空文字列か１でなければならない
~tfoot要素はtbody要素の後に配置しなければならない
=caption要素はtable要素ないに必ず１つ配置しなければならない
~table要素内にscript要素、template要素を配置することで、javascriptから表を操作できる
~table要素直下にtr要素が存在する場合は、tbody要素を使用できない

45. レスポンシブWebデザインで使用する技術の説明として、正しいものを３つ選びなさい。（×）

=viewportとは、ブラウザの表示領域を設定する機能である
=フルードグリッドとは、グリッドという単位でWebページのレイアウトを構成し、ブラウザのウィンドウサイズによってグリッドの数や横幅を切り替える手法である
~メディアクエリとは、デバイスの種類や画面サイズに応じて表示するWebページを切り替える機能である
=フルードイメージとは、ブラウザのウィンドウサイズに応じて表示する画面や動画を切り替える技術である
~Canvasとは、複数の画像を１つの背景画像としてまとめる手法である

46. フルードグリッドの説明として、正しいものを２つ選びなさい。（◯）

~javascriptによるそりが必要である
~デバイスサイズに応じてグリッドの横幅のみを切り替える
~ブラウザのウィンドウサイズに応じて表示する画像や動画のサイズ変更する手法である
=ブラウザのウィンドウ幅に応じて表示する表示するコンテンツのレイアウトを変更する
=グリッドの横幅を％で相対指定することによって実現する

47. 画面が縦向きであることを意味する値を記述しなさい。（×）

	@media all and (orientation: [landscape] ) {}

48. メディアタイプとその説明について、正しい組み合わせを選びなさい。（×）
①音声読み上げブラウザ
②一般的なカラーディスプレイ
③携帯電話など、画面が小さい端末

~ ①speech	②display	③mobile
= ①speech	②screen	③handheld
~ ①speech	②screen	③mobile
~ ①sound	②display	③mobile
~ ①sound	②screen	③handheld


49. 以下のメディアクエリの説明として、正しいものを選びなさい。（×）
	<link rel="stylesheet" media="screen and (min-width:480px), print" ...>

=viewportの横幅が480px以上のディスプレイと、プリンタで適用される
~viewportの横幅が480px以上のプリンタと、ディプレイで適用される
~viewportの横幅が480px以下でディスプレイと、プリンタで適用される
~viewportの横幅が480px以下でプリンタと、ディスプレイで適用される
~viewportの横幅が480px以下のディスプレイで適用される

50. WebページにJavascriptファイルを読み込む方法の説明として、正しいものを選びなさい。（◯）
~type属性の記述が必須である
=script要素のsrc属性に読み込むファイルを指定する
~スクリプトファイルは非同期処理で取得される
~javascriptのMIMEタイプはscript/javascriptだる
~script要素の終了タグは省略できる

51. ストリーミング配信を実現するためのjavascriptAPI　として正しいものを選びなさい。（×）
~websocket
=media source extensions
~webRTC
~encrypted media extensions
~XMLHttpRequest

52. EMEの説明として、正しいものを選びなさい。（×）
~ネットワークの状況によって再生品質を変更し、コンテンツがスムーズに再生できる
~専用のプラグインが必要である
=著作権保護されたコンテンツを再生できる
~動画の合間に広告などのコンテンツを挿入できる
~動画の画質はプロトコルに依存しない

53. CanvasAPIの説明として、正しいものを２つ選びなさい。（×）
=画面全体を入れ替えるようなアニメーションが実行される画像
~拡大・縮小して表示する画像
~CSSでデザイン設定できる
=canvas要素に画像データを出力する
~タグで画像を表現する

54. Geolocation APIでデバイスから取得できる情報として、誤っているものを選びなさい。（◯）
~緯度・経度
~方向
=地域情報
~高度
~速度

55. ディスプレイをマルチタッチしたときに発生するイベントとして、正しいものを選びなさい。（◯）
~マウスイベント
~入力イベント
=Touchイベント
~Pointerイベント
~キーボードイベント

56. localStorageの説明として、正しいものを選びなさい。（◯）
=ウィンドウやタブの間でデータが共有できる
~blobデータを保存できる
~リクエストのたびサーバへ値を送信する
~最大4kbまでデータを保存可能
~データをサーバに保存する

57. 機能の利用にHTTPS通信が必須となるAPIを２つ選びなさい。（×）
=Service Workers
~XMLHttpRequest
=Geolocation API
~Server-Sent Events
~DeviceOrientation Event

58. UI操作に影響を与えず、バックグラウンドで処理を実行したい。このような要件を満たす技術として、適切なもの２つを選びなさい。（◯）
~Application cache
=WebWorkers
~WebSocket
=ervice Workers
~XMLHttpRequest

59. ユーザの位置情報をスマートフォンから取得し、ブラウザを実行していなくても、周辺のおすすめ情報を通知するWebアプリケーションを開発したい。このようなアプリケーションの実現に必要なAPIをすべて選びなさい。（◯）
=NotificationAPI
=Geolocation API
=Service Workers
~WebSocket
=PushAPI

60. WebRTCの説明として、正しいものを２つ選びなさい。（×）
~Webサーバから一方的にデータを送信する
=ブラウザ間で通信を行う
=オーディオ・ビデオなどを送受信できる
~データ送信のみ可能
~同期通信を行う
