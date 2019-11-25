# angular

## 使い方

### コンポーネントの追加
  ng generate component hoge

### ルーティング

### パイプ
* 書式設定

### ディレクティブ
* *ngFor
* *ngIf

## angular+materials

## angular+phonegap(cordova)+onsen-ui
### ナビゲーション
#### OnsNavigator
  画面遷移は、画面の push/pop で表現する。
  ルーティングと違いは、URLで切り替えるか切り替えないか。

## バージョンアップ
  ＜基本事項＞
    Angualr のバージョニングは、半年毎にメジャーバージョンがリリースされ、
    各バージョンのサポート期間は「１８カ月」である。
    そのため、１年周期でアップグレードを行うことが望ましい。
    アップグレードは、次バージョンへ順次行うことが推奨される。
    また、OnsenUIを使用している場合、更新が最も遅いため、
    はじめにバージョンの依存関係を確認するとよい。
    ↓Angularのアップデートガイドに従う
    https://update.angular.io/#6.0:7.2

  ・  npm のバージョンを確認する
      npm --version

    【現バージョンより新しいバージョンがある場合】
    ・  最新バージョンにアップデートする
        npm install -g npm
    ・  npm のバージョンを確認する
        npm --version

  ・  アップデートチェッカーをインストールする
      npm install -g npm-check-updates

  ・  現バージョンを確認する
      ncu -g

    【現バージョンより新しいバージョンがある場合】
    ・  更新したいバージョンにするため、対象ソフトウェアを削除する
        npm uninstall -g @angular/cli
        npm uninstall -g phonegap
        npm uninstall -g typescript

    ・  更新したいバージョンの対象ソフトウェアをインストールする
        npm install -g phonegap
        npm install -g @angular/cli@x.y.z
        npm install -g typescript@x.y.z

  ＜プロジェクトフォルダ内で作業＞
    ・  現バージョンを確認する
        ncu

    ・  package.json のバージョンを最新にする
        ncu -u

      【新しいバージョンが更新したいバージョンと異なる場合】
      ・  必要なバージョンを１つずつアップデートする
      ・  たくさん更新対象がある場合は、package.jsonを直接編集する

    ・  最新バージョンをインストールする
        npm install

    ・  アップデートを確認する
        ncu

    ・  モジュールを確認する
        npm ls

      【モジュール不足のエラーが出たら】
      ・  下記のツールをインストールして、実行する
          npm install -g npm-install-missing
          npm-install-missing
      ・  それでもおかしい場合、node_modules フォルダを削除したのち
          npm install
        を実行する

    ・  プロジェクトのソースを更新する
        ng update

  ＜リリース時＞
  ・  android studio のバージョンを確認する

  ・  インストールされたphonegapに対応した、android SDK をインストールする
      例）ver.9は、APIレベル28のSDKが必要




https://lacolaco.hatenablog.com/entry/2019/04/10/235400
https://lacolaco.hatenablog.com/entry/2019/05/10/005829


phonegap のバージョンがｖ８からｖ９に更新される。（AndroidAPIレベル２８対応）																					
	https://docs.monaca.io/ja/release_notes/20190627_cordova9/																				
typescript の変更点（参考）																					
	https://qiita.com/vvakame/items/e7bbaff54db8fbf986bb																				
angular/cli の変更点																					
	https://codezine.jp/article/detail/11665																				
angular の変更点																					
	https://www.publickey1.jp/blog/19/angular_8ivyjsdifferential_loading.html																				
＜おまけ：新機能の検証＞																					
【高速化】レンダリングエンジンをIvyに変更する																					←動作があやしい
	https://dev.classmethod.jp/client-side/angular-v8-release/																				
【高速化】ビルド高速化ツールのインストール																					←動作せず
	https://angular.jp/guide/bazel																				
【高速化】web worker を使用する																					←動作せず
	https://angular.jp/guide/web-worker																				
