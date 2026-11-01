# CLAUDE.md

## プロジェクト概要

- GitHub Pagesで公開する個人サイト `https://hiroshikuze.github.io/` のリポジトリ（`hiroshikuze/hiroshikuze.github.io`）。
- 目的は検索エンジン（SEO）とAI検索（AIO）向けの対策。
- 静的ファイルのみでビルド工程はない。デフォルトブランチ `main` のルートにある `index.html` が配信される。
- アクセス解析はumamiを使う。Google Analyticsは使わない。
- 見た目はHTML5 UPのHyperspace（CC BY 3.0）を改変して使っている。フッターの「Design: HTML5 UP」のリンクと、`index.html`・`assets/css/main.css`・`assets/js/main.js`の先頭にあるクレジットのコメントは削除しない。
- `index.html`の`<head>`にある、JSON-LD・umamiのスクリプト・`title`・`description`・`canonical`・OGP・Search Consoleの確認用`<meta>`タグは、デザインを変えても削除しない。

## 構成

```text
.
├── index.html         公開ページ（Hyperspaceを改変）
├── assets/            Hyperspace由来のCSS・JS、jQuery、Font Awesomeのフォント
├── robots.txt         クローラーの許可とサイトマップの場所
├── sitemap.xml        サイトマップ
├── llms.txt           AI向けのサイト概要とプロジェクト一覧
├── README.md          概要とライセンス表記
├── LICENSE            MITライセンス（自作部分）
└── .claude/
    ├── revision_log.md    改訂記録
    └── rules/
        ├── coding.md      コーディング規約
        ├── git.md         Gitワークフロー
        └── writing.md     日本語執筆規約（*.md・*.html に適用）
```

## 作業の進め方

- セッション開始時は `.claude/revision_log.md` を読む。
- 編集前に該当ファイルを読む。作業内容に応じて `.claude/rules/` の該当ルールを読む。
- 文書は日本語で書き、表記は `.claude/rules/writing.md` に従う。
- `index.html`のプロジェクト一覧を変えたら、`llms.txt`のプロジェクト一覧も同じ内容にそろえる。
- `assets/`のjQueryやFont Awesomeを更新したら、READMEのバージョン表記と`assets/css/main.css`のヘッダーも直す。

## Git

- 作業ブランチは `claude/<slug>` の形式で作る。
- `main` へ直接プッシュしない（ユーザーの明示的な許可がある場合を除く）。
- PRは、ユーザーから依頼があったときだけ作成する。マージはユーザーが行う。
- PRがマージ済みのブランチは再利用しない。最新の`main`から新しいブランチを切る。

## 公開前の確認

公開ページの変更は、次の手順で目視確認する。

1. リポジトリ直下で`python -m http.server 8765 --bind 127.0.0.1`を起動する（`file://`はClaude in Chromeで開けない）。
2. Claude in Chromeで`http://127.0.0.1:8765/index.html`を開き、テキスト・リンク・見た目をスクリーンショットで確認する。Claude in Chromeが使えない環境では、導入済みのPlaywright（Chromium）で代用し、代用したことを報告する。
3. スマートフォン幅の確認は、`document.documentElement.scrollWidth > window.innerWidth`がfalseであることで行う。ウィンドウのリサイズが効かない場合は、この確認を省かず、結果が取れなかったことを報告する。
4. コンソールエラーと失敗したリクエストがないことを確認する。リンクを変えていない場合は、変更前後で外部リンクの`href`が同じであることも確認する。
5. 確認が終わったら、サーバーを停止する。

## 見直し

- 月1回、セッションで `/doctor prompt-audit` を実行し、古い記述・存在しないファイルへの参照・矛盾を修正する。
- 見直した日付は `.claude/revision_log.md` に記録する。
- 作成が完了した「今後作成予定」の項目は、その場で削除する。
