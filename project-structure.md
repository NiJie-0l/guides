# 项目结构规范

## 通用结构

```
project/
├── README.md           # 必须：项目介绍
├── LICENSE             # 必须：许可证
├── .gitignore          # 必须：排除规则
├── CHANGELOG.md        # 版本记录
├── CONTRIBUTING.md     # 贡献指南
├── src/                # 源代码
├── tests/              # 测试
├── docs/               # 文档
└── .github/
    ├── workflows/      # CI/CD
    ├── ISSUE_TEMPLATE/ # Issue 模板
    └── PULL_REQUEST_TEMPLATE.md
```

## Python 项目

```
python-project/
├── pyproject.toml      # 项目配置（替代 setup.py）
├── src/
│   └── package/
│       ├── __init__.py
│       └── main.py
├── tests/
│   ├── conftest.py
│   └── test_main.py
└── .github/workflows/ci.yml
```

## Node.js 项目

```
node-project/
├── package.json
├── src/
│   └── index.js
├── test/
│   └── index.test.js
└── .github/workflows/ci.yml
```

## 文档项目

```
docs-project/
├── README.md
├── docs/
│   ├── getting-started.md
│   ├── api-reference.md
│   └── examples.md
└── .github/workflows/deploy.yml  # GitHub Pages
```
