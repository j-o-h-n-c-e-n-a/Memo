### 新機能
#### vCenter Server 
* アプライアンス（VCSA）
    + Photon OS(Linux)
    + キャパシティ(ホスト数、仮想マシン数)は6.0の約2倍
    + vSphere Update Manager, Auto Deploy, Host Profilesの機能を統合
* バックアップ・リストア
    + ファイルベースで実行可能
* 可用性の向上
    + vCenter HA
* 多要素認証ログイン
    + SSO
* vCenter間の連携
    + Platform Services Controller(PSC)
        - 外部構成
        - 組込構成
    + 異なるバージョンの連携はサポート外(vMotionなどができない)
#### Web ClientのHTML5対応
#### REST API
#### 自動化インターフェイスについて
#### ESXi
* 論理CPUを400⇒576個、物理メモリを最大12TBまで拡張し、ホストあたり最大1024 VM（vCPU 合計4096個）までサポート
* 仮想ハードウェアバージョン13は、4096⇒6128GBメモリまで拡張を可能とすると共に、NVMe対応のストレージをサポート
* 新たなファイルシステムであるVMFS 6は512バイトエミュレーションをサポートし、ストレージの容量効率、可用性ならびにパフォーマンスを向上
#### ストレージの機能強化
#### ネットワークの機能強化
* Cross-CloudなVM移行機能（Cross-Cloud vMotion）
    + オンプレ-オフプレクラウド間のvMotionに対応
* vSphere Network I/O Control バージョン 3
    + 参考：     https://docs.vmware.com/jp/VMware-vSphere/6.0/com.vmware.vsphere.networking.doc/GUID-98E0B3C2-52A7-4CAB-A839-4DA82A9F6D3A.html
    + https://blogs.vmware.com/jp-cim/2018/07/vexpert-nakagawa-vmware-vs-part6-html.html

#### セキュリティ
* 仮想マシンの暗号化（VM Encryption）
    + VMを暗号化
    + VMotionの通信暗号化
    + 暗号化キーの管理サーバー(KMS)の障害後、KMSへ接続がない間は暗号化VMは起動できない
* セキュアブート(UEFI)
    + ブートイメージの改ざん防止
* ログ機能の強化
    + セキュリティ監査にも対応（誰が、何を、どこで、何時実行したかを追跡可能）
* 仮想マシンサンドボックス
#### 可用性の向上
* Proactive HAの機能
    + 各ハードウェアベンダーが提供している専用の監視ソフトウェアと連携。ハードウェア障害の兆しを事前に察知した場合、影響範囲にある仮想マシンをvMotionで健全なホストに移動（VM稼働時間の最大化）
    + DRSの有効化が必要（Enterprise Plusのライセンスが必要）
* Predictive DRSの機能
    + リソース使用率の急上昇が発生する前に、仮想マシンのワークロードのバランスをとる
    + 実行されるしきい値のアルゴリズムに基づいてリソースの使用率を調整
#### vSphere Web Client
* 従来のvSphere Client はサポート廃止
#### VMware vSphere Integrated Containers
* Docker サポート
#### vSphere 6.5 へのバージョンアップ
* vSphere Update Manager
* ConverterによるP2Vやマイグレーション要件
* vCenter Server Appliance Migration Tool
    + 既存のvCenter Server からVCSAへの移行およびアップグレード
* アップグレードベースライン
    + 参考：https://www.school.ctc-g.co.jp/vmware/columns/noda/noda35.html
#### 参考サイト
* [qiita](https://qiita.com/ymunemasa/items/039fc1ba330e133a8176)
* [IT価値創造塾](https://vmware-juku.jp/solutions/vsphere6-5-offering/)
* [VMware BLOGS](https://blogs.vmware.com/jp-cim/2017/06/vexpert-nakagawa-vmware-vsphere-6-5-part2.html)

### Veeam Backup & Replication
1. アプリケーション対応
    * 独自VSSを利用したバックアップ
2. 柔軟なリカバリ
3. ストレージ連携
* [Veeam Backup & Replication](https://blogs.vmware.com/jp-cim/2018/05/vsan_veeam_backup02.html)

### その他機能
#### VM Component Protection (VMCP)
  データストアでAPLまたはPDLの障害が発生したときに挙動を制御できる
* APL
    + All path down:全パスが切れた場合
* PDL
    + Permanent device loss:LUNがぶっ壊れて認識できなくなった場合など
* 参考：https://kb.vmware.com/s/article/2081089

#### Storage DRS
  ストレージリソースの自動最適化を行う
* 有効となるコンポーネント
    1. データストアクラスタ内のデータストア間の空間負荷分散
    2. ペースおよびI / Oワークロードに基づく仮想ディスクの初期配置
    3. データストアクラスタ内のデータストア間のI / Oロードバランシング
* 参考：http://www.fujitsu.com/jp/products/computing/storage/lib-f/tech/beginner/vmware-sdrs/

#### CPUオーバーコミットメント
  クラスタ内で仮想CPUと物理CPUの比率を設定し、オーバーコミットを制御します。オプションで定義された値に達すると、追加の仮想マシンをパワーオンことはできません。

#### vCenter Converter Standalone
* LinuxマシンはSSHデーモンが起動している必要がある

#### multi-processor Fault Tolerance (SMP-FT)
* vCPUの割り当てが不足していると有効化できない
* 仮想マシンのスナップショットが残っていると有効化できない

#### NPIV（N_Port ID Virtualization）
　1つのHBAに対して複数のID(WWPN)を割り当てることで、1つのHBAポートを複数のHBAポートに見せる ための技術
　RDMのディスクを持つ仮想マシンについて、 アクセス制御, QoSなどのために使われる
* 制限事項
    1. スイッチ側でNPIVを有効化
    2. ホストのHBAがNPIVをサポートしている
    3. 利用できる仮想マシンは、RDMディスクを持つもののみ
    4. 1台の仮想マシンに対して、最大4つの仮想ポートを割り当てられる(つまり、最大4つのWWPNが割り当てられる)

#### AutoDeploy
* PXE(Preboot eXecution Environment)ブートをサポートする必要がある
* TFTPサーバをセットアップして実行する必要があります
* レガシーOSのプロビジョニングにはIPv4アドレスが必要
* ホストのカスタマイズによって固定IPアドレスを提供するため、アドレス割り当てにDHCP予約を使用することは推奨されない
* 参考：http://docs.hol.vmware.com/HOL-2012/HOL-INF-03_JA/HOL-INF-03-m1/lessons/Automate_Your_vSphere_Deployment_with_Auto_Deploy_-_Introduction.html

### ログ
#### vpxa.log
  vCenter ServerとESXi 6.5ホスト間の通信ログ
#### hosted.log
  管理エージェントのログ

### ESXCLIコマンド
* ESXiホストのアップグレードができる

### vSphere 6.7
  
### バージョンアップ
    例えば、vCenter 5.0, ESXi 5.0 から 一気に vCenter 6.5 まであげてしまうとESXi5.0 が管理できなくなる。（一度5.5に引き上げる必要がある。）

* [互換性表](https://www.vmware.com/resources/compatibility/sim/interop_matrix.php)

### 用語集
* NUMA
* vCPU hot add
* vApp と DRS enabled


## 仮想環境
* https://blogs.vmware.com/jp-euc