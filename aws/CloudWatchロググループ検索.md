# CloudWatchロググループを検索する

※CloudWatch Logs insights ではない

[Amazon CloudWatch Logs - フィルターとパターンの構文](https://docs.aws.amazon.com/ja_jp/AmazonCloudWatch/latest/logs/FilterAndPatternSyntax.html)

## 文字列検索

### 除外

除外する語句にハイフンを付与

```
ERROR -ARGUMENTS
```

## JSON形式のログを検索

### キーを指定

`$.`にキー名をつづけることで特定のキーの値をもつログを検索できる

```
{ $.status = "500" }
```

### ワイルドカード

アスタリスクを利用してワイルドカード検索が可能

```
{ $.status = "5*" }
```

### 複数条件

`&&` でAND検索、`||`でOR検索

```
{($.status = "500") && ($.uri = "/api/user)}
```
