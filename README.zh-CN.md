<div align="center">
  <h1>PhoneBase Skill 模板</h1>
  <p><code>pb skills new</code> 的脚手架模板仓库</p>
  <p>
    <a href="https://github.com/phonebase-cloud/phonebase-cli"><img src="https://img.shields.io/badge/pb%20CLI-1.0.4+-2F81F7.svg" alt="pb CLI 1.0.4+" /></a>
    <a href="./LICENSE"><img src="https://img.shields.io/badge/License-GPL%20v3-blue.svg" alt="License: GPL v3" /></a>
  </p>
  <p><a href="./README.md">English</a> | <a href="./README.zh-CN.md">简体中文</a></p>
</div>

## 这是什么？

运行 `pb skills new <name>` 时，CLI 会自动从本仓库拉取模板生成新的 skill 项目。你不需要手动克隆本仓库 — `pb` 会自动处理。

## 目录结构

```
templates/
└── default/
    ├── SKILL.md.tmpl           # Skill 定义（frontmatter + 操作指南）
    └── scripts/
        ├── _lib.js.tmpl        # 共享工具（不会注册为命令）
        ├── open.js.tmpl        # 启动应用
        ├── close.js.tmpl       # 强制停止应用
        └── clear.js.tmpl       # 清除应用数据
```

## 创建 skill

```bash
# 先连接设备
pb connect <device-id>

# 创建应用 skill（交互式选择应用）
pb skills new myapp --package com.example.app

# 创建通用 skill（无目标应用）
pb skills new mytool
```

生成的 skill 会放在 `~/.phonebase/skills/<name>/`，立即可用：`pb <name>`。

## 自定义模板仓库

可以用环境变量指向其他模板仓库：

```bash
PHONEBASE_SKILL_TEMPLATE_REPO=https://github.com/your-org/your-templates.git pb skills new myskill
```

## 相关项目

- [phonebase-cli](https://github.com/phonebase-cloud/phonebase-cli) — pb CLI 工具
- [phonebase-skill-hub](https://github.com/phonebase-cloud/phonebase-skill-hub) — 社区 skill 目录
- [phonebase-skills](https://github.com/phonebase-cloud/phonebase-skills) — 全局 AI agent skill
