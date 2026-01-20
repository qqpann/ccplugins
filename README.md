# ccplugins

自作 Claude Code プラグイン集。

## Plugins

| Name | Description |
|------|-------------|
| [session-wrap](./session-wrap/) | セッション間の作業継続性を維持（`/wrap`, `/catchup`） |

## Installation

`~/.claude/settings.json` に追加:

```json
{
  "plugins": [
    "~/workspace/ccplugins/session-wrap"
  ]
}
```

または、複数プラグインをまとめて:

```json
{
  "plugins": [
    "~/workspace/ccplugins/session-wrap",
    "~/workspace/ccplugins/another-plugin"
  ]
}
```

## Development

新しいプラグインを作成する場合:

```bash
mkdir -p ~/workspace/ccplugins/new-plugin/.claude-plugin
mkdir -p ~/workspace/ccplugins/new-plugin/commands
```
