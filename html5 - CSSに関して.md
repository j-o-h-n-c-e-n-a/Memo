<h2>HTML5プロフェッショナル認定試験レベル1 サンプル問題</h2>
<section>
<div class="section-inner">
<div class="sample-box">
  <p class="lead">例題解説とその内容については、例題提供者の監修です。内容や試験問題に関わるお問い合わせにつきましては、LPI-Japan事務局ではお応えできませんのでご了承ください。<br>例題解説のご提供者さまを募集中です。<a href="mailto:&#109;&#97;&#105;&#108;&#64;&#108;&#112;&#105;&#46;&#111;&#114;&#46;&#106;&#112;">LPI-Japan事務局</a>までぜひご投稿ください。選ばれた方の例題解説は本サイトに掲載させていただきます。</p>
<h3 id="lv1_2">1.2 CSS</h3>
<!--
<div class="question">
<dl>
<dt>例題2.★「★」</dt>
<dd>
★
</dd>
<dd>
<ul class="option">
	<li>★</li>
</ul>
</dd>
</dl>
  <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><a href="lv1_2_★.html"><img width="5" height="8" src="../images/common/arrow-right2.png" alt="" /> 答えはこちら</a></p>
</div>
-->
         <div class="question">
          <dl>
            <dt>例題2.22「1.2.2 CSSデザイン」</dt>
            <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_122">1.2.2 CSSデザイン</a>」からの出題です。<br>
            親要素のCSSプロパティの設定を子要素に強制的に継承する際に指定する値は次のうちどれか。
            </dd>
            <dd>
              <ul class="option">
                <li>clone</li>
                <li>derived</li>
                <li>fork</li>
                <li>inherit</li>
              </ul>
            </dd>
          </dl>
          <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
          <p class="answer_check"><span>答えはこちら</span></p>
					<div class="answer">
						<dl>
							<dt>答えは<span> D</span>です。</dt>
							<dd>
CSS のプロパティには親要素から子要素に設定が継承されるものとされないものがありますが、inherit を指定することで強制的に継承することができます。<br>
例えば長子要素にのみ指定する場合は疑似セレクタを使用して下記のように行います。<br>
<pre>
<code>
div:first-child {
    border: inherit;
    float: inherit;
}
</code>
</pre>

逆に all, initial, unset で継承を回避することも可能です。allを使用するとすべてのプロパティ（例外を除く）を対象にでき、値に initial を指定すると初期値が適用できます。unset を指定すると上書きされた値がクリアされ、初期値または継承値を適用できます。<br>
継承はプログラミングの効率化のための技術ですのでマスターすることで効率的なコードを書くことができます。<br><br>
例題の選択肢には、他の分野での継承に似た効率化の手法です。<br>
Aのclone は生物学や仮想化技術で使用される複製に関する用語です。<br>
Bのderived は派生の意でC++, C#などの継承で使用されます。<br>
Cのfork はLinuxのプロセス遷移の最初の手続きです。			
							</dd>	
								</dl>
						<p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_122">出題範囲の詳細</a></p>
                        <div class="present">
    						<p>LPI-Japan<br>中谷　徹</p>
						</div>
					</div>
        </div>          
	<div class="question">
          <dl>
            <dt>例題2.21「1.2.2 CSSデザイン」</dt>
            <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_122">1.2.2 CSSデザイン</a>」からの出題です。<br>
            データベースに登録された英語住所が大文字小文字混在しているため、CSSを用い、すべて大文字で表示したい。text-transform プロパティで指定する値として適切なのは次のうちどれか。
            </dd>
            <dd>
              <ul class="option">
                <li>uppercase</li>
                <li>lowercase</li>
                <li>capitalize</li>
                <li>acronym</li>
                <li>abbreviation</li>
              </ul>
            </dd>
          </dl>
          <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
          <p class="answer_check"><span>答えはこちら</span></p>
					<div class="answer">
						<dl>
							<dt>答えは<span> A</span>です。</dt>
							<dd>
Aの uppercaseは文字をすべて大文字に変換します。これが正解になります。<br>
例: Home Page → HOME PAGE<br><br>
Bの lowercaseは文字をすべて小文字に変換します。<br>
	例: Home Page → home page<br><br>
Cの capitalizeは単語の先頭の文字を大文字に変換します。先頭以外の文字はそのままです。<br>
	例: home page → Home Page, HOME PAGE → HOME PAGE<br><br>
Dの acronymは単語の頭文字からなる略語を意味する英単語ですが、text-transformの値としては無効です。<br>
もし、機能するとしたら、Home Page → HP となるでしょう。<br><br>
Eの abbreviationは短縮/省略を意味する英単語ですが、text-transformの値としては無効です。<br>
もし、機能するとしたら、これも Home Page → HP となるのでしょうか。<br>
日本語の略語「パソコン」や「スマホ」などは、acronymではなくabbreviation方式ですね。<br><br>
なお、text-transform はオングストローム（ångström,Å）などのアクセント付き文字を含むアルファベットのみに有効で、日本語の漢字やひらがなには無効です。また、カタカナや英数字の全角半角の変換もできません。
なので、lowercaseを指定しても「つ」は「っ（小さいつ）」には変換できないので注意しましょう。<br><br>
text-transformとは関係ありませんが、ケースには他にも、camelCase、snake_case、PascalCase、kebab-caseといったケースがあるようです。								
							</dd>	
								</dl>
						<p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_122">出題範囲の詳細</a></p>
                        <div class="present">
    						<p>LPI-Japan<br>中谷　徹</p>
						</div>
					</div>
        </div> 
         <div class="question">
          <dl>
            <dt>例題2.20「1.2.2 CSSデザイン」</dt>
            <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_122">1.2.2 CSSデザイン</a>」からの出題です。<br>
            下記のHTML/CSSコードにおける transition についての説明として正しいのは次のうちどれか。３つ選びなさい。
            </dd>
            <dd>
<div class="box">
<pre>
<code>
【HTML】
&lt;!DOCTYPE html&gt;
&lt;html&gt;
&lt;head&gt;
&lt;meta charset="utf-8"&gt;
&lt;title&gt;transition&lt;/title&gt;
&lt;style type="text/css"&gt;
button {
    background-color: #00f;
    margin:  10px;
    width:  100px;
    height: 50px;
    transition: transform 1s ease 0.2s,
                color 1s cubic-bezier(0,0,1,1) 0s,
                background-color 1s linear;
}
button:hover {
    transform: translate(20px,20px) scale(1.5) rotate(360deg); /* 変形 */
    color: #ff0;               /* 文字色*/
}
button:active {
    color: #00f;               /* 文字色*/
    background-color: #f00;    /* 背景色 */
}
&lt;/style&gt;

&lt;/head&gt;
   &lt;body&gt;
       &lt;button&gt;ボタン&lt;/button&gt;
&lt;/body&gt;
&lt;/html&gt;
</code>
</pre>
</div>
            </dd>
            <dd>
              <ul class="option">
                <li>マウスポインタをボタン上に置いた時、ボタンの変形と文字色の変化は同時に開始する。</li>
                <li>マウスポインタをボタン上に置いた時、ボタンの変形は文字色の変化完了の0.2秒後に完了する。</li>
                <li>ボタンをクリックした時、文字色の変化と背景色の変化は同じ時間経過で遷移する。</li>
                <li>ボタンのクリックを解除した時、瞬時にボタンは初期状態になる。</li>
                <li>ボタンはクリックしたままマウスポインタを遠ざけた時、ボタン形状は元に戻るが色は変わらない。</li>
              </ul>
            </dd>
          </dl>
          <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
          <p class="answer_check"><span>答えはこちら</span></p>
					<div class="answer">
						<dl>
							<dt>答えは<span> B、C、E</span>です。</dt>
							<dd>
transition は状態遷移の詳細を指定するプロパティで下記の４つをこの順序で同時に指定できます。<br>
・transition-duration: 状態遷移にかける時間<br>
・transition-timing-function: ３次ベジェ(cubic-bezier)関数での経時変化<br>
・transition-delay: 状態遷移を開始するまでの時間<br>
transition-timing-functionの３次ベジェのcubic-bezier(P0, P1, P2, P3) は、P0(始点)からP3(終点)をP1,P2のハンドル指定でつなぐ曲線で、下記の既定値があります。<br><br>
ease : cubic-bezier(0.25,0.1,0.25,1)<br>
linear : cubic-bezier(0,0,1,1) (直線)<br>
ease-in : cubic-bezier(0.42,0,1,1)<br>
ease-out : cubic-bezier(0,0,0.58,1)<br>
ease-in-out: cubic-bezier(0.42,0,0.58,1)<br><br>

transition の省略時のデフォルト値はそれぞれ、all, 0s, ease,0sで、複数の対象がある場合は、例題のようにコンマ(,)で区切って指定します。<br><br>

例題では、ボタンの変形のdelayは0.2秒に対し、文字色変化のdelayは0秒なので同時に開始せず、Aは不正解です。<br>
ボタンの変形と文字色変化のdurationは共に1秒のため、ボタンの変形はdelayの分の0.2秒後に完了するので、Bは正解です。<br>
文字色も背景色も共に0秒のdelayで1秒かけて直線的(linear)に遷移し、Cは正解です。<br>
クリックを解除しても、マウスがボタン上にあれば button:hover が効いて初期状態には戻らず、Dは不正解です。<br>
クリックしたままマウスを遠ざけると button:hover は解除され、ボタンの変形のみ元に戻るので、Eは正解です。								</dd>	
								</dl>
						<p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_122">出題範囲の詳細</a></p>
                        <div class="present">
    						<p>LPI-Japan<br>中谷　徹</p>
						</div>
					</div>
        </div> 
         <div class="question">
          <dl>
            <dt>例題2.19「1.2.2 CSSデザイン」</dt>
            <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_122">1.2.2 CSSデザイン</a>」からの出題です。<br>
            長い間大きな変更をしてなかったホームページを急遽レスポンシブWEBデザインに対応するよう依頼され、下記のように最小限の変更で対応した。【１】〜【３】に入る文字列の組み合わせとして最適なのは次のうちどれか。            </dd>
            <dd>
<div class="box">
<pre>
<code>
【HTML】
&lt;!DOCTYPE html&gt;
&lt;html&gt;
&lt;head&gt;
&lt;meta http-equiv="Content-Type" content="text/html; charset=UTF-8" /&gt;
&lt;meta name="viewport" content="width=device-width,initial-scale=1" /&gt;
&lt;style type="text/css"&gt;
div { 
    text-align: center;
    }
.default {
    background-color: #ccc;
    }
@media screen and (max-width: 600px) {	/* for mobile - narrow */
.pc {
   【  １  】: 【  ２  】; 
    }	/* PC で非表示 *
.mobile {
   【  １  】: 【  ３  】; 
    }	/* スマホで表示 */
    }
@media screen and (min-width: 601px) {	/* for pc - wide */
.mobile {
   【  １  】: 【  ２  】; 
    }	/* スマホで非表示 */
.pc { 
   【  １  】: 【  ３  】; 
    }	/* PC で表示 */
    }
#footer {
     position: fixed;
     bottom: 0;
	 width: 100%;
    }
&lt;/style&gt;
&lt;/head&gt;
&lt;body&gt;
&lt;div class="default pc"&gt;
	&lt;p&gt;PC Menu&lt;/p&gt;
&lt;/div&gt;
&lt;div class="default mobile"&gt;
	&lt;p&gt;Mobile Menu(New)&lt;/p&gt;
&lt;/div&gt;
&lt;div class="default"&gt;
	&lt;p&gt;Main Contents&lt;/p&gt;
&lt;/div&gt;
&lt;div class="default pc"&gt;
	&lt;p&gt;Rich Contents&lt;/p&gt;
&lt;/div&gt;
&lt;div id="footer" class="default"&gt;
	&lt;p&gt;Footer&lt;/p&gt;
&lt;/div&gt;
&lt;/body&gt;
&lt;/html&gt;
</code>
</pre>
</div>
            </dd>
            <dd>
              <ul class="option">
                <li>hide, true, false</li>
                <li>visibility, hidden, visible</li>
                <li>display, invisible, visible</li>
                <li>display, none, block</li>
                <li>opacity, 0, 1</li>
              </ul>
            </dd>
          </dl>
          <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
          <p class="answer_check"><span>答えはこちら</span></p>
					<div class="answer">
						<dl>
							<dt>答えは<span> D</span>です。</dt>
							<dd>
ウェブサイトのスマートフォンによるアクセスシェアが急速に高まるに連れ、ウェブサイトのスマートフォン対応化の要求が急激に高まっています。<br><br>
手っ取り早くスマホに対応するには、従来のサイトをそのままに、スマホでの表示に耐えられる変更が必要になります。<br><br>
最初に行うのが viewport の指定です。meta要素のcontent 属性には例題で指定した値の他に、コンテンツの拡大縮小の可否を制御する user-scalable=yes/no がありますが、近くの文字が見えにくくなったおじさん達のためにもデフォルトのままで、no にしない配慮をしていただきたいものです。<br><br>
次に画面のサイズ等の条件に合わせて表示を制御する記述を行います。<br>
条件分岐は HTML内に記述して異なるCSSファイルを利用する方法と、同一のCSS内に記述する方法があり、例題ではCSS内に記述しています。<br>
要素の表示/非表示の制御は、display プロパティと visibility プロパティで指定できますが、visibilityでは表示領域を確保したまま要素を非表示にするため、今回の目的にあったレイアウトで表示できません。<br>
期待するレイアウトを実現するには display を使用するのが適していると言え、非表示には none を指定します。<br>
この例題では、opacity プロパティで透明度を指定しても表示/非表示を実現できますが、visibilyと同様の効果となり、レイアウトを満足できません。また、hide というプロパティは存在しません。<br><br>
従って、正解は D になります。
								</dd>	
								</dl>
						<p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_122">出題範囲の詳細</a></p>
                        <div class="present">
    						<p>LPI-Japan<br>中谷　徹</p>
						</div>
					</div>
        </div>                          
         <div class="question">
          <dl>
            <dt>例題2.18「1.2.2 CSSデザイン」</dt>
            <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_122">1.2.2 CSSデザイン</a>」からの出題です。<br>
            以下は、ボタンにアニメーションを設定した例である。説明として間違っているのは次のうちどれか。２つ選びなさい。 
            </dd>
            <dd>
<div class="box">
<pre>
<code>
【HTML】
&lt;!DOCTYPE html&gt;
&lt;html&gt;
&lt;head&gt;
&lt;meta charset="utf-8"&gt;
&lt;title&gt;jinni effect like&lt;/title&gt;
&lt;style type="text/css"&gt;
button {
        background-color: #00f;
        width: 100px;
        height: 100px;
        border-radius: 50px;
        transition: transform 0.8s;
}
button:hover {
        transform: translate(0,-10px) scale(1.3);
        color: #ff0;
        background-color: #00a;
}
button:active {
        background-color: #f00;
}
&lt;/style&gt;
&lt;/head&gt;
&lt;body&gt;
&lt;table&gt;
&lt;tr&gt;&lt;th colspan=3&gt;ジニーイフェクト風ボタン&lt;/th&gt;&lt;/tr&gt;
&lt;tr&gt;
&lt;td&gt;&lt;button&gt;ボタン1&lt;/button&gt;&lt;/td&gt;
&lt;td&gt;&lt;button&gt;ボタン2&lt;/button&gt;&lt;/td&gt;
&lt;td&gt;&lt;button&gt;ボタン3&lt;/button&gt;&lt;/td&gt;
&lt;/tr&gt;
&lt;/table&gt;    
&lt;/body&gt;
&lt;/html&gt;
</code>
</pre>
</div>
            </dd>
            <dd>
              <ul class="option">
                <li>ボタンの形状は、正方形である。</li>
                <li>マウスがボタン上に来ると、ボタンが大きくなる。</li>
                <li>マウスがボタン上に来ると、ボタンの色が薄い青になる。</li>
                <li>マウスがボタン上に来ると、0.8秒かけて変形する。</li>
                <li>ボタンを押すと、ボタンの背景色が赤に変わる。</li>
              </ul>
            </dd>
          </dl>
          <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
          <p class="answer_check"><span>答えはこちら</span></p>
					<div class="answer">
						<dl>
							<dt>答えは<span> A と C</span>です。</dt>
							<dd>
A. ボタンサイズは縦横(width,height)共に100pxで、角の丸み(border-radius)50pxの指定があるのでボタン形状は丸になり、説明としては間違いです。<br>
B. マウスがボタン上に来た時(hover)に、大きく(scale 1.3)変形(transform)する指定があるので、説明として正しいです。<br>
C. マウスがボタン上に来た時(hover)に、背景色(background-color)を濃いの青(#00a) にする指定があるので、説明としては間違いです。<br>
D. マウスがボタン上に来た時(hover)に、0.8秒かけて変形(transition: transform 0.8s)する指定があるので、説明として正しいです。<br>
E. ボタンを押す(activate)と、ボタンの背景色が赤(background-color: #f00)に変わる指定があるので、説明として正しいです。
						</dd>
						</dl>
						<p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_122">出題範囲の詳細</a></p>
                        <div class="present">
    						<p>LPI-Japan<br>中谷　徹</p>
						</div>
					</div>
        </div>         
         <div class="question">
          <dl>
            <dt>例題2.17「1.2.2 CSSデザイン」</dt>
            <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_122">1.2.2 CSSデザイン</a>」からの出題です。<br>
            HTMLファイルをブラウザで表示したところ、下記のように表示された。HTMLファイルの下線部に入るCSSのプロパティ名を2つ選びなさい。 
            </dd>
            <dd>
            <div class="box">
            【表示画面】<br>
            I Am A Cat.<br>
            As Yet I Have No Name.
			</div>
<div class="box">
<pre>
<code>
【HTML】
&lt;html&gt;
&lt;head&gt;
&lt;meta charset="utf-8"/&gt;
&lt;style type="text/css"&gt;
        p.test {
		_____________: capitalize;
		_____________: pre;
	}
&lt;/style&gt;
&lt;/head&gt;
    &lt;body&gt;
        &lt;p class="test"&gt;
        I am a cat.&lt;br /&gt;
        As yet I have no name.
	&lt;/p&gt;
    &lt;/body&gt;
&lt;/html&gt;
</code>
</pre>
</div>
            </dd>
            <dd>
              <ul class="option">
                <li>case-transform</li>
                <li>text-transform</li>
                <li>word-wrap</li>
                <li>word-break</li>
                <li>white-space</li>
              </ul>
            </dd>
          </dl>
          <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
          <p class="answer_check"><span>答えはこちら</span></p>
					<div class="answer">
						<dl>
							<dt>答えは<span> B と E</span>です。</dt>
							<dd>
選択肢Bのtext-transform プロパティは、テキストの大文字小文字を変換します。<br>
主な有効値は次のとおりです。<br>
・lowercase: テキストを全て小文字に変換します。<br>
・uppercase: テキストを全て大文字に変換します。<br>
・capitalize: 単語の1文字目を大文字にします。<br>
なお、日本語にはこれに該当する大文字小文字の区別はないので日本語は変換はされません。<br><br>
選択肢Eのwhite-space プロパティは、テキストのwhitespace（空白: タブ、スペース、改行）の表示方法を指定します。<br>
主な有効値は次のとおりです。<br>
・normal: スペース、タブ、改行を1つの空白に置換して表示します。<br>
・pre: スペース、タブ、改行をそのまま表示します。<br>
・nowrap:スペース、タブ、改行を1つの空白に置換して表示します。nowrapの、normalとの違いは、表示するボックス幅が小さくても改行されない点です。<br><br>
なお、スペースは、半角のスペースのみで、全角のスペースは漢字１文字として処理され、white-spaceの処理対象にはなりません。<br><br>
扱うテキストが英語の場合、単語と単語がスペースで区切られるため、何も指定しなければ、表示領域に到達する手前のスペースで自動的に改行され、単語の途中で改行されることはありません。<br>
しかし、日本語にはそのような都合の良いスペースがなく、逆にどこでも改行でき、幅が極端に狭い場合、縦一列で表示されることもあります。<br>句読点（。、）や、閉じ括弧（」）が行の先頭に来ないよう、ブラウザには禁則処理機能がありますが、ブラウザにより動作は異なるようです。<br><br>
選択肢Aのcase-transform は、存在しません。<br>
選択肢Cのword-wrap は、単語の途中の改行に関するプロパティです。<br>
選択肢Dのword-break は、改行位置を厳格に扱うプロパティで、CJK（Chinese, Japanese, Korean)に対応しています。<br><br>
								その他、英語には改行しないスペースとして「&amp;nbsp;（non-breaking space)」という特殊な文字もあります。							
						</dd>
						</dl>
						<p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_122">出題範囲の詳細</a></p>
                        <div class="present">
    						<p>LPI-Japan<br>中谷　徹</p>
						</div>
					</div>
        </div>         
        <div class="question">
          <dl>
            <dt>例題2.16「1.2.1 スタイルシートの基本」</dt>
            <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_121">1.2.1 スタイルシートの基本</a>」からの出題です。<br>
            下記のHTMLファイルについて、ブラウザに表示される6行のリストのうち橙色(Orange)で表示される行は何行あるか。行数を数字1文字で記述しなさい。 
 </dd>
            <dd>
<div class="box">
<pre>
<code>
&lt;html&gt;
&lt;head&gt;
&lt;meta charset="utf-8"/&gt;
&lt;style type="text/css"&gt;
ol       { color: brown; }
li#red   { color: red;   }
.red     { color: red;   }
li.blue  { color: blue;  }
#green   { color: green; }
.orange  { color: orange;}
li:nth-child(even)
         { color: orange;}
&lt;/style&gt;
&lt;/head&gt;
    &lt;body&gt;
    &lt;ol&gt;
        &lt;li id   ="red"   &gt;red    &lt;/li&gt;
        &lt;li id   ="green" &gt;green  &lt;/li&gt;
        &lt;li class="blue"  &gt;blue   &lt;/li&gt;
        &lt;li class="red"   &gt;red    &lt;/li&gt;
        &lt;li class="green" &gt;green  &lt;/li&gt;
        &lt;li id   ="orange"&gt;orange &lt;/li&gt;
    &lt;/ol&gt;
    &lt;/body&gt;
&lt;/html&gt;
</code>
</pre>
</div>
            </dd>
          </dl>
          <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
          <p class="answer_check"><span>答えはこちら</span></p>
					<div class="answer">
						<dl>
							<dt>答えは<span> 2</span>です。</dt>
							<dd>
								基本的なCSSの設定方法とHTMLでの指定方法、およびセレクタの優先順位に関する問題です。<br /> ブラウザでの表示は以下のようになり、4行目と6行目の2つが橙色で表示されるので、答えは「２」となります。<br />
1. red		.. 赤<br>
2. green	.. 緑<br>
3. blue		.. 青<br>
4. red		.. 橙<br>
5. green	.. 茶<br>
6. orange	.. 橙<br><br /> 
						まず、CSSパートの設定を確認します。<br />
(a) ol要素内の色を茶色<br />
(b) li要素のID名redを赤色<br />
(c) クラス名redを赤色<br />
(d) li要素のクラス名blueを青色<br />
(e) ID名greenを緑色<br />
(f) クラス名orangeを橙色<br />
(g) li要素の偶数番目を橙色<br /><br /> HTMLのol要素内での指定とCSSの対応を確認すると下記のようになります。<br>
1. id=redの(b)が、(a)より優先され、赤<br>
2. id=greenの(e)が、(a)(g)より優先され、緑<br>
3. class=blueの(d)が、(a)より優先され、青<br>
4. class=redの(c)より、(g)が優先されるため、橙<br>
5. class=greenの設定がCSSに無いので、(a)の茶<br>
6. id=orangeの設定がCSSに無いが、6行目で(g)により、橙<br><br /> 実際のファイルでは、このようなわかりにくいコーディングはないと思いますが、すごく複雑なものは存在します。思った通りの体裁にならないときに、基本的なセレクタとそれらの優先順位を計算して、原因を追求できるようにしておきましょう。

							</dd>
						</dl>
						<p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_121">出題範囲の詳細</a></p>
                        <div class="present">
    						<p>LPI-Japan<br>中谷　徹</p>
						</div>
					</div>
        </div>

              <div class="question">
          <dl>
            <dt>例題2.15「1.2.1 スタイルシートの基本」</dt>
            <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_121">1.2.1 スタイルシートの基本</a>」からの出題です。<br>
            HTML5のstyle要素にtype属性が指定されていない場合の、type属性のデフォルト値を記述しなさい。</dd>
            <dd>
            </dd>
          </dl>
          <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
          <p class="answer_check"><span>答えはこちら</span></p>
					<div class="answer">
						<dl>
							<dt>答えは<span> text/css  </span>です。</dt>
							<dd>
								HTML5よりも前のHTML/XHTMLでは、style要素のtype属性にはデフォルト値が設定されていなかったため、type属性は必ず指定する必要がありました。type属性にはスタイルシート言語の種類をMIMEタイプで指定することになっており、CSSであればその値は「text/css」となります。HTML5では、この「text/css」がデフォルト値として設定されたため、CSSを使用するのであればtype属性は省略可能となっています。
							</dd>
						</dl>
						<p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_121">出題範囲の詳細</a></p>
					<div class="present">
						<p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル１認定者　大藤 幹 氏</p>
					</div>
					</div>
        </div>
              <div class="question">
          <dl>
            <dt>例題2.14「1.2.1 スタイルシートの基本」</dt>
            <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_121">1.2.1 スタイルシートの基本</a>」からの出題です。<br>
            1つめのtr要素にのみスタイルを適用するセレクタをすべて選びなさい。 </dd>
            <dd>
            </dd>
            <dd>
              <ul class="option">
                <li>tr:first-child</li>
                <li>tr:nth-child(1) </li>
                <li>tr:nth-child(0n+1) </li>
                <li>tr:nth-child(1n)</li>
                <li>tr:nth-child(1n+0)</li>
              </ul>
            </dd>
          </dl>
          <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
          <p class="answer_check"><span>答えはこちら</span></p>
					<div class="answer">
						<dl>
							<dt>答えは<span> A,B,C </span>です。</dt>
							<dd>
								Aの「:first-child」は、要素内容の先頭にある要素を適用対象とするセレクタです。よって、まずはこれが答えの1つとなります。<br><br> 
残りのB〜Eのセレクタは、すべて (an+b) 形式の式を持っています。 (an+b) 形式の式において、aが0の場合はanは省略できます。上の選択肢Cの (0n+1) ではaが0なので、0nは省略できます。省略するとBの (1) と同じになります。つまり、BとCの式は同じもので、両方とも1番目の要素を適用対象としますので、これらも答えに含まれることになります。 
<br><br>
また、(an+b) 形式の式において、an+bのbが0の場合には+bが省略できます。上の選択肢Eの (1n+0) ではbが0なので、+bは省略でき、省略するとDの (1n) と同じになります。これらは1つめだけでなく、すべてのtr要素にスタイルを適用します。よって答えは A、B、C となります。 
							</dd>
						</dl>
						<p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_121">出題範囲の詳細</a></p>
					<div class="present">
						<p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル１認定者　大藤 幹 氏</p>
					</div>
					</div>
        </div>
              <div class="question">
          <dl>
            <dt>例題2.21「1.2.2 CSSデザイン」</dt>
            <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_122">1.2.2 CSSデザイン</a>」からの出題です。<br>
            transformプロパティで指定できない関数を1つ選びなさい。</dd>
            <dd>
              <ul class="option">
                <li>perspective</li>
                <li>rotate3d</li>
                <li>scale3d</li>
                <li>translate3d</li>
                <li>opacity</li>
              </ul>
            </dd>
          </dl>
          <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
          <p class="answer_check"><span>答えはこちら</span></p>
					<div class="answer">
						<dl>
							<dt>答えは<span> E </span>です。</dt>
							<dd>
A：3D変形の奥行感を指定することが出来る関数です。<br>
B：要素を回転表示することが出来る関数です。<br>
C：要素の3D縮尺比率を指定することが出来る関数です。<br>
D：要素を3D方向に移動させることが出来る関数です。<br>
E：透明度を指定するプロパティです。transformプロパティでは指定できません。
							</dd>
						</dl>
						<p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_122">出題範囲の詳細</a></p>
					<div class="present">
						<p>例題解説の提供：豊田 健次 氏</p>
					</div>
					</div>

        </div>
              <div class="question">
          <dl>
            <dt>例題2.20「1.2.2 CSSデザイン」</dt>
            <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_122">1.2.2 CSSデザイン</a>」からの出題です。<br>
            CSSを使って英単語の先頭だけを大文字表示する場合、text-transformプロパティに設定する値として正しいものを選びなさい。</dd>
            <dd>
            </dd>
            <dd>
              <ul class="option">
                <li>ucfirst</li>
                <li>capitalize</li>
                <li>uppercase</li>
                <li>camelcase</li>
                <li>proper</li>
              </ul>
            </dd>
          </dl>
          <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
          <p class="answer_check"><span>答えはこちら</span></p>
					<div class="answer">
						<dl>
							<dt>答えは<span> B </span>です。</dt>
							<dd>
A：PHPやPerlなどのプログラミング言語で用いられる、先頭を大文字に変換する関数の名前です。<br>
B：CSSにおいて、text-transformプロパティに設定することで、単語の先頭を大文字で表示することができますので、正解です。<br>
C：CSSにおいて、すべての文字を大文字で表示することができます。<br>
D：頭文字だけを大文字にして書く記法名称のひとつです。<br>
E：表計算アプリケーション等で用いられる、先頭を大文字に変換する関数の名前です。</dd>
						</dl>
						<p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_122">出題範囲の詳細</a></p>
					<div class="present">
						<p>例題解説の提供：豊田 健次 氏</p>
					</div>
					</div>
        </div>
              <div class="question">
          <dl>
            <dt>例題2.19「1.2.2 CSSデザイン」</dt>
            <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_122">1.2.2 CSSデザイン</a>」からの出題です。<br>
            CSSのアニメーションの@keyframesの書式内において、「100%」の代わりに使用できるキーワードを1つ選びなさい。</dd>
            <dd>
            </dd>
            <dd>
              <ul class="option">
                <li>to</li>
                <li>end</li>
                <li>over</li>
                <li>last</li>
                <li>finished</li>
              </ul>
            </dd>
          </dl>
          <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
          <p class="answer_check"><span>答えはこちら</span></p>
					<div class="answer">
						<dl>
							<dt>答えは<span>  A </span>です。</dt>
							<dd>
@keyframesの書式では、「0%」の代わりに「from」、「100%」の代わりに「to」が使用できます。よって、答えはAとなります。<br><br> キーワードではなくパーセント値を使用する場合には、必ず数値に「%」をつける必要があります。そのため、「0%」は正しい指定ですが、「0」は文法エラーとなります。<br>@keyframesの書式内においては、「%」は0でも省略できない点にも注意しましょう。</dd>
						</dl>
						<p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_122">出題範囲の詳細</a></p>
					<div class="present">
						<p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル１認定者　大藤 幹 氏</p>
					</div>
					</div>
        </div>
              <div class="question">
          <dl>
            <dt>例題2.18「1.2.2 CSSデザイン」</dt>
            <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_122">1.2.2 CSSデザイン</a>」からの出題です。<br>
            CSSの背景に関する記述のうち正しいものをすべて選びなさい。 </dd>
            <dd>
            </dd>
            <dd>
              <ul class="option">
                <li>すべての背景関連プロパティは、カンマ区切りで複数の値を指定できる。</li>
                <li>background-colorプロパティにはカンマ区切りの値を指定できない。</li>
                <li>カンマ区切りで先（左側）に指定した背景画像ほど上（画面上で手前）に表示される。</li>
                <li>カンマ区切りで後（右側）に指定した背景画像ほど上（画面上で手前）に表示される。 </li>
                <li>backgroundプロパティにカンマ区切りの値を指定する際、背景色は先頭（一番左）に指定する値の１つとして指定する。</li>
              </ul>
            </dd>
          </dl>
          <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
          <p class="answer_check"><span>答えはこちら</span></p>
					<div class="answer">
						<dl>
							<dt>答えは<span> B、C </span>です。</dt>
							<dd>
CSS3からは、1つのボックスに複数の背景画像を指定できるようになりました。背景画像をカンマ区切りで指定すると、先（左側）に指定した背景画像ほど上（画面上で手前）に重なって表示されます。よってCは正しく、Dは間違いとなります。<br><br> カンマ区切りで指定した背景画像は個別の背景レイヤーに表示されますが、背景色はそれらすべての背景レイヤーのうち、一番下のレイヤーにのみ表示されます。そのため、背景色は一番下の背景レイヤーとなる一番右側の値の１つとして指定することになっています。よってEは間違いです。また、結果として背景色は値を1つしか指定できないことになり、Aは間違いで、Bは正しいことになります。							</dd>
						</dl>
						<p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_122">出題範囲の詳細</a></p>
					<div class="present">
						<p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル１認定者　大藤 幹 氏</p>
					</div>
					</div>
        </div>

              <div class="question">
          <dl>
            <dt>例題2.17「1.2.2 CSSデザイン」</dt>
            <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_122">1.2.2 CSSデザイン</a>」からの出題です。<br>
            CSSのbox-shadowプロパティの値の指定方法として間違っているものをすべて選びなさい。 </dd>
            <dd>
            </dd>
            <dd>
              <ul class="option">
                <li>box-shadow: 1px;</li>
                <li>box-shadow: 1px 1px;</li>
                <li>box-shadow: 3px 3px 6px 2px;</li>
                <li>box-shadow: 3px 3px 6px 2px inset;</li>
                <li>box-shadow: rgba(0,0,0,0.5) 3px 3px 6px 2px inset;</li>
              </ul>
            </dd>
          </dl>
          <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
          <p class="answer_check"><span>答えはこちら</span></p>
					<div class="answer">
						<dl>
							<dt>答えは<span> A </span>です。</dt>
							<dd>
								box-shadowプロパティの値の数値は、2個・3個・4個のいずれかを連続して指定する必要があります。よって、数値が1つしか指定されていないAは間違いです。<br><br>
影の「色」とキーワードの「inset」は、どちらもオプションです。BやCのように省略指定しても問題ありません。影の色を省略した場合のデフォルトは、colorプロパティの値となります。<br><br>
数値は必ず連続して指定する必要がありますが、色とinsetはそれらの数値の前後いずれにでも指定可能です。よって、DとEも間違いではありません。
							</dd>
						</dl>
						<p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_122">出題範囲の詳細</a></p>
					<div class="present">
						<p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル１認定者　大藤 幹 氏</p>
					</div>
					</div>
        </div>

              <div class="question">
          <dl>
            <dt>例題2.16「1.2.1 スタイルシートの基本」</dt>
            <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_121">1.2.1 スタイルシートの基本</a>」からの出題です。<br>
            body要素の内容が次のようになっているとき、段落3と段落4にのみスタイルを適用するセレクタを1つ選びなさい。 
 </dd>
            <dd>
<div class="box">
<pre>
<code>
&lt;h1&gt;見出し&lt;/h1&gt; 

&lt;h2&gt;見出し&lt;/h2&gt; 

&lt;p&gt;段落1&lt;/p&gt;

&lt;p&gt;段落2&lt;/p&gt; 

&lt;h3&gt;見出し&lt;/h3&gt; 

&lt;p&gt;段落3&lt;/p&gt; 

&lt;p&gt;段落4&lt;/p&gt;
</code>
</pre>
</div>
            </dd>
            <dd>
              <ul class="option">
                <li>h3 p </li>
                <li>h3 ~ p</li>
                <li>h3 + p</li>
                <li>h3 &lt; p</li>
                <li>h3 &gt; p</li>
              </ul>
            </dd>
          </dl>
          <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
          <p class="answer_check"><span>答えはこちら</span></p>
					<div class="answer">
						<dl>
							<dt>答えは<span> B  </span>です。</dt>
							<dd>
								CSS3の結合子で使用される記号とそれがあらわす意味をしっかり覚えているかどうかを確認する問題です。<br /> Aはh3要素の中に含まれるp要素が適用対象となりますので、上のHTMLではどこに適用されません。<br /> Cはh3要素の直後にあるp要素が適用対象となりますので、スタイルは段落3にのみ適用されます。<br /> Dの結合子はCSS3では定義されていませんので、CSSの文法エラーとなります。<br /> Eはh3要素の直接の子要素が適用対象となりますので、上のHTMLではどこに適用されません。
							</dd>
						</dl>
						<p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_121">出題範囲の詳細</a></p>
					<div class="present">
						<p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル１認定者　大藤 幹 氏</p>
					</div>
					</div>
        </div>

              <div class="question">
          <dl>
            <dt>例題2.15「1.2.1 スタイルシートの基本」</dt>
            <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_121">1.2.1 スタイルシートの基本</a>」からの出題です。<br>
            HTML5のstyle要素にtype属性が指定されていない場合の、type属性のデフォルト値を記述しなさい。</dd>
            <dd>
            </dd>
          </dl>
          <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
          <p class="answer_check"><span>答えはこちら</span></p>
					<div class="answer">
						<dl>
							<dt>答えは<span> text/css  </span>です。</dt>
							<dd>
								HTML5よりも前のHTML/XHTMLでは、style要素のtype属性にはデフォルト値が設定されていなかったため、type属性は必ず指定する必要がありました。type属性にはスタイルシート言語の種類をMIMEタイプで指定することになっており、CSSであればその値は「text/css」となります。HTML5では、この「text/css」がデフォルト値として設定されたため、CSSを使用するのであればtype属性は省略可能となっています。
							</dd>
						</dl>
						<p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_121">出題範囲の詳細</a></p>
					<div class="present">
						<p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル１認定者　大藤 幹 氏</p>
					</div>
					</div>
        </div>
              <div class="question">
          <dl>
            <dt>例題2.14「1.2.1 スタイルシートの基本」</dt>
            <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_121">1.2.1 スタイルシートの基本</a>」からの出題です。<br>
            1つめのtr要素にのみスタイルを適用するセレクタをすべて選びなさい。 </dd>
            <dd>
            </dd>
            <dd>
              <ul class="option">
                <li>tr:first-child</li>
                <li>tr:nth-child(1) </li>
                <li>tr:nth-child(0n+1) </li>
                <li>tr:nth-child(1n)</li>
                <li>tr:nth-child(1n+0)</li>
              </ul>
            </dd>
          </dl>
          <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
          <p class="answer_check"><span>答えはこちら</span></p>
					<div class="answer">
						<dl>
							<dt>答えは<span> A,B,C </span>です。</dt>
							<dd>
								Aの「:first-child」は、要素内容の先頭にある要素を適用対象とするセレクタです。よって、まずはこれが答えの1つとなります。<br><br> 
残りのB〜Eのセレクタは、すべて (an+b) 形式の式を持っています。 (an+b) 形式の式において、aが0の場合はanは省略できます。上の選択肢Cの (0n+1) ではaが0なので、0nは省略できます。省略するとBの (1) と同じになります。つまり、BとCの式は同じもので、両方とも1番目の要素を適用対象としますので、これらも答えに含まれることになります。 
<br><br>
また、(an+b) 形式の式において、an+bのbが0の場合には+bが省略できます。上の選択肢Eの (1n+0) ではbが0なので、+bは省略でき、省略するとDの (1n) と同じになります。これらは1つめだけでなく、すべてのtr要素にスタイルを適用します。よって答えは A、B、C となります。 
							</dd>
						</dl>
						<p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_121">出題範囲の詳細</a></p>
					<div class="present">
						<p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル１認定者　大藤 幹 氏</p>
					</div>
					</div>
        </div>
        
  <div class="question">
          <dl>
            <dt>例題2.13「1.2.3 カスケード（優先順位）」</dt>
            <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_123">1.2.3 カスケード（優先順位）</a>」からの出題です。<br>
            tr要素を12個含むtable要素があり次のCSSが適用された場合に、後述する設問に解答しなさい。</dd>
            <dd>
              <div class="box">
                <pre>
                <code>【CSS】
tr:nth-child(3n){
background-color:‪#‎FFC‬;
}
tr:nth-child(3n+1){
background-color:‪#‎FDD‬;
}
tr:nth-child(3n+2){
background-color:‪#‎DFD‬;
}
tr{
background-color:‪#‎CCC‬;
}</code>
</pre>
              </div>
            </dd>
            <dd>10番目のtr要素の背景色は何色になるか、次の選択肢から1つ選びなさい。</dd>
            <dd>
              <ul class="option">
                <li>白</li>
                <li>グレー</li>
                <li>薄黄色</li>
                <li>薄ピンク</li>
                <li>薄緑</li>
              </ul>
            </dd>
          </dl>
          <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
          <p class="answer_check"><span>答えはこちら</span></p>
					<div class="answer">
						<dl>
							<dt>答えは<span> D </span>です。</dt>
							<dd>
								tr要素に対するセレクタで背景色に#CCC（グレー）が指定されていますが、他のnth-child擬似クラスで指定されているスタイルの方が優先されます。<br>
								10番目の要素は「3n+1」の条件に適合するので#FDD（薄ピンク）となります。
							</dd>
						</dl>
						<p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_123">出題範囲の詳細</a></p>
					<div class="present">
						<p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル１認定者　林 拓也 氏</p>
					</div>
					</div>
        </div>
        
        <div class="question">
          <dl>
            <dt>例題2.12「1.2.2 CSSデザイン」</dt>
            <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_122">1.2.2 CSSデザイン</a>」からの出題です。<br>
            Web制作においてCSSの設定が複雑化し、ともすれば破綻しかねないケースがある。近年、Web制作のシーンでCSSを効率的に運用するための、運用・管理・命名規則などのルールや指針がいくつも発表されている。次の中で、CSSの効率的な運用方法のルール・指針と最も関係が薄いものはどれか。1つ選びなさい。</dd>
            <dd>
              <ul class="option">
                <li>SMACSS</li>
                <li>DOM</li>
                <li>OOCSS</li>
                <li>BEM</li>
              </ul>
            </dd>
          </dl>
          <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
          <p class="answer_check"><span>答えはこちら</span></p>
					<div class="answer">
						<dl>
							<dt>答えは<span> B </span>です。</dt>
							<dd>
								SMACSSはスタイルをベース、レイアウト、モジュール、ステート、テーマに分類して管理・運用します。<br>
								OOCSはObject Oriented CSS（オブジェクト指向CSS）の略です。ある特定の要素専用のスタイルを定義するのではなく、小さいパーツの組み合わせで実現する手法です。Structure（構造）とSkin（見た目）を分離して管理します。<br>
								BEMはBlock、Element、Modifierの3つのレベルによる命名規則でクラス名を設定する手法です。<br>
								DOMはDocument Object Modelの略で、主にJavaScriptでHTMLの要素にアクセスするための仕組みのことです。
							</dd>
						</dl>
						<p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_122">出題範囲の詳細</a></p>
					<div class="present">
						<p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル１認定者　林 拓也 氏</p>
					</div>
					</div>
        </div>
				<div class="question">
				<dl>
	                <dt>例題2.11「1.2.3 カスケード（優先順位）」</dt>
	                <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_123">1.2.3 カスケード（優先順位）</a>」からの出題です。<br>
						1つのHTML文書に、次のような「ユーザーのスタイルシート」と「制作者のスタイルシート」が同時に指定されているとき、p要素のフォントサイズは何ポイントになるか。次の選択肢から選びなさい。 </dd>
						<dd>
							<div class="box">
<pre>
<code>
【ユーザーのスタイルシート】
p { font-style: italic !important }
p { font-size: 11pt }
p { font-size: 12pt }

【制作者のスタイルシート】
p { font: normal 13pt serif !important }
p { font-size: 14pt }
p { font-size: 15pt }

</code>
</pre>
							</div>
							<ul class="option">
								<li>11ポイント</li>
								<li>12ポイント</li>
								<li>13ポイント</li>
								<li>14ポイント</li>
								<li>15ポイント</li>
							</ul>
						</dd>
				</dl>
  <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span>答えはこちら</span></p>
					<div class="answer">
						<dl>
							<dt>答えは<span> C  </span>です。</dt>
							<dd>
								指定されているCSSが「ユーザーのスタイルシート」だけであった場合は、フォントサイズは最後の指定である12ポイントとなります。しかし、「制作者のスタイルシート」の1行目には !important が付けられているため、fontプロパティによる文字サイズの13ポイントが優先されて適用されます。「制作者のスタイルシート」の2行目と3行目の指定には !important が無いため無効となります。<br>
								!important が無い場合は「ユーザーエージェント（ブラウザ）のスタイルシート」「ユーザーのスタイルシート」「制作者のスタイルシート」の順に適用の優先度が高くなります。!important がある指定はそれらよりも優先度は高くなりますが、その場合の優先度は「ユーザーエージェント（ブラウザ）のスタイルシート」「制作者のスタイルシート」「ユーザーのスタイルシート」の順となります。つまり、!important を付けた場合はユーザーによる要求の優先度を最も高くすることで、アクセシビリティを向上させる仕組みとなっています。
							</dd>
						</dl>
						<p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_123">出題範囲の詳細</a></p>
					<div class="present">
						<p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル１認定者　大藤 幹 氏</p>
					</div>
					</div>
</div>
<div class="question">
				<dl>
	                <dt>例題2.10「1.2.1 スタイルシートの基本」</dt>
	                <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_121">1.2.1 スタイルシートの基本</a>」からの出題です。<br>
						CSSのセレクタのうち、書式が間違っているものをすべて選びなさい。</dd>
						<dd>
							<ul class="option">
								<li>::root</li>
								<li>::before</li>
								<li>::after</li>
								<li>::first-child</li>
								<li>::last-child</li>
							</ul>
						</dd>
				</dl>
  <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span>答えはこちら</span></p>
					<div class="answer">
						<dl>
							<dt>答えは<span> A、D、E </span>です。</dt>
							<dd>疑似クラスと疑似要素の違いを明確にするために、CSS3（Selectors Level 3）では疑似要素名の前にはコロンを2つ付けることになっています。疑似クラスについては、CSS2.1と同様にコロンは1つだけ付けます。<br>
							選択肢の中で、疑似要素はBとCだけで、それ以外は疑似クラスですので、書式として間違っているのは A、D、E となります。CSS3の仕様では、上の選択肢にある疑似要素以外では ::first-line と ::first-letter が定義されています。<br>
							なお、CSS1やCSS2.1との互換性を維持する目的で、ブラウザはコロンが1つだけの疑似要素を今後もサポートすることになっています。</dd>
						</dl>
						<p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_121">出題範囲の詳細</a></p>
					<div class="present">
						<p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル１認定者　大藤 幹 氏</p>
					</div>
					</div>
</div>
<div class="question">
<dl>
                <dt>例題2.9「1.2.3 カスケード（優先順位）」</dt>
                <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_123">1.2.3 カスケード（優先順位）</a>」からの出題です。<br>
次のようなHTMLとCSSの組み合わせがある場合に、後述する設問に解答しなさい。</dd>
<div class="box">
<pre>
<code>
【HTML】
&lt;body&gt;
&lt;div&gt;
　&lt;p class="lead"&gt;
	&lt;strong&gt;CSS&lt;/strong&gt;はHTMLと共にWeb制作の中心となる技術です。
  &lt;/p&gt;
&lt;/div&gt;
&lt;/body&gt;

【CSS】
.lead {
　font-size:18px;
}
div>p {
　font-size:14px;
}
strong {
　font-size: 24px;
}
</code>
</pre>
</div>
<dd>この場合のp要素（strong要素外）の文字サイズとstrong要素の文字サイズはそれぞれ何ピクセルか選びなさい。</dd>
<dd>
  <ul>
	<li style="list-style-type: decimal;">p要素：18ピクセル／strong要素：18ピクセル
	<li style="list-style-type: decimal;">p要素：14ピクセル／strong要素：18ピクセル
	<li style="list-style-type: decimal;">p要素：18ピクセル／strong要素：24ピクセル
	<li style="list-style-type: decimal;">p要素：14ピクセル／strong要素：24ピクセル
  </ul>
</dd>
</dl>
  <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span>答えはこちら</span></p>
<div class="answer">
              <dl>
                <dt>答えは<span> 3 </span>です。</dt>
                <dd>p要素に対してはleadクラスセレクタと、div>pの複合セレクタが競合することになります。<br>
				同一の要素に対する指定では、セレクタ内のIDが多いもの、クラスが多いもの、要素が多いものの順で優先度が決まります。<br>
				p要素に対してはleadクラスセレクタの優先度が高くなるので、文字サイズは18ピクセルとなります。<br>
				strong要素にはleadクラスセレクタの文字サイズ指定が継承されますが、直接strong要素セレクタで上書きしているので24ピクセルとなります。<br>
				継承や優先度はCSSの効率的な利用における重要なポイントとなります。</dd>
                </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_123">出題範囲の詳細</a></p>
  <div class="present">
						<p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル１認定者　林 拓也 氏</p>
  </div>
</div>
</div>
<div class="question">
<dl>
<dt>例題2.8「1.2.2 CSSデザイン」</dt>
<dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_122">1.2.2 CSSデザイン</a>」からの出題です。<br>
次のようなHTMLとCSSの組み合わせがある場合に、後述する設問に解答しなさい。<br>
<dd>
<div class="box">
<pre>
<code>【HTML】
&lt;body&gt;
　&lt;div&gt;
　　&lt;h1&gt;タイトル&lt;/h1&gt;
　　&lt;p&gt;本文…………………&lt;/p&gt;
　&lt;/div&gt;
&lt;/body&gt;

【CSS】
body {
　margin: 0;
　padding: 0;
}
div {
　columns: 150px 3;
　column-gap: 20px;
}
</code>
</pre>
</div>
<dd>全てのCSSプロパティが適切に動作する前提で、ブラウザのウィンドウ幅が450ピクセルの場合と、1200ピクセルの場合の段組数はそれぞれいくつになるか。<br>
なお「ブラウザのウィンドウ幅＝div要素の幅」と考えて構わないものとする。</dd>
<dd>
  <ul>
	<li style="list-style-type: decimal;">450ピクセル：3つ／1200ピクセル：3つ</li>
	<li style="list-style-type: decimal;">450ピクセル：3つ／1200ピクセル：7つ</li>
	<li style="list-style-type: decimal;">450ピクセル：2つ／1200ピクセル：3つ</li>
	<li style="list-style-type: decimal;">450ピクセル：2つ／1200ピクセル：7つ</li>
  </ul>
</dd>
</dl>
  <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span>答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>答えは<span> 3 </span>です。</dt>
    <dd>columnsプロパティは段組の幅と数を指定します。column-gapプロパティは段組間の余白を指定します。<br>
	2014年8月現在ベンダープレフィックスを用いた書式と併記するのが一般的です。<br>
	columnsプロパティで指定した段組幅は、段組幅の下限として扱われます。<br>
	ウィンドウ幅が450ピクセルの場合、段組を3つ構成するとcolumn-gapプロパティを指定している関係で段組1つあたりの幅がcolumnsプロパティで指定した150ピクセルを下まわることになります。この場合、段組数が減らされ2つになります。<br>
	columnsプロパティで指定した段組数は、段組数の上限として扱われます。<br>
	ウィンドウ幅が十分広い場合でも、指定した数の段組が構成されます。<br>
	段組関係のプロパティは、通常のWebページで使用するだけでなく、レスポンシブWebデザインと組み合わせたり、電子書籍で使用したりすることが考えられます。</dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_122">出題範囲の詳細</a></p>
  <div class="present">
						<p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル１認定者　林 拓也 氏</p>
  </div>
</div>
</div>
<div class="question">
<dl>
<dt>例題2.7「1.2.1 スタイルシートの基本」</dt>
<dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_121">1.2.1 スタイルシートの基本</a>」からの出題です。<br />
次のlink要素のうち、style.css を正しく読み込む書き方をしているものはどれか。2つ選びなさい。</dd>
<dd>
  <ul class="option">
    <li>&lt;link href=&quot;style.css&quot;&gt;</li>
    <li>&lt;link href=&quot;style.css&quot; type=&quot;text/css&quot;&gt;</li>
    <li>&lt;link rel=&quot;stylesheet&quot; href=&quot;style.css&quot;&gt;</li>
    <li>&lt;link rel=&quot;stylesheet&quot; href=&quot;style.css&quot; type=&quot;text/css&quot;&gt;</li>
    <li>&lt;link rel=&quot;stylesheet&quot; href=&quot;style.css&quot; type=&quot;text/plain&quot;&gt; </li>
  </ul>
</dd>
</dl>
  <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span>答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>答え<span> C、D</span></dt>
    <dd>link要素にはrel属性の指定が必須です。よって、AとBは style.css を読み込みません。Cはtype属性が省略されていますが、HTML5ではrel属性の値が「stylesheet」の場合は「text/css」がデフォルト値として設定されているため、Cは style.css を読み込みます。Dは必要な属性が正しく指定されていますので問題なく style.css を読み込みます。Eは、CSS向けのMIMEタイプではない「text/plain」がtype属性の値として指定されていますので、style.css は読み込みまれません。 </dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_121">出題範囲の詳細</a></p>
  <div class="present">
						<p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル１認定者　大藤 幹 氏</p>
  </div>
</div>
<div class="question">
<dl>
<dt>例題2.6「1.2.1 スタイルシートの基本」</dt>
<dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_121">1.2.1 スタイルシートの基本</a>」からの出題です。<br>
link要素で外部スタイルシートを読み込む際に、rel要素の値として指定する語を記述しなさい。</dd>
</dl>
  <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span>答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>答え<span> stylesheet</span></dt>
    <dd>link要素で外部スタイルシートを読み込む場合、rel属性には値として「stylesheet」を指定します（「rel=&quot;stylesheet&quot;」）。rel属性はリンクされている他のリソースファイルのタイプを指定します。<br />
	外部スタイルシートのリンク以外に使用する場合には異なる値を指定することになりますが、指定する値はいずれも大文字・小文字を区別しません。<br />
	つまり「STYLESHEET」や「StyleSheet」と記述しても正解です。</dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_121">出題範囲の詳細</a></p>
  <div class="present">
						<p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル１認定者　林 拓也 氏</p>
  </div>
</div>
</div>
</div>
<div class="question">
<dl>
<dt id="lv1_2_5">例題2.5「1.2.2 CSSデザイン」</dt>
<dd>
レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_122">1.2.2 CSSデザイン</a>」からの出題です。<br>
CSSのwhite-spaceプロパティにおいて、ブラウザで表示させる際にもソースコード上の改行位置で改行させ、連続する半角スペース・タブ・改行コードを1つの半角スペースにまとめず、テキストがウィンドウの右端まで来たときには自動的に行を折り返すようにしたい場合に指定する値はどれか。正しいものを1つ選びなさい。 
</dd>
<dd>
<ul class="option">
	<li>normal</li>
	<li>pre</li>
	<li>nowrap</li>
	<li>pre-wrap</li>
	<li>pre-line</li>
</ul>
</dd>
</dl>
  <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span>答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>答え<span>D</span></dt>
    <dd>white-spaceプロパティの値と表示との関係は次の表のようになっています。表の「改行」はソースコード上の改行位置で改行するかどうか、「まとめ」は連続する半角スペース・タブ・改行コードを1つの半角スペースにまとめるかどうか、「折り返し」はテキストがウィンドウの右端まで来たときに行を折り返すかどうかを示しています。正解は、表で「する」「まとめない」「折り返す」と書かれているpre-wrapとなります。</dd>
	<dd>
		<table style="margin-top: 1em;">
			<tr>
				<td colspan="2">&nbsp;</td>
				<td>改行</td>
				<td style="padding: 0 1em;">まとめ</td>
				<td>折り返し</td>
			</tr>
			<tr>
				<td colspan="5">--------------------------------------------------------------</td>
			</tr>
			<tr>
				<td>normal</td>
				<td>｜</td>
				<td>しない</td>
				<td style="padding: 0 1em;">まとめる</td>
				<td>折り返す</td>
			</tr>
			<tr>
				<td>pre</td>
				<td>｜</td>
				<td>する</td>
				<td style="padding: 0 1em;">まとめない</td>
				<td>折り返さない</td>
			</tr>
			<tr>
				<td>nowrap</td>
				<td>｜</td>
				<td>しない</td>
				<td style="padding: 0 1em;">まとめる</td>
				<td>折り返さない</td>
			</tr>
			<tr>
				<td>pre-wrap</td>
				<td>｜</td>
				<td>する</td>
				<td style="padding: 0 1em;">まとめない</td>
				<td>折り返す</td>
			</tr>
			<tr>
				<td>pre-line</td>
				<td>｜</td>
				<td>する</td>
				<td style="padding: 0 1em;">まとめる</td>
				<td>折り返す</td>
			</tr>
			<tr>
				<td colspan="5">--------------------------------------------------------------</td>
			</tr>
		</table>
	</dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_122">出題範囲の詳細</a></p>
  <div class="present">
						<p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル１認定者　大藤 幹 氏</p>
  </div>
</div>
</div>
<div class="question">
<dl>
<dt id="lv1_2_4">例題2.4「1.2.3 カスケード（優先順位）」</dt>
<dd>
レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_123">1.2.3 カスケード（優先順位）</a>」からの出題です。<br>
次に示すセレクタの中で、計算上もっとも優先順位が高くなる指定はどれか。１つ選びなさい。
</dd>
<dd>
<ul class="option">
	<li>*#abc ul</li>
	<li>#abc #def ul</li>
	<li>body#abc ul</li>
	<li>#ab.cd.ef.gi.hj.kl.mn.op.qr.st.uv.wx.yz ul</li>
	<li>*#ab.cd.ef.gi.hj.kl.mn.op.qr.st.uv.wx.yz ul</li>
</ul>
</dd>
</dl>
  <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span>答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>答え<span> B</span></dt>
    <dd>セレクタによる適用の優先順位は、セレクタに含まれる「idセレクタの数」「属性関連セレクタ（classセレクタ・属性セレクタ・疑似クラス）の数」「要素関連セレクタ（タイプセレクタ・疑似要素）の数」で3桁の数字を作り、その数字が大きいものほど高くなります。このとき、ユニバーサルセレクタ（*）は無視されます。</dd>
	<dd>しかしこの計算においては、いずれかの桁の数字が10以上になったとしても、決して繰り上がることはないルールになっている点に注意してください（つまり10進数ではなく、たとえば100進数の3桁のような数字として計算するということです）。</dd>
	<dd>ここで、便宜的に16進数でこれらの3桁をあらわしてみると、Aは101、Bは201、Cは102、Dは1C1、Eも1C1となり、Bが一番大きな数字となります（10進数の12は、16進数のCであるため）。よって正解はBです。</dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_123">出題範囲の詳細</a></p>
  <div class="present">
						<p>例題解説の提供：HTML5アカデミック認定校　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>
     HTML5レベル１認定者　大藤 幹 氏</p>
  </div>
</div>
</div>
<div class="question">
<dl>
<dt id="lv1_2_3">例題2.3「1.2.1 スタイルシートの基本」</dt>
<dd>
	レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_121">1.2.1 スタイルシートの基本</a>」からの例題を解説します。<br />
	CSSにおけるシンプルセレクタのうち、ユニバーサルセレクタ（Universal selector）に関する説明として正しいものを選びなさい。
</dd>
<dd>
<ul class="option">
	<li>ドット(.)を~=の代わりとして利用し、クラス属性における特定の属性値を持つ要素を示す。</li>
	<li>アスタリスク(*)を用いて表記され、全ての型の要素を示す。</li>
	<li>タッシュタグ(#)の後にID型属性の値を記述し、特定のID属性を持つ要素を示す。</li>
	<li>要素名を記述し特定の要素型の要素を示す。</li>
	<li>任意の属性名と属性値を指定することで、その属性を指定している要素およびその属性値を持つ要素を示す。</li>
</ul>
</dd>
</dl>
  <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span>答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>答え<span>B</span></dt>
    <dd>Aはクラスセレクタに関する説明なので間違いです。<br>
Bはユニバーサルセレクタに関する説明なので正解です。<br>
CはIDセレクタに関する説明なので間違いです。<br>
Dはタイプセレクタに関する説明なので間違いです。<br>
Eは属性セレクタに関する説明なので間違いです。</dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_121">出題範囲の詳細</a></p>
  <div class="present">
						<p>例題解説の提供：<a href="http://media-sketch.com/" target="_blank" >メディアスケッチ株式会社</a><br>
      代表取締役　兼　株式会社コーデセブン　取締役CTO　伊本 貴士 氏<br>
      ITコンサルタント業を中心に、Webサービスの開発や、オープンソースシステムの構築・保守なども行っている。</p>
  </div>
</div>
</div>
<div class="question">
<dl>
<dt id="lv1_2_2">例題2.2「1.2.2 CSSデザイン」</dt>
<dd>
	レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_122">1.2.2 CSSデザイン</a>」からの例題を解説します。<br />
	CSSにおいて、div要素の背景色が半透明になる記述として正しいものを１つ選びなさい。
</dd>
<dd>
<ul class="option">
	<li>div {background-color: rgba(255,0,0,128);}</li>
	<li>div {background-color: #FF000088;}</li>
	<li>div {background-color: rgba(255,0,0,0.5);}</li>
	<li>div {background-color: transparent;}</li>
	<li>div {background-color: rgba(100%,0%,0%,50%);}</li>
</ul>
</dd>
</dl>
  <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span>答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>答え<span>C</span></dt>
    <dd><p>background-colorプロパティにおいて、半透明の色を指定する場合は、rgba()またはhsla()で色を指定する必要があります。<br>
rgba()で色を指定する場合、r値・g値・b値の3つの値は0-255の値で指定し、4つめのアルファ値は0-1の範囲で指定します。<br>
アルファ値は色の透明度を指定する値で、この値が0の場合は透明度が100%（完全な透明色）になり、1の場合は透明度が0%となります。<br>
よって正解はCです。</p>
<p>Aはアルファ値を128と指定しており、最大値の1を超えているので不正解です。<br>
Bのように#で始まる書き方で半透明を指定する事はできません。<br>
Dのtransparentは、完全な透明色を指定する値で半透明にはなりません。<br>
Eは、アルファ値を%で指定しているので半透明にならず不正解です。rgbの各値は%指定可能なのでアルファ値が0.5とかであれば半透明になります。</p>
  </dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_122">出題範囲の詳細</a></p>
  <div class="present">
						<p>例題解説の提供：<a href="http://media-sketch.com/" target="_blank" >メディアスケッチ株式会社</a><br>
      代表取締役　兼　株式会社コーデセブン　取締役CTO　伊本 貴士 氏<br>
      ITコンサルタント業を中心に、Webサービスの開発や、オープンソースシステムの構築・保守なども行っている。</p>
  </div>
</div>
</div>
<div class="question">
<dl>
<dt id="lv1_2_1">例題2.1「1.2.1 スタイルシートの基本」</dt>
<dd>
	レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_121">1.2.1 スタイルシートの基本</a>」からの例題を解説します。<br />
	以下のHTMLにおけるテーブルについて、キャプションがテーブルの下の位置に配置されるように指定したい。この時、キャプションに対して指定するCSSの記述として正しいものを選択肢から選びなさい。 
</dd>
<dd>
  <div class="box">
  <pre>
  <code>
&lt;!DOCTYPE html&gt;
  &lt;html lang="ja"&gt;
  &lt;head&gt;
  &lt;link rel="stylesheet" href="test.css" type="text/css"&gt;
  &lt;/head&gt;
  &lt;body&gt;
  &lt;table border="1"&gt;
      &lt;caption&gt;
          果物の価格一覧
      &lt;/caption&gt;
    
    &lt;tr&gt;
      &lt;th&gt;りんご&lt;/th&gt;
      &lt;td&gt;100円&lt;/td&gt;
    &lt;/tr&gt;
    &lt;tr&gt;
      &lt;th&gt;もも&lt;/th&gt;
      &lt;td&gt;250円&lt;/td&gt;
    &lt;/tr&gt;
    &lt;tr&gt;
      &lt;th&gt;みかん&lt;/th&gt;
      &lt;td&gt;50円&lt;/td&gt;
    &lt;/tr&gt;
  &lt;/table&gt;
&lt;/body&gt;
&lt;/html&gt;
</code>
</pre>
</div>
</dd>
<dd>
  <ul class="option">
    <li>tr{caption-virtical: bottom;}</li>
    <li>caption{caption-virtical: bottom;}</li>
    <li>caption{caption-align: bottom;}</li>
    <li>caption{caption-side: bottom;}</li>
    <li>caption{caption-bottm: yes;}</li>
  </ul>
</dd>
</dl>
  <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span>答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>答え<span>D</span></dt>
    <dd>この場合、キャプションの文字はcaptionタグで指定しています。問題のコードにおけるtr要素はcaption要素を含んでいません。よって、Aはプロパティの名前に関係なく間違いです。
      テーブルにおけるキャプション位置は、caption-sideプロパティで行います。
      A,B,C,Eのプロパティは、CSSにおいては存在しません。
      よって、答えはDです。</dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_121">出題範囲の詳細</a></p>
 <div class="present">
						<p>例題解説の提供：<a href="http://media-sketch.com/" target="_blank" >メディアスケッチ株式会社</a><br>
      代表取締役　兼　株式会社コーデセブン　取締役CTO　伊本 貴士 氏<br>
      ITコンサルタント業を中心に、Webサービスの開発や、オープンソースシステムの構築・保守なども行っている。</p>
  </div></div>
</div>
</section>
<section>
  <div class="section-inner">
    <ul class="banner clearfix">
      <li class="index"> <a href="/measures/sample.html"> <img src="../images/common/arrow-right2.png" height="8" width="5" alt="" />HTML5プロフェッショナル認定試験レベル1 サンプル問題</a> </li>
    </ul>
  </div>
</section>
</div>
</article>
</div>
<!--
  <p id="pagetop-btn"> <a href="#top"> <img src="../images/common/arrow-top.gif" height="13" width="6">このページの先頭へ</a> </p>
-->
</div>