## 参考
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

### ストレージ
#### localstrage
#### IndexedDB

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
	- Angularベース

### 注意点
* 常時HTTPS対応
* バックグラウンドにいるときはコードを実行できない
* キャッシュ管理が大変

### サンプル
* [シンプルなPWAサンプルここに置いておきますね](https://qiita.com/kazaoki/items/e93b88556fcd05d28ddc)
* [サンプルコードで学ぶPWA](https://qiita.com/radiocat/items/034904a094d07c389a4f)
* [PWAをもっと簡単に初めてみる](https://qiita.com/poster-keisuke/items/6651140fa20c7aa18474)

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
													
	＜HTTPSサーバーの用意＞												
	1	自己署名証明書の作成											
		・	PowerShellを管理者モードで起動する										
		・	下記のコマンドを実行し、自己署名証明書を作成する										
			①	$cert = New-SelfSignedCertificate -DnsName "sv_kasprova","192.168.121.197" -CertStoreLocation "cert:\LocalMachine\My"									
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
		・	サーバーとは異なるPCにて、１－④で作成した証明書を「信頼されたルート証明書」へインポートする										
		・	証明書のインストール後、再度URLへ遷移し、エラーが出ないことを確認する										
													
	＜Phonegapの機能置き換え＞												
		カメラ											
		QR											
		バイブレーション											
		位置情報											
		バージョン											
		パーミッション											
		スプラッシュ											
		NFC											
