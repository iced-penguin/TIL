# goenvによるGoバージョン管理

## goenvでGoインストール

### goenv インストール

最初に以下のようにしたが、インストールできるバージョンが少なかった

```
brew install goenv
```

そこで、

```
rm -rf `goenv root`
brew uninstall goenv
git clone https://github.com/syndbg/goenv.git ~/.goenv
```

以下を `.zshrc` に追加して `source ~/.zshrc`

```
export GOENV_ROOT=$HOME/.goenv
export PATH=$GOENV_ROOT/bin:$PATH
export PATH="$GOROOT/bin:$PATH"
export PATH="$PATH:$GOPATH/bin"
eval "$(goenv init -)"
```

### goenvでGoをインストール

```
goenv install 1.13.0
goenv global 1.13.0
```

したが、goのバージョンが変わらず、、

Homebrew ですでに go をインストールしていたためかも

```
$ brew list | grep go
go
gobject-introspection
goenv
golang-migrate
golangci-lint
pango
```

一旦アンインストールしてからgoenvでインストールするとバージョンが変わった

```
$ brew uninstall go
Error: Refusing to uninstall /usr/local/Cellar/go/1.17.5
because it is required by golangci-lint, which is currently installed.
You can override this and force removal with:
  brew uninstall --ignore-dependencies go

$ brew uninstall --ignore-dependencies go
Uninstalling /usr/local/Cellar/go/1.17.5... (10,825 files, 565.8MB)

$ goenv global 1.13.0

$ go version
go version go1.13 darwin/amd64
```

## goenv 使い方

インストール可能なバージョン一覧

```
go install -l
```

インストール済みバージョン一覧

```
goenv versions
```

globalにバージョン設定

```
goenv global <version>
```

goenv アップグレード

```
cd ~/.goenv
git pull
```