# Git 工作流规范

## 分支策略

| 分支 | 用途 | 命名 |
|------|------|------|
| `main` | 稳定发布 | — |
| `dev` | 开发集成 | — |
| `feat/*` | 功能开发 | `feat/add-export` |
| `fix/*` | Bug 修复 | `fix/null-pointer` |
| `docs/*` | 文档更新 | `docs/api-guide` |

## Commit 规范

格式: `type(scope): description`

| type | 说明 |
|------|------|
| feat | 新功能 |
| fix | 修复 |
| docs | 文档 |
| refactor | 重构（不改功能） |
| test | 测试 |
| chore | 构建/工具/依赖 |
| perf | 性能优化 |

示例:
```
feat(sync): add bidirectional feishu sync
fix(export): handle empty markdown output
docs(readme): add installation guide
```

## PR 流程

1. `git checkout -b feat/my-feature`
2. 开发 + 自测
3. `git push -u origin feat/my-feature`
4. `gh pr create --title "feat: my feature" --body "description"`
5. CI 通过 + Review
6. Merge → 自动关闭 PR 和分支

## 常用命令速查

```bash
# 撤销上次 commit（保留修改）
git reset HEAD~1

# 修改上次 commit 信息
git commit --amend

# 暂存当前修改
git stash
git stash pop

# 查看 diff（忽略空白）
git diff -w

# 清理已合并的本地分支
git branch --merged | grep -v main | xargs git branch -d
```
