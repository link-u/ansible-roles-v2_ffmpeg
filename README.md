# ffmpeg

![ansible ci](https://github.com/link-u/ansible-roles-v2_ffmpeg/workflows/ansible%20ci/badge.svg)

## 概要
ffmpeg をインストールする ansible role

## 動作確認バージョン

* Ubuntu: 18.04, 20.04
* ansible: 2.8, 2.9

## 使い方 (ansible)

### Role variables

```yaml
## 基本設定
ffmpeg_install_flag: True ## インストールフラグ
ffmpeg_packages:
  - "ffmpeg-tools"

# ※ 特に group_vars で修正するような項目はない
```

### Example playbook

```yaml
- hosts:
    - servers
  become: True
  roles:
    - { role: ffmpeg, tags: ["ffmpeg"] }
```

## 後方互換性について

### 削除された変数の一覧

以下の変数は ffmpeg をビルドインストールしていたときの名残でです.

現在は弊社の apt リポジトリにビルド済みの ffmpeg の deb パッケージを設置しているため, 
この role 内のビルドに関する変数は削除しました.

そのため以下の変数は `group_vars` から削除して頂いて大丈夫です.

* `ffmpeg_force_install`
* `ffmpeg_prefix`
* `ffmpeg_src_dir`
* `ffmpeg_package`
* `ffmpeg_dl_url`
* `ffmpeg_version`
* `ffmpeg_libraries`
* `ffmpeg_configure_options`
* `ffmpeg_install_dest`
* `nasm_prefix`
* `nasm_src_dir`
* `nasm_install_dest`
* `nasm_version`
* `nasm_package`

## License
MIT
