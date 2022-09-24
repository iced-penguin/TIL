# AWS CLI
aws cli コマンドの使い方。増えてきたら分割。

## 設定

接続設定情報をプロファイルというらしい。

aws cli コマンドを使用するために最初にデフォルトのプロファイルを設定する必要がある。

### 必須：デフォルトのプロファイルを設定

```bash
$ aws configure
AWS Access Key ID [None]: xxxxxxxxxxxxxxxx
AWS Secret Access Key [None]: xxxxxxxxxxxxxxxxxxxxxxx
Default region name [None]: ap-northeast-1 
Default output format [None]: 
```

アクセスキーID、シークレットアクセスキー、リージョンを入力。フォーマットはそのままでOK。

### オプション：プロファイル切り替え

以下のコマンドを実行してプロファイルを作成

```bash
aws configure --profile hoge-profile
```

各プロファイルの設定は`~/.aws/config`

作成したプロファイルを使用してaws cli コマンドを実行するには次のようにする：

```bash
aws s3 ls --profile hoge-profile
```

## S3

### —dryrun

`—dryrun`オプション：コマンドを実際には実行せず、シミュレーション

対象コマンド：cp, mv, rm sync

### ls

アクセスできる全バケット

```bash
aws s3 ls
```

特定パス直下のオブジェクト一覧

```bash
aws s3 ls s3://mybucket
aws s3 ls s3://mybucket/hoge/
```

特定プレフィックス（擬似的なディレクトリ）以下を再帰的に検索（子孫プレフィックス配下も表示）

```bash
aws s3 ls s3://mybucket/hoge/ --recursive
```

### cp

ファイルアップロード

```bash
aws s3 cp hoge.txt s3://mybucket/hoge/
```

ファイルダウンロード

```bash
aws s3 cp s3://mybucket/hoge/hoge.txt ./hoge.txt
```

フォルダごと一括ダウンロード

```bash
aws s3 cp s3://mybucket/hoge/ ./hoge --recursive
```
