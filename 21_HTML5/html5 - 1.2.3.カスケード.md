$CATEGORY: 1.2.3 カスケード（優先順位）



        
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
                ~白
                ~グレー
                ~薄黄色
                ~薄ピンク
                ~薄緑
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
								~11ポイント
								~12ポイント
								~13ポイント
								~14ポイント
								~15ポイント
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
<dt id="lv1_2_4">例題2.4「1.2.3 カスケード（優先順位）」</dt>
<dd>
レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_123">1.2.3 カスケード（優先順位）</a>」からの出題です。<br>
次に示すセレクタの中で、計算上もっとも優先順位が高くなる指定はどれか。１つ選びなさい。
</dd>
<dd>
<ul class="option">
	~*#abc ul
	~#abc #def ul
	~body#abc ul
	~#ab.cd.ef.gi.hj.kl.mn.op.qr.st.uv.wx.yz ul
	~*#ab.cd.ef.gi.hj.kl.mn.op.qr.st.uv.wx.yz ul
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
