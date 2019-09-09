## 参考
* [ひな型の作り方](https://qiita.com/puku0x/items/f12e23aa15a36f439e79)

## 環境構築
### 事前準備
	下記のツールをインストールする
* nodeJS
* TypeScript
* Git

### Github からひな型をクローン

## Androidリリース
### 事前準備
	下記のツールをインストールする
* Android Studio
* JDK
* Android SDK(Phonegapの対応バージョンに合わせる)
### リリースビルド
### 署名
	署名ファイルの作成方法については下記参照
* [署名ファイルの作成方法](https://qiita.com/tsunet111/items/69b46744ba427670dfe1)

## プラグインの使用方法
### スプラッシュスクリーン
	cordova-plugin-splashscreen
### NFC
	phonegap-nfc
* typescriptで使用するには、 @types のインストール後にdtsファイルの変更が必要
### QRコード
	cordova-plugin-camera
	cordova-plugin-device
	cordova-plugin-file
	cordova-plugin-media-capture
	phonegap-plugin-barcodescanner
	phonegap-plugin-image-capture
	phonegap-plugin-media-stream
### GPS
	cordova-plugin-geolocation
* プラグインのインストールにて、navigator が拡張される
### ネットワーク情報
	cordova-plugin-network-information
* typescriptは、 @types のインストールで使用可能になる
### バージョン情報
	cordova-plugin-app-version
* typescriptは、 @types のインストールで使用可能になる
### 権限
	cordova-plugin-android-permissions