
## Q.  1
Compute Engine のアンマネージド インスタンス グループでホストされているグローバルで安全なウェブ アプリケーションがあります。このアプリケーションは現在、us-central1-a にデプロイされています。しかし、会社の成長により、新規顧客のほとんどは地理的にヨーロッパ西部2地域に近くなっています。将来の顧客の需要に合わせてアプリケーションを自動的にスケーリングし、Google が推奨するプラクティスにも従うソリューションを実装する必要があります。あなたは何をすべきか?

1. リージョンの仮想 IP アドレスを使用してネットワーク ロード バランサーをデプロイします。マネージド インスタンス グループを使用してバックエンドを構成します。
2. リージョンの仮想 IP アドレスを使用して HTTP(S) ロードバランサーをデプロイします。マネージド インスタンス グループを使用してバックエンドを構成します。
3. グローバル仮想 IP アドレスを使用して HTTP(S) ロードバランサをデプロイします。europe-west2-a でバックエンドをマネージド インスタンス グループで構成します。
4. グローバル仮想 IP アドレスを使用してネットワーク ロード バランサーをデプロイします。europe-west2-a でバックエンドをアンマネージド インスタンス グループで構成します。
<details><div><pre style="line-height: 1.2;">
    答え：C は Google が推奨する手法に従っているため、正しいです。
    グローバルロードバランサーは、1つのIPアドレスを介して複数のリージョンにトラフィックを転送します。
    これらのサービスの両方を使用してアプリケーションを複数のゾーンに分散することで、ゾーンの中断などの極端なケースでもアプリケーションの可用性を確保できます。

* A は、ネットワーク ロード バランサーのみを使用して複数のリージョンの顧客にサービスを提供できないため、正しくありません。
* B は、リージョン HTTP ロードバランサーが 1 つのリージョンのみをサポートしているため、複数のリージョンの顧客にサービスを提供できないため、正しくありません。
* ネットワーク・ロード・バランサはグローバルではなくリージョナルであるため、グローバル HTTPS アプリケーションには適していないため、D は正しくありません。
 
https://cloud.google.com/load-balancing/docs/https/use-cases#cross-region_load_balancing
 
https://cloud.google.com/compute/docs/tutorials/high-availability-load-balancing
</pre></div></details>

## Q.  2
会社には、現在インターネット全体からのトラフィックを許可するリージョンの Compute Engine SaaS(Software as a Service)アプリケーションがあります。アプリケーションは、パブリックインターネットからアクセスできないようにする必要があります。また、特定の仮想マシン (VM) のみが Secure Shell (SSH) を使用してアプリケーションにアクセスできるようにすることもできます。要件を満たすために何をすべきですか?

1. 0.0.0.0/0 からのトラフィックを許可するルールを削除します。192.168.0.0/16、172.16.0.0/12、および 10.0.0.0/8 からのトラフィックを許可するファイアウォール ルールを作成します。
2. 0.0.0.0/0 からのトラフィックを拒否する新しいルールを作成します。192.168.0.0/16、172.16.0.0/12、および 10.0.0.0/8 からのトラフィックを拒否するファイアウォール ルールを作成します。
3. 0.0.0.0/0 からの SSH トラフィックを許可する事前入力ルールを削除します。TCP 22 へのアクセスを許可するネットワーク タグを作成し、アプリケーションにアクセスする各 VM にタグを適用します。
4. 0.0.0.0/0 からの SSH トラフィックを許可する事前入力ルールを削除します。TCP 3389 へのアクセスを許可するネットワーク タグを作成し、新しく作成したタグをアプリケーションにアクセスする各 VM に適用します。
<details><div><pre style="line-height: 1.2;">
    答え：3. 0.0.0.0/0 からの SSH トラフィックを許可する事前入力ルールを削除します。
    TCP 22 へのアクセスを許可するネットワーク タグを作成し、アプリケーションにアクセスする各 VM にタグを適用します。

* 0.0.0.0/0 からのトラフィックを許可する新しいルールを作成すると、アプリケーションへのパブリック アクセスが許可されるため、A は正しくありません。
* B は、これらのファイアウォール ルールがパブリック アクセスとプライベート アクセスの両方を拒否するため、正しくありません。
* TCP 22 にアクセスできるネットワークタグを使用すると、Secure Shell へのアクセスが許可され、特定の Virtual Private Cloud(VPC)からのアクセスが許可されるため、C は正しいです。
* Remote Desktop Protocol (RDP) には TCP 3389 が使用されているため、D は正しくありません。
 
https://cloud.google.com/vpc/docs/firewalls
</pre></div></details>

## Q.  3
あなたは、すべての Google Cloud ファイアウォール ルールの一元管理を実施したいと考えているエンタープライズ企業で働いています。現在、各社内の事業部門はフォルダを使用して Google Cloud のプロジェクトとネットワークを管理しています。ビジネス ユニットの Compute Engine VM への受信リクエストを拒否する機能が必要です。あなたは何をすべきか?

1. トラフィックを拒否および許可するように VPC ファイアウォール ルールを設定します。
2. 共有 VPC ネットワークを作成し、ホスト プロジェクトでファイアウォールを構成します。
3. 組織レベルで階層型ファイアウォール ポリシーを作成し、必要な部署へのすべてのエグレス トラフィックを許可します。
4. 組織レベルで階層型ファイアウォール ポリシーを作成し、必要なビジネス ユニットへのすべてのイングレス トラフィックを拒否します。
<details><div><pre style="line-height: 1.2;">
    答え：4. 組織レベルで階層型ファイアウォール ポリシーを作成し、必要なビジネス ユニットへのすべてのイングレス トラフィックを拒否します。

* A は正しくありません。VPC を作成しても、組織全体にファイアウォールポリシーを適用できないからです。
* B は正しくありません。共有 VPC ネットワークを作成しても、組織全体にファイアウォール ポリシーを適用できないからです。
* 組織レベルで階層型ファイアウォールポリシーを作成し、エグレストラフィックを許可しても、受信リクエストにポリシーが適用されないため、Cは正しくありません。
* 階層型ファイアウォールポリシーを使用すると、組織全体で一貫したファイアウォールポリシーを作成して適用できるため、Dは正しいです。階層型ファイアウォール ポリシーは、組織全体または個々のフォルダに割り当てることができます。これらのポリシーには、イングレス接続とエグレス接続を明示的に拒否または許可できるルールが含まれています。
 
https://cloud.google.com/vpc/docs/firewall-policies?hl=en
 
https://cloud.google.com/vpc/docs/firewall-policies-examples#example_4_configure_organization-wide_and_folder-specific_rules
</pre></div></details>

## Q.  4
顧客は Google Cloud 上に SaaS アプリケーションを持っています。お客様のアプリケーションを最も安全で費用対効果の高い方法で利用できるようにしたいと考えているでしょう。あなたは何をすべきか?

1. Google Cloud VPC ネットワークへの接続を提供する Cloud VPN ゲートウェイを構成します。
2. Cloud Identity アカウントを作成して、Google Cloud VPC ネットワークにアクセスできるようにします。
3. VPC ネットワーク ピアリングを設定して、Google Cloud VPC ネットワークに直接接続します。
4. Google Cloud VPC ネットワークへの接続を提供するカスタム HTTP アプリケーションを作成します。
<details><div><pre style="line-height: 1.2;">
    答え：3. VPC ネットワーク ピアリングを設定して、Google Cloud VPC ネットワークに直接接続します。

* Cloud VPN を使用すると追加の下り(外向き)費用が発生するため、A は正しくありません。
* Cloud Identity アカウントのみを作成しても、顧客のアプリケーションをサポートするのに十分なアクセス権が得られないため、B は正しくありません。
* VPC ネットワーク ピアリングを使用すると、VPC ネットワークを接続して、異なる VPC ネットワークのワークロードが内部で通信できるようにするため、C は正しいです。トラフィックは Google のネットワーク内にとどまり、公共のインターネットを経由することはありません。
* カスタム HTTP アプリケーションの作成にはソフトウェア開発が必要であり、費用対効果が高くないため、D は正しくありません。
 
https://cloud.google.com/vpc/docs/vpc-peering
</pre></div></details>

## Q.  5
外部からのインバウンド アクセスを防止する Google Kubernetes Engine(GKE)クラスタを作成する必要があります。クラスターで、特定のノードがアウトバウンドインターネットにアクセスできるようにする必要があります。あなたは何をすべきか?

1. VPC ネイティブ クラスターを作成し、プライベート ノードを有効にします。
2. プライベート GKE クラスタを作成し、プライベートノードを有効にします。
3. プライベート GKE クラスタを作成し、外部アクセスに Cloud NAT を使用します。
4. 共有 VPC ネットワーク内に GKE クラスタを作成し、ノードの外部アクセスを許可するファイアウォール ルールを作成します。
 
<details><div><pre style="line-height: 1.2;">
    答え：3. プライベート GKE クラスタを作成し、外部アクセスに Cloud NAT を使用します。

* VPC ネイティブクラスターを作成すると外部アウトバウンドアクセスが許可されないため、A は正しくありません。
* プライベート GKE クラスタにはデフォルトで外部送信アクセス権がないため、B は正しくありません。
* Cloud NAT を使用するプライベート クラスタを作成することは、外部アクセスを防ぐためのベスト プラクティスであるため、C は正しいです。
* 共有 VPC ネットワークでは、外部 IP アドレスがクラスタにアクセスできる可能性があるため、D は正しくありません。
 
https://cloud.google.com/kubernetes-engine/docs/how-to/private-clusters#other_configurations
</pre></div></details>

## Q.  6
現在、会社には Google Kubernetes Engine(GKE)で作成されたルートベースの VPC ネイティブ クラスターがあります。来年は、GKE にさらに多くのアプリケーションをデプロイする予定で、GKE では利用可能なすべての IP アドレスが使用されます。Google が推奨するプラクティスに従って、スケーリングを改善する必要があります。あなたは何をすべきか?

1. オートパイロット モードで公開 GKE クラスタを作成します。
2. 認証済みネットワークを使用して新しい GKE クラスタを作成します。
3. 新しい VPC ネイティブ クラスタを作成し、共有 VPC ネットワークを使用します。
4. 新しいルートベースのクラスタを作成し、共有 VPC ネットワークを使用します。
<details><div><pre style="line-height: 1.2;">
    答え：3. 新しい VPC ネイティブ クラスタを作成し、共有 VPC ネットワークを使用します。

* Autopilot の VPC ネイティブクラスターには事前設定されたポッド制限があるため、A は正しくありません。
* B は正しくありません。これは、許可されたネットワークを持つ GKE クラスタは、スケーラビリティを向上させるためではなく、セキュリティを向上させるために使用されるためです。
* 共有 VPC ネットワークで VPC ネイティブ クラスタを使用することは Google が推奨する方法であるため、C は正しいです。VPC ネイティブ クラスタは、ルートを消費せずにより簡単にスケーリングでき、VPC ネットワークを安全かつ一元的に管理する方法です。
* 新しいルートベースのクラスタでは、RFC 1918 以外の範囲を使用できないため、問題を解決するために必要なスケーラビリティがサポートされないため、D は正しくありません。
 
https://cloud.google.com/kubernetes-engine/docs/best-practices/networking#vpc-native-clusters
 
https://cloud.google.com/kubernetes-engine/docs/how-to/flexible-pod-cidr#cidr_settings_for_clusters
</pre></div></details>

## Q.  7
あなたの会社は、Google Cloud を使用する外部ベンダーと連携しています。ベンダーにプライベート Cloud SQL インスタンスへのアクセス権を付与する必要があります。コストを最小限に抑えながら、高パフォーマンスのアクセスを提供したいと考えています。あなたは何をすべきか?

1. Google プロジェクトの共有 VPC ネットワークを作成して構成します。
2. Cloud Identity でユーザー アカウントを作成し、2 段階認証プロセスを適用します。
3. ベンダーの Google プロジェクトとの VPC ネットワーク ピアリング接続を作成して構成します。
4. ベンダーの Google アカウントを、Cloud SQL インスタンスにアクセスできる既存の Cloud Identity グループに追加します。
<details><div><pre style="line-height: 1.2;">
    答え：3. 

* 共有 VPC 接続では組織へのアクセスが提供されないため、A は正しくありません。
* Cloud Identity と 2 段階認証プロセスでは高パフォーマンスのアクセスが提供されないため、B は正しくありません。
* VPC ネットワーク ピアリングを使用すると、追加料金が発生しにくく、パフォーマンスが向上するため、C は正しいです。
* Cloud Identity グループは高パフォーマンスのアクセスを提供しないため、D は正しくありません。
 
https://cloud.google.com/architecture/best-practices-vpc-design#vpc-peering-limits
</pre></div></details>

## Q.  8
あなたの会社は、大企業のオンプレミス データセンターから Google Cloud への移行を計画しています。現在のオンプレミス ネットワークはローカル ネットワーク チームによって管理されているため、将来の成長に備えてクラウド ネットワークを設計しながら、複数の内部チームが Google Cloud で迅速に作業を開始できるようにしたいと考えています。あなたは何をすべきか?

1. 1 つのホスト プロジェクトで共有 VPC ネットワークを作成します。
2. 複数のホスト プロジェクトを持つ共有 VPC ネットワークを作成します。
3. 内部チームごとに、/8 CIDR ブロックを使用して VPC ネットワークを作成します。
4. 5 つの VPC ネットワークを持つ 1 つのプロジェクトを作成し、それぞれに /28 CIDR ブロックを設定します。
<details><div><pre style="line-height: 1.2;">
    答え：2. 複数のホスト プロジェクトを持つ共有 VPC ネットワークを作成します。

* A は正しくありません。なぜなら、単一のホストプロジェクトを使用すると、プロジェクトのクォータに早く到達する可能性があるため、成長が制限される可能性があるためです。
* B は正しいです。なぜなら、すべての VPC ネットワークの総リソース要件をプロジェクトの割り当て内で満たすことができない場合は、複数のホスト プロジェクトを持つアーキテクチャを使用し、ホスト プロジェクトごとに 1 つの共有 VPC ネットワークを設定する必要があるからです。
* Cは正しくありません、なぜならこのソリューションはネットワークを作成するためにより多くの労力を必要とし、それはあなたの内部チームが迅速に運用を開始することを許さないからです。
* /28 CIDR ブロックを持つ 1 つのプロジェクトは、合計 16 個の IP アドレスしか提供しないため、将来の成長に適していないため、D は正しくありません。
 
https://cloud.google.com/architecture/best-practices-vpc-design#multiple-host-quota
 
https://cloud.google.com/vpc/docs/quota#shared-vpc
</pre></div></details>

## Q.  9
あなたの組織は最近、いくつかのプライベート Google Kubernetes Engine(GKE)クラスタをデプロイしました。一部の GKE クラスタのコントロール プレーンには、どの IP アドレスからでもアクセスできることに気付きました。コントロールプレーンへのネットワークアクセスを制限しながら、インフラストラクチャの変更を最小限に抑えたい。あなたは何をすべきか?

1. 認証済みネットワークを有効にして新しい GKE クラスタを作成します。
2. 認証済みネットワークを有効にした新しい GKE プライベート クラスタを作成します。
3. 既存の GKE プライベート クラスタを更新して、新しい認証済みネットワークを有効にします。
4. 既存のクラスタの外部 IP アドレス範囲を更新して、新しい認証済みネットワークを有効にします。
 
<details><div><pre style="line-height: 1.2;">
    答え：3. 既存の GKE プライベート クラスタを更新して、新しい認証済みネットワークを有効にします。

* 新しい GKE クラスタを作成するにはインフラストラクチャの変更が必要なため、A は正しくありません。
* B は、新しい GKE クラスタを作成するにはインフラストラクチャの変更が必要なため、正しくありません。
* 承認されたネットワークでは CIDR 範囲を指定し、その範囲内の IP アドレスが HTTPS を使用してクラスター コントロール プレーン エンドポイントにアクセスできるため、C は正しいです。既存のクラスタに承認されたネットワークを追加するには、gcloud CLI または Google Cloud Console を使用します。
* 外部 IP アドレス範囲を更新すると、アドレス範囲を拡大または縮小できますが、ネットワーク アクセスは制限されないため、D は正しくありません。
 
https://cloud.google.com/kubernetes-engine/docs/how-to/authorized-networks#overview。
 
https://cloud.google.com/kubernetes-engine/docs/how-to/authorized-networks#add
</pre></div></details>

## Q.  10
Cloud CDN に静的データを持つアプリケーションをデプロイしました。配信元サーバーの分散型サービス拒否 (DDoS) 保護を有効にする必要があります。あなたは何をすべきか?

1. ゾーン ネットワーク エンドポイント グループを設定します。Google Cloud Armor セキュリティ ポリシーを作成し、外部オリジンに適用します。
2. 既存の HTTP ロードバランサーを削除します。新しい HTTP ロードバランサーを作成します。Google Cloud Armor セキュリティ ポリシーを作成し、外部オリジンに適用します。
3. ゾーン ネットワーク エンドポイント グループを持つバックエンド サービスを使用して、内部 HTTP ロード バランサを作成します。Google Cloud Armor セキュリティ ポリシーを作成し、外部オリジンに適用します。
4. 既存の外部 HTTP ロードバランサを、インターネット・ネットワーク・エンドポイント・グループを持つバックエンド・サービスで構成します。Google Cloud Armor セキュリティ ポリシーを作成し、外部オリジンに適用します。
 
<details><div><pre style="line-height: 1.2;">
    答え：4.

* 静的データをホストするバックエンドの Cloud CDN バケットにトラフィックを転送するためにロードバランサが必要なため、A は正しくありません。
* 既存のHTTPロードバランサーを削除して新しいロードバランサーを最初から作成することは技術的な利点がないため、Bは正しくありません。
* DDoS 保護を有効にするには、Cloud CDN バックエンド サービスを備えたレイヤ 7 HTTPS ロードバランサが必要なため、C は正しくありません。
* バックエンド サービスで構成された Cloud CDN デプロイは Google Cloud Armor ポリシーで保護できるため、D は正しいです。
 
https://cloud.google.com/armor/docs/common-use-cases#cdn-ddos-defense
</pre></div></details>

## Q.  11
あなたの組織は、世界中のいくつかの地域でデジタルストリーミングサービスを提供しています。 お客様からのフィードバックから、パフォーマンスに一貫性がないことが示されています。Cloud CDN は Cloud Storage バックエンド バケットで設定します。パフォーマンスを向上させるために、最も効率的な構成を作成したいと考えています。パフォーマンスを最適化するために何をすべきか?

1. HTTP/3 および QUIC プロトコルのサポートを有効にします。
2. ネガティブキャッシングを使用して、バックエンドの負荷を軽減します。
3. WAF ルールを使用して Google Cloud Armor を構成し、HTTP/3 プロトコルと QUIC プロトコルのサポートを有効にします。
4. HTTP/3、QUIC プロトコルのサポート、およびネガティブ キャッシュを有効にして、バックエンドの負荷を軽減します。
 
<details><div><pre style="line-height: 1.2;">
    答え：4.

* HTTP/3 と QUIC プロトコルのサポートを有効にするだけではパフォーマンスの問題が解決しないため、A は正しくありません。
* B は正しくありません。なぜなら、ネガティブキャッシングはパフォーマンスを向上させますが、HTTP/3 および QUIC プロトコルのサポートと共に使用すると、パフォーマンスがさらに向上するためです。
* Google Cloud Armorのルールはパフォーマンスの問題を解決するためではなく、セキュリティを向上させるために使用されるため、Cは正しくありません。HTTP/3およびQUICプロトコルのサポートを有効にするだけではパフォーマンスの問題を解決できません。
* HTTP/3、QUIC プロトコルのサポート、およびネガティブキャッシングを有効にして設定すると、パフォーマンスが最適化されるため、D は正しいです。
 
https://cloud.google.com/cdn/docs/best-practices?hl=en#optimize_performance
</pre></div></details>

## Q.  12
組織でいくつかのワークロードを Google Cloud に移行した。現在の DNS サーバーはオンプレミスであり、DNS 解決の実行方法を決定します。Google が推奨するプラクティスに従い、レイテンシに影響を与えずにハイブリッド環境をサポートするために DNS を変更する必要があります。あなたは何をすべきか?

1. DNS サーバはオンプレミスに保管してください。
2. すべての DNS 解決を Cloud DNS に移行します。
3. ハイブリッド アプローチで 2 つの DNS システムを使用します。
4. すべての DNS 解決を外部プロバイダーに移動します。
<details><div><pre style="line-height: 1.2;">
    答え：3. ハイブリッド アプローチで 2 つの DNS システムを使用します。

* Aは正しくありません。DNS サーバーをオンプレミスに保持すると、Google Cloud からの DNS リクエストのレイテンシが長くなるため、パフォーマンスに影響が及ぶ可能性があります。
* B は、ハイブリッド環境に対して Google が推奨するプラクティスではなく、現在のオンプレミスのワークロードが Cloud DNS にアクセスするときにレイテンシが高くなるため、正しくありません。
* Cは、Googleが推奨するプラクティスが2つの権威DNSシステムによるハイブリッドアプローチを使用することであるため、正しいです。プライベートな Google Cloud 環境に対する権限のある DNS 解決は、Cloud DNS によって行われます。オンプレミス リソースに対する権限のある DNS 解決は、オンプレミスの既存の DNS サーバーによってホストされます。
* D は Google が推奨する方法ではなく、すべての DNS 解決を外部プロバイダに移動するとレイテンシが長くなる可能性があるため、正しくありません。
 
https://cloud.google.com/dns/docs/best-practices#choose_where_dns_resolution_is_performed
</pre></div></details>

## Q.  13
現在、Google Cloud では数百の Compute Engine インスタンスが実行されています。セキュリティ担当者が新しいセキュリティ ポリシーを作成しました: クラウド環境内の VM は外部 (パブリック) IP アドレスを持つことができません。レポートを実行すると、Compute Engine インスタンス上に外部 IP アドレスが割り当てられた複数の本番環境アプリケーションが検出されます。VM は、外部 IP アドレスが削除された後でも、ネットワークのパフォーマンスを低下させることなく、外部送信接続の作成を許可する必要があります。あなたは何をすべきか?

1. インターネットにアクセスするようにプロキシ Compute Engine インスタンスを構成します。
2. ゲートウェイへのトラフィックを拒否する組織の Cloud NAT ポリシーを作成して構成します。
3. Compute Engine インスタンスの外部アクセスを維持するために、新しい Cloud NAT ゲートウェイを作成します。
4. 新しい Cloud NAT ゲートウェイと Cloud Router を使用して GKE プライベート クラスタを作成し、Compute Engine インスタンスで使用されているものと同じ VPC ネットワークを選択します。
<details><div><pre style="line-height: 1.2;">
    答え：3.

* Compute Engine インスタンスの使用は、この問題を解決するために設計された Cloud NAT ほど安全性や拡張性がないため、A は正しくありません。
* B は、このソリューションではすべての VM がインターネットにアクセスできるため、正しくありません。
* Cloud NAT(ネットワーク アドレス変換)では、外部 IP アドレスを持たない指定されたリソースがインターネットへのアウトバウンド接続を作成できるため、C は正しいです。
* GKE プライベート クラスタを作成しても、現在の Compute Engine VM にアクセスできないため、D は正しくありません。
 
https://cloud.google.com/nat/docs/using-nat
 
https://cloud.google.com/blog/topics/developers-practitioners/cloud-nat-explained
</pre></div></details>

## Q.  14
VPN デプロイ用に新しい Cloud Router を作成する必要があります。Cloud Router を作成した後、Border Gateway Protocol(BGP)セッションの確立に失敗したというエラーが表示されます。問題のトラブルシューティングを行う必要があります。あなたは何をすべきか?

1. Google Cloud Console で Cloud Router のログを確認します。Cloud Router を別の BGP IP ピア アドレスで再構成します。
2. Google Cloud コンソールで VPN ログを確認します。VPN ステータス メッセージを確認し、オンプレミスの BGP ルーターの設定を確認します。
3. Google Cloud コンソールで VPN ログを確認します。Cloud Router を削除し、別の BGP IP アドレスで新しい Cloud Router を作成します。
4. Google Cloud Console で Cloud Router のログを確認します。新しい Cloud Router を作成します。VPN ステータス メッセージを確認し、オンプレミスの BGP ルーターの設定を確認します。
<details><div><pre style="line-height: 1.2;">
    答え：2. Google Cloud コンソールで VPN ログを確認します。VPN ステータス メッセージを確認し、オンプレミスの BGP ルーターの設定を確認します。

* A は、Cloud Router を再構成しても問題が解決しないため、正しくありません。
* B が正しいのは、Google が推奨する方法は、オンプレミスの BGP ルーターの設定と Cloud Router の設定が正しいことを確認することです。
* Cloud Router を削除しても問題は解決しないため、C は正しくありません。
* 新しいCloud Routerを作成しても問題は解決しないため、Dは正しくありません。
 
https://cloud.google.com/network-connectivity/docs/router/support/troubleshooting#bgp_session_failed_to_establish
 
https://cloud.google.com/network-connectivity/docs/vpn/support/troubleshooting#troubleshooting-reference
</pre></div></details>

## Q.  15
ネットワーク管理者が Google Cloud にいくつかの HA VPN を作成しています。ただし、HA VPN を使用するいくつかのアプリケーションでは、予期しないタイミングで応答が遅延することが示されています。問題のトラブルシューティングを行う必要があります。あなたは何をすべきか?

1. Google Cloud Console のログとネットワーク トポロジ情報を分析します。
2. パフォーマンス ダッシュボードを使用して、パケット損失と遅延のメトリックを確認します。
3. Performance Dashboardを使用し、接続テストを実行して構成の問題を検出します。
4. 現在のHA VPNをFOUR_IPS_REDUNDANCYで再設定し、ベンチマークテストを実施します。
<details><div><pre style="line-height: 1.2;">
    答え：2.

* Aは、トラブルシューティングに必要な情報を探す場所が間違っているため、正しくありません。
* B は正しいです。レイテンシやパケット損失の問題を特定するために、Google Cloud ネットワーク全体のパフォーマンスをモニタリングできます。Google Cloud のパフォーマンス ビューの Performance Dashboard には、すべての Google Cloud リソースのパケット損失とレイテンシの指標が表示されます。
* 接続テストを実行すると、構成の問題が検出されるだけであるため、C は正しくありません。接続を確認するために、データ プレーンを介してパケットを送信しようとはしません。
* HA VPN を再設定しても問題が特定されないため、D は正しくありません。
 
https://cloud.google.com/network-connectivity/docs/vpn/support/troubleshooting#network_latency_issues_between_vms_in_different_regions
 
https://cloud.google.com/network-intelligence-center/docs/performance-dashboard/how-to/using-performance-dashboard
</pre></div></details>

## Q.  16
オンプレミス ネットワークを Google Cloud に接続するには、新しい Cloud Router を作成する必要があります。リンクに障害が発生した場合にサービスが中断されないようにする必要があります。あなたは何をすべきか?

1. オンプレミスの BGP デバイスでグレースフル リスタートを有効にします。
2. グローバル動的ルーティングを有効にした Cloud Router を作成します。
3. リージョンの動的ルーティングが有効になっている Cloud Router を作成します。
4. 既存の BGP セッションで基本アドバタイズ ルートの優先度を変更します。
<details><div><pre style="line-height: 1.2;">
    答え：1. オンプレミスの BGP デバイスでグレースフル リスタートを有効にします。

* Google が推奨する方法は、オンプレミスの BGP デバイスでグレースフル リスタートを有効にすることであるため、A は正しいです。グレースフル リスタートでは、Cloud Router またはオンプレミスの BGP デバイスに障害が発生しても、ネットワーク間のトラフィックは中断されませんが、グレースフル リスタート期間内に BGP セッションが再確立されます。
* グローバル動的ルーティングでは、リンクに障害が発生した場合のサービスの中断を防ぐことはできないため、B は正しくありません。
* リージョンの動的ルーティングでは、リンクに障害が発生した場合にサービスの中断を防ぐことができないため、C は正しくありません。
* グレースフル リスタートを無効にすると、パケットがドロップされ、ネットワークが中断されるため、D は正しくありません。
 
https://cloud.google.com/network-connectivity/docs/router/concepts/best-practices
 
https://cloud.google.com/network-connectivity/docs/router/concepts/overview#route-advertisement-default
</pre></div></details>

## Q.  17
最近 Google Kubernetes Engine(GKE)をアップグレードした後、一部のアプリケーションがイングレスから予期されるトラフィックを受け取っていないことに気付きました。アプリケーションのトラブルシューティングを行うには、どうすればよいですか?

1. 新しい VPC を作成し、VPC フローログと Cloud Logging を有効にします。バックエンドへのトラフィック パスを検証します。
2. Cloud Logging と Cloud Monitoring を有効にした新しいテスト GKE クラスタを作成します。テスト シナリオを生成します。
3. ログバケットを作成します。Cloud Logging で HTTPS 上り(内向き)リソースのログを確認し、バックエンドへのトラフィックを検証します。
4. 既存の GKE クラスタを変更し、Cloud Logging と Cloud Monitoring を有効にします。ログを BigQuery にエクスポートして分析します。
 
<details><div><pre style="line-height: 1.2;">
    答え：3. ログバケットを作成します。Cloud Logging で HTTPS 上り(内向き)リソースのログを確認し、バックエンドへのトラフィックを検証します。

* 新しい VPC を作成しても、既存の入力トラフィックの問題のトラブルシューティングには役立たないため、A は正しくありません。新しい VPC は、既存のデプロイとは無関係の新しい構成です。
* Cloud Logging と Cloud Monitoring はデフォルトですでに有効になっているため、B は正しくありません。テスト シナリオで新しい GKE クラスタを作成しても、現在の Ingress のトラフィック問題を特定するのに役立ちません。新しい GKE クラスタは、既存のデプロイとは無関係の新しい構成です。
* Cは正しいです。なぜなら、ログをキャプチャするための特定のログバケットを作成すると、使用状況メトリクスを保持して分析することができ、問題を発見することができるからです。
* Cloud Logging と Cloud Monitoring はデフォルトですでに有効になっているため、D は正しくありません。
 
https://cloud.google.com/stackdriver/docs/solutions/gke/managing-logs
 
https://cloud.google.com/logging/docs/buckets
 
https://cloud.google.com/kubernetes-engine/docs/how-to/ingress-features
</pre></div></details>

## Q.  18
新しい VPC を作成し、今後の Compute Engine アプリケーションで使用するファイアウォールを構成しました。アプリケーションをデプロイした後、既存の Compute Engine インスタンスが新しい VPC のリソースに接続できないことに気付きました。この問題の原因は何でしょうか?

1. Policy Troubleshooter API を有効にしませんでした。
2. 接続を許可するために共有 VPC を有効にしませんでした。
 3. 接続を許可するために VPC ネットワークをピアリングしませんでした。
4. 新しい VPC が既存の VPC と同じリージョンに作成されていない。
<details><div><pre style="line-height: 1.2;">
    答え：3. 接続を許可するために VPC ネットワークをピアリングしませんでした。

* Policy Troubleshooter API を有効にすると IAM ポリシーのトラブルシューティングはできますが、2 つの異なるネットワーク間で VPC を共有できなくなるため、A は正しくありません。
* 共有 VPC では VPC ネットワークを他の Google Cloud プロジェクトと共有できるが、2 つの異なるネットワーク間で VPC を共有できないため、B は正しくありません。
* VPC ピアリングを使用すると、2 つの異なるネットワーク間で VPC を共有できるため、C は正しいです。
* Dは正しくありません。VPC がピアリングされていない場合、リソースが同じリージョンにあっても、別々の VPC 内のリソースは相互に通信できません。
 
https://cloud.google.com/vpc/docs/vpc-peering
</pre></div></details>

## Q.  19
会社には、Google Cloud で独自のプロジェクトやリソースを作成、管理する複数の社内チームがあります。最近の脆弱性レポートで不審なネットワーク アクティビティが明らかになった後、マネージャーは Google Cloud サービスのネットワーク使用状況を保護し、監視したいと考えています。Google が推奨するプラクティスに従って、特定の API リクエストに基づく外部イングレス VPC トラフィックのみを許可する必要があります。あなたは何をすべきか?

1. 新しい VPC ファイアウォール ルールを設定して、必要な Google サービスへのサービス アカウント アクセスを拒否します。
2. 既存の組織の階層型ファイアウォールを作成し、IP アドレスに基づいてエグレス トラフィックを許可する新しいルールを追加します。
3. VPC Service Controls を強制モードにして、既存の組織のサービス境界を作成します。必要な Google サービスを許可するように、新しい上り(内向き)ポリシーを設定します。監査ログを確認して、トラフィック フローを確認します。
4. VPC Service Controls をリハーサルモードにして、既存の組織のサービス境界を作成します。新しい下り(外向き)ポリシーを設定して、必要な Google Cloud サービスへのアクセスを許可します。監査ログを確認して、トラフィック フローを確認します。
 
<details><div><pre style="line-height: 1.2;">
    答え：4.

* サービス アカウントで VPC ファイアウォール ルールを設定すると、IPv4 または IPv6 接続でのアクセスのみが許可または拒否され、Google サービスの特定の API ではアクセスが許可されないため、A は正しくありません。
* 階層型ファイアウォールを作成する目的は、IPv4 または IPv6 接続からの接続を許可または拒否することであるため、B は正しくありません。
* 強制モードの VPC Service Controls は、最初にテストせずにポリシーを自動的に適用し、内部入力ポリシーを設定しても外部 API アクセスは提供されないため、C は正しくありません。
* VPC Service Controls を使用してサービス境界を作成すると、VPC の内部と外部から Google サービスへのアクセスを制御できるため、D は正しいです。強制モードを使用する前に、ポリシーをドライランモードでテストすることをお勧めします。
 
https://cloud.google.com/vpc-service-controls/docs/overview#isolate
 
https://cloud.google.com/vpc-service-controls/docs/create-service-perimeters
 
https://cloud.google.com/vpc-service-controls/docs/vpc-accessible-services
 
https://cloud.google.com/vpc-service-controls/docs/troubleshooting
</pre></div></details>

## Q.  20
金融機関は、オンプレミス ネットワークと同じレベルのネットワーク パフォーマンスを維持しながら、5 PB のデータを Google Cloud に移行する必要があります。十分な容量とフェイルオーバー保護を提供する費用対効果の高いCloud Interconnect接続を設定する必要があります。あなたは何をすべきか?

1. us-central1 でデュアル 10 Gbps VLAN アタッチメントをプロビジョニングします。
2. us-central1 で 1 つの 50 Gbps VLAN アタッチメントをプロビジョニングします。
3. 2 つの異なるエッジ可用性ドメインにデュアル 50 Gbps VLAN アタッチメントをプロビジョニングします。
4. 2 つの異なるエッジ可用性ドメインにデュアル 10 Gbps VLAN アタッチメントをプロビジョニングします。
<details><div><pre style="line-height: 1.2;">
    答え：4. 2 つの異なるエッジ可用性ドメインにデュアル 10 Gbps VLAN アタッチメントをプロビジョニングします。

* フェイルオーバー保護のために2つの異なるエッジ可用性ドメインが必要なため、Aは正しくありません。
* B は、1 つの 50 Gbps VLAN アタッチメントでは十分な容量やフェイルオーバー保護を提供できないため、正しくありません。2つの異なるエッジ可用性ドメインが必要です。
* 50 Gbps の VLAN アタッチメントを使用することは最もコスト効率の高いオプションではないため、C は正しくありません。
* Google が推奨するプラクティスは、Cloud Interconnect 接続と VLAN 接続容量をプロビジョニングして、各エッジ可用性ドメインがすべての本番環境ワークロードに十分な容量を持つようにすることであるため、D は正しいです。
 
https://cloud.google.com/network-connectivity/docs/interconnect/concepts/best-practices#scenario_1_sufficient_capacity

</pre></div></details>
