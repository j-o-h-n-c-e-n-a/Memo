## スタイルシートの基本
	大規模なサイトやコンテンツにおいても、見やすく効率的なコードを記述し、複数のページで共有させるために必要な記述を適切に行うことができる。
### 主要な知識範囲
#### 要件やデザイン仕様に合わせて、HTMLから利用したいスタイルシートを指定する際の記述方法
#### 要件やデザイン仕様に合わせて、スタイルシートに正しいセレクタを指定しプロパティ値を指定する際の記述方法
### 重要な技術要素
#### <link>, @import, <style>, style属性
#### セレクタ, タイプセレクタ, クラスセレクタ, IDセレクタ, ユニバーサルセレクタ, 属性セレクタ
#### シンプルセレクタ（疑似クラス）, 疑似要素, 結合子, グループ化

## CSSデザイン
	要件に沿ったデザインをCSSを利用して実現する際に、どのような実現方法が適切か判断でき、仕様に沿った正しいコードを記述する事ができる。
### 主要な知識範囲
#### コンテンツのレイアウトに関する記述方法
#### 色、背景、罫線に関する記述方法
#### テキスト、リスト、テーブルに関する記述方法
#### コンテンツの変形、アニメーションに関する記述方法
### 重要な技術要素
#### ボックス(display, margin, padding, width, height, max-width, min-width, max-height, min-height, float, clear, overflow, visibility) 
#### マルチカラムレイアウト(column-count, column-width, columns, column-gap, column-rule, column-rule-style, column-rule-width, column-rule-color, column-span) 
#### flex, z-index,clip
#### 色指定（color, opacity）
#### 背景指定（background, background-color, background-image, background-repeat, background-position, background-attachment, background-clip, background-origin, background-size） 
#### 罫線（border, border-style, border-width, border-color, border-radius, box-shadow, liner-gradient, radial-gradient） 
#### フォント（font, font-size, font-weight, font-style, font-variant, font-family, Webフォント(@font-face)） 
#### テキスト（text-transform, white-space, word-break, hyphens, text-align, word-spacing, letter-spacing, text-indent） 
#### テキスト装飾（text-decoration, text-decoration-line, text-decoration-style, text-decoration-color, text-shadow, line-height, vertical-align, direction, unicode-bidi, quotes） 
#### リスト（list-style, list-style-type, list-style-image, list-style-position, content:counter, counter-increment, counter-reset） 
#### テーブル（caption-side, table-layout, border-collapse, border-spacing, empty-cells） 
#### 変形（transform, transform-origin）, 移動, 拡大, 縮小, 回転
#### トランジション（transition, transition-duration, transition-property, transition-timing-function, transition-delay）
* transition の時間指定は、変化にかける時間を表しており、遅延時間ではない。
* ease-inは、ゆっくり開始を表しており、等速ではない。

#### アニメーション（@keyframes, animation, animation-name, animation-delay, animation-duration, animation-iteration-count, animation-timing-function, animation-direction, animation-play-state, animation-fill-mode） 
* @keyframes規則での100%は、開始から3秒後を表す。

## カスケード（優先順位）
	大規模なサイトを作成する場合や、外部から提供されたスタイルシートを利用する場合に起こりやすい、HTMLの一つの要素に対して複数の記述が対象となる事象（プロパティの衝突）が発生した場合における適用の優先順位を理解している。
### 主要な知識範囲
#### 外部・内部スタイルシート、インラインスタイルシートの指定に関して記述場所による優先順位
#### セレクタの優先順位に関する計算方法
### 重要な技術要素
#### カスケード
#### 外部スタイルシート, 内部スタイルシート, インラインスタイルシート
#### !important


$CATEGORY: 1.2 CSSに関して

::例題2.26::次のようなHTML文書と3つの外部スタイルシート（s1〜s3.css）があったとき、h1要素のテキストは何色で表示されるか。以下の選択肢から1つ選びなさい。 {
	=red
	~green
	~blue
	~yellow
	~ブラウザで設定されている文字色
}

::例題2.25::ある要素にCSSで「display: flex;」と指定したところ、その中に含まれている5つの子要素が左から順に横に並んだ。これらの子要素のうち、一番右側の子要素にだけ「order: 3;」と指定すると、その子要素は左から何番目に配置されるか。{
	~左から1番目
	~左から2番目
	~左から3番目
	~左から4番目
	=左から5番目
}

::例題2.24::style要素に指定可能な属性を3つ選びなさい。 {
	~%33.3%type
	~%-33.3%src
	~%33.3%media
	~%33.3%nonce
	~%-33.3%charset
}

::例題2.23::親要素のCSSプロパティの設定を子要素に強制的に継承する際に指定する値は次のうちどれか。{
	~clone
	~derived
	~fork
	=inherit
}

::例題2.22::親要素のCSSプロパティの設定を子要素に強制的に継承する際に指定する値は次のうちどれか。{
	~clone
	~derived
	~fork
	=inherit
}

::例題2.21::親要素のCSSプロパティの設定を子要素に強制的に継承する際に指定する値は次のうちどれか。{
	~clone
	~derived
	~fork
	=inherit
}

::例題2.20::CSSを使って英単語の先頭だけを大文字表示する場合、text-transformプロパティに設定する値として正しいものを選びなさい。{
  ~ucfirst
  =capitalize
  ~uppercase
  ~camelcase
  ~proper
} #### 
A：PHPやPerlなどのプログラミング言語で用いられる、先頭を大文字に変換する関数の名前です。<br>
B：CSSにおいて、text-transformプロパティに設定することで、単語の先頭を大文字で表示することができますので、正解です。<br>
C：CSSにおいて、すべての文字を大文字で表示することができます。<br>
D：頭文字だけを大文字にして書く記法名称のひとつです。<br>
E：表計算アプリケーション等で用いられる、先頭を大文字に変換する関数の名前です。</dd>

::例題2.19::CSSのアニメーションの@keyframesの書式内において、「100%」の代わりに使用できるキーワードを1つ選びなさい。{
  =to
  ~end
  ~over
  ~last
  ~finished
} #### @keyframesの書式では、「0%」の代わりに「from」、「100%」の代わりに「to」が使用できます。よって、答えはAとなります。<br><br> キーワードではなくパーセント値を使用する場合には、必ず数値に「%」をつける必要があります。そのため、「0%」は正しい指定ですが、「0」は文法エラーとなります。<br>@keyframesの書式内においては、「%」は0でも省略できない点にも注意しましょう。

::例題2.18::CSSの背景に関する記述のうち正しいものをすべて選びなさい。{
  ~%-50%すべての背景関連プロパティは、カンマ区切りで複数の値を指定できる。
  ~%50%background-colorプロパティにはカンマ区切りの値を指定できない。
  ~%50%カンマ区切りで先（左側）に指定した背景画像ほど上（画面上で手前）に表示される。
  ~%-50%カンマ区切りで後（右側）に指定した背景画像ほど上（画面上で手前）に表示される。 
  ~%-50%backgroundプロパティにカンマ区切りの値を指定する際、背景色は先頭（一番左）に指定する値の１つとして指定する。
} #### CSS3からは、1つのボックスに複数の背景画像を指定できるようになりました。背景画像をカンマ区切りで指定すると、先（左側）に指定した背景画像ほど上（画面上で手前）に重なって表示されます。よってCは正しく、Dは間違いとなります。<br><br> カンマ区切りで指定した背景画像は個別の背景レイヤーに表示されますが、背景色はそれらすべての背景レイヤーのうち、一番下のレイヤーにのみ表示されます。そのため、背景色は一番下の背景レイヤーとなる一番右側の値の１つとして指定することになっています。よってEは間違いです。また、結果として背景色は値を1つしか指定できないことになり、Aは間違いで、Bは正しいことになります。							

::例題2.17::CSSのbox-shadowプロパティの値の指定方法として<u>間違っているもの</u>をすべて選びなさい。{
  =box-shadow: 1px;
  ~box-shadow: 1px 1px;
  ~box-shadow: 3px 3px 6px 2px;
  ~box-shadow: 3px 3px 6px 2px inset;
  ~box-shadow: rgba(0,0,0,0.5) 3px 3px 6px 2px inset;
} #### box-shadowプロパティの値の数値は、2個・3個・4個のいずれかを連続して指定する必要があります。よって、数値が1つしか指定されていないAは間違いです。<br><br>
影の「色」とキーワードの「inset」は、どちらもオプションです。BやCのように省略指定しても問題ありません。影の色を省略した場合のデフォルトは、colorプロパティの値となります。<br><br>
数値は必ず連続して指定する必要がありますが、色とinsetはそれらの数値の前後いずれにでも指定可能です。よって、DとEも間違いではありません。

::例題2.16::Web制作においてCSSの設定が複雑化し、ともすれば破綻しかねないケースがある。近年、Web制作のシーンでCSSを効率的に運用するための、運用・管理・命名規則などのルールや指針がいくつも発表されている。次の中で、CSSの効率的な運用方法のルール・指針と最も関係が薄いものはどれか。1つ選びなさい。{
  ~SMACSS
  =DOM
  ~OOCSS
  ~BEM
}

::例題2.15::HTML5のstyle要素にtype属性が指定されていない場合の、type属性のデフォルト値を記述しなさい。{
  text/css
}

::例題2.14::1つめのtr要素にのみスタイルを適用するセレクタをすべて選びなさい。{
  ~%33.333%tr:first-child
  ~%33.333%tr:nth-child(1) 
  ~%33.333%tr:nth-child(0n+1) 
  ~%-33.333%tr:nth-child(1n)
  ~%-33.333%tr:nth-child(1n+0)
} #### Aの「:first-child」は、要素内容の先頭にある要素を適用対象とするセレクタです。よって、まずはこれが答えの1つとなります。
残りのB〜Eのセレクタは、すべて (an+b) 形式の式を持っています。 (an+b) 形式の式において、aが0の場合はanは省略できます。上の選択肢Cの (0n+1) ではaが0なので、0nは省略できます。省略するとBの (1) と同じになります。つまり、BとCの式は同じもので、両方とも1番目の要素を適用対象としますので、これらも答えに含まれることになります。 
また、(an+b) 形式の式において、an+bのbが0の場合には+bが省略できます。上の選択肢Eの (1n+0) ではbが0なので、+bは省略でき、省略するとDの (1n) と同じになります。これらは1つめだけでなく、すべてのtr要素にスタイルを適用します。よって答えは A、B、C となります。 

::例題2.13::tr要素を12個含むtable要素があり次のCSSが適用された場合に、後述する設問に解答しなさい。
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
10番目のtr要素の背景色は何色になるか、次の選択肢から1つ選びなさい。
{
  ~白
  ~グレー
  ~薄黄色
  =薄ピンク
  ~薄緑
} #### tr要素に対するセレクタで背景色に#CCC（グレー）が指定されていますが、他のnth-child擬似クラスで指定されているスタイルの方が優先されます。<br>
10番目の要素は「3n+1」の条件に適合するので#FDD（薄ピンク）となります。

::例題2.11::1つのHTML文書に、次のような「ユーザーのスタイルシート」と「制作者のスタイルシート」が同時に指定されているとき、p要素のフォントサイズは何ポイントになるか。次の選択肢から選びなさい。
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
{
  ~11ポイント
  ~12ポイント
  =13ポイント
  ~14ポイント
  ~15ポイント
} #### 指定されているCSSが「ユーザーのスタイルシート」だけであった場合は、フォントサイズは最後の指定である12ポイントとなります。しかし、「制作者のスタイルシート」の1行目には !important が付けられているため、fontプロパティによる文字サイズの13ポイントが優先されて適用されます。「制作者のスタイルシート」の2行目と3行目の指定には !important が無いため無効となります。<br>
!important が無い場合は「ユーザーエージェント（ブラウザ）のスタイルシート」「ユーザーのスタイルシート」「制作者のスタイルシート」の順に適用の優先度が高くなります。!important がある指定はそれらよりも優先度は高くなりますが、その場合の優先度は「ユーザーエージェント（ブラウザ）のスタイルシート」「制作者のスタイルシート」「ユーザーのスタイルシート」の順となります。つまり、!important を付けた場合はユーザーによる要求の優先度を最も高くすることで、アクセシビリティを向上させる仕組みとなっています。

::例題2.10::CSSのセレクタのうち、書式が<u>間違っているもの</u>をすべて選びなさい。{
  ~%33.333%::root
  ~%-33.333%::before
  ~%-33.333%::after
  ~%33.333%::first-child
  ~%33.333%::last-child
} #### 疑似クラスと疑似要素の違いを明確にするために、CSS3（Selectors Level 3）では疑似要素名の前にはコロンを2つ付けることになっています。疑似クラスについては、CSS2.1と同様にコロンは1つだけ付けます。
選択肢の中で、疑似要素はBとCだけで、それ以外は疑似クラスですので、書式として間違っているのは A、D、E となります。CSS3の仕様では、上の選択肢にある疑似要素以外では ::first-line と ::first-letter が定義されています。なお、CSS1やCSS2.1との互換性を維持する目的で、ブラウザはコロンが1つだけの疑似要素を今後もサポートすることになっています。

::例題2.9::次のようなHTMLとCSSの組み合わせがある場合に、後述する設問に解答しなさい。
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
{
  ~p要素：18ピクセル／strong要素：18ピクセル
  ~p要素：14ピクセル／strong要素：18ピクセル
  =p要素：18ピクセル／strong要素：24ピクセル
  ~p要素：14ピクセル／strong要素：24ピクセル
} #### p要素に対してはleadクラスセレクタと、div>pの複合セレクタが競合することになります。<br>
同一の要素に対する指定では、セレクタ内のIDが多いもの、クラスが多いもの、要素が多いものの順で優先度が決まります。<br>
p要素に対してはleadクラスセレクタの優先度が高くなるので、文字サイズは18ピクセルとなります。<br>
strong要素にはleadクラスセレクタの文字サイズ指定が継承されますが、直接strong要素セレクタで上書きしているので24ピクセルとなります。<br>
継承や優先度はCSSの効率的な利用における重要なポイントとなります。

::例題2.8::次のようなHTMLとCSSの組み合わせがある場合に、後述する設問に解答しなさい。
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
全てのCSSプロパティが適切に動作する前提で、ブラウザのウィンドウ幅が450ピクセルの場合と、1200ピクセルの場合の段組数はそれぞれいくつになるか。<br>
なお「ブラウザのウィンドウ幅＝div要素の幅」と考えて構わないものとする。
{
  ~450ピクセル：3つ／1200ピクセル：3つ
  ~450ピクセル：3つ／1200ピクセル：7つ
  =450ピクセル：2つ／1200ピクセル：3つ
  ~450ピクセル：2つ／1200ピクセル：7つ
} #### columnsプロパティは段組の幅と数を指定します。column-gapプロパティは段組間の余白を指定します。<br>
	2014年8月現在ベンダープレフィックスを用いた書式と併記するのが一般的です。<br>
	columnsプロパティで指定した段組幅は、段組幅の下限として扱われます。<br>
	ウィンドウ幅が450ピクセルの場合、段組を3つ構成するとcolumn-gapプロパティを指定している関係で段組1つあたりの幅がcolumnsプロパティで指定した150ピクセルを下まわることになります。この場合、段組数が減らされ2つになります。<br>
	columnsプロパティで指定した段組数は、段組数の上限として扱われます。<br>
	ウィンドウ幅が十分広い場合でも、指定した数の段組が構成されます。<br>
	段組関係のプロパティは、通常のWebページで使用するだけでなく、レスポンシブWebデザインと組み合わせたり、電子書籍で使用したりすることが考えられます。

::例題2.7::CSSのwhite-spaceプロパティにおいて、ブラウザで表示させる際にもソースコード上の改行位置で改行させ、連続する半角スペース・タブ・改行コードを1つの半角スペースにまとめず、テキストがウィンドウの右端まで来たときには自動的に行を折り返すようにしたい場合に指定する値はどれか。正しいものを1つ選びなさい。 
{
  ~normal
  ~pre
  ~nowrap
  =pre-wrap
  ~pre-line
} #### white-spaceプロパティの値と表示との関係は次の表のようになっています。表の「改行」はソースコード上の改行位置で改行するかどうか、「まとめ」は連続する半角スペース・タブ・改行コードを1つの半角スペースにまとめるかどうか、「折り返し」はテキストがウィンドウの右端まで来たときに行を折り返すかどうかを示しています。正解は、表で「する」「まとめない」「折り返す」と書かれているpre-wrapとなります。

::例題2.7::次のlink要素のうち、style.css を正しく読み込む書き方をしているものはどれか。2つ選びなさい。
{
  ~%-50%&lt;link href=&quot;style.css&quot;&gt;
  ~%-50%&lt;link href=&quot;style.css&quot; type=&quot;text/css&quot;&gt;
  ~%50%&lt;link rel=&quot;stylesheet&quot; href=&quot;style.css&quot;&gt;
  ~%50%&lt;link rel=&quot;stylesheet&quot; href=&quot;style.css&quot; type=&quot;text/css&quot;&gt;
  ~%-50%&lt;link rel=&quot;stylesheet&quot; href=&quot;style.css&quot; type=&quot;text/plain&quot;&gt; 
} #### link要素にはrel属性の指定が必須です。よって、AとBは style.css を読み込みません。Cはtype属性が省略されていますが、HTML5ではrel属性の値が「stylesheet」の場合は「text/css」がデフォルト値として設定されているため、Cは style.css を読み込みます。Dは必要な属性が正しく指定されていますので問題なく style.css を読み込みます。Eは、CSS向けのMIMEタイプではない「text/plain」がtype属性の値として指定されていますので、style.css は読み込みまれません。 

::例題2.6::link要素で外部スタイルシートを読み込む際に、rel要素の値として指定する語を記述しなさい。
{
  <span> stylesheet</span>
} #### link要素で外部スタイルシートを読み込む場合、rel属性には値として「stylesheet」を指定します（「rel=&quot;stylesheet&quot;」）。rel属性はリンクされている他のリソースファイルのタイプを指定します。<br />
	外部スタイルシートのリンク以外に使用する場合には異なる値を指定することになりますが、指定する値はいずれも大文字・小文字を区別しません。<br />
	つまり「STYLESHEET」や「StyleSheet」と記述しても正解です。

::例題2.4::次に示すセレクタの中で、計算上もっとも優先順位が高くなる指定はどれか。１つ選びなさい。
{
	~*#abc ul
	=#abc #def ul
	~body#abc ul
	~#ab.cd.ef.gi.hj.kl.mn.op.qr.st.uv.wx.yz ul
	~*#ab.cd.ef.gi.hj.kl.mn.op.qr.st.uv.wx.yz ul
} #### セレクタによる適用の優先順位は、セレクタに含まれる「idセレクタの数」「属性関連セレクタ（classセレクタ・属性セレクタ・疑似クラス）の数」「要素関連セレクタ（タイプセレクタ・疑似要素）の数」で3桁の数字を作り、その数字が大きいものほど高くなります。このとき、ユニバーサルセレクタ（*）は無視されます。
しかしこの計算においては、いずれかの桁の数字が10以上になったとしても、決して繰り上がることはないルールになっている点に注意してください（つまり10進数ではなく、たとえば100進数の3桁のような数字として計算するということです）。ここで、便宜的に16進数でこれらの3桁をあらわしてみると、Aは101、Bは201、Cは102、Dは1C1、Eも1C1となり、Bが一番大きな数字となります（10進数の12は、16進数のCであるため）。よって正解はBです。

::例題2.3::CSSにおけるシンプルセレクタのうち、ユニバーサルセレクタ（Universal selector）に関する説明として正しいものを選びなさい。
{
	~ドット(.)を~=の代わりとして利用し、クラス属性における特定の属性値を持つ要素を示す。
	=アスタリスク(*)を用いて表記され、全ての型の要素を示す。
	~タッシュタグ(#)の後にID型属性の値を記述し、特定のID属性を持つ要素を示す。
	~要素名を記述し特定の要素型の要素を示す。
	~任意の属性名と属性値を指定することで、その属性を指定している要素およびその属性値を持つ要素を示す。
} #### Aはクラスセレクタに関する説明なので間違いです。<br>
Bはユニバーサルセレクタに関する説明なので正解です。<br>
CはIDセレクタに関する説明なので間違いです。<br>
Dはタイプセレクタに関する説明なので間違いです。<br>
Eは属性セレクタに関する説明なので間違いです。

::例題2.2::CSSにおいて、div要素の背景色が半透明になる記述として正しいものを１つ選びなさい。{
  ~div {background-color: rgba(255,0,0,128);}
  ~div {background-color: #FF000088;}
  =div {background-color: rgba(255,0,0,0.5);}
  ~div {background-color: transparent;}
  ~div {background-color: rgba(100%,0%,0%,50%);}
} #### <p>background-colorプロパティにおいて、半透明の色を指定する場合は、rgba()またはhsla()で色を指定する必要があります。<br>
rgba()で色を指定する場合、r値・g値・b値の3つの値は0-255の値で指定し、4つめのアルファ値は0-1の範囲で指定します。<br>
アルファ値は色の透明度を指定する値で、この値が0の場合は透明度が100%（完全な透明色）になり、1の場合は透明度が0%となります。<br>
よって正解はCです。</p>
<p>Aはアルファ値を128と指定しており、最大値の1を超えているので不正解です。<br>
Bのように#で始まる書き方で半透明を指定する事はできません。<br>
Dのtransparentは、完全な透明色を指定する値で半透明にはなりません。<br>
Eは、アルファ値を%で指定しているので半透明にならず不正解です。rgbの各値は%指定可能なのでアルファ値が0.5とかであれば半透明になります。</p>

::例題2.1::以下のHTMLにおけるテーブルについて、キャプションがテーブルの下の位置に配置されるように指定したい。この時、キャプションに対して指定するCSSの記述として正しいものを選択肢から選びなさい。 
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
{
  ~tr{caption-virtical: bottom;}
  ~caption{caption-virtical: bottom;}
  ~caption{caption-align: bottom;}
  =caption{caption-side: bottom;}
  ~caption{caption-bottm: yes;}
} #### この場合、キャプションの文字はcaptionタグで指定しています。問題のコードにおけるtr要素はcaption要素を含んでいません。よって、Aはプロパティの名前に関係なく間違いです。
	  テーブルにおけるキャプション位置は、caption-sideプロパティで行います。
	  A,B,C,Eのプロパティは、CSSにおいては存在しません。
	  よって、答えはDです。


::問題２．２１::データベースに登録された英語住所が大文字小文字混在しているため、CSSを用い、すべて大文字で表示したい。text-transform プロパティで指定する値として適切なのは次のうちどれか。
{
	=uppercase
	~lowercase
	~capitalize
	~acronym
	~abbreviation
}

::問題２．２０::下記のHTML/CSSコードにおける transition についての説明として正しいのは次のうちどれか。３つ選びなさい。
{
	~%-50%マウスポインタをボタン上に置いた時、ボタンの変形と文字色の変化は同時に開始する。
	~%50%マウスポインタをボタン上に置いた時、ボタンの変形は文字色の変化完了の0.2秒後に完了する。
	~%50%ボタンをクリックした時、文字色の変化と背景色の変化は同じ時間経過で遷移する。
	~%-50%ボタンのクリックを解除した時、瞬時にボタンは初期状態になる。
	~%50%ボタンはクリックしたままマウスポインタを遠ざけた時、ボタン形状は元に戻るが色は変わらない。
}

::問題２．１９::長い間大きな変更をしてなかったホームページを急遽レスポンシブWEBデザインに対応するよう依頼され、下記のように最小限の変更で対応した。【１】〜【３】に入る文字列の組み合わせとして最適なのは次のうちどれか。
{
	~hide, true, false
	~visibility, hidden, visible
	~display, invisible, visible
	=display, none, block
	~opacity, 0, 1
}

::問題２．１８::以下は、ボタンにアニメーションを設定した例である。説明として<u>間違っているもの</u>は次のうちどれか。２つ選びなさい。
{
	~%50%ボタンの形状は、正方形である。
	~%-50%マウスがボタン上に来ると、ボタンが大きくなる。
	~%50%マウスがボタン上に来ると、ボタンの色が薄い青になる。
	~%-50%マウスがボタン上に来ると、0.8秒かけて変形する。
	~%-50%ボタンを押すと、ボタンの背景色が赤に変わる。
}

::問題２．１７::HTMLファイルをブラウザで表示したところ、下記のように表示された。HTMLファイルの下線部に入るCSSのプロパティ名を2つ選びなさい。
{
	~%-50%case-transform
	~%50%text-transform
	~%-50%word-wrap
	~%-50%word-break
	~%50%white-space
}

::問題２：１３::transformプロパティで指定できない関数を1つ選びなさい。
{
	~perspective
	~rotate3d
	~scale3d
	~translate3d
	=opacity
}
