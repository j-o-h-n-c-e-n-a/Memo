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
    =&lt;link rel="stylesheet" href="/default.css" type="text/css"&gt;
    ~&lt;link rel="alternate" href="/en/index.html" hreflang="English"&gt;
    ~&lt;link rel="alternate" media="smartphone" href="/m/index.html"&gt;
    =&lt;link rel="canonical" href="https://example.com/"&gt;
}

::問題１．１８::下記のように分類される画像をWebで使用する際にそれぞれフォーマットとして最も適した組み合わせは次のうちどれか。
A<br>
・写真が多く、フルカラー（1670万色）で表示したい<br>
・グラデーションのデザイン画がある<br>
・背景を透過したい<br>
B<br>
・企業ロゴなどのイラスト、アイコンが多い<br>
・アイコンにアニメーションを入れたい
{
    ~BMP と PNG
    =PNG と GIF
    ~JPEG と GIF
    ~JPEG と PNG
}

::問題１．１７::ウェブサイトのコンテンツを、一元的に管理する仕組みの名称として最もふさわしいものを選択してください。{
    ~Blog
    =CMS
    ~リポジトリ
    ~データウェアハウス
    ~フレームワーク
}

::問題１．１６::titleタグについての説明で、間違っているものを選択してください。{
    ~headタグ内に記述する必要がある
    ~SEO対策として、title要素は重要である
    =HTML4.01,HTML5ともにtitleは必須タグである
    ~ titleには文書の内容を表す文章を記述する
}

::問題１．１５::HTTPに規定されている認証方式に関する説明として、正しいものを2つ選択してください。{
    ~BASIC認証では、ID,パスワードをウェブブラウザ標準の暗号化方式で送信する
    =Digest認証では、ユーザ名とパスワードを、MD5でダイジェスト化して送信する
    ~Digest認証では、ユーザ名とパスワードを、暗号化せずに一部のみ送信する
    =BASIC認証では、ID,パスワードを暗号化せずに送信する
    ~Captcha認証では、機械には判別しにくい画像を使用して認証を行なう
}

::問題１．１４::HTML5の文書型宣言として間違っているものを2つ選びなさい。{
    =&lt;!doctype&gt;
    ~&lt;!doctype html&gt;
    =&lt; !DOCTYPE HTML&gt;
    ~&lt;!DOCTYPE HTML &gt;
    ~&lt;!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01//EN"&gt;
}

::問題１．１３::HTML5のtitle要素に関する記述のうち、間違っているものをすべて選びなさい。{
    =1つのHTML文書に必ず1つ必要。
    ~head要素内に配置する。
    ~複数は配置できない。
    ~要素内容にはテキストしか入れられない。
    =条件によっては終了タグを省略できる。
}

::問題１．１２::文字（実体）参照として無効な記述を選択してください。{
    ~&amp;amp;
    ~&amp;#39;
    ~&amp;#x266A;
    =&amp;0x1A;
}

::問題１．１１::HTML5のコンテンツ・モデル（Content models）において、セクショニング・コンテンツ（Sectioning content）である要素の組み合わせで適切なものはどれか。正しいものを1つ選びなさい。{
    ~h1 h2 h3 h4 h5 h6
    ~footer header main section
    ~blockquote body fieldset figure td
    =article aside nav section
}

::問題１．１０::Data URIについての解説で誤っているのを選択してください。{
    ~主にWebサイト表示の高速化のための技術である
    =画像ファイルなど、HTMLファイルの外にあるファイルの場所を指すURIである
    ~画像データのエンコードはBase64形式で行なわれる
    ~ブラウザによって対応状況に差がある
    ~HTML、CSSで使用できる
}

::問題１．９::HTML5で、文字エンコーディングを設定するために有効な書式を2つ選びなさい。{
    ~&lt;html lang=&quot;ja&quot;&gt;
    ~&lt;html charset=&quot;UTF-8&quot;&gt;
    =&lt;meta charset=&quot;UTF-8&quot;&gt;
    =&lt;meta http-equiv=&quot;Content-Type&quot; content=&quot;text/html; charset=UTF-8&quot;&gt;
    ~&lt;meta encoding=&quot;UTF-8&quot;&gt;
}

::問題１．８::SSL/TLSの規格として古い順に並べたものを選びなさい。{
    ~SSL 1.0,TLS 1.0,TLS 1.1,TLS 1.2,SSL 2.0,SSL 3.0
    ~TLS 1.0,TLS 1.1,TLS 1.2,SSL 1.0,SSL 2.0,SSL 3.0
    =SSL 1.0,SSL 2.0,SSL 3.0,TLS 1.0,TLS 1.1,TLS 1.2
    ~TLS 1.0,SSL 1.0,TLS 1.1,SSL 2.0,SSL 3.0,TLS 1.2
}

::問題１．７::HTTPSを使用して、Webサーバの正当性を確認するために必要なものを2つ選びなさい。{
    =認証局
    ~クライアント証明書
    ~承認局
    =サーバ証明書
    ~署名局
}

::問題１．６::Base64についての説明で誤っているものを一つ選択しなさい。{
    ~バイナリデータを印字可能文字に置き換える仕組みである
    =データ量は変換前と変換後で変わらない
    ~英数字と記号を使用する
    ~端数に当たる部分には'='を使用する
    ~変換後は1行64文字で改行される
}

::問題１．５::HTTPSに関する説明で、正しいものを2つ選びなさい。{
    ~HTTP通信の速度向上を目的に使用される。
    ~HTTPS通信ではHTTP通信は行われない。
    =HTTPSでは、データを暗号化して送受信する。
    =HTTPS通信には、TLS（またはSSL）プロトコルも使われる。
    ~HTTPSはIETFにより標準化されている。
}

::問題１．４::HTML5文書において、外部スタイルシート「style.css」を読み込ませるための記述として正しいものを１つ選びなさい。{
    ~&lt;link href=&quot;style.css&quot;&gt;
    ~&lt;link href=&quot;style.css&quot; type=&quot;text/css&quot;&gt;
    ~&lt;link rel=&quot;text/css&quot; href=&quot;style.css&quot;&gt;
    =~&lt;link rel=&quot;stylesheet&quot; href=&quot;style.css&quot;&gt;
    ~&lt;link rel=&quot;stylesheet&quot; href=&quot;style.css&quot; type=&quot;text/plain&quot;&gt;
}

::問題１．３::XHTML書式の特徴についての説明で、正しいものを2つ選びなさい。{
    =html要素の開始タグにXHTML用の名前空間を指定する。
    ~html要素の代わりにxhtml要素を使ってもよい。
    ~属性の値は「&quot;」や「&apos;」で囲む必要はない。
    ~要素名や属性名は全て大文字で記述しなければならない。
    =空要素には終了タグを付加するか、開始タグの閉じかっこを「/&gt;」としなければならない。
}

::問題１．２::HTTPプロトコルにおけるExpiresヘッダフィールドに関する記述として間違っているものを１つ選びなさい。{
    ~キャッシュを利用する事でウェブページに関するロードの高速化が期待できる。
    =HTTPリクエストに付加され送信される。
    ~キャッシュの有効期間期限を指定できる。
    ~スクリプトやスタイルシートにも利用できる。
    ~HTTP/1.1において、Cache-Controlフィールドのmax-age指示子がある場合は、Expiresフィールドは上書きされる。
}

::問題１．１::HTTP/1.1に関する記述のうち、間違っているものを選びなさい。{
    ~トランスポート・プロトコルとして、通常はTCPを使用する。
    ~デフォルトのポート番号は80番である。
    =定義されているメソッドは、GETとPOSTの2種類である。
    ~リクエストには、リクエストライン・リクエストヘッダフィールド・ボディメッセージなどが含まれる。
    ~レスポンスにおけるステータスコードの番号が5から始まる場合は、サーバ側でなにか問題が発生している可能性が高い。
}