# 飞书集成开发指南

## 工具链

- lark-cli — 飞书 API CLI 工具
- Hermes Agent — AI agent + lark-cli 自动化

## 核心能力

| 能力 | 命令 |
|------|------|
| 文档导出 | `lark-cli drive +export` |
| 文档上传 | `lark-cli drive +upload` |
| 知识库管理 | `lark-cli wiki +node-list` |
| 多维表格 | `lark-cli base +record-list` |
| 消息发送 | `lark-cli im +messages-send` |

## 同步模式

- **Pull**: 飞书 → Git（lark-cli export → git commit）
- **Push**: Git → 飞书（git diff → lark-cli import/upload）
- **Full**: 双向同步（先 pull 再 push）
