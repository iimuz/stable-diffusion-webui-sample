---
title: Automatic1111/stable-diffusion-webuiの利用スクリプト
date: 2023-09-19
lastmod: 2023-12-31
---

## 概要

[Automatic1111/stable-diffusion-webui](https://github.com/AUTOMATIC1111/stable-diffusion-webui)を利用するためのスクリプトや実行方法に関するメモとなります。

## フォルダ構成

このフォルダに automatic1111 を git clone して環境構築することを想定してスクリプトを記載します。

- .gitignore
- README.md
- stable-diffusion-webui/: クローンしたリポジトリのフォルダ。ただし、.gitignore で設定されているため何もコミットされない。

## 実行方法

taskを利用して実行コマンドを記載します。代表的なコマンド以外は、`task -l`で確認してください。

- 環境構築: `task init`
- サーバーの起動: `task webui`
  - 初回起動時にサーバー環境の構築を行います。

## Tips

### Windows 環境における scoop を利用したバージョン設定

scoop を利用してバージョン管理する場合は下記のようにして利用するバージョンを設定する。

```sh
scoop reset python310
scoop reset cuda11.6
```

### 生成した画像の保存場所

生成した画像は`stable-diffusion-webui/output`の場所に保存されている。
