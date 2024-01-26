## 1
### Q. 質問1: 未回答
クラウドベースのデータ処理システムで費用最適化を設計する場合、Cloud Storage のストレージの費用を管理するための推奨される戦略は何ですか?
1. 　
2. 
3. 
4. Nearline Storage クラスを使用
<details><div>
    答え：4
説明
Cloud Storage でストレージ費用を管理するための推奨される戦略は、アクセス頻度の低いデータには Nearline Storage クラスを使用し、コスト効率とアクセシビリティのバランスを取ることです。[詳細](https://cloud.google.com/storage/docs/storage-classes#nearline)
</div></details>

### Q. 質問2: 未回答
データから有意義な洞察を得るための設計を行う場合、クラウドベースの環境で適切な視覚化ツールと手法を選択するための推奨されるプラクティスは何ですか?
1. 　明確で意味のあるラベルを活用
2. 
3. 
4. 
<details><div>
    答え：1
説明
適切な視覚化ツールと手法を選択するための推奨されるプラクティスは、クラウドベースの環境で明確で意味のあるラベルを活用し、分析情報の解釈可能性とコミュニケーションを強化することです。[詳細](https://cloud.google.com/solutions/data-visualization-and-business-intelligence)
</div></details>

### Q. 質問3: 未回答
カスタム データ処理ロジックが必要なシナリオでは、データ処理パイプラインの一部としてカスタム機械学習モデルを構築およびデプロイするのに適した Google Cloud サービスはどれですか?
1. 　
2. 
3. 
4. AI Platform
<details><div>
    答え：4
説明
AI Platform は、データ処理パイプラインの一部としてカスタム機械学習モデルを構築してデプロイするのに適しており、機械学習モデルのトレーニングと提供のためのマネージド環境を提供します。[詳細](https://cloud.google.com/ai-platform)
</div></details>

### Q. 質問4: 未回答
機械学習モデルのトレーニングに AI Platform Training を使用しています。トレーニングジョブを送信するときに「--config」フラグを設定する目的は何ですか?
1. 　
2. 
3. 
4. ハイパーパラメータの定義
<details><div>
    答え：4
説明
AI Platform Training の「--config」フラグは、トレーニング ジョブを送信するときにハイパーパラメータ値を含む構成ファイルを指定するために使用されます。[AI Platform トレーニング ハイパーパラメータの設定](https://cloud.google.com/ai-platform/training/docs/training-jobs#config)
</div></details>

### Q. 質問5: 未回答
Cloud Dataflow パイプラインでデータの信頼性を設計する場合、ストリーミング データのデータ要素を管理する上でのウィンドウの役割と、処理効率への影響は何ですか?
1. 　
2. 
3. データ要素間でコンテキストを維持
4. 
<details><div>
    答え：３
説明
Cloud Dataflow のウィンドウ処理は、ストリーミング データ内のデータ要素を時間ベースのウィンドウに整理して管理し、管理可能な間隔内で並列処理できるようにすることで処理効率に影響を与えます。[詳細](https://cloud.google.com/dataflow/docs/concepts/windowing)
</div></details>

### Q. 質問6: 未回答
Google Cloud Dataflow で安全なデータ処理を行うためのソリューションを設計しています。処理中に保存データの機密性と整合性を確保するために、どのようなセキュリティ機能を実装できますか?
1. 　
2. 
3. 
4. Dataflow シャッフル暗号化
<details><div>
    答え：４
説明
Google Cloud Dataflow では、Dataflow シャッフル暗号化を実装することで、処理中の保存データの機密性と整合性を確保できます。この機能は、シャッフル操作中にデータを暗号化し、データ処理パイプラインの全体的なセキュリティを強化します。詳細については、[データフローシャッフル暗号化](https://cloud.google.com/dataflow/docs/security)を参照してください。
</div></details>

### Q. 質問7: 未回答
AI Platform Training で、カスタム ワーカー プールを使用してトレーニング ジョブを送信するときに「--worker-pool-spec」フラグを使用する目的は何ですか?
1. 　ワーカープール構成のカスタマイズ
2. 
3. 
4. 
<details><div>
    答え：１
説明
AI Platform Training の「--worker-pool-spec」フラグは、カスタム ワーカー プールを使用してトレーニング ジョブを送信するときに、ワーカー プールの構成をカスタマイズするために使用されます。[AI Platform トレーニング ワーカー プール](https://cloud.google.com/ai-platform/training/docs/training-jobs#custom-worker-pool)
</div></details>

### Q. 質問8: 未回答
AI Platform Prediction でモデル監視を実装している。デプロイされたモデル バージョンの監視を構成するときに '--sampling-rate' フラグを使用する目的は何ですか?
1. 　
2. サンプリングされた予測リクエストのレートを制御
3. 
4. 
<details><div>
    答え：２
説明
AI Platform Prediction の「--sampling-rate」フラグは、モデル監視の設定時にサンプリングされた予測リクエストのレートを制御するために使用され、分析のために予測のサブセットをモニタリングできます。[AI Platform 予測モデル監視サンプリング](https://cloud.google.com/ai-platform/prediction/docs/monitoring)
</div></details>

### Q. 質問9: 未回答
機械学習ワークフローでデータを前処理するために Cloud Dataflow を使用している。Dataflow パイプラインの実行時に「--temp_location」フラグを指定する目的は何ですか?
1. 　
2. 
3. 
4. パイプライン実行用の一時保存場所を指定
<details><div>
    答え：４
説明
Cloud Dataflow の「--temp_location」フラグは、パイプライン実行用の一時保存場所を指定するために使用され、中間データと一時データの場所を提供します。[Cloud Dataflow の一時保存場所](https://cloud.google.com/dataflow/docs/guides/specifying-exec-params#temp_location)
</div></details>

### Q. 質問10: 未回答
BigQuery SQL クエリの PARTITION BY 句の目的は何ですか?
1. 　パーティション内でウィンドウ関数を実行する
2. 
3. 
4. 
<details><div>
    答え：１
説明
BigQuery の PARTITION BY 句は、結果セットのパーティション内でウィンドウ関数を実行するために使用されます。
</div></details>

### Q. 質問11: 未回答
Google Cloud Dataprep で安全なデータ処理を行うためのソリューションを設計しています。データ準備プロセス中に機密データを保護するために、どのようなセキュリティ機能を活用できますか?
1. 　
2. 列レベルのマスキング
3. データリネージ トラッキング
4. 
<details><div>
    答え：２，３
説明
Google Cloud Dataprep では、列レベルのマスキングやデータリネージ トラッキングなどのセキュリティ機能を活用して、データ準備プロセス中に機密データを保護できます。列レベルのマスキングは特定のデータへのアクセスを制御するのに役立ち、データ系列の追跡は、データが処理パイプラインをどのように移動するかを理解するのに役立ちます。詳細については、[Dataprep のセキュリティ機能](https://cloud.google.com/dataprep/docs/html/Security/Security-Features)を参照してください。
</div></details>

### Q. 質問12: 未回答
データ処理システムにおける Cloud Functions の主な目的は何ですか?
1. 　
2. 
3. 
4. イベントドリブン関数にサーバーレス コンピューティング
<details><div>
    答え：４
説明
Cloud Functions は、データ処理システムのイベントドリブン関数にサーバーレス コンピューティングを提供します。これにより、イベントに応答してコードを実行し、需要に基づいて自動的にスケーリングできます。詳細: [Cloud Functions の概要](https://cloud.google.com/functions/docs)
</div></details>

### Q. 質問13: 未回答
Cloud Spanner のアクセス制御を設定しています。データのセキュリティとコンプライアンスのコンテキストにおける監査ログの目的は何ですか?
1. 　
2. データベースへのアクセスと変更を記録
3. 
4. 
<details><div>
    答え：２
説明
Cloud Spanner の監査ログは、データベースへのアクセスと変更を記録するために不可欠です。操作の詳細なログを提供し、誰がデータベースにアクセスし、どのようなアクションが実行されたかを追跡することで、規制要件に準拠し、データセキュリティを強化するのに役立ちます。詳細については、[監査ログ](https://cloud.google.com/spanner/docs/audit-logging)を参照してください。
</div></details>

### Q. 質問14: 未回答
データ処理タスクにカスタムの依存関係とランタイム環境が必要なシナリオでは、コンテナ化されたアプリケーションの構築とデプロイに適した Google Cloud サービスはどれですか?
1. 　
2. Cloud Run
3. 
4. 
<details><div>
    答え：２
説明
Cloud Run は、カスタム依存関係とランタイム環境を使用してコンテナ化されたアプリケーションを構築およびデプロイするのに適しており、データ処理タスクに柔軟性を提供します。[詳細](https://cloud.google.com/run/docs)
</div></details>

### Q. 質問15: 未回答
データ処理環境での Cloud Storage Transfer Service の主な目的は何ですか?
1. 　 Cloud Storage バケット間のデータ転送
2. 
3. 
4. 
<details><div>
    答え：１
説明
Cloud Storage Transfer Service は、データ処理システム内の Cloud Storage バケット間のデータ転送を自動化およびスケジュールするために使用されます。これにより、データ移動の管理プロセスが簡素化されます。詳細:[転送サービスの概要](https://cloud.google.com/storage-transfer/docs)
</div></details>

### Q. 質問16: 未回答
Cloud Dataflow パイプラインでスケーラビリティを設計する場合、イベント時の処理で遅れて到着したデータを処理するには、どのようなアプローチをお勧めしますか?
1. 　別のウィンドウで再処理
2. 
3. 
4. 
<details><div>
    答え：１
説明
Cloud Dataflow で遅れて到着したデータを処理するには、別のウィンドウで再処理して、すべてのデータを正確かつ包括的に分析することをおすすめします。[詳細](https://cloud.google.com/dataflow/docs/concepts/event-time)
</div></details>

### Q. 質問17: 未回答
Cloud Storage で費用最適化を設計する場合、失われた場合に再生成できるデータを扱う際のストレージ費用を管理するためのベスト プラクティスは何ですか?
1. 　
2. Nearline Storage クラスを使用
3. 
4. 
<details><div>
    答え：２
説明
Cloud Storage で Nearline Storage クラスを使用することは、失われた場合に再生成できるデータを処理する際のストレージ費用を管理するためのベスト プラクティスであり、費用効率とアクセシビリティのバランスが取れています。[詳細](https://cloud.google.com/storage/docs/storage-classes#nearline)
</div></details>

### Q. 質問18: 未回答
Apache Hadoop を使用して、大規模なデータセットのバッチ処理を含むデータ処理パイプラインを設計する必要があります。このシナリオに最適な Google Cloud サービスはどれですか?
1. 　
2. Cloud Dataproc
3. 
4. 
<details><div>
    答え：２
説明
Cloud Dataproc は、フルマネージドの Apache Hadoop および Apache Spark サービスであり、データ処理パイプラインで Apache Hadoop を使用して大規模なデータセットのバッチ処理に適しています。スケーラブルで費用対効果の高いソリューションを提供します。詳細: [Cloud Dataproc の概要](https://cloud.google.com/dataproc/docs)
</div></details>

### Q. 質問19: 未回答
機械学習モデルの配信に AI Platform Prediction を使用している。予測インスタンスの自動スケーリングを構成する際の '--min-nodes' フラグと '--max-nodes' フラグの目的は何ですか?
1. 　
2. 自動スケーリングの制限を設定
3. 
4. 
<details><div>
    答え：２
説明
AI Platform Prediction で「--min-nodes」フラグと「--max-nodes」フラグを設定するのは、自動スケーリングの制限を設定し、予測サービスのインスタンス(レプリカ)の最小数と最大数を制御するためのものです。[AI Platform 予測の自動スケーリング](https://cloud.google.com/ai-platform/prediction/docs/autoscaling)
</div></details>

### Q. 質問20: 未回答
依存関係を持つタスクのオーケストレーションと調整を必要とするデータ処理パイプラインを構築しています。このシナリオに最適な Google Cloud サービスはどれですか?
1. 　
2. 
3. 
4. Cloud Composer 
<details><div>
    答え：４
説明
Cloud Composer は、データ処理システムで依存関係を持つタスクのオーケストレーションと調整に適した、フルマネージドのワークフロー オーケストレーション サービスです。さまざまなサービスやツールの統合をサポートします。詳細: [Cloud Composer ドキュメント](https://cloud.google.com/composer/docs)
</div></details>

### Q. 質問21: 未回答
Cloud Storage ベースのデータ処理システムでデータ セキュリティを設計する場合、保存データを保護するための推奨プラクティスは何ですか?
1. 　
2. 
3. 顧客提供のキーを使用して保存データを暗号化する
4. 
<details><div>
    答え：３
説明
Cloud Storage ベースのデータ処理システムで保存されているデータを保護するための推奨方法は、お客様が用意した鍵を使用してデータを暗号化し、追加のセキュリティ レイヤを提供することです。[詳細](https://cloud.google.com/storage/docs/encryption)
</div></details>

### Q. 質問22: 未回答
Cloud Dataflow パイプラインでは、イベント時間データの処理におけるウォーターマークの役割と、正確なウィンドウ処理の確保にどのように貢献しますか?
1. 　
2. イベント時間の進行状況を追跡
3. 
4. 
<details><div>
    答え：２
説明
Cloud Dataflow のウォーターマークは、イベント時間の進行状況を追跡することでイベント時間データの処理に重要な役割を果たし、正確なウィンドウ処理の確保に貢献し、すべての関連データがいつ処理されたかをシステムが理解できるようにします。[詳細](https://cloud.google.com/dataflow/docs/concepts/event-time)
</div></details>

### Q. 質問23: 未回答
Cloud Bigtable に保存されているデータに対して、きめ細かなアクセス制御を実装する必要があります。どの機能を使うべきか?
1. 　
2. 
3. IAMポリシー
4. 
<details><div>
    答え：３
説明
Cloud Bigtable の IAM(Identity and Access Management)ポリシーは、データのきめ細かなアクセス制御を実装するために使用されます。データベースにアクセスできるユーザーと、そのユーザーが実行できるアクションを指定できます。詳細: [Cloud Bigtable IAM](https://cloud.google.com/bigtable/docs/access-control)
</div></details>

### Q. 質問24: 未回答
Apache Kafka を使用したリアルタイムのイベントストリーミングと処理を必要とするデータ処理パイプラインを設計しています。このシナリオに最も適した Google Cloud サービスはどれですか?
1. 　
2. Cloud Pub/Sub 
3. 
4. 
<details><div>
    答え：
説明
Cloud Pub/Sub は、データ処理パイプラインでのリアルタイムのイベント ストリーミングと処理用に設計されています。イベントデータの取り込みと配信をサポートするメッセージングサービスを提供します。詳細: [Cloud Pub/Sub の概要](https://cloud.google.com/pubsub/docs)
</div></details>

### Q. 質問25: 未回答
機械学習モデルを使用したリアルタイムの異常検出を必要とするデータ処理パイプラインを設計しています。このシナリオに最も適した Google Cloud サービスはどれですか?
1. 　
2. 
3. 
4. Cloud AI Platform
<details><div>
    答え：４
説明
Cloud AI Platform は、機械学習モデルのデプロイと管理を目的として設計されているため、データ処理パイプラインで機械学習を使用したリアルタイムの異常検出に適しています。スケーラブルでサーバーレスな環境を提供します。詳細: [Cloud AI Platform の概要](https://cloud.google.com/ai-platform/docs)
</div></details>

### Q. 質問26: 未回答
モバイル アプリケーションやウェブ アプリケーション向けに、フルマネージドでスケーラブルなサーバーレスの NoSQL データベースを提供する Google Cloud サービスはどれですか?
1. 　
2. Cloud Firestore
3. 
4. 
<details><div>
    答え：２
説明
Cloud Firestore は、モバイルおよびウェブ アプリケーション向けに設計された、フルマネージドでスケーラブルなサーバーレスの NoSQL データベースです。柔軟なデータモデルを提供し、自動スケーリングをサポートします。詳細: [Cloud Firestore の概要](https://cloud.google.com/firestore/docs)
</div></details>

### Q. 質問27: 未回答
Cloud Composer では、複数のタスクを含む機械学習ワークフローを設計します。Apache Airflow と Cloud Composer の 'BranchPythonOperator' の目的は何ですか?
1. 　
2. 
3. 条件に基づいてタスクをトリガー
4. 
<details><div>
    答え：３
説明
Apache Airflow と Cloud Composer の「BranchPythonOperator」は、条件に基づいてタスクをトリガーするために使用され、ワークフローの実行フローを動的に制御できます。[Cloud Composer BranchPythonOperator] (クラウド コンポーザー ブランチ パイソン オペレーター)(https://cloud.google.com/composer/docs/how-to/using/operators#branchpythonoperator)
</div></details>

### Q. 質問28: 未回答
クラウドベースのデータ処理システムでデータ プライバシーを重視して設計する場合、機密データを含む Cloud Storage バケットへのアクセス制御を管理するには、どのような方法が推奨されますか?
1. 　
2. きめ細かなアクセス制御を使用
3. 
4. 
<details><div>
    答え：２
説明
機密データを含む Cloud Storage バケットへのアクセス制御を管理するには、きめ細かなアクセス制御を使用して、安全で制御されたデータ処理を行うことをおすすめします。[詳細](https://cloud.google.com/storage/docs/access-control)
</div></details>

### Q. 質問29: 未回答
AI Platform Prediction では、モデル バージョンをデプロイするときに「--model-type」フラグを使用する目的は何ですか?
1. 　
2. 
3. 予測ランタイム フレームワークを構成
4. 
<details><div>
    答え：３
説明
AI Platform Prediction の「--model-type」フラグは、デプロイ プロセス中に予測ランタイム フレームワークを構成するために使用されます。[AI Platform 予測モデルタイプ](https://cloud.google.com/ai-platform/prediction/docs/deploying-models#model-type)
</div></details>

### Q. 質問30: 未回答
機械学習モデルの分散トレーニングに AI Platform Training を使用している。トレーニングジョブを送信するときの「--worker-machine-type」フラグの目的は何ですか?
1. 　
2. 
3. ワーカー ノードのマシンタイプを指定
4. 
<details><div>
    答え：３
説明
AI Platform Training の「--worker-machine-type」フラグは、分散トレーニング ジョブを送信するときにワーカー ノードのマシンタイプを指定するために使用されます。[AI Platform Training Worker マシンタイプ](https://cloud.google.com/ai-platform/training/docs/training-jobs)
</div></details>

### Q. 質問31: 未回答
Google Cloud Storage のアクセス制御を設定しています。データのセキュリティとコンプライアンスのコンテキストにおけるアクセス制御リスト(ACL)の目的は何ですか?
1. 　
2. 
3. 
4. オブジェクトごとのアクセス制御を定義
<details><div>
    答え：４
説明
Google Cloud Storage のアクセス制御リスト(ACL)は、オブジェクトごとのアクセス制御を定義するために使用されます。これにより、バケット内の個々のオブジェクトにアクセスできるユーザーまたはグループを指定し、オブジェクトレベルの権限をきめ細かく制御できます。詳細については、[アクセス制御リストの使用](https://cloud.google.com/storage/docs/access-control/lists)を参照してください。
</div></details>

### Q. 質問32: 未回答
ビジュアル インターフェイスを使用したデータ変換とクレンジングを含むデータ処理パイプラインの設計を担当します。このシナリオに最適な Google Cloud サービスはどれですか?
1. 　
2. 
3. Cloud Dataprep
4. 
<details><div>
    答え：３
説明
Cloud Dataprep は、データ処理パイプラインのビジュアル インターフェースを使用したデータの変換とクレンジング用に設計されています。これは、データの探索と準備のための視覚的でインタラクティブなエクスペリエンスを提供します。詳細: [Cloud Dataprep の概要](https://cloud.google.com/dataprep/docs)
</div></details>

### Q. 質問33: 未回答
機械学習モデルの配信に AI Platform Prediction を使用している。デプロイプロセス中に「--framework」フラグを設定する目的は何ですか?
1. 　
2. 
3. 予測ランタイム フレームワークを構成
4. 
<details><div>
    答え：３
説明
AI Platform Prediction で「--framework」フラグを設定するのは、デプロイ プロセス中に予測ランタイム フレームワークを構成するためのものです。[AIプラットフォーム予測フレームワーク](https://cloud.google.com/ai-platform/prediction/docs/deploying-models#framework)
</div></details>

### Q. 質問34: 未回答
データポータルのレポートで、さまざまな商品カテゴリの収益を比較します。この分析に最も適したチャートの種類はどれですか?
1. 　
2. 棒グラフ
3. 
4. 
<details><div>
    答え：２
説明
棒グラフは、データポータルのレポートでさまざまな商品カテゴリの収益を比較するのに最適です。
</div></details>

### Q. 質問35: 未回答
データ処理で急速に変化するデータのリアルタイム分析が必要なシナリオでは、低レイテンシのアクセスでストリーミング データを取り込んで処理するのに適した Google Cloud サービスはどれですか?
1. 　
2. Cloud Dataflow
3. 
4. 
<details><div>
    答え：２
説明
Cloud Dataflow は、低レイテンシのアクセスでストリーミング データを取り込んで処理するのに適しており、急速に変化するデータをリアルタイムで分析するためのフルマネージドのサーバーレス ソリューションを提供します。[詳細](https://cloud.google.com/dataflow/docs)
</div></details>

### Q. 質問36: 未回答
Cloud Composer を使用して機械学習ワークフローを設計しており、特定のタイムスケジュールに基づいてタスクをトリガーする必要があります。このタスクに適した Cloud Composer コンポーネントはどれですか?
1. 　
2. タイムセンサー
3. 
4. 
<details><div>
    答え：２
説明
Cloud Composer の「TimeSensor」は、Apache Airflow と Cloud Composer で特定のタイムスケジュールに基づいてタスクをトリガーするのに適しています。[Cloud Composer TimeSensor] (クラウド コンポーザー タイムセンサー)(https://cloud.google.com/composer/docs/how-to/using/sensors#timesensor)
</div></details>

### Q. 質問37: 未回答
データポータルで折れ線グラフを作成して、ウェブサイトのトラフィックの推移を示すとします。このグラフのディメンションと指標として何を使用する必要がありますか?
1. 　ディメンションとして日付を使用し、指標としてトラフィック
2. 
3. 
4. 
<details><div>
    答え：１
説明
時間の経過に伴うウェブサイトトラフィックの傾向を示す折れ線グラフを作成するには、ディメンションとして日付を使用し、指標としてトラフィックを使用します。
</div></details>

### Q. 質問38: 未回答
最も低コストでデータをアーカイブするために設計された Cloud Storage クラスはどれですか?
1. 　
2. アーカイブ
3.  
4. 
<details><div>
    答え：２
説明
Cloud Storage のアーカイブ ストレージ クラスは、最も低コストでデータをアーカイブできるように設計されています。めったにアクセスされず、長期保存が必要なデータに適しています。追加情報: [Cloud Storage Classes](https://cloud.google.com/storage/docs/storage-classes)
</div></details>

### Q. 質問39: 未回答
SQL クエリを使用したリアルタイムのデータ変換とクレンジングを含むデータ処理パイプラインを設計する必要があります。このシナリオに最適な Google Cloud サービスはどれですか?
1. 　
2. 
3. BigQuery
4. 
<details><div>
    答え：３
説明
BigQuery は、サーバーレスで拡張性の高いデータ ウェアハウスであり、データ処理パイプラインでリアルタイムのデータ変換とクレンジングのための SQL クエリを実行できます。アドホックなクエリと分析に適しています。詳細: [BigQuery SQL リファレンス](https://cloud.google.com/bigquery/docs/reference/standard-sql)
</div></details>

### Q. 質問40: 未回答
低レイテンシのアクセスでストリーミング データのリアルタイム分析が必要なシナリオでは、ストリーミング データをリアルタイムで取り込んで処理するのに適した Google Cloud サービスはどれですか?
1. 　
2. 
3. Cloud Dataflow
4. 
<details><div>
    答え：３
説明
Cloud Dataflow は、ストリーミング データをリアルタイムで取り込んで処理するのに適しており、大規模なデータセットのリアルタイム分析のためのフルマネージドのサーバーレス ソリューションを提供します。[詳細](https://cloud.google.com/dataflow/docs)
</div></details>

### Q. 質問41: 未回答
機械学習ワークフローのバッチ処理ステップに Cloud Dataflow を使用している。Dataflow パイプラインを実行する際の「--max-num-workers」フラグの目的は何ですか?
1. 　
2. ワーカー ノードの最大数を制御
3. 
4. 
<details><div>
    答え：２
説明
Cloud Dataflow の「--max-num-workers」フラグは、Dataflow パイプライン内のワーカー ノードの最大数を制御するために使用され、リソースを効果的に管理できるようにします。[Cloud Dataflow Max Num Workers] (クラウドデータフロー最大ワーカー数)(https://cloud.google.com/dataflow/docs/guides/specifying-exec-params#max-num-workers)
</div></details>

### Q. 質問42: 未回答
Cloud SQL のアクセス制御を設定しています。オンプレミスまたは Google Cloud の外部で実行されているアプリケーションのデータベース接続を保護するというコンテキストにおける Cloud SQL Proxy の役割は何ですか?
1. 　アプリケーションのユーザー ID を検証
2. 
3. 
4. 
<details><div>
    答え：１
説明
Google Cloud SQL の Cloud SQL Proxy は、オンプレミスまたは Google Cloud の外部で実行されているアプリケーションのユーザー ID を検証するために使用されます。データベースをパブリック インターネットに公開することなく、Cloud SQL データベースに安全に接続する方法を提供し、セキュリティとコンプライアンスを強化します。詳細については、[Cloud SQL Proxy](https://cloud.google.com/sql/docs/mysql/sql-proxy)のドキュメントをご覧ください。
</div></details>

### Q. 質問43: 未回答
AI Platform Prediction のコンテキストで、モデル バージョンのデプロイ時に「--min-replicas」フラグを指定する目的は何ですか?
1. 　
2. レプリカ(インスタンス)の最小数を制御
3. 
4. 
<details><div>
    答え：２
説明
AI Platform Prediction の「--min-replicas」フラグは、予測サービス内のレプリカ(インスタンス)の最小数を制御することで、自動スケーリングの制限を設定するために使用されます。[AI Platform 予測の自動スケーリング](https://cloud.google.com/ai-platform/prediction/docs/autoscaling)
</div></details>

### Q. 質問44: 未回答
データ処理ワークロードが変化するシナリオでは、Apache Spark クラスタと Apache Hadoop クラスタでデータ処理ジョブを実行するのに適した Google Cloud サービスはどれですか?
1. 　Cloud Dataproc
2. 
3. 
4. 
<details><div>
    答え：１
説明
Cloud Dataproc は、データ処理ワークロードが変化するシナリオで、Apache Spark クラスタと Apache Hadoop クラスタを使用してデータ処理ジョブを実行するのに適しています。[詳細](https://cloud.google.com/dataproc/docs)
</div></details>

### Q. 質問45: 未回答
データ処理システムにおいて、クラウドデータ損失防止(DLP)の目的は何ですか?
1. 　
2. 
3. 機密データの漏洩を防ぐ
4. 
<details><div>
    答え：３
説明
Cloud Data Loss Prevention(DLP)は、データ処理環境での機密データの漏洩を防ぐために使用されます。機密情報を特定して保護し、プライバシー規制へのコンプライアンスを確保するのに役立ちます。詳細: [Cloud DLP の概要](https://cloud.google.com/dlp/docs)
</div></details>

### Q. 質問46: 未回答
AI Platform Training を使用して、TensorFlow で機械学習モデルをトレーニングしています。トレーニングジョブを送信する際の「--runtime-version」フラグの目的は何ですか?
1. 　
2. TensorFlow ランタイム バージョンを指定
3. 
4. 
<details><div>
    答え：２
説明
AI Platform Training の「--runtime-version」フラグは、トレーニング ジョブの送信時に TensorFlow ランタイム バージョンを指定するために使用され、目的の TensorFlow バージョンとの互換性を確保します。[AI Platform Training ランタイム バージョン](https://cloud.google.com/ai-platform/training/docs/training-jobs#runtime-version)
</div></details>

### Q. 質問47: 未回答
AI Platform Prediction で機械学習モデルのモニタリングを設定しています。デプロイされたモデル バージョンの監視を構成する場合の '--target-field' フラグの目的は何ですか?
1. 　
2. データセット内のターゲット特徴量を指定
3. 
4. 
<details><div>
    答え：２
説明
AI Platform Prediction の「--target-field」フラグは、モデル監視の設定時にデータセット内のターゲット特徴量を指定するために使用されます。これは、特定のターゲット変数に対するモデルのパフォーマンスを監視するのに役立ちます。[AI Platform 予測対象分野](https://cloud.google.com/ai-platform/prediction/docs/monitoring)
</div></details>

### Q. 質問48: 未回答
データ処理ワークロードが変化するシナリオでは、Cloud Storage、Pub/Sub、または HTTP トリガーからのイベントに応答できるサーバーレス関数の作成に適した Google Cloud サービスはどれですか?
1. 　
2. 
3. Cloud Functions 
4. 
<details><div>
    答え：３
説明
Cloud Functions は、Cloud Storage、Pub/Sub、HTTP トリガーからのイベントに応答できるサーバーレス関数の作成に適しており、データ処理ワークロードに柔軟性とスケーラビリティを提供します。[詳細](https://cloud.google.com/functions/docs)
</div></details>

### Q. 質問49: 未回答
Cloud SQL のデータ アクセス制御を実装している。データのセキュリティとコンプライアンスの観点から、限定公開の Google アクセスの目的は何ですか?
1. 　インスタンスはパブリック IP アドレスなしで Google サービスにアクセス
2. 
3. 
4. 
<details><div>
    答え：１
説明
Cloud SQL の限定公開の Google アクセスを使用すると、インスタンスはパブリック IP アドレスなしで Google サービスにアクセスできます。これにより、公共のインターネットへの露出を減らし、潜在的な攻撃ベクトルを制限し、他の Google サービスとの安全な通信を促進することで、セキュリティとコンプライアンスが強化されます。詳細については、[限定公開の Google Access for Cloud SQL](https://cloud.google.com/sql/docs/mysql/private-ip)をご覧ください。
</div></details>

### Q. 質問50: 未回答
機械学習モデルの提供に AI Platform Prediction を使用しており、予測インスタンスの数を制御して費用を最適化したい。モデルバージョンのデプロイ中に '--initial-replica-count' フラグを設定する目的は何ですか?
1. 　
2. レプリカ(インスタンス)の初期数を定義
3. 
4. 
<details><div>
    答え：２
説明
AI Platform Prediction の「--initial-replica-count」フラグは、モデル バージョンをデプロイする際にレプリカ(インスタンス)の初期数を定義するために使用され、コストとリソースの管理に役立ちます。[AI Platform 予測の初期レプリカ数](https://cloud.google.com/ai-platform/prediction/docs/deploying-models#initial-replica-count)
</div></details>

### Q. 質問51: 未回答
新しいモデル バージョンが AI Platform Prediction にデプロイされるたびに Cloud Functions の関数をトリガーするプロセスを自動化したい。このイベントドリブンなワークフローを自動化するために、パイプラインに統合できる Google Cloud サービスはどれですか?
1. 　
2. 
3. Cloud Pub/Sub
4. 
<details><div>
    答え：３
説明
Cloud Pub/Sub をパイプラインに統合して、新しいモデル バージョンが AI Platform Prediction にデプロイされるたびに Cloud Functions の関数をトリガーするイベントドリブン ワークフローを設定できます。[クラウド Pub/Sub](https://cloud.google.com/pubsub)
</div></details>

### Q. 質問52: 未回答
データポータルでリアルタイム データを視覚化する必要があります。これを実現するための推奨されるアプローチは何ですか?
1. 　
2. 
3. 
4. データポータル API を使用して、データソースからのリアルタイム更新を有効にします
<details><div>
    答え：４
説明
データポータルでリアルタイム データを視覚化するには、データポータル API を使用して、データソースからのリアルタイム更新を有効にします。
</div></details>

### Q. 質問53: 未回答
Cloud Dataprep のデータ処理ジョブでデータの信頼性を設計する場合、一貫性のあるデータ変換を確保する上でスキーマはどのような役割を果たしますか?
1. 　
2. 
3. データの構造と形式を検証
4. 
<details><div>
    答え：３
説明
Cloud Dataprep データ処理ジョブのスキーマは、データの構造と形式を検証し、データの品質と整合性を維持することで、一貫性のあるデータ変換を確保する上で重要な役割を果たします。[詳細](https://cloud.google.com/dataprep/docs/html/Schema-Pages_57341425)
</div></details>

### Q. 質問54: 未回答
Cloud Dataflow パイプラインでは、Dataflow Shuffle サービスの役割と、データ処理の効率をどのように向上させるのでしょうか?
1. 　
2. 並列処理を容易にします
3. 
4. 
<details><div>
    答え：２
説明
Cloud Dataflow の Dataflow Shuffle サービスは、並列処理を容易にし、ワーカー ノード間での効率的なシャッフルとデータの再分散を可能にすることで、データ処理の効率を高めます。[詳細](https://cloud.google.com/dataflow/docs/concepts/shuffle)
</div></details>

### Q. 質問55: 未回答
Cloud Composer を使用して複数のタスクをオーケストレーションする機械学習ワークフローを設計しています。Apache Airflow と Cloud Composer の「ShortCircuitOperator」の目的は何ですか?
1. 　条件に基づいてタスクをスキップ
2. 
3. 
4. 
<details><div>
    答え：１
説明
Apache Airflow と Cloud Composer の「ShortCircuitOperator」は、条件に基づいてタスクをスキップするために使用され、ワークフローの実行フローを動的に制御できます。[Cloud Composer ShortCircuitOperator] (クラウド コンポーザー ショートサーキット オペレーター)(https://cloud.google.com/composer/docs/how-to/using/operators#shortcircuitoperator)
</div></details>

### Q. 質問56: 未回答
データ処理環境での Cloud Armor の主な目的は何ですか?
1. 　DDoS 攻撃からの保護を提供し、データ処理システムのウェブ アプリケーション ファイアウォールとして機能
2. 
3. 
4. 
<details><div>
    答え：１
説明
Cloud Armor は DDoS 攻撃からの保護を提供し、データ処理システムのウェブ アプリケーション ファイアウォールとして機能します。アプリケーションやサービスをサイバー脅威から保護し、トラフィックが急増した場合の可用性を確保します。詳細: [Cloud Armor の概要](https://cloud.google.com/armor/docs)
</div></details>

### Q. 質問57: 未回答
クラウドベースのデータ処理システムにおいて、機密データのセキュリティを確保するために BigQuery データセットへのアクセス制御を管理するには、どのような方法が推奨されますか?
1. 　
2. 
3. 
4. きめ細かなアクセス制御を実装
<details><div>
    答え：４
説明
BigQuery データセットにきめ細かなアクセス制御を実装することは、機密データのセキュリティを確保し、データ処理の制御とセキュリティを提供するためのアクセス管理に推奨されるアプローチです。[詳細](https://cloud.google.com/bigquery/docs/table-access-controls)
</div></details>

### Q. 質問58: 未回答
CPU とメモリの使用率に基づく自動スケーリングを必要とするデータ処理パイプラインを構築しています。データ処理システム内の仮想マシンの自動スケーリングを提供する Google Cloud サービスはどれですか?
1. 　
2. 
3. Compute Engine
4. 
<details><div>
    答え：３
説明
Compute Engine では、データ処理システムの CPU とメモリの使用率に基づいて自動スケーリングを行う仮想マシンを作成できます。これにより、インフラストラクチャに対する柔軟性と制御が提供されます。詳細: [Compute Engine Autoscaler](https://cloud.google.com/compute/docs/autoscaler)
</div></details>

### Q. 質問59: 未回答
データ処理システムにおいて、Cloud Spanner の主な目的は何ですか?
1. 　
2. 
3. グローバルに分散された水平方向にスケーラブルなデータベース
4. 
<details><div>
    答え：３
説明
Cloud Spanner は、データ処理システムで高性能で一貫性のあるデータ処理を行うために設計された、グローバルに分散された水平方向にスケーラブルなデータベースです。強力な一貫性とグローバルトランザクション機能を提供します。詳細: [Cloud Spanner の概要](https://cloud.google.com/spanner/docs)
</div></details>

### Q. 質問60: 未回答
Cloud Dataprep を使用したクラウドベースのデータ処理システムにおいて、データのプロファイリングの目的は何か、データの品質保証にどのように貢献するのか。
1. 　
2. データの分布と品質を分析
3. 
4. 
<details><div>
    答え：２
説明
Cloud Dataprep でのデータのプロファイリングでは、データの分布と品質を分析し、データセット内の異常、パターン、潜在的な問題を特定することで、データの品質保証に貢献します。[詳細](https://cloud.google.com/dataprep/docs/html/ProfilePage_57341635)
</div></details>

### Q. 質問61: 未回答
ハイパーパラメータの調整に AI Platform Training を使用している。ハイパーパラメータ調整ジョブを設定する際の「--parameter-server-machine-type」フラグの目的は何ですか?
1. 　マスターノードのマシンタイプを指定
2. 
3. 
4. 
<details><div>
    答え：１
説明
AI Platform Training の「--parameter-server-machine-type」フラグは、ハイパーパラメータ調整ジョブを構成する際にマスターノードのマシンタイプを指定するために使用されます。[AI Platform トレーニングのハイパーパラメータ調整](https://cloud.google.com/ai-platform/training/docs/hyperparameter-tuning)
</div></details>

### Q. 質問62: 未回答
AI Platform Prediction に機械学習モデルをデプロイする場合、「--instance-type」フラグを設定する意味は何ですか?
1. 　
2. 
3. 予測に使用するマシンタイプを定義
4. 
<details><div>
    答え：３
説明
AI Platform Prediction で「--instance-type」フラグを設定すると、予測に使用するマシンタイプを定義し、各予測インスタンスに割り当てられるリソースを設定できます。[AI Platform 予測インスタンス タイプ](https://cloud.google.com/ai-platform/prediction/docs/deploying-models#instance-type)
</div></details>

### Q. 質問63: 未回答
Google Cloud で安全なデータ処理を行うためのソリューションを設計しています。データセキュリティとコンプライアンスのコンテキストにおける顧客管理の暗号鍵(CMEK)の役割は何ですか?
1. 　
2. 
3. 暗号化レイヤを追加
4. 
<details><div>
    答え：３
説明
Google Cloud の顧客管理の暗号鍵(CMEK)は、保存データの暗号化レイヤを追加します。これにより、お客様は独自の暗号化キーを管理し、保存されたデータの制御とセキュリティを強化できます。詳細については、ドキュメントを参照してください: [顧客管理の暗号化キー](https://cloud.google.com/kms/docs/overview)
</div></details>

### Q. 質問64: 未回答
Cloud Storage 内のデータを保護する責任はお客様にあります。データセキュリティとコンプライアンスのコンテキストで顧客提供の暗号化キー(CSEK)を使用する目的は何ですか?
1. 　
2. 
3. 
4. 暗号化レイヤを追加
<details><div>
    答え：４
説明
Google Cloud Storage の顧客提供の暗号鍵(CSEK)は、保存データの暗号化レイヤを追加します。CSEKは、お客様が独自の暗号化キーを管理できるようにすることで、保存データの制御とセキュリティを強化し、データ保護要件への準拠に貢献します。詳細については、[お客様提供の暗号化キー](https://cloud.google.com/storage/docs/encryption#customer-supplied_encryption_keys)のドキュメントを参照してください。
</div></details>

### Q. 質問65: 未回答
ストリーミング データのリアルタイムの取り込みと処理を必要とするデータ処理パイプラインを構築しています。このシナリオでスケーラブルでフルマネージドのソリューションを提供する Google Cloud サービスはどれですか?
1. 　
2. Cloud Dataflow 
3. 
4. 
<details><div>
    答え：２
説明
Cloud Dataflow は、ストリーミング データをリアルタイムで取り込んで処理するように設計されています。これは、ストリーム処理とバッチ処理の両方に対応するスケーラブルで完全に管理されたソリューションを提供します。詳細: [Cloud Dataflow の概要](https://cloud.google.com/dataflow/docs)
</div></details>

### Q. 質問66: 未回答
Cloud Dataprep を使用したクラウドベースのデータ処理システムでは、結合レシピの目的と、複数のソースからのデータの結合にどのように貢献しますか?
1. 　
2. 指定された条件に基づいて複数のソースからのデータを結合
3. 
4. 
<details><div>
    答え：２
説明
Cloud Dataprep の結合レシピは、指定された条件に基づいて複数のソースからのデータを結合し、データ統合を容易にし、多様なデータセットにわたる包括的な分析を可能にします。[詳細](https://cloud.google.com/dataprep/docs/html/Join-Recipe_57341424)
</div></details>

### Q. 質問67: 未回答
データセットが大きいデータポータルのレポートのパフォーマンスを向上させることができるアクションは、次のうちどれですか?
1. 　
2. データ集計関数を使用
3. フィルターを適用してデータを制限
4. 
<details><div>
    答え：２，３
説明
パフォーマンスを向上させるには、フィルターを適用してデータを制限し、データ集計関数を使用して情報を意味のある方法で要約します。
</div></details>

### Q. 質問68: 未回答
データ処理システムにおいて、Cloud Memorystore の目的は何ですか?
1. 　
2. 
3. 
4. インメモリ データ キャッシュ
<details><div>
    答え：４
説明
Cloud Memorystore は、データ処理システムでのインメモリ データ キャッシュに使用されるフルマネージドのインメモリ データ ストア サービスです。これは、頻繁にアクセスされるデータをキャッシュするための高速でスケーラブルなソリューションを提供します。詳細: [Cloud Memorystore の概要](https://cloud.google.com/memorystore/docs)
</div></details>

### Q. 質問69: 未回答
クラウドベースのデータ処理システムでデータ セキュリティを設計する場合、機密データを含む Cloud Bigtable テーブルへのアクセス制御を管理するには、どのような方法が推奨されますか?
1. 　
2. 
3. きめ細かなアクセス制御を使用
4. 
<details><div>
    答え：３
説明
機密データを含む Cloud Bigtable テーブルへのアクセス制御を管理するには、きめ細かなアクセス制御を使用して、安全で制御されたデータ処理を行うことをおすすめします。[詳細](https://cloud.google.com/bigtable/docs/access-control)
</div></details>

### Q. 質問70: 未回答
Cloud Dataflow を使用して、機械学習ワークフローのストリーミング データを処理している。ストリーミング データ処理のコンテキストでウィンドウ処理を行う目的は何ですか?
1. 　
2. 時間ベースのデータ集計を管理
3. 
4. 
<details><div>
    答え：２
説明
Cloud Dataflow では、ストリーミング データ処理で時間ベースのデータ集計を管理するためにウィンドウが使用され、時間の経過に伴うデータのグループ化方法を定義できます。[クラウドデータフローウィンドウ](https://cloud.google.com/dataflow/docs/concepts/windowing)
</div></details>

### Q. 質問71: 未回答
低レイテンシと費用のバランスが取れた、アクセス頻度の低いデータ用に設計された Cloud Storage クラスはどれですか?
1. 　
2. 
3. Nearline ストレージ クラス
4. 
<details><div>
    答え：３
説明
Cloud Storage の Nearline ストレージ クラスは、低レイテンシとコストのバランスが取れた、アクセス頻度の低いデータ向けに設計されています。これは、アクセス頻度の低いデータに対して費用対効果の高いソリューションを提供します。追加情報: [Cloud Storage Classes](https://cloud.google.com/storage/docs/storage-classes)
</div></details>

### Q. 質問72: 未回答
Google Cloud Pub/Sub のデータを保護する責任はお客様にあります。メッセージの公開時と使用時に転送中のデータを暗号化するために、どのようなセキュリティ機能を有効にできますか?
1. 　TLS/SSL 暗号化
2. 
3. 
4. 
<details><div>
    答え：１
説明
Google Cloud Pub/Sub でメッセージを公開および消費するときに転送中のデータを暗号化するには、TLS/SSL 暗号化を有効にする必要があります。これにより、パブリッシャとサブスクライバーの間でメッセージが安全に送信され、不正アクセスや改ざんが防止されます。詳細については、[TLS/SSLによる通信の保護](https://cloud.google.com/pubsub/docs/secure-communication)を参照してください。
</div></details>

### Q. 質問73: 未回答
データ処理システムにおけるアプリケーションのパフォーマンスをリアルタイムでモニタリングおよびロギングするために設計された Google Cloud サービスはどれですか?
1. 　Cloud Trace
2. 
3. 
4. 
<details><div>
    答え：１
説明
Cloud Trace は、データ処理システムにおけるアプリケーションのパフォーマンスをリアルタイムでモニタリングし、ログを記録するために設計されています。これにより、要求をトレースし、アプリケーションの待機時間を把握できます。詳細: [Cloud Trace の概要](https://cloud.google.com/trace/docs)
</div></details>

### Q. 質問74: 未回答
Cloud Storage に保存されているデータに対して、きめ細かなアクセス制御を実装する必要があります。どの機能を使うべきか?
1. 　
2. 
3. 
4. IAMポリシー
<details><div>
    答え：４
説明
Cloud Storage の IAM(Identity and Access Management)ポリシーは、データに対するきめ細かなアクセス制御を実装するために使用されます。オブジェクトにアクセスできるユーザーと、そのユーザーが実行できるアクションを指定できます。詳細: [Cloud Storage IAM](https://cloud.google.com/storage/docs/access-control/iam)
</div></details>

### Q. 質問75: 未回答
Cloud Storage のアクセス制御を設定しています。データのセキュリティとコンプライアンスのコンテキストにおける VPC Service Controls の目的は何ですか?
1. 　
2. 
3. データ流出を防ぐ
4. 
<details><div>
    答え：３
説明
Google Cloud Storage の VPC Service Controls は、データ流出を防ぐために使用されます。VPC Service Controls は、オンプレミス ネットワークから Google Cloud までの範囲のアクセス境界を定義することで、承認されたソースからのみデータにアクセスできるようにし、全体的なセキュリティとコンプライアンスを強化します。詳細については、「VPC Service Controls の概要」(https://cloud.google.com/vpc-service-controls/docs/overview) を参照してください。
</div></details>

## 2
### Q. 質問1: 未回答
ハイパーパラメータの調整に AI Platform Training を使用している。ハイパーパラメーター調整ジョブを構成する際の '--parallel-trial-count' フラグの目的は何ですか?
1. 　
2. 
3. 
4. 同時試行(並列試行)の数を制御
<details><div>
    答え：4
説明
AI Platform Training の「--parallel-trial-count」フラグは、ハイパーパラメータ調整ジョブを構成する際に、同時試行(並列試行)の数を制御するために使用されます。[AI Platform Training 並列試行回数](https://cloud.google.com/ai-platform/training/docs/hyperparameter-tuning)
</div></details>

### Q. 質問2: 未回答
Cloud Storage のデータ アクセス制御を構成しています。データのセキュリティとコンプライアンスを確保するというコンテキストでのオブジェクト・バージョニングの目的は何ですか。
1. 　
2. 
3. オブジェクトの履歴バージョンを維持
4. 
<details><div>
    答え：
説明
Cloud Storage のオブジェクト バージョニングは、オブジェクトの履歴バージョンを維持し、必要に応じて以前のバージョンにアクセスして復元できるようにします。この機能は、偶発的な削除や変更に対する保護を提供し、データのセキュリティとコンプライアンスに貢献します。詳細については、ドキュメントを参照してください: [オブジェクトのバージョン管理](https://cloud.google.com/storage/docs/object-versioning)
</div></details>

### Q. 質問3: 未回答
分析のためのフルマネージドでスケーラブルなサーバーレス データ ウェアハウスを提供する Google Cloud サービスはどれですか?
1. 　
2. 
3. BigQuery 
4. 
<details><div>
    答え：
説明
BigQuery は、分析用に設計された、フルマネージドでスケーラブルなサーバーレス データ ウェアハウスです。これにより、データ処理システム内の大規模なデータセットに対して高速でSQLのようなクエリを実行できます。詳細: [BigQuery の概要](https://cloud.google.com/bigquery/docs)
</div></details>

### Q. 質問4: 未回答
あなたは、サードパーティの機械学習モデルを統合する必要があるデータ処理パイプラインを設計する任務を負っています。この統合を促進するのはどの Google Cloud サービスですか?
1. 　
2. 
3. Cloud AI Platform
4. 
<details><div>
    答え：
説明
Cloud AI Platform は、サードパーティ モデルを含む機械学習モデルをデプロイ、管理し、データ処理パイプラインに統合するように設計されています。モデルのトレーニングとデプロイのためのツールを提供します。詳細: [Cloud AI Platform の概要](https://cloud.google.com/ai-platform/docs)
</div></details>

### Q. 質問5: 未回答
ストリーミング データのリアルタイム処理に Cloud Dataflow を使用している。Cloud Dataflow の「ウィンドウ」の概念の目的は何ですか?
1. 時間ベースのデータ集計を管理
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataflow では、ストリーミング データ処理における時間ベースのデータ集計を管理するために「ウィンドウ」の概念が使用され、時間の経過に伴うデータのグループ化方法を定義できます。[クラウドデータフローウィンドウ](https://cloud.google.com/dataflow/docs/concepts/windowing)
</div></details>

### Q. 質問6: 未回答
Cloud Dataprep のデータ処理ジョブで保守性を考慮して設計する場合、変化するデータ要件に適応する上でスキーマの進化はどのような役割を果たしますか?
1. 　
2. 
3. 古いデータ形式との下位互換性が確保
4. 
<details><div>
    答え：
説明
Cloud Dataprep データ処理ジョブのスキーマの進化により、古いデータ形式との下位互換性が確保され、変化するデータ要件に適応することで保守性が向上します。[詳細](https://cloud.google.com/dataprep/docs/html/Schema-Pages_57341425)
</div></details>

### Q. 質問7: 未回答
バージョニング機能やロールバック機能を必要とする重要なデータを保存する際に、Cloud Storage でデータの耐久性を確保するためのベスト プラクティスは何ですか?
1. 　
2. オブジェクトのバージョニングを有効
3. 
4. 
<details><div>
    答え：
説明
Cloud Storage でオブジェクトのバージョニングを有効にすることは、データの耐久性を確保し、重要なデータにバージョニングとロールバック機能を提供するためのベスト プラクティスです。[詳細](https://cloud.google.com/storage/docs/object-versioning)
</div></details>

### Q. 質問8: 未回答
リアルタイム予測に AI Platform Prediction を使用する場合、「--min-instances」フラグと「--max-instances」フラグを設定する目的は何ですか?
1. 　
2. 
3. 
4. 自動スケーリングの制限を設定
<details><div>
    答え：
説明
AI Platform Prediction で「--min-instances」フラグと「--max-instances」フラグを設定するのは、自動スケーリングの制限を設定し、予測サービスのインスタンス(レプリカ)の最小数と最大数を制御するためのものです。[AI Platform 予測の自動スケーリング](https://cloud.google.com/ai-platform/prediction/docs/autoscaling)
</div></details>

### Q. 質問9: 未回答
AI Platform Prediction のコンテキストにおいて、予測の提供にグローバル エンドポイントよりも地域エンドポイントを使用する利点は何ですか?
1. 特定のリージョン内のレイテンシを低減
2. 
3. 
4. 
<details><div>
    答え：
説明
AI Platform Prediction でリージョン エンドポイントを使用すると、特定のリージョン内のレイテンシが低くなり、そのリージョンのユーザーへの予測の提供速度が向上します。[AI Platform 予測の地域エンドポイント](https://cloud.google.com/ai-platform/prediction/docs/regional-endpoints)
</div></details>

### Q. 質問10: 未回答
データのイベント駆動型処理を必要とするデータ処理パイプラインを構築しています。イベントドリブン アーキテクチャを促進する Google Cloud サービスはどれですか?
1. Cloud Pub/Sub
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Pub/Sub はイベントドリブン アーキテクチャ向けに設計されており、データ処理システムの独立したコンポーネント間のリアルタイム通信を可能にします。これは、サービスを分離およびスケーリングするためのメッセージング・サービスを提供します。詳細: [Cloud Pub/Sub ドキュメント](https://cloud.google.com/pubsub/docs)
</div></details>

### Q. 質問11: 未回答
データ処理でドキュメントのリアルタイム コラボレーションが必要なシナリオでは、共有データをリアルタイムで管理および同期するのに適した Google Cloud プロダクトはどれですか?
1. 　
2. Cloud Firestore
3. 
4. 
<details><div>
    答え：
説明
Cloud Firestore は、ドキュメントでのリアルタイム コラボレーションに適しており、共有データを管理および同期するためのサーバーレスでスケーラブルなグローバル分散型の NoSQL データベースを提供します。[詳細](https://cloud.google.com/firestore/docs)
</div></details>

### Q. 質問12: 未回答
Apache Spark を使用したデータのバッチ処理を含むデータ処理パイプラインを設計する必要があります。このシナリオに最適な Google Cloud サービスはどれですか?
1. 　
2. Cloud Dataproc
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataproc は、データのバッチ処理に適したフルマネージドの Apache Spark および Hadoop サービスです。これは、Sparkジョブを実行するためのスケーラブルでコスト効率の高いソリューションを提供します。詳細: [Cloud Dataproc の概要](https://cloud.google.com/dataproc/docs)
</div></details>

### Q. 質問13: 未回答
AI Platform Prediction でモデル監視を実装している。デプロイされたモデル バージョンの監視を構成するときに '--slice-columns' フラグを設定する目的は何ですか?
1. 　
2. 
3. 監視対象データのスライスに使用する列を定義
4. 
<details><div>
    答え：
説明
AI Platform Prediction の「--slice-columns」フラグは、モデル監視を構成する際に、監視対象データのスライスに使用する列を定義するために使用されます。[AI Platform 予測スライス列](https://cloud.google.com/ai-platform/prediction/docs/monitoring)
</div></details>

### Q. 質問14: 未回答
Cloud Bigtable でスケーラビリティを重視して設計する場合、データ アクセス パターンを最適化する上で行キーの設計にはどのような意味がありますか?
1. 　
2. 
3. クエリのパフォーマンスを向上
4. 
<details><div>
    答え：
説明
Cloud Bigtable の行キー設計は、データアクセスパターンを最適化し、データの分散方法とアクセス方法を決定することでクエリのパフォーマンスを向上させるために不可欠です。[詳細](https://cloud.google.com/bigtable/docs/schema-design)
</div></details>

### Q. 質問15: 未回答
Cloud Dataflow を使用したデータ処理パイプラインでは、イベント時間データの処理におけるウォーターマークの重要性と、ウォーターマークがウィンドウ処理にどのような影響を与えるか?
1. イベント時間の進行状況を追跡
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataflow のウォーターマークはイベント時間の進行状況を追跡し、データ処理パイプラインでの正確なウィンドウ処理とイベント時間データの効率的な処理を可能にします。[詳細](https://cloud.google.com/dataflow/docs/concepts/event-time)
</div></details>

### Q. 質問16: 未回答
クラウドベースのデータ処理システムでコスト最適化を設計する場合、サーバーレス環境で一時的な中間データを処理するためのベスト プラクティスは何ですか?
1. 　
2. 
3. 
4. 一時的な中間データに Cloud Storage を活用する
<details><div>
    答え：
説明
サーバーレス環境で一時的な中間データに Cloud Storage を活用することは、コストを最適化し、効率性とスケーラビリティを確保するためのベスト プラクティスです。[詳細](https://cloud.google.com/storage/docs/)
</div></details>

### Q. 質問17: 未回答
AI Platform Training で定期的なモデル トレーニング ジョブをスケジュールします。定期的なタスクの cron のようなスケジュールを定義および管理できる Google Cloud サービスは何ですか?
1. 　
2. Cloud Composer 
3. 
4. 
<details><div>
    答え：
説明
Cloud Composer では、定期的なタスクの cron のようなスケジュールを定義して管理できるため、AI Platform Training でのモデル トレーニング ジョブのスケジュール設定に適しています。[クラウドコンポーザー](https://cloud.google.com/composer)
</div></details>

### Q. 質問18: 未回答
Cloud Storage でデータの整合性を確保するためのソリューションを設計している。保存されているオブジェクトのデータ破損を検出して自動的に修復するには、どのような機能を使用できますか?
1. 　
2. 
3. 
4. チェックサム検証
<details><div>
    答え：
説明
Cloud Storage のデータ破損を検出して自動的に修復するには、チェックサム検証を使用します。チェックサムを有効にすると、保存されているオブジェクトの整合性を検証し、可能な場合は破損したデータを自動的に修復することで、データの整合性を確保できます。詳細については、[チェックサムと整合性チェック](https://cloud.google.com/storage/docs/performing-resumable-uploads#checksums-and-integrity-checks)を参照してください。
</div></details>

### Q. 質問19: 未回答
Google Cloud でデータ プライバシーのためのソリューションを設計しています。機密情報のコンテキストにおけるクラウドデータ損失防止(DLP)の目的は何ですか?
1. 　
2. 
3. 機密情報を分類して編集する
4. 
<details><div>
    答え：
説明
Google Cloud の Cloud Data Loss Prevention(DLP)は、機密情報を分類して編集するように設計されています。これは、秘匿化、マスキング、暗号化などのアクションを指定するポリシーを適用することで、機密データを識別して保護するのに役立ちます。これにより、データプライバシー規制への準拠が保証され、不注意による露出から保護されます。詳細については、ドキュメント「[Cloud DLP の概要](https://cloud.google.com/dlp/docs/overview)を参照してください。
</div></details>

### Q. 質問20: 未回答
Google Cloud リソースのモニタリングとアラートを設定しています。データのセキュリティとコンプライアンスを確保するという観点から、Cloud Security Scanner の目的は何ですか?
1. 　
2. 
3. ウェブ アプリケーションの脆弱性を特定
4. 
<details><div>
    答え：
説明
Google Cloud の Cloud Security Scanner は、ウェブ アプリケーションの脆弱性を特定するために設計されています。セキュリティの問題を検出して対処するのに役立ち、アプリケーションの全体的なセキュリティ体制に貢献します。詳細については、ドキュメントを参照してください: [Cloud Security Scanner の概要](https://cloud.google.com/security-scanner/docs/overview)
</div></details>

### Q. 質問21: 未回答
Google Cloud Storage にデータ アクセス制御を実装している。オブジェクトへの一時的なアクセスを許可する際の署名付きURLの役割は何ですか?
1. 　
2. オブジェクトへの一時的なアクセス権を付与
3. 
4. 
<details><div>
    答え：
説明
Google Cloud Storage の署名付き URL を使用すると、オブジェクトへの一時的なアクセス権を付与できます。これらは、Google Cloud Storage の認証情報を公開することなくリソースを共有するための安全な方法を提供します。詳細については、[署名付き URL](https://cloud.google.com/storage/docs/access-control/signed-urls) を参照してください。
</div></details>

### Q. 質問22: 未回答
データから有意義な洞察を得るための設計を行う際、適切な視覚化ツールと手法を選択するための推奨プラクティスは何ですか?
1. 　
2. 
3. 
4. 明確で意味のあるラベルを採用
<details><div>
    答え：
説明
データから有意義なインサイトをデザインするための推奨されるプラクティスは、視覚化ツールに明確で意味のあるラベルを採用し、インサイトの解釈可能性とコミュニケーションを強化することです。[詳細](https://cloud.google.com/solutions/data-visualization-and-business-intelligence)
</div></details>

### Q. 質問23: 未回答
BigQuery の EXTRACT 関数の目的は何ですか?
1. 日付や時刻からコンポーネント(年、月、日など)を抽出する
2. 
3. 
4. 
<details><div>
    答え：
説明
BigQuery の EXTRACT 関数は、日付や時刻からコンポーネント(年、月、日など)を抽出するために使用されます。
</div></details>

### Q. 質問24: 未回答
AI Platform Training を使用して、カスタムのマシンタイプでモデルをトレーニングする機械学習ワークフローを設計しています。トレーニングジョブを送信する際の「--master-machine-type」フラグの目的は何ですか?
1. 　
2. マスター ノードのマシンタイプを指定
3. 
4. 
<details><div>
    答え：
説明
AI Platform Training の「--master-machine-type」フラグは、トレーニング ジョブを送信するときにマスター ノードのマシンタイプを指定するために使用され、マスター ノードに割り当てられるリソースをカスタマイズできます。[AI Platform Training Master マシンタイプ](https://cloud.google.com/ai-platform/training/docs/training-jobs#master-machine-type)
</div></details>

### Q. 質問25: 未回答
Google Cloud プロジェクトのアクセス制御を実装しています。最小権限の原則を適用する上でのIDおよびアクセス管理(IAM)の役割は何ですか?
1. 　
2. 事前定義されたロールを割り当て
3. 
4. きめ細かなアクセス制御を定義
<details><div>
    答え：
説明
Google Cloud の Identity and Access Management(IAM)は、最小権限の原則を適用する上で重要な役割を果たします。IAMでは、事前定義されたロールを割り当て、きめ細かなアクセス制御を定義することで、ユーザーやサービスにタスクに必要な最小限の権限を付与し、不正アクセスのリスクを軽減できます。詳細については、「ロールについて」(https://cloud.google.com/iam/docs/understanding-roles)を参照してください。
</div></details>

### Q. 質問26: 未回答
データ処理システムにおいて、Cloud SQL Proxy の目的は何ですか?
1. 　
2. Cloud SQL インスタンスに安全に接続
3. 
4. 
<details><div>
    答え：
説明
Cloud SQL Proxy は、外部のアプリケーションやサービスから Cloud SQL インスタンスに安全に接続するために使用されます。暗号化された接続を提供し、認証プロセスを簡素化します。詳細: [Cloud SQL Proxy の概要](https://cloud.google.com/sql/docs/mysql/sql-proxy)
</div></details>

### Q. 質問27: 未回答
リアルタイムのストリーミング分析とイベント処理を必要とするデータ処理パイプラインを構築しています。どのサービスを使うべきですか?
1. 　
2. 
3. 
4. Cloud Dataflow 
<details><div>
    答え：
説明
Cloud Dataflow は、リアルタイムのストリーミング分析とイベント処理用に設計されています。これにより、パイプラインを通過するデータをリアルタイムで処理および分析できます。詳細: [Real-time Analytics with Cloud Dataflow](https://cloud.google.com/dataflow/docs/guides/feature-overview)
</div></details>

### Q. 質問28: 未回答
Cloud Storage に保存されているデータに対して、きめ細かなアクセス制御を実装する必要があります。どの機能を使うべきか?
1. アクセス制御リスト
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Storage のアクセス制御リスト(ACL)は、データのきめ細かなアクセス制御を実装するために使用されます。オブジェクトにアクセスできるユーザーと、そのユーザーが持つアクセスレベルを指定できます。追加情報: [Cloud Storage Access Control](https://cloud.google.com/storage/docs/access-control)
</div></details>

### Q. 質問29: 未回答
ディープ ラーニング モデルのトレーニングに AI Platform Training を使用しています。トレーニングジョブを送信するときに「--runtime-version」を指定する目的は何ですか?
1. 　
2. TensorFlow ランタイム バージョンを定義
3. 
4. 
<details><div>
    答え：
説明
AI Platform Training で「--runtime-version」を指定するのは、TensorFlow ランタイム バージョンを定義するためのもので、モデルのトレーニング中に指定したバージョンとの互換性を確保します。[AI Platform Training ランタイム バージョン](https://cloud.google.com/ai-platform/training/docs/runtime-version-list)
</div></details>

### Q. 質問30: 未回答
BigQuery スロットについて正しい記述は、次のうちどれですか?
1. スロット数はワークロードに基づいて動的に調整
2. 
3. 
4. スロットはクエリの実行容量を制御するために使用
<details><div>
    答え：
説明
BigQuery スロットはクエリの実行容量を制御するために使用され、スロット数はワークロードに基づいて動的に調整できます。
</div></details>

### Q. 質問31: 未回答
Kubeflow Pipelinesのコンテキストでは、機械学習モデルを構築してデプロイする際の「フェアリング」ライブラリの目的は何ですか?
1. 　
2. 
3. 
4. カスタムDockerコンテナを定義
<details><div>
    答え：
説明
Kubeflow Pipelinesの「fairing」ライブラリは、カスタムDockerコンテナを定義するために使用され、一貫性のある再現可能な方法で機械学習モデルの構築とデプロイを容易にします。[クーベフローフェアリング](https://www.kubeflow.org/docs/fairing/)
</div></details>

### Q. 質問32: 未回答
データ処理システムにおける Cloud Functions の主な目的は何ですか?
1. 　
2. イベントドリブン関数にサーバーレス コンピューティング
3. 
4. 
<details><div>
    答え：
説明
Cloud Functions は、データ処理システムのイベントドリブン関数にサーバーレス コンピューティングを提供します。これにより、イベントに応答してコードを実行し、需要に基づいて自動的にスケーリングできます。詳細: [Cloud Functions の概要](https://cloud.google.com/functions/docs)
</div></details>

### Q. 質問33: 未回答
クラウドベースのデータ処理システムで、クエリのパフォーマンスを最適化するために BigQuery テーブルでデータを分割するための推奨戦略は何ですか?
1. 　
2. 
3. 日付でパーティション分割
4. 
<details><div>
    答え：
説明
BigQuery テーブルを日付でパーティション分割することは、クエリのパフォーマンスを最適化するための推奨される戦略であり、関連するパーティションのみをスキャンして処理されるデータ量を減らすことができます。[詳細](https://cloud.google.com/bigquery/docs/partitioned-tables)
</div></details>

### Q. 質問34: 未回答
監視とトラブルシューティングのために、ログをほぼリアルタイムで分析するデータ処理パイプラインを設計する必要があります。このシナリオに最適な Google Cloud サービスはどれですか?
1. 　
2. 
3. 
4. Cloud Logging
<details><div>
    答え：
説明
Cloud Logging は、データ処理パイプラインでモニタリングとトラブルシューティングのためにログをほぼリアルタイムで分析できるように設計されています。これにより、ログを保存、検索、および分析できます。詳細: [Cloud Logging の概要](https://cloud.google.com/logging/docs)
</div></details>

### Q. 質問35: 未回答
低レイテンシと費用のバランスが取れた、アクセス頻度の低いデータ用に設計された Cloud Storage クラスはどれですか?
1. 　
2. 
3. 
4. Nearline ストレージ クラス
<details><div>
    答え：
説明
Cloud Storage の Nearline ストレージ クラスは、低レイテンシとコストのバランスが取れた、アクセス頻度の低いデータ向けに設計されています。これは、アクセス頻度の低いデータに対して費用対効果の高いソリューションを提供します。追加情報: [Cloud Storage Classes](https://cloud.google.com/storage/docs/storage-classes)
</div></details>

### Q. 質問36: 未回答
BigQuery に、ネストされた繰り返しフィールドを含むデータセットがあります。ネストされたフィールドを分析用に平坦化する正しいアプローチは何ですか?
1. 　
2. UNNEST 関数
3. 
4. 
<details><div>
    答え：
説明
BigQuery の UNNEST 関数は、ネストされたフィールドや繰り返されるフィールドをフラット化して分析するために使用されます。
</div></details>

### Q. 質問37: 未回答
AI Platform Prediction のコンテキストでは、モデルをデプロイする前に Google Cloud Console でモデル リソースを作成する目的は何ですか?
1. 　
2. 
3. 
4. アクセス権限を管理
<details><div>
    答え：
説明
AI Platform Prediction でモデルをデプロイする前に Google Cloud Console でモデル リソースを作成すると、アクセス権限を管理し、モデルをデプロイしてアクセスできるユーザーを指定できます。[AI Platform 予測モデル リソース](https://cloud.google.com/ai-platform/prediction/docs/deploying-models)
</div></details>

### Q. 質問38: 未回答
データ処理に大規模なバッチ処理が含まれるシナリオでは、バッチ処理タスクを複数のノードに分散して並列化するのに適した Google Cloud サービスはどれですか?
1. Cloud Dataproc
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataproc は、大規模なバッチ処理に適しており、タスクを複数のノードに分散して並列化することで、効率的でスケーラブルな処理を実現します。[詳細](https://cloud.google.com/dataproc/docs)
</div></details>

### Q. 質問39: 未回答
データ セキュリティが最優先事項であるシナリオにおいて、Google Cloud でホストされているデータ処理システムのコンポーネント間の通信を保護するためのベスト プラクティスは何ですか?
1. 　
2. ファイアウォールを実装してネットワークアクセスを制限する
3. 
4. 
<details><div>
    答え：
説明
ファイアウォールを実装してネットワークアクセスを制限することは、データ処理システム内のコンポーネント間の通信を保護し、データセキュリティを強化するためのベストプラクティスです。[詳細](https://cloud.google.com/vpc/docs/firewalls)
</div></details>

### Q. 質問40: 未回答
データ処理環境での Cloud Key Management Service(KMS)の目的は何ですか?
1. データ暗号化を強化
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Key Management Service(KMS)は、データ処理環境でのデータ暗号化を強化するために使用されます。これにより、機密情報を保護するための暗号化キーを管理できます。詳細: [Cloud KMS の概要](https://cloud.google.com/kms/docs)
</div></details>

### Q. 質問41: 未回答
リアルタイムのデータ変換とエンリッチメントを必要とするデータ処理パイプラインを設計しています。このシナリオに最も適した Google Cloud サービスはどれですか?
1. 　
2. Cloud Dataflow 
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataflow は、データ処理パイプラインでのリアルタイムのデータ変換とエンリッチメントを目的として設計されています。これは、ストリーム処理とバッチ処理の両方に対応するサーバーレスのフルマネージド環境を提供します。詳細: [Cloud Dataflow の概要](https://cloud.google.com/dataflow/docs)
</div></details>

### Q. 質問42: 未回答
Cloud Composer で、Cloud Storage バケットへの変更に基づいて機械学習ワークフローをトリガーします。このタスクに適した Cloud Composer コンポーネントはどれですか?
1. 　
2. 
3. FileSensor 
4. 
<details><div>
    答え：
説明
Cloud Composer の FileSensor は、Cloud Storage バケットへの変更に基づいてワークフローをトリガーするのに適しています。指定されたファイルまたはフォルダーの変更を監視します。[Cloud Composer FileSensor] (クラウド コンポーザー FileSensor)(https://cloud.google.com/composer/docs/how-to/using/sensors#filesensor)
</div></details>

### Q. 質問43: 未回答
AI Platform Prediction でモデル監視を実装している。ドリフト検出は、機械学習モデルのコンテキストで識別するのに役立ちますか?
1. 　
2. 
3. 
4. 機能分布の変更点
<details><div>
    答え：
説明
AI Platform Prediction のドリフト検出は、特徴分布の変化を特定するのに役立ち、モデルのパフォーマンスを経時的に監視して維持できます。[AIプラットフォーム予測モデルモニタリング](https://cloud.google.com/ai-platform/prediction/docs/monitoring)
</div></details>

### Q. 質問44: 未回答
CI / CD パイプラインを使用して、AI Platform Prediction での機械学習モデルのデプロイを自動化したい。モデルのデプロイ プロセスを自動化するためにパイプラインに統合できる Google Cloud サービスはどれですか?
1. 　
2. Cloud Build
3. 
4. 
<details><div>
    答え：
説明
Cloud Build はフルマネージドの CI / CD プラットフォームであり、AI Platform Prediction でのモデル デプロイ プロセスを自動化するためにパイプラインに統合できます。[クラウドビルド](https://cloud.google.com/build)
</div></details>

### Q. 質問45: 未回答
トレーニングに GPU アクセラレーションを必要とする機械学習モデルを構築しています。トレーニング ジョブの GPU のタイプと数を指定できる AI Platform Training の設定パラメータはどれですか?
1. 　
2. 「--scale-tier」
3. 
4. 
<details><div>
    答え：
説明
AI Platform Training の「--scale-tier」構成パラメータを使用すると、トレーニング ジョブの GPU のタイプと数を指定し、マシンタイプとハードウェア リソースを制御できます。[AI Platform トレーニング スケーリング](https://cloud.google.com/ai-platform/training/docs/training-jobs)
</div></details>

### Q. 質問46: 未回答
機械学習モデルの配信に AI Platform Prediction を使用している。デプロイプロセス中に「--version」フラグを設定する目的は何ですか?
1. 　
2. モデルのバージョンを指定
3. 
4. 
<details><div>
    答え：
説明
AI Platform Prediction の「--version」フラグは、デプロイ プロセス中にモデルのバージョンを指定するために使用されます。[AI Platform 予測モデル版](https://cloud.google.com/ai-platform/prediction/docs/deploying-models#version)
</div></details>

### Q. 質問47: 未回答
高可用性のためのデータ処理システムを設計する場合、Google Cloud で複数リージョンのデプロイ戦略を選択する際の重要な考慮事項は何ですか?
1. 　
2. 
3. 
4. フォールトトレランスが向上
<details><div>
    答え：
説明
Google Cloud で複数リージョンのデプロイ戦略を選択すると、フォールトトレランスが向上し、複数の地理的リージョンにリソースを分散することで高可用性が実現します。[詳細](https://cloud.google.com/solutions/multi-region-fault-tolerance)
</div></details>

### Q. 質問48: 未回答
データ処理システムでデータのプライバシーを重視して設計する場合、Cloud Storage バケット内の機密情報を処理するための推奨されるアプローチは何ですか?
1. 　
2. 
3. 保存中および転送中のデータを暗号化
4. 
<details><div>
    答え：
説明
Cloud Storage バケット内の機密情報を処理するための推奨されるアプローチは、保存中および転送中のデータを暗号化して、データのプライバシーとコンプライアンスを確保することです。[詳細](https://cloud.google.com/storage/docs/encryption)
</div></details>

### Q. 質問49: 未回答
リアルタイム アプリケーション向けに、フルマネージドでスケーラブル、かつサーバーレスの NoSQL データベースを提供する Google Cloud サービスはどれですか?
1. 　
2. 
3. Cloud Firestore
4. 
<details><div>
    答え：
説明
Cloud Firestore は、リアルタイム アプリケーション向けに設計された、フルマネージドでスケーラブルなサーバーレスの NoSQL データベースです。自動スケーリングをサポートし、柔軟なデータモデルを提供します。詳細: [Cloud Firestore の概要](https://cloud.google.com/firestore/docs)
</div></details>

### Q. 質問50: 未回答
サーバーレスのデータ処理パイプラインにおいて、イベントドリブンのデータ処理タスクに Cloud Functions を使用する主なメリットは何ですか?
1. 　
2. 
3. 
4. 需要に応じて自動的に水平方向にスケーリング
<details><div>
    答え：
説明
Cloud Functions は、サーバーレス データ処理パイプラインにおいて、需要に応じて自動的に水平方向にスケーリングし、効率的で費用対効果の高い実行を実現することで、大きなメリットをもたらします。[詳細](https://cloud.google.com/functions/docs/concepts/exec#how-charges-are-calculated)
</div></details>

### Q. 質問51: 未回答
データ処理環境でのワークフローのオーケストレーションと自動化に適した Google Cloud サービスはどれですか?
1. 　
2. Cloud Composer
3. 
4. 
<details><div>
    答え：
説明
Cloud Composer は、データ処理環境でワークフローをオーケストレーション、自動化できるフルマネージドのワークフロー オーケストレーション サービスです。さまざまなサービスやツールの統合をサポートします。詳細: [Cloud Composer ドキュメント](https://cloud.google.com/composer/docs)
</div></details>

### Q. 質問52: 未回答
Google Cloud リソースのアクセス制御を管理するコンテキストでは、サービス アカウントの目的は何でしょうか?
1. アプリケーションやサービスの認証
2. 
3. 
4. 
<details><div>
    答え：
説明
Google Cloud のサービス アカウントは、アプリケーションやサービスの認証に使用されます。これらは、人間以外のエンティティがユーザーの資格情報を必要とせずにリソースに安全にアクセスする方法を提供します。サービス アカウントは、アクセス制御を管理するコンテキストで重要であり、アプリケーションが必要なアクセス許可でアクションを実行できるようにします。詳細については、[サービスアカウントの概要](https://cloud.google.com/iam/docs/service-accounts)を参照してください。
</div></details>

### Q. 質問53: 未回答
Cloud Dataprep のデータ処理ジョブでデータの信頼性を設計する場合、データリネージと影響分析の役割は何ですか?
1. データの移動を追跡して文書化
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataprep データ処理ジョブのデータ リネージと影響分析は、データの移動を追跡して文書化することで、信頼性を確保し、データ変換への影響分析を容易にします。[詳細](https://cloud.google.com/dataprep/docs/html/DataLineagePage_57341636)
</div></details>

### Q. 質問54: 未回答
BigQuery に接続されたデータポータル レポートの定期的なデータ更新をスケジュールします。これを実現するには、何を使用する必要がありますか?
1. Google Cloud Scheduler 
2. 
3. 
4. 
<details><div>
    答え：
説明
BigQuery に接続されたデータポータル レポートの定期的なデータ更新をスケジュールするには、Google Cloud Scheduler を使用します。
</div></details>

### Q. 質問55: 未回答
大規模なデータセットに対して SQL クエリを定期的に実行する必要があるデータ処理パイプラインを設計しています。このシナリオに最も適した Google Cloud サービスはどれですか?
1. BigQuery 
2. 
3. 
4. 
<details><div>
    答え：
説明
BigQuery は、大規模なデータセットに対して SQL クエリを実行できる、サーバーレスで拡張性の高いデータ ウェアハウスです。これは、データ処理パイプラインでのアドホックなクエリと分析に適しています。詳細: [BigQuery の機能](https://cloud.google.com/bigquery/docs)
</div></details>

### Q. 質問56: 未回答
リアルタイム予測に AI Platform Prediction を使用している。特定の地理的リージョン内で予測を提供するために、グローバル エンドポイントよりもリージョン エンドポイントを使用する利点は何ですか?
1. 　
2. 低遅延
3. 
4. 
<details><div>
    答え：
説明
AI Platform Prediction でリージョン エンドポイントを使用すると、特定の地域内で予測を提供する際のレイテンシが短くなり、予測応答の速度が向上します。[AI Platform 予測の地域エンドポイント](https://cloud.google.com/ai-platform/prediction/docs/regional-endpoints)
</div></details>

### Q. 質問57: 未回答
クラウドベースのデータ処理システムの保守性を考慮して設計する場合、ロギングとモニタリングの役割と、包括的なロギングとモニタリング機能を提供する Google Cloud サービスはどれですか?
1. 　
2. 
3. 
4. Google Cloud Logging 
<details><div>
    答え：
説明
Google Cloud Logging は、包括的なロギングとモニタリング機能を提供し、クラウドベースのデータ処理システムのメンテナンスとトラブルシューティングにおいて重要な役割を果たします。[詳細](https://cloud.google.com/logging/docs/)
</div></details>

### Q. 質問58: 未回答
Cloud Composer を使用して機械学習ワークフローを調整している。Apache Airflow と Cloud Composer の「PubSubPublishSensor」の目的は何ですか?
1. 　
2. Cloud Pub/Sub トピックにメッセージをパブリッシュ
3. 
4. 
<details><div>
    答え：
説明
Apache Airflow と Cloud Composer の「PubSubPublishSensor」は、Cloud Pub/Sub トピックにメッセージをパブリッシュするために使用され、イベントに基づいてダウンストリーム タスクをトリガーできます。[Cloud Composer PubSubPublishSensor] (クラウド コンポーザー PubSubPublishSensor)(https://cloud.google.com/composer/docs/how-to/using/sensors#pubsubpublishsensor)
</div></details>

### Q. 質問59: 未回答
複雑なワークフローのオーケストレーションと調整を必要とするデータ処理パイプラインを構築している。このシナリオに最適な Google Cloud サービスはどれですか?
1. 　
2. 
3. 
4. Cloud Composer
<details><div>
    答え：
説明
Cloud Composer は、データ処理システム内の複雑なワークフローをオーケストレーション、調整できるフルマネージドのワークフロー オーケストレーション サービスです。さまざまなサービスやツールの統合をサポートします。詳細: [Cloud Composer ドキュメント](https://cloud.google.com/composer/docs)
</div></details>

### Q. 質問60: 未回答
ハイパーパラメータ調整用に AI Platform Training を設定する場合、「--parameter-server-count」フラグの目的は何ですか?
1. 　
2. ハイパーパラメータ調整を設定
3. 
4. 
<details><div>
    答え：
説明
AI Platform Training の「--parameter-server-count」フラグは、ハイパーパラメータ調整を設定する際にパラメータ サーバーの数を指定し、トレーニング タスクの分散を制御するために使用されます。[AI Platform トレーニングのハイパーパラメータ調整](https://cloud.google.com/ai-platform/training/docs/hyperparameter-tuning)
</div></details>

### Q. 質問61: 未回答
データ処理環境での Cloud Storage Transfer Service の主な目的は何ですか?
1. 　
2. Cloud Storage バケット間のデータ転送
3. 
4. 
<details><div>
    答え：
説明
Cloud Storage Transfer Service は、Cloud Storage バケット間のデータ転送の自動化とスケジュール設定に使用されます。これは、データ処理システム内のデータ移動を管理するのに役立ちます。詳細:[転送サービスの概要](https://cloud.google.com/storage-transfer/docs)
</div></details>

### Q. 質問62: 未回答
BigQuery のデータアクセス制御を実装している。データのセキュリティを確保するというコンテキストにおけるデータセットレベルのアクセス許可の目的は何ですか?
1. 　
2. 
3. 特定のデータセットへのアクセスを制限する
4. 
<details><div>
    答え：
説明
BigQuery のデータセットレベルの権限は、特定のデータセットへのアクセスを制限するために重要です。これらの権限を構成することで、特定のデータセット内のデータをクエリおよび変更できるユーザーまたはグループを制御し、データのセキュリティを強化できます。詳細については、ドキュメントを参照してください: [データセットへのアクセスの制御](https://cloud.google.com/bigquery/docs/dataset-access-controls)
</div></details>

### Q. 質問63: 未回答
Cloud Functions を使用したサーバーレス データ処理パイプラインでは、トリガーの目的は何か、関数の実行にどのような影響を与えるのでしょうか。
1. 　
2. 
3. 
4. イベントに基づいて関数の実行を開始
<details><div>
    答え：
説明
Cloud Functions のトリガーは、イベントに基づいて関数の実行を開始し、データ処理パイプラインでサーバーレスのイベントドリブン アーキテクチャを実現します。[詳細](https://cloud.google.com/functions/docs/concepts/events-triggers)
</div></details>

### Q. 質問64: 未回答
データ処理システムにおいて、Cloud Armor の目的は何ですか?
1. 　
2. 
3. DDoS 攻撃からの保護を提供し、データ処理システムのウェブ アプリケーション ファイアウォール
4. 
<details><div>
    答え：
説明
Cloud Armor は DDoS 攻撃からの保護を提供し、データ処理システムのウェブ アプリケーション ファイアウォールとして機能します。これにより、サイバー脅威からアプリケーションを保護し、トラフィックが急増した場合の可用性を確保できます。詳細: [Cloud Armor の概要](https://cloud.google.com/armor/docs)
</div></details>

### Q. 質問65: 未回答
データ レジデンシー要件が厳しいシナリオでは、データを特定の地理的な場所内に保持しながらデータを処理および分析するのに適した Google Cloud サービスはどれですか?
1. 　
2. 
3. 
4. BigQuery 
<details><div>
    答え：
説明
BigQuery は、特定の地理的な場所内のデータのクエリと処理が可能なため、データの保存場所が厳しいデータの処理と分析に適しています。[詳細](https://cloud.google.com/bigquery/docs/locations)
</div></details>

### Q. 質問66: 未回答
データ処理で頻繁に更新されるデータへの低レイテンシのアクセスが必要なシナリオでは、リアルタイムの状態情報を維持するのに適した Google Cloud ストレージ ソリューションはどれですか?
1. Cloud Spanner
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Spanner は、頻繁に更新されるデータへの低レイテンシのアクセスを必要とするシナリオに適しており、グローバルに分散され、水平方向にスケーラブルで、強力な一貫性のあるデータベースを提供します。[詳細](https://cloud.google.com/spanner/docs)
</div></details>

### Q. 質問67: 未回答
Cloud Dataflow を使用してデータ処理パイプラインを実装する場合、ストリーミング データの処理におけるウィンドウ処理の目的は何か、また、データ分析にどのような影響を与えるのでしょうか?
1. 　
2. 
3. 
4. 時間ベースのウィンドウのサイズを決定
<details><div>
    答え：
説明
Cloud Dataflow のストリーミング データ処理のウィンドウ処理は、時間ベースのウィンドウのサイズを決定し、効率的な処理のためにデータを管理可能な間隔に整理することで、データ分析に影響を与えます。[詳細](https://cloud.google.com/dataflow/docs/concepts/event-time)
</div></details>

### Q. 質問68: 未回答
データ処理システムにおいて、クラウドデータ損失防止(DLP)の目的は何ですか?
1. 機密データの漏洩を検出して防止
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Data Loss Prevention(DLP)は、データ処理システムにおける機密データの漏洩を検出して防止するために使用されます。機密情報を保護し、プライバシー規制へのコンプライアンスを確保するのに役立ちます。詳細: [Cloud DLP の概要](https://cloud.google.com/dlp/docs)
</div></details>

### Q. 質問69: 未回答
クラウドベースのデータ処理システムで費用を最適化する場合、アクセス頻度の低いデータを長期間保存するために Cloud Storage で適切なストレージ クラスを選択する際の重要な考慮事項は何ですか?
1. 　
2. Coldline Storage クラスを選択
3. 
4. 
<details><div>
    答え：
説明
Cloud Storage で Coldline Storage クラスを選択することは、アクセス頻度の低いデータを費用対効果の高い方法で長期保存し、データの可用性を確保しながら費用を最適化するための重要な考慮事項です。[詳細](https://cloud.google.com/storage/docs/storage-classes#coldline)
</div></details>

### Q. 質問70: 未回答
データポータルのレポートをデザインする場合、フィルタ コントロールの目的は何ですか?
1. 　
2. 
3. レポートに表示されるデータを制限する
4. 
<details><div>
    答え：
説明
データポータルのフィルタ コントロールは、ユーザー定義の条件に基づいてレポートに表示されるデータを制限するために使用されます。
</div></details>

### Q. 質問71: 未回答
AI Platform Prediction に機械学習モデルをデプロイする場合、自動スケーリングを構成する際の「--max-predictions-per-second」フラグの目的は何ですか?
1. 　
2. 1 秒あたりの予測の最大数を制御
3. 
4. 
<details><div>
    答え：
説明
AI Platform Prediction の「--max-predictions-per-second」フラグは、サービスが処理できる 1 秒あたりの予測の最大数を制御することで、自動スケーリングを構成するために使用されます。[AI Platform 予測の自動スケーリング](https://cloud.google.com/ai-platform/prediction/docs/autoscaling)
</div></details>

### Q. 質問72: 未回答
プロジェクトの Cloud Identity and Access Management(IAM)を構成しています。カスタムIAMロールの目的は何ですか?
1. 　
2. 
3. きめ細かなアクセス制御を定義
4. 特定のタスクに必要な権限を正確に指定する
<details><div>
    答え：
説明
Google Cloud IAM のカスタム IAM ロールは、特定のタスクに必要な権限を正確に指定することで、きめ細かなアクセス制御を定義する機能を提供します。これにより、プロジェクトの特定の要件に合わせてロールを調整し、必要なものだけに権限を制限できます。詳細については、[カスタムロールについて](https://cloud.google.com/iam/docs/understanding-custom-roles)を参照してください。
</div></details>

### Q. 質問73: 未回答
Cloud SQL でデータを保護するのはお客様の責任です。Cloud SQL データベースで保存されているデータを保護するには、どのような暗号化オプションを選択する必要がありますか?
1. サーバーサイド暗号化
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud SQL データベースで保存されているデータを保護するには、サーバーサイド暗号化を選択する必要があります。これにより、Cloud SQL に保存されるデータが暗号化され、機密情報のセキュリティが強化されます。詳細については、[暗号化の概要](https://cloud.google.com/sql/docs/encryption)を参照してください。
</div></details>

### Q. 質問74: 未回答
Cloud Storage に保存されているデータの整合性と信頼性を確保する必要があります。どの機能を使うべきか?
1. オブジェクト署名
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Storage のオブジェクト署名は、データの整合性と信頼性を確保するために使用されます。これにより、デジタル署名を使用してオブジェクトに署名し、オブジェクトが改ざんされていないことを確認する方法を提供できます。追加情報: [Object Signing](https://cloud.google.com/storage/docs/xml-api/reference-headers#content-signing)
</div></details>

### Q. 質問75: 未回答
モデルをトレーニングする前に Apache Beam でデータを前処理する機械学習ワークフローを設計しています。Apache Beam パイプラインを大規模に実行するのに適した Google Cloud サービスはどれですか?
1. Cloud Dataflow
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataflow は、Apache Beam パイプラインを大規模に実行するためのフルマネージド サービスであり、機械学習ワークフローでデータを前処理するのに適しています。[クラウドデータフロー](https://cloud.google.com/dataflow)
</div></details>

## 3
### Q. 質問1: 未回答
CI / CD パイプラインを使用して、新しいバージョンの機械学習モデルを AI Platform Prediction にデプロイするプロセスを自動化したい。このデプロイを容易にするために、どの Google Cloud サービスをパイプラインに統合できますか?
1. 
2. 
3. 
4. Cloud Build
<details><div>
    答え：
説明
Cloud Build を CI / CD パイプラインに統合することで、AI Platform Prediction に機械学習モデルの新しいバージョンを簡単にデプロイできます。[クラウドビルド](https://cloud.google.com/build)
</div></details>

### Q. 質問2: 未回答
Cloud Storage で費用を最適化するために設計する場合、頻繁にアクセスされ、有効期間が短い一時データに適したストレージ クラスを選択する際の重要な考慮事項は何ですか?
1. 
2. 
3. 
4.  Standard Storage クラスを使用
<details><div>
    答え：
説明
Cloud Storage で Standard Storage クラスを使用することは、頻繁にアクセスされ、有効期間が短い一時データを費用対効果の高い方法で保存し、最適なパフォーマンスを確保し、費用を最小限に抑えるための重要な考慮事項です。[詳細](https://cloud.google.com/storage/docs/storage-classes#standard)
</div></details>

### Q. 質問3: 未回答
カスタムの依存関係とランタイム環境を必要とするデータ処理タスクのシナリオでは、コンテナ化されたアプリケーションの構築とデプロイに適した Google Cloud サービスはどれですか?
1. 
2. Cloud Run
3. 
4. 
<details><div>
    答え：
説明
Cloud Run は、コンテナ化されたアプリケーションの構築とデプロイに適しており、データ処理タスクのカスタム依存関係とランタイム環境を柔軟に調整できます。[詳細](https://cloud.google.com/run/docs)
</div></details>

### Q. 質問4: 未回答
AI Platform Training を使用して GPU インスタンスでモデルをトレーニングする機械学習ワークフローを設計しています。トレーニングジョブを送信する際の「--master-image-uri」フラグの目的は何ですか?
1. 
2. 
3. マスターノードにカスタム Docker イメージを使用
4. 
<details><div>
    答え：
説明
AI Platform Training の「--master-image-uri」フラグは、トレーニング ジョブを送信するときにマスターノードの Docker イメージを定義するために使用され、マスターノードにカスタム Docker イメージを使用できるようにします。[AI Platform Training マスター画像 URI](https://cloud.google.com/ai-platform/training/docs/training-jobs#master-image-uri)
</div></details>

### Q. 質問5: 未回答
データポータルで Google アナリティクスのデータを視覚化する必要があります。この統合を実現するための推奨される方法は何ですか?
1. 
2. 
3. BigQuery を中間ストレージとして使用する
4. 
<details><div>
    答え：
説明
BigQuery を中間ストレージとして使用すると、Google アナリティクスとデータポータルを効率的に統合でき、信頼性と拡張性に優れたソリューションが実現します。
</div></details>

### Q. 質問6: 未回答
Cloud Dataflow を使用したデータ処理パイプラインでは、ステートフル処理の目的と、ストリーミング データのコンテキスト維持にどのように貢献しますか?
1. 
2. 
3. データ要素間のコンテキストが維持
4. 
<details><div>
    答え：
説明
Cloud Dataflow のステートフル処理では、ストリーミング データ内のデータ要素間のコンテキストが維持されるため、パイプラインは以前の要素に関する情報を保持し、より複雑な処理ロジックを実現できます。[詳細](https://cloud.google.com/dataflow/docs/concepts/stateful-processing)
</div></details>

### Q. 質問7: 未回答
モデルをトレーニングする前に Apache Beam を使用してデータを前処理する機械学習ワークフローを設計しています。Apache Beam パイプラインを大規模に実行するのに適した Google Cloud サービスはどれですか?
1. 
2. 
3. Cloud Dataflow 
4. 
<details><div>
    答え：
説明
Cloud Dataflow は、Apache Beam パイプラインを大規模に実行するためのフルマネージド サービスであり、機械学習ワークフローでデータを前処理するのに適しています。[クラウドデータフロー](https://cloud.google.com/dataflow)
</div></details>

### Q. 質問8: 未回答
AI Platform Prediction のコンテキストで、モデル バージョンのデプロイを構成するときに「--max-age」フラグを設定する目的は何ですか?
1. 
2. 
3. モデル バージョンの最大経過時間を設定
4. 
<details><div>
    答え：
説明
AI Platform Prediction の「--max-age」フラグは、モデル バージョンの最大経過時間を設定するために使用され、バージョンが予測に使用される期間を制御できます。[AI Platform 予測の最大経過時間](https://cloud.google.com/ai-platform/prediction/docs/deploying-models#max-age)
</div></details>

### Q. 質問9: 未回答
AI Platform Prediction のコンテキストでは、機械学習モデルのデプロイ中に「--explain-metadata」フラグを設定することにどのような意味がありますか?
1. 特徴量の重要度値を生成
2. 
3. 
4. 
<details><div>
    答え：
説明
AI Platform Prediction で「--explain-metadata」フラグを設定すると、特徴量の重要度値を生成するため、さまざまな特徴が予測に与える影響を把握できます。[AI Platform Prediction Explain Metadata] (AI プラットフォーム予測1. 
2. 
3. 
4. 
<details><div>
    答え：
説明メタデータ)(https://cloud.google.com/ai-platform/prediction/docs/ai-explanations/setting-up)
</div></details>

### Q. 質問10: 未回答
データ処理システムにおいて、Cloud Armor の目的は何ですか?
1. DDoS 攻撃からの保護を提供し、データ処理システムのウェブ アプリケーション ファイアウォールとして機能
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Armor は DDoS 攻撃からの保護を提供し、データ処理システムのウェブ アプリケーション ファイアウォールとして機能します。これにより、サイバー脅威からアプリケーションを保護し、トラフィックが急増した場合の可用性を確保できます。詳細: [Cloud Armor の概要](https://cloud.google.com/armor/docs)
</div></details>

### Q. 質問11: 未回答
Cloud Composer を使用して機械学習ワークフローを調整している。Apache Airflow と Cloud Composer の「PubSubPublishOperator」の目的は何ですか?
1. 
2. Cloud Pub/Sub トピックにメッセージをパブリッシュする
3. 
4. 
<details><div>
    答え：
説明
Apache Airflow と Cloud Composer の「PubSubPublishOperator」は、Cloud Pub/Sub トピックにメッセージをパブリッシュするために使用され、イベントに基づいてダウンストリーム タスクをトリガーできます。[Cloud Composer PubSubPublishOperator] (クラウド コンポーザー PubSubPublishOperator)(https://cloud.google.com/composer/docs/how-to/using/operators#pubsubpublishoperator)
</div></details>

### Q. 質問12: 未回答
機械学習モデルの配信に AI Platform Prediction を使用しており、予測リクエストの費用を最適化したい。自動スケーリングを構成するときに '--min-instances' フラグと '--max-instances' フラグを設定する目的は何ですか?
1. 
2. インスタンス(レプリカ)の最小数と最大数を制御
3. 
4. 
<details><div>
    答え：
説明
AI Platform Prediction で「--min-instances」フラグと「--max-instances」フラグを設定するのは、自動スケーリングの制限を設定し、予測サービスのインスタンス(レプリカ)の最小数と最大数を制御するためのものです。[AI Platform 予測の自動スケーリング](https://cloud.google.com/ai-platform/prediction/docs/autoscaling)
</div></details>

### Q. 質問13: 未回答
ビジュアルツールを使用したデータのプロファイリング、クレンジング、変換を含むデータ処理パイプラインを設計する必要があります。このシナリオに最適な Google Cloud サービスはどれですか?
1. 
2. 
3. 
4. Cloud Dataprep 
<details><div>
    答え：
説明
Cloud Dataprep は、データ処理パイプラインでビジュアル ツールを使用したデータのプロファイリング、クレンジング、変換用に設計されています。これは、データを探索および準備するための視覚的なインターフェイスを提供します。詳細: [Cloud Dataprep の概要](https://cloud.google.com/dataprep/docs)
</div></details>

### Q. 質問14: 未回答
Google Cloud Storage に保存されている機密データを保護する責任はお客様にあります。ストレージに書き込まれる前にデータを自動的に暗号化するには、どのような暗号化オプションを使用できますか?
1. 
2. クライアントサイド暗号化
3. 
4. 
<details><div>
    答え：
説明
Google Cloud Storage に書き込まれる前にデータを自動的に暗号化するには、クライアントサイド暗号化を使用する必要があります。これにより、データがクラウドに送信および保存される前にクライアント側で暗号化され、セキュリティのレイヤーが追加されます。詳細については、[クライアント側の暗号化](https://cloud.google.com/storage/docs/client-side-encryption)を参照してください。
</div></details>

### Q. 質問15: 未回答
Cloud Dataflow パイプラインでは、無制限のストリーミング データを処理する際のウィンドウ処理にはどのような意味があり、データ分析にどのように貢献しますか?
1. 
2. 時間ベースのウィンドウのサイズを決定
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataflow の無制限のストリーミング データに対するウィンドウ処理は、時間ベースのウィンドウのサイズを決定し、データを管理可能な間隔に整理して効率的に処理することで、データ分析に貢献します。[詳細](https://cloud.google.com/dataflow/docs/concepts/event-time)
</div></details>

### Q. 質問16: 未回答
低レイテンシ要件で頻繁にアクセスされるデータ用に設計された Cloud Storage クラスはどれですか?
1. 
2. 
3. Standard ストレージ クラス
4. 
<details><div>
    答え：
説明
Cloud Storage の Standard ストレージ クラスは、低レイテンシ要件で頻繁にアクセスされるデータ向けに設計されています。Cloud Storage に保存されているデータへの高性能なアクセスを提供します。追加情報: [Cloud Storage Classes](https://cloud.google.com/storage/docs/storage-classes)
</div></details>

### Q. 質問17: 未回答
Cloud Functions を使用したサーバーレス データ処理パイプラインでは、トリガーの役割と関数の実行にどのような影響がありますか?
1. 
2. 
3. イベントに基づいて関数の実行を開始
4. 
<details><div>
    答え：
説明
Cloud Functions のトリガーは、イベントに基づいて関数の実行を開始し、データ処理パイプラインでサーバーレスのイベントドリブン アーキテクチャを実現します。[詳細](https://cloud.google.com/functions/docs/concepts/events-triggers)
</div></details>

### Q. 質問18: 未回答
BigQuery のデータ アクセス制御を構成しています。データのセキュリティとコンプライアンスを確保する上でのクエリ履歴追跡の役割は何ですか?
1. 
2. 
3. 
4. クエリ アクティビティの監査とモニタリング
<details><div>
    答え：
説明
BigQuery のクエリ履歴トラッキングは、クエリ アクティビティの監査とモニタリングに不可欠です。実行されたクエリの履歴レコードを提供し、データセキュリティとプライバシーの規制への準拠を支援します。この機能は、誰がデータにアクセスし、どのような操作が実行されたかを追跡するのに役立ち、全体的なデータガバナンスに貢献します。詳細については、[クエリ履歴情報](https://cloud.google.com/bigquery/query-history)を参照してください。
</div></details>

### Q. 質問19: 未回答
Cloud Storage のアクセス制御を実装している。データセキュリティとコンプライアンスのコンテキストにおけるオブジェクトライフサイクル管理の目的は何ですか?
1. 
2. 古いオブジェクトを自動的に削除する
3. 
4. 
<details><div>
    答え：
説明
Cloud Storage のオブジェクト ライフサイクル管理は、古いオブジェクトを自動的に削除するために使用されます。この機能は、ストレージコストの管理、データ保持ポリシーの遵守、不要なオブジェクトの削除による全体的なデータセキュリティの強化に役立ちます。詳細については、ドキュメント「[オブジェクトライフサイクル管理](https://cloud.google.com/storage/docs/lifecycle)」を参照してください。
</div></details>

### Q. 質問20: 未回答
AI Platform Prediction でモデル監視を実装している。デプロイされたモデル バージョンの監視を構成するときに '--request-paths' フラグを設定する目的は何ですか?
1. サンプリングされた予測リクエストのパスを定義する
2. 
3. 
4. 
<details><div>
    答え：
説明
AI Platform Prediction の「--request-paths」フラグは、モデル モニタリングを設定する際にサンプリングされた予測リクエストのパスを定義するために使用され、アプリケーション内の特定のパスにモニタリングを集中させるのに役立ちます。[AI Platform 予測リクエスト パス](https://cloud.google.com/ai-platform/prediction/docs/monitoring)
</div></details>

### Q. 質問21: 未回答
BigQuery に大規模なデータセットがあり、集計を効率的に実行する必要がある。数値列の合計を計算するには、どの関数を使用する必要がありますか?
1. 
2. 
3. SUM 関数
4. 
<details><div>
    答え：
説明
BigQuery の SUM 関数は、テーブル内の数値列の合計を計算するために使用されます。
</div></details>

### Q. 質問22: 未回答
Cloud Dataprep を使用したクラウドベースのデータ処理システムにおいて、データ変換の信頼性を確保する上で、データリネージと影響分析の役割は何ですか?
1. 
2. 
3. 
4. データの動きを追跡して文書化
<details><div>
    答え：
説明
Cloud Dataprep のデータ リネージと影響分析は、データの動きを追跡して文書化し、データに適用された発生元と変換に関する分析情報を提供することで、データ変換の信頼性を確保します。[詳細](https://cloud.google.com/dataprep/docs/html/DataLineagePage_57341636)
</div></details>

### Q. 質問23: 未回答
AI Platform Prediction でモデル監視を実装している。デプロイされたモデルバージョンの監視を設定するときに '--slice' フラグを使用する目的は何ですか?
1. 
2. 
3. 特定のデータスライスの予測をモニタリング
4. 
<details><div>
    答え：
説明
AI Platform Prediction の「--slice」フラグは、特定のデータスライスの予測をモニタリングするために使用され、データのサブセットでモデルのパフォーマンスを分析できます。[AIプラットフォーム予測モデルモニタリング](https://cloud.google.com/ai-platform/prediction/docs/monitoring)
</div></details>

### Q. 質問24: 未回答
サードパーティの機械学習モデルの統合を含むデータ処理パイプラインの設計を担当します。この統合を促進するのはどの Google Cloud サービスですか?
1. 
2. Cloud AI Platform 
3. 
4. 
<details><div>
    答え：
説明
Cloud AI Platform は、サードパーティ モデルを含む機械学習モデルをデプロイ、管理し、データ処理パイプラインに統合するように設計されています。モデルのトレーニングとデプロイのためのツールを提供します。詳細: [Cloud AI Platform の概要](https://cloud.google.com/ai-platform/docs)
</div></details>

### Q. 質問25: 未回答
データ処理システムでのリアルタイムのモニタリング、ロギング、デバッグに適した Google Cloud サービスはどれですか?
1. 
2. Cloud Logging
3. 
4. 
<details><div>
    答え：
説明
Cloud Logging は、データ処理システムでのリアルタイムのモニタリング、ログ記録、デバッグに適しています。これにより、ログを保存、検索、分析し、アプリケーションやサービスの動作に関する分析情報を得ることができます。詳細: [Cloud Logging の概要](https://cloud.google.com/logging/docs)
</div></details>

### Q. 質問26: 未回答
クラウドベースのデータ処理システムで費用を最適化する場合、アクセス頻度の低いデータを長期間保存するために Cloud Storage で適切なストレージ クラスを選択する際の重要な考慮事項は何ですか?
1. Coldline Storage クラスを選択
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Storage で Coldline Storage クラスを選択することは、アクセス頻度の低いデータの長期保存の費用を最適化し、費用対効果の高いアーカイブ ストレージを提供するための重要な考慮事項です。[詳細](https://cloud.google.com/storage/docs/storage-classes#coldline)
</div></details>

### Q. 質問27: 未回答
機械学習モデルの配信に AI Platform Prediction を使用している。デプロイプロセス中に「--runtime-version」フラグを設定する目的は何ですか?
1. 
2. 
3. 
4. 予測ランタイム用のDockerイメージの定義
<details><div>
    答え：
説明
AI Platform Prediction の「--runtime-version」フラグは、デプロイ プロセス中に予測フレームワークのランタイム バージョンを指定するために使用されます。[AI Platform Prediction ランタイム バージョン](https://cloud.google.com/ai-platform/prediction/docs/deploying-models#runtime-version)
</div></details>

### Q. 質問28: 未回答
Google Cloud Pub/Sub のデータを保護する責任はお客様にあります。ID とグループ メンバーシップに基づいてトピックとサブスクリプションへのアクセスを制御するために、どのようなセキュリティ機能を有効にできますか?
1. IDおよびIAM
2. 
3. 
4. 
<details><div>
    答え：
説明
Google Cloud Pub/Sub では、Identity and Access Management(IAM)を使用して、ID とグループ メンバーシップに基づいてトピックとサブスクリプションへのアクセスを制御できます。IAMはきめ細かなアクセス制御を提供し、許可されたユーザーとサービスのみがメッセージを発行および消費できるようにします。詳細については、[Pub/Sub Access Control](https://cloud.google.com/pubsub/docs/access-control) を参照してください。
</div></details>

### Q. 質問29: 未回答
データ処理パイプラインにおいて、Cloud Storage Transfer Appliance の目的は何ですか?
1. 
2. オンプレミスの場所から Cloud Storage に大量のデータを安全に転送
3. 
4. 
<details><div>
    答え：
説明
Cloud Storage Transfer Appliance は、オンプレミスの場所から Cloud Storage に大量のデータを安全に転送できるように設計されています。効率的なデータ移行のための物理デバイスを提供します。追加情報: [Transfer Appliance の概要](https://cloud.google.com/storage-transfer-appliance/docs)
</div></details>

### Q. 質問30: 未回答
機械学習ワークフローでストリーミング データを処理するために Cloud Dataflow を使用している。Dataflow パイプラインを実行する際の「--num-workers」フラグの目的は何ですか?
1. 
2. ワーカー ノードの数を定義
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataflow の「--num-workers」フラグは、Dataflow パイプライン内のワーカー ノードの数を定義するために使用され、リソースを制御してパフォーマンスを最適化できます。[Cloud Dataflow num-workers](https://cloud.google.com/dataflow/docs/guides/specifying-exec-params#num-workers)
</div></details>

### Q. 質問31: 未回答
データ処理システムでのリアルタイムのログ分析とモニタリングに適した Google Cloud サービスはどれですか?
1. 
2. Cloud Logging
3. 
4. 
<details><div>
    答え：
説明
Cloud Logging は、データ処理システムでのリアルタイムのログ分析とモニタリングに推奨されるサービスです。これにより、ログを保存、検索、分析して、システムの動作に関する洞察を得ることができます。詳細: [Cloud Logging の概要](https://cloud.google.com/logging/docs)
</div></details>

### Q. 質問32: 未回答
Apache Spark を使用して大規模なデータを効率的に変換する必要があるデータ処理パイプラインを構築しています。このシナリオに最適な Google Cloud サービスはどれですか?
1. Cloud Dataproc 
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataproc はフルマネージドの Apache Spark および Hadoop サービスであり、データ処理パイプラインで Apache Spark を使用して大規模データを効率的に変換するのに適しています。スケーラブルで費用対効果の高いソリューションを提供します。詳細: [Cloud Dataproc の概要](https://cloud.google.com/dataproc/docs)
</div></details>

### Q. 質問33: 未回答
AI Platform Prediction のコンテキストで、モデル バージョンのデプロイ時に「--max-replicas」フラグを指定する目的は何ですか?
1. 
2. 自動スケーリングの制限を設定
3. 
4. 
<details><div>
    答え：
説明
AI Platform Prediction の「--max-replicas」フラグは、自動スケーリングの制限を設定し、予測サービス内のレプリカ(インスタンス)の最大数を制御するために使用されます。[AI Platform 予測の自動スケーリング](https://cloud.google.com/ai-platform/prediction/docs/autoscaling)
</div></details>

### Q. 質問34: 未回答
データ処理システムにおいて、Cloud SQL の主な目的は何ですか?
1. フルマネージドのリレーショナル データベース サービス
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud SQL は、データ処理システムでリレーショナル データベースを保存、管理するためのスケーラブルで安全なソリューションを提供する、フルマネージドのリレーショナル データベース サービスです。詳細: [Cloud SQL の概要](https://cloud.google.com/sql/docs)
</div></details>

### Q. 質問35: 未回答
お客様は、Cloud Storage でデータの整合性を確保する責任があります。保存されているオブジェクトのデータ破損を検出して自動的に修正するには、どのような機能を有効にできますか?
1. 
2. 
3. チェックサム検証
4. 
<details><div>
    答え：
説明
Cloud Storage のデータ破損を検出して自動的に修正するには、チェックサム検証を有効にします。チェックサムは、読み取りおよび書き込み操作中にデータを検証し、破損したデータを自動的に修正できるようにすることで、保存されたオブジェクトの整合性を確保するのに役立ちます。詳細については、[チェックサムと整合性チェック](https://cloud.google.com/storage/docs/performing-resumable-uploads#checksums-and-integrity-checks)を参照してください。
</div></details>

### Q. 質問36: 未回答
Google Cloud Storage のデータ アクセス制御を実装しています。データセキュリティとコンプライアンスのコンテキストにおけるUniform Bucket-Level Access(UBLA)の目的は何ですか?
1. 
2. 
3. アクセス制御管理を簡素化
4. 
<details><div>
    答え：
説明
Google Cloud Storage の Uniform Bucket-Level Access(UBLA)は、バケットとオブジェクトへのアクセスを一貫した方法で制御することで、アクセス制御管理を簡素化します。これにより、バケットへのすべてのアクセスが単一の権限セットによって管理され、全体的なセキュリティとコンプライアンスが強化されます。詳細については、[Uniform Bucket-Level Access](https://cloud.google.com/storage/docs/uniform-bucket-level-access)を参照してください。
</div></details>

### Q. 質問37: 未回答
Cloud Composer を使用して機械学習ワークフローを調整している。Apache Airflow と Cloud Composer のコンテキストにおける「PubSubTopicSensor」の目的は何ですか?
1. 
2. Cloud Pub/Sub メッセージに基づいてタスクをトリガー
3. 
4. 
<details><div>
    答え：
説明
Apache Airflow と Cloud Composer の「PubSubTopicSensor」は、Cloud Pub/Sub メッセージに基づいてタスクをトリガーするために使用され、イベントに基づいて動的なタスクを実行できます。[Cloud Composer PubSubTopicSensor](https://cloud.google.com/composer/docs/how-to/using/sensors#pubsubtopicsensor)
</div></details>

### Q. 質問38: 未回答
Cloud Storage で費用を最適化するための設計を行う際、将来必要になる可能性のあるアクセス頻度の低いデータを処理する際のストレージ費用を管理するためのベスト プラクティスは何ですか?
1. 
2. 
3.  Nearline Storage クラスを使用
4. 
<details><div>
    答え：
説明
Cloud Storage で Nearline Storage クラスを使用することは、将来必要になる可能性のあるアクセス頻度の低いデータを処理する際に、コスト効率とアクセシビリティのバランスを取りながら、ストレージ費用を管理するためのベスト プラクティスです。[詳細](https://cloud.google.com/storage/docs/storage-classes#nearline)
</div></details>

### Q. 質問39: 未回答
Cloud Dataflow では、Pub/Sub からのデータを処理し、その結果を BigQuery に書き込むストリーミング パイプラインを設計します。BigQuery シンクの出力場所を指定する際の「--output」フラグの目的は何ですか?
1. 
2. 
3. 
4. 出力場所の指定
<details><div>
    答え：
説明
Cloud Dataflow の「--output」フラグは、出力場所の指定に使用され、処理されたデータ(この場合は BigQuery シンク)の出力形式と出力先を設定できます。[Cloud Dataflow出力設定](https://cloud.google.com/dataflow/docs/guides/templates/provided-streaming#streaming-pubsub-to-bigquery)
</div></details>

### Q. 質問40: 未回答
Cloud Bigtable データ処理ソリューションでスケーラビリティを重視して設計する場合、行キーを使用してデータアクセス パターンを最適化するための推奨されるアプローチは何ですか?
1. 
2. 
3. 
4. クエリのパフォーマンスを最適化
<details><div>
    答え：
説明
Cloud Bigtable でデータ アクセス パターンを最適化するには、クエリのパフォーマンスを最適化する行キーを使用して、効率的なデータの取得とアクセスを確保することを推奨します。[詳細](https://cloud.google.com/bigtable/docs/schema-design)
</div></details>

### Q. 質問41: 未回答
サーバーレスのオーケストレーションとワークフローの調整を必要とするデータ処理パイプラインを構築しています。このシナリオに最適な Google Cloud サービスはどれですか?
1. Cloud Composer 
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Composer は、サーバーレス オーケストレーションとデータ処理システムでのワークフローの調整に適した、フルマネージドのワークフロー オーケストレーション サービスです。さまざまなサービスやツールの統合をサポートします。詳細: [Cloud Composer の概要](https://cloud.google.com/composer/docs)
</div></details>

### Q. 質問42: 未回答
BigQuery SQL クエリの HAVING 句の目的は何ですか?
1. 
2. 
3. 条件に基づいてグループ化された行をフィルタリング
4. 
<details><div>
    答え：
説明
BigQuery の HAVING 句は、集計クエリの条件に基づいてグループ化された行をフィルタリングするために使用されます。
</div></details>

### Q. 質問43: 未回答
Cloud Spanner のアクセス制御を設定しています。データセキュリティとコンプライアンスのコンテキストにおけるIDおよびアクセス管理(IAM)条件の役割は何ですか?
1. コンテキストに応じたアクセス ポリシーを定義し
2. 
3. 
4. 時間ベースのアクセス制限を適用
<details><div>
    答え：
説明
Google Cloud Spanner の IAM 条件を使用すると、コンテキストに応じたアクセス ポリシーを定義し、時間ベースのアクセス制限を適用できます。条件を使用することで、特定の基準に基づいてアクセス制御を調整し、セキュリティと規制要件への準拠を強化できます。詳細については、[IAM 条件](https://cloud.google.com/iam/docs/conditions-overview) を参照してください。
</div></details>

### Q. 質問44: 未回答
イベントタイム ウィンドウ処理によるリアルタイム ストリーム処理を必要とするデータ処理パイプラインを設計しています。このシナリオに最も適した Google Cloud サービスはどれですか?
1. Cloud Dataflow 
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataflow は、データ処理パイプラインでイベントタイム ウィンドウを使用したリアルタイム ストリーム処理用に設計されています。ストリーミング データを処理および分析するためのフル マネージドのサーバーレス環境を提供します。追加情報: [Event Time Processing](https://cloud.google.com/dataflow/docs/concepts/event-time)
</div></details>

### Q. 質問45: 未回答
Google Cloud で安全なデータ転送のためのソリューションを設計しています。データ処理パイプライン内のサービス間の転送中にデータを保護するために、どのような暗号化オプションを使用できますか?
1. 
2. TLS/SSL 暗号化
3. 
4. 
<details><div>
    答え：
説明
データ処理パイプライン内のサービス間の転送中にデータを保護するには、TLS/SSL 暗号化を使用する必要があります。これにより、サービス間の安全な通信が保証され、転送中のデータの不正アクセスや改ざんが防止されます。詳細については、ドキュメントを参照してください: [転送中の暗号化](https://cloud.google.com/security/encryption-in-transit)
</div></details>

### Q. 質問46: 未回答
機械学習モデルの分散トレーニングに AI Platform Training を使用している。トレーニングジョブを送信するときの '--scale-tier' フラグの目的は何ですか?
1. 
2. 分散トレーニングを有効にする
3. 
4. 
<details><div>
    答え：
説明
AI Platform Training の「--scale-tier」フラグは、トレーニング タスクのマシンタイプとインスタンス数を指定することで、分散トレーニングを有効にするために使用されます。[AI Platform トレーニング スケーリング](https://cloud.google.com/ai-platform/training/docs/training-jobs)
</div></details>

### Q. 質問47: 未回答
並列化された計算による大規模なデータセットのバッチ処理を含むデータ処理パイプラインを設計する必要があります。このシナリオに最適な Google Cloud サービスはどれですか?
1. 
2. 
3. Cloud Dataproc 
4. 
<details><div>
    答え：
説明
Cloud Dataproc はフルマネージドの Apache Spark および Hadoop サービスで、並列計算による大規模なデータセットのバッチ処理に適しています。スケーラブルで費用対効果の高いソリューションを提供します。詳細: [Cloud Dataproc の概要](https://cloud.google.com/dataproc/docs)
</div></details>

### Q. 質問48: 未回答
クラウドベースのデータ処理システムにおいて、Cloud Dataflow でストリーミング データを処理する際に、データの鮮度を管理する上で重要な考慮事項は何ですか?
1. 
2. 
3. クエリのパフォーマンスを最適化
4. 
<details><div>
    答え：
説明
Cloud Dataflow でストリーミング データを処理する際に、クラウドベースのデータ処理システムでデータの鮮度を管理するには、クエリのパフォーマンスを最適化することが重要な考慮事項です。[詳細](https://cloud.google.com/dataflow/docs/concepts/streaming-best-practices)
</div></details>

### Q. 質問49: 未回答
データ処理ワークロードが変化するシナリオでは、カスタマイズされたランタイム環境と依存関係でデータ処理ジョブを実行するのに適した Google Cloud サービスはどれですか?
1. 
2. 
3. 
4. Cloud Dataproc
<details><div>
    答え：
説明
Cloud Dataproc は、データ処理ワークロードが変化するシナリオで、カスタマイズされたランタイム環境と依存関係を使用してデータ処理ジョブを実行するのに適しています。[詳細](https://cloud.google.com/dataproc/docs)
</div></details>

### Q. 質問50: 未回答
Cloud Dataflow パイプラインでデータのプライバシーを考慮して設計する場合、変換と処理のステップで機密情報を処理するための推奨されるアプローチは何ですか?
1. 
2. 
3. きめ細かなアクセス制御の実装
4. 
<details><div>
    答え：
説明
きめ細かなアクセス制御の実装は、Cloud Dataflow パイプライン内の変換と処理のステップで機密情報を処理し、安全なデータ処理を確保するために推奨されるアプローチです。[詳細](https://cloud.google.com/dataflow/docs/concepts/security-and-compliance)
</div></details>

### Q. 質問51: 未回答
Cloud Dataflow パイプラインでデータ セキュリティを設計する場合、処理ステージ間の通信を保護するためのおすすめの方法は何ですか?
1. 
2. ファイアウォールを実装してネットワーク アクセスを制限
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataflow の処理ステージ間の通信を保護するためのおすすめの方法は、ファイアウォールを実装してネットワーク アクセスを制限し、データのセキュリティを強化することです。[詳細](https://cloud.google.com/dataflow/docs/concepts/security-and-compliance)
</div></details>

### Q. 質問52: 未回答
ハイパーパラメータの調整に AI Platform Training を使用している。ハイパーパラメータ調整ジョブを設定する際の「--objective」フラグの目的は何ですか?
1. 
2. 最適化目標(最適化する指標)を設定
3. 
4. 
<details><div>
    答え：
説明
AI Platform Training の「--objective」フラグは、ハイパーパラメータ調整ジョブを構成する際に、最適化目標(最適化する指標)を設定するために使用されます。[AI Platform Training Hyperparameter Tuning の目的](https://cloud.google.com/ai-platform/training/docs/hyperparameter-tuning)
</div></details>

### Q. 質問53: 未回答
データ処理に機密情報が含まれ、コンプライアンスが重要なシナリオでは、処理されたデータを含む Cloud Storage バケットへのアクセス制御を管理するための推奨プラクティスは何ですか?
1. 
2. 
3. 
4. きめ細かなアクセス制御を使用
<details><div>
    答え：
説明
機密データを含む Cloud Storage バケットへのアクセス制御を管理するには、きめ細かなアクセス制御を使用して、コンプライアンスと安全なデータ処理を確保することをおすすめします。[詳細](https://cloud.google.com/storage/docs/access-control)
</div></details>

### Q. 質問54: 未回答
BigQuery の機密データを保護するのはお客様の責任です。BigQuery テーブルに保存されているデータを保護するには、どのような暗号化オプションを選択する必要がありますか?
1. 
2. サーバー側の暗号化
3. 
4. 
<details><div>
    答え：
説明
BigQuery テーブルに保存されているデータを保護するには、サーバー側の暗号化を使用する必要があります。これにより、BigQuery に保存されるデータが暗号化され、機密情報のセキュリティが強化されます。詳細については、[保存時の暗号化](https://cloud.google.com/bigquery/docs/reference/auditlogs)を参照してください。
</div></details>

### Q. 質問55: 未回答
データ処理パイプラインのリアルタイム監視とアラートを実装する必要があります。この目的に最も適した Google Cloud サービスはどれですか?
1. 
2. 
3. 
4. Cloud Monitoring
<details><div>
    答え：
説明
Cloud Monitoring は、データ処理パイプラインでのリアルタイムのモニタリングとアラートに推奨されるサービスです。これにより、メトリックに基づいてカスタム アラートを設定し、リソースの正常性とパフォーマンスを監視できます。詳細: [Cloud Monitoring の概要](https://cloud.google.com/monitoring/docs)
</div></details>

### Q. 質問56: 未回答
あなたは、リアルタイムのイベント駆動型関数を含むデータ処理パイプラインを設計する任務を負っています。このシナリオに最適な Google Cloud サービスはどれですか?
1. Cloud Functions 
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Functions は、データ処理パイプラインにおけるリアルタイムのイベントドリブン関数向けに設計されています。これにより、イベントに応答してコードを実行できるため、サーバーレスのアプリケーションやサービスの構築に適しています。詳細: [Cloud Functions の概要](https://cloud.google.com/functions/docs)
</div></details>

### Q. 質問57: 未回答
Cloud Storage でデータの耐久性を設計する場合、ロールバック機能が重要なシナリオでバージョニングを処理するための推奨プラクティスは何ですか?
1. 
2. オブジェクトへの変更を経時的に追跡する
3. 
4. 
<details><div>
    答え：
説明
バージョニングによってオブジェクトへの変更を経時的に追跡することは、ロールバック機能を処理し、Cloud Storage でデータの耐久性を確保するための推奨される方法です。[詳細](https://cloud.google.com/storage/docs/object-versioning)
</div></details>

### Q. 質問58: 未回答
BigQuery のアクセス制御を設定しています。データのセキュリティとコンプライアンスのコンテキストにおけるビューの目的は何ですか?
1. 
2. テーブル内の特定の列へのアクセスを制御
3. 
4. 
<details><div>
    答え：
説明
BigQuery では、テーブル内の特定の列へのアクセスを制御するためにビューが使用されます。ビューを作成することで、ユーザーに表示される列を制限し、許可された個人のみが機密情報にアクセスできるようにすることができます。詳細については、[ビューの作成](https://cloud.google.com/bigquery/docs/views)を参照してください。
</div></details>

### Q. 質問59: 未回答
Cloud Functions を使用してサーバーレス データ処理パイプラインを設計する場合、処理エラーを処理するために再試行する目的と、信頼性にどのように貢献しますか?
1. 
2. 処理エラーに対するフォールト トレランスを提供
3. 
4. 
<details><div>
    答え：
説明
Cloud Functions での再試行は、処理エラーに対するフォールト トレランスを提供し、失敗した関数の実行を自動的に再試行してシステムの復元力を向上させることで、信頼性に貢献します。[詳細](https://cloud.google.com/functions/docs/concepts/exec#retrying-background-functions)
</div></details>

### Q. 質問60: 未回答
機械学習モデルの配信に AI Platform Prediction を使用している。モデル バージョンをデプロイするときに '--accelerator-type' フラグを設定する目的は何ですか?
1. 
2. 
3. GPU アクセラレーションが有効
4. 
<details><div>
    答え：
説明
AI Platform Prediction で「--accelerator-type」フラグを設定すると、モデル バージョンのデプロイ中に GPU アクセラレーションが有効になり、予測のパフォーマンスが向上します。[AIプラットフォーム予測アクセラレータタイプ](https://cloud.google.com/ai-platform/prediction/docs/deploying-models#accelerator-type)
</div></details>

### Q. 質問61: 未回答
データ処理環境での Cloud Key Management Service(KMS)の目的は何ですか?
1. 
2. データ暗号化を強化
3. 
4. 
<details><div>
    答え：
説明
Cloud Key Management Service(KMS)は、データ処理環境でのデータ暗号化を強化するために使用されます。これにより、機密情報を保護するための暗号化キーを管理できます。詳細: [Cloud KMS の概要](https://cloud.google.com/kms/docs)
</div></details>

### Q. 質問62: 未回答
Cloud Composer で、Cloud Storage バケットへの変更に基づいて機械学習ワークフローをトリガーします。このタスクに適した Cloud Composer コンポーネントはどれですか?
1. 
2. 
3. FileSensor
4. 
<details><div>
    答え：
説明
Cloud Composer の「FileSensor」は、Cloud Storage バケットへの変更に基づいてワークフローをトリガーするのに適しています。指定されたファイルまたはフォルダーの変更を監視します。[Cloud Composer FileSensor] (クラウド コンポーザー FileSensor)(https://cloud.google.com/composer/docs/how-to/using/sensors#filesensor)
</div></details>

### Q. 質問63: 未回答
データから有意義な洞察を得るための設計を行う場合、クラウドベースの環境で適切な視覚化ツールと手法を選択するための推奨プラクティスは何ですか?
1. 
2. 明確で意味のあるラベルを活用
3. 
4. 
<details><div>
    答え：
説明
適切な視覚化ツールと手法を選択するための推奨されるプラクティスは、クラウドベースの環境で明確で意味のあるラベルを活用し、分析情報の解釈可能性とコミュニケーションを強化することです。[詳細](https://cloud.google.com/solutions/data-visualization-and-business-intelligence)
</div></details>

### Q. 質問64: 未回答
機械学習機能が組み込まれた分析用のフルマネージドでスケーラブルなサーバーレス データ ウェアハウスを提供する Google Cloud サービスはどれですか?
1. 
2. 
3. BigQuery
4. 
<details><div>
    答え：
説明
BigQuery は、分析用の機械学習機能を内蔵した、スケーラブルでサーバーレスなフルマネージドのデータ ウェアハウスです。これにより、SQLに似たクエリを使用して大規模なデータセットを分析できます。詳細: [BigQuery ML の概要](https://cloud.google.com/bigquery-ml/docs)
</div></details>

### Q. 質問65: 未回答
データポータルを BigQuery データセットに接続する場合、デフォルトの接続を使用するのではなく、カスタムクエリを設定する目的は何ですか?
1. 
2. 
3. カスタム変換を適用
4. 
<details><div>
    答え：
説明
データポータルでカスタムクエリを設定すると、データを視覚化する前にカスタム変換を適用できるため、データ準備の柔軟性が高まります。
</div></details>

### Q. 質問66: 未回答
AI Platform Prediction で新しいバージョンの機械学習モデルにカナリア デプロイ戦略を実装したい。デプロイプロセス中の「--traffic-split」フラグの目的は何ですか?
1. 
2. 
3. 
4. バージョン間で予測リクエストのバランス
<details><div>
    答え：
説明
AI Platform Prediction の「--traffic-split」フラグは、モデルの異なるバージョン間で予測リクエストのバランスを取り、カナリア デプロイとパフォーマンスのモニタリングを可能にするために使用されます。[AI Platform 予測トラフィック分割](https://cloud.google.com/ai-platform/prediction/docs/deploying-models#traffic-split)
</div></details>

### Q. 質問67: 未回答
Cloud Firestore に保存されているデータに対して、きめ細かなアクセス制御を実装する必要があります。どの機能を使うべきか?
1. 
2. 
3. IAM
4. 
<details><div>
    答え：
説明
Cloud Firestore の IAM(Identity and Access Management)ポリシーは、データのきめ細かなアクセス制御を実装するために使用されます。データベースにアクセスできるユーザーと、そのユーザーが実行できるアクションを指定できます。詳細: [Cloud Firestore IAM](https://cloud.google.com/firestore/docs/security/iam)
</div></details>

### Q. 質問68: 未回答
BigQuery の Google Cloud Console のクエリ履歴機能について、次の記述のうち正しいものはどれですか?
1. 実行時間と費用の詳細が表示されます
2. 
3. 
4. 実行されたクエリのリスト
<details><div>
    答え：
説明
BigQuery のクエリ履歴機能には、実行されたクエリのリストと、実行時間と費用の詳細が表示されます。
</div></details>

### Q. 質問69: 未回答
データ処理システムにおいて、Cloud Identity and Access Management(IAM)条件の目的は何ですか?
1. 
2. きめ細かなアクセス制御の実施
3. 
4. 
<details><div>
    答え：
説明
Cloud IAM 条件は、データ処理環境における IP アドレスやデバイスのステータスなどの条件に基づいてコンテキスト アクセス ポリシーを適用できるようにすることで、セキュリティをさらに強化します。追加情報: [IAM 条件の概要](https://cloud.google.com/iam/docs/conditions-overview)
</div></details>

### Q. 質問70: 未回答
データエンリッチメントのために外部 API との統合を必要とするデータ処理パイプラインを設計しています。このシナリオに最適な Google Cloud サービスはどれですか?
1. 
2. 
3. Cloud Functions
4. 
<details><div>
    答え：
説明
Cloud Functions は、イベントドリブン関数にサーバーレス コンピューティングを提供するため、データ処理パイプラインでデータを強化するために外部 API と統合するのに適しています。これにより、イベントに応答してコードを実行できます。詳細: [Cloud Functions の概要](https://cloud.google.com/functions/docs)
</div></details>

### Q. 質問71: 未回答
クラウドベースのデータ処理システムにおいて、Cloud Composer によってオーケストレーションされたワークフローでタスク間の依存関係を管理するためのベスト プラクティスは何ですか?
1. 
2. 
3. 有向非巡回グラフ(DAG)でタスクの依存関係を明示的に定義
4. 
<details><div>
    答え：
説明
Cloud Composer ワークフローでタスク間の依存関係を管理するためのベスト プラクティスは、有向非巡回グラフ(DAG)でタスクの依存関係を明示的に定義し、明確で信頼性の高い実行順序を確保することです。[詳細](https://cloud.google.com/composer/docs/concepts/overview)
</div></details>

### Q. 質問72: 未回答
機械学習モデルのハイパーパラメータ調整に AI Platform Training を使用している。ハイパーパラメーター調整ジョブを構成する際の '--max-hyperparameter-trials' フラグの目的は何ですか?
1. 
2. 
3. ハイパーパラメータの組み合わせの最大数を指定
4. 
<details><div>
    答え：
説明
AI Platform Training の「--max-hyperparameter-trials」フラグは、ハイパーパラメータ調整ジョブ中に探索するハイパーパラメータの組み合わせの最大数を指定するために使用されます。[AI Platform トレーニングのハイパーパラメータ調整](https://cloud.google.com/ai-platform/training/docs/hyperparameter-tuning)
</div></details>

### Q. 質問73: 未回答
大規模なデータセットでリアルタイム分析が必要なシナリオでは、低レイテンシのアクセスでストリーミング データを取り込んで処理するのに適した Google Cloud サービスはどれですか?
1. 
2. Cloud Dataflow
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataflow は、低レイテンシのアクセスでストリーミング データを取り込んで処理するのに適しており、大規模なデータセットのリアルタイム分析のためのフルマネージドのサーバーレス ソリューションを提供します。[詳細](https://cloud.google.com/dataflow/docs)
</div></details>

### Q. 質問74: 未回答
Cloud Dataprep のデータ処理ジョブで保守性を考慮して設計する場合、パラメータ化の役割と、ジョブの柔軟性を高める方法を教えてください。
1. 
2. ジョブ設定の動的な構成
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataprep データ処理ジョブのパラメータ化により、ジョブ設定の動的な構成が可能になり、データ エンジニアが変化する要件に基づいて処理を適応およびカスタマイズできるため、ジョブの柔軟性が向上します。[詳細](https://cloud.google.com/dataprep/docs/html/ParametersPage_57338558)
</div></details>

### Q. 質問75: 未回答
データ処理環境におけるCloud Security Command Center(Cloud SCC)の主な目的は何ですか?
1. 
2. 
3. セキュリティとリスク管理
4. 
<details><div>
    答え：
説明
Cloud Security Command Center(Cloud SCC)は、データ処理環境におけるセキュリティとリスク管理のために設計されています。セキュリティ関連データを一元的に可視化し、セキュリティリスクの特定と軽減を支援します。詳細: [Cloud SCC の概要](https://cloud.google.com/security-command-center/docs)
</div></details>

## 4
### Q. 質問1: 未回答
モバイル アプリケーションやウェブ アプリケーション向けに、フルマネージドでスケーラブルなサーバーレスの NoSQL データベースを提供する Google Cloud サービスはどれですか?
1. 
2. Cloud Firestore
3. 
4. 
<details><div>
    答え：
説明
Cloud Firestore は、モバイルおよびウェブ アプリケーション向けに設計された、フルマネージドでスケーラブルなサーバーレスの NoSQL データベースです。柔軟なデータモデルを提供し、自動スケーリングをサポートします。詳細: [Cloud Firestore の概要](https://cloud.google.com/firestore/docs)
</div></details>

### Q. 質問2: 未回答
データ処理ワークロードが変化するシナリオでは、Cloud Storage、Pub/Sub、または HTTP トリガーからのイベントに応答できるサーバーレス関数の作成に適した Google Cloud サービスはどれですか?
1. 
2. 
3. 
4. Cloud Functions
<details><div>
    答え：
説明
Cloud Functions は、Cloud Storage、Pub/Sub、HTTP トリガーからのイベントに応答できるサーバーレス関数の作成に適しており、データ処理ワークロードに柔軟性とスケーラビリティを提供します。[詳細](https://cloud.google.com/functions/docs)
</div></details>

### Q. 質問3: 未回答
データセットが大きいデータポータルのレポートのパフォーマンスを向上させることができるアクションは、次のうちどれですか?
1. データ集計関数を使用
2. フィルターを適用してデータを制限
3. 
4. 
<details><div>
    答え：
説明
パフォーマンスを向上させるには、フィルターを適用してデータを制限し、データ集計関数を使用して情報を意味のある方法で要約します。
</div></details>

### Q. 質問4: 未回答
データ処理環境での Cloud Storage Transfer Service の主な目的は何ですか?
1. 
2. 
3. Cloud Storage バケット間のデータ転送
4. 
<details><div>
    答え：
説明
Cloud Storage Transfer Service は、データ処理システム内の Cloud Storage バケット間のデータ転送を自動化およびスケジュールするために使用されます。これにより、データ移動の管理プロセスが簡素化されます。詳細:[転送サービスの概要](https://cloud.google.com/storage-transfer/docs)
</div></details>

### Q. 質問5: 未回答
AI Platform Training を使用して、TensorFlow で機械学習モデルをトレーニングしています。トレーニングジョブを送信する際の「--runtime-version」フラグの目的は何ですか?
1. 
2. 
3. 
4. TensorFlow ランタイム バージョンを指定する
<details><div>
    答え：
説明
AI Platform Training の「--runtime-version」フラグは、トレーニング ジョブの送信時に TensorFlow ランタイム バージョンを指定するために使用され、目的の TensorFlow バージョンとの互換性を確保します。[AI Platform Training ランタイム バージョン](https://cloud.google.com/ai-platform/training/docs/training-jobs#runtime-version)
</div></details>

### Q. 質問6: 未回答
データから有意義な洞察を得るための設計を行う場合、クラウドベースの環境で適切な視覚化ツールと手法を選択するための推奨されるプラクティスは何ですか?
1. 
2. 明確で意味のあるラベルを活用
3. 
4. 
<details><div>
    答え：
説明
適切な視覚化ツールと手法を選択するための推奨されるプラクティスは、クラウドベースの環境で明確で意味のあるラベルを活用し、分析情報の解釈可能性とコミュニケーションを強化することです。[詳細](https://cloud.google.com/solutions/data-visualization-and-business-intelligence)
</div></details>

### Q. 質問7: 未回答
機械学習モデルを使用したリアルタイムの異常検出を必要とするデータ処理パイプラインを設計しています。このシナリオに最も適した Google Cloud サービスはどれですか?
1. 
2. 
3. Cloud AI Platform
4. 
<details><div>
    答え：
説明
Cloud AI Platform は、機械学習モデルのデプロイと管理を目的として設計されているため、データ処理パイプラインで機械学習を使用したリアルタイムの異常検出に適しています。スケーラブルでサーバーレスな環境を提供します。詳細: [Cloud AI Platform の概要](https://cloud.google.com/ai-platform/docs)
</div></details>

### Q. 質問8: 未回答
機械学習モデルの分散トレーニングに AI Platform Training を使用している。トレーニングジョブを送信するときの「--worker-machine-type」フラグの目的は何ですか?
1. 
2. 
3. ワーカー ノードのマシンタイプを指定
4. 
<details><div>
    答え：
説明
AI Platform Training の「--worker-machine-type」フラグは、分散トレーニング ジョブを送信するときにワーカー ノードのマシンタイプを指定するために使用されます。[AI Platform Training Worker マシンタイプ](https://cloud.google.com/ai-platform/training/docs/training-jobs)
</div></details>

### Q. 質問9: 未回答
Cloud Dataflow を使用して、機械学習ワークフローのストリーミング データを処理している。ストリーミング データ処理のコンテキストでウィンドウ処理を行う目的は何ですか?
1. 
2. 
3. 時間ベースのデータ集計を管理
4. 
<details><div>
    答え：
説明
Cloud Dataflow では、ストリーミング データ処理で時間ベースのデータ集計を管理するためにウィンドウが使用され、時間の経過に伴うデータのグループ化方法を定義できます。[クラウドデータフローウィンドウ](https://cloud.google.com/dataflow/docs/concepts/windowing)
</div></details>

### Q. 質問10: 未回答
機械学習モデルの配信に AI Platform Prediction を使用している。予測インスタンスの自動スケーリングを構成する際の '--min-nodes' フラグと '--max-nodes' フラグの目的は何ですか?
1. 
2. 
3. 自動スケーリングの制限を設定
4. 
<details><div>
    答え：
説明
AI Platform Prediction で「--min-nodes」フラグと「--max-nodes」フラグを設定するのは、自動スケーリングの制限を設定し、予測サービスのインスタンス(レプリカ)の最小数と最大数を制御するためのものです。[AI Platform 予測の自動スケーリング](https://cloud.google.com/ai-platform/prediction/docs/autoscaling)
</div></details>

### Q. 質問11: 未回答
機械学習モデルのトレーニングに AI Platform Training を使用しています。トレーニングジョブを送信するときに「--config」フラグを設定する目的は何ですか?
1. 
2. ハイパーパラメータの設定
3. 
4. 
<details><div>
    答え：
説明
AI Platform Training の「--config」フラグは、トレーニング ジョブを送信するときにハイパーパラメータ値を含む構成ファイルを指定するために使用されます。[AI Platform トレーニング ハイパーパラメータの設定](https://cloud.google.com/ai-platform/training/docs/training-jobs#config)
</div></details>

### Q. 質問12: 未回答
データポータルのレポートで、さまざまな商品カテゴリの収益を比較します。この分析に最も適したチャートの種類はどれですか?
1. 
2. 
3. 
4. 棒グラフ
<details><div>
    答え：
説明
棒グラフは、データポータルのレポートでさまざまな商品カテゴリの収益を比較するのに最適です。
</div></details>

### Q. 質問13: 未回答
ハイパーパラメータの調整に AI Platform Training を使用している。ハイパーパラメータ調整ジョブを設定する際の「--parameter-server-machine-type」フラグの目的は何ですか?
1. マスターノードのマシンタイプを指定
2. 
3. 
4. 
<details><div>
    答え：
説明
AI Platform Training の「--parameter-server-machine-type」フラグは、ハイパーパラメータ調整ジョブを構成する際にマスターノードのマシンタイプを指定するために使用されます。[AI Platform トレーニングのハイパーパラメータ調整](https://cloud.google.com/ai-platform/training/docs/hyperparameter-tuning)
</div></details>

### Q. 質問14: 未回答
CPU とメモリの使用率に基づく自動スケーリングを必要とするデータ処理パイプラインを構築しています。データ処理システム内の仮想マシンの自動スケーリングを提供する Google Cloud サービスはどれですか?
1. Compute Engine
2. 
3. 
4. 
<details><div>
    答え：
説明
Compute Engine では、データ処理システムの CPU とメモリの使用率に基づいて自動スケーリングを行う仮想マシンを作成できます。これにより、インフラストラクチャに対する柔軟性と制御が提供されます。詳細: [Compute Engine Autoscaler](https://cloud.google.com/compute/docs/autoscaler)
</div></details>

### Q. 質問15: 未回答
Cloud SQL のデータ アクセス制御を実装している。データのセキュリティとコンプライアンスの観点から、限定公開の Google アクセスの目的は何ですか?
1. インスタンスはパブリック IP アドレスなしで Google サービスにアクセス
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud SQL の限定公開の Google アクセスを使用すると、インスタンスはパブリック IP アドレスなしで Google サービスにアクセスできます。これにより、公共のインターネットへの露出を減らし、潜在的な攻撃ベクトルを制限し、他の Google サービスとの安全な通信を促進することで、セキュリティとコンプライアンスが強化されます。詳細については、[限定公開の Google Access for Cloud SQL](https://cloud.google.com/sql/docs/mysql/private-ip)をご覧ください。
</div></details>

### Q. 質問16: 未回答
データ処理システムにおいて、Cloud Memorystore の目的は何ですか?
1. 
2. 
3. インメモリ データ キャッシュ
4. 
<details><div>
    答え：
説明
Cloud Memorystore は、データ処理システムでのインメモリ データ キャッシュに使用されるフルマネージドのインメモリ データ ストア サービスです。これは、頻繁にアクセスされるデータをキャッシュするための高速でスケーラブルなソリューションを提供します。詳細: [Cloud Memorystore の概要](https://cloud.google.com/memorystore/docs)
</div></details>

### Q. 質問17: 未回答
Cloud Dataprep のデータ処理ジョブでデータの信頼性を設計する場合、一貫性のあるデータ変換を確保する上でスキーマはどのような役割を果たしますか?
1. 
2. データの構造と形式を検証
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataprep データ処理ジョブのスキーマは、データの構造と形式を検証し、データの品質と整合性を維持することで、一貫性のあるデータ変換を確保する上で重要な役割を果たします。[詳細](https://cloud.google.com/dataprep/docs/html/Schema-Pages_57341425)
</div></details>

### Q. 質問18: 未回答
Cloud Composer では、複数のタスクを含む機械学習ワークフローを設計します。Apache Airflow と Cloud Composer の 'BranchPythonOperator' の目的は何ですか?
1. 
2. 
3. 条件に基づいてタスクをトリガー
4. 
<details><div>
    答え：
説明
Apache Airflow と Cloud Composer の「BranchPythonOperator」は、条件に基づいてタスクをトリガーするために使用され、ワークフローの実行フローを動的に制御できます。[Cloud Composer BranchPythonOperator] (クラウド コンポーザー ブランチ パイソン オペレーター)(https://cloud.google.com/composer/docs/how-to/using/operators#branchpythonoperator)
</div></details>

### Q. 質問19: 未回答
データ処理環境での Cloud Armor の主な目的は何ですか?
1. 
2. 
3. DDoS 攻撃からの保護を提供し、データ処理システムのウェブ アプリケーション ファイアウォールとして機能
4. 
<details><div>
    答え：
説明
Cloud Armor は DDoS 攻撃からの保護を提供し、データ処理システムのウェブ アプリケーション ファイアウォールとして機能します。アプリケーションやサービスをサイバー脅威から保護し、トラフィックが急増した場合の可用性を確保します。詳細: [Cloud Armor の概要](https://cloud.google.com/armor/docs)
</div></details>

### Q. 質問20: 未回答
Cloud SQL のアクセス制御を設定しています。オンプレミスまたは Google Cloud の外部で実行されているアプリケーションのデータベース接続を保護するというコンテキストにおける Cloud SQL Proxy の役割は何ですか?
1. 
2. アプリケーションのユーザー ID を検証
3. 
4. 
<details><div>
    答え：
説明
Google Cloud SQL の Cloud SQL Proxy は、オンプレミスまたは Google Cloud の外部で実行されているアプリケーションのユーザー ID を検証するために使用されます。データベースをパブリック インターネットに公開することなく、Cloud SQL データベースに安全に接続する方法を提供し、セキュリティとコンプライアンスを強化します。詳細については、[Cloud SQL Proxy](https://cloud.google.com/sql/docs/mysql/sql-proxy)のドキュメントをご覧ください。
</div></details>

### Q. 質問21: 未回答
データポータルでリアルタイム データを視覚化する必要があります。これを実現するための推奨されるアプローチは何ですか?
1. 
2. データポータル API を使用
3. 
4. 
<details><div>
    答え：
説明
データポータルでリアルタイム データを視覚化するには、データポータル API を使用して、データソースからのリアルタイム更新を有効にします。
</div></details>

### Q. 質問22: 未回答
Cloud Dataflow パイプラインでスケーラビリティを設計する場合、イベント時の処理で遅れて到着したデータを処理するには、どのようなアプローチをお勧めしますか?
1. 別のウィンドウで再処理
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataflow で遅れて到着したデータを処理するには、別のウィンドウで再処理して、すべてのデータを正確かつ包括的に分析することをおすすめします。[詳細](https://cloud.google.com/dataflow/docs/concepts/event-time)
</div></details>

### Q. 質問23: 未回答
Apache Kafka を使用したリアルタイムのイベントストリーミングと処理を必要とするデータ処理パイプラインを設計しています。このシナリオに最も適した Google Cloud サービスはどれですか?
1. 
2. 
3. Cloud Pub/Sub
4. 
<details><div>
    答え：
説明
Cloud Pub/Sub は、データ処理パイプラインでのリアルタイムのイベント ストリーミングと処理用に設計されています。イベントデータの取り込みと配信をサポートするメッセージングサービスを提供します。詳細: [Cloud Pub/Sub の概要](https://cloud.google.com/pubsub/docs)
</div></details>

### Q. 質問24: 未回答
Cloud Spanner のアクセス制御を設定しています。データのセキュリティとコンプライアンスのコンテキストにおける監査ログの目的は何ですか?
1. データベースへのアクセスと変更を記録
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Spanner の監査ログは、データベースへのアクセスと変更を記録するために不可欠です。操作の詳細なログを提供し、誰がデータベースにアクセスし、どのようなアクションが実行されたかを追跡することで、規制要件に準拠し、データセキュリティを強化するのに役立ちます。詳細については、[監査ログ](https://cloud.google.com/spanner/docs/audit-logging)を参照してください。
</div></details>

### Q. 質問25: 未回答
Cloud Storage に保存されているデータに対して、きめ細かなアクセス制御を実装する必要があります。どの機能を使うべきか?
1. IAM
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Storage の IAM(Identity and Access Management)ポリシーは、データに対するきめ細かなアクセス制御を実装するために使用されます。オブジェクトにアクセスできるユーザーと、そのユーザーが実行できるアクションを指定できます。詳細: [Cloud Storage IAM](https://cloud.google.com/storage/docs/access-control/iam)
</div></details>

### Q. 質問26: 未回答
ビジュアル インターフェイスを使用したデータ変換とクレンジングを含むデータ処理パイプラインの設計を担当します。このシナリオに最適な Google Cloud サービスはどれですか?
1. Cloud Dataprep 
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataprep は、データ処理パイプラインのビジュアル インターフェースを使用したデータの変換とクレンジング用に設計されています。これは、データの探索と準備のための視覚的でインタラクティブなエクスペリエンスを提供します。詳細: [Cloud Dataprep の概要](https://cloud.google.com/dataprep/docs)
</div></details>

### Q. 質問27: 未回答
AI Platform Prediction のコンテキストで、モデル バージョンのデプロイ時に「--min-replicas」フラグを指定する目的は何ですか?
1. 
2. 
3. 
4. レプリカ(インスタンス)の最小数を制御
<details><div>
    答え：
説明
AI Platform Prediction の「--min-replicas」フラグは、予測サービス内のレプリカ(インスタンス)の最小数を制御することで、自動スケーリングの制限を設定するために使用されます。[AI Platform 予測の自動スケーリング](https://cloud.google.com/ai-platform/prediction/docs/autoscaling)
</div></details>

### Q. 質問28: 未回答
Cloud Storage 内のデータを保護する責任はお客様にあります。データセキュリティとコンプライアンスのコンテキストで顧客提供の暗号化キー(CSEK)を使用する目的は何ですか?
1. 
2. 暗号化レイヤを追加
3. 
4. 
<details><div>
    答え：
説明
Google Cloud Storage の顧客提供の暗号鍵(CSEK)は、保存データの暗号化レイヤを追加します。CSEKは、お客様が独自の暗号化キーを管理できるようにすることで、保存データの制御とセキュリティを強化し、データ保護要件への準拠に貢献します。詳細については、[お客様提供の暗号化キー](https://cloud.google.com/storage/docs/encryption#customer-supplied_encryption_keys)のドキュメントを参照してください。
</div></details>

### Q. 質問29: 未回答
機械学習モデルの配信に AI Platform Prediction を使用している。デプロイプロセス中に「--framework」フラグを設定する目的は何ですか?
1. 予測ランタイム フレームワークを構成
2. 
3. 
4. 
<details><div>
    答え：
説明
AI Platform Prediction で「--framework」フラグを設定するのは、デプロイ プロセス中に予測ランタイム フレームワークを構成するためのものです。[AIプラットフォーム予測フレームワーク](https://cloud.google.com/ai-platform/prediction/docs/deploying-models#framework)
</div></details>

### Q. 質問30: 未回答
Cloud Bigtable に保存されているデータに対して、きめ細かなアクセス制御を実装する必要があります。どの機能を使うべきか?
1. 
2. 
3. IAM
4. 
<details><div>
    答え：
説明
Cloud Bigtable の IAM(Identity and Access Management)ポリシーは、データのきめ細かなアクセス制御を実装するために使用されます。データベースにアクセスできるユーザーと、そのユーザーが実行できるアクションを指定できます。詳細: [Cloud Bigtable IAM](https://cloud.google.com/bigtable/docs/access-control)
</div></details>

### Q. 質問31: 未回答
機械学習ワークフローでデータを前処理するために Cloud Dataflow を使用している。Dataflow パイプラインの実行時に「--temp_location」フラグを指定する目的は何ですか?
1. 
2. 
3. 
4. パイプライン実行用の一時保存場所を指定
<details><div>
    答え：
説明
Cloud Dataflow の「--temp_location」フラグは、パイプライン実行用の一時保存場所を指定するために使用され、中間データと一時データの場所を提供します。[Cloud Dataflow の一時保存場所](https://cloud.google.com/dataflow/docs/guides/specifying-exec-params#temp_location)
</div></details>

### Q. 質問32: 未回答
カスタム データ処理ロジックが必要なシナリオでは、データ処理パイプラインの一部としてカスタム機械学習モデルを構築およびデプロイするのに適した Google Cloud サービスはどれですか?
1. AI Platform
2. 
3. 
4. 
<details><div>
    答え：
説明
AI Platform は、データ処理パイプラインの一部としてカスタム機械学習モデルを構築してデプロイするのに適しており、機械学習モデルのトレーニングと提供のためのマネージド環境を提供します。[詳細](https://cloud.google.com/ai-platform)
</div></details>

### Q. 質問33: 未回答
データ処理システムにおいて、Cloud Spanner の主な目的は何ですか?
1. 
2. 
3. 
4. グローバルに分散された水平方向にスケーラブルなデータベース
<details><div>
    答え：
説明
Cloud Spanner は、データ処理システムで高性能で一貫性のあるデータ処理を行うために設計された、グローバルに分散された水平方向にスケーラブルなデータベースです。強力な一貫性とグローバルトランザクション機能を提供します。詳細: [Cloud Spanner の概要](https://cloud.google.com/spanner/docs)
</div></details>

### Q. 質問34: 未回答
Cloud Composer を使用して機械学習ワークフローを設計しており、特定のタイムスケジュールに基づいてタスクをトリガーする必要があります。このタスクに適した Cloud Composer コンポーネントはどれですか?
1. 
2. 
3. 
4. TimeSensor
<details><div>
    答え：
説明
Cloud Composer の「TimeSensor」は、Apache Airflow と Cloud Composer で特定のタイムスケジュールに基づいてタスクをトリガーするのに適しています。[Cloud Composer TimeSensor] (クラウド コンポーザー タイムセンサー)(https://cloud.google.com/composer/docs/how-to/using/sensors#timesensor)
</div></details>

### Q. 質問35: 未回答
Cloud Storage ベースのデータ処理システムでデータ セキュリティを設計する場合、保存データを保護するための推奨プラクティスは何ですか?
1. 
2. 顧客提供のキーを使用して保存データを暗号化
3. 
4. 
<details><div>
    答え：
説明
Cloud Storage ベースのデータ処理システムで保存されているデータを保護するための推奨方法は、お客様が用意した鍵を使用してデータを暗号化し、追加のセキュリティ レイヤを提供することです。[詳細](https://cloud.google.com/storage/docs/encryption)
</div></details>

### Q. 質問36: 未回答
データ処理で急速に変化するデータのリアルタイム分析が必要なシナリオでは、低レイテンシのアクセスでストリーミング データを取り込んで処理するのに適した Google Cloud サービスはどれですか?
1. 
2. 
3. Cloud Dataflow 
4. 
<details><div>
    答え：
説明
Cloud Dataflow は、低レイテンシのアクセスでストリーミング データを取り込んで処理するのに適しており、急速に変化するデータをリアルタイムで分析するためのフルマネージドのサーバーレス ソリューションを提供します。[詳細](https://cloud.google.com/dataflow/docs)
</div></details>

### Q. 質問37: 未回答
AI Platform Training で、カスタム ワーカー プールを使用してトレーニング ジョブを送信するときに「--worker-pool-spec」フラグを使用する目的は何ですか?
1. 
2. 
3. 
4. カスタム ワーカー プールを使用
<details><div>
    答え：
説明
AI Platform Training の「--worker-pool-spec」フラグは、カスタム ワーカー プールを使用してトレーニング ジョブを送信するときに、ワーカー プールの構成をカスタマイズするために使用されます。[AI Platform トレーニング ワーカー プール](https://cloud.google.com/ai-platform/training/docs/training-jobs#custom-worker-pool)
</div></details>

### Q. 質問38: 未回答
AI Platform Prediction では、モデル バージョンをデプロイするときに「--model-type」フラグを使用する目的は何ですか?
1. 
2. 
3. 予測ランタイム フレームワークを構成
4. 
<details><div>
    答え：
説明
AI Platform Prediction の「--model-type」フラグは、デプロイ プロセス中に予測ランタイム フレームワークを構成するために使用されます。[AI Platform 予測モデルタイプ](https://cloud.google.com/ai-platform/prediction/docs/deploying-models#model-type)
</div></details>

### Q. 質問39: 未回答
Cloud Storage のアクセス制御を設定しています。データのセキュリティとコンプライアンスのコンテキストにおける VPC Service Controls の目的は何ですか?
1. データ流出を防ぐ
2. 
3. 
4. 
<details><div>
    答え：
説明
Google Cloud Storage の VPC Service Controls は、データ流出を防ぐために使用されます。VPC Service Controls は、オンプレミス ネットワークから Google Cloud までの範囲のアクセス境界を定義することで、承認されたソースからのみデータにアクセスできるようにし、全体的なセキュリティとコンプライアンスを強化します。詳細については、「VPC Service Controls の概要」(https://cloud.google.com/vpc-service-controls/docs/overview) を参照してください。
</div></details>

### Q. 質問40: 未回答
データ処理ワークロードが変化するシナリオでは、Apache Spark クラスタと Apache Hadoop クラスタでデータ処理ジョブを実行するのに適した Google Cloud サービスはどれですか?
1. 
2. 
3. Cloud Dataproc 
4. 
<details><div>
    答え：
説明
Cloud Dataproc は、データ処理ワークロードが変化するシナリオで、Apache Spark クラスタと Apache Hadoop クラスタを使用してデータ処理ジョブを実行するのに適しています。[詳細](https://cloud.google.com/dataproc/docs)
</div></details>

### Q. 質問41: 未回答
最も低コストでデータをアーカイブするために設計された Cloud Storage クラスはどれですか?
1. 
2. 
3. アーカイブ ストレージ クラス
4. 
<details><div>
    答え：
説明
Cloud Storage のアーカイブ ストレージ クラスは、最も低コストでデータをアーカイブできるように設計されています。めったにアクセスされず、長期保存が必要なデータに適しています。追加情報: [Cloud Storage Classes](https://cloud.google.com/storage/docs/storage-classes)
</div></details>

### Q. 質問42: 未回答
依存関係を持つタスクのオーケストレーションと調整を必要とするデータ処理パイプラインを構築しています。このシナリオに最適な Google Cloud サービスはどれですか?
1. 
2. Cloud Composer 
3. 
4. 
<details><div>
    答え：
説明
Cloud Composer は、データ処理システムで依存関係を持つタスクのオーケストレーションと調整に適した、フルマネージドのワークフロー オーケストレーション サービスです。さまざまなサービスやツールの統合をサポートします。詳細: [Cloud Composer ドキュメント](https://cloud.google.com/composer/docs)
</div></details>

### Q. 質問43: 未回答
Apache Hadoop を使用して、大規模なデータセットのバッチ処理を含むデータ処理パイプラインを設計する必要があります。このシナリオに最適な Google Cloud サービスはどれですか?
1. 
2. 
3. Cloud Dataproc 
4. 
<details><div>
    答え：
説明
Cloud Dataproc は、フルマネージドの Apache Hadoop および Apache Spark サービスであり、データ処理パイプラインで Apache Hadoop を使用して大規模なデータセットのバッチ処理に適しています。スケーラブルで費用対効果の高いソリューションを提供します。詳細: [Cloud Dataproc の概要](https://cloud.google.com/dataproc/docs)
</div></details>

### Q. 質問44: 未回答
低レイテンシと費用のバランスが取れた、アクセス頻度の低いデータ用に設計された Cloud Storage クラスはどれですか?
1. 
2. 
3.  Nearline ストレージ クラス
4. 
<details><div>
    答え：
説明
Cloud Storage の Nearline ストレージ クラスは、低レイテンシとコストのバランスが取れた、アクセス頻度の低いデータ向けに設計されています。これは、アクセス頻度の低いデータに対して費用対効果の高いソリューションを提供します。追加情報: [Cloud Storage Classes](https://cloud.google.com/storage/docs/storage-classes)
</div></details>

### Q. 質問45: 未回答
クラウドベースのデータ処理システムでデータ プライバシーを重視して設計する場合、機密データを含む Cloud Storage バケットへのアクセス制御を管理するには、どのような方法が推奨されますか?
1. 
2. 
3. きめ細かなアクセス制御を使用
4. 
<details><div>
    答え：
説明
機密データを含む Cloud Storage バケットへのアクセス制御を管理するには、きめ細かなアクセス制御を使用して、安全で制御されたデータ処理を行うことをおすすめします。[詳細](https://cloud.google.com/storage/docs/access-control)
</div></details>

### Q. 質問46: 未回答
機械学習ワークフローのバッチ処理ステップに Cloud Dataflow を使用している。Dataflow パイプラインを実行する際の「--max-num-workers」フラグの目的は何ですか?
1. 
2. 
3. 
4. ワーカー ノードの最大数を制御
<details><div>
    答え：
説明
Cloud Dataflow の「--max-num-workers」フラグは、Dataflow パイプライン内のワーカー ノードの最大数を制御するために使用され、リソースを効果的に管理できるようにします。[Cloud Dataflow Max Num Workers] (クラウドデータフロー最大ワーカー数)(https://cloud.google.com/dataflow/docs/guides/specifying-exec-params#max-num-workers)
</div></details>

### Q. 質問47: 未回答
Google Cloud で安全なデータ処理を行うためのソリューションを設計しています。データセキュリティとコンプライアンスのコンテキストにおける顧客管理の暗号鍵(CMEK)の役割は何ですか?
1. 
2. 
3. 暗号化レイヤを追加
4. 
<details><div>
    答え：
説明
Google Cloud の顧客管理の暗号鍵(CMEK)は、保存データの暗号化レイヤを追加します。これにより、お客様は独自の暗号化キーを管理し、保存されたデータの制御とセキュリティを強化できます。詳細については、ドキュメントを参照してください: [顧客管理の暗号化キー](https://cloud.google.com/kms/docs/overview)
</div></details>

### Q. 質問48: 未回答
Cloud Dataflow パイプラインでは、イベント時間データの処理におけるウォーターマークの役割と、正確なウィンドウ処理の確保にどのように貢献しますか?
1. 
2. イベント時間の進行状況を追跡
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataflow のウォーターマークは、イベント時間の進行状況を追跡することでイベント時間データの処理に重要な役割を果たし、正確なウィンドウ処理の確保に貢献し、すべての関連データがいつ処理されたかをシステムが理解できるようにします。[詳細](https://cloud.google.com/dataflow/docs/concepts/event-time)
</div></details>

### Q. 質問49: 未回答
データ処理システムにおける Cloud Functions の主な目的は何ですか?
1. ベントドリブン関数にサーバーレス コンピューティングを提供
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Functions は、データ処理システムのイベントドリブン関数にサーバーレス コンピューティングを提供します。これにより、イベントに応答してコードを実行し、需要に基づいて自動的にスケーリングできます。詳細: [Cloud Functions の概要](https://cloud.google.com/functions/docs)
</div></details>

### Q. 質問50: 未回答
機械学習モデルの提供に AI Platform Prediction を使用しており、予測インスタンスの数を制御して費用を最適化したい。モデルバージョンのデプロイ中に '--initial-replica-count' フラグを設定する目的は何ですか?
1. レプリカ(インスタンス)の初期数を定義
2. 
3. 
4. 
<details><div>
    答え：
説明
AI Platform Prediction の「--initial-replica-count」フラグは、モデル バージョンをデプロイする際にレプリカ(インスタンス)の初期数を定義するために使用され、コストとリソースの管理に役立ちます。[AI Platform 予測の初期レプリカ数](https://cloud.google.com/ai-platform/prediction/docs/deploying-models#initial-replica-count)
</div></details>

### Q. 質問51: 未回答
データ処理システムにおけるアプリケーションのパフォーマンスをリアルタイムでモニタリングおよびロギングするために設計された Google Cloud サービスはどれですか?
1. 
2. 
3. 
4. Cloud Trace
<details><div>
    答え：
説明
Cloud Trace は、データ処理システムにおけるアプリケーションのパフォーマンスをリアルタイムでモニタリングし、ログを記録するために設計されています。これにより、要求をトレースし、アプリケーションの待機時間を把握できます。詳細: [Cloud Trace の概要](https://cloud.google.com/trace/docs)
</div></details>

### Q. 質問52: 未回答
Google Cloud Dataflow で安全なデータ処理を行うためのソリューションを設計しています。処理中に保存データの機密性と整合性を確保するために、どのようなセキュリティ機能を実装できますか?
1. 
2. Dataflow シャッフル暗号化
3. 
4. 
<details><div>
    答え：
説明
Google Cloud Dataflow では、Dataflow シャッフル暗号化を実装することで、処理中の保存データの機密性と整合性を確保できます。この機能は、シャッフル操作中にデータを暗号化し、データ処理パイプラインの全体的なセキュリティを強化します。詳細については、[データフローシャッフル暗号化](https://cloud.google.com/dataflow/docs/security)を参照してください。
</div></details>

### Q. 質問53: 未回答
Cloud Dataflow パイプラインでデータの信頼性を設計する場合、ストリーミング データのデータ要素を管理する上でのウィンドウの役割と、処理効率への影響は何ですか?
1. 
2. データ要素を時間ベースのウィンドウに整理して管理
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataflow のウィンドウ処理は、ストリーミング データ内のデータ要素を時間ベースのウィンドウに整理して管理し、管理可能な間隔内で並列処理できるようにすることで処理効率に影響を与えます。[詳細](https://cloud.google.com/dataflow/docs/concepts/windowing)
</div></details>

### Q. 質問54: 未回答
AI Platform Prediction に機械学習モデルをデプロイする場合、「--instance-type」フラグを設定する意味は何ですか?
1. 予測に使用するマシンタイプを定義
2. 
3. 
4. 
<details><div>
    答え：
説明
AI Platform Prediction で「--instance-type」フラグを設定すると、予測に使用するマシンタイプを定義し、各予測インスタンスに割り当てられるリソースを設定できます。[AI Platform 予測インスタンス タイプ](https://cloud.google.com/ai-platform/prediction/docs/deploying-models#instance-type)
</div></details>

### Q. 質問55: 未回答
BigQuery SQL クエリの PARTITION BY 句の目的は何ですか?
1. 
2. パーティション内でウィンドウ関数を実行
3. 
4. 
<details><div>
    答え：
説明
BigQuery の PARTITION BY 句は、結果セットのパーティション内でウィンドウ関数を実行するために使用されます。
</div></details>

### Q. 質問56: 未回答
Google Cloud Pub/Sub のデータを保護する責任はお客様にあります。メッセージの公開時と使用時に転送中のデータを暗号化するために、どのようなセキュリティ機能を有効にできますか?
1. 
2. TLS/SSL 暗号化
3. 
4. 
<details><div>
    答え：
説明
Google Cloud Pub/Sub でメッセージを公開および消費するときに転送中のデータを暗号化するには、TLS/SSL 暗号化を有効にする必要があります。これにより、パブリッシャとサブスクライバーの間でメッセージが安全に送信され、不正アクセスや改ざんが防止されます。詳細については、[TLS/SSLによる通信の保護](https://cloud.google.com/pubsub/docs/secure-communication)を参照してください。
</div></details>

### Q. 質問57: 未回答
クラウドベースのデータ処理システムにおいて、機密データのセキュリティを確保するために BigQuery データセットへのアクセス制御を管理するには、どのような方法が推奨されますか?
1. 
2. きめ細かなアクセス制御
3. 
4. 
<details><div>
    答え：
説明
BigQuery データセットにきめ細かなアクセス制御を実装することは、機密データのセキュリティを確保し、データ処理の制御とセキュリティを提供するためのアクセス管理に推奨されるアプローチです。[詳細](https://cloud.google.com/bigquery/docs/table-access-controls)
</div></details>

### Q. 質問58: 未回答
Google Cloud Storage のアクセス制御を設定しています。データのセキュリティとコンプライアンスのコンテキストにおけるアクセス制御リスト(ACL)の目的は何ですか?
1. 
2. オブジェクトごとのアクセス制御を定義
3. 
4. 
<details><div>
    答え：
説明
Google Cloud Storage のアクセス制御リスト(ACL)は、オブジェクトごとのアクセス制御を定義するために使用されます。これにより、バケット内の個々のオブジェクトにアクセスできるユーザーまたはグループを指定し、オブジェクトレベルの権限をきめ細かく制御できます。詳細については、[アクセス制御リストの使用](https://cloud.google.com/storage/docs/access-control/lists)を参照してください。
</div></details>

### Q. 質問59: 未回答
新しいモデル バージョンが AI Platform Prediction にデプロイされるたびに Cloud Functions の関数をトリガーするプロセスを自動化したい。このイベントドリブンなワークフローを自動化するために、パイプラインに統合できる Google Cloud サービスはどれですか?
1. 
2. 
3. Cloud Pub/Sub 
4. 
<details><div>
    答え：
説明
Cloud Pub/Sub をパイプラインに統合して、新しいモデル バージョンが AI Platform Prediction にデプロイされるたびに Cloud Functions の関数をトリガーするイベントドリブン ワークフローを設定できます。[クラウド Pub/Sub](https://cloud.google.com/pubsub)
</div></details>

### Q. 質問60: 未回答
低レイテンシのアクセスでストリーミング データのリアルタイム分析が必要なシナリオでは、ストリーミング データをリアルタイムで取り込んで処理するのに適した Google Cloud サービスはどれですか?
1. 
2. 
3. Cloud Dataflow 
4. 
<details><div>
    答え：
説明
Cloud Dataflow は、ストリーミング データをリアルタイムで取り込んで処理するのに適しており、大規模なデータセットのリアルタイム分析のためのフルマネージドのサーバーレス ソリューションを提供します。[詳細](https://cloud.google.com/dataflow/docs)
</div></details>

### Q. 質問61: 未回答
Cloud Dataprep を使用したクラウドベースのデータ処理システムにおいて、データのプロファイリングの目的は何か、データの品質保証にどのように貢献するのか。
1. データの分布と品質を分析
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataprep でのデータのプロファイリングでは、データの分布と品質を分析し、データセット内の異常、パターン、潜在的な問題を特定することで、データの品質保証に貢献します。[詳細](https://cloud.google.com/dataprep/docs/html/ProfilePage_57341635)
</div></details>

### Q. 質問62: 未回答
データ処理システムにおいて、クラウドデータ損失防止(DLP)の目的は何ですか?
1. 機密データの漏洩を防ぐ
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Data Loss Prevention(DLP)は、データ処理環境での機密データの漏洩を防ぐために使用されます。機密情報を特定して保護し、プライバシー規制へのコンプライアンスを確保するのに役立ちます。詳細: [Cloud DLP の概要](https://cloud.google.com/dlp/docs)
</div></details>

### Q. 質問63: 未回答
データ処理タスクにカスタムの依存関係とランタイム環境が必要なシナリオでは、コンテナ化されたアプリケーションの構築とデプロイに適した Google Cloud サービスはどれですか?
1. 
2. 
3. 
4. Cloud Run 
<details><div>
    答え：
説明
Cloud Run は、カスタム依存関係とランタイム環境を使用してコンテナ化されたアプリケーションを構築およびデプロイするのに適しており、データ処理タスクに柔軟性を提供します。[詳細](https://cloud.google.com/run/docs)
</div></details>

### Q. 質問64: 未回答
ストリーミング データのリアルタイムの取り込みと処理を必要とするデータ処理パイプラインを構築しています。このシナリオでスケーラブルでフルマネージドのソリューションを提供する Google Cloud サービスはどれですか?
1. Cloud Dataflow 
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataflow は、ストリーミング データをリアルタイムで取り込んで処理するように設計されています。これは、ストリーム処理とバッチ処理の両方に対応するスケーラブルで完全に管理されたソリューションを提供します。詳細: [Cloud Dataflow の概要](https://cloud.google.com/dataflow/docs)
</div></details>

### Q. 質問65: 未回答
Cloud Dataprep を使用したクラウドベースのデータ処理システムでは、結合レシピの目的と、複数のソースからのデータの結合にどのように貢献しますか?
1. 
2. 指定された条件に基づいて複数のソースからのデータを結合
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataprep の結合レシピは、指定された条件に基づいて複数のソースからのデータを結合し、データ統合を容易にし、多様なデータセットにわたる包括的な分析を可能にします。[詳細](https://cloud.google.com/dataprep/docs/html/Join-Recipe_57341424)
</div></details>

### Q. 質問66: 未回答
AI Platform Prediction で機械学習モデルのモニタリングを設定しています。デプロイされたモデル バージョンの監視を構成する場合の '--target-field' フラグの目的は何ですか?
1. データセット内のターゲット特徴量を指定
2. 
3. 
4. 
<details><div>
    答え：
説明
AI Platform Prediction の「--target-field」フラグは、モデル監視の設定時にデータセット内のターゲット特徴量を指定するために使用されます。これは、特定のターゲット変数に対するモデルのパフォーマンスを監視するのに役立ちます。[AI Platform 予測対象分野](https://cloud.google.com/ai-platform/prediction/docs/monitoring)
</div></details>

### Q. 質問67: 未回答
Cloud Storage で費用最適化を設計する場合、失われた場合に再生成できるデータを扱う際のストレージ費用を管理するためのベスト プラクティスは何ですか?
1. 
2. Nearline Storage クラスを使用
3. 
4. 
<details><div>
    答え：
説明
Cloud Storage で Nearline Storage クラスを使用することは、失われた場合に再生成できるデータを処理する際のストレージ費用を管理するためのベスト プラクティスであり、費用効率とアクセシビリティのバランスが取れています。[詳細](https://cloud.google.com/storage/docs/storage-classes#nearline)
</div></details>

### Q. 質問68: 未回答
SQL クエリを使用したリアルタイムのデータ変換とクレンジングを含むデータ処理パイプラインを設計する必要があります。このシナリオに最適な Google Cloud サービスはどれですか?
1. BigQuery 
2. 
3. 
4. 
<details><div>
    答え：
説明
BigQuery は、サーバーレスで拡張性の高いデータ ウェアハウスであり、データ処理パイプラインでリアルタイムのデータ変換とクレンジングのための SQL クエリを実行できます。アドホックなクエリと分析に適しています。詳細: [BigQuery SQL リファレンス](https://cloud.google.com/bigquery/docs/reference/standard-sql)
</div></details>

### Q. 質問69: 未回答
AI Platform Prediction でモデル監視を実装している。デプロイされたモデル バージョンの監視を構成するときに '--sampling-rate' フラグを使用する目的は何ですか?
1. 
2. サンプリングされた予測リクエストのレートを制御
3. 
4. 
<details><div>
    答え：
説明
AI Platform Prediction の「--sampling-rate」フラグは、モデル監視の設定時にサンプリングされた予測リクエストのレートを制御するために使用され、分析のために予測のサブセットをモニタリングできます。[AI Platform 予測モデル監視サンプリング](https://cloud.google.com/ai-platform/prediction/docs/monitoring)
</div></details>

### Q. 質問70: 未回答
データポータルで折れ線グラフを作成して、ウェブサイトのトラフィックの推移を示すとします。このグラフのディメンションと指標として何を使用する必要がありますか?
1. 
2. 
3. ディメンションとして日付を使用し、指標としてトラフィックを使用
4. 
<details><div>
    答え：
説明
時間の経過に伴うウェブサイトトラフィックの傾向を示す折れ線グラフを作成するには、ディメンションとして日付を使用し、指標としてトラフィックを使用します。
</div></details>

### Q. 質問71: 未回答
クラウドベースのデータ処理システムでデータ セキュリティを設計する場合、機密データを含む Cloud Bigtable テーブルへのアクセス制御を管理するには、どのような方法が推奨されますか?
1. 
2. きめ細かなアクセス制御を使用
3. 
4. 
<details><div>
    答え：
説明
機密データを含む Cloud Bigtable テーブルへのアクセス制御を管理するには、きめ細かなアクセス制御を使用して、安全で制御されたデータ処理を行うことをおすすめします。[詳細](https://cloud.google.com/bigtable/docs/access-control)
</div></details>

### Q. 質問72: 未回答
Cloud Composer を使用して複数のタスクをオーケストレーションする機械学習ワークフローを設計しています。Apache Airflow と Cloud Composer の「ShortCircuitOperator」の目的は何ですか?
1. 
2. 
3. 条件に基づいてタスクをスキップ
4. 
<details><div>
    答え：
説明
Apache Airflow と Cloud Composer の「ShortCircuitOperator」は、条件に基づいてタスクをスキップするために使用され、ワークフローの実行フローを動的に制御できます。[Cloud Composer ShortCircuitOperator] (クラウド コンポーザー ショートサーキット オペレーター)(https://cloud.google.com/composer/docs/how-to/using/operators#shortcircuitoperator)
</div></details>

### Q. 質問73: 未回答
クラウドベースのデータ処理システムで費用最適化を設計する場合、Cloud Storage のストレージの費用を管理するための推奨される戦略は何ですか?
1. 
2. 
3. 
4. Nearline Storage クラスを使用
<details><div>
    答え：
説明
Cloud Storage でストレージ費用を管理するための推奨される戦略は、アクセス頻度の低いデータには Nearline Storage クラスを使用し、コスト効率とアクセシビリティのバランスを取ることです。[詳細](https://cloud.google.com/storage/docs/storage-classes#nearline)
</div></details>

### Q. 質問74: 未回答
Cloud Dataflow パイプラインでは、Dataflow Shuffle サービスの役割と、データ処理の効率をどのように向上させるのでしょうか?
1. 
2. 
3. 
4. 並列処理を容易
<details><div>
    答え：
説明
Cloud Dataflow の Dataflow Shuffle サービスは、並列処理を容易にし、ワーカー ノード間での効率的なシャッフルとデータの再分散を可能にすることで、データ処理の効率を高めます。[詳細](https://cloud.google.com/dataflow/docs/concepts/shuffle)
</div></details>

### Q. 質問75: 未回答
Google Cloud Dataprep で安全なデータ処理を行うためのソリューションを設計しています。データ準備プロセス中に機密データを保護するために、どのようなセキュリティ機能を活用できますか?
1. 
2. 
3. 列レベルのマスキング
4. データリネージ トラッキング
<details><div>
    答え：
説明
Google Cloud Dataprep では、列レベルのマスキングやデータリネージ トラッキングなどのセキュリティ機能を活用して、データ準備プロセス中に機密データを保護できます。列レベルのマスキングは特定のデータへのアクセスを制御するのに役立ち、データ系列の追跡は、データが処理パイプラインをどのように移動するかを理解するのに役立ちます。詳細については、[Dataprep のセキュリティ機能](https://cloud.google.com/dataprep/docs/html/Security/Security-Features)を参照してください。
</div></details>

## 5
### Q. 質問1: 未回答
データ処理パイプラインにおいて、データのセキュリティとコンプライアンスを確保する上で、Cloud Data Loss Prevention(DLP)はどのような役割を果たしますか?
1. 
2. 機密データを匿名化して編集
3. 
4. 
<details><div>
    答え：
説明
Cloud DLP は、データ処理パイプラインで機密データを匿名化して編集することで、データのセキュリティとコンプライアンスを確保する上で重要な役割を果たします。[詳細](https://cloud.google.com/dlp/docs)
</div></details>

### Q. 質問2: 未回答
Google Cloud Pub/Sub を含むデータ処理パイプラインを設計しています。プロデューサとサブスクライバ間の安全な通信を確保するために、どのようなセキュリティ機能を実装できますか?
1. 
2. 
3. TLS/SSL 暗号化
4. 
<details><div>
    答え：
説明
TLS/SSL 暗号化の実装は、Google Cloud Pub/Sub でプロデューサーとサブスクライバー間の安全な通信を確保するために不可欠です。転送中のデータを暗号化し、盗聴や改ざんの可能性から保護します。詳細については、[TLS/SSLによる通信の保護](https://cloud.google.com/pubsub/docs/secure-communication)を参照してください。
</div></details>

### Q. 質問3: 未回答
あなたは、ストリーミング データのリアルタイムの異常検出を必要とするデータ処理システムを設計する必要があります。どのサービスを使うべきですか?
1. 
2. 
3. Cloud Dataflow 
4. 
<details><div>
    答え：
説明
Cloud Dataflow は、ストリーミング データのリアルタイムの異常検出に適しています。ストリーム処理と分析のためのフルマネージドのサーバーレスアプローチを提供するため、複雑なデータ処理タスクに最適です。詳細: [Cloud Dataflow の概要](https://cloud.google.com/dataflow/docs)
</div></details>

### Q. 質問4: 未回答
複数リージョンのレプリケーションを使用して、可用性が高く、グローバルに分散されたデータベースを設計する必要があります。どの Google Cloud サービスを選ぶべきですか?
1. 
2. 
3. 
4. Cloud Spanner 
<details><div>
    答え：
説明
Cloud Spanner は、グローバルに分散され、水平方向にスケーラブルで、整合性の強いデータベースであり、マルチリージョン レプリケーションをサポートします。これは、高可用性とグローバル展開用に設計されています。詳細: [Cloud Spanner の機能](https://cloud.google.com/spanner/docs/features)
</div></details>

### Q. 質問5: 未回答
AI Platform Prediction でモデルのバージョニングを実装している。新しいモデル バージョンを作成するときにラベルを使用する利点は何ですか?
1. 
2. 
3. 
4. バージョンにメタデータを追加
<details><div>
    答え：
説明
AI Platform Prediction で新しいモデル バージョンを作成する際にラベルを使用すると、バージョンにメタデータを追加できるため、さまざまなモデル バージョンの整理と追跡が容易になります。[AI Platform 予測モデルのバージョン ラベル](https://cloud.google.com/ai-platform/prediction/docs/model-versions#labels)
</div></details>

### Q. 質問6: 未回答
Google Cloud Storage のアクセス制御を設定しています。バケットACL(アクセス制御リスト)の機能は何ですか?
1. バケットレベルで権限を設定
2. 
3. バケットにアクセスできるユーザーとそのアクセスレベルを制御
4. 
<details><div>
    答え：
説明
Google Cloud Storage のバケット ACL を使用すると、バケットレベルで権限を設定し、バケットにアクセスできるユーザーとそのアクセスレベルを制御できます。また、オブジェクトごとのアクセス制御を定義して、バケット内の個々のオブジェクトをきめ細かく制御することもできます。詳細はドキュメントを参照してください: [バケットACLの使用](https://cloud.google.com/storage/docs/access-control/using-acls)
</div></details>

### Q. 質問7: 未回答
BigQuery の機密データを保護するのはお客様の責任です。データセットへのアクセスを監査および監視するには、どのような方法を使用できますか?
1. Cloud Audit Logs
2. 
3. 
4. 
<details><div>
    答え：
説明
BigQuery のデータセットへのアクセスを監査、モニタリングするには、Cloud Audit Logs を使用します。これらのログは、ユーザーが実行したアクションの記録を提供し、誰がデータにアクセスし、どのような操作が実行されたかを追跡できます。詳細については、[BigQuery へのアクセスの監査](https://cloud.google.com/bigquery/docs/reference/auditlogs)を参照してください。
</div></details>

### Q. 質問8: 未回答
AI Platform Training を使用して、カスタム依存関係を持つ機械学習モデルのトレーニングを行っています。トレーニングジョブを送信する際の「--master-accelerator-count」フラグの目的は何ですか?
1. 
2. 
3. マスターノードのアクセラレータ(GPU)の数を指定
4. 
<details><div>
    答え：
説明
AI Platform Training の「--master-accelerator-count」フラグは、カスタム依存関係を含むトレーニング ジョブを送信するときに、マスターノードのアクセラレータ(GPU)の数を指定するために使用されます。[AI Platform Training Master Accelerator Count] (AI プラットフォーム トレーニング マスター アクセラレーター数)(https://cloud.google.com/ai-platform/training/docs/training-jobs#master-accelerator-count)
</div></details>

### Q. 質問9: 未回答
データ処理パイプラインにおいて、Cloud Scheduler の目的は何ですか?
1. 
2. Cloud Functions をトリガー
3. 
4. 
<details><div>
    答え：
説明
Cloud Scheduler は、指定した間隔で Cloud Functions をトリガーできるフルマネージドの cron ジョブ スケジューラです。これは、データ処理システムでのタスクの自動化とスケジューリングに使用されます。詳細: [Cloud Scheduler の概要](https://cloud.google.com/scheduler/docs)
</div></details>

### Q. 質問10: 未回答
AI Platform Prediction でのモデルの説明可能性のコンテキストでは、デプロイされたモデルの特徴量の重要度値を生成できる機能はどれですか? 
1. 予測説明ログ
2. 
3. 
4. 
<details><div>
    答え：
説明
AI Platform Prediction のログ記録では、デプロイされたモデルの特徴量の重要度値を生成でき、さまざまな特徴が予測に与える影響に関する分析情報を得ることができます。[AI Platform 予測説明ログ](https://cloud.google.com/ai-platform/prediction/docs/ai-explanations/logging)
</div></details>

### Q. 質問11: 未回答
Kubeflow Pipelinesを使用して機械学習ワークフローを設計する場合、「PersistentVolumeClaim」リソースの目的は何ですか?
1. 
2. 永続ストレージの割り当て
3. 
4. 
<details><div>
    答え：
説明
Kubeflow Pipelines では、永続ストレージの割り当てに "PersistentVolumeClaim" リソースが使用され、パイプラインの実行間でデータを管理および格納できます。[Kubeflow パイプライン PersistentVolumeClaim](https://www.kubeflow.org/docs/pipelines/sdk/persistent-volume-claims/)
</div></details>

### Q. 質問12: 未回答
BigQuery に複数のテーブルを含むデータセットがある。2つのテーブル間で結合操作を実行するための正しいSQL句は何ですか?
1. JOIN句
2. 
3. 
4. 
<details><div>
    答え：
説明
JOIN句は、SQLで使用され、2つ以上のテーブル間の関連する列に基づいて、2つ以上のテーブルの行を結合します。
</div></details>

### Q. 質問13: 未回答
大規模なデータセットでモデルをトレーニングする機械学習ワークフローを実装しています。AI Platform Training のどの機能で、複数のノードにトレーニングを分散してモデルのトレーニングを高速化できますか?
1. 
2. 
3. 
4. 分散トレーニング
<details><div>
    答え：
説明
分散トレーニングは AI Platform Training の機能で、複数のノードにトレーニングを分散して、大規模なデータセットでのモデル トレーニングを高速化できます。[AI Platform Training 分散トレーニング](https://cloud.google.com/ai-platform/training/docs/training-jobs)
</div></details>

### Q. 質問14: 未回答
カスタム ランタイムを使用して AI Platform Prediction に機械学習モデルをデプロイする場合。モデル・デプロイメントにカスタム・ランタイムでDockerコンテナを使用できる機能はどれですか。
1. カスタム コンテナ
2. 
3. 
4. 
<details><div>
    答え：
説明
カスタム ランタイムを使用した機械学習モデルの AI Platform Prediction へのデプロイは、カスタム コンテナ機能を使用して実現され、カスタム ランタイムで Docker コンテナを使用できます。[AI Platform Prediction カスタム コンテナ](https://cloud.google.com/ai-platform/prediction/docs/use-custom-container)
</div></details>

### Q. 質問15: 未回答
AI Platform Prediction のコンテキストでは、低コストのマシンタイプのモデル バージョンを使用して、予測の提供コストを最適化します。このコスト最適化を実現するための推奨されるアプローチは何ですか?
1. 
2. 目的のマシンタイプで新しいモデル バージョンを作成
3. 
4. 
<details><div>
    答え：
説明
AI Platform Prediction で予測を提供するコストを最適化するには、目的のマシンタイプで新しいモデル バージョンを作成することをおすすめします。[AIプラットフォーム予測コスト最適化](https://cloud.google.com/ai-platform/prediction/docs/cost-optimization)
</div></details>

### Q. 質問16: 未回答
機械学習ワークフローのストリーミング データ処理ステップに Cloud Dataflow を使用している。ストリーミング データ処理でウィンドウ処理のために Dataflow パイプラインを実行する場合の「--window-size」フラグの目的は何ですか?
1. 
2. 
3. 
4. 時間ベースのデータ集計を管理
<details><div>
    答え：
説明
Cloud Dataflow の「--window-size」フラグは、ストリーミング データ処理で時間ベースのデータ集計を管理するために使用され、時間ベースのウィンドウのサイズを定義できます。[Cloud Dataflow ウィンドウサイズ](https://cloud.google.com/dataflow/docs/guides/windowing#setting-the-window-size)
</div></details>

### Q. 質問17: 未回答
機械学習のデプロイにモデル監視を実装する必要があります。モデルの予測、公平性、説明可能性をモニタリングする機能を提供している Google Cloud サービスはどれですか?
1. 
2. 
3. AI Platform Model Monitoring
4. 
<details><div>
    答え：
説明
Google Cloud の AI Platform Model Monitoring には、モデルの予測、公平性、説明可能性をモニタリングする機能が用意されており、デプロイされたモデルに関する分析情報を得ることができます。[AI Platform モデル モニタリング](https://cloud.google.com/ai-platform/prediction/docs/monitoring)
</div></details>

### Q. 質問18: 未回答
データ処理システムにおけるクラウドIAM(Identity and Access Management)の目的は何ですか?
1. 
2. 
3. きめ細かなアクセス制御
4. 
<details><div>
    答え：
説明
Cloud IAM は、データ処理システムにおけるきめ細かなアクセス制御と権限の管理に使用されます。これにより、リソースにアクセスできるユーザーと、そのユーザーが実行できるアクションを制御できます。詳細: [Cloud IAM の概要](https://cloud.google.com/iam/docs)
</div></details>

### Q. 質問19: 未回答
データポータルのレポートを関係者と共有したい。データポータルで共有できるオプションにはどのようなものがありますか?
1. リンクの共有、
2. PDF としてのエクスポート、
3. メール配信のスケジュール設定、
4. ウェブサイトへの埋め込み
<details><div>
    答え：
説明
データポータルには、リンクの共有、PDF としてのエクスポート、メール配信のスケジュール設定、ウェブサイトへの埋め込みなど、レポートを共有するための複数のオプションが用意されています。
</div></details>

### Q. 質問20: 未回答
リアルタイム予測のための機械学習モデルの統合を含むデータ処理パイプラインを実装しています。このシナリオに最適な Google Cloud サービスはどれですか?
1. 
2. 
3. 
4. Cloud AI Platform 
<details><div>
    答え：
説明
Cloud AI Platform は、機械学習モデルをデプロイして提供するために設計されているため、機械学習モデルをデータ処理パイプラインに統合するのに適しています。詳細: [Cloud AI Platform の概要](https://cloud.google.com/ai-platform/docs)
</div></details>

### Q. 質問21: 未回答
複数の Google Cloud サービスを含むデータ処理パイプラインを設計しています。パイプライン内のサービス間を移動するデータの整合性を確保するにはどうすればよいでしょうか。
1. デジタル署名の適用
2. 
3. 
4. チェックサムの実装
<details><div>
    答え：
説明
データ処理パイプラインでデータの整合性を確保するには、チェックサムの実装とデジタル署名の適用が必要です。チェックサムは転送中のデータの整合性を検証し、デジタル署名はデータの真正性と出所を検証する方法を提供します。詳細については、[Data Integrity](https://cloud.google.com/security/best-practices-for-operating-in-the-cloud#data-integrity)を参照してください。
</div></details>

### Q. 質問22: 未回答
データ処理パイプラインにおいて、Cloud Storage Transfer Appliance の目的は何ですか?
1. 
2. オンプレミスの場所から Cloud Storage に大量のデータを安全に転送
3. 
4. 
<details><div>
    答え：
説明
Cloud Storage Transfer Appliance は、オンプレミスの場所から Cloud Storage に大量のデータを安全に転送できるように設計されています。効率的なデータ移行のための物理デバイスを提供します。追加情報: [Transfer Appliance の概要](https://cloud.google.com/storage-transfer-appliance/docs)
</div></details>

### Q. 質問23: 未回答
Kubeflow Pipelinesを使用して機械学習ワークフローを設計する場合、MLメタデータのコンテキストにおけるアーティファクトの目的は何ですか?
1. データセットのバージョンに関するメタデータをキャプチャ
2. 
3. 
4. 
<details><div>
    答え：
説明
Kubeflow Pipelines では、ML メタデータのコンテキストのアーティファクトを使用して、データセットのバージョンに関するメタデータをキャプチャし、データリネージを追跡および管理できるようにします。[Kubeflow パイプラインと ML メタデータ](https://www.kubeflow.org/docs/pipelines/sdk/component-sdk/sdk-overview/)
</div></details>

### Q. 質問24: 未回答
データ処理システムでコスト最適化を設計する場合、Google Cloud Compute Engine インスタンスで適切なマシンタイプを選択する際の重要な考慮事項は何ですか?
1. 
2. 
3. 仮想 CPU の数
4. 
<details><div>
    答え：
説明
適切なマシン・タイプを選択するには、データ処理システムのパフォーマンス要件を満たす仮想 CPU の数を考慮する必要があります。[詳細](https://cloud.google.com/compute/docs/machine-types)
</div></details>

### Q. 質問25: 未回答
Cloud Dataprep のデータ処理ジョブで保守性を考慮して設計する場合、ワークフローにおけるデータ品質チェックの役割は何ですか?
1. データの整合性を検証
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataprep のデータ処理ジョブにおけるデータ品質チェックは、データの整合性を検証する上で重要な役割を果たし、処理されたデータの正確性を確保することで保守性に貢献します。[詳細](https://cloud.google.com/dataprep/docs/html/DataQualityPage_57338842)
</div></details>

### Q. 質問26: 未回答
AI Platform Prediction を使用して機械学習モデルをデプロイしている。モデルの自動スケーリングを構成するときに '--max-replicas' フラグを設定する目的は何ですか?
1. 
2. レプリカ(インスタンス)の最大数を指定
3. 
4. 
<details><div>
    答え：
説明
AI Platform Prediction の「--max-replicas」フラグは、予測サービスでレプリカ(インスタンス)の最大数を指定して自動スケーリングを構成するために使用されます。[AI Platform 予測の自動スケーリング](https://cloud.google.com/ai-platform/prediction/docs/autoscaling)
</div></details>

### Q. 質問27: 未回答
Cloud Storage バケットを使用する際に、安全でコンプライアンスに準拠したデータ処理システムを設計するための重要な考慮事項は何ですか?
1. 
2. 
3. 
4. きめ細かなアクセス制御を実装
<details><div>
    答え：
説明
Cloud Storage バケットにきめ細かなアクセス制御を実装することは、安全でコンプライアンスに準拠したデータ処理システムを設計するための重要な考慮事項であり、データへのアクセスを制御して安全に保ちます。[詳細](https://cloud.google.com/storage/docs/access-control/iam)
</div></details>

### Q. 質問28: 未回答
データポータルで計算フィールドを作成して、商品の利益率を表す必要があります。このシナリオでは、どのような種類の計算を使用する必要がありますか?
1. 
2. 
3. 百分率
4. 
<details><div>
    答え：
説明
利益率を表すには、データポータルの [割合] 計算を使用して、収益と費用に基づいて利益の割合を計算します。
</div></details>

### Q. 質問29: 未回答
データのプライバシーとコンプライアンスが重要なシナリオでは、Cloud Storage 内の機密データを保護するためにどのような暗号鍵管理ソリューションが推奨されますか?
1. Google Cloud Key Management Service
2. 
3. 
4. 
<details><div>
    答え：
説明
Google Cloud Key Management Service(KMS)は、Cloud Storage での安全な暗号鍵管理に推奨され、データのプライバシーとコンプライアンスを確保します。[詳細](https://cloud.google.com/kms/docs)
</div></details>

### Q. 質問30: 未回答
お客様は、Cloud Spanner に保存されているデータの保護を担当しています。Cloud Spanner で保存されているデータを保護するには、どのような暗号化オプションを使用できますか?
1. 
2. 
3. サーバーサイド暗号化
4. 
<details><div>
    答え：
説明
Cloud Spanner で保存されているデータを保護するには、サーバーサイド暗号化を使用します。これにより、Cloud Spanner に保存されたデータが暗号化され、不正アクセスを防ぐためのセキュリティ レイヤが追加されます。詳細については、ドキュメントを参照してください: [保存時の暗号化](https://cloud.google.com/spanner/docs/encryption)
</div></details>

### Q. 質問31: 未回答
AI Platform Prediction でのモデル デプロイのコンテキストで、新しいモデル バージョンをデプロイするときに「--traffic-split」フラグを使用する目的は何ですか?
1. 
2. 
3. 数のモデル バージョン間で予測リクエストのバランス
4. 
<details><div>
    答え：
説明
AI Platform Prediction の「--traffic-split」フラグは、複数のモデル バージョン間で予測リクエストのバランスを取るために使用され、パフォーマンスを監視しながら新しいバージョンを段階的にロールアウトできます。[AI Platform 予測トラフィック分割](https://cloud.google.com/ai-platform/prediction/docs/deploying-models)
</div></details>

### Q. 質問32: 未回答
Cloud Dataprep データ処理ジョブのスケーラビリティを重視して設計する場合、入力データ量の増加に対応するためにどのような戦略が推奨されますか?
1. 
2. 
3. 
4. 水平スケーリング
<details><div>
    答え：
説明
水平スケーリングは、Cloud Dataprep のデータ処理ジョブで増加した入力データ量を処理するために、リソースを追加することをおすすめします。[詳細](https://cloud.google.com/dataprep/docs/html/Run-Job-Page_57124624)
</div></details>

### Q. 質問33: 未回答
モデルのトレーニングに AI Platform Training を使用しています。トレーニングジョブを送信するときの '--scale-tier' フラグの目的は何ですか?
1. 
2. 
3. トレーニング用のコンピューティング リソースをスケーリング
4. 
<details><div>
    答え：
説明
AI Platform Training の「--scale-tier」フラグは、トレーニング用のコンピューティング リソースをスケーリングするために使用され、適切なマシンタイプとインスタンス数を選択できます。[AI Platform トレーニング スケーリング](https://cloud.google.com/ai-platform/training/docs/training-jobs)
</div></details>

### Q. 質問34: 未回答
データ プライバシー規制に準拠するために、BigQuery でデータ マスキング戦略を実装している。クエリ結果の特定の列を編集するには、どのような手法を使用できますか?
1. 動的データ マスキング
2. 
3. 
4. 
<details><div>
    答え：
説明
BigQuery の動的データ マスキングを使用すると、クエリ結果の特定の列を編集できます。マスキングルールを動的に適用することで機密情報を保護し、許可されたユーザーのみが完全なデータを表示でき、他のユーザーには編集された値が表示されるようにします。詳細については、[動的データマスキング](https://cloud.google.com/bigquery/docs/dynamic-data-masking)を参照してください。
</div></details>

### Q. 質問35: 未回答
データベース管理者を必要とせずに SQL クエリを使用して大規模なデータセットを分析できる Google Cloud サービスはどれですか?
1. 
2. BigQuery 
3. 
4. 
<details><div>
    答え：
説明
BigQuery は、サーバーレスで拡張性の高いデータ ウェアハウスであり、データベース管理者を必要とせずに SQL クエリを使用して大規模なデータセットを分析できます。アドホックなクエリと分析に適しています。詳細: [BigQuery の機能](https://cloud.google.com/bigquery/docs)
</div></details>

### Q. 質問36: 未回答
Cloud Composer を使用して機械学習ワークフローを調整している。クラウドコンポーザーのコンテキストにおける「エアフロー.cfg」ファイルの目的は何ですか?
1. 
2. 
3. 
4. Apache Airflow 設定の構成
<details><div>
    答え：
説明
Cloud Composer の「airflow.cfg」ファイルは、Apache Airflow 設定の構成に使用され、オーケストレーション環境の動作をカスタマイズできます。[Cloud Composer の設定](https://cloud.google.com/composer/docs/concepts/configuring-airflow)
</div></details>

### Q. 質問37: 未回答
低レイテンシが求められる頻繁にアクセスされるデータに適した Cloud Storage クラスはどれですか?
1. Standard ストレージ クラス
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Storage の Standard ストレージ クラスは、低レイテンシ要件で頻繁にアクセスされるデータ向けに設計されています。Cloud Storage に保存されているデータへの高性能なアクセスを提供します。追加情報: [Cloud Storage Classes](https://cloud.google.com/storage/docs/storage-classes)
</div></details>

### Q. 質問38: 未回答
Cloud Bigtable で信頼性を重視して設計する場合、ノード間でデータを分散する際の自動シャーディングにはどのような意味があるのでしょうか。
1. 
2. 
3. 
4. バランスの取れたデータ分散
<details><div>
    答え：
説明
Cloud Bigtable の自動シャーディングは、ノード間でバランスの取れたデータ分散を保証し、ホットスポットの防止とパフォーマンスの最適化によって信頼性を高めます。[詳細](https://cloud.google.com/bigtable/docs/automatic-sharding)
</div></details>

### Q. 質問39: 未回答
Google Cloud サービスのログ記録とモニタリングを設定しています。Cloud Monitoring ダッシュボードの目的は何ですか?
1. 
2. 
3. 
4. 指標とログを視覚化して分析
<details><div>
    答え：
説明
Google Cloud の Cloud Monitoring ダッシュボードは、指標とログを視覚化して分析する目的を果たします。パフォーマンス データを一元的に表示し、リソースの正常性とパフォーマンスを監視するのに役立ちます。詳細については、ドキュメント「[Cloud Monitoring の概要](https://cloud.google.com/monitoring/docs)を参照してください。
</div></details>

### Q. 質問40: 未回答
データ処理環境における Cloud Identity and Access Management(IAM)条件の目的は何ですか?
1. 
2. セキュリティレイヤの追加
3. 
4. 
<details><div>
    答え：
説明
Cloud IAM 条件は、データ処理環境における IP アドレスやデバイスのステータスなどの条件に基づいてコンテキスト アクセス ポリシーを適用できるようにすることで、セキュリティをさらに強化します。追加情報: [IAM 条件の概要](https://cloud.google.com/iam/docs/conditions-overview)
</div></details>

### Q. 質問41: 未回答
ほぼリアルタイムのデータ分析が重要なシナリオでは、低レイテンシが要求されるストリーム処理に適した Google Cloud サービスはどれですか?
1. 
2. 
3. Cloud Dataflow
4. 
<details><div>
    答え：
説明
Cloud Dataflow は、低レイテンシが求められるストリーム処理に適しており、ほぼリアルタイムのデータ分析を必要とするシナリオに最適です。[詳細](https://cloud.google.com/dataflow/docs)
</div></details>

### Q. 質問42: 未回答
ストレージの前にデータの変換とクレンジングを必要とするデータ処理パイプラインを構築しています。どのサービスを使うべきですか?
1. Cloud Dataprep
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataprep は、視覚的なデータ ラングリング、変換、クレンジングのためのフルマネージド サービスです。これは、データ処理パイプラインで分析および保存するデータを準備するために設計されています。詳細: [Cloud Dataprep の概要](https://cloud.google.com/dataprep/docs)
</div></details>

### Q. 質問43: 未回答
AI Platform Prediction で、カスタム予測ルーチンを使用してモデル バージョンをデプロイする場合の「--predict-instance-schema-uri」フラグの目的は何ですか?
1. 
2. 
3. 
4. 入力インスタンスのスキーマを定義
<details><div>
    答え：
説明
AI Platform Prediction で「--predict-instance-schema-uri」フラグを設定するのは、カスタム予測ルーチンを使用してモデル バージョンをデプロイするときに、入力インスタンスのスキーマを定義するためのものです。[AI Platform Prediction カスタム予測ルーチン スキーマ](https://cloud.google.com/ai-platform/prediction/docs/custom-prediction-routines#deploy)
</div></details>

### Q. 質問44: 未回答
データ処理環境でのデータカタログの作成と管理に適した Google Cloud サービスはどれですか?
1. 
2. Cloud Data Catalog
3. 
4. 
<details><div>
    答え：
説明
Cloud Data Catalog は、データ処理環境でデータカタログを作成、管理できる、フルマネージドでスケーラブルなメタデータ管理サービスです。これは、データ資産を検出して理解するのに役立ちます。詳細: [Cloud Data Catalog ドキュメント](https://cloud.google.com/data-catalog/docs)
</div></details>

### Q. 質問45: 未回答
Cloud Dataflow を使用したサーバーレス データ処理パイプラインで、ストリーミング データを処理する際にウィンドウを使用する目的は何ですか?
1. 
2. 時間ベースのウィンドウのサイズを決定
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataflow のストリーミング データ処理のウィンドウ処理は、時間ベースのウィンドウのサイズを決定し、ストリーミング データの効果的な処理と分析を可能にします。[詳細](https://cloud.google.com/dataflow/docs/concepts/event-time)
</div></details>

### Q. 質問46: 未回答
ストリーミング データのリアルタイム分析と視覚化を必要とするデータ処理パイプラインを構築しています。どの Google Cloud サービスを使用する必要がありますか?
1. BigQuery 
2. 
3. 
4. 
<details><div>
    答え：
説明
BigQuery は、ストリーミング データのリアルタイム分析とクエリをサポートするフルマネージドのサーバーレス データ ウェアハウスです。これにより、視覚化の目的で高速でインタラクティブなSQLクエリが可能になります。詳細: [BigQuery Real-time Analytics](https://cloud.google.com/bigquery/streaming-data-into-bigquery)
</div></details>

### Q. 質問47: 未回答
Google Cloud 環境では、Resource Manager の目的は何ですか?
1. 
2. クラウドリソースの整理と管理
3. 
4. 
<details><div>
    答え：
説明
Google Cloud Resource Managerは、クラウドリソースの整理と管理に使用されます。これにより、プロジェクトとリソースを階層的に構造化し、組織全体に一貫したポリシーと権限を簡単に適用できます。詳細については、「Resource Manager の概要」(https://cloud.google.com/resource-manager/docs/quickstart) を参照してください。
</div></details>

### Q. 質問48: 未回答
データ処理パイプラインで Cloud Composer を使用する目的は何ですか?
1. 
2. ワークフローのオーケストレーション
3. 
4. 
<details><div>
    答え：
説明
Cloud Composer は、データ処理パイプラインでのワークフローのオーケストレーションを容易にし、さまざまなタスクの調整とスケジューリングを可能にします。[詳細](https://cloud.google.com/composer/docs/concepts/overview)
</div></details>

### Q. 質問49: 未回答
Cloud Storage に保存されている機密情報の保存データ暗号化を実装する必要があります。どのストレージクラスを選択すべきか?
1. 
2. 
3. 
4. リージョン ストレージ クラス
<details><div>
    答え：
説明
Cloud Storage のリージョン ストレージ クラスは、保存時のデータの暗号化を提供し、特定のリージョン内でより高い可用性を必要とするデータ向けに設計されています。これにより、機密情報が暗号化されて保存されます。追加情報: [Cloud Storage Classes](https://cloud.google.com/storage/docs/storage-classes)
</div></details>

### Q. 質問50: 未回答
ストリーミング データのリアルタイム変換を含むデータ処理パイプラインを設計する必要があります。リアルタイムのストリーム処理のためにサーバーレスで完全に管理されたアプローチを提供するサービスはどれですか?
1. 
2. 
3. Cloud Dataflow
4. 
<details><div>
    答え：
説明
Cloud Dataflow は、ストリーム処理とバッチ処理の両方に対応するサーバーレスのフルマネージド サービスです。これは、データ処理パイプラインでのリアルタイムストリーム処理タスクに適しています。詳細: [Cloud Dataflow の概要](https://cloud.google.com/dataflow/docs)
</div></details>

### Q. 質問51: 未回答
データ処理システムにおいて、Cloud Monitoring のカスタム指標の目的は何ですか?
1. 
2. カスタム指標を使用
3. 
4. 
<details><div>
    答え：
説明
Cloud Monitoring のカスタム指標を使用すると、データ処理システムにおける特定のモニタリングのニーズに合わせたカスタム ダッシュボードを作成して可視化できます。これにより、カスタムデータポイントを追跡および分析できます。追加情報: [カスタムメトリクスの作成](https://cloud.google.com/monitoring/custom-metrics)
</div></details>

### Q. 質問52: 未回答
BigQuery でクエリのパフォーマンスを最適化する場合、テーブルのスキーマ設計のベスト プラクティスは何ですか?
1. 
2. 
3. テーブルの非正規化
4. 
<details><div>
    答え：
説明
テーブルの非正規化は、BigQuery でのクエリのパフォーマンスを最適化し、複雑な結合の必要性を減らし、データ取得の効率を向上させるためのベスト プラクティスです。[詳細](https://cloud.google.com/bigquery/docs/best-practices-schema-design)
</div></details>

### Q. 質問53: 未回答
Google Cloud で大量のストリーミング データを低レイテンシで取り込んで処理するのに適したサービスはどれですか?
1. 
2. Cloud Pub/Sub
3. 
4. 
<details><div>
    答え：
説明
Cloud Pub/Sub は、大量のストリーミング データを低レイテンシで取り込んで処理するために設計されたメッセージング サービスです。リアルタイムのメッセージングとイベント駆動型の機能を提供します。詳細: [Cloud Pub/Sub の概要](https://cloud.google.com/pubsub/docs)
</div></details>

### Q. 質問54: 未回答
Cloud Dataflow を使用して、機械学習パイプラインでストリーミング データをリアルタイム処理している。Cloud Dataflow の「ウィンドウ」の概念の目的は何ですか?
1. 
2. 時間ベースのデータ集計を管理
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataflow では、ストリーミング データ処理における時間ベースのデータ集計を管理するために「ウィンドウ」の概念が使用され、時間の経過に伴うデータのグループ化方法を定義できます。[クラウドデータフローウィンドウ](https://cloud.google.com/dataflow/docs/concepts/windowing)
</div></details>

### Q. 質問55: 未回答
Cloud Dataflow でデータ処理パイプラインを実装する場合、イベント時の処理におけるウィンドウ処理の役割は何ですか?
1. 
2. 
3. イベントの時間間隔に基づいてデータをグループ化
4. 
<details><div>
    答え：
説明
Cloud Dataflow を使用したイベント時間処理のウィンドウ処理では、イベントの時間間隔に基づいてデータをグループ化し、効果的な処理と分析を容易にします。[詳細](https://cloud.google.com/dataflow/docs/concepts/event-time)
</div></details>

### Q. 質問56: 未回答
アクセス頻度の低いデータを扱う際に、Google Cloud Storage で費用対効果の高いストレージ ソリューションを設計するためのベスト プラクティスは何ですか?
1. Nearline Storage クラスの使用
2. 
3. 
4. 
<details><div>
    答え：
説明
Google Cloud Storage の Nearline Storage クラスの使用は、アクセス頻度の低いデータを処理する際の費用対効果の高いストレージ ソリューションのベスト プラクティスです。[詳細](https://cloud.google.com/storage/docs/storage-classes#nearline)
</div></details>

### Q. 質問57: 未回答
データ処理システムでのリアルタイムログ分析と監視に適したサービスはどれですか?
1. 
2. Cloud Logging
3. 
4. 
<details><div>
    答え：
説明
Cloud Logging は、データ処理システムでのリアルタイムのログ分析とモニタリングに推奨されるサービスです。これにより、ログを保存、検索、分析して、システムの動作に関する洞察を得ることができます。詳細: [Cloud Logging の概要](https://cloud.google.com/logging/docs)
</div></details>

### Q. 質問58: 未回答
データ処理パイプラインにおいて、Cloud Storage Transfer Serviceの目的は何ですか?
1. 
2. 
3. 
4. ストレージ バケット間のデータ転送
<details><div>
    答え：
説明
Cloud Storage Transfer Service は、ストレージ バケット間のデータ転送の自動化とスケジュール設定に使用されます。これは、データ処理システム内のデータ移動を管理するのに役立ちます。詳細:[転送サービスの概要](https://cloud.google.com/storage-transfer/docs)
</div></details>

### Q. 質問59: 未回答
データ処理に高スループットと低レイテンシのアクセスが必要なシナリオでは、頻繁にアクセスされる大量のデータを処理するのに適した Google Cloud ストレージ ソリューションはどれですか?
1. Cloud Memorystore
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Memorystore は、高スループットと低レイテンシのアクセスを必要とするシナリオに適しており、頻繁にアクセスされるデータのマネージド インメモリ ストアとして機能します。[詳細](https://cloud.google.com/memorystore/docs)
</div></details>

### Q. 質問60: 未回答
並列計算による大規模なデータセットのバッチ処理を必要とするデータ処理パイプラインを設計しています。このシナリオに最適な Google Cloud サービスはどれですか?
1. 
2. 
3. 
4. Cloud Dataproc 
<details><div>
    答え：
説明
Cloud Dataproc はフルマネージドの Apache Spark および Hadoop サービスで、並列計算による大規模なデータセットのバッチ処理に適しています。スケーラブルで費用対効果の高いソリューションを提供します。詳細: [Cloud Dataproc の概要](https://cloud.google.com/dataproc/docs)
</div></details>

### Q. 質問61: 未回答
Google Cloud リソースのアクセス制御を設定しています。Google Cloud Identity and Access Management(IAM)条件を使用する目的は何ですか?
1. 
2. 
3. 時間ベースのアクセス制限を適用
4. 
<details><div>
    答え：
説明
Google Cloud IAM 条件を使用すると、コンテキスト アクセス ポリシーを定義し、時間ベースのアクセス制限を適用できます。条件を使用すると、特定の条件に基づいてアクセス制御を調整し、リソースのアクセス許可に対する柔軟できめ細かなアプローチを提供できます。詳細については、[IAM 条件](https://cloud.google.com/iam/docs/conditions-overview) を参照してください。
</div></details>

### Q. 質問62: 未回答
データポータルのデータソースとして有効なものは、次のうちどれですか?
1. BigQuery 
2. 
3. Google スプレッドシート
4. 
<details><div>
    答え：
説明
データポータルは、Google スプレッドシートや BigQuery など、さまざまなデータソースをサポートしています。
</div></details>

### Q. 質問63: 未回答
AI Platform Prediction に機械学習モデルをデプロイする場合、「--runtime-image-uri」フラグを設定する意味は何ですか?
1. 予測ランタイムの Docker イメージを定義
2. 
3. 
4. 
<details><div>
    答え：
説明
AI Platform Prediction の「--runtime-image-uri」フラグは、モデル バージョンをデプロイするときに予測ランタイムの Docker イメージを定義するために使用され、予測ランタイム環境をカスタマイズできます。[AI Platform 予測ランタイム画像 URI](https://cloud.google.com/ai-platform/prediction/docs/deploying-models#runtime-image-uri)
</div></details>

### Q. 質問64: 未回答
新しいモデル バージョンが AI Platform Prediction にデプロイされるたびに Cloud Functions の関数をトリガーするプロセスを自動化したい。このイベントドリブンなワークフローを自動化するために、パイプラインに統合できる Google Cloud サービスはどれですか?
1. 
2. 
3. Cloud Pub/Sub
4. 
<details><div>
    答え：
説明
Cloud Pub/Sub をパイプラインに統合して、新しいモデル バージョンが AI Platform Prediction にデプロイされるたびに Cloud Functions の関数をトリガーするイベントドリブン ワークフローを設定できます。[クラウド Pub/Sub](https://cloud.google.com/pubsub)
</div></details>

### Q. 質問65: 未回答
データ処理にセンチメント分析が含まれるシナリオでは、テキストからセンチメントの極性を抽出するのに適した Google Cloud Natural Language API 機能はどれですか?
1. 
2. センチメント分析
3. 
4. 
<details><div>
    答え：
説明
Google Cloud Natural Language API のセンチメント分析機能は、テキストからセンチメントの極性を抽出し、表現されたセンチメントに関する分析情報を提供するのに適しています。[詳細](https://cloud.google.com/natural-language/docs/analyzing-sentiment)
</div></details>

### Q. 質問66: 未回答
データ処理システムにおけるデータカタログ作成の目的と、データカタログ機能を提供する Google Cloud サービスはどれですか?
1. メタデータの検出と管理
2. 
3. 
4. 
<details><div>
    答え：
説明
データカタログには、データ処理システムでのメタデータの検出と管理が含まれます。Google Cloud の Data Catalog サービスは、これらの機能を提供します。[詳細](https://cloud.google.com/data-catalog/docs)
</div></details>

### Q. 質問67: 未回答
ワークロードの要求に基づいて自動スケーリングを必要とするデータ処理パイプラインを設計する任務を負っています。どのサービスを使うべきですか?
1. 
2. 
3. Cloud Dataflow 
4. 
<details><div>
    答え：
説明
Cloud Dataflow は、ワークロードの需要に応じて自動的にスケーリングするように設計されています。自動スケーリング機能を備えたストリーム処理とバッチ処理の両方に対応するサーバーレスで完全に管理された環境を提供します。詳細: [Cloud Dataflow Autoscaling](https://cloud.google.com/dataflow/docs/guides/deploying-a-pipeline#autoscaling)
</div></details>

### Q. 質問68: 未回答
機械学習モデルをリアルタイム予測用の RESTful API としてデプロイする必要があります。予測を提供するための HTTP エンドポイントの作成に使用できる Google Cloud サービスはどれですか?
1.  Cloud Endpoints 
2. 
3. 
4. 
<details><div>
    答え：
説明
Google Cloud の Cloud Endpoints を使用して、RESTful API を介して機械学習予測を提供するための HTTP エンドポイントを作成できます。[クラウドエンドポイント](https://cloud.google.com/endpoints)
</div></details>

### Q. 質問69: 未回答
Cloud Storage でデータの耐久性を設計する場合、偶発的なデータの削除や破損を防ぐためのバージョニングの役割は何ですか?
1. 
2. 
3. 
4. オブジェクトへの変更を経時的に追跡
<details><div>
    答え：
説明
Cloud Storage のバージョニングは、オブジェクトへの変更を経時的に追跡し、偶発的なデータの削除や破損を防ぎ、データの耐久性を強化します。[詳細](https://cloud.google.com/storage/docs/using-object-versioning)
</div></details>

### Q. 質問70: 未回答
サーバーレス データ処理パイプラインを実装する場合、ワークフローのオーケストレーションにおいて Cloud Scheduler はどのような役割を果たしますか?
1. 
2. 
3. 
4. スケジュールに基づいてパイプラインの実行をトリガー
<details><div>
    答え：
説明
Cloud Scheduler は、事前定義されたスケジュールに基づいてパイプラインの実行をトリガーすることで、サーバーレスのデータ処理パイプラインを調整し、効率的なワークフロー管理を実現します。[詳細](https://cloud.google.com/scheduler/docs/quickstart)
</div></details>

### Q. 質問71: 未回答
Cloud Composer のワークフローで、モデルのトレーニング前にデータの前処理を実行するカスタム スクリプトを実行します。Cloud Composer のどのコンポーネントでカスタム Python スクリプトを実行できますか?
1. Python スクリプト
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Composer の PythonOperator を使用すると、ワークフロー内でカスタム Python スクリプトを実行して、モデル トレーニング前のデータの前処理などのタスクを実行できるようになります。[Cloud Composer PythonOperator] (クラウド コンポーザー PythonOperator)(https://cloud.google.com/composer/docs/how-to/using/triggering-with-gcf#pythonoperator)
</div></details>

### Q. 質問72: 未回答
データ処理環境におけるデータリネージツールの目的は何か、またデータガバナンスにどのように貢献するのか。
1. データの動きを追跡して文書化
2. 
3. 
4. 
<details><div>
    答え：
説明
データリネージツールは、データの動きを追跡して文書化し、データの流れと変換を可視化することでデータガバナンスに貢献します。[詳細](https://cloud.google.com/data-catalog/docs/how-to/data-lineage)
</div></details>

### Q. 質問73: 未回答
Cloud Dataproc クラスタのスケーラビリティを重視して設計する場合、費用の最適化におけるプリエンプティブル仮想マシン(VM)の役割は何ですか?
1. 
2. 
3. 
4. 費用対効果の高い一時的なコンピューティング容量を提供
<details><div>
    答え：
説明
Cloud Dataproc クラスタのプリエンプティブル VM は、費用対効果の高い一時的なコンピューティング容量を提供するため、費用の最適化が優先されるシナリオに適しています。[詳細](https://cloud.google.com/dataproc/docs/concepts/compute/preemptible-vms)
</div></details>

### Q. 質問74: 未回答
Google Cloud プロジェクトにセキュリティ制御を実装している。VPC Service Controls 境界を設定する目的は何ですか?
1. データ流出を防ぐ
2. 
3. 
4. 
<details><div>
    答え：
説明
Google Cloud で VPC Service Controls 境界を構成すると、リソースの安全な境界を定義することで、データ流出を防ぐことができます。これにより、サービスに出入りするデータの流れを制御し、不正アクセスから保護するためのセキュリティレイヤーを追加できます。詳細については、[VPC Service Controls](https://cloud.google.com/vpc-service-controls/docs/overview)を参照してください。
</div></details>

### Q. 質問75: 未回答
BigQuery SQL クエリの LIMIT 句の目的は何ですか?
1. 
2. 
3. 
4. クエリによって返される行数を制限
<details><div>
    答え：
説明
BigQuery の LIMIT 句は、クエリによって返される行数を制限するために使用されます。
</div></details>

## 6
### Q. 質問1: 未回答
クラウドベースのデータ処理システムで費用最適化を設計する場合、Cloud Storage のストレージの費用を管理するための推奨される戦略は何ですか?
1. 
2. 
3. 
4. Nearline Storage クラス
<details><div>
    答え：
説明
Cloud Storage でストレージ費用を管理するための推奨される戦略は、アクセス頻度の低いデータには Nearline Storage クラスを使用し、コスト効率とアクセシビリティのバランスを取ることです。[詳細](https://cloud.google.com/storage/docs/storage-classes#nearline)
</div></details>

### Q. 質問2: 未回答
データから有意義な洞察を得るための設計を行う場合、クラウドベースの環境で適切な視覚化ツールと手法を選択するための推奨されるプラクティスは何ですか?
1. 明確で意味のあるラベルを活用
2. 
3. 
4. 
<details><div>
    答え：
説明
適切な視覚化ツールと手法を選択するための推奨されるプラクティスは、クラウドベースの環境で明確で意味のあるラベルを活用し、分析情報の解釈可能性とコミュニケーションを強化することです。[詳細](https://cloud.google.com/solutions/data-visualization-and-business-intelligence)
</div></details>

### Q. 質問3: 未回答
カスタム データ処理ロジックが必要なシナリオでは、データ処理パイプラインの一部としてカスタム機械学習モデルを構築およびデプロイするのに適した Google Cloud サービスはどれですか?
1. 
2. 
3. 
4. AI Platform
<details><div>
    答え：
説明
AI Platform は、データ処理パイプラインの一部としてカスタム機械学習モデルを構築してデプロイするのに適しており、機械学習モデルのトレーニングと提供のためのマネージド環境を提供します。[詳細](https://cloud.google.com/ai-platform)
</div></details>

### Q. 質問4: 未回答
機械学習モデルのトレーニングに AI Platform Training を使用しています。トレーニングジョブを送信するときに「--config」フラグを設定する目的は何ですか?
1. 
2. 
3. 
4. ハイパーパラメータの設定
<details><div>
    答え：
説明
AI Platform Training の「--config」フラグは、トレーニング ジョブを送信するときにハイパーパラメータ値を含む構成ファイルを指定するために使用されます。[AI Platform トレーニング ハイパーパラメータの設定](https://cloud.google.com/ai-platform/training/docs/training-jobs#config)
</div></details>

### Q. 質問5: 未回答
Cloud Dataflow パイプラインでデータの信頼性を設計する場合、ストリーミング データのデータ要素を管理する上でのウィンドウの役割と、処理効率への影響は何ですか?
1. 
2. 
3. データ要素を時間ベースのウィンドウに整理して管理
4. 
<details><div>
    答え：
説明
Cloud Dataflow のウィンドウ処理は、ストリーミング データ内のデータ要素を時間ベースのウィンドウに整理して管理し、管理可能な間隔内で並列処理できるようにすることで処理効率に影響を与えます。[詳細](https://cloud.google.com/dataflow/docs/concepts/windowing)
</div></details>

### Q. 質問6: 未回答
Google Cloud Dataflow で安全なデータ処理を行うためのソリューションを設計しています。処理中に保存データの機密性と整合性を確保するために、どのようなセキュリティ機能を実装できますか?
1. 
2. 
3. 
4. Dataflow シャッフル暗号化
<details><div>
    答え：
説明
Google Cloud Dataflow では、Dataflow シャッフル暗号化を実装することで、処理中の保存データの機密性と整合性を確保できます。この機能は、シャッフル操作中にデータを暗号化し、データ処理パイプラインの全体的なセキュリティを強化します。詳細については、[データフローシャッフル暗号化](https://cloud.google.com/dataflow/docs/security)を参照してください。
</div></details>

### Q. 質問7: 未回答
AI Platform Training で、カスタム ワーカー プールを使用してトレーニング ジョブを送信するときに「--worker-pool-spec」フラグを使用する目的は何ですか?
1. ワーカー プールの構成をカスタマイズ
2. 
3. 
4. 
<details><div>
    答え：
説明
AI Platform Training の「--worker-pool-spec」フラグは、カスタム ワーカー プールを使用してトレーニング ジョブを送信するときに、ワーカー プールの構成をカスタマイズするために使用されます。[AI Platform トレーニング ワーカー プール](https://cloud.google.com/ai-platform/training/docs/training-jobs#custom-worker-pool)
</div></details>

### Q. 質問8: 未回答
AI Platform Prediction でモデル監視を実装している。デプロイされたモデル バージョンの監視を構成するときに '--sampling-rate' フラグを使用する目的は何ですか?
1. 
2. サンプリングされた予測リクエストのレートを制御
3. 
4. 
<details><div>
    答え：
説明
AI Platform Prediction の「--sampling-rate」フラグは、モデル監視の設定時にサンプリングされた予測リクエストのレートを制御するために使用され、分析のために予測のサブセットをモニタリングできます。[AI Platform 予測モデル監視サンプリング](https://cloud.google.com/ai-platform/prediction/docs/monitoring)
</div></details>

### Q. 質問9: 未回答
機械学習ワークフローでデータを前処理するために Cloud Dataflow を使用している。Dataflow パイプラインの実行時に「--temp_location」フラグを指定する目的は何ですか?
1. 
2. 
3. 
4. パイプライン実行用の一時保存場所を指定
<details><div>
    答え：
説明
Cloud Dataflow の「--temp_location」フラグは、パイプライン実行用の一時保存場所を指定するために使用され、中間データと一時データの場所を提供します。[Cloud Dataflow の一時保存場所](https://cloud.google.com/dataflow/docs/guides/specifying-exec-params#temp_location)
</div></details>

### Q. 質問10: 未回答
BigQuery SQL クエリの PARTITION BY 句の目的は何ですか?
1. パーティション内でウィンドウ関数を実行
2. 
3. 
4. 
<details><div>
    答え：
説明
BigQuery の PARTITION BY 句は、結果セットのパーティション内でウィンドウ関数を実行するために使用されます。
</div></details>

### Q. 質問11: 未回答
Google Cloud Dataprep で安全なデータ処理を行うためのソリューションを設計しています。データ準備プロセス中に機密データを保護するために、どのようなセキュリティ機能を活用できますか?
1. 
2. 列レベルのマスキング
3. データリネージ トラッキング
4. 
<details><div>
    答え：
説明
Google Cloud Dataprep では、列レベルのマスキングやデータリネージ トラッキングなどのセキュリティ機能を活用して、データ準備プロセス中に機密データを保護できます。列レベルのマスキングは特定のデータへのアクセスを制御するのに役立ち、データ系列の追跡は、データが処理パイプラインをどのように移動するかを理解するのに役立ちます。詳細については、[Dataprep のセキュリティ機能](https://cloud.google.com/dataprep/docs/html/Security/Security-Features)を参照してください。
</div></details>

### Q. 質問12: 未回答
データ処理システムにおける Cloud Functions の主な目的は何ですか?
1. 
2. 
3. 
4. イベントドリブン関数にサーバーレス コンピューティング
<details><div>
    答え：
説明
Cloud Functions は、データ処理システムのイベントドリブン関数にサーバーレス コンピューティングを提供します。これにより、イベントに応答してコードを実行し、需要に基づいて自動的にスケーリングできます。詳細: [Cloud Functions の概要](https://cloud.google.com/functions/docs)
</div></details>

### Q. 質問13: 未回答
Cloud Spanner のアクセス制御を設定しています。データのセキュリティとコンプライアンスのコンテキストにおける監査ログの目的は何ですか?
1. 
2. データベースへのアクセスと変更を記録
3. 
4. 
<details><div>
    答え：
説明
Cloud Spanner の監査ログは、データベースへのアクセスと変更を記録するために不可欠です。操作の詳細なログを提供し、誰がデータベースにアクセスし、どのようなアクションが実行されたかを追跡することで、規制要件に準拠し、データセキュリティを強化するのに役立ちます。詳細については、[監査ログ](https://cloud.google.com/spanner/docs/audit-logging)を参照してください。
</div></details>

### Q. 質問14: 未回答
データ処理タスクにカスタムの依存関係とランタイム環境が必要なシナリオでは、コンテナ化されたアプリケーションの構築とデプロイに適した Google Cloud サービスはどれですか?
1. 
2. Cloud Run 
3. 
4. 
<details><div>
    答え：
説明
Cloud Run は、カスタム依存関係とランタイム環境を使用してコンテナ化されたアプリケーションを構築およびデプロイするのに適しており、データ処理タスクに柔軟性を提供します。[詳細](https://cloud.google.com/run/docs)
</div></details>

### Q. 質問15: 未回答
データ処理環境での Cloud Storage Transfer Service の主な目的は何ですか?
1.  Cloud Storage バケット間のデータ転送
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Storage Transfer Service は、データ処理システム内の Cloud Storage バケット間のデータ転送を自動化およびスケジュールするために使用されます。これにより、データ移動の管理プロセスが簡素化されます。詳細:[転送サービスの概要](https://cloud.google.com/storage-transfer/docs)
</div></details>

### Q. 質問16: 未回答
Cloud Dataflow パイプラインでスケーラビリティを設計する場合、イベント時の処理で遅れて到着したデータを処理するには、どのようなアプローチをお勧めしますか?
1. 別のウィンドウで再処理
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataflow で遅れて到着したデータを処理するには、別のウィンドウで再処理して、すべてのデータを正確かつ包括的に分析することをおすすめします。[詳細](https://cloud.google.com/dataflow/docs/concepts/event-time)
</div></details>

### Q. 質問17: 未回答
Cloud Storage で費用最適化を設計する場合、失われた場合に再生成できるデータを扱う際のストレージ費用を管理するためのベスト プラクティスは何ですか?
1. 
2. Nearline Storage クラスを使用
3. 
4. 
<details><div>
    答え：
説明
Cloud Storage で Nearline Storage クラスを使用することは、失われた場合に再生成できるデータを処理する際のストレージ費用を管理するためのベスト プラクティスであり、費用効率とアクセシビリティのバランスが取れています。[詳細](https://cloud.google.com/storage/docs/storage-classes#nearline)
</div></details>

### Q. 質問18: 未回答
Apache Hadoop を使用して、大規模なデータセットのバッチ処理を含むデータ処理パイプラインを設計する必要があります。このシナリオに最適な Google Cloud サービスはどれですか?
1. 
2. Cloud Dataproc 
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataproc は、フルマネージドの Apache Hadoop および Apache Spark サービスであり、データ処理パイプラインで Apache Hadoop を使用して大規模なデータセットのバッチ処理に適しています。スケーラブルで費用対効果の高いソリューションを提供します。詳細: [Cloud Dataproc の概要](https://cloud.google.com/dataproc/docs)
</div></details>

### Q. 質問19: 未回答
機械学習モデルの配信に AI Platform Prediction を使用している。予測インスタンスの自動スケーリングを構成する際の '--min-nodes' フラグと '--max-nodes' フラグの目的は何ですか?
1. 
2. 自動スケーリングの制限を設定
3. 
4. 
<details><div>
    答え：
説明
AI Platform Prediction で「--min-nodes」フラグと「--max-nodes」フラグを設定するのは、自動スケーリングの制限を設定し、予測サービスのインスタンス(レプリカ)の最小数と最大数を制御するためのものです。[AI Platform 予測の自動スケーリング](https://cloud.google.com/ai-platform/prediction/docs/autoscaling)
</div></details>

### Q. 質問20: 未回答
依存関係を持つタスクのオーケストレーションと調整を必要とするデータ処理パイプラインを構築しています。このシナリオに最適な Google Cloud サービスはどれですか?
1. 
2. 
3. 
4. Cloud Composer 
<details><div>
    答え：
説明
Cloud Composer は、データ処理システムで依存関係を持つタスクのオーケストレーションと調整に適した、フルマネージドのワークフロー オーケストレーション サービスです。さまざまなサービスやツールの統合をサポートします。詳細: [Cloud Composer ドキュメント](https://cloud.google.com/composer/docs)
</div></details>

### Q. 質問21: 未回答
Cloud Storage ベースのデータ処理システムでデータ セキュリティを設計する場合、保存データを保護するための推奨プラクティスは何ですか?
1. 
2. 
3. 顧客提供のキーを使用して保存データを暗号化
4. 
<details><div>
    答え：
説明
Cloud Storage ベースのデータ処理システムで保存されているデータを保護するための推奨方法は、お客様が用意した鍵を使用してデータを暗号化し、追加のセキュリティ レイヤを提供することです。[詳細](https://cloud.google.com/storage/docs/encryption)
</div></details>

### Q. 質問22: 未回答
Cloud Dataflow パイプラインでは、イベント時間データの処理におけるウォーターマークの役割と、正確なウィンドウ処理の確保にどのように貢献しますか?
1. 
2. イベント時間の進行状況を追跡
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataflow のウォーターマークは、イベント時間の進行状況を追跡することでイベント時間データの処理に重要な役割を果たし、正確なウィンドウ処理の確保に貢献し、すべての関連データがいつ処理されたかをシステムが理解できるようにします。[詳細](https://cloud.google.com/dataflow/docs/concepts/event-time)
</div></details>

### Q. 質問23: 未回答
Cloud Bigtable に保存されているデータに対して、きめ細かなアクセス制御を実装する必要があります。どの機能を使うべきか?
1. 
2. 
3. IAM
4. 
<details><div>
    答え：
説明
Cloud Bigtable の IAM(Identity and Access Management)ポリシーは、データのきめ細かなアクセス制御を実装するために使用されます。データベースにアクセスできるユーザーと、そのユーザーが実行できるアクションを指定できます。詳細: [Cloud Bigtable IAM](https://cloud.google.com/bigtable/docs/access-control)
</div></details>

### Q. 質問24: 未回答
Apache Kafka を使用したリアルタイムのイベントストリーミングと処理を必要とするデータ処理パイプラインを設計しています。このシナリオに最も適した Google Cloud サービスはどれですか?
1. 
2. Cloud Pub/Sub 
3. 
4. 
<details><div>
    答え：
説明
Cloud Pub/Sub は、データ処理パイプラインでのリアルタイムのイベント ストリーミングと処理用に設計されています。イベントデータの取り込みと配信をサポートするメッセージングサービスを提供します。詳細: [Cloud Pub/Sub の概要](https://cloud.google.com/pubsub/docs)
</div></details>

### Q. 質問25: 未回答
機械学習モデルを使用したリアルタイムの異常検出を必要とするデータ処理パイプラインを設計しています。このシナリオに最も適した Google Cloud サービスはどれですか?
1. 
2. 
3. 
4. Cloud AI Platform 
<details><div>
    答え：
説明
Cloud AI Platform は、機械学習モデルのデプロイと管理を目的として設計されているため、データ処理パイプラインで機械学習を使用したリアルタイムの異常検出に適しています。スケーラブルでサーバーレスな環境を提供します。詳細: [Cloud AI Platform の概要](https://cloud.google.com/ai-platform/docs)
</div></details>

### Q. 質問26: 未回答
モバイル アプリケーションやウェブ アプリケーション向けに、フルマネージドでスケーラブルなサーバーレスの NoSQL データベースを提供する Google Cloud サービスはどれですか?
1. 
2. Cloud Firestore 
3. 
4. 
<details><div>
    答え：
説明
Cloud Firestore は、モバイルおよびウェブ アプリケーション向けに設計された、フルマネージドでスケーラブルなサーバーレスの NoSQL データベースです。柔軟なデータモデルを提供し、自動スケーリングをサポートします。詳細: [Cloud Firestore の概要](https://cloud.google.com/firestore/docs)
</div></details>

### Q. 質問27: 未回答
Cloud Composer では、複数のタスクを含む機械学習ワークフローを設計します。Apache Airflow と Cloud Composer の 'BranchPythonOperator' の目的は何ですか?
1. 
2. 
3. 条件に基づいてタスクをトリガー
4. 
<details><div>
    答え：
説明
Apache Airflow と Cloud Composer の「BranchPythonOperator」は、条件に基づいてタスクをトリガーするために使用され、ワークフローの実行フローを動的に制御できます。[Cloud Composer BranchPythonOperator] (クラウド コンポーザー ブランチ パイソン オペレーター)(https://cloud.google.com/composer/docs/how-to/using/operators#branchpythonoperator)
</div></details>

### Q. 質問28: 未回答
クラウドベースのデータ処理システムでデータ プライバシーを重視して設計する場合、機密データを含む Cloud Storage バケットへのアクセス制御を管理するには、どのような方法が推奨されますか?
1. 
2. きめ細かなアクセス制御を使用
3. 
4. 
<details><div>
    答え：
説明
機密データを含む Cloud Storage バケットへのアクセス制御を管理するには、きめ細かなアクセス制御を使用して、安全で制御されたデータ処理を行うことをおすすめします。[詳細](https://cloud.google.com/storage/docs/access-control)
</div></details>

### Q. 質問29: 未回答
AI Platform Prediction では、モデル バージョンをデプロイするときに「--model-type」フラグを使用する目的は何ですか?
1. 
2. 
3. 予測ランタイム フレームワークを構成
4. 
<details><div>
    答え：
説明
AI Platform Prediction の「--model-type」フラグは、デプロイ プロセス中に予測ランタイム フレームワークを構成するために使用されます。[AI Platform 予測モデルタイプ](https://cloud.google.com/ai-platform/prediction/docs/deploying-models#model-type)
</div></details>

### Q. 質問30: 未回答
機械学習モデルの分散トレーニングに AI Platform Training を使用している。トレーニングジョブを送信するときの「--worker-machine-type」フラグの目的は何ですか?
1. 
2. 
3. ワーカー ノードのマシンタイプを指定
4. 
<details><div>
    答え：
説明
AI Platform Training の「--worker-machine-type」フラグは、分散トレーニング ジョブを送信するときにワーカー ノードのマシンタイプを指定するために使用されます。[AI Platform Training Worker マシンタイプ](https://cloud.google.com/ai-platform/training/docs/training-jobs)
</div></details>

### Q. 質問31: 未回答
Google Cloud Storage のアクセス制御を設定しています。データのセキュリティとコンプライアンスのコンテキストにおけるアクセス制御リスト(ACL)の目的は何ですか?
1. 
2. 
3. 
4. オブジェクトごとのアクセス制御を定義
<details><div>
    答え：
説明
Google Cloud Storage のアクセス制御リスト(ACL)は、オブジェクトごとのアクセス制御を定義するために使用されます。これにより、バケット内の個々のオブジェクトにアクセスできるユーザーまたはグループを指定し、オブジェクトレベルの権限をきめ細かく制御できます。詳細については、[アクセス制御リストの使用](https://cloud.google.com/storage/docs/access-control/lists)を参照してください。
</div></details>

### Q. 質問32: 未回答
ビジュアル インターフェイスを使用したデータ変換とクレンジングを含むデータ処理パイプラインの設計を担当します。このシナリオに最適な Google Cloud サービスはどれですか?
1. 
2. 
3. Cloud Dataprep 
4. 
<details><div>
    答え：
説明
Cloud Dataprep は、データ処理パイプラインのビジュアル インターフェースを使用したデータの変換とクレンジング用に設計されています。これは、データの探索と準備のための視覚的でインタラクティブなエクスペリエンスを提供します。詳細: [Cloud Dataprep の概要](https://cloud.google.com/dataprep/docs)
</div></details>

### Q. 質問33: 未回答
機械学習モデルの配信に AI Platform Prediction を使用している。デプロイプロセス中に「--framework」フラグを設定する目的は何ですか?
1. 
2. 
3. 予測ランタイム フレームワークを構成
4. 
<details><div>
    答え：
説明
AI Platform Prediction で「--framework」フラグを設定するのは、デプロイ プロセス中に予測ランタイム フレームワークを構成するためのものです。[AIプラットフォーム予測フレームワーク](https://cloud.google.com/ai-platform/prediction/docs/deploying-models#framework)
</div></details>

### Q. 質問34: 未回答
データポータルのレポートで、さまざまな商品カテゴリの収益を比較します。この分析に最も適したチャートの種類はどれですか?
1. 
2. 棒グラフ
3. 
4. 
<details><div>
    答え：
説明
棒グラフは、データポータルのレポートでさまざまな商品カテゴリの収益を比較するのに最適です。
</div></details>

### Q. 質問35: 未回答
データ処理で急速に変化するデータのリアルタイム分析が必要なシナリオでは、低レイテンシのアクセスでストリーミング データを取り込んで処理するのに適した Google Cloud サービスはどれですか?
1. 
2. Cloud Dataflow 
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataflow は、低レイテンシのアクセスでストリーミング データを取り込んで処理するのに適しており、急速に変化するデータをリアルタイムで分析するためのフルマネージドのサーバーレス ソリューションを提供します。[詳細](https://cloud.google.com/dataflow/docs)
</div></details>

### Q. 質問36: 未回答
Cloud Composer を使用して機械学習ワークフローを設計しており、特定のタイムスケジュールに基づいてタスクをトリガーする必要があります。このタスクに適した Cloud Composer コンポーネントはどれですか?
1. 
2. TimeSensor
3. 
4. 
<details><div>
    答え：
説明
Cloud Composer の「TimeSensor」は、Apache Airflow と Cloud Composer で特定のタイムスケジュールに基づいてタスクをトリガーするのに適しています。[Cloud Composer TimeSensor] (クラウド コンポーザー タイムセンサー)(https://cloud.google.com/composer/docs/how-to/using/sensors#timesensor)
</div></details>

### Q. 質問37: 未回答
データポータルで折れ線グラフを作成して、ウェブサイトのトラフィックの推移を示すとします。このグラフのディメンションと指標として何を使用する必要がありますか?
1. ディメンションとして日付を使用し、指標としてトラフィック
2. 
3. 
4. 
<details><div>
    答え：
説明
時間の経過に伴うウェブサイトトラフィックの傾向を示す折れ線グラフを作成するには、ディメンションとして日付を使用し、指標としてトラフィックを使用します。
</div></details>

### Q. 質問38: 未回答
最も低コストでデータをアーカイブするために設計された Cloud Storage クラスはどれですか?
1. アーカイブ ストレージ クラス
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Storage のアーカイブ ストレージ クラスは、最も低コストでデータをアーカイブできるように設計されています。めったにアクセスされず、長期保存が必要なデータに適しています。追加情報: [Cloud Storage Classes](https://cloud.google.com/storage/docs/storage-classes)
</div></details>

### Q. 質問39: 未回答
SQL クエリを使用したリアルタイムのデータ変換とクレンジングを含むデータ処理パイプラインを設計する必要があります。このシナリオに最適な Google Cloud サービスはどれですか?
1. 
2. 
3. BigQuery 
4. 
<details><div>
    答え：
説明
BigQuery は、サーバーレスで拡張性の高いデータ ウェアハウスであり、データ処理パイプラインでリアルタイムのデータ変換とクレンジングのための SQL クエリを実行できます。アドホックなクエリと分析に適しています。詳細: [BigQuery SQL リファレンス](https://cloud.google.com/bigquery/docs/reference/standard-sql)
</div></details>

### Q. 質問40: 未回答
低レイテンシのアクセスでストリーミング データのリアルタイム分析が必要なシナリオでは、ストリーミング データをリアルタイムで取り込んで処理するのに適した Google Cloud サービスはどれですか?
1. 
2. 
3. Cloud Dataflow 
4. 
<details><div>
    答え：
説明
Cloud Dataflow は、ストリーミング データをリアルタイムで取り込んで処理するのに適しており、大規模なデータセットのリアルタイム分析のためのフルマネージドのサーバーレス ソリューションを提供します。[詳細](https://cloud.google.com/dataflow/docs)
</div></details>

### Q. 質問41: 未回答
機械学習ワークフローのバッチ処理ステップに Cloud Dataflow を使用している。Dataflow パイプラインを実行する際の「--max-num-workers」フラグの目的は何ですか?
1. 
2. ワーカー ノードの最大数を制御
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataflow の「--max-num-workers」フラグは、Dataflow パイプライン内のワーカー ノードの最大数を制御するために使用され、リソースを効果的に管理できるようにします。[Cloud Dataflow Max Num Workers] (クラウドデータフロー最大ワーカー数)(https://cloud.google.com/dataflow/docs/guides/specifying-exec-params#max-num-workers)
</div></details>

### Q. 質問42: 未回答
Cloud SQL のアクセス制御を設定しています。オンプレミスまたは Google Cloud の外部で実行されているアプリケーションのデータベース接続を保護するというコンテキストにおける Cloud SQL Proxy の役割は何ですか?
1. アプリケーションのユーザー ID を検証
2. 
3. 
4. 
<details><div>
    答え：
説明
Google Cloud SQL の Cloud SQL Proxy は、オンプレミスまたは Google Cloud の外部で実行されているアプリケーションのユーザー ID を検証するために使用されます。データベースをパブリック インターネットに公開することなく、Cloud SQL データベースに安全に接続する方法を提供し、セキュリティとコンプライアンスを強化します。詳細については、[Cloud SQL Proxy](https://cloud.google.com/sql/docs/mysql/sql-proxy)のドキュメントをご覧ください。
</div></details>

### Q. 質問43: 未回答
AI Platform Prediction のコンテキストで、モデル バージョンのデプロイ時に「--min-replicas」フラグを指定する目的は何ですか?
1. 
2. レプリカ(インスタンス)の最小数を制御
3. 
4. 
<details><div>
    答え：
説明
AI Platform Prediction の「--min-replicas」フラグは、予測サービス内のレプリカ(インスタンス)の最小数を制御することで、自動スケーリングの制限を設定するために使用されます。[AI Platform 予測の自動スケーリング](https://cloud.google.com/ai-platform/prediction/docs/autoscaling)
</div></details>

### Q. 質問44: 未回答
データ処理ワークロードが変化するシナリオでは、Apache Spark クラスタと Apache Hadoop クラスタでデータ処理ジョブを実行するのに適した Google Cloud サービスはどれですか?
1. Cloud Dataproc 
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataproc は、データ処理ワークロードが変化するシナリオで、Apache Spark クラスタと Apache Hadoop クラスタを使用してデータ処理ジョブを実行するのに適しています。[詳細](https://cloud.google.com/dataproc/docs)
</div></details>

### Q. 質問45: 未回答
データ処理システムにおいて、クラウドデータ損失防止(DLP)の目的は何ですか?
1. 
2. 
3. 機密データの漏洩を防ぐ
4. 
<details><div>
    答え：
説明
Cloud Data Loss Prevention(DLP)は、データ処理環境での機密データの漏洩を防ぐために使用されます。機密情報を特定して保護し、プライバシー規制へのコンプライアンスを確保するのに役立ちます。詳細: [Cloud DLP の概要](https://cloud.google.com/dlp/docs)
</div></details>

### Q. 質問46: 未回答
AI Platform Training を使用して、TensorFlow で機械学習モデルをトレーニングしています。トレーニングジョブを送信する際の「--runtime-version」フラグの目的は何ですか?
1. 
2. TensorFlow ランタイム バージョンを指定
3. 
4. 
<details><div>
    答え：
説明
AI Platform Training の「--runtime-version」フラグは、トレーニング ジョブの送信時に TensorFlow ランタイム バージョンを指定するために使用され、目的の TensorFlow バージョンとの互換性を確保します。[AI Platform Training ランタイム バージョン](https://cloud.google.com/ai-platform/training/docs/training-jobs#runtime-version)
</div></details>

### Q. 質問47: 未回答
AI Platform Prediction で機械学習モデルのモニタリングを設定しています。デプロイされたモデル バージョンの監視を構成する場合の '--target-field' フラグの目的は何ですか?
1. 
2. データセット内のターゲット特徴量を指定
3. 
4. 
<details><div>
    答え：
説明
AI Platform Prediction の「--target-field」フラグは、モデル監視の設定時にデータセット内のターゲット特徴量を指定するために使用されます。これは、特定のターゲット変数に対するモデルのパフォーマンスを監視するのに役立ちます。[AI Platform 予測対象分野](https://cloud.google.com/ai-platform/prediction/docs/monitoring)
</div></details>

### Q. 質問48: 未回答
データ処理ワークロードが変化するシナリオでは、Cloud Storage、Pub/Sub、または HTTP トリガーからのイベントに応答できるサーバーレス関数の作成に適した Google Cloud サービスはどれですか?
1. 
2. 
3. Cloud Functions
4. 
<details><div>
    答え：
説明
Cloud Functions は、Cloud Storage、Pub/Sub、HTTP トリガーからのイベントに応答できるサーバーレス関数の作成に適しており、データ処理ワークロードに柔軟性とスケーラビリティを提供します。[詳細](https://cloud.google.com/functions/docs)
</div></details>

### Q. 質問49: 未回答
Cloud SQL のデータ アクセス制御を実装している。データのセキュリティとコンプライアンスの観点から、限定公開の Google アクセスの目的は何ですか?
1. インスタンスはパブリック IP アドレスなしで Google サービスにアクセス
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud SQL の限定公開の Google アクセスを使用すると、インスタンスはパブリック IP アドレスなしで Google サービスにアクセスできます。これにより、公共のインターネットへの露出を減らし、潜在的な攻撃ベクトルを制限し、他の Google サービスとの安全な通信を促進することで、セキュリティとコンプライアンスが強化されます。詳細については、[限定公開の Google Access for Cloud SQL](https://cloud.google.com/sql/docs/mysql/private-ip)をご覧ください。
</div></details>

### Q. 質問50: 未回答
機械学習モデルの提供に AI Platform Prediction を使用しており、予測インスタンスの数を制御して費用を最適化したい。モデルバージョンのデプロイ中に '--initial-replica-count' フラグを設定する目的は何ですか?
1. 
2. レプリカ(インスタンス)の初期数を定義
3. 
4. 
<details><div>
    答え：
説明
AI Platform Prediction の「--initial-replica-count」フラグは、モデル バージョンをデプロイする際にレプリカ(インスタンス)の初期数を定義するために使用され、コストとリソースの管理に役立ちます。[AI Platform 予測の初期レプリカ数](https://cloud.google.com/ai-platform/prediction/docs/deploying-models#initial-replica-count)
</div></details>

### Q. 質問51: 未回答
新しいモデル バージョンが AI Platform Prediction にデプロイされるたびに Cloud Functions の関数をトリガーするプロセスを自動化したい。このイベントドリブンなワークフローを自動化するために、パイプラインに統合できる Google Cloud サービスはどれですか?
1. 
2. 
3. Cloud Pub/Sub 
4. 
<details><div>
    答え：
説明
Cloud Pub/Sub をパイプラインに統合して、新しいモデル バージョンが AI Platform Prediction にデプロイされるたびに Cloud Functions の関数をトリガーするイベントドリブン ワークフローを設定できます。[クラウド Pub/Sub](https://cloud.google.com/pubsub)
</div></details>

### Q. 質問52: 未回答
データポータルでリアルタイム データを視覚化する必要があります。これを実現するための推奨されるアプローチは何ですか?
1. 
2. 
3. 
4. データポータル API を使用
<details><div>
    答え：
説明
データポータルでリアルタイム データを視覚化するには、データポータル API を使用して、データソースからのリアルタイム更新を有効にします。
</div></details>

### Q. 質問53: 未回答
Cloud Dataprep のデータ処理ジョブでデータの信頼性を設計する場合、一貫性のあるデータ変換を確保する上でスキーマはどのような役割を果たしますか?
1. 
2. 
3. データの構造と形式を検証
4. 
<details><div>
    答え：
説明
Cloud Dataprep データ処理ジョブのスキーマは、データの構造と形式を検証し、データの品質と整合性を維持することで、一貫性のあるデータ変換を確保する上で重要な役割を果たします。[詳細](https://cloud.google.com/dataprep/docs/html/Schema-Pages_57341425)
</div></details>

### Q. 質問54: 未回答
Cloud Dataflow パイプラインでは、Dataflow Shuffle サービスの役割と、データ処理の効率をどのように向上させるのでしょうか?
1. 
2. 並列処理を容易
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataflow の Dataflow Shuffle サービスは、並列処理を容易にし、ワーカー ノード間での効率的なシャッフルとデータの再分散を可能にすることで、データ処理の効率を高めます。[詳細](https://cloud.google.com/dataflow/docs/concepts/shuffle)
</div></details>

### Q. 質問55: 未回答
Cloud Composer を使用して複数のタスクをオーケストレーションする機械学習ワークフローを設計しています。Apache Airflow と Cloud Composer の「ShortCircuitOperator」の目的は何ですか?
1. 条件に基づいてタスクをスキップ
2. 
3. 
4. 
<details><div>
    答え：
説明
Apache Airflow と Cloud Composer の「ShortCircuitOperator」は、条件に基づいてタスクをスキップするために使用され、ワークフローの実行フローを動的に制御できます。[Cloud Composer ShortCircuitOperator] (クラウド コンポーザー ショートサーキット オペレーター)(https://cloud.google.com/composer/docs/how-to/using/operators#shortcircuitoperator)
</div></details>

### Q. 質問56: 未回答
データ処理環境での Cloud Armor の主な目的は何ですか?
1. DDoS 攻撃からの保護を提供し、データ処理システムのウェブ アプリケーション ファイアウォールとして機能
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Armor は DDoS 攻撃からの保護を提供し、データ処理システムのウェブ アプリケーション ファイアウォールとして機能します。アプリケーションやサービスをサイバー脅威から保護し、トラフィックが急増した場合の可用性を確保します。詳細: [Cloud Armor の概要](https://cloud.google.com/armor/docs)
</div></details>

### Q. 質問57: 未回答
クラウドベースのデータ処理システムにおいて、機密データのセキュリティを確保するために BigQuery データセットへのアクセス制御を管理するには、どのような方法が推奨されますか?
1. 
2. 
3. 
4. きめ細かなアクセス制御を実装
<details><div>
    答え：
説明
BigQuery データセットにきめ細かなアクセス制御を実装することは、機密データのセキュリティを確保し、データ処理の制御とセキュリティを提供するためのアクセス管理に推奨されるアプローチです。[詳細](https://cloud.google.com/bigquery/docs/table-access-controls)
</div></details>

### Q. 質問58: 未回答
CPU とメモリの使用率に基づく自動スケーリングを必要とするデータ処理パイプラインを構築しています。データ処理システム内の仮想マシンの自動スケーリングを提供する Google Cloud サービスはどれですか?
1. 
2. 
3. Compute Engine 
4. 
<details><div>
    答え：
説明
Compute Engine では、データ処理システムの CPU とメモリの使用率に基づいて自動スケーリングを行う仮想マシンを作成できます。これにより、インフラストラクチャに対する柔軟性と制御が提供されます。詳細: [Compute Engine Autoscaler](https://cloud.google.com/compute/docs/autoscaler)
</div></details>

### Q. 質問59: 未回答
データ処理システムにおいて、Cloud Spanner の主な目的は何ですか?
1. 
2. 
3. グローバルに分散された水平方向にスケーラブルなデータベース
4. 
<details><div>
    答え：
説明
Cloud Spanner は、データ処理システムで高性能で一貫性のあるデータ処理を行うために設計された、グローバルに分散された水平方向にスケーラブルなデータベースです。強力な一貫性とグローバルトランザクション機能を提供します。詳細: [Cloud Spanner の概要](https://cloud.google.com/spanner/docs)
</div></details>

### Q. 質問60: 未回答
Cloud Dataprep を使用したクラウドベースのデータ処理システムにおいて、データのプロファイリングの目的は何か、データの品質保証にどのように貢献するのか。
1. 
2. データの分布と品質を分析
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataprep でのデータのプロファイリングでは、データの分布と品質を分析し、データセット内の異常、パターン、潜在的な問題を特定することで、データの品質保証に貢献します。[詳細](https://cloud.google.com/dataprep/docs/html/ProfilePage_57341635)
</div></details>

### Q. 質問61: 未回答
ハイパーパラメータの調整に AI Platform Training を使用している。ハイパーパラメータ調整ジョブを設定する際の「--parameter-server-machine-type」フラグの目的は何ですか?
1. マスターノードのマシンタイプを指定
2. 
3. 
4. 
<details><div>
    答え：
説明
AI Platform Training の「--parameter-server-machine-type」フラグは、ハイパーパラメータ調整ジョブを構成する際にマスターノードのマシンタイプを指定するために使用されます。[AI Platform トレーニングのハイパーパラメータ調整](https://cloud.google.com/ai-platform/training/docs/hyperparameter-tuning)
</div></details>

### Q. 質問62: 未回答
AI Platform Prediction に機械学習モデルをデプロイする場合、「--instance-type」フラグを設定する意味は何ですか?
1. 
2. 
3. 予測に使用するマシンタイプを定義
4. 
<details><div>
    答え：
説明
AI Platform Prediction で「--instance-type」フラグを設定すると、予測に使用するマシンタイプを定義し、各予測インスタンスに割り当てられるリソースを設定できます。[AI Platform 予測インスタンス タイプ](https://cloud.google.com/ai-platform/prediction/docs/deploying-models#instance-type)
</div></details>

### Q. 質問63: 未回答
Google Cloud で安全なデータ処理を行うためのソリューションを設計しています。データセキュリティとコンプライアンスのコンテキストにおける顧客管理の暗号鍵(CMEK)の役割は何ですか?
1. 
2. 
3. 暗号化レイヤを追加
4. 
<details><div>
    答え：
説明
Google Cloud の顧客管理の暗号鍵(CMEK)は、保存データの暗号化レイヤを追加します。これにより、お客様は独自の暗号化キーを管理し、保存されたデータの制御とセキュリティを強化できます。詳細については、ドキュメントを参照してください: [顧客管理の暗号化キー](https://cloud.google.com/kms/docs/overview)
</div></details>

### Q. 質問64: 未回答
Cloud Storage 内のデータを保護する責任はお客様にあります。データセキュリティとコンプライアンスのコンテキストで顧客提供の暗号化キー(CSEK)を使用する目的は何ですか?
1. 
2. 
3. 
4. 暗号化レイヤを追加
<details><div>
    答え：
説明
Google Cloud Storage の顧客提供の暗号鍵(CSEK)は、保存データの暗号化レイヤを追加します。CSEKは、お客様が独自の暗号化キーを管理できるようにすることで、保存データの制御とセキュリティを強化し、データ保護要件への準拠に貢献します。詳細については、[お客様提供の暗号化キー](https://cloud.google.com/storage/docs/encryption#customer-supplied_encryption_keys)のドキュメントを参照してください。
</div></details>

### Q. 質問65: 未回答
ストリーミング データのリアルタイムの取り込みと処理を必要とするデータ処理パイプラインを構築しています。このシナリオでスケーラブルでフルマネージドのソリューションを提供する Google Cloud サービスはどれですか?
1. 
2. Cloud Dataflow 
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataflow は、ストリーミング データをリアルタイムで取り込んで処理するように設計されています。これは、ストリーム処理とバッチ処理の両方に対応するスケーラブルで完全に管理されたソリューションを提供します。詳細: [Cloud Dataflow の概要](https://cloud.google.com/dataflow/docs)
</div></details>

### Q. 質問66: 未回答
Cloud Dataprep を使用したクラウドベースのデータ処理システムでは、結合レシピの目的と、複数のソースからのデータの結合にどのように貢献しますか?
1. 
2. 指定された条件に基づいて複数のソースからのデータを結合
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataprep の結合レシピは、指定された条件に基づいて複数のソースからのデータを結合し、データ統合を容易にし、多様なデータセットにわたる包括的な分析を可能にします。[詳細](https://cloud.google.com/dataprep/docs/html/Join-Recipe_57341424)
</div></details>

### Q. 質問67: 未回答
データセットが大きいデータポータルのレポートのパフォーマンスを向上させることができるアクションは、次のうちどれですか?
1. 
2. データ集計関数を使用
3. フィルターを適用してデータを制限
4. 
<details><div>
    答え：
説明
パフォーマンスを向上させるには、フィルターを適用してデータを制限し、データ集計関数を使用して情報を意味のある方法で要約します。
</div></details>

### Q. 質問68: 未回答
データ処理システムにおいて、Cloud Memorystore の目的は何ですか?
1. 
2. 
3. 
4. インメモリ データ キャッシュ
<details><div>
    答え：
説明
Cloud Memorystore は、データ処理システムでのインメモリ データ キャッシュに使用されるフルマネージドのインメモリ データ ストア サービスです。これは、頻繁にアクセスされるデータをキャッシュするための高速でスケーラブルなソリューションを提供します。詳細: [Cloud Memorystore の概要](https://cloud.google.com/memorystore/docs)
</div></details>

### Q. 質問69: 未回答
クラウドベースのデータ処理システムでデータ セキュリティを設計する場合、機密データを含む Cloud Bigtable テーブルへのアクセス制御を管理するには、どのような方法が推奨されますか?
1. 
2. 
3. きめ細かなアクセス制御を使用
4. 
<details><div>
    答え：
説明
機密データを含む Cloud Bigtable テーブルへのアクセス制御を管理するには、きめ細かなアクセス制御を使用して、安全で制御されたデータ処理を行うことをおすすめします。[詳細](https://cloud.google.com/bigtable/docs/access-control)
</div></details>

### Q. 質問70: 未回答
Cloud Dataflow を使用して、機械学習ワークフローのストリーミング データを処理している。ストリーミング データ処理のコンテキストでウィンドウ処理を行う目的は何ですか?
1. 
2. 時間ベースのデータ集計を管理
3. 
4. 
<details><div>
    答え：
説明
Cloud Dataflow では、ストリーミング データ処理で時間ベースのデータ集計を管理するためにウィンドウが使用され、時間の経過に伴うデータのグループ化方法を定義できます。[クラウドデータフローウィンドウ](https://cloud.google.com/dataflow/docs/concepts/windowing)
</div></details>

### Q. 質問71: 未回答
低レイテンシと費用のバランスが取れた、アクセス頻度の低いデータ用に設計された Cloud Storage クラスはどれですか?
1. 
2. 
3. Nearline ストレージ クラス
4. 
<details><div>
    答え：
説明
Cloud Storage の Nearline ストレージ クラスは、低レイテンシとコストのバランスが取れた、アクセス頻度の低いデータ向けに設計されています。これは、アクセス頻度の低いデータに対して費用対効果の高いソリューションを提供します。追加情報: [Cloud Storage Classes](https://cloud.google.com/storage/docs/storage-classes)
</div></details>

### Q. 質問72: 未回答
Google Cloud Pub/Sub のデータを保護する責任はお客様にあります。メッセージの公開時と使用時に転送中のデータを暗号化するために、どのようなセキュリティ機能を有効にできますか?
1. TLS/SSL 暗号化を有効
2. 
3. 
4. 
<details><div>
    答え：
説明
Google Cloud Pub/Sub でメッセージを公開および消費するときに転送中のデータを暗号化するには、TLS/SSL 暗号化を有効にする必要があります。これにより、パブリッシャとサブスクライバーの間でメッセージが安全に送信され、不正アクセスや改ざんが防止されます。詳細については、[TLS/SSLによる通信の保護](https://cloud.google.com/pubsub/docs/secure-communication)を参照してください。
</div></details>

### Q. 質問73: 未回答
データ処理システムにおけるアプリケーションのパフォーマンスをリアルタイムでモニタリングおよびロギングするために設計された Google Cloud サービスはどれですか?
1. Cloud Trace 
2. 
3. 
4. 
<details><div>
    答え：
説明
Cloud Trace は、データ処理システムにおけるアプリケーションのパフォーマンスをリアルタイムでモニタリングし、ログを記録するために設計されています。これにより、要求をトレースし、アプリケーションの待機時間を把握できます。詳細: [Cloud Trace の概要](https://cloud.google.com/trace/docs)
</div></details>

### Q. 質問74: 未回答
Cloud Storage に保存されているデータに対して、きめ細かなアクセス制御を実装する必要があります。どの機能を使うべきか?
1. 
2. 
3. 
4. IAM
<details><div>
    答え：
説明
Cloud Storage の IAM(Identity and Access Management)ポリシーは、データに対するきめ細かなアクセス制御を実装するために使用されます。オブジェクトにアクセスできるユーザーと、そのユーザーが実行できるアクションを指定できます。詳細: [Cloud Storage IAM](https://cloud.google.com/storage/docs/access-control/iam)
</div></details>

### Q. 質問75: 未回答
Cloud Storage のアクセス制御を設定しています。データのセキュリティとコンプライアンスのコンテキストにおける VPC Service Controls の目的は何ですか?
1. 
2. 
3. データ流出を防ぐ
4. 
<details><div>
    答え：
説明
Google Cloud Storage の VPC Service Controls は、データ流出を防ぐために使用されます。VPC Service Controls は、オンプレミス ネットワークから Google Cloud までの範囲のアクセス境界を定義することで、承認されたソースからのみデータにアクセスできるようにし、全体的なセキュリティとコンプライアンスを強化します。詳細については、「VPC Service Controls の概要」(https://cloud.google.com/vpc-service-controls/docs/overview) を参照してください。
</div></details>
