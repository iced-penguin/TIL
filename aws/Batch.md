# AWS Batch

## 概要

### AWS Batch とは

full managed バッチ実行サービス

### 概念

ジョブ：バッチの実行単位

ジョブキュー：ジョブの待ち行列。ジョブは投入されるとジョブキューに送信される

## シナリオ

### 定期実行

Cloudwatch Events でスケジュール設定（EventBridgeでもOK？）

ターゲットにBatchを指定

[AWS Batchを使ってcronのような定期的処理を実現する - Qiita](https://qiita.com/tsukasa1301/items/8bd927eaa928ff981414)
