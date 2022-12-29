# ログインせずにSQLを実行

#DB #MySQL

## SQLを直接指定する方法

`-e` オプションを使う

```sh
mysql -u ユーザー名 -h ホスト名 -p -e "sql statement"
```

結果をファイルに保存したい時はリダイレクト

```sh
mysql -u user_name -h host_name -p -e "sql statement" > file_name
```

## SQLファイルを指定する方法

```sh
mysql -u ユーザー名 -h ホスト名 -p < sql_file
```

## 参考

[MySQLコマンドラインでSQLを実行する - Qiita](https://qiita.com/redpanda/items/0b0729cb07ba6bea6340)
