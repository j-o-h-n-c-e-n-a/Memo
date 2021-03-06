## 要素と属性の意味（セマンティクス）
  HTML要素や属性のセマンティクスを理解し、コンテンツの意味を解釈しながら適切なHTML要素や属性を使ってHTMLコーディングができる。

### 主要な知識範囲
#### HTML5.1仕様で規定されたHTML要素と属性の意味
【追加】
* picture要素とsrcset属性の追加
	+ picture要素にsource要素を入れることで、画像サイズや解像度での画像の切替が可能に
* details要素とsummary要素の追加
	+ HTMLのみでアコーディオンのような動きが可能に（IE/Edgeは未対応）
【削除】
* ネストされたセクション要素の見出しに全てh1を置くこと
* tfoot要素をtbody要素の前に置くこと【変更】
* セクション要素の中のheader/footer要素は入れ子にできる
* figcaption要素はfigure要素のどこに書いても良い
* img要素のalt属性は削除してはいけない（たとえtitle属性がついていたり、友達にe-mailを書くような場合であっても）
#### HTML5.2仕様で規定されたHTML要素と属性の意味
【追加】
* dialog要素の追加
* link要素のrel属性値に“canonical”、“noreferrer”、“apple-touch-icon” の値が追加
* WAI-ARIA1.1に準拠
【削除】
* keygen、menu、menuitem要素が廃止
【変更】
* dl要素の直下にdiv要素を記述できる
* body要素内にscoped属性を指定することで、style要素を記述できる（ただしパフォーマンス面の問題から従来どおりhead要素内に記述することを推奨）
* 複数のmain要素を記述できる（ただし最初にユーザに見せるのは1つだけで、他はhidden属性で隠す）
* fieldset要素内のlegend要素の中に見出し要素を記述できる
#### セクションの概念
	セクショニング・ルートとなる要素は、ドキュメント全体の階層構造（アウトライン）とは別の、独自の階層構造（アウトライン）を持つ。
* セクションがなくても見出しがあれば、暗黙的にセクションが作られる
#### セクショニングルート要素
* body要素
* blockquote要素
* fieldset要素
* figure要素
* td要素

### 重要な技術要素
#### セクション
  セクショニングコンテンツに分類される要素は、[article, aside, nav, section]
  blockquote要素はセクショニングルートにあるため、独自のアウトラインを持ち、その内部のセクションは祖先のアウトラインに影響を与えません。
#### セクションの種類
* section要素
	+ 一般的なセクション
	+ 以下の3つのセクション以外の時に使う
* article要素
	+ 新聞・雑誌・ブログなどの記事を始めとする、「それだけで全部の/それだけで完結している」セクション
	+ 単独で配布・再利用が可能なコンテンツ
* aside要素
	+ aside要素はその内容が前後の内容とほぼ関係なく、それらと分離されたものであると考えられるセクション 例：広告・プルクォート、補足記事など
* nav要素
	+ そのページにおけるナビゲーションリンクを含むセクション
##### heder要素
* セクションまたはセクショニングルートのヘッダー
* 通常見出しを含む(必須ではない)
* 内容例：見出し、ナビゲーション、ロゴ、検索フォーム、目次
* header, footer, main要素は含むことはできない
##### footer要素
* セクションまたはセクショニングルートのフッター
* 内容例：著作権情報、問い合わせ先(address要素)、関連文書へのリンク(前・次ページなど)、執筆者
* セクションの前と後ろどちらに配置してもいい
##### main要素
* ページ全体におけるメインコンテンツ
* 内容例:そのページ特有のコンテンツのみを入れる
* サイト内の複数ページで共通しているナビゲーションやロゴ、検索フォーム、著作権情報などのコンテンツは含めない
* 以下の要素の中には含められない 
	+ article要素
	+ aside要素
	+ nav要素
	+ header要素
	+ footer要素
#### 書式方向
#### ルビ
  ruby要素をサポートしないブラウザでふりがなの代替テキストを表示するには、rp要素を使用する。
##### ruby要素
* rubyとはルビ(ふりがな)のこと
* ルビを振りたい漢字を〜で囲む
##### rt要素
* ruby text の略
* ルビとして小さい文字で表示させるテキスト（ふりがな）
##### rb要素
* bは base text
* その内容がルビを振る対象となるテキスト(ルビを振る漢字部分)
##### rp要素
* p は parentheses(パーレーン=丸括弧)
* ルビに未対応のブラウザなどでルビが普通サイズのテキスト担ってしまう時にそれらを()で囲って表示
##### rtc要素
* ruby text container (rt要素の入れ物)
* rt要素をグループ化する時に使う
##### ルール
* 以下のものは終了タグを省略できる 
	+ rt要素
	+ rb要素
	+ rp要素
	+ rtc要素
* 漢字のテキスト or rb 要素は1つ以上いれる
* rt要素またはrtc要素を1つ以上いれる
#### 挿入と削除のセマンティクス
#### グルーピングのセマンティクス
#### テキストレベルのセマンティクス
  ディスクロージャーウィジェットを作成する為にはdetails要素を使用する。
##### mark要素
* オリジナルの文章はそうなっていないが、参照してもらいやすいように目立たせた部分 
##### data要素
* 人が読み取り可能な要素内容と共に、機械が読み取り可能なデータも提供
* 機械が読み取り可能なデータは必須属性であるvalue属性の値として指定 
##### time要素
* data要素ん中でも日時での使用に特化させた要素
* valueではなくdatetime属性を使用する
* data要素のvalueとは異なり、datetime属性は必須ではない(あらかじめ機械読み取り可能な形式にする必要がある)
##### wbr要素
* 英単語やURLの途中でも行を折り返すことができる要素
##### dbi要素
* 特定の範囲のテキストを意図的に分離独立させる
* unicodeの双方向アルゴリズムの影響を受けないようにする
* ユーザーが自由に入力できるテキストをページ内のコンテンツの一部とするような部分で使用される
##### 装飾要素への意味づけ
	以前は単純にテキストを装飾するだけの要素だったが、HTML5ではそれぞれに意味が付けられた
* bタグ
	+ 文書内のキーワードや製品名など、実用的な意味で目立たせた方が良いと思われるもの。
* iタグ
	+ 声や心の中で思ったことなど、普通のテキストとは違う性質のものに切り替わっているもの。
* strongタグ
	+ 強い重要性・緊急性。
* smallタグ
	+ 免責・警告・著作権など、注釈のような付随的な情報をマークアップするもの。
* hrタグ
	+ 段落レベルでのテーマの区切り・変わり目を示す。
#### リンクの関連性のセマンティクス
#### 言語のセマンティクス
#### 表のセマンティクス


## メディア要素
  ビデオやオーディオをHTMLコンテンツとして適切に活用できる。

### 主要な知識範囲
  video要素とaudio要素の違いは動画や字幕を再生する領域があるかないかのみ
  別形式の代替データを指定するにはSource要素のみを使用する
#### ビデオ再生のためのHTMLマークアップ知識
#### オーディオ再生のためのHTMLマークアップ知識
#### ビデオファイルとオーディオファイルの知識
#### 字幕表示のためのHTMLマークアップ知識

### 重要な技術要素
#### ビデオやオーディオに関連するHTML要素と属性
##### video要素
* 動画を再生
* video要素にしかない属性 
	+ poster: 動画が再生可能となるまでの間に表示させる画像のアドレス
	+ width: 幅
	+ height: 高さ
##### audio要素
* 音声を再生
##### source要素
* 代替データとして異なる形式のデータも合わせて指定しておきたい場合
* これを使用するときはvideo, audio要素のsrc属性には指定できない
* video, audio要素の先頭に配置する必要がある
##### track要素
* videoやaudio要素での再生時に同期させる外部のテキストトラック 
* 空要素
* source要素よりも後、その他の要素より前に配置する必要がある
* kind属性: テキストトラックの種類 
+ subtitles: 音は聞こえるが理解できない場合(洋画の日本語字幕など) 
	- 映像に重ねて表示
+ captions: 音が聞こえない場合 
	- 映像に重ねて表示
+ descriptions: 映像が見えない場合 
	- 合成音声で読み上げる
+ chapters: 映画のチャプタータイトル 
	- 移動可能なチャプターの一覧としてユーザーに提示
+ metadatas: スクリプトから利用することを想定したメタデータ 
	- 表示されない
##### embed要素
* プラグインを使用する外部のコンテンツを組み込む際に使用される要素
* 空要素
#### ビデオコーデック
#### オーディオコーデック
#### コンテナ
#### 字幕


## インタラクティブ要素
  ユーザーの操作を伴うHTML要素を効果的に活用できる。

### 主要な知識範囲
#### ハイパーリンク
#### フォーム
  time要素内かdatetime属性に日付型を指定する必要がある。
##### meter要素
* メーター
* 特定の範囲内での位置を示す
##### progress要素
* タスク(コンピュータが行っている作業)の進み具合を表す
##### datalist要素
* input要素にサジェスト機能を追加する(入力候補の選択肢を与える)要素
* option要素が選択肢
* 関連付け 
	+ datalistのid属性の値をinput属性のlist属性に指定
* やり方は2つ 
1. datalistの中にそのままoption要素を入れて選択肢にする
2. (datalist未対応ブラウザ用に)select要素をいれてその中のoptionを選択肢に使用 
* →これで対応ブラウザでは表示されずにoption要素だけが入力候補として使用される
##### output要素
* 計算結果やユーザーの操作による結果を示すための要素
* 属性 
	+ for: 計算の元となったフォームの部品
	+ name: フォームの部品
	+ form: フォームの部品を特定のform要素(id属性の値で指定)と関連づける
##### validation
#### フレーム
#### コンテキストメニュー
#### ディスクロージャーウィジット
#### コマンドメニュー

### 重要な技術要素
#### ハイパーリンク関連要素および属性
	ブロック要素を含めることができるようになった
* download属性
* media属性
#### フォーム関連要素および属性
#### フレーム関連要素および属性
#### コンテキストメニュー関連要素および属性
#### ディスクロージャーウィジット関連要素および属性
#### コマンドメニュー関連要素および属性

### その他の要素
#### 新属性
* contenteditable
* role
	+ 例えば、テーブルはレイアウト目的で使用するべきではなくなったが、それでもレイアウト目的に使用する場合は、role=”presentation” を指定する必要がある。
* aria-(状態)
* draggable
#### dl要素
	以前は定義リストを意味していたが、HTML5では説明リストとなった
	以前のような定義リストは、<dfn>となる
#### figure要素
* メインコンテンツの本文から参照される図版
* それ自身がまとまったひとつの完結した内容となっているFlow content(一般コンテンツ)
* 例：図表、写真、イラスト、ソースコードの一部
#### figcaption要素
* 図版のキャプションや説明文部分
* figure要素の一番前 or 一番後ろにしか配置できない
#### template要素
* その範囲がスクリプトによって生成(複製・挿入)される部分であることを示す
#### canvas要素
* スクリプトによって描画するビットマップの動的なグラフィックとなる要素
* デフォルトで width:300 height:150


$CATEGORY: 1.3 要素に関して

::例題3.27::iframe要素のsrcdoc属性に指定するHTML文書に関する説明のうち、間違っているものをすべて選びなさい。{
  =DOCTYPE宣言は省略できない
  ~html要素のタグは省略可能
  ~head要素のタグは省略可能
  ~title要素はなくてもよい
  ~body要素のタグは省略可能
}

::例題3.26::video要素に指定可能な次の属性のうち、論理属性に該当するものをすべて選びなさい。{
  ~%-25%preload
  ~%25%autoplay
  ~%25%loop
  ~%25%muted
  ~%25%controls
}

::例題3.25::英語の文章の中にフランス語の慣用句が含まれている場合に、そのフランス語の部分をマークアップするのに最もふさわしい要素は次のうちのどれか。{
  ~em要素
  ~q要素
  =i要素
  ~b要素
  ~u要素
}

::例題3.24::下記はinput要素を使用して画像を取り込む際にスマートフォンやタブレットのカメラを起動する例である。下線部に入る値として有効なものをすべて選びなさい。{
  ~%-50%yes
  ~%-50%camera
  ~%50%environment
  ~%-50%system
  ~%50%user
}

::例題3.23::input要素のpattern属性に指定する値の内、文字列 A を受け付けないのは次のうちどれか。{
  ~(A|B|C)
  ~[ABC]
  ~[A-C]
  ~^[ABC]
  =[^ABC]
}

::例題3.22::a要素でハイパーリンクを作成する際、target属性によって表示先を指定できるが、target属性の指定を省略した場合と同等の、つまりデフォルトの target は次のうちどれか。{
  ~_my
  ~_me
  ~_mine
  =_self
  ~_own
}

::例題3.21::textarea要素のサイズはデフォルトで２０文字ｘ２行で、rows, cols により変更が可能である。
 更にデフォルトではユーザーがブラウザ上でリサイズ可能であるが、リサイズの可否は CSS で指定する。
resizeプロパティの有効な値として間違っているのは次のうちどれか。{
  ~none
  ~horizontal
  ~vertical
  =either
  ~both
}

::例題3.20::ページのメイン・コンテンツを示すmain要素の説明として正しいのは次のうちどれか。{
  ~%-50%main要素はアウトラインを構成する。
  ~%-50%main要素の子要素subはサブ・コンテンツを表す。
  ~%50%main要素はrole属性を併用することが推奨されている。
  ~%-50%main要素はbody要素と同じ意味・役割である。
  ~%50%main要素はWHATWGとW3Cで仕様に違いがある。
} #### ページは通常 header, footer, nav 等のページが遷移してもいつも表示され るアイテムとそのページでだけ表示されるメインのコンテンツで構成されますが、main要素はその領域を示すためにbody要素内で使用されます。<br>
また、main要素は WAI-ARIA (Web Accessibility Initiative - Accessible Rich Internet Applications)というアクセシビリティを目的とした仕様と関わりがあります。<br><br>
アクセシビリティは、バリアフリーに似た意味で、たとえばスクリーンリーダー（画面読み上げソフト）などの人ではなく機械が文章のrole(役割)を識別して視覚障害者にもその旨が伝わるように利用されます。<br><br>
さて、例題の選択肢ですが、main要素はh1要素などと違いアウトラインには寄与しないので、Aは不正解です。<br>
sub要素はH&lt;sub&gt;2&lt;/sub&gt;Oなど、下付きの文字を表示する要素なので、Bは不正解です。<br>
ARIA のrole "main" を併記することが推奨されており、Cは正解です。<br>
main要素はbody要素とは異なる意味があるので、Dは不正解です。<br>
WHATWGではmain要素はフロー・コンテンツが使用できる箇所ではどこでも使用できるとしていますが、W3Cでは article, asideなどの子孫要素にはなれないとあるので、Eは正解です。<br><br>
ARIAを取り入れ、バリアフリーなWebアプリケーションを制作しましょう。

::例題3.19::fieldset 要素に説明を付加する子要素は次のうちどれか。{
  ~caption
  ~summary
  ~series
  =legend
  ~folklore
} #### <p>HTML5 には、対で使用してはじめて機能する要素があります。<br>
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

::例題3.18::下記の動画配信ページの説明として正しいのは次のうちどれか。
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
{
  ~ページを開くと動画が自動的に再生される。
  ~動画再生時にデフォルトで日本語の字幕が表示される。
  ~動画再生時に日本語訳と英語での描写が同時に表示される。
  =動画再生時に音声は再生できない。
  ~ページを開くと動画は自動的にロードされる。
} #### <p>video要素に track要素を指定することで、動画に字幕を表示することができます。<br>
video要素に controls属性を指定すると、再生、休止、ミュート、音量調節、シーク（進捗バーを掴んで移動）が可能な操作画面が利用できます。追加の属性指定により、自動再生(autoplay)、リピート(loop)、ポスター表示(poster)が可能です。<br>
video要素の制御に対してJavaScriptが必要になるのは、スロー再生などの再生速度の変更ぐらいかもしれません。</p> 
<p>video要素にtrack要素を追加することで字幕の利用が可能になります。<br>
字幕の詳細は WebVTT(The Web Video Text Tracks Format)ファイルまたは TTML(Timed Text Markup Language) ファイルで提供でき、表示の開始/終了時間は HH:MM:SS.mmm のミリ秒単位で指定し、オプションにより表示位置なども指定できます。</p>
<p>例題の選択肢の解釈は次のとおりです。</p>
<p>A: video 要素に autoplay属性の指定がないので再生は自動的に開始せず、poster属性で指定した画像が表示されるので、間違いです。</p>
<p>B: デフォルトでは字幕は「オフ」なので、間違いです。字幕を表示させるには操作画面でlabelで指定された字幕を選択します。また予め日本語を選択しておくには、下記のようにdefault を追加します。<br>
	&lt;track kind="captions"  src="ja.vtt" label="日本語" default&gt;</p>
<p>C: 字幕の表示は日本語か英語のどちらか一方になるので、間違いです。<br>
kind属性のsubtitlesは翻訳の字幕などに、captionsは状況説明などに使用します。デフォルトは subtitlesです。</p>
<p>D: video要素でmuted属性が指定されているのでミュート（消音）状態でページは開きますが、操作画面でミュート解除や音量制御もできるので、間違いです。</p>
<p>E: video要素に preload属性が指定可能です。大きな動画では負荷軽減のために none(preloadしない）を指定可能ですが、デフォルトはautoで自動的にロードを行うので、正解です。</p>

::例題3.17::下記の動画配信ページの説明として正しいのは次のうちどれか。
HTML5アプリを納品したが、スマホユーザーから「登録画面が使いにくい。」との苦情が多かったらしく、改善を要求された。<br>
以下はそのコードの抜粋であるが、スマホへの改善策として最も適しているのは次のうちどれか。
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
{
  ~autocomplete=“on”で入力を簡素化する。
  ~kbd属性でキーボード配列(QWERTYまたは10キーなど)を指定する。
  ~picker属性でカレンダーピッカーやスライダーを指定する。
  ~pattern属性で受け付けない文字を入力できないよう指定する。
  =type属性で入力値の分類を指定する。
} #### <p>スマホの文字入力は、画面の一部に表示されるソフトウェアキーボードを使用します。小さな画面スペースに指で押せるサイズを確保するため、キーの数が制限されます。そのため入力する文字列によってはキーボードの切り替えが頻発する場合があります。<br>
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

::例題3.16::HTML5で、誤植を修正する際の記述として適切なのは次のうちどれか。{
  ~アーカイブを&lt;ng&gt;回答&lt;/ng&gt;&lt;ok&gt;解凍&lt;/ok&gt;できない。
  ~私は&lt;err&gt;隠し事&lt;/err&gt;&lt;corr&gt;書く仕事&lt;/corr&gt;が得意です。
  =漢字の&lt;del&gt;返還&lt;/del&gt;&lt;ins&gt;変換&lt;/ins&gt;ミスに気をつけよう。
  ~田舎町に有名歌手が&lt;typo&gt;音ずれ&lt;/typo&gt;&lt;fix&gt;訪れ&lt;/fix&gt;た。
} #### HTML5では、del要素で削除箇所をins要素で追記箇所がわかるように記述することができます。<br>
多くのブラウザでは、削除箇所は取り消し線付きで表示し、追記箇所は下線付きで表示されます。<br>
したがって、正解はCです。<br><br>
del要素、ins要素ともにdatetime属性で修正日時を、cite属性で引用元のURLを記述することができます。<br><br>
なお、A、B、Cの要素はありません。

::例題3.15::object要素は、画像、音声、HTML文書など様々な外部リソースを文書内に取り込む際に使用しますが、次のうち指定方法として適切なものを1つ選べ。{
  ~&lt;object href="sample.svg" …&gt;
  =&lt;object data="sample.mpg" …&gt;
  ~&lt;object embed="sample.swf"  …&gt;
  ~&lt;object src="sample.gif" …&gt;
} #### object要素は、data属性でファイルを指定し、type属性でMIMEタイプを指定することで文書内に外部リソースを埋め込んで表示することができます。したがって正解は B です。<br><br>
A.のhref属性は、a要素、area要素、link要素でのリンク先の指定や、base要素での基準となるURLを指定することに使用します。<br>
C.のembedは要素で、src属性を指定して画像などの埋め込みに使用しますが、object要素の属性ではありません。<br>
D.のsrc属性は、embed要素やimg要素で参照先を指定するときなどに使用しますが、object要素の属性としては使用できません。</dd>

::例題3.14::下記のように、画面に「▶︎詳細」と表示し、「詳細」をクリックすると「詳細な説明」を表示したり、非表示にしたりするHTML5の記述は次のうちどれか。余分な文字を表示せず、正しく動作するものをすべて選びなさい。
<pre>
  ▶︎詳細
　⇅　
  ▼詳細
  詳細な説明
</pre>
{
  ~ 
   &lt;summary&gt;詳細<br> 
   &lt;details&gt;詳細な説明&lt;/details&gt;<br>
   &lt;/summary&gt;
   = 
   &lt;details&gt;<br>
   詳細な説明<br>
   &lt;/details&gt;
   ~
   &lt;details&gt;詳細<br>
   &lt;summary&gt;概要&lt;/summary&gt;<br>
   詳細な説明<br>
   &lt;/details&gt;
   = 
   &lt;details&gt;<br>
   詳細な説明<br>
   &lt;summary&gt;詳細&lt;/summary&gt;<br>
   &lt;/details&gt;
} #### details要素は、&lt;details&gt;タグで囲われた部分を非表示にし、必要に応じて利用者がクリックすることで参照できるようにできます。summary要素は、details要素の子要素で、省略時に表示される「詳細」（ブラウザにより異なる）を別の文字列に置き換える。

::例題3.13::次の要素のうち、セクションに分類される要素をすべて選びなさい。
{
  ~%-50%header
  ~%50%nav
  ~%-50%main
  ~%50%aside
  ~%-50%footer
} #### HTML5の要素のうち、セクションに分類される要素（Sectioning content）は、「section」「article」「aside」「nav」の4種類のみです。<br>HTML5プロフェッショナル認定試験を受験するのであれば、この4種類の要素については、しっかりと確実に覚えておく必要があります。headerとfooterは、それらを含むもっとも近いセクション（またはセクショニング・ルート）のヘッダーとフッターとなります。<br>mainは（セクションではなく）文書全体におけるメインコンテンツの範囲を示す要素です。header・footer・mainは、要素のカテゴリーとしては Flow content に含まれます。

::例題3.12::videoタグを使って動画圧縮規格がh.264の映像を表示する場合、sourceタグに設定する適切なtype属性を選びなさい。{
  =video/mp4
  ~video/ogg
  ~video/h264
  ~video/webm
  ~video/264
} #### A：コンテナフォーマットがmp4の場合に設定します。mp4コンテナフォーマットには動画圧縮規格h.264が使われていますので、Aが正解です。<br><br>
B：コンテナフォーマットがogg/ogvの場合に設定します。ogg/ogvコンテナフォーマットにはTheoraという動画圧縮規格が使われています。<br>
C：sourceタグのtype属性に設定できるものに、「video/h264」は存在しません。<br>
D：コンテナフォーマットがwebmの場合に設定します。webmはVP8という動画圧縮規格が使われています。<br>
E：sourceタグのtype属性に設定できるものに、「video/264」は存在しません。

::例題3.11::role属性の機能として正しいものを1つ選びなさい。{
  ~ユーザーが独自の属性を追加する。
  ~要素を回転させる角度を指定する。
  =既存の要素の役割・意味を上書きして変更する。
  ~ゲームキャラクターの特性を示す。
  ~ユーザーインターフェイスの状態や特性を示す。
} #### role属性のroleは「役割」という意味で、既存の要素が持っている「役割・意味」とは異なる「役割・意味」を上書きして与えることのできる属性です。たとえば、既存のHTMLの要素にはユーザーインターフェイスとしての「タブ」や「ツリーウィジェット」をあらわす要素はありませんが、role属性を使用することでli要素やdiv要素などをタブ要素やツリーウィジェット要素に変更することができます（それによってスクリーンリーダーなどの支援技術がタブやツリーウィジェットを正しく認識できるようになります）。role属性の詳細な仕様は、HTML5とは別のWAI-ARIA 1.0という仕様書で定義されています。<br><br>
Aはカスタムデータ（data-*属性）属性の説明です。BとDのような属性はHTML5にはありません。Eは、role属性と同じくWAI-ARIA 1.0の仕様書で定義されているaria-*属性の説明です。

::例題3.10::次のうち、mark要素としてマークアップするのにふさわしいものをすべて選びなさい。{
  ~%-50%製品名やキーワード 
  ~%-50%中国語の固有名詞
  ~%50%検索結果の表示における検索語
  ~%-50%スペルが間違っている単語
  ~%50%引用文の中で読者に注目してもらいたい部分
} #### mark要素は、一般的なブラウザでは蛍光ペンでマークしたような表示となります。このことからもわかるように、オリジナルでは通常のテキストである部分を、そのWebページの読者に注目してもらうためにハイライト表示させるのがmark要素の役割です。<br><br> 
Aの製品名やキーワードについては、HTML5ではb要素を使用します。Bの「中国語の固有名詞」とDの「スペルが間違っている単語」については、HTML5ではu要素を使用することになっています。<br><br> 
テキスト関連の要素とその代表的な用途はしっかりと覚えておきましょう。</dd>

::例題3.9::time要素で指定する日時の書式として<u>間違っているもの</u>を1つ選びなさい。{
  ~&lt;time&gt;02:50&lt;/time&gt;
  =&lt;time&gt;2時50分&lt;/time&gt;
  ~&lt;time datetime="02:50"&gt;真夜中&lt;/time&gt;
  ~&lt;time datetime="2015-12-24T02:50"&gt;2時50分&lt;/time&gt;
  ~&lt;time datetime="2015-12-24 02:50:00"&gt;ニ時五十分&lt;/time&gt;
} #### time要素は、datetime属性が指定されている場合は、その値を仕様書で定められている機械読み取り可能な書式にする必要があります。datetime属性が指定されていない場合は、time要素の要素内容のテキストを機械読み取り可能な書式にする必要があります。<br><br> 
Bにはdatetime属性が指定されていないため、要素内容を機械読み取り可能な書式にする必要があります。しかし、「2時50分」というテキストは仕様書で定義されている機械読み取り可能な書式には含まれていません。よって、答えはBです。<br><br> 
C、D、Eについては、要素内容は機械読み取り可能な書式ではありませんが、datetime属性の値が正しい書式で書かれているため問題ありません。

::例題3.8::HTML5において、form要素の外部にあるフォーム関連要素をform要素と関連づける際に使用する属性はどれか。次の選択肢から1つ選びなさい。{
	~for属性
	=form属性
	~rel属性
	~formlink属性
	~formassociate属性
} #### フォーム関連要素にform属性を指定し、その値にform要素のid属性の値を指定することで、フォーム関連要素の配置場所にかかわらず特定のform要素と関連づけることができます。form属性が指定できるのは、input要素、textarea要素、select要素、button要素、output要素、keygen要素、label要素、fieldset要素、object要素です。<br>
ただし、form属性を実際に使用する際は、ブラウザの対応状況に注意する必要があります。

::例題3.7::HTML5で「長万部」という漢字にルビをふる際のマークアップとして文法的に正しくないものをすべて選びなさい。{
  ~&lt;ruby&gt;長万部&lt;rt&gt;おしゃまんべ&lt;/ruby&gt;
  ~&lt;ruby&gt;長万部&lt;rt&gt;おしゃまんべ&lt;/rt&gt;&lt;/ruby&gt;
  ~&lt;ruby&gt;長万部&lt;rp&gt;（&lt;/rp&gt;&lt;rt&gt;おしゃまんべ&lt;/rt&gt;&lt;rp&gt;）&lt;/rp&gt;&lt;/ruby&gt;
  ~&lt;ruby&gt;&lt;rb&gt;長万部&lt;rp&gt;（&lt;rt&gt;おしゃまんべ&lt;rp&gt;）&lt;/ruby&gt;
  =&lt;ruby&gt;&lt;rtc&gt;&lt;rb&gt;長万部&lt;/rb&gt;&lt;rt&gt;おしゃまんべ&lt;/rt&gt;&lt;/rtc&gt;&lt;/ruby&gt;
} #### ruby要素の最初の子要素には、ルビを振る対象となるテキスト（phrasing content）またはrb要素を配置する必要があります。したがって、最初の子要素としてrtc要素を配置しているEは文法的に正しくありません。ルビを振る対象となるテキストは、rb要素のタグを付けても付けなくても問題はありませんが、rb要素のタグを付けることでそこにCSSが指定しやすくなるなどの利点もあります。<br>
ruby要素自体はタグを省略することはできませんが、その内容となるruby関連の各要素は終了タグを省略することが可能です。<br>
ルビ関連の要素は、要素名が何の略なのかをおぼえておくと記憶しやすくなります。たとえばrtは「ruby text」の略で、それがルビのテキスト（振仮名となるテキスト）であることを示しています。rtcは「ruby ext container」の略なので、そこにrt要素を入れるということがわかります。rb要素のbは「base text」を意味し、rp要素のpは「parentheses（パーレン=丸括弧）」を意味しています。<br>
なお、XHTML1.1ではrbc要素が定義されていましたが、HTML5ではrbc要素は定義されていません。

::例題3.6::次の要素のうち、セクションを示す要素ではないものはどれか。1つ選びなさい。{
  ~nav
  =main
  ~aside
  ~article
  ~section
} #### HTML5の要素のうち、セクションを示す要素（カテゴリーが「Sectioning content」に該当する要素）は、nav・aside・article・sectionの4種類のみです。main はセクションとはならず、文書のアウトラインにも影響を与えない要素です。

::例題3.5::動画ファイルの埋め込みに関係するHTML要素を次の選択肢から全て選びなさい。{
  ~%50%source要素
  ~%50%video要素
  ~%-50%movie要素
  ~%-50%control要素
  ~%-50%volume要素
} #### 動画ファイルの埋め込みは、video要素単独で記述する書式と、video要素とsource要素を組み合わせて記述する書式があります。<br>
	source要素を使う場合には、video要素の子として複数の動画ファイルを再生候補として指定できます。その場合、Webブラウザは上から順に利用可能なファイルをチェックします。<br>
	なお、他の選択肢は存在しない架空のものです。

::例題3.4::ページのタイトルおよび本文に対してエンコードの種類を指定するcharset属性の記述位置として最も適切なものを選びなさい。
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
{
  ~(A)の位置に記述する
  =(B)の位置に記述する
  ~(C)の位置に記述する
  ~(D)の位置に記述する
  ~(E)の位置に記述する
} #### meta要素のcharset属性は、本文だけではなくタイトルのエンコードに関する種類を指定できます。<br>
この記述はコードの&lt;head&gt;内に記述する必要があります。<br>
またタイトルに対しても指定する場合は、&lt;title&gt;より前に指定しなければなりません。</dd>
<dd>問題の選択肢では、&lt;head&gt;内にあり&lt;title&gt;より前に位置しているのは（B）のみです。<br>
よって正解はBとなります。

::例題3.3::以下の説明に関する要素名の組み合わせで正しいものを選びなさい。
<p style="margin-bottom:1em;">
(1) コンピュータコードを表すために利用される要素である。<br>
(2) コンピュータコードや数学における変数を示す場合に利用される要素である。<br>
(3) コンピュータからの出力内容を示す場合に利用される要素である。<br>
(4) コンピュータからの入力内容を示す場合に利用される要素である。</p>
{
  ~(1) pre (2) samp (3) var (4) kbd
  ~(1) pre (2) var (3) samp (4) kbd
  ~(1) pre (2) var (3) kbd (4) samp
  =(1) code (2) var (3) samp (4) kbd
  ~(1) code (2) var (3) kbd (4) samp
} ### <p>HTMLには、コンピュータコードを表示するための要素があります。<br>
コンピュータコードとは、XML要素名・ファイル名・プログラムのソースコードなどが含まれます。</p>
<p>プログラムのコードなどを表示する場合はcode要素を使って記述するのが適切です。<br>
多くの主要なブラウザの場合、code要素を使って表示すると等幅フォントで表示されます。</p>
<p>ソースコードを表示する時にcode要素と合わせてpre要素がよく利用されますが、pre要素はフォーマット済みのテキストブロックを示すもの、つまり字下げや改行コードをそのまま表示するための要素であり、コンピュータコーを表すためのものではありません。<br>
よって、A,B,Cは間違いです。</p>
<p>コンピュータコードの変数を示す要素はvar要素、コンピュータからの出力を示す要素はsamp要素、コンピュータからの入力を示す要素はkbd要素なので正解はDです。</p></dd>

::例題3.2::HTML5におけるsource要素に関する説明として、正しいものを1つ選びなさい。{
  ~コンピュータのコードを表示するための要素である。
  ~文書内のコンテンツが他の情報源からの引用である事を示す要素である。
  ~文書内に、Javascriptやデータブロックを組み込むための要素である。
  ~サイトの外部にある画像のURLを指定するための要素である。
  =動画や音声に関するメディアファイルの種類やURLを指定するための要素である。
} #### source要素は、video要素やaudio要素の子要素として、メディアファイルの種類やURLを指定するために使われます。よって正解はEです。<br>
		Dにある画像のURLに関してですが、ファイルがどこに存在するかに関わらずimg要素のsrc属性で指定します。<br>
		Aはcode要素、Bはq要素およびblockquote要素、Cはscript要素に関する説明です。

::例題3.1::以下のようにHTML5の仕様でマークアップを行い、テキストの一部を“重要なテキスト範囲”として指定し、音声出力における強い表現などを期待したい。コード内の①に入る、最も適切な要素名を選択肢から一つ選びなさい。{
  ~mark
  ~s
  =strong
  ~b
  ~i
} #### Aのmark要素は、ハイライト表示を行うために使う要素でテキストの重要性を指定するものではありません。Bのs要素は、正確でなくなった情報について指定し、一般的なブラウザでは打ち消し線が引かれますので不正解です。Cのstrong要素は、重要な部分を指定するために定義されているものなので正解です。Dのb要素で囲まれたテキストは、一般的なブラウザでは太字表示されます。しかし、これはHTML5においては文体を変えるために使うものであって、重要性を指定するためのものではないと明示されています。よって不正解です。Eのi要素は、一般的なブラウザでは斜体表示されるものですが、重要性を指定するためものではありません。HTML5でマークアップする際は、似たような表示を行う要素でも、それぞれ使用する場面の想定が違う場合があるので気をつけましょう。 