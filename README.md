# ubuntu-docker-cloud-config

> Docker の動く Ubuntu をセットアップする cloud-config ファイルです

## 想定環境

- Cloud-init をサポートしている VPS
- メモリは 1 GB（1 GB 以外の場合はスワップを変更する）
- OS は Ubuntu 24.04
- ユーザーは ubuntu を使用、SSH キーは VPS のサービスのコンソールから登録する

## ローカルで試す

[Multipass](https://github.com/canonical/multipass) を使います。

```sh
# 立ち上げる
multipass launch --name ubuntu-docker --memory 1G --disk 20G --cpus 1 --cloud-init cloud-config.yml 24.04

# 接続する
multipass shell ubuntu-docker

# 起動する
multipass start ubuntu-docker

# 停止する
multipass stop ubuntu-docker

# 削除する
multipass delete ubuntu-docker

# 完全に削除する
multipass purge

# その他
multipass -h
```
