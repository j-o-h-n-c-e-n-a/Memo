## 参考
* [](https://www.webprofessional.jp/retrofit-your-website-as-a-progressive-web-app/undefined)
* [はじめてのプログレッシブ ウェブアプリ](https://codelabs.developers.google.com/codelabs/your-first-pwapp-ja/#0)
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
* 位置情報
* センサー
* カメラ
* マイクとスピーカー
* 音声合成と読み上げ
* Bluetooth
* 音声認識
### 通知
* Push API
* Notification API
### ストレージ
* localstrage
* IndexedDB
### キャッシュ
* 古いキャッシュの取り扱い
	- 古いキャッシュが読み込まれないように工夫する
		+ キャッシュのバージョニング
### デザイン
* アイコンの用意
* テーマカラーの設定
	- ブラウザテーマカラー
	- アプリテーマカラー
### フレームワーク
* ionic
	- Angularベース
### 注意点
* バックグラウンドにいるときはコードを実行できない
* キャッシュ管理が大変

## 利用アイデア
