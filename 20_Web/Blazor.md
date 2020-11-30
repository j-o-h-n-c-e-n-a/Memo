## 概要
* C#
* Razor構文
* await/async

## 実装
* BlazorStrap
  + 便利ではあるが冗長で、ショボいスマホだと動作が重くなった
* bootstrap
* コンポーネント作成
  + QRコード
    - jsQR.js を使用
  + 仮想キーボード
    - Modal でテンキーっぽいものを作成
  + スワイプ
    - タッチイベントを利用したが、パラメータの更新頻度が多くて重くなった
  + PullToReflesh
    - タッチイベントを利用したが、パラメータの更新頻度が多くて重くなった
* 依存性の注入
* WebAPI呼出
* localstrage/sessionstrage
  + Blazored シリーズのライブラリを使用
* ログイン認証
	+ https://qiita.com/Mutz/items/1b0d7a826004dd9272db
* javascriptを実行
  + javascript 呼出が、思いの外動作が重くなる
* javascriptから実行
* settings.json
* PDF.js
  + Blazorと関係ないけど、PDFを表示するために使用

## データベース
* Entity Framework
  + レスポンスの制限が厳しいため採用を見送り
  + Dapper の利用も検討
  + 結局はDBConnectionの直接クエリ実行

## 配布
* Blazor PWA を TWA にしてアプリストアで配布
  + アプリストアの利用は規定でできないので、やり方だけ調査
* サービスワーカー関連
  + インストールボタンと更新表示の実装


## 参考
* [Blazor入門](https://mseeeen.msen.jp/asp-dotnet-core-blazor-install/)
* [ASP.NET Core Blazor - Blazor WebAssembly と Blazor Server の違いは？ ５つのポイント](https://qiita.com/furugen/items/24b53174ff3977ef50e7)
* [Blazor Tutorialまとめ](https://qiita.com/NAVE/items/1e9d44ea2c0b43dcd9b7)
* [.NET 5 がリリース！ 主に Blazor の変更点についてまとめました](https://qiita.com/furugen/items/57de9de6bb721f7cfdb7)
* [ASP.NET Core Blazor WebAssembly パフォーマンスに関するベスト プラクティス](https://docs.microsoft.com/ja-jp/aspnet/core/blazor/webassembly-performance-best-practices?view=aspnetcore-5.0)
* [PWA（Progressive Web Apps）を最低限で試してみる](https://qiita.com/tsunet111/items/450728056ba92d35508c)
* [Service Workerの基本とそれを使ってできること](https://qiita.com/y_fujieda/items/f9e765ac9d89ba241154)
* [Service Worker スクリプトのインストールと更新処理](https://nhiroki.jp/2018/02/15/service-worker-install-and-update-scripts)
* [Service Worker の Registration](https://nhiroki.jp/2015/07/05/service-worker-registration)
* [Service Worker](https://qiita.com/propella/items/6500f76c9c1521878a6b)
* [Trusted Web Activityを触ってみる](https://blog.uskay.io/article/004-trusted-web-activity)
* [Google Play Store でPWA配信 (TWA)](https://qiita.com/zprodev/items/181c1c8f19bc0beb1183)
* [PWAをTWAでGoogle Play Storeに配信してみた](https://www.maytry.net/how-to-release-twa/)
* [ASP.NET MVC の初回実行時の表示が遅いのを解消する方法](https://webbibouroku.com/Blog/Article/iis-preload)
* [パフォーマンスに関する考慮事項 (Entity Framework)](https://docs.microsoft.com/ja-jp/dotnet/framework/data/adonet/ef/performance-considerations)
* [EntityFramework(24):落穂ひろい](http://gushwell.ldblog.jp/archives/52443624.html)
* [Dapper Tutorial](https://dapper-tutorial.net/dapper)
* [Dapperについてまとめてみた](https://sweets-junkie.hatenablog.com/entry/2014/03/07/010004)
* [DapperのQueryを使ってマルチマッピングしてみる](https://qiita.com/Tokeiya/items/dda1096d03dfbf5fe431)
* [EntityFramework Core のメモ](https://qiita.com/gelehrte/items/6245142c7425870eb30e)
* [Blazor-Fluxor = C# + Redux + DI](https://blablablazor.hatenablog.com/entry/try-blazor-fluxor-1)