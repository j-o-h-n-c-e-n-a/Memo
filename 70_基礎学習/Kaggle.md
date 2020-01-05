## チュートリアル
### XGBoost Example
* https://github.com/awslabs/amazon-sagemaker-examples
### An Intoroduction to Ensembling/Stacking in Python
### AWS SageMaker
#### 1. S3バケットの作成
* バケットの指定
bucket = '-ml'
prefix = 'sagemaker/xxx_xgboost'
* IAMのRoleを宣言
import sagemaker
role = sagemaker.get_execution_role()
* 使用ライブラリのインポート
import numpy as np                                
import pandas as pd                               
import matplotlib.pyplot as plt   
from IPython.display import Image                 
from IPython.display import display               
from sklearn.datasets import dump_svmlight_file   
from time import gmtime, strftime                 
import sys                                        
import math                                       
import json
import boto3
* 使用データの宣言
+ KaggleからダウロードしたデータセットをS3のバケットへ格納
+ ファイル名を指定する
raw_data_filename = 'test.csv'
+ boto3経由でs3内に格納したデータをSageMakerのノートブックインスタンスへ移します
s3 = boto3.resource('s3')
s3.Bucket(bucket).download_file(raw_data_filename, 'raw_data.csv')
+ PandasのデータフレームへCSVファイルを変換
+ Pandasの行表示制限のオプション設定を変更
+ データを表示させる
data = pd.read_csv('./raw_data.csv')
pd.set_option('display.max_rows', 20)
data

#### 2. データ集計/整形
* 前処理
+ データ集計
+ 使用する特徴量の決定
  - 不要項目の除外
+ 欠損値
#### 3. 学習モデル作成/トレーニング
* コンテナ
+ AZを指定
+ S3とSageMakerは同じAZにて実行する必要がある
* 適切な学習用インスタンスを指定
#### 4. 学習済みモデルのデプロイ
* 適切なホスティング用インスタンスを指定
#### 5. 推論実行
#### 6. ハイパーパラメータチューニング

## 画像
    画像のデータセットは容量が大きく、機械学習も層の深いNNを利用するので計算量が多い。
    計算源としては、GPUを利用することが必須となる。
### 分類
### 識別
### 検出
### セグメンテーション
### GAN


## テキストデータ
    自然言語処理が題材となる。
### Bag of Words
### TF-IDF
### Word2Vec

## 解析
    最適なモデルを見つけるため、既存のモデルは一通り適用してみる。
    如何に漏れなくスムーズに回すかがポイント。
    このため各種適用手順をしっかりとマスターし、再現性も確保しておく。

## 環境づくり
### GCP

### AWS
#### SageMaker
### Git
### k8s

## コンペ
  過去のNotebookを確認する
* titanic
* games
* 

## リンク
### Kaggler
* [u++](https://upura.hatenablog.com/archive)
* https://qiita.com/upura/items/3c10ff6fed4e7c3d70f0
* https://www.st-hakky-blog.com/
### codexa
* [ml-dataset-list](https://www.codexa.net/ml-dataset-list/)
* [amazon-sagemaker-tutorial](https://www.codexa.net/amazon-sagemaker-tutorial-marketing-offers/)
* [amazon-sagamaker-xgboost](https://www.codexa.net/amazon-sagamaker-xgboost-game-sales-predictions/)
* [lightgbm](https://www.codexa.net/lightgbm-beginner/)
* [what-is-kaggle](https://www.codexa.net/what-is-kaggle/)
* [what-is-ensemble-learning](https://www.codexa.net/what-is-ensemble-learning/)
* []()
### ガイド
* [youtube解説](https://www.youtube.com/watch?v=NHQTw-ORcSQ&vl=ja)
* [wiki](https://kaggler-ja-wiki.herokuapp.com/kaggle初心者ガイド)
