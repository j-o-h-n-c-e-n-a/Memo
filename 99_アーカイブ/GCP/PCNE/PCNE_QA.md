### 問1-18
単一のサブネットを持つ Dev という名前の新しい VPC ネットワークを作成しました。ネットワーク開発者に HTTP トラフィックのみを許可するファイアウォール ルールを追加し、ログ記録を有効にしました。リモート デスクトップ プロトコルを介してサブネット内のインスタンスにログインしようとすると、ログインは失敗します。 Stackdriver Logging でファイアウォール ルールのログを探しますが、ブロックされたトラフィックのエントリが表示されません。ブロックされたトラフィックのログを確認したいとします。あなたは何をするべきか？
* A. インスタンスの VPC フロー ログを確認します。
* B. SSH 経由でインスタンスに接続してみて、ログを確認します。
* C. ポート 22 からのトラフィックを許可する新しいファイアウォール ルールを作成し、ログを有効にします。
* D. 優先度 65500 の新しいファイアウォール ルールを作成して、すべてのトラフィックを拒否し、ログを有効にします。
<details><div><pre style="line-height: 1.2;">
A. インスタンスの VPC フロー ログを確認します。 これが最も適切な選択肢です。

* 理由：
    * VPC フローログ: VPC 内のネットワークトラフィックに関する詳細な情報を提供します。ファイアウォールで許可または拒否されたトラフィック、ソース/宛先IPアドレス、ポート、プロトコルなど、多岐にわたる情報がログとして記録されます。
    * ファイアウォールログ: ファイアウォールルールそのものの適用状況やエラーログなどが主であり、必ずしも個々のパケットの許可/拒否状況が詳細に記録されるとは限りません。
    * リモートデスクトップ: 一般的にTCPポート3389を使用します。HTTPトラフィックのみを許可しているため、このポートに対するトラフィックは当然ブロックされます。
    * ログが見つからない理由: ファイアウォールログでは、意図したとおりにHTTPトラフィックのみが許可されているという結果しか表示されない可能性があります。
* B. SSH 経由でインスタンスに接続してみて、ログを確認します: SSHは別のプロトコルを使用するため、問題解決には繋がりません。
* C. ポート22からトラフィックを許可する新しいファイアウォールルールを作成し、ログを有効にします: 問題解決にはつながりますが、HTTPトラフィックのみを許可するという当初の目的から外れてしまいます。
* D. 優先度65500の新しいファイアウォールルールを作成して、すべてのトラフィックを拒否し、ログを有効にします: すべてのトラフィックを拒否してしまうため、問題解決には繋がりません。また、ネットワークが利用できなくなる可能性があります。
</pre></div></details>

### 問2-32
トラフィックを検査するためにサードパーティの次世代ファイアウォールを使用しています。送信トラフィックをファイアウォールにルーティングするカスタム ルート 0.0.0.0/0 を作成しました。パブリック IP アドレスを持たない VPC インスタンスが、ファイアウォールを介してトラフィックを送信せずに BigQuery および Cloud Pub/Sub API にアクセスできるようにしたいと考えています。どの 2 つのアクションを取る必要がありますか? (2つお選びください。)
* A. サブネット レベルで限定公開の Google アクセスをオンにします。
* B. VPC レベルで限定公開の Google アクセスを有効にします。
* C. VPC レベルでプライベート サービス アクセスをオンにします。
* D. デフォルトのインターネット ゲートウェイ経由で Google API およびサービスの外部 IP アドレスにトラフィックを送信するためのカスタム静的ルートのセットを作成します。
* E. デフォルトのインターネット ゲートウェイ経由で Google API およびサービスの内部 IP アドレスにトラフィックを送信するためのカスタム静的ルートのセットを作成します。
<details><div><pre style="line-height: 1.2;">
C,E

* A. サブネット内のインスタンスがGoogleサービスにアクセスできるようになりますが、VPC全体の制御が難しくなります。
* B. VPC内のすべてのインスタンスがGoogleサービスにアクセスできるようになりますが、ファイアウォールを経由せずに直接アクセスできるようになるわけではありません。
* C. VPC内のインスタンスが、プライベートIPアドレスを使用してGoogleサービスに直接アクセスできるようになります。ファイアウォールを経由せずにアクセスするため、パフォーマンスが向上し、セキュリティも強化されます。
* D. Googleサービスの外部IPアドレスは頻繁に変更されるため、この方法は推奨されません。
* E. Googleサービスの内部IPアドレスは比較的安定しており、この方法を使用することで、ファイアウォールを経由せずにGoogleサービスにアクセスできます。
</pre></div></details>
