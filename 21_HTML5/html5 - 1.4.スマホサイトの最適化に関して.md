<h2>HTML5プロフェッショナル認定試験レベル1 サンプル問題</h2>
<section>
<div class="section-inner">
<div class="sample-box">
  <p class="lead">例題解説とその内容については、例題提供者の監修です。内容や試験問題に関わるお問い合わせにつきましては、LPI-Japan事務局ではお応えできませんのでご了承ください。<br>例題解説のご提供者さまを募集中です。<a href="mailto:&#109;&#97;&#105;&#108;&#64;&#108;&#112;&#105;&#46;&#111;&#114;&#46;&#106;&#112;">LPI-Japan事務局</a>までぜひご投稿ください。選ばれた方の例題解説は本サイトに掲載させていただきます。</p>
  <h3 id="lv1_4">1.4 レスポンシブWebデザイン</h3>
<!--
  <div class="question">
    <dl>
      <dt>問題4.★ ★</dt>
      <dd class="lead">★</dd>
      <dd>
        <ul class="option">
          <li>★</li>
          <li>★</li>
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><a href="★.html"><img width="5" height="8" src="../images/common/arrow-right2.png" alt="" /> 答えはこちら</a></p>
  </div>
-->
  <div class="question">
    <dl>
      <dt>例題4.15 「1.4.3 スマートフォンサイト最適化」</dt>
      <dd class="lead">
        レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_143">1.4.3 スマートフォンサイト最適化</a>」からの出題です。<br>
        ブラウザのブックマークやタブに表示するアイコンの設定として正しいものを２つ選びなさい。
      </dd>
      <dd>
        <ul class="option">
        <li>&lt;link rel="icon" href="/favicon.png"&gt;</li>
        <li>&lt;link rel="android-touch-icon" href="/favicon.png"&gt;</li>
        <li>&lt;link rel="apple-touch-icon" href="/favicon.png"&gt;</li>
        <li>&lt;link rel="apple-touch-icon-precomposed" href="/favicon.png"&gt;</li>
        <li>&lt;link rel="shortcut icon" href="/favicon.png"&gt;</li>
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>正解<span> A、E</span></dt>
    <dd>
      正解のA、Eは Microsoft IE5の「お気に入り」に導入されたfavicon.icoを表示する機能で、一般にファビコン(Favorite Icon)と呼ばれています。指定したアイコンは、ブラウザにより異なりますが、タブやアドレスバーに表示されるので識別しやすくなります。<br>
HTML5の仕様に正式に登録されているのは選択肢Aのrel="icon"のみです。名残で"shortcut icon"でも動作しますが、"shortcut"に意味はありません。アイコンに使用できるファイルの種類はブラウザにより異なるので
.ico、.png、.gifが無難です。<br>
選択肢CとDは、iOSのタッチアイコンの設定です。<br>
共有ボタン([↑]のアイコン)から「ホーム画面に追加」を選択することで、ホーム画面にアプリと同じようにサイトのアイコンを表示できます。最近ではこのアイコンもファビコンに分類されているようです。<br>
選択肢Cのrel="apple-touch-icon"では、アイコンはiOSに加工され、角が丸く表示されますが、選択肢Dの rel="apple-touch-icon-precomposed"では、加工されずに表示されます。<br>
Android でも動作しますが、デバイスのサイズにより挙動が異なるので、複数のサイズを用意しておく必要があります。
なお、選択肢Bの指定はありません。

    </dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_143">出題範囲の詳細</a></p>
  <div class="present">
    <p>例題解説の提供：LPI-Japan<br>中谷　徹</p>
  </div>
</div>

  </div>  
   <div class="question">
    <dl>
      <dt>例題4.14 「1.4.3 スマートフォンサイト最適化」</dt>
      <dd class="lead">
        レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_143">1.4.3 スマートフォンサイト最適化</a>」からの出題です。<br>
        CSSスプライトの特徴として正しくない説明を選択してください。
      </dd>
      <dd>
        <ul class="option">
        <li>アイコンなどの複数の画像を1枚の画像に配置する</li>
        <li>使用する画像パーツをCSSで画像の座標とサイズを指定して表示させる</li>
        <li>CSSスプライトの画像はキャッシュされることがない</li>
        <li>画像の読み込みが一度で完了するため、ページ表示の高速化につながる</li>
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>正解<span> C</span></dt>
    <dd>
      アイコンなどの小さな画像は、HTTPで1ファイルごとにダウンロードされるため、数が多くなるとページの表示速度に影響を与えます。<br>
そこで、小さな画像をまとめて1枚の画像に配置することで、まとめてダウンロードし、CSSの指定で表示する技法をCSSスプライトと呼びます。<br>
1枚の画像に複数のアイコンが含まれるので、表示するためには工夫が必要です。<br>
CSSのbackground-imageを使って画像を表示することになりますが、background-positionでまとめた画像のなかの位置を、widthとheightで切り出すサイズを指定します。<br><br>

CSSスプライトのデメリットとしては、個別の画像を変更するたびにまとめた画像ファイルも変更が必要になる点と、CSSで表示位置とサイズを指定する手間が挙げられます。<br>
現在では、複数の画像を与えると、自動的にまとめた画像とCSSのサンプルを作成してくれるツールもありますので有効活用すると良いでしょう。
    </dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_143">出題範囲の詳細</a></p>
  <div class="present">
    <p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル２認定者　高井 歩 氏</p>
  </div>
</div>

  </div>
  <div class="question">
    <dl>
      <dt>例題4.13 「1.4.1 マルチデバイス対応ページの作成」</dt>
      <dd class="lead">
        レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_141">1.4.1 マルチデバイス対応ページの作成</a>」からの出題です。<br>
        フルードグリッドの特徴として正しくないものを選択してください。
      </dd>
      <dd>
        <ul class="option">
        <li>グリッド幅、グリッドの数をウインドウ幅に合せて変更する</li>
        <li>メディアクエリーを使用してCSSを切り替える</li>
        <li>グリッド幅を相対値で指定する</li>
        <li>画像の大きさをウインドウ幅に合せて変更する</li>
        <li>かならずしもJavaScriptを必要としない</li>
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>正解<span> D</span></dt>
    <dd>
      レスポンシブWebデザインで良く使用される、フルードグリッドに関する問題です。<br>
      ウィンドウ幅に合せて流動的にデザインを変更するリキッドレイアウトと、ウィンドウもしくはコンテンツ領域をいくつかのグリッドと呼ばれる領域に分割してレイアウトの基準とするグリッドシステムを合せたものをフルードグリッドと呼びます。<br>
      フルードグリッドでは、画像の大きさについては明示的に扱いません。ウィンドウ幅に合せて変更する技術はフルードイメージと呼ばれます。<br>
      従ってフルードグリッドの特徴として、D.は正しくありません。<br>
      その他の選択肢については、以下の通りです。<br>
      A. 通常のグリッドシステムでは、グリッド幅やグリッドの分割数は固定ですが、フルードグリッドでは、幅、数ともにウィンドウ幅に合せて変化します。<br>
      B. グリッドの数の切り替えには、CSSのメディアクエリーを使って指定します。<br>
      C. グリッドの幅をウィンドウ幅に合せて変化させるためには、グリッド幅を相対値で指定します。<br>
      E. JavaScriptを使って実現することもできますが、CSSだけでも実現可能です。
    </dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_141">出題範囲の詳細</a></p>
  <div class="present">
    <p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル２認定者　高井 歩 氏</p>
  </div>
</div>

  </div>
  <div class="question">
    <dl>
      <dt>例題4.12 「1.4.1 マルチデバイス対応ページの作成」</dt>
      <dd class="lead">
        レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_141">1.4.1 マルチデバイス対応ページの作成</a>」からの出題です。<br>
        フルードイメージ(Fluid Image)を実現するためのHTMLおよびCSSの記述として正しい組み合わせを選択してください。
      </dd>
      <dd>
        <ul class="option">
        <li>img { max-width:100%; }<br>
        &lt;img src="images/sample.jpg"&gt;</li>
        <li>img { max-height:100%; }<br>
        &lt;img src="images/sample.jpg"&gt;</li>
        <li>img { max-width:100%; max-height:100% }<br>
        &lt;img src="images/sample.jpg"&gt;</li>
        <li>img { max-width:100%; }<br>
        &lt;img src="images/sample.jpg" width="300" height="200"&gt;</li>
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>正解<span> A</span></dt>
    <dd>
      フルードイメージ(Fluid Image)は画像サイズをウインドウ幅に応じて変化させる手法です。<br>
      通常、imgタグにより表示された画像がウインドウ幅を越える幅、高さである場合、スクロールしないと全てを見ることができません。<br>
      フルードイメージでは、ウインドウ幅に合せて自動的に画像の表示幅、高さが調節されます。<br>
      フルードイメージを使用することで、レスポンシブWebデザインなどで、ウインドウ幅に合せた画像のレイアウトがおこなえます。<br>
      フルードイメージを実現するためには、<br>
・imgタグにwidth,height属性を指定しない。<br>
・対象となるHTML要素にCSSのmax-widthプロパティを使用して、ウインドウ幅に対するサイズを指定する。<br>
      の2点が必要になります。<br>
      width,height属性を指定すると、画面幅はウインドウ幅に応じて変化しますが、高さが変わらないため、画像の縦横比が変化してしまいます。<br>
      max-widthプロパティのかわりに、max-heightプロパティは使用できません。<br>
      実際にいくつかのWebブラウザで試してみると、ウインドウ幅に応じて高さが変化しないことが確認できます。
    </dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_141">出題範囲の詳細</a></p>
  <div class="present">
    <p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル２認定者　高井 歩 氏</p>
  </div>
</div>
  </div>
  <div class="question">
    <dl>
      <dt>例題4.11 「1.4.2 メディアクエリ」</dt>
      <dd class="lead">
        レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_142">1.4.2 メディアクエリ</a>」からの出題です。<br>
        次のようなHTMLとCSSの組み合わせがある場合に、後述する設問に解答しなさい。
      </dd>
      <dd>
        <div class="box">
          <pre>
          <code>【HTML】
&lt;body&gt;
&lt;div id="wrap"&gt;sample&lt;/div&gt;
&lt;/body&gt;
【CSS】
body, div {
margin: 0;
padding: 0;
}
‪#‎wrap‬ {
background-color: ‪#‎FF0000‬;
width: 100vmin;
height: 100vmin;
}
@media screen and (max-width: 1024px) and (orientation:landscape) {
#wrap {
width: 100vmax;
height: 100vmin;
}
}
@media screen and (max-width: 480px) and (orientation:portrait) {
#wrap {
width: 100vmin;
height: 100vmax;
}
}</code></pre>
        </div>
      </dd>
      <dd>
        Webブラウザで表示した際の動作に関する記述で、間違っているものを次の選択肢から1つ選びなさい。
      </dd>
      <dd>
        <ul class="option">
        <li>Webブラウザの表示領域の幅が400ピクセルのとき、表示領域が縦長でも横長でも背景色は全面赤色で表示される。</li>
        <li>Webブラウザの表示領域が幅800ピクセル、高さ600ピクセルのとき、div要素は表示領域より幅が大きくなる。</li>
        <li>Webブラウザの表示領域が幅800ピクセル、高さ1,200ピクセルのとき、下部に400ピクセルの余白ができる。</li>
        <li>Webブラウザの表示領域が幅1,200ピクセル、高さ1,400ピクセルのとき、下部に200ピクセルの余白ができる。</li>
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>正解<span> B</span></dt>
    <dd>
      例題で使用している単位、vminは表示領域の幅か高さのいずれか小さい方に対するパーセンテージを表し、vmaxは大きい方に対するパーセンテージを表します。<br>
      1つめの#wrapセレクタは幅か高さの小さい方のサイズで正方形を作成します。<br>
      2つめの#wrapセレクタは幅が1,024ピクセル以下で横長の場合に全面を覆う長方形を作成します。<br>
      3つめの#wrapセレクタは幅が480ピクセル以下で縦長の場合に全面を覆う長方形を作成します。<br>
      選択肢Aの場合、表示領域が横長のときは2つめのセレクタが、縦長のときは3つめのセレクタが適用されるので、‪#‎wrapの背景色である赤が全面に表示されます‬。<br>
      選択肢Cの場合、表示領域の幅は2つめのセレクタの範囲ですが、縦横比が縦長なので2つめのセレクタは適用されません。結局デフォルトの1つめのセレクタが適用されるので下部に余白ができることになります。<br>
      選択肢Dもデフォルトの1つめのセレクタが適用されます。
    </dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_142">出題範囲の詳細</a></p>
  <div class="present">
    <p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル２認定者　林拓 也 氏</p>
  </div>
</div>
  </div>
  <div class="question">
    <dl>
      <dt>例題4.10 「1.4.1 マルチデバイス対応ページの作成」</dt>
      <dd class="lead">
        レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_141">1.4.1 マルチデバイス対応ページの作成</a>」からの出題です。<br>
        今後の仕様化が検討されているpicture要素についての記述で不適切なものを1つ選びなさい。なお本問題の仕様はHTML 5.1 2015年10月8日ワーキングドラフトに基づくものとする。
      </dd>
      <dd>
        <ul class="option">
        <li>picture要素ではsource要素、img要素を組み合わせて、表示領域のサイズに応じて複数の画像を指定できる。</li>
        <li>source要素ではmedia属性でメディアクエリ（Media Queries）を指定できる。</li>
        <li>picture要素には指定が必須の属性は無い。</li>
        <li>source要素の属性はグローバル属性を除くとsrcset属性、sizes属性、media属性、type属性の4つがある。</li>
        <li>img要素でもsrcset属性やsize属性が利用できるが、srcset属性を指定した場合src属性は指定してはいけない。</li>
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>正解<span> E</span></dt>
    <dd>
      picture要素は0個以上のsource要素とそれに続くimg要素を子として持ちます。<br>
      source要素では一般に、表示すべき画像をsrcset属性で、表示する条件をmedia属性で指定します。
        <pre>
        <code>
      例1）
&lt;picture&gt;
&lt;source media="(min-width: 45em)" srcset="large.jpg"&gt;
&lt;source media="(min-width: 32em)" srcset="med.jpg"&gt;
&lt;img src="small.jpg" alt="HTML5プロフェッショナル"&gt;
&lt;/picture&gt;
        </code>
        </pre>
      2015年10月8日ワーキングドラフトではimg要素でもsrcset属性やsize属性が利用できるようになっています。<br>
      img要素ではsize属性で指定されたサイズを基に、srcset属性で指定された画像の候補リストから適切な画像が表示されます。
        <pre>
        <code>
      例2）
&lt;img sizes="100vw" srcset="wolf-400.jpg 400w, wolf-800.jpg 800w, 
wolf-1600.jpg 1600w" src="wolf-400.jpg" alt="The rad wolf"&gt;
        </code>
        </pre>
      細かい仕様は今後変わっていくと思われるので、現状は大まかなところを把握しておけばよいでしょう。
    </dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_141">出題範囲の詳細</a></p>
  <div class="present">
    <p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル２認定者　林拓 也 氏</p>
  </div>
</div>
  </div>
  <div class="question">
    <dl>
      <dt>例題4.9 「1.4.3 スマートフォンサイト最適化」</dt>
      <dd class="lead">
      		レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_143">1.4.3 スマートフォンサイト最適化</a>」からの出題です。<br>
      		HTML外部のjavascriptファイルを読み込む際に、非同期で読み込みをおこないWebページのレンダリングをブロックさせない属性を選択してください。
      </dd>
      <dd>
        <ul class="option">
		    <li>non-block</li>
		    <li>defer</li>
		    <li>async</li>
		    <li>sync</li>
		    <li>lazy</li>
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>正解<span> C</span></dt>
    <dd>
		通常、&lt;script&gt;タグが読み込まれると、Webブラウザはページの描画を一時停止してJavascriptの実行を先に行ないます。<br>
		その分ページの描画が遅れるため、&lt;script&gt;タグをhtmlの&lt;/body&gt;タグ直前に置いて、ページ描画を先に行なうなどの工夫がされてきました。<br>
		HTML5では、&lt;script&gt;タグにasync属性(C.)を追加することで、外部ファイルの読み込みと、ページ描画を非同期に行なうことができます。<br>
		その他の選択肢については以下の通りです。<br>
		A,D,Eはそのような属性はありません。<br>
		Bのdeferは、これまでwindow.onloadイベントや、jQueryのreadyメソッドを使用していたように、UIの更新完了時に実行されるよう指示をする属性です。
    </dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_143">出題範囲の詳細</a></p>
  <div class="present">
    <p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル２認定者　高井 歩 氏</p>
  </div>
</div>

  </div>
    <div class="question">
    <dl>
      <dt>例題4.8「1.4.2 メディアクエリ」</dt>
      <dd class="lead">
			レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_142">1.4.2 メディアクエリ</a>」からの出題です。<br>
			メディアクエリで使用出来る解像度の単位として誤っているものを2つ選択してください。
      </dd>
      <dd>
        <ul class="option">
		    <li>dpo</li>
		    <li>dpi</li>
		    <li>dpm</li>
		    <li>dpcm</li>
		    <li>dppx</li>
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>正解<span> A,C</span></dt>
    <dd>
    	スマートフォンや高解像度モニタの普及で、同じピクセル数で表示すると見た目の大きさが大きく異なることがあります。<br>
		そのような不具合を少なくするために、メディアクエリで画面の解像度を指定してスタイルを変更することができます。<br>
		画面解像度の指定は、1インチあたりのドット数であるdpi(B.)、1センチメートルあたりのドット数であるdpcm(D.)、およびピクセル数あたりのドット数を表すdppx(E.)を使用することができます。<br>
		ピクセルとドットの関係がわかりづらいですが、iPhoneのRetinaディスプレイなど高解像度な画面では、論理的な1ピクセルをより細かいドットの組み合わせで表示することがあります。<br>
		たとえば、2dppxであれば、1ピクセルを2×2の4ドットで表示することになります。<br>
		その他の選択肢は単位として使用できません。
	</dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_142">出題範囲の詳細</a></p>
  <div class="present">
    <p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル２認定者　高井 歩 氏</p>
  </div>
</div>
  </div>
  <div class="question">
    <dl>
      <dt>例題4.7「1.4.1マルチデバイス対応ページの作成」</dt>
      <dd class="lead">
			レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_141">1.4.1マルチデバイス対応ページの作成</a>」からの出題です。<br>
			デバイスの画面幅に合せて表示領域を指定する場合に設定するviewportのcontent属性を選択してください。
      </dd>
      <dd>
        <ul class="option">
		    <li>content="device-width"</li>
		    <li>content="width=device-portrait" </li>
		    <li>content="width=device-horizontal"</li>
		    <li>content="width" </li>
		    <li>content="width=device-width" </li>
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>正解<span> E </span></dt>
    <dd>表示領域のサイズや拡大縮小を設定する、viewportに関する問題です。<br>
		スマートフォン上のブラウザで表示する際には、基本的にPC上で横幅980pxのブラウザで表示したのと同じような見た目になるように扱われます。<br>
		しかし、この設定では縮小表示になってしまい、文章が読みにくくなることがあります。<br>
		&lt;meta name=&quot;viewport&quot; content=&quot;width=device-width&quot;&gt; (E.)<br>
		と記述することで、スマートフォンのデバイスの横幅で描画が行なわれるようになります。<br>
		他の選択肢は間違いです。<br>
		正しい記述はcontent=&quot;&quot;の中にwidth=device-widthが入りますので注意が必要です。</dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_141">出題範囲の詳細</a></p>
  <div class="present">
    <p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル２認定者　高井 歩 氏</p>
  </div>
</div>
  </div>
  <div class="question">
    <dl>
      <dt>例題4.6「1.4.3 スマートフォンサイト最適化」</dt>
      <dd class="lead">
			レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_143">1.4.3 スマートフォンサイト最適化</a>」からの出題です。<br>
			ターゲットに高解像度なスマートフォンを含むWebサイトを作成する場合に、使用する画像について気をつけるべき点は何か。誤っているものを一つ選びなさい。
      </dd>
      <dd>
        <ul class="option">
			<li>2倍程度のサイズの高解像度画像を用意し、imgタグのwidth,heightの値を元の画像サイズに設定する</li>
			<li>背景画像の場合はdevicePixelRatioの値によってbackground-imageを切り替える</li>
			<li>低解像度のスマートフォン向けには負荷を減らすため低解像度の画像を使用する</li>
			<li>写真などの複雑な画像で無ければSVGやCSS3による画像を使用する</li>
			<li>ファイル名に、'@2x'を追加した(例:img@2x.png)高解像度画像を用意すればデバイスにあわせて自動的に選択される</li>
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
  <div class="answer">
    <dl>
      <dt>正解<span> E </span></dt>
	<dd>高解像度なディスプレイを持つスマートフォンではPCや低解像度スマートフォン向けに用意した画像がぼやけたような感じになってしまうことがあります。<br>
		高解像度デバイスでは低解像度デバイスの1ピクセルあたり、1.5から2ピクセル以上で表示します。<br>
		このとき画像の拡大処理が行なわれますが、結果としてぼやけたようになってしまうことがあります。</dd>
		<dd>選択肢のうち、対策として間違っているのは、E.のファイル名に'@2x'をつける、というものです。<br>
		これはiPhoneなどiOS向けのネイティブアプリを作成する場合の手法で、Webページでは効果がありません。</dd>
		<dd>その他の選択肢については以下の通りです。<br>
		A.通常より高解像度なサイズの画像を作成しておき、imgタグやスタイルでwidth,heightに元のサイズを指定することで鮮明に表示されます。<br>
		B.background-imageであれば、メディアクエリでmin-device-pixel-ratioを使用し、devicePixelRatioが1なら低解像度、1.5以上なら高解像度の画像を使用するように、スタイルを二つ定義します。<br>
		C.低解像度なスマートフォンで高解像度の画像を表示すると負荷が高くなります。B.のような工夫をしたり、JavaScriptやPHPなどを使ってimgタグのsrcを切り替えます。<br>
		D.ベクトル形式であるSVGやCSS3による画像は解像度に関係なく鮮明に表示されます。画像の内容によってはSVG,CSS3を選択すると良いでしょう。</dd>
    </dl>
    <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_143">出題範囲の詳細</a></p>
  <div class="present">
    <p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル２認定者　高井 歩 氏</p>
  </div>
  </div>
  </div>
  <div class="question">
    <dl>
      <dt>例題4.5「1.4.2 メディアクエリ」</dt>
      <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_142">1.4.2 メディアクエリ</a>」からの出題です。<br>
      メディアクエリを利用して、表示領域の幅に応じて3段階に背景色を切り替える仕組みを作成する。仕様は幅768ピクセル未満は赤、幅768ピクセル縲鰀1024ピクセルは緑、それより大きい場合は青とする。<br>
				以下のCSSで、1、2それぞれに入れる指定で適切なものを選択しなさい。</dd>
                <dd>
                <div class="box">
<pre>
<code>
body {
background-color: red;
}
@media screen and (　　　1　　　){
body {
background-color: green;
}
}
@media screen and (　　　2　　　){
body {
background-color: blue;
}
}
</code>
</pre>
</div>
                </dd>
                <dd>
                  <ul class="option">
					<li>1：min-width:768px、2：max-width:1024px</li>
					<li>1：max-width:768px、2：min-width:1024px</li>
					<li>1：min-width:768px、2：min-width:1025px</li>
					<li>1：max-width:1024px、2：max-width:767px</li>
                  </ul>
                </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
  <div class="answer">
    <dl>
      <dt>答え<span> C </span></dt>
                <dd>レスポンシブWebデザインでデバイスの表示領域に応じてCSSを切り替える場合、モバイル環境（小さい画面）をデフォルトとして設定し、大きな画面用の設定を追加していく形と、デスクトップ環境（大きい画面）をデフォルトとして設定し、小さな画面用の設定を追加していく形があります。<br>
				前者をモバイルファースト、後者をデスクトップファーストと呼びます。<br>
				問題のCSSではデフォルトのスタイルが赤になっているので、モバイルファーストの考え方で指定を行うことになります。<br>
				選択肢Cは、最小範囲が赤で、最低幅768ピクセルの場合が緑、最低幅1025ピクセルの場合が青という指定で、与えられた仕様に適ったものとなります。<br>
				選択肢Dはデスクトップファーストの指定になります。3段階に色が変化しますが、サイズと色の組み合わせが仕様と異なるので不適切です。</dd>
    </dl>
    <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_142">出題範囲の詳細</a></p>
  <div class="present">
    <p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル１認定者　林 拓也 氏</p>
  </div>
  </div>


  </div>
  <div class="question">
    <dl>
      <dt>例題4.4「1.4.2 メディアクエリ」</dt>
      <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_142">1.4.2 メディアクエリ</a>」からの出題です。<br>
      メディアクエリの記述として、間違っているものを１つ選びなさい。
      </dd>
      <dd>
        <ul class="option">
			<li>@media screen and (color) { ... }</li>
			<li>@media screen or (color) { ... }</li>
			<li>@media screen and (color), projection and (color) { ... }</li>
			<li>@media not screen and (color) { ... }</li>
			<li>@media only screen and (color) { ... }</li>
         </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
  <div class="answer">
    <dl>
      <dt>答え<span> B</span></dt>
		<dd>メディアクエリの構文において「or」というキーワードは使用できません。論理式におけるORは、カンマ(,)であらわします。「not」キーワードをメディアクエリの先頭に記述すると、条件（真と偽）が逆になります。「only」キーワードは、メディアクエリに未対応の古いブラウザに書式を無視させるためのもので、メディアクエリに対応したブラウザでは「only」キーワードがないものとして処理されます。</dd>
    </dl>
    <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_142">出題範囲の詳細</a></p>
  <div class="present">
    <p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル１認定者　大藤 幹 氏</p>
  </div>
  </div>
  </div>
  <div class="question">
    <dl>
      <dt>例題4.3 「1.4.3 スマートフォンサイト最適化」</dt>
      <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_143">1.4.3 スマートフォンサイト最適化</a>」からの出題です。<br>
      スマートフォンでホーム画面にWebページへのリンクを作成する場合に、アイコンとして使用される画像を指定するrel属性を二つ選びなさい。</dd>
      <dd>
        <ul class="option">
			<li>apple-touch-icon</li>
			<li>touch-icon</li>
			<li>apple-touch-icon-precomposed</li>
			<li>touch-icon-precomposed</li>
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
  <div class="answer">
    <dl>
      <dt>答え<span> A、C </span></dt>
		<dd>iOS端末、Android端末に関わらず、
		<pre>
        <code>
&lt;link rel=”apple-touch-icon” href=”アイコンファイル名” /&gt;
        </code>
        </pre>
	または
		<pre>
        <code>
&lt;link rel=”apple-touch-icon-precomposed” href=”アイコンファイル名” /&gt;
        </code>
        </pre>
	と記述します。<br>
	apple-touch-iconを指定すると元画像に対して、角丸処理などが自動的に行なわれることがあります。デザイン上、自動処理を行なわれたく無い場合には、apple-touch-icon-precomposedを指定します。<br>
	OSの種類やバージョンによって表示が異なることがあるので、表示確認は欠かせません。</dd>
    </dl>
    <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_143">出題範囲の詳細</a></p>
  <div class="present">
    <p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル１認定者　高井 歩 氏</p>
  </div>
  </div>
  </div>
  <div class="question">
    <dl>
      <dt id="lv1_4_2">例題4.2「1.4.2 メディアクエリ」</dt>
      <dd class="lead">
			レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_142">1.4.2 メディアクエリ</a>」からの例題を解説します。<br>
			CSS3におけるMedia Queries（メディアクエリ）に関して以下のような記述がある場合、中に記述しているbody要素に関するスタイルシートが適用される条件として正しいものを1つ選びなさい。
      </dd>
      <dd>
        <div class="box">
	      <pre>
          <code>@media screen and (max-width :640px) {
      body {
            background-color: blue;
            margin: 30px;
      }
}</code></pre>
        </div>
      </dd>
      <dd>
        <ul class="option">
			<li>端末における画面解像度の幅が、640px以上の時に適用される。</li>
			<li>端末における画面解像度の幅が、640px以下の時に適用される。</li>
			<li>ビューポート（ブラウザの表示領域）の幅が、640px以上の時に適用される。</li>
			<li>ビューポート（ブラウザの表示領域）の幅が、640px以下の時に適用される。</li>
			<li>環境に関わらず、いかなる条件下でも適用されない。</li>
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
  </div>
  <p class="answer_check"><span> 答えはこちら</span></p>
  <div class="answer">
    <dl>
      <dt>答え<span> D </span></dt>
	<dd>Media Queriesは、スタイルシートの適用条件にスクリーンサイズや端末の向きなどを指定できるCSS3の機能です。<br>
	問題にある記述ではmedia typeにscreen、media feature（媒体特性）にmax-widthとあるので、ビューポート（ブラウザの表示領域）の幅・最大640pxまでを適用の条件としています。<br>
	よって答えはDです。<br>
	Cの640px以上である事を条件に指定したい場合、media featureはmin-widthとなります。<br>
	A,Bにある、端末の画面解像度を条件とする場合は、media feature（媒体特性）にmin-device-width,max-device-widthと指定する必要があるので、ビューポートのサイズとの混同に注意してください。</dd>
    </dl>
    <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_142">出題範囲の詳細</a></p>
  <div class="present">
    <p>例題解説の提供：<a href="http://media-sketch.com/" target="_blank" >メディアスケッチ株式会社</a><br>
      代表取締役　兼　株式会社コーデセブン　取締役CTO　伊本 貴士 氏<br>
      ITコンサルタント業を中心に、Webサービスの開発や、オープンソースシステムの構築・保守なども行っている。</p>
  </div>
  </div>
  <div class="question">
    <dl>
      <dt>例題4.1「1.4.1 マルチデバイス対応ページの作成」</dt>
      <dd class="lead">
			レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_141">1.4.1 マルチデバイス対応ページの作成</a>」からの例題を解説します。<br>
			Luke Wroblewski氏が提唱した「Mobile First（モバイルファースト）」の説明として正しいものを選びなさい。
      </dd>
      <dd>
        <ul class="option">
          <li>HTML5をモバイルデバイスで高速に動作させるために考えられたアーキテクチャである。</li>
          <li>モバイルデバイスの種類や画面サイズに合わせて、それぞれ専用のWebコンテンツを作るという考え方である。</li>
          <li>モバイルデバイスでの表示を考えて、サイズなどをピクセル数ではなく%などの可変サイズで指定をするレイアウト手法の事である。</li>
          <li>クライアントのデバイスがPCなのかモバイルデバイスか判別が付かない場合に、モバイルデバイス用のページを表示させるという考え方である。</li>
          <li>マルチデバイス対応サイトにおいて、制約が多いモバイルサイトでの利用を優先的に設計・制作という考え方である。</li>
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
  </div>
  <p class="answer_check"><span> 答えはこちら</span></p>
  <div class="answer">
    <dl>
      <dt>答え<span>E</span></dt>
      <dd>「Mobile First（モバイルファースト）」は、マルチデバイス対応サイトにおいてモバイルデバイスの設計を優先的に考える考え方の事です。
        よって、答えはEです。
        モバイルデバイスの普及が背景にありますが、制約の多いモバイルデバイスで確認をしておくと、同じソースでPCとモバイルデバイスの両方に対応しやすいという利点もあります。
        
        Aは間違いです。動作速度とモバイルファーストは関係ありません。
        Bは間違いです。モバイルデバイスの種類や画面サイズ毎にWebコンテンツを作ると、作成の手間が大幅に増え、メンテナンスも大変なので通常の場合、あまり適切な手法とは言えません。
        Cはリキッドレイアウトに関する説明です。よって、間違いです。
        Dは間違いです。このような考え方はありませんし、一般的にモバイルデバイス以外のクライアントからのアクセスには、通常のPC用ページが表示されます。</dd>
    </dl>
    <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_141">出題範囲の詳細</a></p>
  <div class="present">
    <p>例題解説の提供：<a href="http://media-sketch.com/" target="_blank" >メディアスケッチ株式会社</a><br>
      代表取締役　兼　株式会社コーデセブン　取締役CTO　伊本 貴士 氏<br>
      ITコンサルタント業を中心に、Webサービスの開発や、オープンソースシステムの構築・保守なども行っている。</p>
  </div>
  </div>
</div>