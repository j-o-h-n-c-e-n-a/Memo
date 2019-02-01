<h2>HTML5プロフェッショナル認定試験レベル1 サンプル問題</h2>
<section>
<div class="section-inner">
<div class="sample-box">
  <p class="lead">例題解説とその内容については、例題提供者の監修です。内容や試験問題に関わるお問い合わせにつきましては、LPI-Japan事務局ではお応えできませんのでご了承ください。<br>例題解説のご提供者さまを募集中です。<a href="mailto:&#109;&#97;&#105;&#108;&#64;&#108;&#112;&#105;&#46;&#111;&#114;&#46;&#106;&#112;">LPI-Japan事務局</a>までぜひご投稿ください。選ばれた方の例題解説は本サイトに掲載させていただきます。</p>
  <h3 id="lv1_3">1.3 要素</h3>
<!--
  <div class="question">
    <dl>
      <dt>例題3.★ ★</dt>
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
      <dt>例題3.20 「1.3.1 要素と属性の意味（セマンティクス）」</dt>
    <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_131">1.3.1 要素と属性の意味（セマンティクス）</a>」からの出題です。<br>
		ページのメイン・コンテンツを示すmain要素の説明として正しいのは次のうちどれか。</dd>
      <dd>
        <ul class="option">
          <li>main要素はアウトラインを構成する。</li>
          <li>main要素の子要素subはサブ・コンテンツを表す。</li>
          <li>main要素はrole属性を併用することが推奨されている。</li>
          <li>main要素はbody要素と同じ意味・役割である。</li>
          <li>main要素はWHATWGとW3Cで仕様に違いがある。</li>
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
		<div class="answer">
		  <dl>
			<dt>答えは<span> C、E </span>です。</dt>
			<dd>
ページは通常 header, footer, nav 等のページが遷移してもいつも表示され るアイテムとそのページでだけ表示されるメインのコンテンツで構成されますが、main要素はその領域を示すためにbody要素内で使用されます。<br>
また、main要素は WAI-ARIA (Web Accessibility Initiative - Accessible Rich Internet Applications)というアクセシビリティを目的とした仕様と関わりがあります。<br><br>
アクセシビリティは、バリアフリーに似た意味で、たとえばスクリーンリーダー（画面読み上げソフト）などの人ではなく機械が文章のrole(役割)を識別して視覚障害者にもその旨が伝わるように利用されます。<br><br>
さて、例題の選択肢ですが、main要素はh1要素などと違いアウトラインには寄与しないので、Aは不正解です。<br>
sub要素はH&lt;sub&gt;2&lt;/sub&gt;Oなど、下付きの文字を表示する要素なので、Bは不正解です。<br>
ARIA のrole "main" を併記することが推奨されており、Cは正解です。<br>
main要素はbody要素とは異なる意味があるので、Dは不正解です。<br>
WHATWGではmain要素はフロー・コンテンツが使用できる箇所ではどこでも使用できるとしていますが、W3Cでは article, asideなどの子孫要素にはなれないとあるので、Eは正解です。<br><br>
ARIAを取り入れ、バリアフリーなWebアプリケーションを制作しましょう。            
			</dd>
		  </dl>
			<p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_131">出題範囲の詳細</a></p> 
              <div class="present">
    			<p>LPI-Japan<br>中谷　徹</p>
			  </div>
		</div>            
	</div>    <div class="question">
    <dl>
      <dt>例題3.19 「1.3.1 要素と属性の意味（セマンティクス）」</dt>
    <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_131">1.3.1 要素と属性の意味（セマンティクス）</a>」からの出題です。<br>
		fieldset 要素に説明を付加する子要素は次のうちどれか。</dd>
      <dd>
        <ul class="option">
          <li>caption</li>
          <li>summary</li>
          <li>series</li>
          <li>legend</li>
          <li>folklore</li>
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
		<div class="answer">
		  <dl>
			<dt>答えは<span> D </span>です。</dt>
			<dd>
				<p>HTML5 には、対で使用してはじめて機能する要素があります。<br>
A. caption 要素は table 要素の子要素として機能します。<br>
B. summary 要素は details 要素の子要素として機能します。<br>
fieldset はフォームの入力項目をグループ化する際に使用し、項目を枠で囲みます。<br>
legend 要素を指定すると枠の一部が指定した文字列で表示されます。<br>
従って D が正解です。<br>
legend は辞書で調べると最初に「伝説」と出てきますが、ここでは「凡例」や「説明」
の意味となります。<br>
C. series は、legend と同様、グラフの凡例の意味で使用される英単語で不正解です。<br>
E. folklore は、伝説、民話といった意味の英単語で不正解です。</p> 
                <p>以下に table/caption, fieldset/legend, details/summary を使用した例を記載します。<br>
label要素はラベルをクリックすると対応する入力ボックスにフォーカスが当たります。
下記のラジオボタンでは、指先で押しやすいサイズにするメリットもあります。
label と inputの対応付けもマスターしましょう。</p>
				<p>
				<pre><code>
&lt;html&gt;
&lt;head&gt;
&lt;meta http-equiv="Content-Type" content="text/html; charset=UTF-8" /&gt;
&lt;/head&gt;
&lt;body&gt;
&lt;form action="a.cgi" method="post"&gt;
&lt;table width=300px&gt;
&lt;caption&gt;登録画面&lt;/caption&gt;
&lt;tr&gt;
&lt;td&gt;
&lt;fieldset&gt;
&lt;legend&gt;連絡先&lt;/legend&gt;
&lt;table width=100%&gt;
&lt;tr&gt;
&lt;td&gt;&lt;label for=name&gt;名前:&lt;/label&gt;&lt;/td&gt;
&lt;td&gt;&lt;input type=text id=name placeholder="例）資格月斗" required&gt;&lt;/td&gt;
&lt;/tr&gt;
&lt;tr&gt;
&lt;td&gt;&lt;label for=tel&gt;電話:&lt;/label&gt;&lt;/td&gt;
&lt;td&gt;&lt;input type=tel id=tel pattern="^[0-9]+$" placeholder="例）
08099999999" required&gt;&lt;/td&gt;
&lt;/tr&gt;
&lt;tr&gt;
&lt;td colspan=2&gt;
&lt;details&gt;&lt;summary>オプション&lt;/summary&gt;
&lt;table width=100%&gt;
&lt;tr&gt;
&lt;td&gt;性別:&lt;/td&gt;
&lt;td&gt;
&lt;input type=radio name=gender id=male  &gt;&lt;label for=male&gt;男&lt;/label&gt;
&lt;input type=radio name=gender id=female&gt;&lt;label for=female&gt;女&lt;/label&gt;
&lt;input type=radio name=gender id=custom&gt;&lt;label for=custom&gt;その他&lt;/label&gt;
&lt;/td&gt;
&lt;/tr&gt;
&lt;/table&gt;
&lt;/details&gt;
&lt;/td&gt;
&lt;/tr&gt;
&lt;/table&gt;
&lt;/fieldset&gt;
&lt;/td&gt;
&lt;/tr&gt;
&lt;tr&gt;
&lt;td colspan=2 align=right&gt;&lt;input type=submit value="登録"&gt;&lt;/td&gt;
&lt;/tr&gt;
&lt;/table&gt;
&lt;/body&gt;
&lt;/html&gt;
				</code></pre>
				</p>

            </dd>
		  </dl>
			<p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_131">出題範囲の詳細</a></p> 
              <div class="present">
    			<p>LPI-Japan<br>中谷　徹</p>
			  </div>
		</div>            
	</div>  
	
  <div class="question">
    <dl>
      <dt>例題3.18 「1.3.2 メディア要素」</dt>
    <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_132">1.3.2 メディア要素</a>」からの出題です。<br>
		下記の動画配信ページの説明として正しいのは次のうちどれか。</dd>
      <dd>
      <div class="box">
      <pre>
      <code>
　&lt;html&gt;
　&lt;head&gt;
　　&lt;meta charset="UTF-8"&gt;
　&lt;/head&gt;
&lt;body&gt;
&lt;video src=help.mov poster=help.png width=800 height=600 controls muted&gt;
       &lt;track kind="subtitles" src="ja.vtt" label="日本語"&gt;
       &lt;track kind="captions"  src="en.vtt" label="English"&gt;
&lt;/video&gt;
&lt;/body&gt;
&lt;/html&gt;
	 </code>
     </pre>
      </div>
        <ul class="option">
          <li>ページを開くと動画が自動的に再生される。</li>
          <li>動画再生時にデフォルトで日本語の字幕が表示される。</li>
          <li>動画再生時に日本語訳と英語での描写が同時に表示される。</li>
          <li>動画再生時に音声は再生できない。</li>
          <li>ページを開くと動画は自動的にロードされる。</li>
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
		<div class="answer">
		  <dl>
			<dt>答えは<span> E </span>です。</dt>
			<dd>
				<p>video要素に track要素を指定することで、動画に字幕を表示することができます。<br>
                video要素に controls属性を指定すると、再生、休止、ミュート、音量調節、シーク（進捗バーを掴んで移動）が可能な操作画面が利用できます。追加の属性指定により、自動再生(autoplay)、リピート(loop)、ポスター表示(poster)が可能です。<br>
			video要素の制御に対してJavaScriptが必要になるのは、スロー再生などの再生速度の変更ぐらいかもしれません。</p> 
                <p>video要素にtrack要素を追加することで字幕の利用が可能になります。<br>
                字幕の詳細は WebVTT(The Web Video Text Tracks Format)ファイルまたは TTML(Timed Text Markup Language) ファイルで
提供でき、表示の開始/終了時間は HH:MM:SS.mmm のミリ秒単位で指定し、オプションにより表示位置なども指定できます。</p>

<p>例題の選択肢の解釈は次のとおりです。</p>
<p>A: video 要素に autoplay属性の指定がないので再生は自動的に開始せず、poster属性で指定した画像が表示されるので、間違いです。</p>
<p>B: デフォルトでは字幕は「オフ」なので、間違いです。字幕を表示させるには操作画面でlabelで指定された字幕を選択します。また予め日本語を選択しておくには、下記のようにdefault を追加します。<br>
	&lt;track kind="captions"  src="ja.vtt" label="日本語" default&gt;</p>
<p>C: 字幕の表示は日本語か英語のどちらか一方になるので、間違いです。<br>
kind属性のsubtitlesは翻訳の字幕などに、captionsは状況説明などに使用します。デフォルトは subtitlesです。</p>
<p>D: video要素でmuted属性が指定されているのでミュート（消音）状態でページは開きますが、操作画面でミュート解除や音量制御もできるので、間違いです。</p>
<p>E: video要素に preload属性が指定可能です。大きな動画では負荷軽減のために none(preloadしない）を指定可能ですが、デフォルトはautoで自動的にロードを行うので、正解です。</p>


<p>下記に日本語と英語の字幕ファイルのサンプル(ja.vttとen.vtt)を紹介します。
動画もポスター画像もスマホで簡単に揃えられますので、ぜひ試してみましょう。<br>
なお、上記サンプルのHTMLファイルはローカルに置いて file:// で簡単に再生できますが、
Chrome で再生する場合 Webサーバー経由(http(s)://)でのみ字幕を表示することができます。</p>
<p>---- ja.vtt ----<br>
WEBVTT - 歌詞<br>
<br>
第1小節<br>
00:00:00.200 --> 00:00:01.000 line:90%<br>
ヘルプ! 誰か!<br>
<br>
第2小節<br>
00:00:01.000 --> 00:00:03.000 line:90%<br>
ヘルプ! 誰でもいいってわけじゃないけど...<br>
<br>
---- en.vtt ----<br>
WEBVTT - Lyrics<br>
<br>
1st bar<br>
00:00:00.200 --> 00:00:01.000 line:90%<br>
Help, I need somebody,<br>
<br>
2nd bar<br>
00:00:01.000 --> 00:00:03.000 line:90%<br>
Help, Not just anybody,
			
				</p> 
            </dd>
		  </dl>
			<p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_132">出題範囲の詳細</a></p> 
              <div class="present">
    			<p>LPI-Japan<br>中谷　徹</p>
			  </div>
		</div>            
	</div>  
 
  <div class="question">
    <dl>
      <dt>例題3.17 「1.3.3 インタラクティブ要素」</dt>
    <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_133">1.3.3 インタラクティブ要素</a>」からの出題です。<br>
		HTML5アプリを納品したが、スマホユーザーから「登録画面が使いにくい。」との苦情が多かったらしく、改善を要求された。<br>
以下はそのコードの抜粋であるが、スマホへの改善策として最も適しているのは次のうちどれか。</dd>
      <dd>
      <div class="box">
      <pre>
      <code>
　&lt;html&gt;
　&lt;head&gt;
　　&lt;meta charset="UTF-8"&gt;
　&lt;/head&gt;
&lt;body&gt;
　&lt;h1>登録&lt;/h1&gt;
&lt;form action="reg.pl" method="post"&gt;
　&lt;table&gt;
　　&lt;tr&gt;
　　　&lt;td&gt; 氏名:
　　　&lt;td&gt;&lt;input name="name" placeholder="資格月斗"&gt;
　　&lt;tr&gt;
　　　&lt;td&gt; メール:
　　　&lt;td&gt;&lt;input name="email" placeholder="shikaku@example.org"&gt;
　　&lt;tr&gt;
　　　&lt;td&gt; 電話番号:
　　　&lt;td&gt;&lt;input name="tel" placeholder="09012345678"&gt;
　　&lt;tr&gt;
　　　&lt;td&gt; 生年月日:
　　  &lt;td&gt;&lt;input name="birth" placeholder="1999/12/31"&gt;
　　&lt;tr&gt;
　　　&lt;td&gt; URL:
　　　&lt;td&gt;&lt;input name="url" placeholder="http://example.org/"&gt;
　&lt;/table&gt;
&lt;input type="submit" name="register"&gt;
&lt;/form&gt;
&lt;/body&gt;
&lt;/html&gt;
	 </code>
     </pre>
      </div>
        <ul class="option">
          <li>autocomplete=“on”で入力を簡素化する。</li>
          <li>kbd属性でキーボード配列(QWERTYまたは10キーなど)を指定する。</li>
          <li>picker属性でカレンダーピッカーやスライダーを指定する。</li>
          <li>pattern属性で受け付けない文字を入力できないよう指定する。</li>
          <li>type属性で入力値の分類を指定する。</li>
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
		<div class="answer">
		  <dl>
			<dt>答えは<span> E </span>です。</dt>
			<dd>
				<p>スマホの文字入力は、画面の一部に表示されるソフトウェアキーボードを使用します。小さな画面スペースに指で押せるサイズを確保するため、キーの数が制限されます。そのため入力する文字列によってはキーボードの切り替えが頻発する場合があります。<br>
                HTML5 の input 要素には多くのtype 属性が追加され、適切な値を指定することで適したキーボードを表示する事ができ、キーボード切り替えの負担を軽減できます。</p> 
				<p>以下は主な type 属性の値と説明です。<br>
text: デフォルト値です。アルファベット主体のキー配列が表示されます。<br>
email: アルファベットの他に @ と . キーが表示されます。<br>
url: アルファベットの他に / と . のキーが表示されます。iOSでは、さらに、.jp のキーが表示されます。<br>
date: 年、月、日のドラムロールが表示されます。PCでは、カレンダーも利用できます。日付の入力は、予約など今日の前後数ヶ月を入力する場合と、生年月日のような何十年も前(^^;)の日付を入力する場合があるので、使い分ける検討も必要です。<br>
time: 時、分のドラムロールが表示されます。<br>
tel: 数字といくつかの記号のみのキーが表示されます。<br>
number: 数字を主体とするキー配列が表示されます。</p>
				<p>その他の選択肢については以下のとおりです。<br>
A.のautocomplete属性は、入力を自動化する機能です。スマホ以外にも有効です。<br>
B.のkbd属性はありませんが、kbd要素は存在し、キーボードで入力するテキストを指す場合に使用します。QWERTYは通常のキーボード配列で、最上段の左から6文字の並びから命名されています。10キーは0~9の10個の数字キーでしたが、文字入力も可能になり日本語テンキーとも呼ばれます。<br>
C.のpicker属性はありません。<br>
D.のpattern属性は入力制限を正規表現で指定する機能です。<br><br>
type属性はブラウザにより実装やバリデーションが異なります。pattern属性を併用したり、動作の確認をしてから使用することをお勧めします。</p>
				<p>参考コード：type属性を指定した例
			    <pre><code>
　&lt;html&gt;
　&lt;head&gt;
　　&lt;meta charset="UTF-8"&gt;
　&lt;/head&gt;
&lt;title>登録&lt;/title&gt;
&lt;body>
　&lt;h1>登録&lt;/h1&gt;
&lt;form action=reg.pl method=post&gt;
　&lt;table>
　　&lt;tr&gt;
　　　&lt;td&gt; 氏名: 
　　　&lt;td&gt;&lt;input type="text" name="name" placeholder="資格月斗"&gt;
　　&lt;tr&gt;
　　　&lt;td&gt; メール: 
　　　&lt;td&gt;&lt;input type="email" name="email" placeholder="shikaku@example.org"&gt;
　　&lt;tr&gt;
　　　&lt;td&gt; 電話番号: 
　　　&lt;td&gt;&lt;input type="tel" name="tel"   placeholder="09012345678"&gt;
　　&lt;tr&gt;
　　　&lt;td&gt; 生年月日: 
　　　&lt;td&gt;&lt;input type="date" name="birth" placeholder="1999/12/31"&gt;
　　&lt;tr&gt;
　　　&lt;td&gt; URL: 
　　　&lt;td&gt;&lt;input type="url" name="url"   placeholder="http://example.org"&gt;
　　&lt;tr&gt;
　　　&lt;td&gt; 時刻: 
　　　&lt;td&gt;&lt;input type="time" name="time" placeholder="09:00"&gt;
　　&lt;tr&gt;
　　　&lt;td&gt; 検索: 
　　　&lt;td&gt;&lt;input type="search" name="search" placeholder="HTML5 認定"&gt;
　　&lt;tr&gt;
　　　&lt;td&gt; 数字: 
　　　&lt;td&gt;&lt;input type="number" name="number"   placeholder="123456789"&gt;
　&lt;/table&gt;
&lt;input type="submit" name="register"&gt;
&lt;/form&gt;
&lt;/body&gt;
&lt;/html&gt;			    
			    </code></pre>
				</p> 
            </dd>
		  </dl>
			<p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_133">出題範囲の詳細</a></p> 
              <div class="present">
    			<p>LPI-Japan<br>中谷　徹</p>
			  </div>
		</div>            
	</div>  
	
	<div class="question">
    <dl>
      <dt>例題3.16 「1.3.1 要素と属性の意味（セマンティクス）」</dt>
    <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_131">1.3.1 要素と属性の意味（セマンティクス）</a>」からの出題です。<br>
		HTML5で、誤植を修正する際の記述として適切なのは次のうちどれか。</dd>
      <dd>
        <ul class="option">
          <li>アーカイブを&lt;ng&gt;回答&lt;/ng&gt;&lt;ok&gt;解凍&lt;/ok&gt;できない。</li>
          <li>私は&lt;err&gt;隠し事&lt;/err&gt;&lt;corr&gt;書く仕事&lt;/corr&gt;が得意です。</li>
          <li>漢字の&lt;del&gt;返還&lt;/del&gt;&lt;ins&gt;変換&lt;/ins&gt;ミスに気をつけよう。</li>
          <li>田舎町に有名歌手が&lt;typo&gt;音ずれ&lt;/typo&gt;&lt;fix&gt;訪れ&lt;/fix&gt;た。</li>
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
					<div class="answer">
						<dl>
							<dt>答えは<span> C</span>です。</dt>
							<dd>HTML5では、del要素で削除箇所をins要素で追記箇所がわかるように記述することができます。<br>
多くのブラウザでは、削除箇所は取り消し線付きで表示し、追記箇所は下線付きで表示されます。<br>
したがって、正解はCです。<br><br>
del要素、ins要素ともにdatetime属性で修正日時を、cite属性で引用元のURLを記述することができます。<br><br>
なお、A、B、Cの要素はありません。					
					    </dd>
						</dl>
						<p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_131">出題範囲の詳細</a></p> 
                        <div class="present">
    						<p>LPI-Japan<br>中谷　徹</p>
						</div>
					</div>            
			  </div>
  <div class="question">
    <dl>
      <dt>例題3.15 「1.3.1 要素と属性の意味（セマンティクス）」</dt>
    <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_131">1.3.1 要素と属性の意味（セマンティクス）</a>」からの出題です。<br>
		object要素は、画像、音声、HTML文書など様々な外部リソースを文書内に取り込む際に使用しますが、次のうち指定方法として適切なものを1つ選べ。</dd>
      <dd>
        <ul class="option">
          <li>&lt;object href="sample.svg" …&gt;</li>
          <li>&lt;object data="sample.mpg" …&gt;</li>
          <li>&lt;object embed="sample.swf"  …&gt;</li>
          <li>&lt;object src="sample.gif" …&gt;</li>
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
					<div class="answer">
						<dl>
							<dt>答えは<span> B</span>です。</dt>
							<dd>object要素は、data属性でファイルを指定し、type属性でMIMEタイプを指定することで文書内に外部リソースを埋め込んで表示することができます。したがって正解は B です。<br><br>
A.のhref属性は、a要素、area要素、link要素でのリンク先の指定や、base要素での基準となるURLを指定することに使用します。<br>
C.のembedは要素で、src属性を指定して画像などの埋め込みに使用しますが、object要素の属性ではありません。<br>
D.のsrc属性は、embed要素やimg要素で参照先を指定するときなどに使用しますが、object要素の属性としては使用できません。</dd>
						</dl>
						<p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_131">出題範囲の詳細</a></p> 
                        <div class="present">
    						<p>LPI-Japan<br>中谷　徹</p>
						</div>
					</div>            
			  </div>
  <div class="question">
    <dl>
      <dt>例題3.14 「1.3.3 インタラクティブ要素」</dt>
    <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_133">1.3.3 インタラクティブ要素</a>」からの出題です。<br>
		下記のように、画面に「▶︎詳細」と表示し、「詳細」をクリックすると「詳細な説明」を表示したり、非表示にしたりするHTML5の記述は次のうちどれか。余分な文字を表示せず、正しく動作するものをすべて選びなさい。</dd>
      <dd>
      <div class="box">
      <pre>
      ▶︎詳細
	　⇅　
	  ▼詳細
	  詳細な説明
     </pre>
      </div>
        <ul class="option">
          <li> 
          &lt;summary&gt;詳細<br> 
          &lt;details&gt;詳細な説明&lt;/details&gt;<br>
          &lt;/summary&gt;
         </li>
          <li> 
          &lt;details&gt;<br>
          詳細な説明<br>
          &lt;/details&gt;
          </li>
          <li>
          &lt;details&gt;詳細<br>
          &lt;summary&gt;概要&lt;/summary&gt;<br>
          詳細な説明<br>
          &lt;/details&gt;
        </li>
          <li>
          &lt;details&gt;<br>
         詳細な説明<br>
         &lt;summary&gt;詳細&lt;/summary&gt;<br>
        &lt;/details&gt;
        </li>
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
					<div class="answer">
						<dl>
							<dt>答えは<span> B、D </span>です。</dt>
							<dd>details要素は、&lt;details&gt;タグで囲われた部分を非表示にし、必要に応じて利用者がクリックすることで参照できるようにできます。summary要素は、details要素の子要素で、省略時に表示される「詳細」（ブラウザにより異なる）を別の文字列に置き換える。
                        </dd>
						</dl>
						<p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_133">出題範囲の詳細</a></p> 
                        <div class="present">
    						<p>LPI-Japan<br>中谷　徹</p>
						</div>
					</div>            
			  </div>
  <div class="question">
    <dl>
      <dt>例題3.13 「1.3.1 要素と属性の意味（セマンティクス）」</dt>
    <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_131">1.3.1 要素と属性の意味（セマンティクス）</a>」からの出題です。<br>
		次の要素のうち、セクションに分類される要素をすべて選びなさい。</dd>
      <dd>
        <ul class="option">
          <li>header</li>
          <li>nav</li>
          <li>main</li>
          <li>aside</li>
          <li>footer</li>
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
					<div class="answer">
						<dl>
							<dt>答えは<span> B、D </span>です。</dt>
							<dd>HTML5の要素のうち、セクションに分類される要素（Sectioning content）は、「section」「article」「aside」「nav」の4種類のみです。<br>HTML5プロフェッショナル認定試験を受験するのであれば、この4種類の要素については、しっかりと確実に覚えておく必要があります。headerとfooterは、それらを含むもっとも近いセクション（またはセクショニング・ルート）のヘッダーとフッターとなります。<br>mainは（セクションではなく）文書全体におけるメインコンテンツの範囲を示す要素です。header・footer・mainは、要素のカテゴリーとしては Flow content に含まれます。
                        </dd>
						</dl>
						<p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_131">出題範囲の詳細</a></p> 
                        <div class="present">
    <p>例題解説の提供：<a href="http://html5exam.jp/measures/learning.html">HTML5アカデミック認定校</a>
                        <a href="http://html5exam.jp/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>
					    　HTML5レベル１認定者　大藤 幹 氏</p>
					</div>
					</div>
  </div>
  <div class="question">
    <dl>
      <dt>例題3.12 「1.3.2 メディア要素」</dt>
    <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_132">1.3.2 メディア要素</a>」からの出題です。<br>
		videoタグを使って動画圧縮規格がh.264の映像を表示する場合、sourceタグに設定する適切なtype属性を選びなさい。</dd>
      <dd>
        <ul class="option">
          <li>video/mp4</li>
          <li>video/ogg</li>
          <li>video/h264</li>
          <li>video/webm</li>
          <li>video/264</li>
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
					<div class="answer">
						<dl>
							<dt>答えは<span> A </span>です。</dt>
							<dd>A：コンテナフォーマットがmp4の場合に設定します。mp4コンテナフォーマットには動画圧縮規格h.264が使われていますので、Aが正解です。<br><br>
B：コンテナフォーマットがogg/ogvの場合に設定します。ogg/ogvコンテナフォーマットにはTheoraという動画圧縮規格が使われています。<br>
C：sourceタグのtype属性に設定できるものに、「video/h264」は存在しません。<br>
D：コンテナフォーマットがwebmの場合に設定します。webmはVP8という動画圧縮規格が使われています。<br>
E：sourceタグのtype属性に設定できるものに、「video/264」は存在しません。
                        </dd>
						</dl>
						<p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_132">出題範囲の詳細</a></p> 
                        <div class="present">
    <p>例題解説の提供：<a href="http://www.dht-jpn.co.jp/" target="_blank" class="linkwin">株式会社 デジタル・ヒュージ・テクノロジー</a><br>
					    　豊田 健次 氏</p>
					</div>
					</div>
  </div>
  <div class="question">
    <dl>
      <dt>例題3.11 「1.3.1 要素と属性の意味（セマンティクス）」</dt>
    <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_131">1.3.1 要素と属性の意味（セマンティクス）</a>」からの出題です。<br>
		role属性の機能として正しいものを1つ選びなさい。</dd>
      <dd>
        <ul class="option">
          <li>ユーザーが独自の属性を追加する。</li>
          <li>要素を回転させる角度を指定する。</li>
          <li>既存の要素の役割・意味を上書きして変更する。</li>
          <li>ゲームキャラクターの特性を示す。</li>
          <li>ユーザーインターフェイスの状態や特性を示す。</li>
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
					<div class="answer">
						<dl>
							<dt>答えは<span> C </span>です。</dt>
							<dd>role属性のroleは「役割」という意味で、既存の要素が持っている「役割・意味」とは異なる「役割・意味」を上書きして与えることのできる属性です。たとえば、既存のHTMLの要素にはユーザーインターフェイスとしての「タブ」や「ツリーウィジェット」をあらわす要素はありませんが、role属性を使用することでli要素やdiv要素などをタブ要素やツリーウィジェット要素に変更することができます（それによってスクリーンリーダーなどの支援技術がタブやツリーウィジェットを正しく認識できるようになります）。role属性の詳細な仕様は、HTML5とは別のWAI-ARIA 1.0という仕様書で定義されています。<br><br>
Aはカスタムデータ（data-*属性）属性の説明です。BとDのような属性はHTML5にはありません。Eは、role属性と同じくWAI-ARIA 1.0の仕様書で定義されているaria-*属性の説明です。
                            </dd>
						</dl>
						<p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_131">出題範囲の詳細</a></p> 
                        <div class="present">
    <p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル１認定者　大藤 幹 氏</p>
					</div>
					</div>
  </div>
  <div class="question">
    <dl>
      <dt>例題3.10 「1.3.1 要素と属性の意味（セマンティクス）」</dt>
    <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_131">1.3.1 要素と属性の意味（セマンティクス）</a>」からの出題です。<br>
		次のうち、mark要素としてマークアップするのにふさわしいものをすべて選びなさい。</dd>
      <dd>
        <ul class="option">
          <li>製品名やキーワード </li>
          <li>中国語の固有名詞</li>
          <li>検索結果の表示における検索語</li>
          <li>スペルが間違っている単語</li>
          <li>引用文の中で読者に注目してもらいたい部分</li>
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
					<div class="answer">
						<dl>
							<dt>答えは<span> C、 E </span>です。</dt>
							<dd>mark要素は、一般的なブラウザでは蛍光ペンでマークしたような表示となります。このことからもわかるように、オリジナルでは通常のテキストである部分を、そのWebページの読者に注目してもらうためにハイライト表示させるのがmark要素の役割です。<br><br> 
Aの製品名やキーワードについては、HTML5ではb要素を使用します。Bの「中国語の固有名詞」とDの「スペルが間違っている単語」については、HTML5ではu要素を使用することになっています。<br><br> 
テキスト関連の要素とその代表的な用途はしっかりと覚えておきましょう。</dd>
						</dl>
						<p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_131">出題範囲の詳細</a></p> 
                        <div class="present">
    <p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル１認定者　大藤 幹 氏</p>
					</div>
					</div>
  </div>
  <div class="question">
    <dl>
      <dt>例題3.9 「1.3.1 要素と属性の意味（セマンティクス）」</dt>
    <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_131">1.3.1 要素と属性の意味（セマンティクス）</a>」からの出題です。<br>
		time要素で指定する日時の書式として間違っているものを1つ選びなさい。</dd>
      <dd>
        <ul class="option">
          <li>&lt;time&gt;02:50&lt;/time&gt;</li>
          <li>&lt;time&gt;2時50分&lt;/time&gt;</li>
          <li>&lt;time datetime="02:50"&gt;真夜中&lt;/time&gt;</li>
          <li>&lt;time datetime="2015-12-24T02:50"&gt;2時50分&lt;/time&gt;</li>
          <li>&lt;time datetime="2015-12-24 02:50:00"&gt;ニ時五十分&lt;/time&gt;</li>
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
					<div class="answer">
						<dl>
							<dt>答えは<span> B </span>です。</dt>
							<dd>time要素は、datetime属性が指定されている場合は、その値を仕様書で定められている機械読み取り可能な書式にする必要があります。datetime属性が指定されていない場合は、time要素の要素内容のテキストを機械読み取り可能な書式にする必要があります。<br><br> 
Bにはdatetime属性が指定されていないため、要素内容を機械読み取り可能な書式にする必要があります。しかし、「2時50分」というテキストは仕様書で定義されている機械読み取り可能な書式には含まれていません。よって、答えはBです。<br><br> 
C、D、Eについては、要素内容は機械読み取り可能な書式ではありませんが、datetime属性の値が正しい書式で書かれているため問題ありません。</dd>
						</dl>
						<p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_131">出題範囲の詳細</a></p> 
                        <div class="present">
    <p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル１認定者　大藤 幹 氏</p>
					</div>
					</div>
  </div>
  <div class="question">
    <dl>
        <dt>例題3.8「1.3.1 要素と属性の意味（セマンティクス）」</dt>
        <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_131">1.3.1 要素と属性の意味（セマンティクス）</a>」からの出題です。<br>
			HTML5において、form要素の外部にあるフォーム関連要素をform要素と関連づける際に使用する属性はどれか。次の選択肢から1つ選びなさい。</dd>
			<dd>
				<ul class="option">
					<li>for属性</li>
					<li>form属性</li>
					<li>rel属性</li>
					<li>formlink属性</li>
					<li>formassociate属性</li>
				</ul>
			</dd>
	</dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
					<div class="answer">
						<dl>
							<dt>答えは<span> B </span>です。</dt>
							<dd>
								フォーム関連要素にform属性を指定し、その値にform要素のid属性の値を指定することで、フォーム関連要素の配置場所にかかわらず特定のform要素と関連づけることができます。form属性が指定できるのは、input要素、textarea要素、select要素、button要素、output要素、keygen要素、label要素、fieldset要素、object要素です。<br>
								ただし、form属性を実際に使用する際は、ブラウザの対応状況に注意する必要があります。
							</dd>
						</dl>
						<p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_131">出題範囲の詳細</a></p> 
                        <div class="present">
    <p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル１認定者　大藤 幹 氏</p>
					</div>
					</div>
  </div>

	<div class="question">
	<dl>
        <dt>例題3.7「1.3.1 要素と属性の意味（セマンティクス）」</dt>
        <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_131">1.3.1 要素と属性の意味（セマンティクス）</a>」からの出題です。<br>
			HTML5で「長万部」という漢字にルビをふる際のマークアップとして文法的に正しくないものをすべて選びなさい。</dd>
			<dd>
				<ul class="option">
					<li>&lt;ruby&gt;長万部&lt;rt&gt;おしゃまんべ&lt;/ruby&gt;</li>
					<li>&lt;ruby&gt;長万部&lt;rt&gt;おしゃまんべ&lt;/rt&gt;&lt;/ruby&gt;</li>
					<li>&lt;ruby&gt;長万部&lt;rp&gt;（&lt;/rp&gt;&lt;rt&gt;おしゃまんべ&lt;/rt&gt;&lt;rp&gt;）&lt;/rp&gt;&lt;/ruby&gt;</li>
					<li>&lt;ruby&gt;&lt;rb&gt;長万部&lt;rp&gt;（&lt;rt&gt;おしゃまんべ&lt;rp&gt;）&lt;/ruby&gt;</li>
					<li>&lt;ruby&gt;&lt;rtc&gt;&lt;rb&gt;長万部&lt;/rb&gt;&lt;rt&gt;おしゃまんべ&lt;/rt&gt;&lt;/rtc&gt;&lt;/ruby&gt;</li>
				</ul>
			</dd>
	</dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
					<div class="answer">
						<dl>
							<dt>答えは<span> E </span>です。</dt>
							<dd>
								ruby要素の最初の子要素には、ルビを振る対象となるテキスト（phrasing content）またはrb要素を配置する必要があります。したがって、最初の子要素としてrtc要素を配置しているEは文法的に正しくありません。ルビを振る対象となるテキストは、rb要素のタグを付けても付けなくても問題はありませんが、rb要素のタグを付けることでそこにCSSが指定しやすくなるなどの利点もあります。<br>
								ruby要素自体はタグを省略することはできませんが、その内容となるruby関連の各要素は終了タグを省略することが可能です。<br>
								ルビ関連の要素は、要素名が何の略なのかをおぼえておくと記憶しやすくなります。たとえばrtは「ruby text」の略で、それがルビのテキスト（振仮名となるテキスト）であることを示しています。rtcは「ruby text container」の略なので、そこにrt要素を入れるということがわかります。rb要素のbは「base text」を意味し、rp要素のpは「parentheses（パーレン=丸括弧）」を意味しています。<br>
								なお、XHTML1.1ではrbc要素が定義されていましたが、HTML5ではrbc要素は定義されていません。
							</dd>
						</dl>
						<p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_131">出題範囲の詳細</a></p> 
                        <div class="present">
    <p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a><a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル１認定者　大藤 幹 氏</p>
					</div>
					</div>

  </div>
<div class="question">
<dl>
      <dt>例題3.6「1.3.1 要素と属性の意味（セマンティクス）」</dt>
      <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_131">1.3.1 要素と属性の意味（セマンティクス）</a>」からの出題です。<br>
      次の要素のうち、セクションを示す要素ではないものはどれか。1つ選びなさい。</dd>
      <dd>
        <ul class="option">
          <li>nav</li>
          <li>main</li>
          <li>aside</li>
          <li>article</li>
          <li>section</li>
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>答え<span> B</span></dt>
    <dd>HTML5の要素のうち、セクションを示す要素（カテゴリーが「Sectioning content」に該当する要素）は、nav・aside・article・sectionの4種類のみです。main はセクションとはならず、文書のアウトラインにも影響を与えない要素です。</dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_131">出題範囲の詳細</a></p> 
  <div class="present">
    <p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル１認定者　大藤 幹 氏</p>
  </div>
</div>
  </div>
  <div class="question">
    <dl>
      <dt>例題3.5「1.3.2 メディア要素」</dt>
      <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_132">1.3.2 メディア要素</a>」からの出題です。<br>
      動画ファイルの埋め込みに関係するHTML要素を次の選択肢から全て選びなさい。
      </dd>
      <dd>
        <ul class="option">
          <li>source要素</li>
          <li>video要素</li>
          <li>movie要素</li>
          <li>control要素</li>
          <li>volume要素</li>
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>答え<span> A、B</span></dt>
    <dd>動画ファイルの埋め込みは、video要素単独で記述する書式と、video要素とsource要素を組み合わせて記述する書式があります。<br>
    source要素を使う場合には、video要素の子として複数の動画ファイルを再生候補として指定できます。その場合、Webブラウザは上から順に利用可能なファイルをチェックします。<br>
    なお、他の選択肢は存在しない架空のものです。
    </dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_132">出題範囲の詳細</a></p> 
  <div class="present">
    <p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル１認定者　林 拓也 氏</p>
  </div>
</div>
  </div>
  <div class="question">
    <dl>
      <dt>例題3.4「1.3.1 要素と属性の意味（セマンティクス）」</dt>
      <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_131">1.3.1 要素と属性の意味（セマンティクス）</a>」からの出題です。<br />
      ページのタイトルおよび本文に対してエンコードの種類を指定するcharset属性の記述位置として最も適切なものを選びなさい。</dd>
      <dd>
		<div class="box">
<pre>
<code>
エンコード指定の記述：
&lt;meta charset="UTF-8">

記述先のコード：
&lt;!DOCTYPE html&gt;
&lt;html lang="ja"&gt;
（Ａ）
&lt;head&gt;
	（Ｂ）
	&lt;title&gt;...&lt;/title&gt;
	（Ｃ）
&lt;/head&gt;
（Ｄ）
&lt;body&gt;
	（Ｅ）
 ...
&lt;/body&gt;
&lt;/html&gt;
</code>
</pre>
</div>
        <ul class="option">
          <li>(A)の位置に記述する</li>
          <li>(B)の位置に記述する</li>
          <li>(C)の位置に記述する</li>
          <li>(D)の位置に記述する</li>
          <li>(E)の位置に記述する</li>
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>答え<span>B</span></dt>
    <dd>meta要素のcharset属性は、本文だけではなくタイトルのエンコードに関する種類を指定できます。<br>
この記述はコードの&lt;head&gt;内に記述する必要があります。<br>
またタイトルに対しても指定する場合は、&lt;title&gt;より前に指定しなければなりません。</dd>
<dd>問題の選択肢では、&lt;head&gt;内にあり&lt;title&gt;より前に位置しているのは（B）のみです。<br>
よって正解はBとなります。</dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_131">出題範囲の詳細</a></p> 
  <div class="present">
    <p>例題解説の提供：<a href="http://media-sketch.com/" target="_blank" >メディアスケッチ株式会社</a><br>
      代表取締役　兼　株式会社コーデセブン　取締役CTO　伊本 貴士 氏<br>
      ITコンサルタント業を中心に、Webサービスの開発や、オープンソースシステムの構築・保守なども行っている。</p>
  </div>
</div>
  </div>
  <div class="question">
    <dl>
      <dt id="lv1_3_3">例題3.3「1.3.1 要素と属性の意味（セマンティクス）」</dt>
      <dd>
      		レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_131">1.3.1 要素と属性の意味（セマンティクス）</a>」からの例題を解説します。<br />
      		以下の説明に関する要素名の組み合わせで正しいものを選びなさい。
      </dd>
      <dd>
			<p style="margin-bottom:1em;">(1) コンピュータコードを表すために利用される要素である。<br>
			(2) コンピュータコードや数学における変数を示す場合に利用される要素である。<br>
			(3) コンピュータからの出力内容を示す場合に利用される要素である。<br>
			(4) コンピュータからの入力内容を示す場合に利用される要素である。</p>
        <ul class="option">
			<li>(1) pre (2) samp (3) var (4) kbd</li>
			<li>(1) pre (2) var (3) samp (4) kbd</li>
			<li>(1) pre (2) var (3) kbd (4) samp</li>
			<li>(1) code (2) var (3) samp (4) kbd</li>
			<li>(1) code (2) var (3) kbd (4) samp</li>
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
  <p class="answer_check"><span> 答えはこちら</span></p>
  <div class="answer">
    <dl>
      <dt> 答え <span>D</span> </dt>
		<dd>
		<p>HTMLには、コンピュータコードを表示するための要素があります。<br>
		コンピュータコードとは、XML要素名・ファイル名・プログラムのソースコードなどが含まれます。</p>
		<p>プログラムのコードなどを表示する場合はcode要素を使って記述するのが適切です。<br>
		多くの主要なブラウザの場合、code要素を使って表示すると等幅フォントで表示されます。</p>
		<p>ソースコードを表示する時にcode要素と合わせてpre要素がよく利用されますが、pre要素はフォーマット済みのテキストブロックを示すもの、つまり字下げや改行コードをそのまま表示するための要素であり、コンピュータコードを表すためのものではありません。<br>
		よって、A,B,Cは間違いです。</p>
		<p>コンピュータコードの変数を示す要素はvar要素、コンピュータからの出力を示す要素はsamp要素、コンピュータからの入力を示す要素はkbd要素なので正解はDです。</p></dd>
    </dl>
    <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_131">出題範囲の詳細</a></p> <div class="present">
    <p>例題解説の提供：<a href="http://media-sketch.com/" target="_blank" >メディアスケッチ株式会社</a><br>
      代表取締役　兼　株式会社コーデセブン　取締役CTO　伊本 貴士 氏<br>
      ITコンサルタント業を中心に、Webサービスの開発や、オープンソースシステムの構築・保守なども行っている。</p>
  </div>
  </div>
  </div>
  <div class="question">
    <dl>
      <dt id="lv1_3_2">例題3.2「1.3.2 メディア要素」</dt>
      <dd>
			レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_132">1.3.2 メディア要素</a>」からの例題を解説します。<br />
			HTML5におけるsource要素に関する説明として、正しいものを1つ選びなさい。
      </dd>
      <dd>
        <ul class="option">
		<li>コンピュータのコードを表示するための要素である。</li>
		<li>文書内のコンテンツが他の情報源からの引用である事を示す要素である。</li>
		<li>文書内に、Javascriptやデータブロックを組み込むための要素である。</li>
		<li>サイトの外部にある画像のURLを指定するための要素である。</li>
		<li>動画や音声に関するメディアファイルの種類やURLを指定するための要素である。</li>
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
  <p class="answer_check"><span> 答えはこちら</span></p>
  <div class="answer">
    <dl>
      <dt> 答え <span>E</span> </dt>
		<dd>source要素は、video要素やaudio要素の子要素として、メディアファイルの種類やURLを指定するために使われます。よって正解はEです。<br>
		Dにある画像のURLに関してですが、ファイルがどこに存在するかに関わらずimg要素のsrc属性で指定します。<br>
		Aはcode要素、Bはq要素およびblockquote要素、Cはscript要素に関する説明です。</dd>
    </dl>
    <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_132">出題範囲の詳細</a></p> <div class="present">
    <p>例題解説の提供：<a href="http://media-sketch.com/" target="_blank" >メディアスケッチ株式会社</a><br>
      代表取締役　兼　株式会社コーデセブン　取締役CTO　伊本 貴士 氏<br>
      ITコンサルタント業を中心に、Webサービスの開発や、オープンソースシステムの構築・保守なども行っている。</p>
  </div>
  </div>

  </div>
  <div class="question">
    <dl>
      <dt id="lv1_3_1">例題3.1「1.3.1 要素と属性の意味（セマンティクス）」</dt>
      <dd>
			レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_131">要素と属性の意味（セマンティクス）</a>」からの例題を解説します。<br />
			以下のようにHTML5の仕様でマークアップを行い、テキストの一部を“重要なテキスト範囲”として指定し、音声出力における強い表現などを期待したい。コード内の①に入る、最も適切な要素名を選択肢から一つ選びなさい。 
      </dd>
      <dd>
        <div class="box"> &lt;p&gt; &lt;①&gt;重要なお知らせ！&lt;/①&gt; 明日の集合時間は７時に変更となりました。&lt;/p&gt; </div>
      </dd>
      <dd>
        <ul class="option">
          <li>mark</li>
          <li>s</li>
          <li>strong</li>
          <li>b</li>
          <li>i</li>
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
  <p class="answer_check"><span> 答えはこちら</span></p>
  <div class="answer">
    <dl>
      <dt> 答え <span>C</span> </dt>
      <dd> Aのmark要素は、ハイライト表示を行うために使う要素でテキストの重要性を指定するものではありません。Bのs要素は、正確でなくなった情報について指定し、一般的なブラウザでは打ち消し線が引かれますので不正解です。Cのstrong要素は、重要な部分を指定するために定義されているものなので正解です。Dのb要素で囲まれたテキストは、一般的なブラウザでは太字表示されます。しかし、これはHTML5においては文体を変えるために使うものであって、重要性を指定するためのものではないと明示されています。よって不正解です。Eのi要素は、一般的なブラウザでは斜体表示されるものですが、重要性を指定するためものではありません。HTML5でマークアップする際は、似たような表示を行う要素でも、それぞれ使用する場面の想定が違う場合があるので気をつけましょう。 </dd>
    </dl>
    <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_131">出題範囲の詳細</a></p> 
    <div class="present">
    <p>例題解説の提供：<a href="http://media-sketch.com/" target="_blank" >メディアスケッチ株式会社</a><br>
      代表取締役　兼　株式会社コーデセブン　取締役CTO　伊本 貴士 氏<br>
      ITコンサルタント業を中心に、Webサービスの開発や、オープンソースシステムの構築・保守なども行っている。</p>
  </div>
  </div>
  </div>
</div>