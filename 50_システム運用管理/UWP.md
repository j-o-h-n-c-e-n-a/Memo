## 課題
1. バックライトの制御
	* エラーになっていた処理は、懐中電灯モードのためのAPI呼出
	* Lamp API が存在していないデバイスでは懐中電灯モードは使えない
	* カメラ撮影時に常時ライトをつけたい場合は、FlashControl APIを使う（HDR撮影はせずにFlashOnのみ有効にする）
2. 全体の文字サイズの拡大方法。
	* 指による拡大縮小
		+ https://docs.microsoft.com/ja-jp/windows/uwp/design/input/touch-interactions
	* アプリ自体の文字サイズ変更は別機能
3. バイブレーションの制御
	* https://docs.microsoft.com/ja-jp/previous-versions/windows/dn611853(v=win.10)
	* どのような場面で使いたい？
4. 例外処理のログ出力
	* MetroLog
5. SQLServerへの接続方法。
	* SQL Client
		+ https://docs.microsoft.com/ja-jp/windows/uwp/data-access/sql-server-databases
	* .NET Standard2.0
		+ エンタープライズ認証の宣言が必要
		+ Windows認証が必要（AD認証済であること）
		+ SQLServer側にタブレット用ADユーザを登録して、読み書き権限のロールを与える
		+ 問題点：タブレット用ADユーザの取り扱いが不透明
	* LocalDB
		+ 使用できない
		+ ローカルでやりたい場合、SQLiteデータベースを使用する
6. WebAPIを通したデータのやり取り
	* Webサーバーが必要
		+ 問題点：サーバーメンテナンス中はサービスが停止する
7. 更新プログラムの再配布方法についての調査
	* 現行のWindows環境では、サイドローディングで手動インストールする方法しか取れない
		+ 【対策】携帯端末のバージョンを1803以降にする
		+ 【対策】開発端末のバージョンを1803以降にする
			- サポート機能が豊富なVS2017での開発が望ましい
	* サイドローディング
		+ https://qiita.com/TakenoriHirao/items/dfc2bf9ddd024f46be9f
		+ https://msdn.microsoft.com/ja-jp/library/windows/hardware/dn938326(v=vs.85).aspx
		+ 利用には端末設定を「サイドロードアプリ」にする必要がある
		+ サイドローディングの自動更新機能はWindows10のバージョンを1803以降にする必要がある
	* msixパッケージ
		+ msiパッケージの後継
		+ ClickOnceと似たのやり方で配布ができる
		+ Windows10のバージョンを1803以降にする必要がある
		+ https://blog.okazuki.jp/entry/2018/09/27/182936
8. WinFormsでも作る(WinFormsの説明ファイルを参照)
* 番号を手入力
* ズーム機能が欲しい

### 通知領域への通知
* https://book.mynavi.jp/manatee/detail/id=75974