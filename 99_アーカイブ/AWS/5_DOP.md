## 1: SDLCの自動化


CI/CD

CodeCommit
Jenkins

CodeBuild

CodeDeploy
    ColudFormation
    Beanstalk
    OpsWprks

CodePipeline
    ソース
        S3
        CodeCommit
        GitHub
    ビルド
        CodeBuild
    テスト
        CodeBuild
        Jenkins
    デプロイ
        CodeDeploy
    コール
        Lambda
    サブミット
        SNS

テスト
    単体テスト
    結合テスト
    回帰テスト
    負荷テスト

## 2: 設定管理とIaC
IaC
システム更新
    カナリア
    B/Gデプロイ

OpsWorks
    Chef
    Puppet

コンテナ
    ECS、ECR

API Gateway

## 3: モニタとロギング

## 4: ポリシーと標準の自動化
Inspecter

Config

コスト最適化
    Trusted Advisor

コンプライアンス
    Service Catalog

## 5: インシデントとイベントレスポンス

## 6: 高可用性、耐障害性、災害対策
