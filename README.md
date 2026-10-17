# xiaoyao-skills

公开技能库：收录**可对外分享**的 Claude Code / DeepSeek Harness / Codex 技能。

私有技能、含本机习惯或敏感内容的技能，留在 [`LiXiaoyao2/my-skills`](https://github.com/LiXiaoyao2/my-skills)（私有库）。两边结构一致，技能可以从私有库「毕业」到这里。

## 结构

```
xiaoyao-skills/
├── README.md
└── skills/                   ← 必须存在，cc-switch 按此目录发现技能
    └── <技能名>/
        ├── SKILL.md          必需：YAML frontmatter + 技能说明
        ├── scripts/          可选：可执行脚本
        ├── references/       可选：按需加载的参考文档
        └── assets/           可选：输出用模板/资源
```

> `skills/` 这一层不能省。技能目录直接放仓库根目录时，cc-switch 扫描会报 `SKILL_DIR_NOT_FOUND`。

## 收录标准

往这里放之前逐条过，任一不过就别公开：

- **通用**：不绑定某台机器。不写死绝对路径（用 `~` 或相对自身目录），不依赖只有我这儿才有的版本。
- **无敏感**：不含密钥、token、内网地址、个人目录结构、账号标识。
- **实测过**：没验证过的流程不进公开库。结论要带验证条件，推断标「待核」。
- **可执行**：写成「现象 → 根因 → 处置」，没有动作的纯描述不收。
- **frontmatter 完整**：`name` + `description`（description 决定触发准确率，写清“做什么”和“什么情况下用”）。

## 安装

cc-switch 里添加本仓库即可（公开库可直接下载 archive）。手动安装：

```bash
ln -s "$PWD/skills/<技能名>" ~/.claude/skills/<技能名>
```

## 新增技能

1. 建 `skills/<技能名>/SKILL.md`，frontmatter 至少含 `name` 和 `description`
2. 按上面的收录标准自查一遍
3. `git add . && git commit -m "feat: 新增 <技能名>" && git push`
4. cc-switch 里刷新本仓库

## 许可

技能内容为个人笔记与自建脚本。引用第三方项目行为的，只写实测结论与自建脚本，不分发其源码。
