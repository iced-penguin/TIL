色々な記事があるが、公式に従う：

[removal | npm Docs](https://docs.npmjs.com/cli/v7/using-npm/removal)

※ 上の記事はv7についてのものなので適宜バージョンを選択すること

基本的にはこれでOK

```
sudo npm uninstall npm -g
```

ダメだった場合は次のコマンドを試す

```
rm -rf /usr/local/{lib/node{,/.npm,_modules},bin,share/man}/npm*
```

アンインストールできたら、次のコマンドを打っても`npm not found`のようなメッセージが表示されるはず
```
npm -v
```
