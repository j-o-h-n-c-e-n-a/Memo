## 4つのケーススタディ
### 1. 
### 2. 
### 3．
### 4．
### メルカリ
    https://cloud.google.com/blog/ja/topics/customers/google-cloud-platform-mercari-kubernetes


## 参考資料
* [Google Cloud ソリューション](https://cloud.google.com/solutions/?hl=ja)
* [ドキュメント](https://cloud.google.com/docs/?hl=ja)
* [Professional Cloud Architect](https://cloud.google.com/certification/practice-exam/cloud-architect)
* [AWSプロフェッショナルのためのGCP](https://cloud.google.com/docs/compare/aws/?hl=ja)
* [Azure プロフェッショナルのためのGCP](https://cloud.google.com/docs/compare/azure/?hl=ja)
* [CloudOnAir](https://inthecloud.withgoogle.com/jp-onair-19/archive.html)
* [codelabs](https://codelabs.developers.google.com/)
* [GCPUG](https://gcpug.jp/about)
* [1 行でわかる Google Cloud Platform](https://lp.google-mkto.com/rs/248-TPC-286/images/GCP_clearfile_A4_for_PaperPrint.pdf)
* [topgate](https://www.topgate.co.jp/gcp07-how-to-start-docker-image-gke)
* [tech-run](https://www.tech-run.net/ja/contents/gke)
* []()

### Qwiklabs
    ラボ用のユーザーIDとパスワードでログインする
* [](https://google.qwiklabs.com/focuses/1734?locale=ja&parent=catalog)
* [](https://google.qwiklabs.com/catalog?format%5B%5D=courses&utm_source=cloud-dot-google&utm_medium=website)

### coursera
* [coursera_1](https://www.coursera.org/learn/gcp-fundamentals-aws)
* [coursera_2](https://www.coursera.org/specializations/gcp-architecture-jp)

* Colaboratory
* Google Research Football Environment

* Cloud Console
* Cloud Identity-Aware Proxy(IAP)


* Android Enterprise
* Cloud Identity
  + https://cloud.google.com/docs/authentication/end-user?hl=ja
1. Googleの「API Console」に自分のアプリを登録
2. 「API Console」でOAuth2認証で必要な情報を集める（Client ID、Client Secret, Redirect URIs）
3. 「OAuth 2.0 Playground」を使って許可範囲（scope）を決定する
4. 集めた情報を使ってWebViewでOAuth2認証ページを表示する
5. OAuth2認証ページでユーザー自身でアプリケーションからの接続の許可をしてもらう
6. ユーザー許可後のページタイトルから「code」を取得する
7. 「code」を使って「アクセストークン」を取得する
