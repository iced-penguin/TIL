# Lamabdaユースケース

## トリガー：SQS

SQSをLambda関数のトリガーに設定

* LambdaはSQSキューをポーリングし、メッセージを処理する
* Lamdbaの処理が正常に実行されるとメッセージはキューから削除される

[Amazon SQS での Lambda の使用](https://docs.aws.amazon.com/ja_jp/lambda/latest/dg/with-sqs.html)

## 定期実行

EventBridgeで一定の間隔で実行するようスケジュールされたルールを作成し、Lambda関数のトリガーに設定

EventBridgeの定期実行ルールはcron式またはrate式によって定義できる。ルールの作成方法は[こちら](https://docs.aws.amazon.com/ja_jp/eventbridge/latest/userguide/eb-create-rule-schedule.html)
