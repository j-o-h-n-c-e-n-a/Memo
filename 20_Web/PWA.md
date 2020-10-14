## 参考
* [awesome blazor](https://github.com/AdrienTorris/awesome-blazor)
* [はじめてのプログレッシブ ウェブアプリ](https://codelabs.developers.google.com/codelabs/your-first-pwapp-ja/#0)
* [GitHubを使って3分でHPを公開する。](https://qiita.com/budougumi0617/items/221bb946d1c90d6769e9)
* [API一覧](https://developers.google.com/web/updates/capabilities)

### ステップ
1. HTTPSを有効にする
2. Webアプリのマニュフェストを作る
  * [Web App Manifest](https://developer.mozilla.org/en-US/docs/Web/Manifest)
3. Service Workersを作る
  * install
  	- 必要なファイルをキャッシュする
  * activate
  * fetch
  	- リクエストの際に発生し、キャッシュからリソースを返す
  	- キャッシュの読み込みに失敗したら、ネットワークからリソースを読み込む

### デバイス
#### 位置情報
#### センサー
#### カメラ
  * QR, バーコード読み取り
  * OCR
#### NFC
#### マイクとスピーカー
#### 音声合成と読み上げ
#### Bluetooth
#### 音声認識

### 通知
#### Push API
  * [プッシュ通知を作る](https://techblog.asahi-net.co.jp/entry/2018/06/15/162752)
#### Notification API
* [BlazorExtensions](https://github.com/BlazorExtensions/Notifications)

### ストレージ
#### localstrage
#### IndexedDB

### WebAssembly
#### rust:rustc
#### typescript:Assemblyscript

### キャッシュ
1. 古いキャッシュの取り扱い
  - 古いキャッシュが読み込まれないように工夫する
  	+ キャッシュのバージョニング

### デザイン
1. アイコンの用意
2. テーマカラーの設定
  - ブラウザテーマカラー
  - アプリテーマカラー

### フレームワーク
#### ionic
  * Angularベース
#### Blazor
 
### 注意点
  * 常時HTTPS対応
  * バックグラウンドにいるときはコードを実行できない
  * キャッシュ管理が大変

### サンプル
  * [シンプルなPWAサンプルここに置いておきますね](https://qiita.com/kazaoki/items/e93b88556fcd05d28ddc)
  * [サンプルコードで学ぶPWA](https://qiita.com/radiocat/items/034904a094d07c389a4f)
  * [PWAをもっと簡単に初めてみる](https://qiita.com/poster-keisuke/items/6651140fa20c7aa18474)

  * [](https://qiita.com/h_tyokinuhata/items/ab8e0337085997be04b1)
 
## 利用アイデア
													
	参考												
	①	[Cordova Angular6のアプリをPWA化してみる](https://qiita.com/beholder/items/925f523c6ae276e4a495)											
	②	[Angular CLI v8でPWAを作ってみよう](https://qiita.com/puku0x/items/a6db78cc67d1eb960384)											
	③	[サービスワーカーを始める](https://angular.jp/guide/service-worker-getting-started)											
													
	＜プロジェクトのフォルダ内で実行＞												
	1	PWAのモジュールをインストール											
			ng add @angular/pwa										
													
		・	インストールがうまくいかない場合、下記も実行										
			A.	npm i @angular/service-worker									
			B.	angular.json の編集									※
			C.	app.moduel.ts の編集									※
													※：②のリンクにあるGitHubを参照のこと
	2	ビルド実行											
			ng build --prod										
													
	3	ビルド先にファイルができていることを確認											
													
	4	アプリケーションを実行するためにIISにビルド先を登録											
													
	5	ブラウザからURLを指定して、アプリケーション実行（ローカル）											
													
	1	自己署名証明書の作成											
		・	PowerShellを管理者モードで起動する										
		・	下記のコマンドを実行し、自己署名証明書を作成する										
			①	$cert = New-SelfSignedCertificate -Subject "sv_kasprova" -DnsName "sv_kasprova","192.168.121.197" -CertStoreLocation "cert:\LocalMachine\My" -KeyAlgorithm RSA -KeyLength 2048 -KeyExportPolicy Exportable -NotAfter (Get-Date).AddYears(10)
			②	$password = ConvertTo-SecureString -String "P@ssw0rd" -Force -AsPlainText									
			③	Export-PfxCertificate -Cert $cert -FilePath "F:\cert\sv_kasprova.pfx" -Password $password									
			④	Export-Certificate -Type CERT -Cert $cert -FilePath F:\cert\sv_kasprova.cer									
	2	IISへの追加											
		・	自PCのホーム→IIS→サーバー証明書を選択し、「機能を開く」をクリックする										
		・	「インポート」より、発行した自己署名証明書をインポートする										
		・	新しいWebサイトを作成する										
		・	バインドの種類を「https」とし、「SSL証明書」に作成した自己署名証明書を選択する										
		・	作成されたWebサイトに、ビルド先のファイルをWebアプリケーションとして追加する										
	3	クライアントでの確認											
		[windows]											
		・	サーバーとは異なるPCにて、１－④で作成した証明書を「信頼されたルート証明書」へインポートする										
		・	証明書のインストール後、再度URLへ遷移し、エラーが出ないことを確認する										
		[android]											
		・	「設定」→「セキュリティ」の順にタップ										
		・	「認証情報ストレージ」セクションの証明書を保存した保存先をタップ										
		・	証明書の一覧からインポートするクライアント証明書を選択。										
		・	クライアント証明書のパスワードを入力し、「OK」をタップ										

	自己署名だと、スマホ利用時にChromeでエラーが出る。このため認証局を立てる方法をとる。
	下記の手順に則り、認証局とルート証明書、Webサーバーのサーバー証明書を作成する。
* [自組織のCAを作成するための手順](https://www.ipentec.com/document/windows-windows-server-create-certification-authority-of-own-organization)
	クライアントにはルート証明書をインストールする。
	その他
* [Windows Server ADCSの証明書自動配布設定](https://mitomoha.hatenablog.com/entry/2019/08/14/001734)

	＜Phonegapの機能置き換え＞												
		〇	カメラ										
		〇	QR										
		△	バイブレーション										
			・	振動することは可能だが、タッチ操作に関係がない									
			・	タッチイベントと組み合わせて、似た動作を実装は可能だが強弱をつけれない（端末がバイブOFFだと動作しない？）									
		◎	位置情報										
			・	実装済み									
		〇	バージョン										
			・	マニュフェストに記載する									
		×	パーミッション										
			・	カメラや位置情報の使用許可は、ブラウザ（OS）で制御する									
		〇	スプラッシュ										
		×	NFC										
			・	まだドラフト版らしいが、近い将来に使用できる									
		〇	ネットワーク接続情報										
			・	Chromeは取得可能な模様									
		？	端末識別										
			・	端末識別に関する基礎知識									
				https://www.saitolab.org/fp_site/									
			・	端末識別に関して１００％信頼できる手法がないため、									
				何らかのユーザ認証方式に変更する必要がある									
				①	生体認証								
				②	デバイス認証しつつ、ログイン認証と組み合わせ								
					（デバイス情報が変更となった場合は、ログインさせる等）								
				③	Googleの認証を利用する（Androidのアカウントを使用）								


https://entityframeworkcore.com/ja/knowledge-base/59955735/
https://thinkami.hatenablog.com/entry/2019/12/17/224720#StartupcsにDbContextと接続文字列を追加
https://devadjust.exblog.jp/28138344/


https://qiita.com/Naoto9282/items/8427918564400968bd2b
https://techblog.roxx.co.jp/entry/2019/03/13/135739
https://anatoo.hatenablog.com/entry/2018/10/03/000518

https://knowledge.sakura.ad.jp/23201/
https://techracho.bpsinc.jp/hachi8833/2019_10_09/80851
https://unskilled.site/デバイスを判別する5つの方法/
https://www.saitolab.org/fp_site/

https://www.cresco.co.jp/blog/

https://qiita.com/TakeshiNickOsanai/items/8d012a128827c9db980d