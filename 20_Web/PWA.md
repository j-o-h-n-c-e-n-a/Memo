## 参考
* [はじめてのプログレッシブ ウェブアプリ](https://codelabs.developers.google.com/codelabs/your-first-pwapp-ja/#0)
* [GitHubを使って3分でHPを公開する。](https://qiita.com/budougumi0617/items/221bb946d1c90d6769e9)
* 
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
