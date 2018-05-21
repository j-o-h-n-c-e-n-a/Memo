$CATEGORY: 1.1 Webの基礎知識

::問題１．２２::Ajax と最も関連のない技術は次のうちどれか。{
	~Javascript
    =JavaServerPages
    ~jQuery
    ~JSON
	~XMLHttpRequest
}

::問題１．２１::カスタムデータ属性 (data-*) 名の * 部分の使用制限として正しいのは次のうちどれか。３つ選びなさい。{
	~ハイフン（-）を使ってはならない。
    =xml で始めてはならない。
    =コロン (:) を使ってはならない。
    =大文字の A から Z を使ってはならない。
	~アンダースコア（_）を使ってはならない。
}

::問題１．２０::価格を表示する箇所で円マーク(¥)を正しく表示できないのは次のうちどれか。
なお、文字セットは UTF8、フォントは arial、円マークの unicode 文字番号は10進表記で165とする。{
	~&amp;yen;
    ~&amp;#165;
    =&#o245;
    ~&amp;#xA5;
	~¥
}

::問題１．１９::link 要素の rel 属性の使用方法として正しいものを2つ答えよ。{
    ~&lt;link rel="stylesheet" href="/default.css" type="text/css"&gt;
    ~&lt;link rel="alternate" href="/en/index.html" hreflang="English"&gt;
    ~&lt;link rel="alternate" media="smartphone" href="/m/index.html"&gt;
    ~&lt;link rel="canonical" href="https://example.com/"&gt;
}


     <div class="question">
    <dl>
      <dt>例題1.19「1.1.2 HTMLの書式」</dt>
      <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_112">1.1.2 HTMLの書式</a>」からの出題です。<br>
      link 要素の rel 属性の使用方法として正しいものを2つ答えよ。</dd>
      <dd>
        <ul class="option">
          <li>&lt;link rel="stylesheet" href="/default.css" type="text/css"&gt;
          <li>&lt;link rel="alternate" href="/en/index.html" hreflang="English"&gt;
          <li>&lt;link rel="alternate" media="smartphone" href="/m/index.html"&gt;
          <li>&lt;link rel="canonical" href="https://example.com/"&gt;
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>正解<span> A、D</span></dt>
    <dd>
     link要素は、外部リソースを参照する際に使用する要素です。<br><br>
Bの他言語対応のページで指定できるhreflangは、ISO 639の言語コードと国コードの組み合わせで指定する必要があり、"en", "en-us",
"fr-ca" などの形式になります。<br>
Cのmediaに指定できる値に、smartphoneはありません。携帯デバイスの場合、”handheld”を使用します。<br>
DのcanonicalはSEOへの重複ページの影響を回避できます。
    </dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_112">出題範囲の詳細</a></p>
                        <div class="present">
    						<p>LPI-Japan<br>中谷　徹</p>
						</div>
</div>
  </div>
   <div class="question">
    <dl>
      <dt>例題1.18「1.1.3 Web関連技術の概要」</dt>
      <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_113">1.1.3 Web関連技術の概要</a>」からの出題です。<br>
      下記のように分類される画像をWebで使用する際にそれぞれフォーマットとして最も適した組み合わせは次のうちどれか。</dd>
        <div class="box">
        <p style="padding-top:0;">グループ①<br>
・写真が多く、フルカラー（1670万色）で表示したい<br>
・グラデーションのデザイン画がある<br>
・背景を透過したい
</p>
          <p>グループ②<br>
・企業ロゴなどのイラスト、アイコンが多い<br>
・アイコンにアニメーションを入れたい
</p>
        </div>
      <dd>
        <ul class="option">
          <li>BMP と PNG
          <li>PNG と GIF
          <li>JPEG と GIF
          <li>JPEG と PNG
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>正解<span> B</span></dt>
    <dd>
     選択肢の中でアニメーションが可能な画像はGIFのみなので、AとDは不正解です。<br>
BとCのPNGとJPEGでは、ともにフルカラーで表示できますが、背景を透過できるのはPNGのみなので、正解はBになります。<br><br>

・BMP(Bitmap Image)は、Windowsに作られた画像フォーマットで、Webでは使用できません。<br>
・JPEG(Joint Photographic Experts Group) の特徴は、フルカラーの表現ができ、グラデーションも綺麗に表現します。<br>
・PNG(Portable NetworkGraphics)は、JPEGと同様、フルカラーの表現ができますが、ファイルサイズがJPEGより大きくなる場合があります。JPEGと異なり、背景の透過が可能です。<br>
・GIF(Graphics Interchange Format)は、背景の透過が可能で、アニメーションも可能ですが、256色までしか表現できません。過去に透過GIFでライセンスの問題が発生しPNGが開発された経緯があります。<br>
上記以外にTIFF(Tagged Image File Format)と言うフォーマットもあります。高解像度の画像に向いていますが、サイズが大きくなります。

    </dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_113">出題範囲の詳細</a></p>
                        <div class="present">
    						<p>LPI-Japan<br>中谷　徹</p>
						</div>
</div>
  </div>

    <div class="question">
    <dl>
      <dt>例題1.17「1.1.3 Web関連技術の概要」</dt>
      <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_113">1.1.3 Web関連技術の概要</a>」からの出題です。<br>
      ウェブサイトのコンテンツを、一元的に管理する仕組みの名称として最もふさわしいものを選択してください。</dd>
      <dd>
        <ul class="option">
          <li>Blog
          <li>CMS
          <li>リポジトリ
          <li>データウェアハウス
          <li>フレームワーク
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>正解<span> B</span></dt>
    <dd>
     コンテンツを一元的に管理する仕組みのことを、CMS(Contents Management System)と呼びます。<br>一般には、ウェブサイトのコンテンツをウェブブラウザからHTMLの知識を必要とせず編集できるものをCMSと呼ぶことが多いです。<br>A. BlogもCMSの一形態と言えますが、時系列のある記事を管理することに特化しているため、最もふさわしいとは言えない選択肢です。<br><br>その他の選択肢については、C.リポジトリはバージョン管理システム、D.データウェアハウスはデータベース、E.フレームワークはアプリケーション開発と、異なる領域の用語ですので間違いです。
    </dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_113">出題範囲の詳細</a></p>
	<div class="present">
    <p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル２認定者　高井 歩 氏</p>
	</div>
</div>
  </div>
  
    <div class="question">
    <dl>
      <dt>例題1.16「1.1.2 HTMLの書式」</dt>
      <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_112">1.1.2 HTMLの書式</a>」からの出題です。<br>
      titleタグについての説明で、間違っているものを選択してください。</dd>
      <dd>
        <ul class="option">
          <li>headタグ内に記述する必要がある
          <li>SEO対策として、title要素は重要である
          <li>HTML4.01,HTML5ともにtitleは必須タグである
          <li> titleには文書の内容を表す文章を記述する
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>正解<span> C</span></dt>
    <dd>
     HTML5での変更点として、titleタグが必須では無くなったことが挙げられます。<br>HTML4.01まではtitleタグは省略することが出来ませんでしたが、HTML5では必要が無ければ省略することが出来ます。<br>最近のウェブブラウザ、とくにスマートフォンやタブレットでのウェブブラウザにおいて、titleで指定したタイトルが表示されないケースもあるため、titleに頼った情報提供は推奨されなくなってきています。<br>しかし、PCのブラウザでは重要な項目ですので、ウェブサイトのターゲット層にあわせてtitleタグの有無や内容を決める必要があります。

    </dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_112">出題範囲の詳細</a></p>
	<div class="present">
    <p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル２認定者　高井 歩 氏</p>
	</div>
</div>
  </div>

  
    <div class="question">
    <dl>
      <dt>例題1.15「1.1.1 HTTP, HTTPSプロトコル」</dt>
      <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_111">1.1.1 HTTP, HTTPSプロトコル</a>」からの出題です。<br>
      HTTPに規定されている認証方式に関する説明として、正しいものを2つ選択してください。</dd>
      <dd>
        <ul class="option">
          <li>BASIC認証では、ID,パスワードをウェブブラウザ標準の暗号化方式で送信する
          <li>Digest認証では、ユーザ名とパスワードを、MD5でダイジェスト化して送信する
          <li>Digest認証では、ユーザ名とパスワードを、暗号化せずに一部のみ送信する
          <li>BASIC認証では、ID,パスワードを暗号化せずに送信する
          <li>Captcha認証では、機械には判別しにくい画像を使用して認証を行なう
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>正解<span> B,D</span></dt>
    <dd>
     HTTPを使用してウェブページなどを表示する際に、ユーザ名とパスワードが一致しないとエラーにする手段を認証と言います。<br>
     HTTPでは、BASIC認証とDigest認証という二種類の認証方法が規定されています。
認証が必要とされるウェブページ(などのリソース)にアクセスすると、ユーザ名とパスワードの入力が求められます。
。<br>
     BASIC認証では、ユーザが入力したユーザ名とパスワードは一切暗号化されることなく送信されます。<br>
     Digest認証では、ユーザ名とパスワードは、MD5というハッシュ関数(簡単に言うと逆算して元の文字列を推測しにくい文字列に変換)を使用して、ユーザ名とパスワードをダイジェスト(ハッシュ)化して送信します。<br>
     ウェブサーバは、毎回異なるランダムな文字列をブラウザに送信してハッシュ関数に使用するため、ネットワークを盗聴しても、ユーザ名とパスワードを盗まれにくい仕組みになっています。<br>
     ウェブ制作の現場では、作成中のウェブページを非公開にして制作とクライアントの間でのみ閲覧可能にする場合などに認証はよく使われています。<br>
     認証を行なうためにはウェブサーバ側に設定が必要ですので、利用する場合にはウェブサーバの仕様を確認してください。<br>
    Captcha認証の説明は、説明としては正しいですが、HTTPに規定されている認証方式ではありませんので、間違いとなります。 
    </dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_111">出題範囲の詳細</a></p>
	<div class="present">
    <p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル２認定者　高井 歩 氏
</p>
	</div>
</div>
  </div>

  <div class="question">
    <dl>
      <dt>例題1.14「1.1.2 HTMLの書式」</dt>
      <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_112">1.1.2 HTMLの書式</a>」からの出題です。<br>
      HTML5の文書型宣言として間違っているものを2つ選びなさい。</dd>
      <dd>
        <ul class="option">
          <li>&lt;!doctype&gt;
          <li>&lt;!doctype html&gt;
          <li>&lt; !DOCTYPE HTML&gt;
          <li>&lt;!DOCTYPE HTML &gt;
          <li>&lt;!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01//EN"&gt;
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>正解<span> A、C</span></dt>
    <dd>
      HTML5の文書型宣言の基本形は、「&lt;!DOCTYPE」＋1個以上のスペース＋「HTML」＋0個以上のスペース＋「&gt;」です。アルファベットは大文字でも小文字でもかまいません。<br>
      Aは文字列「HTML」が含まれていないので間違いです。Cは「&lt;!DOCTYPE」のように続けて書くべきところを「&lt; !DOCTYPE」のようにスペースを入れているので間違いとなります。<br>
      Dのように「HTML」と「&gt;」の間にスペースを入れるのは間違いではありません。<br>
      HTML5では、HTML5の短い文書型宣言に未対応のオーサリングツールのために、HTML4.0、HTML4.01、XHTML1.0、XHTML1.1の文書型宣言も使用できる仕様となっています（ただしStrictのみ）。よって、Eの文書型宣言はHTML5でも問題なく使用できます。
    </dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_112">出題範囲の詳細</a></p>
	<div class="present">
    <p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル１認定者　大藤 幹 氏</p>
	</div>
</div>
  </div>
  <div class="question">
    <dl>
      <dt>例題1.13「1.1.2 HTMLの書式」</dt>
      <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_112">1.1.2 HTMLの書式</a>」からの出題です。<br>
      HTML5のtitle要素に関する記述のうち、間違っているものをすべて選びなさい。</dd>
      <dd>
        <ul class="option">
          <li>1つのHTML文書に必ず1つ必要。
          <li>head要素内に配置する。
          <li>複数は配置できない。
          <li>要素内容にはテキストしか入れられない。
          <li>条件によっては終了タグを省略できる。
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>正解<span> A、E</span></dt>
    <dd>
      HTML5より前のHTML/XHTMLでは、title要素は1つの文書に必ず1つ必要でした。しかし、HTML5では「iframe要素のsrcdoc属性で指定する文書」および「上位レベルのプロトコルがタイトル情報を提供する場合（たとえば電子メールとしての件名が付けられているHTMLメールなど）」においては、title要素を省略することが可能です。したがって、選択肢のAは間違いです。 また、title要素自体は条件によっては省略可能ですが、開始タグ・終了タグともにタグの省略は一切できません。そのため、選択肢のEも間違いです。
    </dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_112">出題範囲の詳細</a></p>
	<div class="present">
    <p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル１認定者　大藤 幹 氏</p>
	</div>
</div>
  </div>
  <div class="question">
    <dl>
      <dt>例題1.12「1.1.2 HTMLの書式」</dt>
      <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_112">1.1.2 HTMLの書式</a>」からの出題です。<br>
      文字（実体）参照として無効な記述を選択してください。</dd>
      <dd>
        <ul class="option">
          <li>&amp;amp;
          <li>&amp;#39;
          <li>&amp;#x266A;
          <li>&amp;0x1A;
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>正解<span> D</span></dt>
    <dd>
      HTMLなどで意味のある記号として扱われる、"&lt;"、"&gt;"や、直接入力できない文字を表示するための仕組みが、文字(実体)参照です。<br>
      たとえば、文章内に"&lt;p&gt;"と書かれていれば、Webブラウザはタグとして処理しようとします。しかし、製作者の意図としては、文章の一部として表示してほしいとします。<br>
      このようなときに、"&lt;"を"&amp;lt;"、"&gt;"を"&amp;gt;"と記述することで、Webブラウザはタグとして処理せず、表示上だけ、それぞれ"&lt;","&gt;"とすることができます。<br>
      よくつかわれる文字参照としては、<br>
      &amp;lt; &lt;<br>
      &amp;gt; &gt;<br>
      &amp;amp; &amp;<br>
      &amp;copy; &copy;<br>
      &amp;nbsp; 空白文字<br>
      などが挙げられます。これらは、記号の名称(略称)を&amp;の後に記述し、最後に";"を付けます。<br>
      名称を指定する以外にも、文字コード(番号)を指定する方法もあります。<br>
      文字コードを指定する場合には2種類の書き方があり、&amp;#10進数; と、 &amp;#x16進数; です。<br>
      したがって、D.の書式は無効です。
    </dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_112">出題範囲の詳細</a></p>
	<div class="present">
    <p>例題解説の提供：<a href="http://html5exam.jp/measures/learning.html">HTML5アカデミック認定校</a>　<a href="http://html5exam.jp/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル２認定者　高井 歩 氏</p>
	</div>
</div>
  </div>
  <div class="question">
    <dl>
      <dt>例題1.11「1.1.2 HTMLの書式」</dt>
      <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_112">1.1.2 HTMLの書式</a>」からの出題です。<br>
      HTML5のコンテンツ・モデル（Content models）において、セクショニング・コンテンツ（Sectioning content）である要素の組み合わせで適切なものはどれか。正しいものを1つ選びなさい。</dd>
      <dd>
        <ul class="option">
		    <li>h1 h2 h3 h4 h5 h6
		    <li>footer header main section
		    <li>blockquote body fieldset figure td
		    <li>article aside nav section
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>正解<span> D</span></dt>
    <dd>
    	HTML5ではコンテンツ・モデルに基いて要素を配置します。コンテンツ・モデルのコンテンツのカテゴリーは次の7つです。
    	<ul>
    		<li>メタデータ・コンテンツ
    		<li>フロー・コンテンツ
    		<li>セクショニング・コンテンツ
    		<li>ヘッディング・コンテンツ
    		<li>フレージング・コンテンツ
    		<li>エンベッディッド・コンテンツ
    		<li>インタラクティブ・コンテンツ
    	</ul>
    	セクショニング・コンテンツは基本的に、見出しとそれに関連付けられたコンテンツによるアウトラインを含みます。<br>
		選択肢Aはヘッディング・コンテンツの要素です。選択肢Cはセクショニング・コンテンツには含まれませんが、セクショニング・ルートと呼ばれる要素で、独自のアウトラインを持つことができます。
    </dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_112">出題範囲の詳細</a></p>
	<div class="present">
    <p>例題解説の提供：<a href="http://html5exam.jp/measures/learning.html">HTML5アカデミック認定校</a>　<a href="http://html5exam.jp/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル１認定者　林拓也 氏</p>  
	</div>
</div>
  </div>
  <div class="question">
    <dl>
      <dt>例題1.10「1.1.3 Web関連技術の概要」</dt>
      <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_113">1.1.3 Web関連技術の概要</a>」からの出題です。<br>Data URIについての解説で誤っているのを選択してください。</dd>
      <dd>
        <ul class="option">
		    <li>主にWebサイト表示の高速化のための技術である
		    <li>画像ファイルなど、HTMLファイルの外にあるファイルの場所を指すURIである
		    <li>画像データのエンコードはBase64形式で行なわれる
		    <li>ブラウザによって対応状況に差がある
		    <li>HTML、CSSで使用できる
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>答え<span> B</span></dt>
    <dd>Data URIは、通常外部ファイルへのURIを記述する、imgタグのsrc属性やCSSのurl()に直接画像データなどを埋め込むための技術です。<br>
	Data URIはデータの場所を指すものではありませんので、B.の説明は間違っています。<br>
	その他の説明は正しいです。<br>
	A. 1度のリクエストでData URIで埋め込まれた画像も取得できるため、通信回数を削減できます。<br>
	C. 画像データにはテキストとして見ると表示可能文字以外も含まれていますが、Base64エンコードをすることで文字として表わすことが出来るようになります。<br>
	D. 一部ブラウザ(IE8未満など)では対応していなかったり、扱えるデータ形式に制限があります。<br>
	E. HTMLではsrc属性など、CSSではbackground-imageのurl指定で使用することができます。</dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_113">出題範囲の詳細</a></p>
  <div class="present">
    <p>例題解説の提供：<a href="http://html5exam.jp/measures/learning.html">HTML5アカデミック認定校</a>　<a href="http://html5exam.jp/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル２認定者　高井 歩 氏</p>
  </div>
</div>
  </div>
  <div class="question">
    <dl>
      <dt>例題1.9「1.1.2 HTMLの書式」</dt>
	  <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_112">1.1.2 HTMLの書式</a>」からの出題です。<br>HTML5で、文字エンコーディングを設定するために有効な書式を2つ選びなさい。</dd>
      <dd>
        <ul class="option">
	      <li>&lt;html lang=&quot;ja&quot;&gt;
	      <li>&lt;html charset=&quot;UTF-8&quot;&gt;
	      <li>&lt;meta charset=&quot;UTF-8&quot;&gt;
	      <li>&lt;meta http-equiv=&quot;Content-Type&quot; content=&quot;text/html; charset=UTF-8&quot;&gt;
	      <li>&lt;meta encoding=&quot;UTF-8&quot;&gt;
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>答え<span> C,D</span></dt>
    <dd>HTML5では、文書のエンコーディングをC.のように短縮して記述することができるようになりました。<br>
	また、D.のようなHTML4までの表記も継続して使用できます。<br>
	A.は使用言語の指定ですので、文字エンコーディングの指定ではありません。<br>
	B.はhtmlタグにはcharset属性はありません。<br>
	E.はmetaタグにはencoding属性はありません。<br>
	Webページの文字化けを防ぐためにも、文字エンコーディングは指定すべきですし、当然HTMLファイルの文字エンコーディングと一致させる必要があります。<br>
</dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_112">出題範囲の詳細</a></p>
  <div class="present">
    <p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル２認定者　高井 歩 氏</p>
  </div>
</div>
  </div>
  <div class="question">
    <dl>
      <dt>例題1.8「1.1.1 HTTP, HTTPSプロトコル」</dt>
      <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_111">1.1.1 HTTP, HTTPSプロトコル</a>」からの出題です。<br>SSL/TLSの規格として古い順に並べたものを選びなさい</dd>
      <dd>
        <ul class="option">
			<li>SSL 1.0,TLS 1.0,TLS 1.1,TLS 1.2,SSL 2.0,SSL 3.0
			<li>TLS 1.0,TLS 1.1,TLS 1.2,SSL 1.0,SSL 2.0,SSL 3.0
			<li>SSL 1.0,SSL 2.0,SSL 3.0,TLS 1.0,TLS 1.1,TLS 1.2
			<li>TLS 1.0,SSL 1.0,TLS 1.1,SSL 2.0,SSL 3.0,TLS 1.2
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>答え<span> C</span></dt>
    <dd>HTTPSで使用される暗号化などのセキュリティに対応した通信プロトコルの規格についての出題です。<br>
	規格にはSSL(Secure Sockets Layer)とTLS(Transport Layer Security)の2種類があります。<br>
	一般にはSSLと総称されることが多いのですが、現在ではセキュリティ上の問題から、SSLよりもTLSを使用することを推奨されています。<br>
	規格成立の年代を見ると、SSL 1.0(未公開)、SSL 2.0(1994年)、SSL 3.0(1995年)、TLS 1.0(1999年)、TLS 1.1(2006年)、TLS 1.2(2008年)<br>
	となります。つまり、SSLの後に、TLSが制定されていることになります。<br>
	最近(2014/10)、SSL 3.0に脆弱性が発見され、各Webブラウザでは、SSL 3.0の対応を打ち切る方向でバージョンアップが行なわれています。<br>
	ちなみに、SSL/TLSの規格のバージョンと、OpenSSLなどの実際のプログラムのバージョンを混同しないよう注意が必要です。</dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_111">出題範囲の詳細</a></p>
  <div class="present">
    <p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル２認定者　高井 歩 氏</p>
  </div>
</div>
  </div>
  <div class="question">
    <dl>
      <dt>例題1.7「1.1.1 HTTP, HTTPSプロトコル」</dt>
      <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_111">1.1.1 HTTP, HTTPSプロトコル</a>」からの出題です。<br>HTTPSを使用して、Webサーバの正当性を確認するために必要なものを2つ選びなさい。</dd>
      <dd>
        <ul class="option">
			<li>認証局
			<li>クライアント証明書
			<li>承認局
			<li>サーバ証明書
			<li>署名局
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>正解<span> A,D</span></dt>
    <dd>
        HTTPSはWebクライアントとWebサーバの間の通信を暗号化する他に、Webサーバの正当性を保証する仕組みを持っています。<br>
        正当性を保証するために、Webサーバにはサーバ証明書(D)と呼ばれるファイルを設置します。<br>
        サーバ証明書には、Webサーバのホスト名などの情報の他、正当性を保証するための第三者機関による認証局(A)による電子署名が付与されています。<br>
        Webクライアントでは、アクセスするWebサーバからサーバ証明書を受けとると、認証局へ問い合わせを行ない、証明書の正当性を確認します。<br>
        最近のWebブラウザでは、正当性が確認されたWebページにはアドレスバーに南京錠のアイコンなどが表示されるようになっています。<br>
        なお、クライアント証明書(B)はクライアントの正当性を確認する必要がある場合にのみ使用されます。<br>
        また、承認局(C)、署名局(E)という用語はありません。
    </dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_111">出題範囲の詳細</a></p>
  <div class="present">
    <p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル２認定者　高井 歩 氏</p>
  </div>
</div>
  </div>
<div class="question">
<dl>
<dt>例題1.6「1.1.3 Web関連技術の概要」</dt>
<dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_113">1.1.3 Web関連技術の概要</a>」からの出題です。<br>
Base64についての説明で誤っているものを一つ選択しなさい。</dd>
<dd>
  <ul class="option">
	<li>バイナリデータを印字可能文字に置き換える仕組みである
	<li>データ量は変換前と変換後で変わらない
	<li>英数字と記号を使用する
	<li>端数に当たる部分には'='を使用する
	<li>変換後は1行64文字で改行される
  </ul>
</dd>
</dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>正解<span> B</span></dt>
    <dd>Base64は、バイナリデータやマルチバイト文字列(日本語など)をルールに従ってASCII文字のうち、英数字と記号の印字可能文字だけで記述されたテキストデータに変換します。<br>
ASCII文字とは英数字と記号など俗に半角文字(ASCII文字)と呼ばれる文字のことです。<br>
ASCIIテキストデータに変換することで、ASCIIテキストしか扱えない通信方式やテキストエディタでデータを扱えるようになります。<br>
変換の手順は以下のようになります。<br>
まずもとになるデータを24ビット取りだし、6ビットずつ4つに切り分けます。次に、6ビットで表せる数、0から63までを対応表を使って0→A,1→Bのように4文字の印字可能文字に変換します。<br>
最後に印字可能文字をそれぞれASCIIコード8bitで表現します。そのため、変換前のデータ24ビットにつき、変換後のデータ量は32ビットになります。<br>
これをデータが終わるまで繰り返します。</dd>
<dd>その他の選択肢については以下の通りです。<br>
A.バイナリデータ(不可視文字を含む)を印字可能文字を使って表現する仕組みです。<br>
C.Base64ではA-Z,a-z,0-9,+,/の64文字を使用します。<br>
D.元のデータが24ビットで割り切れない場合は、足りない分を'='で埋めます。<br>
E.変換後の文字列が64文字以上になった場合は、64文字ごとに改行文字を挿入します。</dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_113">出題範囲の詳細</a></p>
  <div class="present">
    <p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル２認定者　高井 歩 氏</p>
  </div>
</div>
  </div>
  <div class="question">
    <dl>
      <dt>例題1.5「1.1.1 HTTP, HTTPSプロトコル」</dt>
      <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_111">1.1.1 HTTP, HTTPSプロトコル</a>」からの出題です。<br>
      HTTPSに関する説明で、正しいものを2つ選びなさい。
      </dd>
      <dd>
        <ul class="option">
          <li>HTTP通信の速度向上を目的に使用される。
          <li>HTTPS通信ではHTTP通信は行われない。
          <li>HTTPSでは、データを暗号化して送受信する。
          <li>HTTPS通信には、TLS（またはSSL）プロトコルも使われる。
          <li>HTTPSはIETFにより標準化されている。
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>答え<span> C、D</span></dt>
    <dd>HTTPSはセキュリティ向上のために使用されます。セキュリティ向上のためにデータを暗号化して送受信します。<br>
    データの暗号化にはTLS（またはSSL）プロトコルが使われ、まずTLS（またはSSL）のセッションを確立し、その後にHTTP通信を行います。<br>
    HTTPはIETFにより標準化されています（RFC2616）が、HTTPSは標準化されていません。なお、RFC2181「HTTP Over TLS」の文書がありますが、これは情報適用用の「メモ」という位置づけで、標準を定めるものではありません。
    </dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_111">出題範囲の詳細</a></p>
  <div class="present">
    <p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル１認定者　林 拓也 氏</p>
  </div>
</div>
  </div>
  <div class="question">
    <dl>
      <dt>問題1.4 「1.1.2 HTMLの書式」</dt>
      <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_112">1.1.2 HTMLの書式</a>」からの出題です。<br>
      HTML5文書において、外部スタイルシート「style.css」を読み込ませるための記述として正しいものを１つ選びなさい。</dd>
      <dd>
        <ul class="option">
			<li>&lt;link href=&quot;style.css&quot;&gt;
			<li>&lt;link href=&quot;style.css&quot; type=&quot;text/css&quot;&gt;
			<li>&lt;link rel=&quot;text/css&quot; href=&quot;style.css&quot;&gt;
			<li>&lt;link rel=&quot;stylesheet&quot; href=&quot;style.css&quot;&gt;
			<li>&lt;link rel=&quot;stylesheet&quot; href=&quot;style.css&quot; type=&quot;text/plain&quot;&gt;
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>答え<span> D</span></dt>
    <dd>HTML5では、link要素には必ずrel属性を指定する必要があります。Cはrel属性の値として、キーワードではなくMIMEタイプを指定していますので間違いです。Eのtype属性に指定されているMIMEタイプ「text/plain」はCSS向けのものではありませんので、「style.css」は読み込まれません。Dのようにtype属性が省略されると、rel属性の値が「stylesheet」の場合のデフォルト値「text/css」が適用されます。<br>
	よって正解はDとなります。</dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_112">出題範囲の詳細</a></p>
  <div class="present">
    <p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル１認定者　大藤 幹 氏</p>
  </div>
</div>
  </div>
  <div class="question">
    <dl>
      <dt>例題1.3「1.1.3 Web関連技術の概要」</dt>
      <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_113">1.1.3 Web関連技術の概要</a>」からの出題です。<br>
      XHTML書式の特徴についての説明で、正しいものを2つ選びなさい。</dd>
      <dd>
        <ul class="option">
			<li>html要素の開始タグにXHTML用の名前空間を指定する。
			<li>html要素の代わりにxhtml要素を使ってもよい。
			<li>属性の値は「&quot;」や「&apos;」で囲む必要はない。
			<li>要素名や属性名は全て大文字で記述しなければならない。
			<li>空要素には終了タグを付加するか、開始タグの閉じかっこを「/&gt;」としなければならない。
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
<div class="answer">
  <dl>
    <dt>答え<span> A、E </span></dt>
    <dd>HTML5はXHTML書式を利用できます。<br>
	その際、html要素にはデフォルト名前空間としてxmlns属性で「<a href="http://www.w3.org/1999/xhtml" target="_blank" class="linkwin">http://www.w3.org/1999/xhtml</a>」を指定する必要があります。<br>
	要素名や属性名は全て小文字で記述する必要があります。<br>
	属性の値は「&quot;」や「&apos;」で囲む必要があります。<br>
	xhtml要素という要素はいずれのXHTML仕様にも存在しません（2014年5月現在）。</dd>
  </dl>
  <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_113">出題範囲の詳細</a></p>
  <div class="present">
    <p>例題解説の提供：<a href="/measures/learning.html">HTML5アカデミック認定校</a>　<a href="/measures/learning_03.html">株式会社クリーク・アンド・リバー社</a><br>HTML5レベル１認定者　林 拓也 氏</p>
  </div>
</div>
  </div>
  <div class="question">
    <dl>
      <dt>例題1.2「1.1.1 HTTP, HTTPSプロトコル」</dt>
      <dd class="lead">レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_11">1.1.1 HTTP， HTTPSプロトコル</a>」からの出題です。<br />
      HTTPプロトコルにおけるExpiresヘッダフィールドに関する記述として間違っているものを１つ選びなさい。</dd>
      <dd>
        <ul class="option">
			<li>キャッシュを利用する事でウェブページに関するロードの高速化が期待できる。
			<li>HTTPリクエストに付加され送信される。
			<li>キャッシュの有効期間期限を指定できる。
			<li>スクリプトやスタイルシートにも利用できる。
			<li>HTTP/1.1において、Cache-Controlフィールドのmax-age指示子がある場合は、Expiresフィールドは上書きされる。
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
  <div class="answer">
    <dl>
      <dt> 答え <span>B</span> </dt>
      <dd>Expiresヘッダフィールドは、Webコンテンツ提供者がそのコンテンツが最新である期間を示すために指定するものです。<br>
	よって、レスポンスに記述されるものであり、リクエストに付加されるというBの記述は間違いです。</dd>
	<dd>A,C,D,EはExpiresヘッダフィールドの説明として適切です。</dd>
    </dl>
    <p class="detail"><a href="/outline/objectives_lv1_v2.html#lv1_11">出題範囲の詳細</a></p>
  <div class="present">
    <p>例題解説の提供：<a href="http://media-sketch.com/" target="_blank" >メディアスケッチ株式会社</a><a href="http://www.lpi.or.jp/bp/" target="_blank">（ビジネスパートナー）</a><br>
      代表取締役　兼　株式会社コーデセブン　取締役CTO　伊本 貴士 氏<br>
      ITコンサルタント業を中心に、Webサービスの開発や、オープンソースシステムの構築・保守なども行っている。</p>
  </div>
  </div>
  </div>
  <div class="question">
    <dl>
      <dt>例題1.1「1.1.1 HTTP, HTTPSプロトコル」</dt>
      <dd class="lead">
      	レベル1の出題範囲「<a href="/outline/objectives_lv1_v2.html#lv1_11">1.1.1 HTTP, HTTPSプロトコル</a>」からの例題を解説します。<br>
      	HTTP/1.1に関する記述のうち、間違っているものを選びなさい。
      </dd>
      <dd>
        <ul class="option">
          <li>トランスポート・プロトコルとして、通常はTCPを使用する。
          <li>デフォルトのポート番号は80番である。
          <li>定義されているメソッドは、GETとPOSTの2種類である。
          <li>リクエストには、リクエストライン・リクエストヘッダフィールド・ボディメッセージなどが含まれる。
          <li>レスポンスにおけるステータスコードの番号が5から始まる場合は、サーバ側でなにか問題が発生している可能性が高い。
        </ul>
      </dd>
    </dl>
    <p class="notice">※この例題は実際のHTML5プロフェッショナル認定試験とは異なります。</p>
    <p class="answer_check"><span> 答えはこちら</span></p>
  <div class="answer">
    <dl>
      <dt> 答え <span>C</span> </dt>
      <dd> Aは正しい記述です。
        HTTPプロトコルは、アプリケーション層のプロトコルとして定義されており、OSI参照モデルにおける第7層に位置するプロトコルです。HTTPは第4層のトランスポート・プロトコルに、通常TCPを利用します。よって、ファイアウォールにおいてTCPに関する設定をしている場合は、HTTPのプロトコルにも影響する場合があります。
        Bは正しい記述です。デフォルトポートは80番で、ブラウザで特にアクセスするポート番号を指定しない場合は、自動的に80番ポートに接続する事になります。
        Cは、間違いです。HTTP/1.1では、GET、POST以外にも、PUT、DELETE、HEADなど合計8個のメソッドが定義されています。ほとんどの場合、GETかPOSTを使いますが、最近ではRESTアーキテクチャのような、相互データ交換の目的でPUTやDELETEを使うこともあります。Dは正しい記述です。リクエストには様々なヘッダを記述することができ、それによってクライアントに関する情報（利用しているブラウザの種類など）をサーバに送信することができます。Eは正しい記述です。RFC2616（Hypertext Transfer Protocol -- HTTP/1.1）の定義では、ステータスコードが5xxの場合、つまり5で始まる3桁の数字であればサーバがエラー状態にあるか、処理する能力がない場合に返すと定義されています。 </dd>
    </dl>