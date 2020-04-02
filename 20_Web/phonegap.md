## 参考
	下記のサイトを参考にPhoneGapでのアプリ開発を行う。
* [署名ファイルの作成方法](https://qiita.com/tsunet111/items/69b46744ba427670dfe1)
* [WindowsでPhoneGapアプリ開発＆デバッグ環境構築](https://qiita.com/tsunet111/items/2ab7a1bfdf58a08af38f)
* [OnsenUI2 + Angular2 + PhoneGapの雛形を作る](https://qiita.com/puku0x/items/301800e43a78c046a085)
* [Angular + Onsen UI 2 + PhoneGap Starter](https://github.com/puku0x/angular-onsenui2-webpack2)
* [PhoneGap日本語公式](http://ja.docs.phonegap.com/)
* [プラグインAPI](http://ja.docs.phonegap.com/references/plugin-apis/)
* [OnsenUI公式](https://ja.onsen.io/)
* [Angular公式](https://angular.jp/)

### 1. 環境構築

1. node.js　をダウンロードしてインストールする。
その他、typescriptのインストールも済ませておくこと。（別紙の「環境構築」手順書参照）

2. インストール後、PowerShell　より下記のコマンドを実行する。
（npm はnode.js のコマンド。パッケージ名の後に＠を付けて必要なバージョンを記述）
```
npm install -g phonegap
npm install -g @angular/cli@6.0.3
```

3. 開発作業用に任意のフォルダを作成し、
下記のコマンドを実行すると、開発用のテンプレートが作成される。
```
phonegap create hello
```
hello の部分がアプリ名となる。

以下は、3. の開発作業用フォルダでの作業となる。※
4. 下記のコマンドを実行し、依存ライブラリをインストールする。
```
npm init -y
```

5. 4.にて作成された、package.json　ファイルを開き、必要なパッケージ情報を追記する。
OnsenUIは、2. のようにnpm install コマンドに --save オプションを付けることでも
インストール可能。（バージョンに注意）
* scriptsにビルド用スクリプト追加
* dependenciesにOnsenUI2とAngular2関連を追加
* devDependenciesにTypeScriptとWebpack関連を追加

6. 下記のコマンドを実行し、追記したライブラリをインストールする。
```
npm install
```

※3. により、PhoneGap でのデフォルト環境が構築されるが、
現行アプリを利用する場合は、ソース管理ツールより任意のフォルダに
ソースをダウンロードすることで、3.～5.の作業は省略できるため、
6.を実行する。

### 2. フォルダ構成
	プログラムは下記のような構成をしている。
* dist
* e2e
* hooks
* node_modulesangularなど使用モジュールの格納先。
* platforms実行ビルドパッケージの格納先。
* plugin使用プラグインの格納先。
* srcプログラムソースの格納先。
* wwwデバッグ実行ファイルの格納先。
	+ config.xmlアプリの設定ファイル（アプリ名などを記述）。
	+ package.jsonパッケージ登録ファイル。

### 3. プログラム実装
	TypeScriptでの記述やコンポーネント、サービス、DIの考え方などの基礎は、
	Angularの開発手法に則り、プログラムの実装を行う。
	開発の流れは、Angular公式の基礎ガイド→チュートリアルを一読のこと。（参考書あり）

	PhoneGapプラグインを使用する場合は、npm コマンドにてパッケージをインストールし、
	プラグイン仕様に則って使用する。（詳細はPhoneGap公式かプラグインの配布元サイトを参照のこと）

* 以下、プログラムを実装する主なフォルダの説明
1. src　フォルダ
	+ 基本的にはsrcフォルダに必要なプログラムを配置する。
2. environments　フォルダ
	+ アプリの設定値を定義する場所
3. src/app　フォルダ
	+ アプリを配置する場所。
	+ 以下は構成例。
		- models：アプリ内部で保持するデータを定義する。
		- modules：アプリ画面を配置。
		- services：アプリから呼び出すサービスを定義する。
			* db：内部データ操作
			* function：関数呼び出し定義
			* http：外部呼び出し定義（WebAPIの呼び出しを行う）
			* shareddata：内部データ格納先
### 4. 使用プラグイン
詳細は、
[プラグインまとめサイト](https://cordova.apache.org/plugins/)
参照のこと。

#### 概要
* cordova-plugin-android-permissions
	+ アプリ実行時にカメラやドキュメントへのアクセス許可を求め、アプリが利用できるようにする。
* cordova-plugin-app-version
	+ アプリのバージョン情報を取得する。（config.xmlに記載）
	+ typescriptは、 @types 型定義ファイルのインストールで使用する
* cordova-plugin-camera
	+ アプリがカメラを使用できるようにする。
* cordova-plugin-compat
	+ Cordovaとの互換性の為にインストールされる。（phonegap-plugin-barcodescannerにて使用）
* cordova-plugin-device
	+ Cordovaのバージョン情報を取得。
* cordova-plugin-file
	+ 端末内のファイルへアクセスする。
* cordova-plugin-geolocation
	+ 端末の位置情報を取得する。
	+ プラグインのインストールにて、navigator が拡張される
	+ [ジオローケーションAPI仕様]]](http://www.asahi-net.or.jp/~ax2s-kmtn/internet/geo/REC-geolocation-API-20131024.html)
	+ [A-GPS](https://kimagurenote.net/kn/A-GPS)
* cordova-plugin-media-capture
	+ 端末側の録音・録画機能にアクセスする。
* cordova-plugin-network-information
	+ 端末のネットワーク接続情報を取得する。（WiFi/Sim）
	+ typescriptは、 @types 型定義ファイルのインストールで使用する
* cordova-plugin-splashscreen
	+ アプリ起動時にスプラッシュスクリーンを表示する。
* cordova-plugin-whitelist
	+ アプリが遷移できるURLを指定することができる。
* es6-promise-plugin
	+ Cordovaでのスクリプトの実装がコールバック地獄（関数の戻り値に対する記述が多くなる）
	となるのをPromiseでラップして、簡略化する。
	+ [参考](http://neos21.hatenablog.com/entry/2017/09/07/080000)

#### PhoneGapのカメラ関連プラグイン
* phonegap-plugin-media-stream
* phonegap-plugin-barcodescanner
* phonegap-plugin-image-capture

#### PhoneGapのNFC関連プラグイン
* phonegap-nfc
	+ typescriptで利用するには、 @types 型定義ファイルのインストール後にdtsファイルの変更が必要
##### 変更内容１
	[index.d.ts]ファイルを下記のとおり変更し、利用バージョンのtypescript型定義を有効にする
```
declare module 'nfc' {
```
↓
```
declare module 'phonegap-nfc' {
```
##### 変更内容２
	[AndroidManifest.xml]ファイルを下記のとおり変更し、NFC利用を許可する
```
<uses-feature android:name="android.hardware.nfc" android:required="false" />
```
↓
```
<uses-feature android:name="android.hardware.nfc" android:required="true" />
```
##### 変更内容３
	プラグイン利用箇所の定義方法
```
import { } from 'phonegap-nfc';
// サンプルコード
 nfc.addNdefListener(
            (nfcEvent) => {
                var rec: PhoneGapNfc.NdefRecord;
                console.log(`Get.`);
                rec = nfcEvent.tag.ndefMessage[0];
                console.log(`${ndef.textHelper.decodePayload(rec.payload)}`);
            },
            () => {
                console.log(`Success.`);
            },
            () => {
                console.log(`Fail.`);
            }
        );
```
##### 参考
* [github](https://github.com/chariotsolutions/phonegap-nfc)
* [phonegap](https://phonegap.com/blog/2011/09/26/building-an-nfc-enabled-android-application-with-phonegap/)
* [AndroidアプリでNFCタグを読み書きするための基礎知識](https://www.atmarkit.co.jp/ait/articles/1211/27/news072.html)

### 5. OnsenUI 使用コンポーネント
詳細は、
[公式サイト](https://ja.onsen.io/v2/api/angular2/)
参照のこと。

#### 概要
* ons-navigator
	+ 画面遷移に使用している。（ons-pageと組み合わせ）
	+ pushで画面出力し、popで表示画面を閉じる。
	+ popでひとつ前にpushされた画面に戻る。
* ons-page
	+ 画面の定義に使用。
* ons-button
	+ ボタンに使用。
* ons-toolbar
	+ ツールバーの表示に使用。
* ons-list
	+ 項目をリスト表示する。
* ons-list-header
	+ リストのヘッダを定義する。
* ons-row
	+ 項目の配置をグリッド配置に調整する。（行）
* ons-col
	+ 項目の配置をグリッド配置に調整する。（列）
* ons-tabbar
	+ 画面下部のタブ表示に使用。（ons-tabと組み合わせ）
* ons-tab
	+ 画面下部のタブ表示に使用。
* ons-carousel
	+ アイテムを横にスワイプできるようにする。（カルーセル）
* ons-carousel-item
	+ カルーセル用のアイテムを定義する。
* ons-dialog
	+ ダイアログを表示する。
* ons-progress-circular
	+ ローディング中にクルクル回る表示をする。

### 6. Angular Material　関連
* [Angular Material 公式（英語）](https://material.angular.io/)
カンバンアプリでは、見栄えをよくする為にマテリアルデザインのコントロールを配置している。
このため、パッケージに @angular/material が追加されており、
プログラムに src/material.module.ts が配置されている。

material.module.ts で使用するモジュール（コントロール）を定義しているのだが、
使わなくなったものもあり、全てを使用しているわけではない。

* 主に使用されているコントロールは以下のとおり
1. mat-sidenav-container
	+ ツールバーを横から表示するために使用している。
2. mat-icon
	+ マテリアルデザインなアイコン表示をする。
3. mat-button-toggle
	+ マテリアルデザインなボタン表示をする。（設定画面にて使用）

### 7. バージョンアップ
