### ComponentOne
* TouchToolkit for WinForms でタッチ操作に対応
	+ https://www.grapecity.co.jp/developer/controls/winforms/touchtoolkit
	+ C1ApplicationZoom
		- アプリケーション内のすべてのフォームでズームジェスチャを有効にします。
	+ ジェスチャサポート
		- ピンチズーム、スワイプ、エクスパンドなどのあらゆるジェスチャを使用して、アプリケーションを簡単に操作できます。
	+ ズーム、拡大、パンのサポート
		- デバイスが小さくても 大丈夫です。最小サイズの Windows デバイスでも、ズーム、拡大、パンを使用して、アプリケーション内を簡単にナビゲートできます。


* BarCode for WinForms でバーコードとQRコードの読込に対応


### ClickOnce
* http://www.atmarkit.co.jp/ait/subtop/features/dotnet/clickonce_index.html
* https://msdn.microsoft.com/ja-jp/library/ms973805.aspx
* 良くない点
	+ 新しいバージョンがでる度に全体をダウンロードし直して、インストールする

### MSIX
	MSIパッケージの後継。ClickOneceの機能も含む
* https://www.infoq.com/jp/news/2018/08/UWP-Application-Distribution
* 良い点
	+ 差分リリースが可能

### その他
* レイアウト
	+ 左右に表示させる？
* 回転への対応
* ダブルタップで標準サイズに戻る方が良い？
* テキスト入力のモードについて、英数字のみにしたい
* カメラは使える？
	+ Windows10標準APIのMediaCaptureが上手く動作しない（カメラが起動しない）とのこと
		- https://dobon.net/cgi-bin/vbbbs/srch.cgi?mode=srch&logs=./vb/vb.dat&page=140&no=0&word=%82%C5%82%CD&andor=and&KYO=&PAGE=20
	+ WPFなら別のツールがある模様

### Framework
* 判定方法
	reg query "HKLM\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full" | find "Release"
* 4.6.x
	+ Visual Studio 2015
* 4.7.x
	+ Visual Studio 2017
	+ 4.7.0:Windows 10 ver.1703←ｲﾏｺｺ
	+ 4.7.1:Windows 10 ver.1709
	+ 4.7.2:Windows 10 ver.1803、ver.1809
		- 下位バージョンのWindowsでもインストール可能
* 4.8.x
	+ Visual Studio 2019
	+ Windows 10 ver.1903?

### WPF
	WPFでUWPもどきのアプリケーションを作成するために、UwpDesktopを使う
* https://www.nuget.org/packages/UwpDesktop/
* CaptureElementが使えず、プレビューが動作しない
	+ 替わりにイメージ変換してから表示するが、変換処理に時間と負荷が掛かる
* CameraCaptureUI