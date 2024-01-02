---
title: Automatic1111/stable-diffusion-webuiの利用スクリプト
date: 2023-09-19
lastmod: 2024-01-02
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

### Dynamic prompt

プロンプトをランダムに変更できる拡張機能。
どのようなプロンプトにするか考えられないときや、てきとうにくっつけて変化を見たいときに使える。

以下のURLをExtensionの"Install from URL" -> "URL from extension's git repository"から設定する。

- <https://github.com/adieyal/sd-dynamic-prompts.git>

完全ランダムなプロンプト作成をする場合は、下記のように設定する。

- "Dynamic Prompts enabled"を有効化
- "Prompts Magic" -> "Magic prompt"を有効化

以下は設定値の説明。

- Max magic prompt length: プロンプトの最大長
- Magic prompt blocklist regex: 除外したいプロンプト

### Stable diffusion XL

Stable Diffusion XLを利用するためには下記のようなデータをダウンロードして設定すればよい。

- [Hugging Face - stable-diffusion-xl-base-1.0](https://huggingface.co/stabilityai/stable-diffusion-xl-base-1.0/tree/main)
  - `models/Stable-diffusion`に保存する。
- [Hugging Face - stable-diffusion-xl-refiner-1.0](https://huggingface.co/stabilityai/stable-diffusion-xl-refiner-1.0/tree/main)
  - `models/Stable-diffusion`に保存する。
- [Hugging Face - sdxl-vae](https://huggingface.co/stabilityai/sdxl-vae/tree/main)
  - `models/VAE`に保存する。
  - "Settings" -> "VAE"から設定する。
  - VAEの設定については、"Settings" -> "User Interface" -> "Quick settings list"で"sd-vae"をリストに追加することでtext2imgのタブに出現させられる。
