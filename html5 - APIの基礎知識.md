<h2>HTML5プロフェッショナル認定試験レベル1 サンプル問題</h2>
<section>
<div class="section-inner">
<div class="sample-box">
  <p class="lead">例題解説とその内容については、例題提供者の監修です。内容や試験問題に関わるお問い合わせにつきましては、LPI-Japan事務局ではお応えできませんのでご了承ください。<br>例題解説のご提供者さまを募集中です。<a href="mailto:&#109;&#97;&#105;&#108;&#64;&#108;&#112;&#105;&#46;&#111;&#114;&#46;&#106;&#112;">LPI-Japan事務局</a>までぜひご投稿ください。選ばれた方の例題解説は本サイトに掲載させていただきます。</p>
  <h3 id="lv1_5">1.5 APIの基礎知識</h3>
<div class="question">
<dl>
<dt>例題5.15「1.5.4 通信系API概要」</dt>
<dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_154">1.5.4 通信系API概要</a>」からの出題です。<br>
リアルタイム通信を可能にするWebアプリケーションの開発に必要な技術(API)は次のうちどれか。2つ選びなさい。
</dd>
<dd>
<ul class="option">
<li>socket</li>
<li>Socket.io</li>
<li>WebSocket</li>
<li>Winsock</li>
<li>Red Sox</li>
</ul>
</dd>
</dl>
<p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。<br>例題公開日：2018年5月8日</p>
<p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>答え<span> B、C</span></dt>
<dd>
<p>もともとWebの通信はブラウザの要求に従いサーバーがデータを送信するという仕組みです。<br>
しかし、Web技術の高度化と多様化に伴い、従来のアプリと同等またはそれ以上の機能が要求されるようになってきました。<br>
そのひとつにリアルタイム性があり、ポーリングやComet(ロングポーリング)の技術がでてきましたが、リアルタイム性を高めるにはポーリングの間隔を短くする必要があり、負荷増大の原因となっていました。</p>

<p>CのWebSocketはこれを解決するためのHTML5の双方向通信の技術なので、正解です。<br>
BのSocket.ioはCometやWebSocketなどを意識せずに使用できるようにしたAPIなので、正解です。</p>
<p>AのsocketはBSD UNIX で開発されたTCP/IP通信を開始する最初のC言語の関数なので、不正解です。WebSocketやSocket.io、Winsockの名前の由来となる有名な用語でもあります。<br>
DのWinsockはWindows上でTCP/IPの標準インターフェースなので、不正解です。<br>
EのRed Sox は米国ボストンを本拠地とするメジャーリーグのチーム名なので、不正解です。</p>
</dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_154">出題範囲の詳細</a></p>
  <div class="present">
    <p>LPI-Japan<br>中谷 徹</p>
  </div>
</div>
</div>
<div class="question">
<dl>
<dt>例題5.14「1.5.2 デバイスアクセス系API概要」</dt>
<dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_152">1.5.2 デバイスアクセス系API概要</a>」からの出題です。<br>
利用者の寝返り振動を利用した目覚ましスマホアプリを開発したい。<br>
HTML5で利用できる寝返り感知のためのAPIは次のうちどれか。2つ選びなさい。<br>
なお、スマホは枕元に置いて使用するものとする。
</dd>
<dd>
<ul class="option">
<li>DeviceMotion Event（加速度センサー）</li>
<li>DeviceOrientation Event（ジャイロセンサー）</li>
<li>GeoLocation API（位置情報取得）</li>
<li>Proximity API（近接センサー）</li>
<li>Vibration API（バイブレーション）</li>
</ul>
</dd>
</dl>
<p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
<p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>答え<span> A、B</span></dt>
<dd>
<p>通常、目覚まし時計は指定した時刻にアラームを鳴らす機能と、アラームを止めて寝過ごすことが無いようスヌーズ機能が備わっています。しかしアラームが鳴っても寝ぼけたままスヌーズ機能も解除してしまい寝過ごした経験をお持ちの方も少なくないのではないでしょうか。<br>
最近のスマホの目覚まし時計アプリはスグレモノで、指定した時刻帯で眠りの浅い瞬間にアラームを鳴らすようになっています。その眠りの浅い瞬間を拾うタイミングは、レム睡眠、ノンレム睡眠の周期などではなく、寝返りだそうです。<br>
スマホの加速度センサーやジャイロセンサーにより寝返りの振動を拾うことで眠りが浅くなった時にアラームを鳴らすことができ、快適な目覚めになります。それでも…という方は、複数のアプリをセットして下さい。</p>

<p>Aの加速度センサーはX,Y,Zの3軸方向の加速度を振動として devicemotion イベントで検知できるので、正解です。<br>
Bのジャイロセンサーは角速度センサーとも呼ばれ、X,Y,Zの3軸方向の角加速度を振動として deviceorientation イベントで検知できるので、正解です。<br>
CのGeoLocation APIは位置情報を取得するAPIで、スマホではGPS、PCではIPアドレスなどからおおよその位置情報を取得できますが、寝返りを検知できるほどの精度ではないので不正解です。<br>
Dの近接センサーは赤外線で距離を検知します。通常、通話のため顔を近づけたことを検知し画面を暗くしたり、タッチパネルの誤動作を防ぐために使用されるもので、不正解です。<br>
EのバイブレーションAPIは振動を感知するためのものではなくスマホを振動させるためのAPIなので、不正解です。</p>
</dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_152">出題範囲の詳細</a></p>
  <div class="present">
    <p>LPI-Japan<br>中谷 徹</p>
  </div>
</div>
</div>
<div class="question">
<dl>
<dt>例題5.13「1.5.4 通信系API概要」</dt>
<dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_154">1.5.4 通信系API概要</a>」からの出題です。<br>
リアルタイム通信を可能にするWebアプリケーションの開発に必要な技術(API)は次のうちどれか。2つ選びなさい。
</dd>
<dd>
<ul class="option">
<li>socket</li>
<li>Socket.io</li>
<li>WebSocket</li>
<li>Winsock</li>
<li>Red Sox</li>
</ul>
</dd>
</dl>
<p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
<p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>答え<span> B、C</span></dt>
<dd>もともとWebの通信はブラウザの要求に従いサーバーがデータを送信するという仕組みです。<br>
しかし、Web技術の高度化と多様化に伴い、従来のアプリと同等またはそれ以上の機能が要求されるようになってきました。<br>
そのひとつにリアルタイム性があり、ポーリングやComet(ロングポーリング)の技術がでてきましたが、リアルタイム性を高めるにはポーリングの間隔を短くする必要があり、負荷増大の原因となっていました。<br><br>

選択肢CのWebSocketはこれを解決するためのHTML5の双方向通信の技術なので、正解です。<br>
選択肢BのSocket.ioはCometやWebSocketなどを意識せずに使用できるようにしたAPIなので、正解です。<br>
選択肢AのsocketはBSD UNIX で開発されたTCP/IP通信を開始する最初のC言語の関数なので、不正解です。<br>
WebSocketやSocket.io、Winsockの名前の由来となる有名な用語でもあります。<br>
選択肢DのWinsockはWindows上でTCP/IPの標準インターフェースなので、不正解です。<br>
選択肢EのRed Sox は米国ボストンを本拠地とするメジャーリーグのチーム名なので、不正解です。
</dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_154">出題範囲の詳細</a></p>
  <div class="present">
    <p>LPI-Japan<br>中谷 徹</p>
  </div>
</div>
</div>
<div class="question">
<dl>
<dt>例題5.12「1.5.3 オフライン・ストレージ系API概要」</dt>
<dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_153">1.5.3 オフライン・ストレージ系API概要</a>」からの出題です。<br>
HTML5 アプリでファイル送信機能を盛り込みたい。有効なAPIを３つ選びなさい。
</dd>
<dd>
<ul class="option">
<li>Drag and Drop API</li>
<li>File API</li>
<li>FTP API</li>
<li>Progress Events</li>
<li>SCP API</li>
</ul>
</dd>
</dl>
<p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
<p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>答え<span> A、B、D</span></dt>
<dd>ファイルの送信を行うアプリでは、送信ファイルの選択、送信の開始、送信状況（進捗・完了）の通知が必要です。<br><br>

選択肢BのFile APIは、&lt;input type=file multiple&gt;によるファイル選択ダイアログで取得したファイルを javascript で処理するAPIです。<br>
選択肢AのDrag and Drop APIは、ファイルをドラッグ＆ドロップするAPIで、状況によりファイル選択ダイアログより使用しやすくなります。<br>
選択肢DのProgress Eventsは、プログレスバーを表示する際の各種イベント処理のAPIです。ファイルが大きい、通信速度が遅いなど、転送時間が長い場合に有効です。<br>
選択肢CのFTP API、選択肢EのSCP APIはHTML5のAPIとしては存在ないので不正解です。<br>
FTP(File Transfer Protocol)は、古くからあるファイル転送のプロトコルで広く使用されていましたが、現在はセキュアな通信の必要性から SCP/SFTP
が利用されるようになっています。
</dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_153">出題範囲の詳細</a></p>
  <div class="present">
    <p>LPI-Japan<br>中谷 徹</p>
  </div>
</div>
</div>
<div class="question">
<dl>
<dt>例題5.11「1.5 APIの基礎知識」</dt>
<dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_15">1.5 APIの基礎知識</a>」からの出題です。<br>
スマートフォン利用者の所在地に従って、他のアプリの実行中であっても、雷雨情報を通知できる雷雨アラートWEBアプリを開発したい。利用を検討すべき API を２つ選びなさい。</dd>
<dd>
<ul class="option">
<li>WebRTC</li>
<li>DeviceOrientation Event</li>
<li>Geolocation API</li>
<li>Message API</li>
<li>Notifications API</li>
</ul>
</dd>
</dl>
<p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
<p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>答え<span> C、E</span></dt>
    <dd>開発に必要な機能は、所在地情報取得と通知です。所在地情報の取得は Geolocation API(C)、通知には Notifications API(E) で実現できます。<br>

Aの WebRTC は、ブラウザでWeb会議を実現するAPIで、音声および動画のリアルタイム通信の他、チャットやファイル共有の機能を利用できますが、このアプリには必要ありません。Bの
DeviceOrientation Event は、デバイスの方向や傾きなどの情報を取得するAPIですが、位置そのものは取得できません。Dの Message API は Androidアプリ開発環境にはあるようですが、HTML5にはありません。<br>

実際に開発するには、これらの他、Web Workers または Service Workers, Push API, fetch の併用が必要になるでしょう。<br>
また、付加機能として Vibration API で通知の際にスマホを振動させたりすることも可能でしょう。

</dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_15">出題範囲の詳細</a></p>
  <div class="present">
    <p>LPI-Japan<br>中谷 徹</p>
  </div>
</div>
</div>
<div class="question">
<dl>
<dt>例題5.10「1.5.1 マルチメディア・グラフィックス系API概要」</dt>
<dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_151">1.5.1 マルチメディア・グラフィックス系API概要</a>」からの出題です。<br>
SVG の説明として適切なのは次のうちどれか。</dd>
<dd>
<ul class="option">
<li>文字や図形の装飾や変形は CSS で指定する必要がある。</li>
<li>HTML では img 要素でのみ指定できる。</li>
<li>ラスター形式のため拡大してもきれいに表示できる。</li>
<li>XML形式のためテキストエディタで作成・編集できる。</li>
<li>写真などのデータは扱えない。</li>
</ul>
</dd>
</dl>
<p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
<p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>答え<span> D</span></dt>
    <dd>SVG（Scalable Vector Graphics）はベクター形式のグラフィックスをXMLで表現する仕様です。<br>
グラフィックスにはラスター形式とベクター形式があります。円を描く場合、ラスター形式では方眼紙の目を塗りつぶして円を表現するのに対し、ベクター形式では白紙にコンパスで円を表現するといった描画の違いがあります。この違いにより、方眼紙状の液晶画面を最終出力先とした場合、画質に差が生じます。<br>
例えば、アイコン用に作成したグラフィックスを高解像度の液晶画面に拡大して表示する際、ラスター形式は作成したドット表現を虫眼鏡で拡大したイメージとなりギザギザが増幅されますが、ベクター形式では高解像度の画面上に新たにコンパスで円を描くので高精細できれいな円を表示できます。<br>
また、CSSと同様にSVG単体で文字や図形の作成、装飾や変形が可能な上、CSSでの装飾も可能です。
利用例として、ロゴやアイコンを１つのSVGでまかなうことができ、レスポンシブデザインにも有効です。また、円グラフや棒グラフなど、さまざまな形式のチャート表現にも利用されています。<br><br>
各選択肢の解釈は下記のとおりです。<br>
A. SVG は単独で装飾や変形によるアニメーションが可能なので、不正解です。<br>
B. svg は png等と同様 img 要素での指定とインラインでの使用が可能なので、不正解です。<br>
C. SVGはベクター形式なので、不正解です。<br>
D. SVGはXMLで表記しテキストエディタで編集できるので、正解です。<br>
E. pngなどの画像をsvgに変換するツールを利用したり、svgのimage要素でpngなどを取り込むことが出来るため写真などのデータも利用できるので、不正解です。
</dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_151">出題範囲の詳細</a></p>
  <div class="present">
    <p>LPI-Japan<br>中谷 徹</p>
  </div>
</div>
</div>

<div class="question">
<dl>
<dt>例題5.9「1.5.3 オフラインストレージ系 API 概要」</dt>
<dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_153">1.5.3 オフラインストレージ系 API 概要</a>」からの出題です。<br>
楽しみながら学習できる子供向けアプリをHTML5で開発したいが、どうしても時間のかかる処理がある。子供に敬遠されないよう、その処理をバックグラウンドで処理し、画面上は別の操作を進められるようにしたい。実現するためのAPIは次のうちどれか。２つ選びなさい。</dd>
<dd>
<ul class="option">
<li>Service Workers</li>
<li>Background Tasks</li>
<li>Web Workers</li>
<li>Multiple Threads</li>
<li>Nomad Workers</li>
</ul>
</dd>
</dl>
<p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
<p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>答え<span> A、C</span></dt>
    <dd>A. Service Workers と C. Web Workers は Javascript で処理をバックグラウンドで実行できるAPIです。<br>
C. Web Workers は、複数の処理をWorkerという単位で並列処理することができるため、計算処理や大きなファイルアクセスなど時間のかかる処理をバックグランドで実行し、アプリのユーザビリティを向上できます。<br>
A. Service Workers は、Application Cacheに代わるオフライン処理のAPIですが、Push API, fetch を
併用して、バックグラウンド処理と同期して同様の処理を実現します。<br>
選択肢B、DのようなAPIはありません。<br>

E. Nomad Workers は、インターネットやモバイルデバイスの進化により増加した、働く場所を特定しない人たちの事です。</dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_153">出題範囲の詳細</a></p>
  <div class="present">
    <p>LPI-Japan<br>中谷 徹</p>
  </div>
</div>
</div>
<div class="question">
<dl>
<dt>例題5.8「1.5.1 マルチメディア・グラフィックス系API概要」</dt>
<dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_151">1.5.1 マルチメディア・グラフィックス系API概要</a>」からの出題です。<br>
動画の配信に、HLS、MPEG-DASHなどを Media Source Extensions(MSE) APIで呼び出すストリーミング配信技術が主流となっているが、そのメリットは次のうちどれか。３つ選びなさい。</dd>
<dd>
  <ul class="option">
	<li>動画全体のダウンロードの完了待たずに動画再生が開始可能である。</li>
	<li>ブラウザのみで再生でき、専用プラグインをインストールする必要がない。</li>
	<li>ライブストリーミング配信動画でも、いつでも最初から視聴できる。</li>
	<li>ブラウザ標準対応のストリーミング技術を利用すると動画が高画質に再生できる。</li>
	<li>ブラウザ側にファイルとして残らないため、著作権の保護の観点でも有利である。</li>
  </ul>
</dd>
</dl>
<p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
<p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>正解<span> A、B、E</span></dt>
    <dd>HTML5で使用できるストリーミング技術であるHLS(HTTP Live Streaming), MPEG-DASH(DASH: Dynamic Adaptive Streaming over HTTP)は Media Source Extensions（MSE) といった技術を使用することで、従来のようなファイルのダウンロードを待たずに動画の再生を開始でき、利用者側にファイルとして残さないためセキュアでもあります。<br>また、HTTPサーバーのみで配信でき、ブラウザのみで再生できる点が主流となる理由です。ライブ配信の動画は配信時間を過ぎれば視聴できません。また、動画の画質はプロトコルに依存しないため、CとDは不正解です。</dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_151">出題範囲の詳細</a></p>
  <div class="present">
    <p>LPI-Japan<br>中谷 徹</p>
  </div>
</div>
</div>
<div class="question">
<dl>
<dt>例題5.7「1.5.2 デバイスアクセス系 API 概要」</dt>
<dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_152">1.5.2 デバイスアクセス系 API 概要</a>」からの出題です。<br>
次のデバイスアクセス系のAPIの内、デバイス付近の照度を取得するものは次のうちどれか。</dd>
<dd>
  <ul class="option">
	<li>Geolocation API</li>
	<li>Device Light API</li>
	<li>Ambient Light Event</li>
	<li>Device Orientation Event</li>
	<li>Screen Luminos API</li>
  </ul>
</dd>
</dl>
<p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
<p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>正解<span> C</span></dt>
    <dd>Ambient Light Event は、デバイス付近の照度（光量レベル）を取得するAPIで、カーナビのようなアプリで夜間やトンネル内で輝度を落とすなどの機能をもたせたい場合などに使用できます。<br>
A.のGeolocation APIは、位置情報を取得するAPIなので、不正解です。<br>
B.のようなAPIはありません。不正解です。<br>
D.のDevice Orientation Eventは、加速度センサーから得られる、デバイスの向き、傾き、移動時の加速度などを取得できます。<br>
E.はスクリーンの輝度と言う意味ですが、このようなAPIはありません。不正解です。</dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_152">出題範囲の詳細</a></p>
  <div class="present">
    <p>LPI-Japan<br>中谷 徹</p>
  </div>
</div>
</div>
<div class="question">
<dl>
<dt>例題5.6「1.5.2 デバイスアクセス系 API 概要」</dt>
<dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_152">1.5.2 デバイスアクセス系 API 概要</a>」からの出題です。<br>
Geolocation API の説明として正しいものは次のうちどれか。正しいものをすべて選びなさい。</dd>
<dd>
  <ul class="option">
	<li>GPS機能のないデスクトップPCでは位置情報を取得できない。</li>
	<li>インターネットに接続していれば、必ず位置情報を取得できる。</li>
	<li>取得した位置情報の精度は、APIからは判断できない。</li>
	<li>緯度と経度の他に、方角と速度も取得できる。</li>
	<li>取得できる位置情報は緯度と経度のみで、高度は取得できない。</li>
  </ul>
</dd>
</dl>
<p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
<p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>正解<span> D</span></dt>
    <dd>Geolocation API では、GPS、WiFi、IPアドレス、基地局などからデバイスの位置情報を、緯度、経度、高度及びそれらの誤差、方角、速度で取得できます。<br>
したがって、AとCとEは間違いです。Bは、インターネットに接続していれば、位置情報を取得するためのリソースはありますが、デバイスの利用者が位置情報の取得を許可していない場合には取得できません。位置情報はプライバシーに関わる情報であるため、一般に利用者によって拒否できるようになっています。</dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_152">出題範囲の詳細</a></p>
  <div class="present">
    <p>LPI-Japan<br>中谷 徹</p>
  </div>
</div>
</div>
<div class="question">
<dl>
<dt>例題5.5「1.5.3 オフラインストレージ系 API 概要」</dt>
<dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_153">1.5.3 オフラインストレージ系 API 概要</a>」からの出題です。<br>
オフラインWebアプリケーションのMIME設定を行なうために使用されるファイルを2つ選択してください。<br>
ただし、ApacheをWebサーバとして使用しているものとします。</dd>
<dd>
<ul class="option">
<li>.htaccess</li>
<li>Manifest</li>
<li>index.html</li>
<li>manifest</li>
<li>httpd.conf</li>
</ul>
</dd>
</dl>
<p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
<p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>答え<span> A、E</span></dt>
    <dd>オフラインWebアプリケーションとしてWebページを提供する場合、MANIFESTファイルについては"text/cache-manifest"というMIMEタイプが使用されます。<br>
	しかし、Apacheでは初期状態でこのMIMEタイプの設定が無いため、設定に追加する必要があります。<br>
	MIMEの設定は通常、 .htaccess(A)か、httpd.conf(E)のどちらかで行ないます。<br>
	どちらで行なうべきかは、そのWebサーバの設定によります。<br>
	その他の選択肢では、MIMEの設定は行なえません。<br>
	Apache以外のWebサーバ、例えばnginxではmime.typesで設定するなど、Webサーバによって設定を行なうファイルは異なります。</dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_153">出題範囲の詳細</a></p>
  <div class="present">
    <p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル２認定者　高井 歩 氏</p>
  </div>
</div>
</div>
<div class="question">
<dl>
<dt>例題5.4「1.5.3 オフラインストレージ系 API 概要」</dt>
<dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_153">1.5.3 オフラインストレージ系 API 概要</a>」からの出題です。<br>
キャッシュマニフェストファイルで、必ずネットワーク経由でアクセスするリソースを記述するセクションは次のうちどれか。正しいものを一つ選択しなさい。</dd>
<dd>
  <ul class="option">
	<li>CACHE</li>
	<li>NETWORK</li>
	<li>FALLBACK</li>
	<li>ONLINE</li>
	<li>NOCACHE</li>
  </ul>
</dd>
</dl>
<p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
<p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>正解<span> B</span></dt>
    <dd>オフラインWebアプリケーションでも、ネットワークに接続してサーバ上の最新のリソースを利用したいケースもあります。<br>
NETWORKセクションにリソースを列挙すると、指定したリソースはサーバから取得して使用します。<br>
NETWORKセクションでリソースを指定しないと、ネットワーク接続が有効でもオフラインキャッシュ内のリソースを使用します。<br>
NETWORKセクションで指定したリソースを取得できない場合、FALLBACKで代替リソースを指定していてもエラーになります。<br>
FALLBACKで代替できるのはNETWORKセクションで指定されていないリソースに限ります。</dd>
<dd>その他の選択肢については以下の通りです。<br>
A.キャッシュするリソースを指定するセクションです。<br>
C.リソースにアクセスできない場合の代替リソースを指定するセクションです。<br>
D.ONLINEというセクションはありません。<br>
E.NOCACHEというセクションはありません。</dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_153">出題範囲の詳細</a></p>
  <div class="present">
    <p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル２認定者　高井 歩 氏</p>
  </div>
</div>
</div>
<div class="question">
<dl>
<dt>例題5.3「1.5.3 オフラインストレージ系 API 概要」</dt>
<dd class="lead">
    レベル1の出題範囲「<a href="http://html5exam.jp/outline/objectives_lv1_v2.html#lv1_153">1.5.3 オフラインストレージ系 API 概要</a>」からの出題です。<br>
オフラインウェブアプリケーションにおけるマニフェストファイルをウェブページに関連づけるには、どの要素の何属性を使用するか？<br>
正しいものを一つ選びなさい。<br>
</dd>
<dd>
<ul class="option">
	<li>meta要素のcontent属性</li>
	<li>meta要素のhttp-equiv属性</li>
	<li>link要素のhref属性</li>
	<li>link要素のmanifest属性</li>
	<li>html要素のmanifest属性</li>
</ul>
</dd>
</dl>
<p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
<p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>答え<span> E</span></dt>
    <dd>オフラインウェブアプリケーションにおけるマニフェストファイルは、html要素のmanifest属性にそのURLを指定することで関連づけます。<br>
	よって、答えはEです。</dd>
	<dd>マニフェストファイルの文字コードは「UTF-8」で、MIMEタイプは「text/cache-manifest」、拡張子は「.appcache」が使用されます。</dd>
  </dl>
    <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_153">出題範囲の詳細</a></p>
  <div class="present">
    <p>例題解説の提供：HTML5アカデミック認定校　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>
     HTML5レベル１認定者　大藤 幹 氏</p>
  </div>
</div>
</div>
<div class="question">
<dl>
<dt id="lv1_5_2">例題5.2「1.5.3 オフラインストレージ系 API 概要」</dt>
<dd class="lead">
    レベル1の出題範囲「<a href="http://html5exam.jp/outline/objectives_lv1_v2.html#lv1_153">1.5.3 オフラインストレージ系 API 概要</a>」からの例題を解説します。<br />
    オフラインウェブアプリケーションにおけるマニフェストファイルに関する記述として、間違っているものを１つ選びなさい。
</dd>
<dd>
<ul class="option">
<li>一行目には、「CACHE MANIFEST」と記述する必要がある。</li>
<li>#から始まる行はコメントとなる。</li>
<li>対象ファイルとして拡張子が.html .html .cssのファイルのみ指定可能である。</li>
<li>CACHE、FALLBACK、NETWORKの３つのセクションが存在する。</li>
<li>マニフェストファイルは、通常Webサーバ上に配置する。</li>
</ul>
</dd>
</dl>
<p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
<p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>答え<span>C</span></dt>
    <dd><p>マニフェストファイルは、ユーザがオフラインウェブアプリケーションを利用するにあたって、どのファイルをキャッシュするかなどの指定が記述されたファイルです。<br>
マニフェストファイルは、1行目にCACHE MANIFESTと記述されているという決まりがあり、セクション毎に対象となるファイルを指定していきます。</p>
<p>CACHE、FALLBACK、NETWORKの３つのセクションが存在し、たとえば、CACHEセクションに記載されたファイルは、キャッシュされるファイルとなりオフラインでも閲覧できるファイルとなります。</p>
<p>指定できるファイルは.htmlファイルや.cssのファイル以外にも、Javascriptのコードファイルや、PNGなどの画像ファイルを指定する事ができます。<br>
よって、Cに関する記述は間違いで、この問題の正解はCとなります。</p>
<p>A,B,D,Eは正しい内容となります。</p>
  </dd>
  </dl>
    <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_153">出題範囲の詳細</a></p>
  <div class="present">
    <p>例題解説の提供：<a href="http://media-sketch.com/" target="_blank" >メディアスケッチ株式会社</a><br>
      代表取締役　兼　株式会社コーデセブン　取締役CTO　伊本 貴士 氏<br>
      ITコンサルタント業を中心に、Webサービスの開発や、オープンソースシステムの構築・保守なども行っている。</p>
  </div>
</div>
</div>
  <div class="question">
    <dl>
      <dt id="lv1_5_1">例題5.1「1.5.3 オフラインストレージ系 API 概要」</dt>
      <dd class="lead">
          レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_153">1.5.3 オフラインストレージ系 API 概要</a>」からの例題を解説します。<br />
          一般的にオフラインアプリケーションを動作させるために行う事として、正しいものを一つ選びなさい。
      </dd>
      <dd>
        <ul class="option">
          <li>Webコンテンツをバーチャルホストに配置する。</li>
          <li>Webサーバにキャッシュマニフェストファイルを置く。</li>
          <li>Webサーバにて、オフラインアプリケーション用のポートへのアクセスを新たに許可する。</li>
          <li>クライアント側にて、オフラインアプリケーション動作のためのソフトウェアをインストールしておく。</li>
          <li>クライアント側にて、データ保存のためのオフラインアプリケーション専用のディスク領域を設定し確保しておく。</li>
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
  <div class="answer">
    <dl>
      <dt>答え<span>B</span></dt>
      <dd>オフラインアプリケーションは、動作させるコンテンツとマニフェストファイルの二つを用意する必要があります。
        マニフェストファイルには、アプリケーションを動作させるために必要なJavascriptファイルやスタイルシートなどが記述されており、それに従って動作に必要なファイルをオフラインでも動作できるように全てクライアントにダウンロードしておきます。
        よって、答えはBです。
        Aのバーチャルホスト上にあるかどうかは、オフラインアプリケーションは関係ありません。よって間違いです。
        オフラインアプリケーションは、新たにポートを必要とすることはありませんので、Cは間違いです。
        D,Eのように、オフラインアプリケーションを動作にあたって、クライアント側でなにか事前に準備しておく必要はなく、オフラインアプリケーション対応のブラウザがあれば問題ありません。
        そして、サーバ側でマニフェストファイルなどの準備や設定を行います。</dd>
    </dl>
    <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_153">出題範囲の詳細</a></p>
  <div class="present">
    <p>例題解説の提供：<a href="http://media-sketch.com/" target="_blank" >メディアスケッチ株式会社</a><br>
      代表取締役　兼　株式会社コーデセブン　取締役CTO　伊本 貴士 氏<br>
      ITコンサルタント業を中心に、Webサービスの開発や、オープンソースシステムの構築・保守なども行っている。</p>
  </div>