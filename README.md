# 7242

夜空を写真が流れるアルバムサイト。GitHub Pages でホスト（[masato-masa.github.io/7242](https://masato-masa.github.io/7242/)）。

## 画像の追加方法

### サイト上のメニューからアップロード（推奨）

右上の「☰」メニュー →「📷 アップロード」から、スマホ・PC問わずブラウザ上で画像を追加できます。
画像ごとに日付・タイトルを入力して送信すると、GitHub にコミットされてサイトに反映されます。

初回のみ、このリポジトリへの書き込み権限を持つ GitHub の Personal Access Token（Fine-grained、
Repository access をこのリポジトリのみに限定し、Contents を Read and write）の入力が必要です。
入力したトークンはその端末のブラウザ（localStorage）にのみ保存され、他の人と共有されることはありません。
トークンを知っている人だけがアップロードできます。取り扱いに注意してください。

「☰」メニューの「🖼 思い出一覧」から、これまでの写真を一覧表示できます。

### 手動で追加する場合

1. `images/` フォルダに写真ファイルを追加する
2. `photos.json` に写真情報を追記する

```json
[
  { "file": "photo1.jpg", "date": "20260101", "caption": "元日の空" },
  { "file": "photo2.jpg", "date": "20260215", "caption": "" }
]
```

- `file`: `images/` 内のファイル名
- `date`: `YYYYMMDD` 形式（例: `20260101`）
- `caption`: 省略可

写真をクリックすると拡大表示（背景クリックまたは Esc で閉じる）。

## 注意

このリポジトリは GitHub Pages のホストのために public 設定になっています。
ページ自体は `noindex, nofollow` を指定して検索エンジンには表示されませんが、
公開 URL を知っている人は誰でも閲覧できます。個人情報を含む写真の扱いに注意してください。

## ローカル確認

```bash
python -m http.server 8000
```

`http://localhost:8000` で確認できます（`fetch('photos.json')` を使うため `file://` では動作しません）。
