# ngrok の利用方法

## ngrokとは？
ngrok（エングロック）を使うと、Webhook を利用するための publicURL を発行できる。
簡易的にセキュアな URL をローカルホストサーバーに NAT や Firewall を通して構築することが可能となる。

## ngrok のメリット
1. デモサイトをデプロイせずに試すことが出来る
2. 開発環境でwebhookを試す事が出来る
3. モバイルappのバックエンドサービスをテストを出来る。
4. httpだけではなくhttps通信可能

## ngrokの使い方

### インストール
```console
scoop install ngrok
```

### 実行
ローカルの開発サーバを起動しておく。

ローカルサーバの例（API ドキュメント）:
```
http://localhost:8080/swagger-ui/index.html
```

ngrok コマンドを実行する。
```console
ngrok http 8080
```
実行例:
```
ngrok by @inconshreveable                                                                              (Ctrl+C to quit)                                                                                                                       Session Status                online                                                                                   Session Expires               7 hours, 55 minutes                                                                      Version                       2.3.35                                                                                   Region                        United States (us)                                                                       Web Interface                 http://127.0.0.1:4040                                                                    Forwarding                    http://{Unique ID}.ngrok.io -> http://localhost:8080                                    Forwarding                    https://{Unique ID}.ngrok.io -> http://localhost:8080                                                                                                                                                          Connections                   ttl     opn     rt1     rt5     p50     p90                                                                            6       0       0.01    0.01    32.25   70.61                                                                                                                                                                   HTTP Requests                                                                                                          -------------                                                                                                                                                                                                                                 GET /v2/api-docs                              200  
```

### アクセス
httpの場合（例）:  
```
http://1fd2ec17.ngrok.io
```

https の場合
```
https://1fd2ec17.ngrok.io
```

まとめ
簡単にローカル環境をhttp/httpsで外部公開できるので、webhookURLで本当にhttps受信できるのか確認したりする時に便利です。あと、デモサイトを外部に一時的に見せるときとかにも便利です。
