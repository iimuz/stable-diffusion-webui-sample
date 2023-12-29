---
title: Automatic1111/stable-diffusion-webuiの利用スクリプト
date: 2023-09-19
lastmod: 2023-12-29
---

## 概要

[Automatic1111/stable-diffusion-webui](https://github.com/AUTOMATIC1111/stable-diffusion-webui)を利用するためのスクリプトや実行方法に関するメモとなります。

## フォルダ構成

このフォルダに automatic1111 を git clone して環境構築することを想定してスクリプトを記載します。

- .gitignore
- README.md
- stable-diffusion-webui/: クローンしたリポジトリのフォルダ。ただし、.gitignore で設定されているため何もコミットされない。

## 実行方法

WebUI を起動するためには、環境構築が完了して以降は下記のように実行するとサーバーが立ち上がる。

```sh
cd ./stable-diffusion-webui
./webui-user.bat
```

## 環境構築方法

(Windows 環境の場合)

```sh
git clone https://github.com/AUTOMATIC1111/stable-diffusion-webui.git
cd ./stable-diffusion-webui
git switch -c v1.7.0 tags/v1.7.0
./webui-user.bat
```

## Tips

### Windows 環境における scoop を利用したバージョン設定

scoop を利用してバージョン管理する場合は下記のようにして利用するバージョンを設定する。

```sh
scoop reset python310
scoop reset cuda11.6
```

### 生成した画像の保存場所

生成した画像は`stable-diffusion-webui/output`の場所に保存されている。
