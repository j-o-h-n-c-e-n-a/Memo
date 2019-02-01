$CATEGORY: 1.2.1 スタイルシートの基本

::問題１．１::HTTP/1.1に関する記述のうち、間違っているものを選びなさい。{
  
}

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
                ~h3 p 
                ~h3 ~ p
                ~h3 + p
                ~h3 &lt; p
                ~h3 &gt; p
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
                ~tr:first-child
                ~tr:nth-child(1) 
                ~tr:nth-child(0n+1) 
                ~tr:nth-child(1n)
                ~tr:nth-child(1n+0)
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
	                <dt>例題2.10「1.2.1 スタイルシートの基本」</dt>
	                <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_121">1.2.1 スタイルシートの基本</a>」からの出題です。<br>
						CSSのセレクタのうち、書式が間違っているものをすべて選びなさい。</dd>
						<dd>
							<ul class="option">
								~::root
								~::before
								~::after
								~::first-child
								~::last-child
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
    ~tr{caption-virtical: bottom;}
    ~caption{caption-virtical: bottom;}
    ~caption{caption-align: bottom;}
    ~caption{caption-side: bottom;}
    ~caption{caption-bottm: yes;}
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
      <li class="index"> <a href="/measures/sample.html"> <img src="../images/common/arrow-right2.png" height="8" width="5" alt="" />HTML5プロフェッショナル認定試験レベル1 サンプル問題</a> 
    </ul>
  </div>
</section>
</div>
</article>
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
	~ドット(.)を~=の代わりとして利用し、クラス属性における特定の属性値を持つ要素を示す。
	~アスタリスク(*)を用いて表記され、全ての型の要素を示す。
	~タッシュタグ(#)の後にID型属性の値を記述し、特定のID属性を持つ要素を示す。
	~要素名を記述し特定の要素型の要素を示す。
	~任意の属性名と属性値を指定することで、その属性を指定している要素およびその属性値を持つ要素を示す。
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
<dt>例題2.7「1.2.1 スタイルシートの基本」</dt>
<dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_121">1.2.1 スタイルシートの基本</a>」からの出題です。<br />
次のlink要素のうち、style.css を正しく読み込む書き方をしているものはどれか。2つ選びなさい。</dd>
<dd>
  <ul class="option">
    ~&lt;link href=&quot;style.css&quot;&gt;
    ~&lt;link href=&quot;style.css&quot; type=&quot;text/css&quot;&gt;
    ~&lt;link rel=&quot;stylesheet&quot; href=&quot;style.css&quot;&gt;
    ~&lt;link rel=&quot;stylesheet&quot; href=&quot;style.css&quot; type=&quot;text/css&quot;&gt;
    ~&lt;link rel=&quot;stylesheet&quot; href=&quot;style.css&quot; type=&quot;text/plain&quot;&gt; 
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
