# DNS

## DNSとは

DNS（Domain Name System）：ドメイン名とIPアドレスを変換するためのシステム

名前解決：ドメイン名→IPアドレスへの変換

権威サーバー：ドメイン名とIPアドレスの対応表を持っているサーバー

## キャッシュ

名前解決をより高速に行うためにキャッシュできる

以下のような方法がある：

- キャッシュサーバーを置く
- ブラウザでキャッシュ

## DNSレコード

### Aレコード

Aレコード：ドメインとIPアドレスの対応

１ドメインに対して複数IPアドレスを持つことができる →　複数IPに順番にアクセスすることで負荷分散（DNSラウンドロビン）

e.g. ELB

### SPFレコード

SPFレコード：ドメインの管理者が作成するテキストデータ。メール送信を許可されているサーバーを表現

SMTP（サーバー間でメールを送るプロトコル）では差出人を偽装できる
→ SPFによって送信者を保証し、なりすまし等を防止

[SendGrid 送信ドメインを認証するためのSPFレコードに詳しくなろう](https://sendgrid.kke.co.jp/blog/?p=3509&utm_source=google&utm_medium=cpc&utm_content=text&utm_campaign=dsa&gclid=CjwKCAjwi8iXBhBeEiwAKbUofYplJ_rSoSrq9DFnGCLVUwCshu4YpoMHsPQvf0QjlKy-cDmbkFIJCRoCIXQQAvD_BwE)
