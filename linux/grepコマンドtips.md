# grep

## 構文

```bash
# ファイル内を検索
grep [オプション] パターン ファイル名 

# 標準入力から検索
grep [オプション] パターン
```

パターンには正規表現を使用できる。

## 大文字と小文字を区別しない

```bash
grep -i パターン ファイル名 
```

## 特定ディレクトリ配下のファイルをgrep

```bash
grep パターン -rl ディレクトリ
```

## 正規表現にマッチする部分を抜き出す

```
grep -o '正規表現'
```

## 行番号を表示

```
grep -n パターン
```

## ２ファイルの共通行を抽出

```
grep -xif file1 file2
```
