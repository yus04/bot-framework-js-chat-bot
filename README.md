# chat-bot
このリポジトリは、Bot Framework を使ったボット開発のテンプレートです。

## 前提条件
- Azure App Service が Node ラインタイムでデプロイされているものとする。

## 手順
ここではボットのテンプレートの作成手順と、ボットのローカル実行、Azure App Service へのデプロイ手順をまとめます。
本リポジトリのコードをそのまま利用する場合は、テンプレートの作成手順はスキップしてください。

### テンプレートのボット作成
```
npm install -g npm
npm install -g yo
npm install -g generator-botbuilder
yo botbuilder
```

### テンプレートのボットをローカル実行
```
cd chat-bot
npm start
```

### テンプレートのボットを App Service にデプロイ
```
cd chat-bot
zip -r ../deploy.zip .
cd ..
az webapp deployment source config-zip --resource-group ＜Resource Group Name＞ --name ＜App Service Name＞ --src ./deploy.zip
```

### (参考) デプロイされたボットのテスト
- Azure ポータルの「Web チャットでテスト」でボットとのやり取りが可能です。
- Teams 等のチャンネルと接続すれば、ボットとのやり取りを接続先でも可能です。