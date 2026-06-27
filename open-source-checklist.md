# 开源项目发布检查清单

## 必须有

- [ ] **README.md** — 项目介绍、安装、使用、贡献方式
- [ ] **LICENSE** — 明确许可证（MIT/Apache-2.0/GPL-3.0）
- [ ] **.gitignore** — 排除构建产物、密钥、临时文件
- [ ] **CHANGELOG.md** — 版本变更记录
- [ ] **CODE_OF_CONDUCT.md** — 行为准则

## 强烈建议

- [ ] **CONTRIBUTING.md** — 贡献指南（PR 流程、代码规范）
- [ ] **CI/CD** — GitHub Actions 自动测试
- [ ] **语义化版本** — v1.2.3 格式，用 git tag
- [ ] **Issue 模板** — bug report / feature request
- [ ] **PR 模板** — 变更描述、测试、截图

## 选择性开源策略

### 适合公开
- 工具脚本、CLI 工具
- 配置文件、dotfiles
- 项目模板
- 学习笔记/教程
- 通用库/中间件

### 保持私有
- 包含个人数据的文档
- 商业逻辑/核心算法
- API 密钥/凭证
- 未完成的原型

### 部分公开
- 核心逻辑开源，业务配置私有
- 文档公开，数据私有
- 模板公开，实际项目私有

## 发布流程

```bash
# 1. 确认 .gitignore 排除了敏感文件
git status

# 2. 检查历史中是否有密钥泄露
git log --all --full-history -- "*.env" "*secret*" "*password*"

# 3. 打 tag
git tag -a v1.0.0 -m "first release"
git push --tags

# 4. 在 GitHub 创建 Release
gh release create v1.0.0 --title "v1.0.0" --notes "First public release"

# 5. 添加 topics（标签）让项目可被发现
gh repo edit --add-topic "python,cli,tool"
```
