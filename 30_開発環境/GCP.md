* [Google Cloud ソリューション](https://cloud.google.com/solutions/?hl=ja)
* [ドキュメント](https://cloud.google.com/docs/?hl=ja)
* [Professional Cloud Architect](https://cloud.google.com/certification/practice-exam/cloud-architect)
* [1 行でわかる Google Cloud Platform](https://cloud.google.com/blog/ja/products/gcp/google-cloud-platform-paperprint?utm_source=feedburner&utm_medium=feed&utm_campaign=Feed:%2BGoogleCloudPlatformJapanBlog%2B(Google%2BCloud%2BPlatform%2BJapan%2BBlog))


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