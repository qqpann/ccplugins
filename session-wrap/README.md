# session-wrap

Claude Code のセッション間で作業の継続性を維持するプラグイン。

## Commands

### `/wrap`

セッション終了時に実行。現在の作業内容を要約して `.claude/sessions/YYYY-MM-DD.md` に保存します。

```
/wrap
```

### `/catchup`

セッション開始時に実行。直近の作業ログを読み取り、状況を把握してからセッションを開始します。

```
/catchup
```

## Log Format

```markdown
## 2026-01-20 14:30

### やったこと
- 機能Aの実装を完了
- テストを追加

### 途中のこと
- 機能Bのリファクタリング中

### 次やること
- 機能Bの完成
- コードレビュー依頼

### メモ
- APIの仕様変更に注意
```

## Installation

```bash
# Claude Code settings で追加
claude /plugins add ~/.claude/plugins/session-wrap
```

## File Location

ログは各プロジェクトの `.claude/sessions/` ディレクトリに保存されます。
