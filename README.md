# ffmpeg

## 概要
ffmpeg をインストールする ansible role

## 動作確認バージョン

- Ubuntu 18.04 (bionic)
- ansible >= 2.8
- Jinja2 2.10.3

## 使い方 (ansible)

```yaml
- hosts:
    - servers
  become: True
  roles:
    - { role: ffmpeg, tags: ["ffmpeg"] }
```

## 各種変数について
Comming soon.