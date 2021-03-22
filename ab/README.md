# ab - Apache HTTP server benchmarking tool

## 正式名称

Apache HTTP server benchmarking tool

## 公式ドキュメント

https://httpd.apache.org/docs/2.4/programs/ab.html

## インストール方法

+ Ubuntu

```
sudo apt update
sudo apt install apache2-utils
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

## 事前にやっておくこと

ファイルディスクリプタの上限を引き上げておく

```
ulimit -n 1024
```

+ ファイルディスクリプタの設定値の確認

```
ulimit -a
```
```
### Ex.

# ulimit -a | grep files
open files                      (-n) 1024
```

+ `fs.nr_open` 1プロセスが開ける上限の確認

```
sysctl fs.nr_open
```
```
### Ex.

# sysctl fs.nr_open
fs.nr_open = 1048576
```

+ `fs.file-max` システム全体の上限の確認

```
sysctl fs.file-max
```

+ ファイルディスクリプタの設定値を `1プロセスが開ける上限` まで増やす

```
ulimit -n 1048576
```
```
# ulimit -a | grep files
open files                      (-n) 1048576
```


## 参考

https://qiita.com/takc923/items/238597a53a2328025b09
