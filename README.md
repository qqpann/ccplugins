# ccplugins

Claude Code プラグインマーケットプレイス。

## Plugins

| Name | Description |
|------|-------------|
| [session-wrap](./plugins/session-wrap/) | セッション間の作業継続性を維持（`/wrap`, `/catchup`） |

## Installation

### マーケットプレイスとしてインストール（推奨）

GitHubリポジトリから追加：
```
/plugin marketplace add qqpann/ccplugins
```

ローカルディレクトリから追加（開発用）：
```
/plugin marketplace add ./ccplugins
```

インストール後、利用したいプラグインを選択できます。

### 個別プラグインのインストール

`~/.claude/settings.json` に直接追加:

```json
{
  "plugins": [
    "~/workspace/ccplugins/plugins/session-wrap"
  ]
}
```

## Development

新しいプラグインを作成する場合:

```bash
mkdir -p plugins/new-plugin/.claude-plugin
mkdir -p plugins/new-plugin/commands
```

`plugins/new-plugin/.claude-plugin/plugin.json` を作成:

```json
{
  "name": "new-plugin",
  "version": "1.0.0",
  "description": "Your plugin description"
}
```

マーケットプレイスに登録する場合は `.claude-plugin/marketplace.json` の `plugins` 配列に追加してください。
