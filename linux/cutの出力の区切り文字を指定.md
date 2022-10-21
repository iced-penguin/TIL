# cutの出力の区切り文字を指定

Macを使用しているが、cutコマンドの標準出力に区切り文字を指定したい

BSD系であるMacのcutでは指定できないようなので、GNU版をインストールして使う

```
brew install coreutils
which gcut
```

gcut コマンドでGNU版cutが使用できる

出力の区切り文字を指定するには以下のようにする

```
cat sample.txt | gcut -f 1,2 --output-delimiter=','
```

csvファイルを作るときなどに便利
