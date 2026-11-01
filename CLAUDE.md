# CLAUDE.md

## プロジェクト概要

- GitHub Pagesで公開する個人サイト `https://hiroshikuze.github.io/` のリポジトリ（`hiroshikuze/hiroshikuze.github.io`）です。
- 目的は、検索エンジン（SEO）とAI検索（AIO）向けの対策です。
- 現時点は静的ファイルのみで、ビルド工程はありません。デフォルトブランチのルートにある `index.html` が配信されます。
- SEO用ファイル（`robots.txt`・`sitemap.xml`・`llms.txt`・構造化データなど）は今後作成する予定です。

## 作業の進め方

- セッション開始時は `.claude/CLAUDE.md`（索引）と `.claude/revision_log.md` を読みます。
- 作業内容に応じて `.claude/rules/` 配下の該当ルールを読みます。
- 文書は日本語で書き、表記は `.claude/rules/writing.md` に従います。

## Git

- 作業ブランチは `claude/<slug>` の形式で作ります。
- `main` への直接プッシュはしません（ユーザーの明示的な許可がある場合を除く）。
- PRは、ユーザーから依頼があったときだけ作成します。
