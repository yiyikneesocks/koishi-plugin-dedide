# ⚠️ DEPRECATED — split into standalone plugins

This plugin has been **split** into focused, standalone plugins:

| Old feature | New package |
|---|---|
| Message collection + DB + offline catchup (mock/what tables) | [`koishi-plugin-chatlog`](https://github.com/yiyikneesocks/koishi-plugin-chatlog) |
| Greeting / 问玩法 / 复读 / Mock 名人名言 | [`koishi-plugin-group-gags`](https://github.com/yiyikneesocks/koishi-plugin-group-gags) |
| Wordcloud | [`koishi-plugin-wordcloud`](https://github.com/yiyikneesocks/koishi-plugin-wordcloud) |
| 的/地/得 correction (was already separate) | [`koishi-plugin-dedide-ercorrection`](https://github.com/yiyikneesocks/koishi-plugin-dedide-ercorrection) |

Install the new packages instead. This repo will receive no further updates.

## Data migration

The old `mock` / `what` / `mock_catchup` tables are renamed in place — run:

```sql
RENAME TABLE mock TO chatlog_message;
RENAME TABLE what TO chatlog_vocab;
RENAME TABLE mock_catchup TO chatlog_watermark;
```
