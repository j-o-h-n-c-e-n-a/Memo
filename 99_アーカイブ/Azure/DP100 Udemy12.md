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
    答え：2
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
1. 
2. 
3. 
4. 
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
1. 
2. 
3. 
4. 
<details><div>
    答え：2
    Azure Container Instancesは、テストや開発用のコンピュートターゲットとして使用できます。48GB以下のRAMを必要とする、CPUベースの低スケールなワークロードに使用します。
</div></details>

### Q. 13
    あなたは分類タスクを解いています。
    データセットはアンバランスです。
    あなたは、分類の精度を向上させるためにAzure Machine Learning Studioのモジュールを選択する必要があります。
    あなたはどのモジュールを使用する必要がありますか？
1. 
2. 
3. 
4. 
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
1. 
2. 
3. 
4. 
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
1. 
2. 
3. 
4. 
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
1. 
2. 
3. 
4. 
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
1. 
2. 
3. 
4. 
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


    あなたは、次のシナリオのためにどのコンピュート環境を使用するかを決定する必要があります。
    どのコンピュートタイプを使用する必要がありますか？答えとしては、適切な計算環境を適切なシナリオにドラッグしてください。各コンピュート環境は、1回だけ使うことも、2回以上使うことも、全く使わないこともできます。ペイン間でスプリットバーをドラッグしたり、コンテンツを表示するためにスクロールする必要がある場合があります。
1. 
2. 
3. 
4. 
<details><div>
    答え：1,3
    Azure Machine Learningでは、コンピュートターゲットと総称されるさまざまなリソースや環境でモデルを学習させることができます。コンピュートターゲットは、ローカルマシン、またはAzure Machine Learning Compute、Azure HDInsight、リモート仮想マシンなどのクラウドリソースにすることができます。
</div></details>

### Q. 24
    STANDARD_D1仮想マシンイメージを使用して、ComputeOneというAzure Machine Learningコンピュートターゲットを作成します。
    Azure Machine Learningのワークスペースを参照するwasというPython変数を定義する。以下のPythonコードを実行する。


    次の各ステートメントについて、そのステートメントが真である場合は、[はい]を選択します。そうでない場合は、[いいえ]を選択します。
1. 
2. 
3. 
4. 
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

    OPTION:B
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
1. 
2. 
3. 
4. 
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

    OPTION:B
1. A
2. B
<details><div>
    答え：1
    steps パラメータには、ステップの配列を指定します。複数のステップを持つパイプラインを構築するには、この配列にステップを順番に並べます。
</div></details>

### Q. 28
    Azure ML SDKを使った実験の準備中で、computeを作成する必要があります。次のコードを実行します。


    以下の各ステートメントについて、そのステートメントが真である場合は、Yes を選択します。そうでない場合は、「いいえ」を選択します。
1. 
2. 
3. 
4. 
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
1. 
2. 
3. 
4. 
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
1. 
2. 
3. 
4. 
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
1. 
2. 
3. 
4. 
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
1. 
2. 
3. 
4. 
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
1. 
2. 
3. 
4. 
<details><div>
    答え：1,4

</div></details>

### Q. 35
    次のコードを使用して、Azure Machine Learning リアルタイム Web サービスとしてモデルをデプロイします。


    デプロイは失敗します。
    あなたは、デプロイ中に実行されたアクションを決定し、失敗した特定のアクションを識別することによって、デプロイの失敗をトラブルシュートする必要があります。
    あなたはどのコードセグメントを実行する必要がありますか？
1. 
2. 
3. 
4. 
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
1. 
2. 
3. 
4. 
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
1. 
2. 
3. 
4. 
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

    実験の実行が完了した後、Runオブジェクトのget_metricsメソッドを使用して返すことができるrow_countという名前のメトリックとして、行数を記録する必要があります。
    どのようなコードを使用すればよいでしょうか？
1. 
2. 
3. 
4. 
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
1. 
2. 
3. 
4. 
<details><div>
    答え：3
    もしローカルコンピュータに既存のConda環境があるなら、環境オブジェクトを作成するためにサービスを使うことができます。この戦略を使うことで、ローカルの対話型環境をリモートで実行する際に再利用することができます。
</div></details>

### Q. 43
    Azure Machine Learning サービスで機械学習モデルを学習するためのスクリプトを作成する。
    以下のコードを実行し、エスティメーターを作成します。
    以下の各ステートメントについて、そのステートメントが真である場合はYesを選択する。そうでない場合は、「いいえ」を選択します。
1. 
2. 
3. 
4. 
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
1. 
2. 
3. 
4. 
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
    あなたは、モデルを訓練し、デプロイのためのリアルタイムパイプラインを準備します。
    あなたは、推論パイプラインをWebサービスとして公開する必要があります。
    どのコンピュートタイプを使用する必要がありますか？
1. 
2. 
3. 
4. 
<details><div>
    答え：2
    Azure Kubernetes Service（AKS）は、リアルタイム推論を利用することができます。
</div></details>

### Q. 46
    Azure ML SDKを使用して、バッチ推論パイプラインを作成します。以下のコードを実行し、パイプラインのパラメータを設定します。

    あなたは、パイプラインの実行から出力を取得する必要があります。
    あなたはどこで出力を見つけるのだろうか？
1. 
2. 
3. 
4. 
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
1. 
2. 
3. 
4. 
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
1. 
2. 
3. 
4. 
<details><div>
    答え：1,2,3
    回答はこちら ABC 正しい選択肢です。
    A . Azure ML SDKライブラリを使用し、名前、subscription_id、resource_group、およびlocationパラメータでWorkspace.createメソッドを呼び出すPythonコードを実行します。
    B . Microsoft.MachineLearningServices/ワークスペース資源とその依存関係を含むAzureリソース管理テンプレートを使用します。C
     . Azure Command Line Interface（CLI）をAzure Machine Learning extensionと一緒に使用して、-nameと-locationパラメーターでaz group create関数を呼び出し、次にaz ml workspace create関数でワークスペース名とリソースグループにCwとCgパラメーターを指定する。
     D . Azure Machine Learning studioに移動し、ワークスペースを作成します。E . Azure ML SDK ライブラリを使用し、名前、subscription_id、resource_group パラメータを指定して Workspace.get メソッドを呼び出す Python コードを実行する。
</div></details>

### Q. 50
    TSV ファイルのセットを含む Azure blob コンテナがあります。Azure blob コンテナは、Azure Machine Learning サービスのワークスペースのデータストアとして登録されています。各TSVファイルは、同じデータスキーマを使用する。
    あなたは、Azure Machine Learning SDK for Python を使用して、すべての TSV ファイルのデータをまとめて集約し、集約したデータを Azure Machine Learning ワークスペースのデータセットとして登録することを計画しています。
    以下のコードを実行します。

    以下の各ステートメントについて、そのステートメントが真である場合は、[はい]を選択します。そうでない場合は、[いいえ]を選択します。
1. 
2. 
3. 
4. 
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
1. 
2. 
3. 
4. 
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
1. 
2. 
3. 
4. 
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
1. 
2. 
3. 
4. 
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
1. 
2. 
3. 
4. 
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
1. 
2. 
3. 
4. 
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
1. 
2. 
3. 
4. 
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
1. 
2. 
3. 
4. 
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
1. 
2. 
3. 
4. 
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
1. 
2. 
3. 
4. 
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
### Q. 
1. 
2. 
3. 
4. 
<details><div>
    答え：
</div></details>
