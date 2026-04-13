<div align="center">
  <h1>PhoneBase Skill Template</h1>
  <p>Scaffolding templates for <code>pb skills new</code></p>
  <p>
    <a href="https://github.com/phonebase-cloud/phonebase-cli"><img src="https://img.shields.io/badge/pb%20CLI-1.0.4+-2F81F7.svg" alt="pb CLI 1.0.4+" /></a>
    <a href="./LICENSE"><img src="https://img.shields.io/badge/License-GPL%20v3-blue.svg" alt="License: GPL v3" /></a>
  </p>
  <p><a href="./README.md">English</a> | <a href="./README.zh-CN.md">简体中文</a></p>
</div>

## What is this?

When you run `pb skills new <name>`, the CLI pulls templates from this repo to generate a new skill project. You don't need to clone this repo manually — `pb` handles it automatically.

## Structure

```
templates/
└── default/
    ├── SKILL.md.tmpl           # Skill definition (frontmatter + guide)
    └── scripts/
        ├── _lib.js.tmpl        # Shared utilities (not registered as a command)
        ├── open.js.tmpl        # Launch the app
        ├── close.js.tmpl       # Force stop the app
        └── clear.js.tmpl       # Clear app data
```

## Creating a skill

```bash
# Connect to a device first
pb connect <device-id>

# Create an app skill (interactive app picker)
pb skills new myapp --package com.example.app

# Create a general-purpose skill (no target app)
pb skills new mytool
```

The generated skill is placed in `~/.phonebase/skills/<name>/` and immediately available as `pb <name>`.

## Custom template repo

You can point `pb skills new` to a different template repo:

```bash
PHONEBASE_SKILL_TEMPLATE_REPO=https://github.com/your-org/your-templates.git pb skills new myskill
```

## Related

- [phonebase-cli](https://github.com/phonebase-cloud/phonebase-cli) — The `pb` CLI tool
- [phonebase-skill-hub](https://github.com/phonebase-cloud/phonebase-skill-hub) — Community skill directory
- [phonebase-skills](https://github.com/phonebase-cloud/phonebase-skills) — Global AI agent skill
