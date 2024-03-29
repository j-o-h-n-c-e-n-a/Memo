## 入力
### input関数
	input()
* スペース区切りをリストに格納
```python:
input().split() 
```
* カンマ区切りをリストに格納
```python:
input().split(',') 
```
* 型変換して取得
```python:
map(int,input().split()) 
```
* 入力をリストに格納
```python:
list(input()) 
```
* 複数行を取得
```python:
[input() for i in range(int(input()))] 
```
* 単純にinput()するより早い
```python:（import sys が必要）
sys.stdin.readline
```
### コピー
* deepcopy:ディープコピー

## リストとタプル、ディクショナリ
	タプルはリストに比べて要素の入替ができない分、はやい
### list関数
* 要素をリスト化する
```python:
list()
```
### リスト内包表記
* Nは直前にinput()で取得
```python:
l = [input() for i in range(N)] 
```
* 10*10の2次元リストの生成
```python:
l = [[0] * 10 for i in range(10)]
```
### all()
	リスト要素が全て真であればTrueを返す
### any()
	リスト要素に一つでも真があればTrueを返す
### sorted()
### len()
### max()
### min()
### sum()
### reduce()：総積
### map()：一括変換
### filter：条件で絞り込む
### ディクショナリ
* dict(list)
* {キー:バリュー}
### セット
	インデクスをもたないデータの集まり。集合の考え方を使う。
	また、重複した要素は取り除かれる
* 和集合：set(a) | set(b), union
* 積集合：set(a) & set(b), interesction
* 差集合：set(a) - set(b), difference
* 排他的論理和集合：set(a) ^ set(b), symmetric_difference
* issu

## 制御構文
### 条件分岐
* if~else, elif
### ループ
* for i in range(x):
	- i:カウンタ（0スタート）
* for idx,elem in enumerate(a):
	- idx:カウンタ
	- elem:要素
	- reversed() でリストの逆順での取り出しも可能
* for i in range(x) if~:
	- 条件式の値を取得
* for-else, while-else
	- else節は一度もbreakされなかった場合に発生
* while(条件式):
* while(True):~if 条件式:break
### with文

## クラス
### コンストラクタ
	def __init__(self):
### デストラクタ
	def __del___():
### 基底クラス
### private要素
	__attr
### nonlocal変数
### コンテキストマネージャ
### クラスメソッド
```
class Users:
	def __init__(self):
	def method():
```
* メソッド呼び出し
	- Users.method()
### 抽象基底クラス
### 親クラス
	super

## 関数
### ジェネレータ関数
	イテレータを作る関数。next()を呼ばれたときに次の要素を探しにいく
### 関数デコレータ
### ドキュメンテーション文字列
### 関数アノテーション
### 特殊メソッド

## math
### 絶対値：abs()
### 商と余り：divmod()
### 乗算：pow()
### 四捨五入：round()
### 切り上げ：math.ceil()
### 切り捨て：math.floor()
### 階乗：math.factorial()
### 平方根：math.sqrt()
### 対数：math.log10()

## itertools
	組み合わせやデカルト積を求める場合に使用する
### count
	無条件のrange
### cycle
	無限ループ
### repeat 
	無限回繰り返し
### accumulate 
	累加関数
### chain 
	iterablesをまとめる
### compress 
	selectorsの評価値が真となるようなiterableの要素を取り出す
### dropwhile
	iterableの各要素に対して、predicateの評価値が偽になったら、その要素から、以降の要素を返すイテレータを作る（何かしらの条件を満たさない時点を探す）
### filterfalse
### groupby
### islice
	スライスの結果をイテレータとして返す
### starmap
### takewhile
### tee
### permutations
	順列を返すイテレータを作る
```
list(itertools.permutations([1, 2, 3])) # 3! 通り
```
### product
	直積を生成する
```
list(itertools.product([1, 2, 3], repeat=2)) # 3**2 通り
```
### combinations
	組み合わせを返すイテレータを作る
```
list(itertools.combinations([1, 2, 3, 4], 2)) # 4C2 通り 
```
### combinations_with_replacement
	3H3個
```
list(itertools.combinations_with_replacement([1, 2, 3], 3)) 
```

## collections
	リスト/文字列の要素数をカウントする
```python:サンプル
import collections
c = collections.Counter('abccbabcabcbaba')
mc = c.most_common()
mc[0] #最大
mc[-1] #最小
```

## 型変換
### int関数
* int("")
### str関数
* str(0)
* str.format()
* str.maketrans()
	+ 辞書を作る
* str.translate()
	+ 文字列を変換
```python:サンプル
s = 'abccba'
s.translate(str.maketrans('abc', '123'))  #'123321'
```
### map関数
* nums = map(int, input())
* strs = map(str, nums)

## 文字列
* 終端文字がとれる
```python:
'abcd123ef'[-1:]
```
* 最後の1文字以外のものがとれる
```python:
'abcd123ef'[:-1] 
```
* 文字が逆転する()
```python:
'abcd123ef'[::-1] 
```
* ２文字毎に出力(スライス)
```python:
'abcd123ef'[::2]
```
### len関数:文字数を取得
```
len("")
```
### join関数:文字列に連結
```
','.join(strs)
```
### ゼロ埋め・幅寄せ
* 左詰め
```python:
"STR".ljust(15, '') 
```
* 中央寄せ
```python:
"STR".center(15, '') 
```
* 右詰め
```python:
"STR".rjust(15, '') 
```
### 大文字・小文字
* upper
* lower
### ほか
* print('YNeos'[a::2])
* ord()
	+ 1文字の文字列をキャラクターコード（数値）に変換する。
* chr()
	+ キャラクターコード（数値）を1文字の文字列に変換する。

## 正規表現
```python:サンプル
import re
s='hoge6hoge21foo:bar'
re.findall(r'[a-z]+',s) #['hoge', 'hoge', 'foo', 'bar']
re.findall(r'[a-z0-9]+',s) #['hoge6hoge21foo', 'bar']
```
## 無名関数
	ラムダ式、lambda
### if文を使う
```
lambda x: 'even' if x % 2 == 0 else 'odd'
```
### sorted(), sort(), max(), min()の引数keyに使う
```
l_sorted_second = sorted(l, key=lambda x: x[1])
```
### map()やfilter()の第一引数に使う
```
map_square = map(lambda x: x**2, l)
```
### リストを使うときはリスト内包式の方が良い
```
l_square = [x**2 for x in l]
```

## Pythonライブラリ
### 標準ライブラリ
### 数値計算の基本になるライブラリ「Numpy／Scipy」
### 散布図、グラフ、ヒストグラムなどを描くためのライブラリ「Matplotlib」
### 実行結果を確認しながら実行できるWebエディタ「Jupyter Notebook」
### 大規模データ処理を高速に行えるライブラリ「Pandas」
### Pythonの標準的な機械学習ライブラリ「Scikit-learn」
### トピックモデルに特化している自然言語処理のライブラリ「Gensim」
### グーグルが開発したDeep Learning用エンジン／ライブラリ「TensorFlow」
### 数理最適化問題を簡単にコーディングできる「PuLP」
### ライブラリのインポート
```
import numpy as np
import numpy.random as random
import pandas as pd
from pandas import Series, DataFrame
import matplotlib.pyplot as plt
import matplotlib as mpl
import scipy as sp
import seaborn as sns
```

## 演習
1. ランダム関数で一様分布の標本を作る
2. １からランダムで標本平均を採って正規分布を作る
3. ２から標本平均を採ってt分布を作ったり、標本の2乗和からχ２乗分布を作る

## 参考サイト
* [『退屈なことはPythonにやらせよう』のリポジトリ](https://github.com/oreilly-japan/automatestuff-ja)
* [お気楽Pythonプログラミング入門](http://www.nct9.ne.jp/m_hiroi/light/index.html#python_abc)
* [Pythonライブラリ](http://www.atmarkit.co.jp/ait/articles/1611/24/news023.html)
* [京都大学](https://repository.kulib.kyoto-u.ac.jp/dspace/handle/2433/245698)

* http://cup.sakura.ne.jp/python_list.htm

* pyQ