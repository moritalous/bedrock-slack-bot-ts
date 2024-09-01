# bedrock-slack-bot-ts

## 事前準備

* SAM CLIのインストール

```shell
curl -L "https://github.com/aws/aws-sam-cli/releases/latest/download/aws-sam-cli-linux-x86_64.zip"  -o "aws-sam-cli-linux-x86_64.zip"
unzip aws-sam-cli-linux-x86_64.zip -d sam-installation
sudo ./sam-installation/install
```

* AWSの認証情報のセット

```shell
aws configure
```

## デプロイ

```shell
sam build
sam deploy --guided
```

## ローカル環境での動作確認

`env.json.sample`を参考に`env.json`を作成してください。
次のコマンドを実行してください。

```shell
sam build
sam local start-api --env-vars env.json
```

```shell
curl -XPOST localhost:3000/slack/events -H "Content-Type: application/json" -d '{}' -v
```

Pinggyでlocalhostをトンネルします。

```shell
ssh -p 443 -R0:localhost:3000 a.pinggy.io
```

## Slack側の設定

（準備中）
