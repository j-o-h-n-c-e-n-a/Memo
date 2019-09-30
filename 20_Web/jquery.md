# jQuery
	2018年時点において、TypeScript が主流となりjQueryによる記述よりも
	javascript本来の記述の方が好まれるようになった。
## 備忘録
* $(document).ready
	- $(function(){  //なにかしらの処理});　と同じ。

* $.getJSON(url, [,object] [function])
	jQuery.getメソッドをjsonに限定しただけのメソッド。
	以下、下位になるほど汎用的（詳細な設定が可能）になる。
	- $.get(url, [,object] [function])
		jQuery.ajaxメソッドを簡単に利用できるようにしたメソッド
	- $.ajax( url [,object] )

* $.stringify(object)


## 参考リンク
[jQueryの基本](http://qiita.com/8845musign/items/88a8c693c84ba63cea1d)
[jQuery入門](http://www.jquerystudy.info/tutorial/intro/ready.html)
[JavaScript 日本語リファレンス ](http://js.studio-kingdom.com/)
