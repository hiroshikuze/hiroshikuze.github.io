# rules/docs-workflow.md — docs/ファイル命名・構成規約

すべてYes/Noで判定できる条件として記述。

---

## ファイル作成チェック

- [ ] 新規ファイル作成前に同テーマの既存ファイルがないか確認したか？
- [ ] ファイル名は下表のパターンに従っているか？
- [ ] 記載するURLは実際に存在を確認済みか？（推測・生成したURLを書いていないか）
- [ ] 既存ファイルを上書きしていないか？（追記または新規ファイルで対応）

## ファイル命名パターン

| ファイル種別 | パターン | 例 |
| --- | --- | --- |
| 調査・トレンド | `YYYY-MM-DD-<topic>.md` | `2026-03-26-trend-analysis.md` |
| リファレンスリスト・運用マニュアル | `<category>.md`（`references/`配下） | `competitive-tools.md`・`admin-credit-tool-manual.md` |
| 確定済みプラン・仕様 | `plan-<feature>.md` | `plan-ai-panel-review.md` |
| decision-logの退避分（フェーズ別アーカイブ） | `decision-log-archive-<topic>.md` | `decision-log-archive-spec-design.md` |
| 未確定アイデアの一時置き場（単一ファイル・確定プロセス不要） | `idea-backlog.md` | `idea-backlog.md` |
| 意思決定ログ（追記式・単一ファイル） | `decision-log.md` | `decision-log.md` |
| 仕様vs実装ギャップ一覧（生きているトラッカー・単一ファイル） | `implementation-gaps.md` | `implementation-gaps.md` |
| UI/UXデザイン仕様（`plan-`命名は使わない・単一ファイル） | `<topic>.md` | `design-guidelines.md`・`requirements-screens.md` |
| 素材ファイル | `assets/<subdir>/<name>.<ext>` | `assets/yobiko/01_standing.png` |

## ディレクトリ構成

```text
(これからまとめる)
```
