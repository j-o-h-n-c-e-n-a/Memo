
### Link
* [例題](https://postd.cc/50-data-structure-and-algorithms-interview-questions-for-programmers/)
* [例題2](https://tech.pjin.jp/blog/2016/04/26/java-silver-練習問題%EF%BC%91/)
* [java 8 から 11 変更点](https://qiita.com/nowokay/items/1ce24079f4daafc73b4a)
* [](https://qiita.com/to-lz1/items/898421e5050cae90ec20)
* [Java SE 8からJava SE 11までの主要な変更点](https://terasolunaorg.github.io/guideline/5.5.1.RELEASE/ja/Appendix/Java11Changes.html)
* [Java9,10,11の新機能](https://qiita.com/chan_kaku/items/ecdde8228a9c67a36dd0)
* [モジュールシステムを学ぶ](https://qiita.com/opengl-8080/items/93c8e0cf58654d5f73cb)
* [](https://qiita.com/Allenie/items/8ff17501b49f6a889ff8)
* [](https://qiita.com/snowrabbit_ccf/items/db9de0e8fb5fd82e8ad3)
* [](https://qiita.com/atushi-machine/items/a3d372e53cc19ae4ec1c)
* [](https://www.r-staffing.co.jp/engineer/entry/20200515_1)
* [](https://ja.wikipedia.org/wiki/Javaバージョン履歴)

## 試験
### 出題範囲
#### Javaテクノロジと開発環境についての理解
* Javaテクノロジと開発環境
* Java 言語の主要機能
#### 簡単なJavaプログラムの作成
* mainメソッドを持つ実行可能なJavaプログラムの作成
* コマンドラインでのJavaプログラムのコンパイルと実行
* パッケージの宣言とインポート
#### Javaの基本データ型と文字列の操作
* 変数の宣言および初期化 (基本データ型のキャストとプロモーションを含む)
* 変数のスコープ
* Local Variable Typeインタフェースの使用
* 文字列の作成と操作
* StringBuilderクラスのメソッドを使用した文字列の操作
#### 演算子と制御構造
* 演算子の使用 (演算子の優先順位を変更するための括弧の使用を含む)
* 分岐文( if、if/else、switch)の使用
* 繰り返し文(do/while、while、for文および拡張for文)の使用とネストした繰り返し文およびbreak、continuneの使用
#### 配列の操作
* 1次元配列の宣言、インスタンス化、初期化および使用
* 2次元配列の宣言、インスタンス化、初期化および使用
#### クラスの宣言とインスタンスの使用
* 参照型の宣言とインスタンス化、およびオブジェクトのライフサイクル(作成、再割り当てによる参照解除、ガベージ・コレクションなど)
* Javaクラスの定義
* オブジェクトのフィールドへの読み取りと書き込み
#### メソッドの作成と使用
* 引数や戻り値を持つメソッドとコンストラクタの作成
* メソッドのオーバーロードとメソッド呼び出し
* static変数とstaticメソッド
#### カプセル化の適用
* アクセス修飾子の使用
* クラスに対するカプセル化の適用
#### 継承による実装の再利用
* サブクラスとスーパークラスの作成と使用
* 抽象クラスの作成と継承
* メソッドのオーバーライドによるポリモーフィズム
* 参照型のキャストとポリモーフィックなメソッド呼び出し
* オーバーロード、オーバーライドおよび隠蔽の区別
#### インタフェースによる抽象化
* インタフェースの作成と実装
* 具象クラスの継承とインタフェース、抽象クラスの継承
* ListインタフェースとArrayListクラスの使用
* ラムダ式の理解
#### 例外処理
* 例外処理の仕組みとチェック例外、非チェック例外、エラーの違い
* try-catch文による例外処理
* 例外をスローするメソッドの作成と呼び出し
#### モジュール・システム
* モジュール型JDK
* モジュールの宣言とモジュール間のアクセス
* モジュール型プロジェクトのコンパイルと実行
#### Javaテクノロジに対する理解


### ポイント
    『Effective Java』、『レガシーコード改善ガイド』より
#### オブジェクト指向
* クラスの定義、インスタンス化
* 継承関係
#### 新機能
* ラムダ式
* モジュールシステム
* ローカル値型インターフェース
* Javaコマンドによるソースファイルの実行
#### パターン
##### staticファクトリメソッド
##### テレスコーピング・コンストラクタ・パターン
    順序に依存したパラメータを受けるコンストラクタ
##### JavaBeanパターン
#### 依存性の注入
#### try-with-resources
#### publicのアクセッサーメソッド
#### コンポジション
    既存クラスを拡張するのではなく、新たなクラスに既存のクラスのインスタンスをprivateフィールドで持たせ、既存クラスが新たなクラスの構成要素となる
#### タグ付きクラスよりもクラス階層を選ぶ
    特性が複数あるならばクラスを分けたほうがわかりやすい。継承、サブタイプ化をして階層構造で実装する。
#### APIの柔軟性向上のために境界ワイルドカードを使う
#### 無名クラスよりもラムダを選ぶ
#### ボクシングされた基本データよりも基本データ型を選ぶ
#### 回復可能な状態にはチェックされる例外を、プログラミングエラーには実行時例外を使う
##### 検査例外(チェックされる例外)
    プログラマが必ずtry/catchしなければならない例外
* FileNotFoundException
* IOException
* SQLException
##### 非検査例外(実行時例外)
    例外が発生する可能性はあるが、必ずしも例外処理を行う必要がない
* RuntimeException
* ArrayIndexOutOfBoundsException
* ClassCastException
* IllegalArgumentException
* NullPointerException
##### エラー
    Error系例外は回復不可能な重大なエラー
* OutOfMemoryError
* NoClassDefFoundError
#### チェックされる例外を不必要に使うのを避ける
#### エラーアトミック性に務める
    例外によってメソッドの呼び出しに失敗したあとに、オブジェクトがメソッドの呼び出し前の状態にしておくことをエラーアトミック性と言う
#### テスト駆動
#### スプラウトメソッドとラップメソッド
* スプラウトメソッド:既存のメソッド内に追加する新しいロジックをメソッドにする。
* ラップメソッド：既存のメソッドを同じメソッド名でラップして修正コードを付け加える。

### レガシーコード改善
#### 削除からはじめる
#### 小さく進める
#### リファクタリング
#### 命名
* 明確な単語を選ぶ
* 名前が「他の意味と間違えられることはないだろうか？」と自問自答する
* 一貫性のあるスタイルは「正しい」スタイルよりも大切
* コメントの目的は書き手の意図を読み手に知らせること
* コードからわかることを書かない
* コードを理解するのに役立つものを書く
#### テストを書く
#### 設計の改善


### Tips
* 重複排除
    - HashSetを使用する
* 文字列内の指定文字をカウント
* べき乗の計算
    - 基本は2重ループや再帰呼び出しだが、求めるものによって因数分解できないか検討する
* 10進数の変換
```java:
// 2進数
Integer.toBinaryString()
// 8進数
Integer.toOctalString()
// 16進数
Integer.toHexString()
```
* 文字列のパディング
```java:
String str = "123";
String paddingStr = str.format("%5s", str);
```
* 文字列を繰り返す方法
```java:
String.join("", Collections.nCopies(繰り返す回数, "繰り返したい文字列" )); 
```
* StringJoiner
```java:
    StringJoiner sj = new StringJoiner(",");
    Arrays.stream(arr).forEach(i -> sj.add(String.valueOf(i)));
```
