# Git 工作流规范

## 分支策略

- `main` — 稳定发布分支
- `dev` — 开发集成分支
- `feat/*` — 功能分支
- `fix/*` — 修复分支

## Commit 规范

格式: `type(scope): description`

- feat: 新功能
- fix: 修复
- docs: 文档
- refactor: 重构
- test: 测试
- chore: 构建/工具

## PR 流程

1. 从 main 创建 feat/ 分支
2. 开发 + 自测
3. Push + 创建 PR
4. CI 通过 + Review
5. Merge → 自动关闭 PR 和分支
