# stress コマンド

## インストール

+ Debian

```
apt update
apt install stress
```

+ Alpine

```
apk update
apk add stress-ng
```

## 使い方

+ `-q`
    + 起動メッセージを表示しないようにするオプション

### CPU負荷(-c)

+ stressコマンド実行

```
stress -c 1 -q &
```
```
### Ex.

# stress -c 1 -q &
[1] 372
```


+ プロセスの状態確認

```
ps -C stress -o comm,pid,ppid,%cpu,psr,wchan
```
```
### Ex.

# ps -C stress -o comm,pid,ppid,%cpu,psr,wchan
COMMAND             PID    PPID %CPU PSR WCHAN
stress              372      21  0.0   1 do_wait
stress              373     372 79.5   0 -
```

+ コマンドの強制終了

```
pkill stress
```
```
### Ex.

# pkill stress
[1]-  Terminated              stress -c 1 -q
[2]+  Terminated              stress -c 1 -q
```

## 参考

https://qiita.com/hana_shin/items/b1d8cd559d1a326f4d42
