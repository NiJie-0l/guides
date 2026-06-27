# 飞书集成开发指南

## 工具链

| 工具 | 用途 | 安装 |
|------|------|------|
| lark-cli | 飞书 API CLI | `brew install lark-cli` |
| Hermes Agent | AI agent + 自动化 | `~/.local/bin/hermes` |

## 核心能力

| 能力 | 命令 | 说明 |
|------|------|------|
| 文档导出 | `lark-cli drive +export` | docx→markdown, sheet→xlsx |
| 文档上传 | `lark-cli drive +upload` | 本地文件→飞书 |
| 知识库管理 | `lark-cli wiki +node-list` | 列出/创建/移动节点 |
| 多维表格 | `lark-cli base +record-list` | CRUD 记录/字段/视图 |
| 消息发送 | `lark-cli im +messages-send` | 文本/卡片/图片 |
| 日历 | `lark-cli calendar event list` | 查询/创建日程 |

## 同步模式

| 模式 | 方向 | 命令 |
|------|------|------|
| pull | 飞书→Git | `feishu-sync.sh pull` |
| push | Git→飞书 | `feishu-sync.sh push` |
| full | 双向 | `feishu-sync.sh full` |

## 身份选择

- `--as user` — 以你的身份操作，权限 = 你在飞书的权限
- `--as bot` — 以应用身份操作，权限 = 应用 scope

**优先用 `--as user`**，bot 身份有部门/权限限制。

## 常见坑

1. **wiki token ≠ file token** — wiki URL 里的 token 要先 `drive +inspect` 解包
2. **export 输出路径** — 必须 cd 到目标目录，不支持绝对路径
3. **select 字段** — 创建时不能带 options，要 `+field-update` 后加
4. **record 写入** — JSON 不要用 `fields` 包裹，直接传字段
5. **strict-mode** — 默认 bot-only，用 `lark-cli config strict-mode off` 切换
