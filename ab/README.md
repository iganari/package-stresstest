# ab - Apache HTTP server benchmarking tool

## 正式名称

Apache HTTP server benchmarking tool

## 公式ドキュメント

https://httpd.apache.org/docs/2.4/programs/ab.html

## インストール方法

+ Ubuntu

```
apt update
apt install apache2-utils
```

## 基本的な使い方

+ n オプション
    + 生成するリクエスト数を指定します
+ c オプション
    + 並列実行する数（コネクション数）を指定します

たとえば、「10ユーザがそれぞれ10回リクエストした場合」をシミュレートしたいときは、次のようなコマンドを発行します。

```
ab -n 100 -c 10 http://example.com/
```

## よく使うオプション

WIP

## 例

WIP
