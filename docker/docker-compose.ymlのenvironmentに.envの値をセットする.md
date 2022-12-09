# docker-compose.ymlのenvironmentに.envの値をセットする

`.env`

```
NAME="Tarou"
```

上記の値を読み込みたいとする。


次のように書くと`.env`で上書きされず、`NAME`に`Jirou`がセットされてしまう。

**書式1**

`docker-compose.yml`

```yaml
environment:
  NAME: "Jirou"
```

これを避けるため、次のように書く。

**書式2**

`docker-compose.yml`

```yaml
environment:
  NAME: "${NAME:-Jirou}"
```

書式：`${環境変数名:-デフォルト値}`または`${環境変数名}`

`.env`に記述がない場合はデフォルト値が採用される。

いずれの場合もシェルの環境変数で上書きされる。
例えば、次のようにシェルに環境変数をセットしてdockerコンテナを起動すると`Saburou`が読み込まれる。

```
export NAME=Saburou
```

書式2で書いた場合の優先順位をまとめると

1. シェル環境変数
2. `.env`
3. `docker-compose.yml`のデフォルト値
