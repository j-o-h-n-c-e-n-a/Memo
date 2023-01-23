## 1
### Q. 1
    あなたは、Docker for Windowsを参加者に紹介するためのハンズオンワークショップを開発しています。
    あなたは、ワークショップの参加者が自分のデバイスにDockerをインストールできることを保証する必要があります。
    参加者はどの2つの前提条件コンポーネントをデバイスにインストールする必要がありますか？各正解は、ソリューションの一部を提示します。
1. Microsoft Hardware-Assisted Virtualization detection Tool
2. Kiematic
3. BIOS-Enabeld virtualization
4. VirtualBox
5. Windows 10 64-bit Proffessional
<details><div>
    答え：3,5
    C: Windowsシステムがハードウェア仮想化技術に対応しており、仮想化が有効になっていることを確認する。
    E: Dockerを実行するには、お使いのマシンがWindows 7以上の64ビットオペレーティングシステムを搭載している必要があります。
</div></details>

### Q. 2
    あなたのチームは、データエンジニアリングとデータサイエンスの開発環境を構築しています。
    その環境は、以下の要件をサポートしている必要があります。
        PythonとScalaのサポート
        データの保存、移動、処理サービスを自動化されたデータパイプラインに構成する。
        データエンジニアリングとデータサイエンスの両方のオーケストレーションに同じツールを使用する必要があります。
        ワークロードの分離とインタラクティブなワークロードをサポートする。
        マシンのクラスタにまたがるスケーリングを可能にする
    環境を構築する必要があります。
    どうすればいいのでしょうか？
1. HDInsightはApache Hiveで環境を構築し、オーケストレーションはAzure Data Factoryを使用します。
2. Azure Databricksで環境を構築し、オーケストレーションにAzure Data Factoryを使用します。
3. Apache Spark for HDInsightで環境を構築し、オーケストレーションにAzure Container Instancesを使用します。
4. Azure Databricksで環境を構築し、オーケストレーションにAzure Container Instancesを使用します。
<details><div>
    答え：2
    Azure Databricksでは、2種類のクラスタを作成することができます。
    標準、これらはデフォルトのクラスタで、Python、R、Scala、SQLで使用できる。
    ハイコンカレンシー
        Azure Databricksは、Azure Data Factoryと完全に統合されています。
    不正解です。
        D：Azureコンテナインスタンスは、開発またはテストに適しています。本番ワークロードには適していません。
</div></details>

### Q. 3
    機械学習モデルを用いたインテリジェントなソリューションを構築するのです。
    その環境は、以下の要件をサポートしている必要があります。
        データサイエンティストは、クラウド環境でノートブックを構築しなければならない
        データサイエンティストは、機械学習パイプラインで自動フィーチャーエンジニアリングとモデル構築を使用する必要があります。
        ノートブックは、動的なワーカー割り当てを行うSparkインスタンスを使用して再トレーニングするためにデプロイされる必要があります。
        ノートブックは、ローカルでバージョン管理できるようにエクスポートできる必要があります。
    あなたは環境を作成する必要があります。
    どの4つのアクションを順番に実行する必要がありますか？回答するには、アクションのリストから適切なアクションを回答エリアに移動し、正しい順序でそれらを並べます。
1. Microsoft Machine Learning for Apache Sparkをインストールします。クラスタ上でZeppelin notebooksを作成し、実行します。クラスタの準備ができたら、Zeppelinノートブックをローカル環境にエクスポートします。Apache Spark MLlibライブラリを含めるために、Azure HDInsightクラスタを作成します。
2. Apache Spark MLlib ライブラリを含めるために、Azure HDInsight クラスターを作成します。
Microsoft Machine Leaarning for Apache Spark をインストールします。
クラスタ上でZeppelinノートブックを作成し、実行します。
クラスタの準備ができたら、Zepplin notebooksをローカル環境にエクスポートします。
3. クラスタ上でZeppelinノートブックを作成し、実行します。
クラスタの準備ができたら、Zepplinのノートブックをローカル環境にエクスポートします。
Apache Spark MLlib ライブラリを含めるために Azure HDInsight クラスターを作成します。
Microsoft Machine Leaarning for Apache Spark をインストールします。
<details><div>
    答え：2
    ステップ1：Apache Spark Mlibライブラリを含めるためにAzure HDInsightクラスタを作成します。
    ステップ2：Microsot Machine Learning for Apache Sparkをインストールする
              Azure HDInsight クラスターに AzureML をインストールします。
              Microsoft Machine Learning for Apache Spark（MMLSpark）は、Spark Machine LearningパイプラインをMicrosoft Cognitive Toolkit（CNTK）およびOpenCVとシームレスに統合するなど、Apache Spark向けに多数の深層学習およびデータサイエンスツールを提供し、大規模な画像およびテキストデータセットに対して強力かつ拡張性の高い予測モデルおよび分析モデルを迅速に作成することが可能です。
    ステップ3：クラスタ上でZeppelinノートブックを作成し、実行します。
    ステップ4: クラスターの準備ができたら、Zeppelinノートブックをローカル環境にエクスポートします。
               ノートブックは、ローカルでバージョン管理するためにエクスポート可能である必要があります。
</div></details>

### Q. 4
    チームでデータサイエンス環境を構築する予定の方。機械学習パイプラインでモデルを学習するためのデータは、20GB以上のサイズになる予定です。
    以下のような要件があります。
        モデルはCaffe2またはChainerフレームワークを使用して構築する必要があります。
        データサイエンティストは、データサイエンス環境を使用して、接続されたネットワーク環境と切断されたネットワーク環境の両方で、個人のデバイスで機械学習パイプラインの構築とモデルのトレーニングを行うことができる必要があります。
        個人所有のデバイスは、ネットワーク接続時に機械学習パイプラインの更新をサポートしている必要があります。
    データサイエンス環境を選択する必要があります。
    どの環境を使用する必要がありますか？
1. Azure Machine Learning Service
2. Azure Machine Learning Studio
3. Azure Databricks
4. Azure Kubernetes Service
<details><div>
    答え：1
    データサイエンスバーチャルマシン（DSVM）は、データサイエンスに特化したMicrosoft Azureクラウド上のカスタマイズされたVMイメージである。Caffe2とChainerはDSVMでサポートされています。
    DSVMは、Azure Machine Learningと統合されています。
    不正解です。
        B：機械学習モデルを迅速かつ容易に実験したい場合、機械学習スタジオを使用し、組み込みの機械学習アルゴリズムがあなたのソリューションに十分である。
</div></details>

### Q. 5
    あなたは、株価を予測するための機械学習モデルを実装しています。
    このモデルはPostgreSQLデータベースを使用し、GPU処理を必要とします。
    あなたは、必要なツールで事前に構成された仮想マシンを作成する必要があります。
    あなたは何をする必要がありますか？
1. Data Scienece Virtual Machine Window 版を作成します。
2. Geo AI Data Science Virtual Machine Window エディションを作成します。
3. Deep Learning Virtual Machine Linuxエディションの作成
4. ディープラーニング仮想マシンWindow版の作成。
<details><div>
    答え：1
    DSVMでは、学習モデルはGPU(Graphics Processing Unit)をベースとしたハードウェア上で深層学習アルゴリズムを使用することができます。
    PostgreSQLは、以下のOSで利用可能です。Linux（最近のすべてのディストリビューション）、macOS（OS X）バージョン10.6以降で利用可能な64ビットインストーラ - Windows（64ビット版で利用可能なインストーラ、最新バージョンとWindows 2012 R2に戻ってテストされています。
    不正解です。
        B: Azure Geo AI Data Science VM（Geo-DSVM）は、MicrosoftのData Science VMから地理空間分析機能を提供します。具体的には、このVMは、ESRIの市場をリードするArcGIS Pro地理情報システムを追加することにより、Data Science VMのAIおよびデータサイエンスツールキットを拡張します。
        C、D：DLVMは、DSVMイメージの上にテンプレートを乗せたもの。パッケージやGPUドライバなどは、すべてDSVMイメージの中に入っています。DLVMは、Azure上のGPU VMインスタンスにのみ作成することを許可しています。
</div></details>

### Q. 6
    あなたは、半構造化、非構造化、および構造化データ型を分析するためのディープラーニングモデルを開発しています。
    あなたは、モデル構築に利用できる以下のデータを持っています。
        スポーツイベントのビデオ録画
        イベントに関するラジオ解説のトランスクリプト
        スポーツイベント中に取得された、関連するソーシャルメディアフィードのログ
        モデルを作成するための環境を選択する必要があります。
    どの環境を使用する必要がありますか？
1. Azure Cognitive Service
2. Azure Data Lake Analytics
3. Azure HDInsight with Spark MLib
4. Azure Machine Learning Studio
<details><div>
    答え：1
    Azure Cognitive Servicesは、Microsoftの機械学習APIの進化したポートフォリオを拡張し、開発者が感情やビデオの検出、顔、音声、視覚認識、音声や言語の理解などの認知機能をアプリケーションに簡単に追加できるようにするものです。Azure Cognitive Servicesの目標は、開発者が見たり、聞いたり、話したり、理解したり、さらには推論を始めることができるアプリケーションを作成するのを支援することです。Azure Cognitive Services内のサービスカタログは、ビジョン、スピーチ、言語、検索、ナレッジの5つの主要な柱に分類されます。
</div></details>

### Q. 7
    Azure Machine Learningをサポートするためには、Azure Blob Storageにデータを保存する必要があります。
    あなたはAzure Blob Storageにデータを転送する必要があります。
    目標を達成するための3つの可能な方法は何ですか？各正解は完全な解決策を提示します。
    注：各正解の選択には1点の価値があります。
1. Bulk Insert SQL Query
2. AzCopy
3. Python script
4. Azure Storage Explorer
5. Bulk Copy Program
<details><div>
    答え：2,3,4,5
    Azure Blobストレージとの間で、さまざまなテクノロジーを使ってデータを移動することができます。
        Azureストレージエクスプローラー
        AzCopy
        Python
        SSIS
</div></details>

### Q. 8
    Azure Machine Learning StudioからWeka環境に大きなデータセットを移動します。
    あなたは、Weka環境用にデータをフォーマットする必要があります。
    どのモジュールを使用する必要がありますか？
1. Convert to CSV
2. Convert to Dataset
3. Convert to ARFF
4. Convert to SVMLight
<details><div>
    答え：3
    Azure Machine Learning StudioのConvert to ARFFモジュールを使用して、Azure Machine Learningのデータセットと結果を、Wekaツールセットで使用される属性-関連ファイル形式に変換します。このフォーマットは、ARFFとして知られています。
    WekaのARFFデータ仕様は、データの前処理、分類、特徴選択など、複数の機械学習タスクをサポートしています。このフォーマットでは、データはエントリとその属性によって整理され、1つのテキストファイルに収められています。
</div></details>

### Q. 9
    あなたは音声認識ディープラーニングモデルを作成する予定です。
    このモデルは、最新バージョンのPythonをサポートする必要があります。
    データサイエンスバーチャルマシン（DSVM）に含める音声認識用の深層学習フレームワークを推奨する必要があります。
    何を推奨すべきですか？
1. Rattle
2. Tensorflow
3. Weka
4. scilit-learn
<details><div>
    答え：2
    TensorFlowは、数値計算と大規模な機械学習のためのオープンソースライブラリです。Pythonを使用し、フレームワークを使ったアプリケーションを構築するための便利なフロントエンドAPIを提供します。
    TensorFlowは、手書きの数字分類、画像認識、単語埋め込み、リカレントニューラルネットワーク、機械翻訳のための配列間モデル、自然言語処理、PDE（偏微分方程式）ベースのシミュレーションのための深いニューラルネットワークを訓練して実行することができます。
    不正解です。
        A：Rattleは、データ解析と機械学習を始めるためのR分析ツールです。
        C：Wekaは、Javaによるビジュアルデータマイニングや機械学習ソフトウェアとして使用されています。
        D：Scikit-learnは、Pythonで機械学習を行うための最も便利なライブラリの1つです。このライブラリは、NumPy、SciPy、matplotlib上にあり、分類、回帰、クラスタリング、次元削減を含む機械学習と統計モデリングのための多くの効果的なツールを含んでいます。
</div></details>

### Q. 10
    あなたは、Compute Unified Device Architecture（CUDA）計算を使用して深層学習モデルを訓練するために、深層学習仮想マシン（DLVM）を使用することを計画しています。
    あなたは、CUDAをサポートするためにDLVMを構成する必要があります。
    あなたは何を実装する必要がありますか？
1. Solid State Drive
2. Computer Processing Unit speed increase by using overclocking
3. Graphic Processing Unit
4. High Random Access Memory cinfiguration
5. Intel software Guard Extensins technology
<details><div>
    答え：3
    Deep Learning Virtual Machineは、GPUインスタンスを用いたディープラーニングのための事前設定された環境です。
</div></details>

### Q. 11
    オープンソースの深層学習フレームワークであるCaffe2とPyTorchでデータサイエンスバーチャルマシン（DSVM）を使用する予定があります。
    フレームワークをサポートするために、事前に設定されたDSVMを選択する必要があります。
    何を作成する必要がありますか？
1. DataScience Virtual Machine for windows 2012
2. DataScience Virtual Machine for Linux(Cent OS)
3. Geo AI DataScience Virtual Machine with ArcGIS
4. DataScience Virtual Machine for windows 2016
5. DataScience Virtual Machine for Linux(Ubuntu)
<details><div>
    答え：5
    Caffe2、PyTorchはData Science Virtual Machine for Linuxでサポートされています。
    Microsoftは、DSVMのLinux版として、Ubuntu 16.04 LTSとCentOS 7.4を提供しています。
    UbuntuのDSVMのみ、Caffe2とPyTorch用に事前に設定されています。
    不正解です。
        D：Caffe2とPytOCHは、Linux用のData Science Virtual Machineでのみサポートされています。
</div></details>

### Q. 12
    Azure Machine Learning サービスを使用するデータサイエンスワークスペースを開発中です。
    あなたは、ワークスペースをデプロイするために計算ターゲットを選択する必要があります。
    何を使用する必要がありますか？
1. Azure Data Lake Analytics
2. Azure Databricks
3. Azure Container Service
4. Apache Spark for HDInsight
<details><div>
    答え：2
    Azure Container Instancesは、テストや開発用のコンピュートターゲットとして使用できます。48GB以下のRAMを必要とする、CPUベースの低スケールなワークロードに使用します。
</div></details>

### Q. 13
    あなたは分類タスクを解いています。
    データセットはアンバランスです。
    あなたは、分類の精度を向上させるためにAzure Machine Learning Studioのモジュールを選択する必要があります。
    あなたはどのモジュールを使用する必要がありますか？
1. 順列特徴重要度
2. フィルタベースの特徴選択
3. フィッシャー線形識別分析
4. 合成少数点オーバーサンプリング法（SMOTE）
<details><div>
    答え：4
    Azure Machine Learning Studio (classic)のSMOTEモジュールを使用して、機械学習に使用するデータセット内の未提示のケースを増やします。SMOTEは、既存のケースを単純に複製するよりも、レアケースの数を増やすのに適した方法です。
    SMOTEモジュールをアンバランスなデータセットに接続する。データセットがアンバランスになる理由は様々です。対象とするカテゴリが母集団の中で非常に稀であったり、単にデータの収集が困難であったりします。一般的には、分析したいクラスが十分に表現されていない場合に、SMOTEを使用します。
</div></details>

### Q. 14
    あなたは、Windows用のDeep Learning仮想マシンを構成します。
    以下を実行するために、ツールやフレームワークを推奨する必要があります。
        ディープニューラルネットワーク(DNN)モデルの構築
        インタラクティブなデータ探索と可視化の実行
    どのツールとフレームワークを推奨する必要がありますか？回答するには、適切なツールを正しいタスクにドラッグします。各ツールは、1回、2回以上、または全く使用されないかもしれません。ペイン間の分割バーをドラッグしたり、コンテンツを表示するためにスクロールする必要がある場合があります。
1. Task, Build DNN model, Tool, Vowpal Wabbit
2. Task, Build DNN model, Tool, PowerBI Desktop
3. Task, Enable interactive data exploration and visualization, Tool, PowerBI Desktop
4. Task, Enable interactive data exploration and visualization, Tool, Microsoft Cognitive Toolkit
<details><div>
    答え：1,3
ボックス1：Vowpal Wabbit
    Azure Machine Learning Studio（クラシック）のTrain Vowpal Wabbit Version 8モジュールを使用し、Vowpal Wabbitを使用して機械学習モデルを作成します。
ボックス2：PowerBIデスクトップ
    Power BI Desktopは、強力なビジュアルデータ探索とインタラクティブなレポート作成ツールです
    BIは、ユーザーが企業全体のデータから洞察を見つけ、探索し、共有することを可能にする、ビジネス意思決定のための現代的なアプローチに与えられた名前です。
</div></details>

### Q. 15
    あなたは、地元のタクシー会社からの履歴データを含むデータセットを分析しています。あなたは、回帰モデルを開発しています。
    あなたは、タクシー旅行の運賃を予測しなければなりません。
    あなたは、回帰モデルを正しく評価するために、パフォーマンス測定基準を選択する必要があります。
    あなたはどの 2 つのメトリックを使用できますか? 各正解は完全な解答を提示しますか?
1. 二乗平均平方根誤差の値が小さい
2. R-sared値が0に近い
3. f1スコアが低い
4. R-suaredの値が1に近い 
5. f1スコアが高い
6. 二乗平均平方根誤差が大きい
<details><div>
    答え：1,4
    RMSEとR2は、どちらも回帰モデルの指標です。
    A: RMSE（Root mean squared error）は、モデルの誤差を要約した単一の値を作成します。差を2乗することで、この指標は過剰予測と過小予測の差を無視する。
    D: 決定係数、しばしばR2と呼ばれ、モデルの予測力を0と1の間の値で表します。0はモデルがランダムであること（何も説明しない）、1は完全に適合していることを意味します。しかし、R2 値の解釈には注意が必要です。低い値は完全に正常であり、高い値は疑わしい可能性があるからです。
    不正解。
        C, E: Fスコアは分類モデルに使用され、回帰モデルには使用されません。
</div></details>

### Q. 16
    Azure Machine Learning を使用して、分類モデルをトレーニングする実験を実行します。
    Hyperdrive を使用して、モデルの AUC メトリクスを最適化するパラメータを見つけたいとします。次のコードを実行して、実験用のHyperDriveConfigを構成します。

    この設定を使用して、ランダムフォレストモデルをトレーニングし、検証データでそれをテストするスクリプトを実行する予定です。検証データのラベル値はy_test変数という変数に格納され、モデルから予測される確率はy_predictedという変数に格納されます。
    HyperdriveがAUCメトリックのハイパーパラメータを最適化できるようにするために、スクリプトにロギングを追加する必要があります。
    解決策 次のコードを実行します。
        logging.info("メッセージ")
    解決策は目標を達成しましたか?
1. はい
2. いいえ
<details><div>
    答え：1
    Pythonの印刷/ログの例です。
    logging.info(メッセージ)
    出力先 ドライバログ、Azure Machine Learning デザイナー
</div></details>

### Q. 17
    Azure Machine Learning を使用して、分類モデルをトレーニングする実験を実行します。
    Hyperdrive を使用して、モデルの AUC メトリクスを最適化するパラメータを見つけたいとします。次のコードを実行して、実験用のHyperDriveConfigを構成します。


    この設定を使用して、ランダムフォレストモデルをトレーニングし、検証データでそれをテストするスクリプトを実行する予定です。検証データのラベル値はy_test変数という変数に格納され、モデルから予測される確率はy_predictedという変数に格納されます。
    HyperdriveがAUCメトリックのハイパーパラメータを最適化できるようにするために、スクリプトにロギングを追加する必要があります。
    解決策 次のコードを実行します。

    解決策は目標を達成しましたか?
1. はい
2. いいえ
<details><div>
    答え：2
    代わりに logging.info(message) を使った解決策を使用します。
    注：Pythonの印刷/ログの例です。
    logging.info(メッセージ)
    宛先は ドライバログ、Azure Machine Learning デザイナー
</div></details>

### Q. 18
    Azure Machine Learning を使用して、分類モデルをトレーニングする実験を実行します。
    Hyperdrive を使用して、モデルの AUC メトリクスを最適化するパラメータを見つけたいとします。次のコードを実行して、実験用のHyperDriveConfigを構成します。

    この設定を使用して、ランダムフォレストモデルをトレーニングし、検証データでそれをテストするスクリプトを実行する予定です。検証データのラベル値はy_test変数という変数に格納され、モデルから予測される確率はy_predictedという変数に格納されます。
    HyperdriveがAUCメトリックのハイパーパラメータを最適化できるようにするために、スクリプトにロギングを追加する必要があります。
    解決策 次のコードを実行します。

    解決策は目標を達成しましたか?
1. はい
2. いいえ
<details><div>
    答え：2
    代わりに logging.info(message) を使った解決策を使用します。
    注：Pythonの印刷/ログの例です。
    logging.info(メッセージ)
    宛先は ドライバログ、Azure Machine Learning デザイナー
</div></details>

### Q. 19
    財務チームから、finance-dataという名前のAzure Storage blobコンテナ内のデータを使用してモデルをトレーニングするように依頼されました。
    あなたは、Azure Machine Learningワークスペースのデータストアとしてコンテナを登録し、コンテナが存在しない場合にエラーが発生することを確認する必要があります。
    どのようにコードを完成させるべきですか？回答するには、回答領域で適切なオプションを選択します。
    OPTION:A
        datastore = Datastore.[register_azure_blob_container](
            workspace = ws,
            datastore_name = '',
            container_name = '',
            account_name = '',
            account_key = '',
            [create_if_not_exists = False]
        )
    OPTION:B

1. A
2. B
<details><div>
    答え：1
ボックス1：register_azure_blob_container
    データストアにAzure Blob Containerを登録します。
ボックス 2: create_if_not_exists = False
    ファイル共有が存在しない場合に作成します。デフォルトはFalseです。
</div></details>

### Q. 20
    データサイエンス プロジェクトのために、Azure Machine Learning Basic エディションのワークスペースをプロビジョニングすることを計画しています。
    あなたは、ワークスペースで実行できるタスクを特定する必要があります。
    あなたはどの3つのタスクを実行することができますか？各正解は完全な解決策を提示します。
1. コンピュートインスタンスを作成し、それを使ってjupyter notebooksでコードを実行する。
2. Azure Kubernetesサービス推論クラスタを作成する
3. デザイナーを使用して、定義済みのモジュールをドラッグ＆ドロップしてモデルをトレーニングする
4. バージョン管理をサポートする表形式データセットを作成する
5. 自動化された機械学習のユーザーインターフェイスを使用して、モデルをトレーニングする
<details><div>
    答え：1,2,4
    C, E: UIはEnterprise版のみに搭載されています。
</div></details>

### Q. 21
    同僚が以下のコードを使用して、Machine Learningサービスのワークスペースにデータストアを登録しました。

    あなたはノートブックからデータストアにアクセスするコードを記述する必要があります。
    あなたはどのようにコードセグメントを完了する必要がありますか？回答するには、回答領域で適切な選択肢を選択します。
    OPTION:A

    OPTION:B
        import azireml.core
        from azureml.core import Workspace,Datastore
        ws = Workspace.from_config()
        datastore = [Datastore].get([ws], '[demo_datastore]')
1. A
2. B
<details><div>
    答え：2
ボックス1：データストア
    現在のワークスペースに登録されている特定のデータストアを取得するには、Datastoreクラスのget()静的メソッドを使用します。
    * 現在のワークスペースからデータストアを取得する。
    datastore = Datastore.get(ws, datastore_name='your datastore name')
ボックス2: ws
ボックス3: demo_datastore
</div></details>

### Q. 22
    一組のCSVファイルには、売上記録が含まれています。すべての CSV ファイルは、同じデータスキーマを持っています。
    各CSVファイルは、特定の月の売上記録を含み、sales.csvというファイル名を持っています。各ファイルは、データが記録された月と年を示すフォルダに格納されています。フォルダは、Azure Machine Learning ワークスペースにデータストアが定義されている Azure blob コンテナ内にある。フォルダは、sales という名前の親フォルダで整理され、次のような階層構造になっています。


    各月末に、その月の売上ファイルを含む新しいフォルダが sales フォルダに追加されます。
    あなたは、次の要件に基づいて、販売データを使用して機械学習モデルを訓練することを計画しています。
    これまでのすべての売上データを、データフレームに簡単に変換できる構造にロードするデータセットを定義する必要があります。
    特定の前月以前に作成されたデータのみを使用し、その月以降に追加されたデータを無視する実験を作成できること。
    登録できるデータセットの数は最小限でなければならない。
    Azure Machine Learning サービスのワークスペースに、売上データをデータセットとして登録する必要があります。
    どうすればいいのでしょうか？
1. データソースを参照し、毎月「sales/mm-yyyy/sales.csv」ファイルを指定する表形式のデータセットを作成し、毎月sales_datasetという名前でデータセットを登録し、既存のデータセットを置き換えて登録した月と年を示すmonthというタグを付ける。
2. データストアを参照し、パス 'sales/*/sales.csv' を指定した表形式のデータセットを作成し、sales_dataset という名前と、登録した年月を示す month というタグをつけて登録し、このデータセットを全ての実験に使用する。
3. データストアを参照する表形式のデータセットを新規に作成し、毎月の 'sales/mm-yyyy/sales.csv' ファイルを明示的に指定する。このデータセットを毎月 sales_dataset_MM-YYYY という名前で、月と年を MM と YYYY で適切に登録し、実験にはその月特有のデータセットを使用する。
4. このデータセットを参照し、毎月「sales/mm-yyyy/sales.csv」ファイルを指定する表形式データセットを作成する。
このデータセットを、毎月新しいバージョンとして sales_dataset という名前で登録し、登録した年月を示す month というタグを付ける。
このデータセットをすべての実験に使用し、必要に応じてmonthタグを元に使用するバージョンを特定する。
<details><div>
    答え：2
    パスを指定します。
例
    次のコードでは、既存のワークスペースと目的のデータストアを名前で取得します。そして、データストアとファイルの場所をpathパラメータに渡して、新しいTabularDatasetであるweather_dsを作成します。
        from azureml.core import Workspace, Datastore, Dataset
        datastore_name = 'あなたのデータストア名'
* 既存のワークスペースを取得
    workspace = Workspace.from_config()
* 名前でワークスペース内の既存のデータストアを取得する
    datastore = Datastore.get(workspace, datastore_name)
* データストアにある3つのファイルパスから TabularDataset を作成する。
    datastore_paths = [(datastore, 'weather/2018/11.csv'),
                   (datastore, 'weather/2018/12.csv'),
                   (データストア, 'weather/2019/*.csv')]とする。
    weather_ds = Dataset.Tabular.from_delimited_files(path=datastore_paths)
</div></details>

### Q. 23
    ある組織がAzure Machine Learningサービスを使用しており、機械学習の利用を拡大したいと考えています。
    次のコンピュート環境があります。組織は、別のコンピュート環境を作成することを望んでいません。
        nb_server: Compute Instance
        aks_cluster: Azure Kubernetes Service
        mlc_cluster: Machine Learning Compute
    あなたは、次のシナリオのためにどのコンピュート環境を使用するかを決定する必要があります。
    どのコンピュートタイプを使用する必要がありますか？答えとしては、適切な計算環境を適切なシナリオにドラッグしてください。各コンピュート環境は、1回だけ使うことも、2回以上使うことも、全く使わないこともできます。ペイン間でスプリットバーをドラッグしたり、コンテンツを表示するためにスクロールする必要がある場合があります。
1. シナリオ：azure機械学習デザイナーのトレーニングパイプラインを実行します。環境：nb_server
2. シナリオ：azure機械学習デザイナーのトレーニングパイプラインを実行します。環境：mlc_cluster
3. シナリオ：azure機械学習デザイナーからWebサービスをデプロイする。環境：mlc_cluster
4. シナリオ：azure機械学習デザイナーからWebサービスをデプロイする。環境：adks_cluster
<details><div>
    答え：1,3
    Azure Machine Learningでは、コンピュートターゲットと総称されるさまざまなリソースや環境でモデルを学習させることができます。コンピュートターゲットは、ローカルマシン、またはAzure Machine Learning Compute、Azure HDInsight、リモート仮想マシンなどのクラウドリソースにすることができます。
</div></details>

### Q. 24
    STANDARD_D1仮想マシンイメージを使用して、ComputeOneというAzure Machine Learningコンピュートターゲットを作成します。
    Azure Machine Learningのワークスペースを参照するwasというPython変数を定義する。以下のPythonコードを実行する。
        from azureml.core.compute import ComputeTarget, AmlCompute
        from azureml.core.compute_target import ComputeTargetException
        the_cluster_name = "ComputeOne"
        try:
            the_cluster = ComputeTarget(workspace=ws, name=the_cluster_name)
            print('Step1')
        except ComputeTargetException:
            config = AmlCompute.provisioning_configuration(vm_size='STANDARD_DS12_V2', max_nodes=4)
            the_cluster = ComputeTarget.create(ws, the_cluster, config)
            print('Step2')
    次の各ステートメントについて、そのステートメントが真である場合は、[はい]を選択します。そうでない場合は、[いいえ]を選択します。
1. 新しい機械学習用コンピューターリソースが作成され、仮想マシンのサイズは standard_ds12_v2 で、最大 4 ノードが使用できます。
2. 新しい機械学習用コンピューターリソースが作成され、仮想マシンのサイズは standard_ds12_v2 で、最大 4 ノードが使用できません。
3. クラスタを使用するように設定された実験は、コンピュータ1上で実行されます。
4. クラスタを使用するように設定された実験は、コンピュータ1上で実行されません。
5. ステップ1の文字が画面に表示されます。
6. ステップ1の文字が画面に表示されません。
<details><div>
    答え：1,3,6
ボックス1：あり
    ComputeTargetExceptionクラス。コンピュート・ターゲットの作成、操作、または設定時の失敗に関連する例外です。この例外は、コンピュート・ターゲットのアタッチに失敗した場合、ヘッダが見つからない場合、およびサポートされていないコンフィギュレーション値の場合によく発生します。
    Create(workspace, name, provisioning_configuration)   
    コンピュートタイプおよび関連するコンフィギュレーションを指定して、コンピュートオブジェクトをプロビジョニングします。
    このメソッドは、既存のものをアタッチするのではなく、新しいコンピュートターゲットを作成します。
ボックス2: はい
ボックス3: No
    print('Step1')の前の行は、失敗します。
</div></details>

### Q. 25
    あなたは、TensorFlowを使用して深層学習モデルを開発しています。あなたは、Azure Machine Learning Compute Instance上でモデルトレーニングワークロードを実行することを計画しています。
        あなたは、CUDAベースのモデルトレーニングを使用する必要があります。
        あなたは、Compute Instanceをプロビジョニングする必要があります。
    どの2つの仮想マシンサイズを使用することができますか？回答するには、回答領域で適切な仮想マシンのサイズを選択します。
    OPTION:A
        GPU なし
    OPTION:B
        GPU あり
1. A
2. B
<details><div>
    答え：2
    CUDAは、Nvidiaが自社のGPU（グラフィックス・プロセッシング・ユニット）上で一般的な計算を行うために開発した並列計算プラットフォームおよびプログラミングモデルである。CUDAは、開発者が計算の並列化可能な部分にGPUのパワーを利用することで、計算集約型のアプリケーションを高速化することを可能にします。
</div></details>

### Q. 26
    次のコードを使用して、Azure Machine Learning で実験としてスクリプトを実行します。


    実験の実行によって生成される出力ファイルを特定する必要があります。
    あなたは、出力ファイル名を取得するためのコードを追加する必要があります。
    どのコードセグメントをスクリプトに追加する必要がありますか？
1. files = run.get_properties()
2. files = run.get_file_names()
3. files = run.get_details_with_logs()
4. files = run.get_metrics()
5. files = run.get_details()
<details><div>
    答え：2
    run.get_file_names() を呼び出すと、このランレコードに関連するすべてのファイルを一覧表示することができます。
</div></details>

### Q. 27
    あなたは、別紙Aで指定された順序で処理されなければならない5つのPythonスクリプトを書きます - これは、同じモジュールを並行して実行することができますが、依存関係のあるモジュールを待つことになります。
    あなたは、Python SDKを使用してAzure Machine Learningパイプラインを作成する必要があり、パイプラインを作成するスクリプトは、バージョン管理システムで追跡されるようにしたいからです。5 つの PythonScriptSteps を作成し、モジュール名と一致するように変数に名前を付けました。

    あなたは、示されたパイプラインを作成する必要があります。すべての関連するインポートが行われたと仮定してください。
    どのPythonコードセグメントを使うべきですか？
    OPTION:A
        p = Pipeline(ws, steps=[[[[step_1_a, step_1_b], step_2_a], step_2_b], step3])
    OPTION:B

1. A
2. B
<details><div>
    答え：1
    steps パラメータには、ステップの配列を指定します。複数のステップを持つパイプラインを構築するには、この配列にステップを順番に並べます。
</div></details>

### Q. 28
    Azure ML SDKを使った実験の準備中で、computeを作成する必要があります。次のコードを実行します。
        from azureml.core.compute import ComputeTarget, AmlCompute
        from azureml.core.compute_target import ComputeTargetException
        ws = Workspace.from_config()
        cluster_name = 'aml-cluster'
        try:
            training_compute = ComputeTarget(workspace=ws, name=cluster_name)
        except ComputeTargetException:
            compute_config = AmlCompute.provisioning_configuration(vm_size='STANDARD_D2_V2', vm_priority='lowpriority', max_nodes=4)
            training_compute = ComputeTarget.create(ws, cluster_name, compute_config)
            trainnig_compute.wait_for_completion(show_output=True)

    以下の各ステートメントについて、そのステートメントが真である場合は、Yes を選択します。そうでない場合は、「いいえ」を選択します。
1. ワークスペースにaml-clusterという名前のトレーニングクラスタが既に存在する場合、それは削除され置き換えられます。
2. ワークスペースにaml-clusterという名前のトレーニングクラスタが既に存在する場合、それは削除され置き換えられません。
3. wit_for_completion()メソッドは、aml-cluster computeが4つのアクティブノードを持つまで再開されません。
4. wit_for_completion()メソッドは、aml-cluster computeが4つのアクティブノードを持つまで再開されます。
5. このコードが新しいaml-clusterコンピュータターゲットを作成する場合、容量の制約のために先制されることがあります。
6. このコードが新しいaml-clusterコンピュータターゲットを作成する場合、容量の制約のために先制されることがありません。
7. 学習実験終了後、aml-cluster computer targetはワークスペースから削除されます。
8. 学習実験終了後、aml-cluster computer targetはワークスペースから削除されません。
<details><div>
    答え：2,3,5,8
ボックス1：なし
    トレーニングクラスターが既に存在する場合は、それを使用する。
ボックス2: Yes
    wait_for_completionメソッドは、クラスタ上で現在のプロビジョニング操作が終了するのを待ちます。
ボックス3: はい
    低優先度VMは、Azureの余剰能力を使用するため、安価ですが、実行が先取りされるリスクがあります。
ボックス4: いいえ
    training_compute.delete()を使って、AmlComputeターゲットをデプロビジョニングして削除する必要があります。
</div></details>

### Q. 29
    Azure Storage アカウントの blob コンテナを参照する training_data という名前のデータストアを作成します。blobコンテナには、複数のカンマ区切り値（CSV）ファイルが格納されているcsv_filesというフォルダが含まれています。
    ./scriptというローカルフォルダにtrain.pyというスクリプトがあり、推定値を使用した実験として実行する予定です。このスクリプトには、csv_filesフォルダからデータを読み込むための次のコードが含まれています。


    次のようなスクリプトがあります。


    このスクリプトでは、training_dataデータストアにあるcsv_filesフォルダを参照するdata_refというデータ参照からデータを読み込むように、実験用のestimatorを構成する必要があります。
    推定器を設定するために、どのコードを使用すべきか。
    OPTION:A
        script_params = {
            '--data-folder': [data_ref.as_mount()]
        }
        estimator = SKLearn(source_directory='./script',
        script_params=script_params,
        compute_target='local',
        entry_script='train.py')
    OPTION:B
1. A
2. B
<details><div>
    答え：1
        データセットは estimator の inputs パラメータで渡す以外に、 script_params で渡し、引数で学習スクリプトのデータパス（マウントポイント）を取得することができる。こうすることで、学習用スクリプトをazureml-sdkに依存しないものにすることができます。つまり、どのクラウドプラットフォームでも、ローカルデバッグとリモートトレーニングに同じトレーニングスクリプトを使用することができるようになります。
</div></details>

### Q. 30
    PyTorchフレームワークを使用して、マルチクラス画像分類のディープラーニング実験を作成します。あなたは、GPUを備えたノードを持つAzure Computeクラスタ上で実験を実行することを計画しています。
    あなたは、画像分類モデルの毎月の再トレーニングを実行するために、Azure Machine Learningサービスパイプラインを定義する必要があります。パイプラインは、最小限のコストで実行され、モデルのトレーニングに必要な時間を最小限に抑える必要があります。
    どの3つのパイプラインステップを順番に実行する必要がありますか？回答するには、アクションのリストから適切なアクションを回答領域に移動し、それらを正しい順序で並べます。
1. 実行する pythonscriptstep() を設定する。
image_resize.pyを実行するように設定します。
bird_classifier_train.pyを実行するestimatorをgpu_computeターゲットで実行するようestimatorstep()を設定します。
datransferstep()を設定し、cpu_computeターゲットで動作するパブリックWebポータルから新しい画像データを取得する。
2. 新しいイメージを取得するためのデータ転送ステップを設定する。
公開ポータルからデータを取得し、cpu-computeコンピュートターゲットで実行する。
Pythonscriptstep() を構成し、以下の処理を実行します。
image_resize.pyをcpu-computeコンピュート・ターゲット上で実行するようにpythonscriptstep()を設定します。
bird_classifire_train.pyを実行するestimatorをgpu_computeターゲットで実行するようestimatorstep()を設定します。
<details><div>
    答え：2
Step 1: DataTransferStep()を構成して、新しい画像データをフェッチする...
Step 2: cpu-compute計算機上でimage_resize.yを実行するようにPythonScriptStep()を設定します。
Step 3: EstimatorStep()を構成し、gpu_computeの計算機ターゲットで学習スクリプトを実行します。
    PyTorch estimatorは、計算機ターゲット上でPyTorchのトレーニングジョブを起動する簡単な方法を提供します。
</div></details>

### Q. 31
    あなたは、鳥の健康と移動を追跡するプロジェクトのリードデータサイエンティストです。あなたは、専門家が収集したラベル付きの鳥の写真のセットを使用する、複数画像の分類ディープラーニングモデルを作成します。あなたは、このモデルを使用して、アプリのユーザーが捕獲した鳥の種類を予測するクロスプラットフォームのモバイルアプリを開発することを計画しています。
    あなたは、学習したモデルをWebサービスとしてテストし、デプロイする必要があります。デプロイされたモデルは、以下の要件を満たしている必要があります。
        テストには、認証された接続が必要であってはなりません。
        デプロイされたモデルは、推論時に低レイテンシーで実行される必要があります。
        RESTエンドポイントはスケーラブルであり、複数のエンドユーザーがモバイルアプリケーションを使用する場合に、大量のリクエストを処理する能力を備えている必要があります。
        有効な REST リクエストが送信されたときに、Web サービスが期待される JSON 形式で予測値を返すことを確認する必要があります。
    どの計算リソースを使用する必要がありますか？回答するには、回答領域で適切なオプションを選択してください。
1. Context, Test, Resource, ds-workstation notebook VM
2. Context, Test, Resource, gpu-compute cluster
3. Context, Test, Prduction, gpu-compute cluster
4. Context, Test, Prduction, ds-workstation notebook VM
<details><div>
    答え：1,3
Box 1: ds-workstation ノートブック型VM
    認証された接続は、テストに必要ないこと。
    データサイエンス仮想マシン（DSVM）を含むMicrosoft Azureの仮想マシン（VM）では、VMのプロビジョニング中にローカルユーザーアカウントを作成します。その後、ユーザーはこれらの資格情報を使用してVMに認証します。
Box 2: GPU計算機クラスタ
    画像分類はGPUコンピュートクラスタに適している
</div></details>

### Q. 32
    あなたは、GPUベースのトレーニングを使用して、Azure Machine Learningサービス上で画像認識のための深層学習モデルを作成します。
    あなたは、リアルタイムでGPUベースの推論を可能にするコンテキストにモデルをデプロイする必要があります。
    あなたは、モデルの推論のための計算機リソースを構成する必要があります。
    どのコンピュートタイプを使用する必要がありますか？
1. Azure Container Instance
2. Azure Kubernetes Service
3. Field Programmable Gate Array
4. Machine Learining Compute
<details><div>
    答え：2
    Azure Machine Learningを使って、GPU対応モデルをWebサービスとしてデプロイすることができます。Azure Kubernetes Service（AKS）上にモデルをデプロイすることも選択肢の一つです。AKSクラスタは、推論にモデルが使用するGPUリソースを提供します。
    推論、またはモデルのスコアリングは、デプロイされたモデルが予測を行うために使用されるフェーズです。CPUの代わりにGPUを使用することで、高度に並列化可能な計算においてパフォーマンス上の利点が得られます。
</div></details>

### Q. 33
    Azure ML SDKを使用して、バッチ推論パイプラインを作成します。パイプラインの実行は、以下のコードで行います。

        from azureml.pipeline.core import Pipeline
        from azureml.core.experiment import Experiment
        pipeline = Pipeline(workspace=ws, steps=[parallelrun_step])
        pipeline_run = Experiment(ws, 'batch_pipeline').submit(pipeline)

    パイプラインの実行状況を監視する必要があります。
    この目標を達成するために可能な2つの方法は何ですか？各正解は完全な解決策を提示します。
    OPTION:A


    OPTION:B


    OPTION:C
        Machine Learning StudioのInference Clustersタブを使用する。

    OPTION:D
        機械学習ワークスペースのAzureポータルのアクティビティログを使用する。
1. A
2. B
3. C
<details><div>
    答え：1,2
    バッチ推論ジョブは終了までに長い時間がかかることがあります。この例では、Jupyterのウィジェットを使って進捗を監視しています。また、ジョブの進捗を管理することもできます。
    Azure Machine Learning Studioを使用してジョブの進捗を管理することもできます。
    PipelineRunオブジェクトからのコンソール出力。
        from azureml.widgets import RunDetails
        RunDetails(pipeline_run).show()
        pipeline_run.wait_for_completion(show_output=True)を実行します。
</div></details>

### Q. 34
    Azure Machine Learningワークスペースにモデルをトレーニングして登録します。
    クライアントアプリケーションがバッチ推論にモデルを使用できるように、パイプラインを公開する必要があります。入力データから予測を得るために Python 推論スクリプトを実行する、単一の ParallelRunStep ステップを持つパイプラインを使用する必要があります。
    ParallelRunStepパイプライン・ステップの推論スクリプトを作成する必要があります。
    あなたはどの2つの関数を含めるべきですか？各正解は、ソリューションの一部を提示します。
1. run(mini_batch)
2. main()
3. batch()
4. init()
5. score(mini_batch)
<details><div>
    答え：1,4
</div></details>

### Q. 35
    次のコードを使用して、Azure Machine Learning リアルタイム Web サービスとしてモデルをデプロイします。
        service = Model.deploy(ws, 'classification-service', [model], inference_config, deployment_config)
        service.wait_for_deployment(True)
    デプロイは失敗します。
    あなたは、デプロイ中に実行されたアクションを決定し、失敗した特定のアクションを識別することによって、デプロイの失敗をトラブルシュートする必要があります。
    あなたはどのコードセグメントを実行する必要がありますか？
1. service.get_logs()
2. service.state
3. service.serialize()
4. service.update_deployment_state()
<details><div>
    答え：1
サービスオブジェクトから詳細なDockerエンジンのログメッセージを印刷することができます。ACI、AKS、および Local デプロイメントのログを表示することができます。次の例は、ログを印刷する方法を示しています。
* もしあなたが既にサービスオブジェクトを手にしている場合
    print(service.get_logs())
* サービスの名前だけ知っている場合 (同じ名前で異なるバージョン番号のサービスが複数存在する可能性があることに注意してください)
    print(ws.webservices['mysvc'].get_logs())
</div></details>

### Q. 36
    Azure Container Instance にモデルをデプロイします。
    モデルAPIを呼び出すには、Azure Machine Learning SDKを使用する必要があります。
    あなたは、ネイティブSDKクラスとメソッドを使用して、デプロイされたモデルを呼び出す必要があります。
    あなたはどのようにコマンドを完了する必要がありますか？回答するには、回答領域で適切なオプションを選択します。
    OPTION:A

    OPTION:B
        from azureml.core import Workspace 
        from azureml.core.webservice import Webservice

        predictions = service.run(input_json)
1. A
2. B
<details><div>
    答え：2
Box 1: from azureml.core.webservice import Webservice
    次のコードは、SDK を使用して、Web サービスのモデル、環境、エントリスクリプトを Azure Container Instances に更新する方法を示しています。
        from azureml.core import Environment
        from azureml.core.webservice import Webservice
        from azureml.core.model import Model, InferenceConfig
Box 2: predictions = service.run(input_json)
例 以下のコードでは，サービスへデータを送信しています．
import json
    test_sample = json.dumps({'data': [

        [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],

        [10, 9, 8, 7, 6, 5, 4, 3, 2, 1]

    ]})
    test_sample = bytes(test_sample, encoding='utf8')
    prediction = service.run(input_data=test_sample)
    print(prediction)
</div></details>

### Q. 37
    マルチクラス画像分類のディープラーニングモデルを作成します。
    あなたは、PyTorchバージョン1.2を使用してモデルを訓練します。
    あなたは、モデルがデプロイされたときに、推論環境のために正しいバージョンのPyTorchが識別されることを確認する必要があります。
    あなたは何をする必要がありますか？
1. モデルをローカルに.ptファイルとして保存し、ローカルなWebサービスとしてデプロイします。
2. デフォルトの Azure 機械学習 conda 環境を使用するように設定されたコンピュータに、モデルをデプロイします。
3. モデルの拡張子をa.pt、プロパティをデフォルトバージョンとして登録します。
4. model_framework と model_framework_version_properties を指定して、モデルを登録します。
<details><div>
    答え：4
    framework_version: 学習コードの実行に使用する PyTorch のバージョン。
</div></details>

### Q. 38
    このセクションの問題に解答した後、その問題に戻ることはできません。その結果、これらの問題はレビュー画面には表示されません。
    あなたは、機械学習モデルを訓練し、登録します。
    あなたは、このモデルをリアルタイムのWebサービスとして配備する予定です。アプリケーションは、モデルを使用するためにキーベースの認証を使用する必要があります。
    あなたは、Webサービスをデプロイする必要があります。
    解決策
        AksWebservice インスタンスを作成します。
        auth_enabledプロパティの値をFalseに設定します。
        token_auth_enabled プロパティの値を True に設定します。
        このモデルをサービスにデプロイします。
    このソリューションは、目標を達成しましたか？
1. はい
2. いいえ
<details><div>
    答え：2
    代わりに auth_enabled = TRUE のみを使用します。
注：キーベースの認証。
    AKS にデプロイされたウェブサービスは、デフォルトでキーベースの認証が有効になっています。ACI にデプロイされたサービスは、デフォルトでキーベースの認証が無効になっていますが、ACI ウェブサービスを作成するときに auth_enabled = TRUE を設定することで有効にすることができます。以下は、キーベースの認証を有効にしたACIデプロイメント設定の作成例である。
deployment_config <- aci_webservice_deployment_config(cpu_cores = 1,
                                                      memory_gb = 1,
                                                      auth_enabled = TRUE)
</div></details>

### Q. 39
    このセクションの問題に解答した後、その問題に戻ることはできません。その結果、これらの問題はレビュー画面には表示されません。
    あなたは、機械学習モデルを訓練し、登録します。
    あなたは、このモデルをリアルタイムのWebサービスとして配備する予定です。アプリケーションは、モデルを使用するためにキーベースの認証を使用する必要があります。
    あなたは、Webサービスをデプロイする必要があります。
    解決策
        AksWebservice インスタンスを作成します。
        auth_enabled プロパティの値を True に設定します。
        モデルをサービスにデプロイします。
    解決策は目標を達成しましたか？
1. はい
2. いいえ
<details><div>
    答え：1
    キーベース認証。
AKS にデプロイされたウェブサービスは、デフォルトでキーベースの認証が有効になっています。ACI にデプロイされたサービスは、デフォルトではキーベースの認証が無効になっていますが、ACI ウェブサービスを作成する際に auth_enabled = TRUE と設定することで有効にすることができます。以下は、キーベースの認証を有効にしたACIデプロイメント設定の作成例である。
deployment_config <- aci_webservice_deployment_config(cpu_cores = 1,
                                                      memory_gb = 1,
                                                      auth_enabled = TRUE)
</div></details>

### Q. 40
    このセクションの問題に解答した後、その問題に戻ることはできません。その結果、これらの問題はレビュー画面には表示されません。
    あなたは、機械学習モデルを訓練し、登録します。
    あなたは、このモデルをリアルタイムのWebサービスとして配備する予定です。アプリケーションは、モデルを使用するためにキーベースの認証を使用する必要があります。
    あなたは、Webサービスをデプロイする必要があります。
    解決策
        AciWebserviceインスタンスを作成する。
        ssl_enabledプロパティの値をTrueに設定する。
        モデルをサービスにデプロイする。
    解決策は目標を達成しているか？
1. はい
2. いいえ
<details><div>
    答え：2
    代わりに auth_enabled = TRUE のみを使用します。
注：キーベースの認証。
AKS にデプロイされたウェブサービスは、デフォルトでキーベースの認証が有効になっています。ACI にデプロイされたサービスは、デフォルトでキーベースの認証が無効になっていますが、ACI ウェブサービスを作成するときに auth_enabled = TRUE を設定することで有効にすることができます。以下は、キーベースの認証を有効にしたACIデプロイメント設定の作成例である。
deployment_config <- aci_webservice_deployment_config(cpu_cores = 1,
                                                      memory_gb = 1,
                                                      auth_enabled = TRUE)
</div></details>

### Q. 41
    あなたは、カンマ区切り値（CSV）ファイル内のデータを処理するPythonスクリプトを作成します。
    このスクリプトは、Azure Machine Learningの実験として実行する予定です。
    スクリプトは、データをロードし、次のコードを使用して、それが含む行数を決定します。
        from azureml.core import Run
        import pandas as pd

        run = pd.read_csv()
        rows = (len(data))
    実験の実行が完了した後、Runオブジェクトのget_metricsメソッドを使用して返すことができるrow_countという名前のメトリックとして、行数を記録する必要があります。
    どのようなコードを使用すればよいでしょうか？
1. run.upload_file()
2. run.log()
3. run.tag()
4. run.log_table()
5. run.log_row()
<details><div>
    答え：2
log(name, value, description=''）を使用して、指定された名前のランに数値または文字列値をログに記録します。ランにメトリックを記録すると、そのメトリックは実験のランレコードに保存されます。一つのランの中で同じ測定値を複数回記録することができ、その結果はその測定値のベクトルとみなされます。

例：run.log("accuracy", 0.95)

不正解です。
    E: log_row(name, description=None, **kwargs) を使用すると、kwargs に記述されているように、複数の列を持つメトリックが作成されます。log_rowは、任意のタプルを記録するために一度だけ呼び出すことができ、完全なテーブルを生成するためにループ内で複数回呼び出すことができます。
例：run.log_row("Y over X", x=1, y=0.4)
</div></details>

### Q. 42
    スクリプト実行設定を使って、実験としてスクリプトを実行する予定です。スクリプトは scipy ライブラリのモジュールと、通常デフォルトの conda 環境ではインストールされない Python パッケージをいくつか使用します。
    小規模なデータセットについてはローカルのワークステーションで実験を実行し、大規模なデータセットについてはより強力なリモート計算クラスタで実行して実験をスケールアウトする予定です。
    ローカルとリモートの計算機で、最小限の管理作業で実験がうまく実行されるようにする必要があります。
    どうすればいいのでしょうか？
1. 実験の実行設定に環境を指定しない場合は、デフォルトの環境を使用して実験を実行します。
2. 必要なPythonの設定をした仮想マシンを作成し、その仮想マシンをCompute Targetとしてアタッチします。
3. 必要なパッケージを含む環境を作成し、登録します。すべての実験の実行には、この環境を使用します。
4. 必要な conda パッケージを定義した config.yaml ファイルを作成し、そのファイルを experiment フォルダに保存します。
5. 常にデフォルトのパッケージを使用し、estimatorを使用して実験を実行する。
<details><div>
    答え：3
    もしローカルコンピュータに既存のConda環境があるなら、環境オブジェクトを作成するためにサービスを使うことができます。この戦略を使うことで、ローカルの対話型環境をリモートで実行する際に再利用することができます。
</div></details>

### Q. 43
    Azure Machine Learning サービスで機械学習モデルを学習するためのスクリプトを作成する。
    以下のコードを実行し、エスティメーターを作成します。
    以下の各ステートメントについて、そのステートメントが真である場合はYesを選択する。そうでない場合は、「いいえ」を選択します。
1. は，実験に必要なファイルをローカルコンピュータ環境の training-experiment ディレクトリから検索する．
2. は，実験に必要なファイルをローカルコンピュータ環境の training-experiment ディレクトリから検索しない．
3. ローカルデータフォルダをマウントし、パラメータを使用してスクリプトから利用できるようにします。
4. ローカルデータフォルダをマウントし、パラメータを使用してスクリプトから利用できるようにしません。
5. が存在しない場合、train.py スクリプトが作成されます。
6. が存在しない場合、train.py スクリプトが作成されません。
7. scikit-learnの実験を実行することができます。
8. scikit-learnの実験を実行することができません。
<details><div>
    答え：1,3,6,7
ボックス1: はい
    パラメータ source_directory は、トレーニングジョブに必要な実験設定ファイルやコードファイルを含むローカルディレクトリである。
ボックス2: Yes
    script_params は、entry_script で指定されたトレーニングスクリプトに渡すコマンドライン引数のディクショナリです。
ボックス 3: No
ボックス4: はい
    conda_packages パラメータは、実験用の Python 環境に追加する conda パッケージを表す文字列のリストです。
</div></details>

### Q. 44
    あなたは、マルチクラス画像分類のディープラーニングモデルを作成します。
    モデルは、公共のWebポータルからフェッチされた新しい画像データで毎月再トレーニングする必要があります。あなたは、新しいデータをフェッチし、画像のサイズを標準化し、モデルを再トレーニングするためにAzure Machine Learningパイプラインを作成します。
    あなたは、Azure Machine Learning SDKを使用して、パイプラインのスケジュールを構成する必要があります。
    どの4つのアクションを順番に実行する必要がありますか？回答するには、アクションのリストから適切なアクションを回答領域に配置し、それらを正しい順序で並べます。
1. パイプライン ID の取得、scheduleRecurrence() オブジェクトの作成、定義された再帰指定による schedule.create.create メソッドによる azure 機械学習パイプラインのスケジュール定義、パイプラインの公開。
2. パイプラインの公開, パイプライン ID の取得、scheduleRecurrence() オブジェクトの作成、定義された再帰指定による schedule.create.create メソッドによる azure 機械学習パイプラインのスケジュール定義
3. scheduleRecurrence() オブジェクトの作成、定義された再帰指定による schedule.create.create メソッドによる azure 機械学習パイプラインのスケジュール定義, パイプラインの公開, パイプライン ID の取得
<details><div>
    答え：2
ステップ1：パイプラインを公開する。
    パイプラインをスケジュールするには、ワークスペースへの参照、公開したパイプラインの識別子、スケジュールを作成する実験名が必要です。
ステップ2：パイプラインのIDを取得する。
    スケジュールに必要です。
ステップ3：ScheduleRecurrence.を作成します。
    パイプラインを定期的に実行するために、スケジュールを作成します。スケジュールは、パイプライン、実験、トリガーを関連付けます。
    まず、スケジュールを作成する。例 15分ごとに実行を開始するスケジュールを作成する。
        recurrence = ScheduleRecurrence(frequency="Minute", interval=15)
ステップ4：Azure Machine Learningパイプラインのスケジュールを定義する。
例、続きです。
    recurring_schedule = Schedule.create(ws, name="MyRecurringSchedule",
                            description="Based on time",
                            pipeline_id=pipeline_id,
                            experiment_name=experiment_name。
                            recurrence=recurrence)
</div></details>

### Q. 45
    Azure Machine Learningデザイナーを使用して、リアルタイムサービスエンドポイントを作成します。単一のAzure Machine Learningサービスのコンピュートリソースを持っています。
    あなたは、モデルを訓練し、デプロイのための[リアルタイム]パイプラインを準備します。
    あなたは、[推論]パイプラインをWebサービスとして公開する必要があります。
    どのコンピュートタイプを使用する必要がありますか？
1. a new Machine Learning Compute resource
2. Azure Kubernetes Services
3. HDInsight
4. the existing Machine Learning Compute resouece
5. Azure Databricks
<details><div>
    答え：2
    Azure Kubernetes Service（AKS）は、リアルタイム推論を利用することができます。
</div></details>

### Q. 46
    Azure ML SDKを使用して、バッチ推論パイプラインを作成します。以下のコードを実行し、パイプラインのパラメータを設定します。

    あなたは、パイプラインの実行から出力を取得する必要があります。
    あなたはどこで出力を見つけるのだろうか？
1. the digit_identification.py script
2. the debug log
3. the Activity Log in the Azure portal for the Machine Learning
4. the Inference Clusters tab in Machine Learning studio
5. a file named parallel_run_step.txt located in output folder
<details><div>
    答え：5
    output_action (str)。出力をどのように構成するか。現在サポートされている値は 'append_row' と 'summary_only' です。
    append_row' - run()メソッドによって出力されたすべての値は、出力場所に作成されるparallel_run_step.txtという一意のファイルに集約されます。
    'summary_only'
</div></details>

### Q. 47
    ある組織が、ラベル付けされた写真のセットを使用するマルチクラス画像分類ディープラーニングモデルを作成し、配備している。
    ソフトウェアエンジニアリングチームは、夏の間、予測ウェブサービスに大きな推論負荷がかかっていることを報告しました。このモデルの本番ウェブサービスは、ウェブサービスが配備されている計算クラスタを完全に利用しているにもかかわらず、需要を満たすことができません。
    あなたは、最小限のダウンタイムと最小限の管理作業で、画像分類Webサービスのパフォーマンスを向上させる必要があります。
    あなたは、IT運用チームに何をするよう助言すべきですか？
1. ノードに大きな VM サイズを使用して新しい計算クラスタを作成し、そのクラスタに Web サービスを再展開し、サービスのエンドポイントの DNS 登録を更新して、新しいクラスタを指すようにします。
2. ウェブサービスが配置されているコンピュートクラスタのノード数を増やす
3. ウェブサービスが配置されている計算クラスタの最小ノード数を増やす。
<details><div>
    答え：2
    Azure Machine Learning SDKは、AKSクラスタのスケーリングをサポートしていません。クラスター内のノードをスケールするには、Azure Machine LearningスタジオでAKSクラスターのUIを使用します。クラスターのVMサイズではなく、ノード数のみを変更することができます。
</div></details>

### Q. 48
    Azure Machine Learningを使用して、モデルをトレーニングして登録します。
    このモデルを、IT 部門が Azure Machine Learning ワークスペースに作成した service-compute という名前の推論クラスターに、リアルタイムの Web サービスとして実運用にデプロイする必要があります。
    配備された Web サービスを消費するクライアントアプリケーションは、Azure Active Directory のサービスプリンシパルに基づき認証される必要があります。
    Azure Machine Learning SDK を使用して、モデルをデプロイするスクリプトを記述する必要があります。必要なモジュールはインポートされています。
    あなたはどのようにコードを完成させるべきですか？回答するには、回答領域で適切な選択肢を選択します。
    OPTION:A

    OPTION:B
        deploy_target = AksCompute(ws, "service-compute")
        deployment_config = AksWebservice.deploy_configuration(cpu_cores=1,memory_gb=1,token_auth_enabled=false)
1. A
2. B
<details><div>
    答え：1
ボックス1：AksCompute
例
    aks_target = AksCompute(ws, "myaks")
* dev/test 用に設定されたクラスタにデプロイする場合、そのクラスタがこのデプロイ設 # 定に対応できるだけのコアとメモリで作成されていることを確認します。
* dev/test 用に設定されたクラスタにデプロイする場合、このデプロイ設定を処理するのに十分なコ メモリは
* メモリは依存関係や AML コンポーネントなどにも使われることに注意してください。
    deployment_config = AksWebservice.deploy_configuration(cpu_cores = 1, memory_gb = 1)
    service = Model.deploy(ws, "myservice", [model], inference_config, deployment_config, aks_target)
ボックス2：AksWebservice
ボックス3：token_auth_enabled=Yes
    Webserviceでトークン認証が有効かどうか。
注：Azure Active Directory（Azure AD）で定義されたサービスプリンシパルは、Azure Databricksで認証および認可ポリシーを適用できるプリンシパルとして機能します。
Azure Active Directory Authentication Library（ADAL）は、ユーザーのAzure ADアクセストークンをプログラムで取得するために使用することができます。

不正解です。
    auth_enabled（bool）。このWebserviceでキー認証を有効にするかどうか。デフォルトはTrue。
</div></details>

### Q. 49
    新しい Azure サブスクリプションを作成します。サブスクリプションにリソースはプロビジョニングされていません。
    あなたは、Azure Machine Learningワークスペースを作成する必要があります。
    この目標を達成するための3つの可能な方法は何ですか？各正解は完全な解決策を提示します。
1. Azure ML SDKライブラリを使用し、名前、subscription_id、resource_group、およびlocationパラメータでWorkspace.createメソッドを呼び出すPythonコードを実行します。
2. crosoft.MachineLearningServices/ワークスペース資源とその依存関係を含むAzureリソース管理テンプレートを使用します。
3. Azure Command Line Interface（CLI）をAzure Machine Learning extensionと一緒に使用して、-nameと-locationパラメーターでaz group create関数を呼び出し、次にaz ml workspace create関数でワークスペース名とリソースグループにCwとCgパラメーターを指定する。
4. Azure Machine Learning studioに移動し、ワークスペースを作成します。
5. Azure ML SDK ライブラリを使用し、名前、subscription_id、resource_group パラメータを指定して Workspace.get メソッドを呼び出す Python コードを実行する。
<details><div>
    答え：1,2,3
    回答はこちら ABC 正しい選択肢です。
    A . Azure ML SDKライブラリを使用し、名前、subscription_id、resource_group、およびlocationパラメータでWorkspace.createメソッドを呼び出すPythonコードを実行します。
    B . Microsoft.MachineLearningServices/ワークスペース資源とその依存関係を含むAzureリソース管理テンプレートを使用します。
    C . Azure Command Line Interface（CLI）をAzure Machine Learning extensionと一緒に使用して、-nameと-locationパラメーターでaz group create関数を呼び出し、次にaz ml workspace create関数でワークスペース名とリソースグループにCwとCgパラメーターを指定する。
    D . Azure Machine Learning studioに移動し、ワークスペースを作成します。
    E . Azure ML SDK ライブラリを使用し、名前、subscription_id、resource_group パラメータを指定して Workspace.get メソッドを呼び出す Python コードを実行する。
</div></details>

### Q. 50
    TSV ファイルのセットを含む Azure blob コンテナがあります。Azure blob コンテナは、Azure Machine Learning サービスのワークスペースのデータストアとして登録されています。各TSVファイルは、同じデータスキーマを使用する。
    あなたは、Azure Machine Learning SDK for Python を使用して、すべての TSV ファイルのデータをまとめて集約し、集約したデータを Azure Machine Learning ワークスペースのデータセットとして登録することを計画しています。
    以下のコードを実行します。

    以下の各ステートメントについて、そのステートメントが真である場合は、[はい]を選択します。そうでない場合は、[いいえ]を選択します。
1. myDataset_1 データセットは、以下の方法で pandas データフレームに変換することができます。mydataset_1.to_pandas_dataframe() を使用します。
    はい
2. myDataset_1 データセットは、以下の方法で pandas データフレームに変換することができます。mydataset_1.to_pandas_dataframe() を使用します。
    いいえ
3. mydataset_1.to_path() メソッドは、データセット内のすべての tsv のファイルパスの配列を返します。
    はい
4. mydataset_1.to_path() メソッドは、データセット内のすべての tsv のファイルパスの配列を返します。
    いいえ
5. myDataset_2 データセットは、以下の方法で pandas データフレームに変換することができます。mydataset_2.to_pandas_dataframe() を使用します。
    はい
6. myDataset_2 データセットは、以下の方法で pandas データフレームに変換することができます。mydataset_2.to_pandas_dataframe() を使用します。
    いいえ
<details><div>
    答え：2,3,5
ボックス1：なし
    FileDatasetは、データストアや公開URLから、単一または複数のファイルを参照する。TSVファイルは解析する必要がある。
ボックス 2: はい
    to_path() は、データセットで定義された各ファイルストリームのファイルパスのリストを取得する。
ボックス3: Yes
    TabularDataset.to_pandas_dataframe は、データセットからすべてのレコードを pandas DataFrame にロードします。
    TabularDatasetは、提供されたファイルまたはファイルのリストをパースして作成された表形式のデータを表します。
注：TSV は、表計算ソフトで使用されるタブ区切りファイルのファイル拡張子です。TSVはTab Separated Valuesの略です。TSVファイルは生データに使用され、表計算ソフトにインポートしたり、表計算ソフトからエクスポートしたりすることができる。TSVファイルは基本的にテキストファイルであり、生データをテキストエディタで閲覧することができるが、表計算ソフト間で生データを移動する際によく利用される。
</div></details>

### Q. 51
    モデルを学習させるために、Azure Machine Learningのコンピュートリソースを作成します。コンピュートリソースは、以下のように構成されます。
        最小ノード数：2
        最大ノード数 4
    最小ノード数を減らし、最大ノード数を増やして、次の値にする必要があります。
        最小ノード数: 0
        最大ノード数：8
    あなたは、コンピュートリソースを再構成する必要があります。
    この目標を達成するために可能な3つの方法は何ですか？各正解は完全な解決策を提示します。
1. Use the Azure Machine Learning studio
2. Run the update method of the AmlCompute class in the Pyton SDK
3. Use the Azure portal
4. use the Azure Machine Lratning designer
5. Run the refresh_state() method of the BatchCompute class in the Python SDK
<details><div>
    答え：1,2,3
A: Azure Machine Learning studioでアセットとリソースを管理することができます。
B：AmlComputeクラスのupdate(min_nodes=None, max_nodes=None, idle_seconds_before_scaledown=None) は、このAmlComputeターゲットのScaleSettingsを更新しているんだ。
C: クラスタ内のノードを変更するには、Azure ポータルのクラスタ用の UI を使用します。
</div></details>

### Q. 52
    Azure Machine Learningを使用して、機械学習モデルをトレーニングしています。学習スクリプトをリモートで実行するために、ターゲットを計算する必要があります。
    次の Python コードを実行します。

    次の各ステートメントについて、ステートメントが真である場合は、[はい]を選択します。そうでない場合は、「いいえ」を選択します。
1. コンピュートは、他のユーザーと共有できるリソースとして、ワークスペース領域内に作成されます。：はい
2. コンピュートは、他のユーザーと共有できるリソースとして、ワークスペース領域内に作成されます。：いいえ
3. コードによって作成されたコンピュータリソースは、Azure Machine Learning Studioにコンピュータクラスタとして表示されます。：はい
4. コードによって作成されたコンピュータリソースは、Azure Machine Learning Studioにコンピュータクラスタとして表示されます。：いいえ
5. 最小ノード数は0になります：はい
6. 最小ノード数は0になります：いいえ
<details><div>
    答え：1,3,5
ボックス1: はい
    コンピュートは、他のユーザーと共有できるリソースとして、ワークスペース領域内に作成されます。
ボックス2: Yes
    コンピュート・クラスターとして表示されます。
    コンピュート・ターゲットの表示
1. ワークスペースのすべてのコンピュートターゲットを表示するには、次の手順を実行します。
2. Azure Machine Learning studioに移動します。
3. 3. [Manage]で[Compute]を選択します。
4. 4. 上部のタブを選択すると、各タイプのコンピュートターゲットが表示されます。
ボックス3: はい
    min_nodesが指定されていないため、デフォルトは0です。
</div></details>

### Q. 53
    Azure Machine Learningのワークスペースを作成します。ノートパソコンにローカルのPython環境を用意します。ノートパソコンでワークスペースに接続し、実験を実行します。
    以下のようなconfig.jsonファイルを作成します。


    ワークスペースのデータや実験を操作するには、Azure Machine Learning SDK を使用する必要があります。
    あなたは、Python環境からワークスペースに接続するためにconfig.jsonファイルを構成する必要があります。
    ワークスペースに接続するために、どの2つの追加パラメータをconfig.jsonファイルに追加する必要がありますか？各正解は、ソリューションの一部を提示します。
1. login
2. resource_group
3. subscription_id
4. key
5. region
<details><div>
    答え：2,3
同じワークスペースを複数の環境で使用する場合は、JSON設定ファイルを作成します。設定ファイルには、サブスクリプション（subscription_id）、リソース（resource_group）、ワークスペース名を保存し、簡単にロードできるようにします。
次のサンプルは、ワークスペースを作成する方法を示しています。

from azureml.core import Workspace
   ws = Workspace.create(name='myworkspace',
               subscription_id='<azure-subscription-id>',
               resource_group='myresourcegroup',
               create_resource_group=True,
               location='eastus2'
               )
</div></details>

### Q. 54
    あなたは、画像分類のための深層学習畳み込みニューラルネットワークモデルを構築する準備をしています。CUDAデバイスを使用してモデルをトレーニングするためのスクリプトを作成します。
    このスクリプトを実行する実験をAzure Machine Learningワークスペースに提出する必要があります。
    次の計算リソースが使用できます。
        Microsoft Office がインストールされた Microsoft Surface デバイス。企業の IT ポリシーにより、追加ソフトウェアのインストールは禁止されています。
        ワークスペース内のds-workstationという名前のCompute Instance（2CPUと8GBのメモリを搭載）。
        8つのCPUベースのノードを持つcpu-clusterという名前のAzure Machine Learningのコンピュートターゲット
        4つのCPUおよびGPUベースのノードを持つgpu-clusterという名前のAzure Machine Learningコンピュートターゲット
    モデルのトレーニング時間を最短にするために、実験を提出するコードの実行とスクリプトの実行に使用する計算リソースを指定する必要があります。
    データサイエンティストはどのリソースを使うべきでしょうか？回答するには、回答欄で適切な選択肢を選択してください。
1. resource type, run code to submit the experiment, option, the microsoft surface device
2. resource type, run code to submit the experiment, option, the ds-workstaion notebook vm
3. resource type, tun the traning script, option, the gpu-computer target
4. resource type, tun the traning script, option, the microsoft surface device
<details><div>
    答え：2,3
箱1: ds-workstationノートブックVM
ボックス2：GPUコンピュート・ターゲット
    GPUが前例のないトレーニングと推論性能によってディープラーニングに革命をもたらしたように、RAPIDSは従来の機械学習の実践者がGPUを使用してゲームを変える性能を解放することを可能にします。RAPIDS on Azure Machine Learningサービスでは、NC_v3、NC_v2、ND、ND_v2ファミリーのGPUを使用して、データ処理、トレーニング、推論を含む機械学習パイプライン全体を高速化することが可能です。ユーザーは、20倍以上の性能向上（4GPU使用時）を実現し、トレーニング時間を数時間から数分に短縮し、タイムトゥインサイトを劇的に短縮することが可能です。
</div></details>

### Q. 55
    あなたは、学習済みモデルのリアルタイム推論サービスを導入しています。
    展開されたモデルは、ビジネスクリティカルなアプリケーションをサポートしており、Webサービスに送信されたデータと、そのデータが生成する予測を監視できることが重要です。
    あなたは、最小限の管理作業で、配備されたモデルの監視ソリューションを実装する必要があります。
    どうすればよいでしょうか。
1. azure ml studio で登録されたモデルの説明を見る。
2. サービスエンドポイントの azure application insight を有効にし、azure ポータルでログを表示する。
3. モデルをトレーニングするために使用した実験によって生成されたログファイルを表示します。
4. エンドポイントを参照する ml flow tracking url を作成し、ml flow によって記録されたデータを閲覧する。
<details><div>
    答え：2
Azure Machine Learningスタジオでロギングを設定する
Azure Machine Learning studio からも Azure Application Insights を有効にすることができます。モデルを Web サービスとしてデプロイする準備ができたら、次の手順で Application Insights を有効化します。

1. https://ml.azure.com でスタジオにサインインします。
2. 2. [モデル]に移動して、デプロイするモデルを選択します。
3. 3. +Deployを選択します。
4. 4. Deploy model フォームに入力します。
5. 5. [詳細設定]メニューを展開します。
6. Application Insights の診断とデータ収集の有効化]を選択します。
</div></details>

### Q. 56
    Hyperdriveを使用して、モデルのトレーニング時に選択されたハイパーパラメータを最適化することを計画しています。ハイパーパラメータ実験のオプションを定義するために、以下のコードを作成します。

    以下の各ステートメントについて、そのステートメントが真である場合はYesを選択します。そうでない場合は、「いいえ」を選択します。
1. このハイパーパラメータチューニング実験では、50回の実行が必要です。：はい
2. このハイパーパラメータチューニング実験では、50回の実行が必要です。：いいえ
3. hyperparamenterconfigクラスのpolicy paramenterを使用して、セキュリティポリシーを指定することができます。：はい
4. hyperparamenterconfigクラスのpolicy paramenterを使用して、セキュリティポリシーを指定することができます。：いいえ
5. この実験では、学習率パラメータを 0.5 から 0.15 の間のあらゆる値に設定したランが作成される。：はい
6. この実験では、学習率パラメータを 0.5 から 0.15 の間のあらゆる値に設定したランが作成される。：いいえ
<details><div>
    答え：2,3,6
ボックス1：なし
    max_total_runs (ここで50)
    作成するランの最大合計数。サンプル空間がこの値より小さい場合は、実行回数が少なくなる可能性があります。
ボックス 2: はい
    ポリシー EarlyTerminationPolicy
    使用する早期終了の方針。None（デフォルト）の場合、早期終了ポリシーは使用されません。
ボックス3: No
    離散ハイパーパラメータは、離散値間の選択として指定されます。
    1つまたは複数のカンマ区切りの値
    範囲オブジェクト
    任意のリスト・オブジェクト
</div></details>

### Q. 57
    バッチ推論パイプラインで使用する予定のモデルを登録します。
    バッチ推論パイプラインは、ファイルデータセット内のファイルを処理するためにParallelRunStepステップを使用する必要があります。スクリプトは、推論関数が呼び出されるたびに6つの入力ファイルを処理するParallelRunStepステップを実行する必要があります。
    パイプラインを構成する必要があります。
    PralleRunStepステップのParallelRunConfigオブジェクトで指定すべき構成設定はどれですか？
1. process_count_per_node=6
2. node_count=6
3. mini_batch_size=6
4. error_threschold=6
<details><div>
    答え：2
node_countは、ParallelRunStepの実行に使用されるコンピュートターゲットのノード数です。
不正解です。
    A：process_count_per_node（プロセスカウント・パー・ノード
        各ノードで実行されるプロセス数。(オプション、デフォルトはノード上のコア数)
    C: mini_batch_size
        FileDataset入力の場合、このフィールドは、ユーザスクリプトが1回のrun()コールで処理できるファイルの数である。TabularDataset入力の場合、このフィールドは、ユーザースクリプトが1回のrun()呼び出しで処理できるデータのおおよその大きさである。値の例は、1024、1024KB、10MB、および1GBである。
    D: エラーしきい値
        処理中に無視すべき、TabularDataset の場合はレコード失敗の数、FileDataset の場合はファイル失敗の数を指定する。エラー回数がこの値を超えると、ジョブは中断される。
</div></details>

### Q. 58
    機械学習モデルを学習させる。
    そのモデルをテスト用のリアルタイム推論サービスとして配備する必要があります。このサービスでは、CPU使用率が低く、48MB未満のRAMが必要です。配備されたサービスの計算ターゲットは、コストと管理オーバーヘッドを最小限に抑えながら、自動的に初期化する必要があります。
    どのコンピュート・ターゲットを使うべきでしょうか？
1. azure container instance
2. atatched azure databricks cluster
3. azure lubernetes service inference cluster
4. azure machine learning compute cluster
<details><div>
    答え：1
Azure Container Instances (ACI) は、1 GB 未満の小規模なモデルにのみ適しています。
48GB以下のRAMを必要とする、CPUベースの低スケールなワークロードに使用します。
注：Microsoftは、より大きなモデルの開発テストには、シングルノードのAzure Kubernetes Service（AKS）クラスターを使用することを推奨しています。
</div></details>

### Q. 59
    このセクションの問題に解答した後、その問題に戻ることはできません。その結果、これらの質問はレビュー画面に表示されません。
    あるIT部門は、次のAzureリソースグループとリソースを作成します。


    IT部門は、Azure Machine Learningワークスペースにaks-clusterという名前のAzure Kubernetes Service（AKS）ベースの推論コンピュートターゲットを作成します。
    あなたは、GPUを搭載したMicrosoft Surface Bookコンピュータを持っています。Python 3.6とVisual Studio Codeがインストールされています。
    ディープニューラルネットワーク（DNN）モデルをトレーニングし、損失と精度のメトリックをログに記録するスクリプトを実行する必要があります。
    解決策 Azure ML SDKをSurface Bookにインストールします。Pythonコードを実行してワークスペースに接続し、ローカルコンピューティング上で実験としてトレーニングスクリプトを実行します。
    解決策は目標を達成していますか？
1. はい
2. いいえ
<details><div>
    答え：2
    Azure Machine Learningワークスペースのコンピュートターゲットとして、mlvm仮想マシンをアタッチする必要があります。
</div></details>

### Q. 60
    このセクションの問題に解答した後、その問題に戻ることはできません。その結果、これらの質問はレビュー画面に表示されません。
    あるIT部門は、次のAzureリソースグループとリソースを作成します。


    IT部門は、Azure Machine Learningワークスペースにaks-clusterという名前のAzure Kubernetes Service（AKS）ベースの推論コンピュートターゲットを作成します。
    あなたは、GPUを搭載したMicrosoft Surface Bookコンピュータを持っています。Python 3.6とVisual Studio Codeがインストールされています。
    ディープニューラルネットワーク（DNN）モデルをトレーニングし、損失と精度のメトリックをログに記録するスクリプトを実行する必要があります。
    解決策 Azure Machine Learningワークスペースのコンピュートターゲットとしてmlvm仮想マシンをアタッチします。Surface BookにAzure ML SDKをインストールし、Pythonコードを実行して、ワークスペースに接続します。mlvmリモートコンピュートリソース上で実験としてトレーニングスクリプトを実行します。
    このソリューションは目標を達成していますか？
1. はい
2. いいえ
<details><div>
    答え：1
VMをコンピュート・ターゲットとして使用します。
注：コンピュート・ターゲットとは、トレーニング・スクリプトを実行したり、サービス・デプロイメントをホストする、指定されたコンピュート・リソース/環境です。この場所は、ローカルマシンまたはクラウドベースのコンピュートリソースである可能性があります。
</div></details>

### Q. 61
    あなたは、短い文章で書かれた12,000件のカスタマーレビューを含むCSVファイルを使用してセンチメント分析を行うことになりました。CSVファイルをAzure Machine Learning Studioに追加し、実験の開始点データセットとして設定します。テキストからN-gram特徴を抽出するモジュールを実験に追加して、データセットのカスタマーレビュー列からキーフレーズを抽出します。
    カスタマーレビューのテキストから新しいN-gram辞書を作成し、最大N-gramサイズをtrigramsに設定する必要があります。
    何を選択する必要がありますか？回答するには、回答欄の適切な選択肢を選択してください。
    OPTION:A

    OPTION:B
1. A
2. B
<details><div>
    答え：1
説明
    ボキャブラリーモードです。作成
    Vocabularyモードでは、Createを選択すると、N-gram featureの新しいリストを作成することを意味します。
        N-gramサイズ：3
    N-gramsのサイズには、抽出・保存するN-gramの最大サイズを表す数値を入力します。例えば、3 と入力すると、ユニグラム、ビッググラム、トリグラムが作成されます。
    重み付け関数。空白のまま
    重み付け機能オプションは、語彙のマージまたは更新を行う場合にのみ必要です。このオプションは、2つの語彙の用語とそのスコアにどのような重み付けをするかを指定します。
</div></details>

### Q. 62
    workspace1 という名前の Azure Machine Learning ワークスペースがあり、パブリックエンドポイントからアクセスできます。このワークスペースには、store1 という名前の Azure Blob ストレージ データストアが含まれており、これは account1 という名前の Azure ストレージ アカウントの blob コンテナを表します。ワークスペース 1 とアカウント 1 は、同じ仮想ネットワーク内のプライベート エンドポイントを使用してアクセスできるように構成します。
    Azure Machine Learning SDK for Python を使用して、store1 のコンテンツにアクセスできるようにする必要があります。Azure Machine Learning studio を使用して、store1 のコンテンツをプレビューできる必要があります。
    store1 を構成する必要があります。
    あなたは何をする必要がありますか？回答するには、回答領域で適切な選択肢を選択します。
1. 要件、azure machine learning sdk for python を使用して store1 のコンテンツにアクセス、アクション: store1 をデフォルトデータストアとして設定。
2. 要件、azure machine learning sdk for python を使用して store1 のコンテンツにアクセス、 action: regunerate the keys of account1
3. 要件、Azure機械学習スタジオを使用してstore1のコンテンツをプレビューする、アクション：store1をdefultデータストアとして設定する。
4. 要件は、Azureマシンラーニングスタジオを使用してstore1の内容をプレビューし、アクション：store1の認証を更新します。
<details><div>
    答え：2,4
Box 1: account1 のキーを再生成します。
    Azure Blob Storageは、アカウントキーまたはSASトークンによる認証をサポートしています。
    ストレージサービスへのアクセスを認証するには、アカウントキー、共有アクセス署名（SAS）トークン、またはサービスプリンシパルのいずれかを提供することができます。
ボックス 2: store1 の認証を更新します。
    Azure Machine Learning studioのユーザーにとって、いくつかの機能はデータセットからデータを読み取る能力に依存しています。例えば、データセットのプレビュー、プロファイル、自動機械学習などです。これらの機能が仮想ネットワークの背後にあるストレージで動作するようにするには、スタジオでワークスペース マネージド ID を使用して、Azure Machine Learning が仮想ネットワークの外からストレージ アカウントにアクセスできるようにします。
注：スタジオの一部の機能は、仮想ネットワークではデフォルトで無効になっています。これらの機能を再度有効にするには、スタジオで使用する予定のストレージアカウントに対してマネージドアイデンティティを有効にする必要があります。
仮想ネットワークでは、以下の操作はデフォルトで無効になっています。
スタジオでデータをプレビューする。
</div></details>


## 2
### Q. 1
    あなたは、いくつかの列に欠損値が含まれる数値データセットを分析しています。
    特徴セットの次元に影響を与えることなく、適切な操作で欠損値を除去する必要があります。
    すべての値を含む完全なデータセットを分析する必要があります。
    解決策 列の中央値を計算し、その中央値を列の欠損値の置き換えとして使用する。
    解決策は目標を達成しているか？
1. はい
2. いいえ
<details><div>
    答え：2
    MICE（Multiple Imputation by Chained Equations）方式を使用します。
</div></details>

### Q. 2
    あなたは、Azure Machine Learning Studioを使用するデータサイエンティストです。
    あなたは、ターゲットカラムを予測するために、ビンに出力カラムを生成する値を正規化する必要があります。
    解決策 カスタム開始と停止ビンニングモードで等幅を適用します。
    解決策は目標を満たしていますか？
1. はい
2. いいえ
<details><div>
    答え：2
    ターゲットカラムを持つEntropy MDLのビニングモードを使用します。
</div></details>

### Q. 3
    あなたは、Azure Machine Learning Studioを使用するデータサイエンティストです。
    あなたは、ターゲットカラムを予測するために、ビンに出力カラムを生成する値を正規化する必要があります。
    解決策 PQuantile正規化でQuantilesビンニングモードを適用します。
    解決策は目標を満たしていますか？
1. はい
2. いいえ
<details><div>
    答え：2
    ターゲットカラムを持つEntropy MDLビニングモードを使用します。
</div></details>

### Q. 4
    Azure Machine Learning Studioで実験を作成します。10,000行を含むトレーニングデータセットを追加します。最初の9,000行はクラス0(90%)を表します。
    残りの1,000行は、クラス1（10％）を表します。
    このトレーニングセットは2つのクラス間の不均衡を表しています。5つのデータ行を使用して、クラス1のトレーニング例の数を4,000に増やす必要があります。SMOTE (Synthetic Minority Oversampling Technique) モジュールを実験に追加します。
    あなたは、モジュールを設定する必要があります。
    どの値を使うべきですか？回答するには、回答欄のダイアログボックスで適切なオプションを選択してください。
    OPTION:A

    OPTION:B
1. A
2. B
<details><div>
    答え：1
    ボックス1: 300
        300 (%) と入力すると、元のデータセット (1000) と比較して、少数派のケースの割合が3倍 (3000) になります。
    ボックス2: 5
        5つのデータ行を使用する必要があります。
        最近傍の数」オプションを使用して、SMOTEアルゴリズムが新しいケースを構築する際に使用する特徴空間の大きさを決定します。最近傍とは、あるターゲット・ケースに非常に類似したデータ行（ケース）のことです。2つのケース間の距離は、すべての特徴の重み付けされたベクトルを組み合わせることで測定されます。
        最近傍の数を増やすことで、より多くのケースから特徴を取得することができます。
        最近傍の数を少なくすることで、より元のサンプルに近い特徴を使用することができます。
</div></details>

### Q. 5
    あなたは分類タスクを解いています。
    k-foldクロスバリデーションを用いて、限られたデータサンプルでモデルを評価する必要があります。あなたは、分割数としてkパラメータを設定することから始めます。
    あなたは、クロスバリデーションのためにkパラメータを設定する必要があります。
    どの値を使うべきですか？
1. 
2. 
3. 
4. 
<details><div>
    答え：3
    リーブ・ワン・アウト（LOO）クロスバリデーション
    K = n (オブザベーションの数)をセットすると，n-フォールドとなり， K-フォールド・アプローチの特別なケースであるLOO (leave-one out cross-validation)と呼ばれる．
    LOO CVは有用な場合もありますが、一般的にはデータを十分に揺さぶることができません。各フォールドからの推定値は相関が高く、それゆえ、それらの平均は高い分散を持つことがあります。
    このため、通常、K=5または10が選択されます。これは，バイアスと分散のトレードオフのための良い妥協点を提供します。
</div></details>

### Q. 6
    Azure Machine Learning Studioを使用して、機械学習実験を構築します。
    あなたは、データを2つの異なるデータセットに分割する必要があります。
    あなたはどのモジュールを使用する必要がありますか？
1. 
2. 
3. 
4. 
<details><div>
    答え：3
    Partition and SampleでStratified splitオプションを指定すると、指定したルールで分割された複数のデータセットが出力されます。
</div></details>

### Q. 7
    あなたは、Azure Machine Learning Studioを使用して実験を作成しています。
    あなたは、評価のためにデータを4つのサブセットに分割する必要があります。データには高度な欠測値があります。あなたは、分析のためにデータを準備する必要があります。
    あなたは実験を生成するための適切な方法を選択する必要があります。
    どの3つのモジュールを順番に実行する必要がありますか？回答するには、アクションのリストから適切なアクションを回答エリアに移動し、正しい順番で並べます。
    注意: 回答の選択肢の順番は1つ以上あってもかまいません。あなたが選択した正しい順序のいずれかが単位となります。
1. 
2. 
3. 
4. 
<details><div>
    答え：2
    Azure Machine Learning StudioのClean Missing Dataモジュールで、欠損値を削除、置換、または推論するためのものです。
    不正解です。
        潜在的ディリクレ変換。Azure Machine Learning Studio の Latent Dirichlet Allocation モジュールで、分類されていないテキストをいくつかのカテゴリにグループ化する。潜在的ディリクレ配分（LDA）は、しばしば自然言語処理（NLP）で使用され、類似しているテキストを見つけるために使用されます。もう一つの一般的な用語は、トピックモデリングです。
        ビルド・カウンティング・トランスフォーム Azure Machine Learning Studio の Build Counting Transform モジュールで、トレーニングデータを分析します。このデータから、このモジュールは、予測モデルで使用することができるカウントベースの特徴のセットと同様に、カウントテーブルを構築します。
        Missing Value Scrubber: Missing Values Scrubberモジュールは、非推奨です。
        Feature hashing: Feature hashingは言語学で使用され、ユニークなトークンを整数に変換することで機能する。
        離散値の置き換え：Azure Machine Learning Studioの離散値の置き換えモジュールは、離散値を表すために使用できる確率のスコアを生成するために使用されます。このスコアは、離散値の情報価値を理解するために有用である。
</div></details>

### Q. 8
    Azure Machine Learning Studioを使用して、大規模なデータストアからデータを取得しています。
    システムクロックに基づくランダムサンプリングシードを使用して、テスト用にデータのサブセットを作成する必要があります。
    Partition and Sample モジュールを実験に追加します。
    あなたは、モジュールのプロパティを選択する必要があります。
    どの値を選択する必要がありますか？回答するには、回答欄で適切な選択肢を選んでください。
    OPTION:A

    OPTION:B
1. A
2. B
<details><div>
    答え：2
    ボックス1：サンプリング
        データのサンプルを作成する
        このオプションは、単純無作為抽出または層化無作為抽出をサポートします。これは、テスト用に小さい代表的なサンプルデータセットを作成したい場合に便利です。

1. 1. Studio で Partition and Sample モジュールを実験に追加し、データセットに接続する。
2. PartitionまたはSampleモード。Samplingに設定する。
3. 3. サンプリングのレート。以下のボックス2を参照してください。

    ボックス2: 0

3. サンプリングの割合。サンプリングのためのランダムシード。オプションで、シード値として使用する整数を入力します。

    このオプションは、行を毎回同じように分割したい場合に重要である。デフォルト値は0であり、システムクロックに基づいて開始シードが生成されることを意味する。これは、実験を実行するたびに微妙に異なる結果をもたらす可能性がある。
</div></details>

### Q. 9
    あなたは、機械学習モデルを作成している。あなたは、NULL行を含むデータセットを持っています。
    あなたは、Azure Machine Learning StudioのClean Missing Dataモジュールを使用して、データセット内のNULLおよび欠損データを識別して解決する必要があります。
    あなたはどのパラメータを使用する必要がありますか？
1. 
2. 
3. 
4. 
<details><div>
    答え：3
    行全体を削除する。データセット内の1つ以上の欠損値を持つ任意の行を完全に削除します。これは、欠損値がランダムに欠損していると考えられる場合に有効です。
</div></details>

### Q. 10
    あなたは、クリーニングが必要な生のデータセットを分析しています。
    Azure Machine Learning Studioを使用して、変換と操作を実行する必要があります。
    あなたは、変換を実行するために適切なモジュールを識別する必要があります。
    あなたはどのモジュールを選択する必要がありますか？回答するには、適切なモジュールを正しいシナリオにドラッグします。各モジュールは、1回、2回以上、または全く使用されないかもしれません。
    ペイン間の分割バーをドラッグしたり、コンテンツを表示するためにスクロールする必要があるかもしれません。
    注：正しい選択には1点ずつ価値があります。
1. 
2. 
3. 
4. 
<details><div>
    答え：1,3,5,7
    ボックス1：欠落データのクリーニング
    ボックス2：SMOTE
        Azure Machine Learning StudioのSMOTEモジュールを使用して、機械学習に使用するデータセット内の未提示のケースを増やします。SMOTEは、既存のケースを単純に複製するよりも、レアケースの数を増やすのに有効な方法です。
    ボックス3：指標値への変換
        Azure Machine Learning Studio の Convert to Indicator Values モジュールを使用する。このモジュールの目的は、カテゴリ値を含む列を、機械学習モデルの特徴としてより簡単に使用できる一連のバイナリ指標列に変換することです。
    ボックス 4: 重複した行を削除する
</div></details>

### Q. 11
    salesDataという名前のPythonデータフレームが以下のような形式で用意されています。
    このデータフレームは、以下のようにロングデータ形式にアンピボットする必要があります。

    Python の pandas.melt() 関数を使用して変換を実行する必要があります。
    あなたはどのようにコードセグメントを完了する必要がありますか？回答するには、回答領域で適切なオプションを選択します。

    OPTION:A

    OPTION:B
1. A
2. B
<details><div>
    答え：1
    ボックス1：dataFrame
        構文: pandas.melt(frame, id_vars=None, value_vars=None, var_name=None, value_name='value', col_level=None)[source] この構文では、フレームをデータとして扱うことができます。
        ここで、frameはDataFrameである
    ボックス 2: ショップ
        パラメータ id_vars id_vars : タプル、リスト、または ndarray, オプション
        識別子変数として使用するカラム(複数可)
    ボックス3：['2017','2018']です。
        value_vars : タプル、リスト、またはndarray(オプション)
        ピボット解除する列(複数可)。指定しない場合、id_varsとして設定されていないすべての列を使用する。
</div></details>

### Q. 12
    あなたは分類の課題に取り組んでいます。あなたは、生徒がサッカーをしたいかどうか、および関連する属性を示すデータセットを持っています。このデータセットには以下の列が含まれます。
    あなたは、変数をタイプによって分類する必要があります。
    どの変数を各カテゴリに追加すべきですか? 答えるには、解答欄で適切な選択肢を選んでください。
    注意: 正しい選択にはそれぞれ 1 ポイントの価値があります。
1. 
2. 
3. 
4. 
<details><div>
    答え：2,4

</div></details>

### Q. 13
    CSVファイルからテキストを前処理する予定です。Azure Machine Learning Studioのデフォルトのストップワードリストをロードします。
    次の要件を満たすために、Preprocess Text モジュールを構成する必要があります。
    単一の正規形から複数の関連する単語を確保する。
    テキストからパイプ文字を削除します。
    情報検索を最適化するために単語を削除します。
    どの3つのオプションを選択する必要がありますか？回答するには、回答欄で適切な選択肢を選択してください。

    OPTION:A

    OPTION:B
1. A
2. B
<details><div>
    答え：2
    ボックス1：ストップワードの除去
        情報検索を最適化するために、単語を削除する。
        ストップワードを削除する テキスト列にあらかじめ定義されたストップワードリストを適用する場合は、このオプションを選択します。ストップワードの除去は、他の処理の前に実行されます。
    ボックス2：レマット化
        複数の関連語を1つの正規形から確実に抽出します。
        Lemmatizationは、複数の関連する単語を1つの正規形に変換します。
    ボックス3: 特殊文字の除去
        特殊文字を削除します。このオプションを使用すると、英数字以外の特殊文字をパイプ | 文字に置き換えることができます。
</div></details>

### Q. 14
    あなたは、Azure Machine Learning Studioを使用して、データセットの特徴エンジニアリングを実行しています。
    あなたは、ビンにグループ化された特徴カラムを生成するために値を正規化する必要があります。
    解決策 Entropy Minimum Description Length（MDL）ビンニングモードを適用します。
    解決策は目標を達成しましたか？
1. はい
2. いいえ
<details><div>
    答え：1
    エントロピーのMDLビン化モード。この方法では、予測したい列と、ビンにグループ化したい列を選択する必要があります。そして、データ上を通過し、エントロピーを最小化するビンの数を決定しようとする。言い換えれば、データ列がターゲット列を最もよく予測できるビンの数を選択するのである。そして、データの各行に関連するビン番号を<colname>quantizedというカラムで返します。
</div></details>

### Q. 15
    あなたは、Azure Machine Learning Studioを使用するデータサイエンティストです。
    あなたは、ターゲットカラムを予測するために、ビンに出力カラムを生成する値を正規化する必要があります。
    解決策 QuantileIndex正規化でQuantiles正規化を適用します。
    解決策は目標を満たしていますか？
1. はい
2. いいえ
<details><div>
    答え：2
    ターゲットカラムを持つEntropy MDLのビニングモードを使用します。
</div></details>

### Q. 16
    Azure Machine Learning Studio で新しい実験を作成しているところです。
    あるクラスは、トレーニングセット内の他のクラスよりもはるかに少ない数の観測値を持っています。
    あなたは、クラスの不均衡を補償するために、適切なデータサンプリング戦略を選択する必要があります。
    解決策 あなたは、Scale and Reduceサンプリングモードを使用します。
    この解決策は目標を達成しましたか？
1. はい
2. いいえ
<details><div>
    答え：2
    代わりに、SMOTE（Synthetic Minority Oversampling Technique）サンプリングモードを使用します。
    注：SMOTEは、機械学習に使用されるデータセットにおいて、不特定多数のケースを増加させるために使用されます。SMOTEは、単に既存のケースを複製するよりも、レアケースの数を増やすのに適した方法です。
</div></details>

### Q. 17
    Azure Machine Learning Studio で新しい実験を作成しているところです。
    あるクラスは、トレーニングセット内の他のクラスよりもはるかに少ない数の観測値を持っています。
    あなたは、クラスの不均衡を補償するために、適切なデータサンプリング戦略を選択する必要があります。
    解決策 あなたは、SMOTE（Synthetic Minority Oversampling Technique）サンプリングモードを使用します。
    この解決策は目標を達成しましたか？
1. はい
2. いいえ
<details><div>
    答え：1
    SMOTEは、機械学習に使用するデータセットにおいて、未提示の事例を増やすために使用される。SMOTEは、単に既存の事例を複製するよりも、希少な事例を増やすのに有効な方法である。
</div></details>

### Q. 18
    Azure Machine Learning Studio で新しい実験を作成しているところです。
    あるクラスは、トレーニングセット内の他のクラスよりもはるかに少ない数の観測値を持っています。
    あなたは、クラスの不均衡を補償するために、適切なデータサンプリング戦略を選択する必要があります。
    解決策 あなたは、サンプリングモードに層別分割を使用します。
    この解決策は目標を達成しましたか？
1. はい
2. いいえ
<details><div>
    答え：2
    代わりに、SMOTE（Synthetic Minority Oversampling Technique）サンプリングモードを使用します。
    注：SMOTEは、機械学習に使用されるデータセットにおいて、不特定多数のケースを増加させるために使用されます。SMOTEは、単に既存のケースを複製するよりも、レアケースの数を増やすのに適した方法です。
</div></details>

### Q. 19
    あなたは、機械学習モデルを作成しています。
    あなたは、データ中の外れ値を識別する必要がある。
    あなたはどの2つの可視化を使うことができますか？各正解は完全な解決策を提示します。
    注：各正解の選択は1点の価値があります。
1. 
2. 
3. 
4. 
<details><div>
    答え：2,5
    箱ひげ図アルゴリズムは、外れ値を表示するために使用することができます。
    Outliersを視覚的にすばやく識別するもう1つの方法は、散布図を作成することである。
</div></details>

### Q. 20
    あなたは、Azure Machine Learning Studioを使用してデータセットを解析しています。
    あなたは、各特徴列のp値およびユニークカウントを含む統計的要約を生成する必要があります。
    あなたはどの2つのモジュールを使用することができますか？各正解は完全な解決策を提示します。
    注：各正解の選択は1点の価値があります。
1. 
2. 
3. 
4. 
<details><div>
    答え：2,5
    Export Count Tableモジュールは、Build Count Table（非推奨）およびCount Featurizer（非推奨）モジュールを使用する実験との後方互換性のために提供されています。
    E: Summarize Data statisticsは、完全なデータセットの特性を理解したい場合に有用です。例えば、次のようなことを知る必要があるかもしれません。
        各列にいくつの欠損値があるか？
        特徴列の中にユニークな値はいくつあるか？
        各列の平均と標準偏差は何ですか？
    このモジュールは、各列の重要なスコアを計算し、入力として提供された各変数（データ列）の要約統計の行を返します。
    不正解です。
        A: Azure Machine Learning Studio の Compute Linear Correlation モジュールは、入力データセット内の変数の可能なペアごとに、ピアソン相関係数のセットを計算するために使用されます。
        C：Pythonを使用すると、次のような既存のStudioモジュールで現在サポートされていないタスクを実行することができます。
            matplotlib を使用したデータの可視化
            Python ライブラリを使用した、ワークスペース内のデータセットとモデルの列挙
            Import Dataモジュールでサポートされていないソースからのデータの読み込み、ロード、および操作
        D: Convert to Indicator Values モジュールの目的は、カテゴリ値を含む列を、機械学習モデルの特徴としてより簡単に使用できる一連のバイナリ指標列へ変換することです。
</div></details>

### Q. 21
    あなたは、完成した二値分類の機械学習モデルを評価しています。
    あなたは評価指標として精度を使用する必要があります。
    どの可視化を使うべきですか？
1. 
2. 
3. 
4. 
<details><div>
    答え：4
    A: バイオリンプロットは、伝統的にボックスプロットとカーネル密度プロットを組み合わせたビジュアルである。
    B: 勾配降下法は、関数の最小値を求めるための一次反復最適化アルゴリズムである。勾配降下法を用いて関数の局所的最小値を求めるには、現在の点での関数の勾配（または近似勾配）の負に比例したステップを踏みます。
    C: 箱ひげ図では、中央値、平均値、範囲、四分位値などのデータの基本的な分布情報を見ることができるが、データがその範囲全体でどのように見えるかを示すことはない。
</div></details>

### Q. 22
    あなたは、いくつかの列に欠損値が含まれる数値データセットを分析しています。
    特徴セットの次元に影響を与えることなく、適切な操作で欠損値を除去する必要があります。
    すべての値を含む完全なデータセットを分析する必要があります。
    解決策 LOCF（Last Observation Carried Forward）法を使用して、欠損データ点をインピュートします。
    解決策は目標を達成しているか？
1. はい
2. いいえ
<details><div>
    答え：2
    代わりにMICE（Multiple Imputation by Chained Equations）メソッドを使用します。
    MICE を使用して置換します。このオプションは，各欠損値について，統計文献に "Multivariate Imputation using Chained Equations" または "Multiple Imputation by Chained Equations" として記載されている方法を用いて計算された新しい値を割り当てる．多重代入法では、欠損値を埋める前に、データ中の他の変数を用いて欠損データのある各変数を条件付きでモデル化する。
    注：Last observation carried forward (LOCF) は，縦断的研究における欠損値のインピュテーションの手法である．もしある人が研究終了前に脱落した場合、その人の従属変数の最後に観測されたスコアが、その後のすべての観測点（すなわち、欠損）に使用されます。LOCFは、サンプルサイズを維持し、研究参加者の減少によって引き起こされるバイアスを低減するために使用されます。
</div></details>

### Q. 23
    150以上の特徴を持つデータセットがあります。あなたは、サポートベクターマシン（SVM）バイナリ分類器を訓練するためにデータセットを使用します。
    あなたは、Azure Machine Learning StudioのPermutation Feature Importanceモジュールを使用して、データセットの特徴重要度スコアのセットを計算する必要があります。
    どの順序でアクションを実行する必要がありますか？回答するには、アクションのリストからすべてのアクションを回答領域に移動し、正しい順序でそれらを配置します。
1. 
2. 
3. 
4. 
<details><div>
    答え：2
    ステップ1：2クラスサポートベクトルマシンモジュールを追加し、SVM分類器を初期化します。
    ステップ2: 実験用データセットの追加
    ステップ3: Split Data モジュールを追加し、トレーニングデータセットとテストデータセットを作成する。
        特徴スコアのセットを生成するためには、テストデータセットだけでなく、すでに学習済みのモデルも必要です。
    ステップ4: Permutation Feature Importanceモジュールを追加し、トレーニング済みモデルとテストデータセットに接続します。
    ステップ5：パフォーマンス測定のプロパティのMetricをClassification - Accuracyに設定し、実験を実行します。
</div></details>

### Q. 24
    あなたはPythonで機械学習モデルを作成している。提供されたデータセットには、いくつかの数値列と一つのテキスト列がある。テキストカラムは商品のカテゴリを表す。商品カテゴリは常に以下のいずれかになる。
        バイク
        車
        バン
        ボート
    あなたは、scikit-learn Python パッケージを使用して回帰モデルを構築しています。
    あなたは、テキストデータを scikit-learn Python パッケージと互換性があるように変換する必要があります。
    あなたはどのようにコードセグメントを完成させるべきですか？回答するには、回答欄で適切な選択肢を選んでください。
    OPTION:A

    OPTION:B
1. A
2. B
<details><div>
    答え：1
    ボックス1: dfとしてのパンダ
        Pandasはデータ（CSVやTSVファイル、SQLデータベースなど）を受け取り、データフレームと呼ばれる行と列を持つPythonオブジェクトを作成します。これは統計ソフト（例えばExcelやSPSSなど）のテーブルに非常によく似ています。
    ボックス2：transpose[ProductCategoryMapping]を使用します。
        pandas Seriesから列にデータをリシェイプします。
</div></details>

### Q. 25
    Azure Machine Learning Studioを使用して、マルチクラス分類器を構築するために、データセットのフィルターベースの特徴選択を実行しています。
    データセットには、出力ラベルカラムと高い相関を持つカテゴリ特徴が含まれています。
    あなたは、主要な予測因子を識別するために、適切な特徴スコアリング統計手法を選択する必要があります。
    あなたはどの方法を使用する必要がありますか？
1. 
2. 
3. 
4. 
<details><div>
    答え：4
    ピアソンの相関統計量、またはピアソンの相関係数は、統計モデルではr値としても知られています。任意の2つの変数について、相関の強さを示す値を返します。
    ピアソンの相関係数は、2つの連続変数間の統計的な関係、または関連を測定する検定統計量である。 共分散の方法に基づいているため、目的の変数間の関連性を測定する最良の方法として知られています。 関連性の大きさ、つまり相関関係だけでなく、関連性の方向についての情報も得られます。
    不正解です。
        C：二元配置カイ二乗検定は、期待値が実際の結果にどれだけ近いかを測定する統計手法である。
</div></details>

### Q. 26
    あなたは、ある人が病気を持っているかどうかを予測するための二値分類モデルを作成します。
    あなたは、起こりうる分類の誤りを検出する必要があります。
    それぞれの記述に対して、どのエラータイプを選択すべきですか？回答するには、回答欄で適切な選択肢を選択してください。
    注：正しい選択にはそれぞれ1点の価値があります。
1. 
2. 
3. 
4. 
<details><div>
    答え：1,3,6,7
    ボックス 1: True Positive
        トゥルーポジティブとは、モデルが正しくポジティブクラスを予測した結果のことです。
    ボックス2: True Negative
        True Negative は、モデルが正しくネガティブクラスを予測する結果である。
    ボックス3: False Positive
        False Positive は、モデルが誤って正のクラスを予測した結果である。
    ボックス 4: 偽陰性(False Negative)
        false negative は、モデルが誤って negative クラスを予測した結果です。
    注：以下のように定義する。
        "オオカミ" は肯定的なクラスです。
        「オオカミはいない" は否定クラスである。
        狼予測」モデルは、4つの可能な結果すべてを描写する2x2の混同行列を用いて要約することができます。
</div></details>

### Q. 27
    Azure Machine Learning Service を使用して、ニューラルネットワークの分類モデルのハイパーパラメータ探索を自動化します。
    以下の要件に従って、ランダムサンプリングを使用してハイパーパラメータを自動的に調整するために、ハイパーパラメータ空間を定義する必要があります。
        学習率は、平均値 10、標準偏差 3 の正規分布から選択する必要があります。
        バッチサイズは16、32、64でなければならない。
        保持確率は0.05〜0.1の範囲で一様分布から選択された値でなければならない。
    Azure Machine Learning Service 用の Python API の param_sampling メソッドを使用する必要があります。
    あなたはどのようにコードセグメントを完了する必要がありますか？回答するには、回答領域で適切な選択肢を選択します。

    OPTION:A

    OPTION:B
1. A
2. B
<details><div>
    答え：1
    ランダムサンプリングでは、定義された探索空間からハイパーパラメータ値がランダムに選択される。ランダムサンプリングでは、探索空間に離散的なハイパーパラメータと連続的なハイパーパラメータの両方を含めることができます。
</div></details>

### Q. 28
    あなたは、数人の学生を対象にしたハンズオンワークショップを開催する予定です。ワークショップでは、Pythonを使用してデータの可視化を作成することに焦点を当てます。各生徒は、インターネットにアクセスできるデバイスを使用します。
    生徒のデバイスは、Pythonの開発用に設定されていません。学生は、デバイスにソフトウェアをインストールするための管理者アクセス権を持っていません。Azureのサブスクリプションは、学生には利用できません。
    あなたは、学生がPythonベースのデータ可視化コードを実行できることを確認する必要があります。
    あなたはどのAzureツールを使用する必要がありますか？
1. 
2. 
3. 
4. 
<details><div>
    答え：3
</div></details>

### Q. 29
    あなたは、いくつかの列に欠損値が含まれる数値データセットを分析しています。
    特徴セットの次元に影響を与えることなく、適切な操作で欠損値を除去する必要があります。
    すべての値を含む完全なデータセットを分析する必要があります。
    解決策 連鎖式による多重インピュテーション（MICE）法を使用して、各欠損値を置き換えます。
    解決策は目標を達成しているか？
1. はい
2. いいえ
<details><div>
    答え：1
    MICEを使用して置換する。このオプションは，各欠損値について，統計文献に "Multivariate Imputation using Chained Equations" または "Multiple Imputation by Chained Equations" として記載されている方法を用いて計算された新しい値を割り当てる．Multiple imputation 法では，欠損値を埋める前に，欠損データを持つ各変数が，データ中の他の変数を用いて条件付きでモデル化される．
注：連鎖式による多変量インピュテーション（MICE）は，時に "完全条件付き仕様" または "逐次回帰多重インピュテーション" と呼ばれ，欠損データに対処する原理的な方法の1つとして統計文献に現れている．シングルインピュテーションとは対照的にマルチプルインピュテーションを作成することで、インピュテーションにおける統計的不確実性を説明する。さらに、連鎖式アプローチは非常に柔軟で、様々なタイプの変数（例えば、連続またはバイナリ）だけでなく、境界や調査のスキップパターンなどの複雑なものを扱うことができます。
</div></details>

### Q. 30
    あなたは、いくつかの列に欠損値が含まれる数値データセットを分析しています。
    特徴セットの次元に影響を与えることなく、適切な操作で欠損値を除去する必要があります。
    すべての値を含む完全なデータセットを分析する必要があります。
    解決策 欠損データ点を含む列全体を削除する。
    解決策は目標を達成しているか？
1. はい
2. いいえ
<details><div>
    答え：2
    MICE（Multiple Imputation by Chained Equations）方式を使用します。
</div></details>

### Q. 31
    Azure Machine Learning Studio で新しい実験を作成しているところです。
    あるクラスは、トレーニングセット内の他のクラスよりもはるかに少ない数の観測値を持っています。
    あなたは、クラスの不均衡を補償するために、適切なデータサンプリング戦略を選択する必要があります。
    解決策 あなたは、主成分分析（PCA）サンプリングモードを使用します。
    この解決策は目標を達成しましたか？
1. はい
2. いいえ
<details><div>
    答え：2
    代わりに、SMOTE（Synthetic Minority Oversampling Technique）サンプリングモードを使用します。
注：SMOTEは、機械学習に使用されるデータセットにおいて、不特定多数のケースを増加させるために使用されます。SMOTEは、単に既存のケースを複製するよりも、稀なケースの数を増やすのに適した方法です。
不正解です。
    Azure Machine Learning Studio（classic）のPrincipal Component Analysisモジュールは、学習データの次元を減らすために使用されます。このモジュールは、データを分析し、データセットに含まれるすべての情報をキャプチャし、より少ない数の特徴で、縮小された特徴セットを作成します。
</div></details>

### Q. 32
    Azure Machine Learning Studioで新しい実験を作成しているところです。あなたは、多くの列で欠損値を持つ小さなデータセットを持っています。このデータでは、各列に予測器を適用する必要はありません。あなたは、欠落データのクリーニングを使用する予定です。
    あなたは、データクリーニングの方法を選択する必要があります。
    どの方法を使用すべきですか？
1. 
2. 
3. 
4. 
<details><div>
    答え：1
    確率的PCAによる置換：連鎖方程式を用いたマルチプルインピュテーション（MICE）などの他のオプションと比較して、このオプションは、各列の予測変数の適用を必要としないという利点があります。その代わりに、それは全データセットの共分散を近似します。したがって、多くの列で欠損値を持つデータセットに対して、より良いパフォーマンスを提供することができます。
</div></details>

### Q. 33
    あなたは、完成した二値分類の機械学習モデルを評価しています。
    あなたは評価指標として精度を使用する必要があります。
    どの可視化を使うべきですか？
1. 
2. 
3. 
4. 
<details><div>
    答え：4
    受信者動作特性（ROC）とは，特定のモデルについて，正しく分類されたラベルと誤って分類されたラベルをプロットしたものである．
不正解。
    A: バイオリンプロットは、伝統的にボックスプロットとカーネル密度プロットを組み合わせた視覚的なものである。
    B: 勾配降下法は、関数の最小値を求めるための一次反復最適化アルゴリズムである。勾配降下法を用いて関数の局所的最小値を求めるには、現在の点における関数の勾配（または近似勾配）の負に比例したステップを踏む。
    C: 散布図は、モデルによって予測された値に対して、データの実際の値をグラフにしたものである。散布図は、X軸に実際の値を表示し、Y軸に予測値を表示する。また、予測値が実際の値と正確に一致する完全予測を示す線も表示されます。
</div></details>

### Q. 34
    あなたは分類タスクを解いています。
    k-foldクロスバリデーションを用いて、限られたデータサンプルでモデルを評価する必要があります。あなたは、分割数としてkパラメータを設定することから始めます。
    あなたは、クロスバリデーションのためにkパラメータを設定する必要があります。
    どの値を使うべきですか？
1. 
2. 
3. 
4. 
<details><div>
    答え：2
    リーブ・ワン・アウト（LOO）クロスバリデーション
    K = n (オブザベーションの数)をセットすると，n-フォールドとなり， K-フォールド・アプローチの特別なケースであるLOO (leave-one out cross-validation)と呼ばれる．
    LOO CVは有用な場合もありますが、一般的にはデータを十分に揺さぶることができません。各フォールドからの推定値は相関が高く、それゆえ、それらの平均は高い分散を持つことがあります。
    このため、通常、K=5または10が選択されます。これは、バイアスと分散のトレードオフのための良い妥協点を提供します。
</div></details>

### Q. 35
    Azure Machine Learning Studioを使用して、機械学習実験を構築します。
    あなたは、データを2つの異なるデータセットに分割する必要があります。
    あなたはどのモジュールを使用する必要がありますか？
1. 
2. 
3. 
4. 
<details><div>
    答え：3
</div></details>

### Q. 36
    あなたは、鳥の健康と移動を追跡するプロジェクトのリードデータサイエンティストです。あなたは、専門家によって収集されたラベル付きの鳥の写真のセットを使用するマルチクラス画像分類のディープラーニングモデルを作成します。
    あなたは鳥の写真100,000枚を持っています。すべての写真はJPG形式を使用し、AzureサブスクリプションのAzure blobコンテナに格納されています。
    深層学習モデルのトレーニングに使用されるAzure Machine Learningサービスのワークスペースから、Azure blobコンテナ内の鳥の写真ファイルにアクセスする必要があります。あなたは、データの移動を最小限に抑える必要があります。
    あなたは何をする必要がありますか？
1. 
2. 
3. 
4. 
<details><div>
    答え：4
    Azure Blob コンテナ用のデータストアを作成することを推奨します。ワークスペースを作成すると、Azure Blob コンテナと Azure ファイル共有が自動的にワークスペースに登録されます。
</div></details>

### Q. 37
    あなたは、さまざまな都市における住宅所有の人口統計データを調査する予定です。データは、以下の形式のCSVファイルである。
        年齢,都市,収入,住宅所有者
        21,シカゴ,50000,0
        35,シアトル,120000,1
        23,シアトル,65000,0
        45,シアトル,130000,1
        18,シカゴ,48000,0

    Azure Machine Learningワークスペースで実験を実行し、データを探索し、結果をログに記録する必要があります。実験では、次の情報をログに記録する必要があります。
        データセット内のオブザベーションの数
        home_owner 別の収入の箱ひげ図
        都市名と各都市の平均所得を含むディクショナリ
    必要な情報を記録するために、実験の実行オブジェクトの適切なログ記録メソッドを使用する必要があります。
    どのようにコードを完成させるべきでしょうか？答えを出すには、適切なコードセグメントを正しい位置にドラッグしてください。各コードセグメントは、1回だけ使っても、2回以上使っても、全く使わなくてもかまいません。

    オプション:A

    オプション:B
1. A
2. B
<details><div>
    答え：1
    ボックス 1: log
        データセット内のオブザベーションの数。
            run.log(name, value, description='')
        スカラー値。指定された名前のランに数値または文字列の値をログに記録します。ランにメトリックを記録すると、そのメトリックが実験中のランの記録に保存されます。1つのランの中で同じメトリックを複数回記録することができ、その結果はそのメトリックのベクトルとみなされます。
        例：run.log("accuracy", 0.95)
    ボックス2：log_image
        home_owner 別の所得を箱ひげ図にしたもの。
        log_image ランの記録に画像を記録します。log_imageを使用して、.PNG画像ファイルまたはmatplotlibプロットをランに記録します。これらの画像は、ランの記録で表示され、比較することができます。
        例：run.log_image("ROC", plot=plt)
    ボックス3：log_table
        都市名と各都市の平均所得を含む辞書。
        log_table。指定された名前のランに辞書オブジェクトをログ出力します。
</div></details>

### Q. 38
    Azure Machine Learning サービスを使用して、training_data という表形式のデータセットを作成します。このデータセットを学習スクリプトで使用する予定です。
    次のコードを使用して、データセットを参照する変数を作成します。
        training_ds = workspace.datasets.get("training_data")
    スクリプトを実行するための推定量を定義します．
    スクリプトがtraining_dataデータセットにアクセスできるように、estimatorに正しいプロパティを設定する必要があります。
    どのプロパティを設定する必要がありますか。
1. 
2. 
3. 
4. 
<details><div>
    答え：2
</div></details>

### Q. 39
    フォルダを参照する csv_folder という名前のファイルデータセットを登録します。このフォルダには、Azure ストレージ blob コンテナ内の複数のカンマ区切り値 (CSV) ファイルが含まれています。
    あなたは、次のコードを使用して、ファイルデータセットからデータをロードするスクリプトを実行することを計画しています。あなたは、次の変数を作成し、インスタンス化します。
    あなたは、次のコードを持っています。

    スクリプトが参照するファイルを確実に読み取ることができるように、データセットを渡す必要があります。
    コードコメントを置き換えるために、どのコードセグメントを挿入する必要がありますか？
1. 
2. 
3. 
4. 
<details><div>
    答え：2
</div></details>

### Q. 40
    あなたは、デザイナーを使用して新しいAzure Machine Learningパイプラインを作成しています。
    パイプラインは、Web サイトで公開されているカンマ区切り値（CSV）ファイルのデータを使用してモデルをトレーニングする必要があります。このファイルのデータセットは作成されていません。
    あなたは、最小限の管理作業を使用して、CSVファイルからデザイナーのパイプラインにデータを取り込む必要があります。
    Designerのパイプラインに追加すべきモジュールはどれですか？
1. 
2. 
3. 
4. 
<details><div>
    答え：4
    パイプラインにデータを提供する方法として、データセットオブジェクトを使用することが推奨されています。Datasetオブジェクトは、データストアやWeb URLに存在するデータ、またはそこからアクセス可能なデータを指します。Datasetクラスは抽象クラスなので、FileDataset（1つまたは複数のファイルを参照）またはTabularDataset（データの区切り列を持つ1つまたは複数のファイルから作成）のいずれかのインスタンスを作成することになります。
</div></details>

### Q. 41
    Azure Storage の blob コンテナに対して、ml-data というデータストアを定義します。コンテナには、train という名前のフォルダがあり、data.csv という名前のファイルが含まれています。このファイルを使用して、Azure Machine Learning SDK を使用してモデルをトレーニングする予定です。
    Azure Machine Learning SDKを使用して、ローカル計算機上で実験を実行することにより、モデルをトレーニングする予定である。
    次のコードを実行して、DataReference オブジェクトを定義します。
    あなたは、トレーニングデータをロードする必要があります。
    あなたはどのコードセグメントを使用する必要がありますか？
    OPTION:A

    OPTION:B
1. A
2. B
<details><div>
    答え：2
</div></details>


### 42
#### 概要
    あなたは、プロスポーツイベントのデータサイエンスを提供する企業でデータサイエンティストです。モデルは、グローバルおよびローカルな市場データを使用して、以下のビジネス目標を達成します。
    スポーツイベントにおけるモバイルデバイスユーザーのセンチメントを、観客の反応から得た音声に基づいて理解する。
    広告に対するユーザーの反応傾向を把握する。
    モバイル端末に配信される広告のスタイルをカスタマイズする。
    ペナルティイベントの検知に動画を活用
#### 現在の環境
    ペナルティ検知に使用されるメディアは、コンシューマーデバイスから提供されます。メディアには、スポーツイベント中に撮影され、ソーシャルメディア上で共有される画像や動画が含まれることがあります。画像や動画のサイズや形式はさまざまです。
    モデル構築のために利用できるデータは、7年分のスポーツイベントメディアから構成されています。スポーツイベントのメディアには、録画されたビデオやラジオの解説、スポーツイベント中に撮影された関連するソーシャルメディアフィードのログが含まれます。
    群集心理には、イベント参加者から提出されたモノラルとステレオの両方の形式の音声記録が含まれます。
#### ペナルティの検出と感情
    データサイエンティストは、ペナルティイベントの検出のために複数の機械学習モデルを使用して、インテリジェントなソリューションを構築する必要があります。
    データサイエンティストは、機械学習パイプラインの自動特徴エンジニアリングとモデル構築を使って、ローカル環境でノートブックを構築する必要があります。
    ノートブックは、動的ワーカー割り当てのSparkインスタンスを使用して、再トレーニングのためにデプロイされなければなりません。
    ノートブックは、新しいSparkインスタンスで同じコードで実行し、データのソースのみを再コード化する必要があります。
    グローバルなペナルティ検出モデルは、学習時に動的な実行時グラフ計算を使用して学習する必要があります。
    ローカルペナルティ検出モデルは、BrainScriptを用いて記述すること。
    ローカルな群衆感情モデルの実験では、ローカルなペナルティ検出データを組み合わせる必要があります。
    群集感情モデルは、歓声やキャッチフレーズなどの既知の音を識別しなければならない。個々の群衆感情モデルは、類似した音を検出する。
    ローカルモデルで共有する素性は全て連続変数である。
    共有される特徴量は倍精度を使用しなければならない。後続のレイヤーは、集計された実行平均と標準偏差のメトリクスが利用可能でなければならない。
#### 広告
    最初の数週間の運用で、以下のことが観察されました。
    広告のレスポンス率が低下した。
    広告のスタイルによって、レスポンスの低下が異なる。
    トレーニングデータと本番データの特徴量の分布が一致しない。
    分析によると、ユーザーの位置と行動に関する100個の数値特徴のうち、位置情報ソースに由来する47個の特徴が生の特徴として使用されていることがわかりました。偏りと分散の問題を改善するために提案された実験は、線形的に相関のない10個の特徴を設計することです。
    初期データ発見では、群衆感情モデルに使用される学習データにおいて、対象状態の密度が広範囲に渡っていることが示された。
    すべてのペナルティ検出モデルにおいて、SGD（Stochastic Gradient Descent）を用いた推論フェーズが遅すぎることがわかる。
    音声サンプルでは、キャッチフレーズの長さが地域によって25%～47%変化していることがわかる
    グローバルペナルティ検出モデルの性能は、トレーニングセットと検証セットを比較すると、分散は小さいがバイアスが大きいことがわかります。機能変更を実施する前に、すべてのトレーニングケースと検証ケースを使用して、バイアスと分散を確認する必要があります。
    広告レスポンスモデルは、各イベントの開始時にトレーニングし、スポーツイベント中に適用する必要があります。
    市場セグメンテーションモデルは、類似した広告レスポンス履歴に対して最適化されなければなりません。
    サンプリングは、同じ特徴を共有するローカルとグローバルのセグメンテーションモデル間で相互的かつ集団的な排他性を保証しなければならない。
    ローカル・マーケット・セグメンテーション・モデルは、ユーザーの広告反応傾向を判断する前に適用される。
    広告反応モデルは、特徴の非線形境界をサポートする必要がある。
    広告傾向モデルは、カットスレッショルドを0.45とし、重み付きカッパが0.1±5%から逸脱した場合に再トレーニングを行う。
    広告傾向モデルは、下図に示すようなコスト係数を使用する。
    広告傾向モデルには、以下の図に示すコスト係数案が使用されています。
    現在のコスト係数と提案されたコスト係数のシナリオのパフォーマンスカーブを以下の図に示します。

### Q. 43
    ローカルペナルティ検出データのスケーリング戦略を実装する必要があります。
    どの正規化タイプを使用する必要がありますか？
1. 
2. 
3. 
4. 
<details><div>
    答え：2
    Post batch normalization statistics (PBN) は、推論に利用できる Batch Normalization の母平均と分散を評価する方法の Microsoft Cognitive Toolkit (CNTK) 版である Original Paper.
    CNTKでは、BrainScriptNetworkBuilderを使ってカスタムネットワークを定義し、CNTKのネットワーク記述言語 "BrainScript" で記述しています。
シナリオを作成する。
    局所的なペナルティ検出モデルをBrainScriptで記述する必要がある。
</div></details>

### Q. 44
    あなたは、Python言語を使用して、グローバルペナルティ検出モデル用のサンプリング戦略を構築する必要があります。
    あなたはどのようにコードセグメントを完成させるべきですか？回答するには、回答欄で適切な選択肢を選択してください。

    OPTION:A

    OPTION:B
1. A
2. B
<details><div>
    答え：1
    ボックス1：import pytorch as deeplearninglib
    箱2: ..DistributedSampler(Sampler)...。
        DistributedSampler(Sampler).DistributedSampler(Sampler)の略。
        データの読み込みをデータセットの部分集合に制限するSampler。
        特に、class:`torch.nn.parallel.DistributedDataParallel`と組み合わせると便利です。この場合、各プロセスはDistributedSamplerのインスタンスをDataLoaderのサンプラーとして渡し、自分専用のオリジナルデータセットのサブセットをロードすることができる。
        シナリオ サンプリングは、同じ特徴を共有するローカルとグローバルのセグメンテーションモデル間で、相互排他的、集団排他的な保証が必要。
    ボックス3：optimizer = deeplearninglib.train. GradientDescentOptimizer(learning_rate=0.10)です。
不正解： ...SGD...。
    シナリオ すべてのペナルティ検出モデルは、SGD（Stochastic Gradient Descent）を使用した推論フェーズがあまりにも遅く実行されていることを示しています。
    ボックス4： ...nn.parallel.DistributedDataParallel.
        DistributedSampler(Sampler)。データの読み込みをデータセットのサブセットに制限するサンプラーです。
    特に :class:`torch.nn.parallel.DistributedDataParallel` と組み合わせると便利です。
</div></details>

### 45 事例紹介
#### 概要
    あなたは、アメリカの良質な個人・商業用不動産を専門に扱う企業、Fabrikam Residencesのデータサイエンティストです。Fabrikam Residencesはヨーロッパへの進出を検討しており、ヨーロッパの主要都市における個人住宅の価格を調査するよう依頼されました。
    あなたは、Azure Machine Learning Studioを使用して、不動産の中央値を測定します。線形回帰とベイズ線形回帰モジュールを使用して、不動産価格を予測する回帰モデルを作成します。
#### データセット
    ロンドンとパリの2つの都市の不動産詳細を含むCSV形式の2つのデータセットがあります。両方のファイルを別々のデータセットとしてAzure Machine Learning Studioに追加し、実験の出発点とします。両方のデータセットには、次の列が含まれています。
    最初の調査では、MedianValueカラムを除けば、両データセットの構造は同じであることがわかります。小さい方のParisデータセットにはテキスト形式のMedianValueが含まれ、大きい方のLondonデータセットには数値形式のMedianValueが含まれます。
#### データに関する問題
##### 欠落値
    両データセットのAccessibilityToHighwayカラムには欠損値があります。欠損値を埋める前に、データ中の他の変数を用いて条件付きでモデル化するため、欠損データを新しいデータに置き換える必要があります。
    各データセットのカラムには欠損値やヌル値が含まれている。また、データセットには多くの外れ値が含まれている。年齢列は外れ値の割合が高い。Age 列に外れ値がある行を削除する必要があります。MedianValue と AvgRoomsInHouse 列は、両方とも数値形式のデータを保持しています。2つの列の関係をより詳細に分析するために、特徴選択アルゴリズムを選択する必要があります。
##### モデルの適合性
    モデルはオーバーフィットの兆候を示す。オーバーフィッティングを低減する、より洗練された回帰モデルを作成する必要がある。
#### 実験要件
    パフォーマンスを評価するために、線形回帰モジュールとベイズ線形回帰モジュールを交差検証する実験をセットアップする必要があります。それぞれの場合において、データセットの予測変数はMedianValueという名前の列です。パリのデータセットの MedianValue カラムのデータ型が、ロンドンのデータセットの構造と一致することを確認する必要があります。
    結果を予測するためのデータ列の優先順位を決めなければなりません。あなたは、関係を測定するためにノンパラメトリック統計学を使用しなければなりません。
    MedianValue列とAvgRoomsInHouse列の間の関係を分析するために、特徴選択アルゴリズムを使用する必要があります。
#### モデル学習
##### 並べ替え特徴の重要度
    学習済みモデルとテストデータセットがある場合、特徴変数の Permutation Feature Importance スコアを計算する必要があります。モデルの絶対的な適合度を決定する必要があります。
##### ハイパーパラメータ
    学習フェーズを高速化するために、モデル学習プロセスにおいてハイパーパラメータを設定する必要があります。また、この設定により、各評価区間で最も性能の低い実行をキャンセルし、成功する可能性の高いモデルに労力とリソースを振り向ける必要があります。
    モデルがハイパーパラメータのチューニングで計算資源を効率的に使用できないことを懸念している。また、モデルによって全体のチューニング時間が増加することを懸念しています。したがって、有望なジョブを終了させることなく節約できるような、モデルの早期停止基準を実装する必要があります。
#### テスト
    Azure Machine Learning StudioのPartition and Sampleモジュールを使用して、サンプリングに基づくデータセットの複数のパーティションを作成する必要があります。
##### クロスバリデーション
    クロスバリデーションのために、3つの等しいパーティションを作成する必要があります。また、テストデータセットとトレーニングデータセットの行が、各都市の主要河川に近い物件によって均等に分割されるように、クロスバリデーション処理を構成する必要があります。このタスクは、データがサンプリングプロセスを通過する前に完了する必要があります。
##### 線形回帰モジュール
    線形回帰モジュールをトレーニングするとき、モデルで使用する最適な特徴を決定する必要があります。フィーチャー重要性プロセスが完了する前と後のパフォーマンスを測定するために提供されている標準的なメトリックを選択することができます。複数の学習モデルにおける特徴の分布は、一貫していなければなりません。
#### データの可視化
    テスト結果をファブリカム・レジデンス・チームに提供する必要があります。あなたは、結果を提示するのに役立つデータの可視化を作成します。
    モデルの診断テスト評価を行うために、ROC（Receiver Operating Characteristic）曲線を作成する必要があります。2クラス決定林モジュールと2クラス決定ジャングルモジュールを互いに比較するために、Azure Machine Learning StudioでROC曲線を作成するための適切な方法を選択する必要があります。

### Q. 46
    AccessibilityToHighway 列の欠損データを置換する必要があります。
    Clean Missing Data モジュールをどのように構成する必要がありますか？回答するには、回答領域で適切なオプションを選択します。

    OPTION:A
    OPTION:B
1. A
2. B
<details><div>
    答え：2
    ボックス1：MICEを利用した置き換え
        MICEを使用して置換します。このオプションは，各欠損値について，統計文献に "Multivariate Imputation using Chained Equations" または "Multiple Imputation by Chained Equations" として記述されている方法を用いて計算される新しい値を割り当てる．多重代入法では、欠損値を埋める前に、データ中の他の変数を用いて、欠損データのある各変数が条件付きでモデル化される。
        シナリオ 両方のデータセットのAccessibilityToHighway列が欠損値を含んでいます。欠損値を埋める前に、データ中の他の変数を用いて条件付きでモデル化されるように、欠損データを新しいデータで置き換えなければならない。
    ボックス2：伝搬
        Cols with all missing values は、すべての欠損値の列が出力に保存されるべきかどうかを示す。
</div></details>

### Q. 47
    あなたは、データの可視化の要件に従って、診断テスト評価のための可視化を作成する必要があります。
    どの 3 つのモジュールを順番に使用することを推奨しますか？回答するには、モジュール一覧から該当するモジュールを回答エリアに移動し、正しい順序で並べる。
1. 
2. 
3. 
4. 
<details><div>
    答え：2
    ステップ1：スイープクラスタリング
        まず、"Tune Model Hyperparameters "モジュールを使って、検討中の各モデルに最適なパラメータセットを選択することから始めます。
        Tune Model Hyperparameters "モジュールの興味深い点は、チューニングの結果を出力するだけでなく、Train Modelも出力することです。
    ステップ2：モデルの訓練
    ステップ3: モデルの評価
        シナリオ テスト結果をFabrikam Residencesのチームに提供する必要があります。あなたは、結果を提示するのに役立つデータの可視化を作成します。
        モデルの診断テスト評価を実施するために、ROC（Receiver Operating Characteristic）曲線を作成する必要があります。2クラス決定林モジュールと2クラス決定ジャングルモジュールを互いに比較するために、Azure Machine Learning StudioでROC曲線を作成するための適切な方法を選択する必要があります。
</div></details>

### Q. 48
    Age列に外れ値が存在するかどうかを視覚的に識別し、外れ値を除去する前に外れ値を定量化する必要があります。
    あなたはどの3つのAzure Machine Learning Studioモジュールを使用する必要がありますか？各正解は、ソリューションの一部を提示します。
    注：各正解の選択には1点の価値があります。
1. 
2. 
3. 
4. 
<details><div>
    答え：1,2,3
    B: 全体像を把握するために、summarize data モジュールを使用することができます。モジュールを追加し、視覚化する必要があるデータセットに接続します。
    A: Outliersを視覚的に素早く特定する方法の1つは、散布図を作成することです。
    C: Azure MLで外れ値を扱う最も簡単な方法は、Clip Valuesモジュールを使用することです。指定した閾値以上または以下のデータ値を特定し、オプションで置き換えることができます。
    Azure Machine Learning StudioのClip Valuesモジュールを使用すると、指定した閾値以上または以下のデータ値を識別し、オプションで置き換えることができます。これは、外れ値を削除したり、平均値、定数、または他の代替値に置き換えたりする場合に便利です。
</div></details>

### Q. 49
    テスト要件に従ってデータを分割する方法を特定する必要があります。
    どのプロパティを選択する必要がありますか？回答するには、回答欄の適切な選択肢を選択してください。
    OPTION:A
    OPTION:B
1. A
2. B
<details><div>
    答え：1
シナリオ テスト
    Azure Machine Learning StudioのPartition and Sampleモジュールを使用して、サンプリングに基づくデータセットの複数のパーティションを作成する必要があります。
    ボックス 1: フォールドに割り当てる
        データセットをサブセットに分割する場合は、Assign to folds オプションを使用します。このオプションは、クロスバリデーションのためにカスタム数のフォールドを作成したい場合や、行をいくつかのグループに分割したい場合にも便利です。
        Not Head：Headモードを使用して、最初のn行のみを取得します。このオプションは、少数の行でパイプラインをテストし、データのバランスやサンプリングが必要ない場合に便利です。
        サンプリングしない Samplingオプションは、単純無作為抽出または層化無作為抽出をサポートします。これは、テスト用のより小さな代表的なサンプルデータセットを作成したい場合に便利です。
    ボックス2：均等にパーティション
        パーティション分割の方法を指定します。各パーティションにどのようにデータを割り当てるか、以下のオプションで指定します。
        均等に分割する。このオプションは、各パーティションに同じ数の行を配置するために使用します。出力パーティションの数を指定するには、［均等に分割するフォールドの数を指定］テキストボックスに整数を入力します。
</div></details>

### Q. 50
    データセットの構造を一致させるために、Edit Metadata モジュールを設定する必要があります。
    どの設定オプションを選択する必要がありますか？回答するには、回答欄で適切なオプションを選択してください。
    OPTION:A
    OPTION:B
1. A
2. B
<details><div>
    答え：2
    ボックス1：浮動小数点
        中央値には浮動小数点が必要
    シナリオ 最初の調査では、MedianValue の列を除けば、2 つのデータセットの構造は同じであることがわかった。小さい方のParisデータセットにはテキスト形式のMedianValueが含まれ、大きい方のLondonデータセットには数値形式のMedianValueが含まれる。
    ボックス2: 変更なし
    注：選択した列の値をカテゴリとして扱うことを指定するには、Categoricalオプションを選択します。
        例えば、0,1,2という数字を含む列があったとして、その数字が実際には「喫煙者」「非喫煙者」「不明」を意味することが分かっている場合です。このような場合、その列をカテゴリーとしてフラグを立てることで、その値が数値計算には使用されず、データのグループ化にのみ使用されることを保証することができます。
</div></details>

### Q. 51
    ワークスペースにAzure Machine Learningサービスのデータストアを作成します。データストアには、次のファイルが含まれています。
        /data/2018/Q1.csv
        /データ/2018/Q2.csv
        /データ/2018/Q3.csv
        /データ/2018/Q4.csv
        /data/2019/Q1.csv （データ/2019/Q1.csv
    すべてのファイルには、以下の形式でデータが格納されています。
        ID,F1,F2,I
        1,1,2,0
        2,1,1,1
        3,2,1,0
        4,2,2,1
    以下のコードを実行する。

    あなたは、次のコードを使用して、training_dataという名前のデータセットを作成し、すべてのファイルから単一のデータフレームにデータをロードする必要があります。

    解決策 次のコードを実行してください。

    解答は目標を達成しているか？
1. はい
2. いいえ
<details><div>
    答え：2
    代わりに2つのファイルパスでパスを定義します。データがクレンジングされないので、Dataset.Tabular_from_delimeted を使用する。
</div></details>

### Q. 52
    ワークスペースにAzure Machine Learningサービスのデータストアを作成します。データストアには、次のファイルが含まれています。
        /data/2018/Q1.csv
        /データ/2018/Q2.csv
        /データ/2018/Q3.csv
        /データ/2018/Q4.csv
        /data/2019/Q1.csv （データ/2019/Q1.csv
    すべてのファイルには、以下の形式でデータが格納されています。
        ID,F1,F2,I
        1,1,2,0
        2,1,1,1
        3,2,1,0
        4,2,2,1
    以下のコードを実行する。
    
    あなたは、次のコードを使用して、training_dataという名前のデータセットを作成し、すべてのファイルから単一のデータフレームにデータをロードする必要があります。
    解決策 次のコードを実行してください。

    解答は目標を達成しているか？
1. はい
2. いいえ
<details><div>
    答え：2
    2つのファイルパスを使用します。
    Dataset.File.from_files の代わりに Dataset.Tabular_from_delimeted を使用することで、データが浄化されません。
注意
    FileDatasetは、データストアや公開URLの単一ファイルまたは複数ファイルを参照します。もしデータが既にクリーンアップされ、学習実験に使用できる状態であれば、ファイルをFileDatasetオブジェクトとして計算機にダウンロードまたはマウントすることができます。
    TabularDatasetは、提供されたファイルやファイルのリストをパースしてデータを表形式で表現します。これにより、データをpandasやSpark DataFrameに実体化することができるため、ノートブックから離れることなく、使い慣れたデータ準備や学習ライブラリで作業することができます。.csv, .tsv, .parquet, .jsonlファイルや、SQLクエリの結果からTabularDatasetオブジェクトを作成することができます。
</div></details>

### Q. 53
    ワークスペースにAzure Machine Learningサービスのデータストアを作成します。データストアには、次のファイルが含まれています。
        /data/2018/Q1.csv
        /データ/2018/Q2.csv
        /データ/2018/Q3.csv
        /データ/2018/Q4.csv
        /data/2019/Q1.csv （データ/2019/Q1.csv
    すべてのファイルには、以下の形式でデータが格納されています。
        ID,F1,F2,I
        1,1,2,0
        2,1,1,1
        3,2,1,0
        4,2,2,1
    以下のコードを実行する。
    
    あなたは、次のコードを使用して、training_dataという名前のデータセットを作成し、すべてのファイルから単一のデータフレームにデータをロードする必要があります。
    解決策 次のコードを実行してください。

    解答は目標を達成しているか？
1. はい
2. いいえ
<details><div>
    答え：1
    ファイルパスを2つ使用します。
    データがクレンジングされないので、Dataset.Tabular_from_delimetedを使用します。
注意
    TabularDatasetは、提供されたファイルまたはファイルのリストをパースすることによって、表形式でデータを表現します。これは、データをpandasやSpark DataFrameに実体化する機能を提供し、ノートブックから離れることなく、使い慣れたデータ準備や学習ライブラリで作業することができます。.csv, .tsv, .parquet, .jsonlファイルや、SQLクエリの結果からTabularDatasetオブジェクトを作成することができます。
</div></details>

### Q. 54
    Azure Machine Learning の Hyperdrive 機能を使用して、モデルのトレーニング時に最適なハイパーパラメータ値を決定することを計画しています。
    Hyperdrive を使用して、以下のハイパーパラメーター値の組み合わせを試す必要があります。
        learning_rate: 0.001 から 0.1 の間の任意の値
        batch_size: 16、32、または64
    Hyperdrive実験のための探索空間を設定する必要があります。
    どの2つのパラメータ式を使うべきですか？各正解は解決策の一部を提示する。
    注：各正解は1ポイントに相当します。
1. 
2. 
3. 
4. 
<details><div>
    答え：2,4
    B: 連続ハイパーパラメータは、連続した値の範囲に渡る分布として指定されます。サポートされている分布は以下の通りです。
        uniform(low, high) - lowとhighの間に一様に分布する値を返す。
    D：離散ハイパーパラメータは，離散値の中から選択するものとして指定されます．
        1つまたは複数のカンマ区切りの値
        範囲オブジェクト
        任意のリストオブジェクト
</div></details>

### Q. 55
    Azure Machine Learningのワークスペースには、real_estate_dataというデータセットがあります。データセット内のデータのサンプルは次のとおりです。
    あなたは、自動化された機械学習を使用して、価格列を予測するための最適な回帰モデルを見つけたいと考えています。
    あなたは、Azure Machine Learning SDKを使用して自動化された機械学習実験を構成する必要があります。
    あなたはどのようにコードを完成させるべきですか？回答するには、回答領域で適切なオプションを選択します。
    OPTION:A
    OPTION:B
    注：各正解の選択は1点の価値があります。
1. 
2. 
3. 
4. 
<details><div>
    答え：1
    ボックス 1: training_data
        実験に使用する学習データ。トレーニングデータとラベル列（オプションでサンプル重み列）を含む必要がある。training_dataを指定する場合は、label_column_nameパラメータも指定する必要がある。
    ボックス2：validation_data
        検証用データを用意する。この場合、1つのデータファイルから始めて、それをトレーニングセットとバリデーションセットに分けるか、バリデーションセット用に別のデータファイルを用意することができます。どちらの場合でも、AutoMLConfigオブジェクトのvalidation_dataパラメータは、検証セットとして使用するデータを割り当てます。
        例として、次のコード例では、datasetに含まれるデータのうち、どの部分を学習と検証に使用するかを明示的に定義しています。

        dataset = Dataset.Tabular.from_delimited_files(data)
        training_data, validation_data = dataset.random_split(percentage=0.8, seed=1)
        automl_config = AutoMLConfig(compute_target = aml_remote_compute,

                                    task = '分類',

                                    primary_metric = 'AUC_weighted',

                                    training_data = training_data,

                                    validation_data = validation_data,

                                    label_column_name = 'クラス'.

                                    )
    ボックス3：label_column_name
        label_column_name。
        ラベルカラムの名前です。入力データが pandas.DataFrame でカラム名を持たない場合、代わりにカラムインデックスを整数値で指定することができます。
        このパラメータは training_data と validation_data パラメータに適用される。
不正解です。
    X: 実験中にパイプラインをフィッティングする際に使用するトレーニング機能です。この設定は非推奨となっています。代わりにtraining_dataとlabel_column_nameを使用してください。
    Y: 実験中にパイプラインをフィッティングする際に使用するトレーニングラベル。これは、モデルが予測する値です。この設定は非推奨です。代わりにtraining_dataとlabel_column_nameを使用してください。
    X_valid。実験中にパイプラインのフィッティングを行う際に使用する検証機能。
    指定する場合は、y_validまたはsample_weight_validも指定する必要があります。
    Y_valid。実験中にパイプラインのフィッティングを行う際に使用するバリデーションラベル。
    X_validとy_validの両方を一緒に指定する必要がある。
    exclude_nan_labels: ラベルにNaN値が含まれる行を除外するかどうか。デフォルトはTrue。
    y_max: y_max (float)
    回帰実験における y の最大値。y_min と y_max の組み合わせは、入力データ範囲に基づいてテストセットメトリクスを正規化するために使用される。指定しない場合、最大値はデータから推測される。
</div></details>

### Q. 56
    Python スクリプトを使用して、Azure Machine Learning 実験を実行する予定です。スクリプトは、実験実行コンテキストへの参照を作成し、ファイルからデータをロードし、ラベル列の一意の値のセットを識別し、実験実行を完了します。

        from azureml.core import Run
        import pandas as pd
        run = Run.get_context()
        data = pd.read_csv('data.csv')
        label_vals = data['label'].unique()

        ＊ ここにメトリクスを記録するコードを追加

        run.complete()

    実験では、データ中のユニークラベルを、後でレビューできるように、ランのメトリクスとして記録する必要があります。
    コメントで示された時点で、ユニークラベルの値をランのメトリクスとして記録するコードをスクリプトに追加する必要があります。
    解決策 コメントを次のコードに置き換えます。

    run.uproad_file('outsouts/labels.csv', './data.csv')

    解決策は目標を達成しましたか？
1. はい
2. いいえ
<details><div>
    答え：2
    label_vals はユニークなラベルを持ち（label_vals = data['label'].unique() というステートメントから）、それはログに記録されなければならない。
注意してください。
    代わりに、run_log 関数を使用して、label_vals の内容をログに記録してください。
</div></details>

### Q. 57
    Python スクリプトを使用して、Azure Machine Learning 実験を実行する予定です。スクリプトは、実験実行コンテキストへの参照を作成し、ファイルからデータをロードし、ラベル列の一意の値のセットを識別し、実験実行を完了します。

        from azureml.core import Run
        import pandas as pd
        run = Run.get_context()
        data = pd.read_csv('data.csv')
        label_vals = data['label'].unique()

        ＊ ここにメトリクスを記録するコードを追加

        run.complete()

    実験では、データ中のユニークラベルを、後でレビューできるように、ランのメトリクスとして記録する必要があります。
    コメントで示された時点で、ユニークラベルの値をランのメトリクスとして記録するコードをスクリプトに追加する必要があります。
    解決策 コメントを次のコードに置き換えます。
        run.log_table('Label Values', label_vals)
    この解決策は、目標を達成していますか？
1. はい
2. いいえ
<details><div>
    答え：2
    その代わり、run_log 関数を使用して、label_vals に内容を記録します。
</div></details>

### Q. 58
    Python スクリプトを使用して、Azure Machine Learning 実験を実行する予定です。スクリプトは、実験実行コンテキストへの参照を作成し、ファイルからデータをロードし、ラベル列の一意の値のセットを識別し、実験実行を完了します。

        from azureml.core import Run
        import pandas as pd
        run = Run.get_context()
        data = pd.read_csv('data.csv')
        label_vals = data['label'].unique()

        ＊ ここにメトリクスを記録するコードを追加

        run.complete()

    実験では、データ中のユニークラベルを、後でレビューできるように、ランのメトリクスとして記録する必要があります。
    コメントで示された時点で、ユニークラベルの値をランのメトリクスとして記録するコードをスクリプトに追加する必要があります。
    解決策 コメントを次のコードに置き換えます。
        for label_val in label_vals:
          run.log('Label Values', label_val)
    この解決策は、目標を達成していますか？
1. はい
2. いいえ
<details><div>
    答え：1
    run_log関数は、label_valsに内容を記録するために使用されます。
</div></details>

### Q. 59
    ビジネスアプリケーションで使用されるバッチ式推論パイプラインを公開します。
    アプリケーション開発者は、公開されたパイプラインのRESTインターフェイスにどの情報を送信し、どの情報を返すべきかを知る必要があります。
    RESTリクエストで要求され、公開パイプラインから応答として返される情報を特定する必要があります。
    RESTリクエストでどの値を使用し、レスポンスでどの値を期待するか？回答するには、回答領域で適切な選択肢を選択します。
    注：正しい各選択肢は1点の価値があります。
1. 
2. 
3. 
4. 
<details><div>
    答え：2,3,5
    Box 1: OAuthベアラートークンを含むJSON
        リクエストに認証ヘッダを指定する
        RESTエンドポイントからパイプラインを実行するには、OAuth2 Bearerタイプの認証ヘッダが必要です。
    ボックス2：実験名を含むJSON
        実験名を持つJSONペイロードオブジェクトを追加します。
    ボックス3：ランIDを含むJSON
        実行を開始するためのリクエストを作成します。レスポンス辞書からIdキーにアクセスし、ランIDの値を取得するコードを記述します。
</div></details>

### Q. 60
    畳み込みニューラルネットワークモデルを複数のエポックにわたって学習させ、各エポック後に検証損失をログに記録するスクリプトを作成します。このスクリプトには、バッチサイズと学習率に関する引数が含まれています。
    試してみたいバッチサイズと学習率の値のセットを特定します。
    Azure Machine Learning を使用して、検証損失が最も小さいモデルをもたらすバッチサイズと学習率の組み合わせを見つける必要があります。
    どうすればよいでしょうか？
1. 
2. 
3. 
4. 
<details><div>
    答え：5
</div></details>
