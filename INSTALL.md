# Chromatic 团队安装指南

## 安装步骤

### 1. 复制 Agent 配置

将 `agents/` 目录下的所有文件复制到 Claude Code 的 agents 目录：

```bash
# Windows (Git Bash)
cp -r chromatic-team/agents/*.md ~/.claude/agents/

# macOS / Linux
cp -r chromatic-team/agents/*.md ~/.claude/agents/
```

### 2. 复制 Skill 配置

将 `skills/` 目录下的协调器复制到 Claude Code 的 skills 目录：

```bash
# Windows (Git Bash)
cp -r chromatic-team/skills/chromatic-coordinator ~/.claude/skills/

# macOS / Linux
cp -r chromatic-team/skills/chromatic-coordinator ~/.claude/skills/
```

### 3. 重启 Claude Code

重启 Claude Code 以加载新的配置。

### 4. 验证安装

使用以下关键词测试团队是否正确加载：

| 测试方式 | 关键词示例 |
|----------|------------|
| 协调器 | "帮我设计一个后台管理系统的UI" |
| Prism | "帮我定调这个APP的视觉风格" |
| Pixel | "用Tailwind实现这个组件" |

## 手动安装（分步）

如果需要逐个文件安装：

### Agents

```bash
# 创建目标目录（如果不存在）
mkdir -p ~/.claude/agents

# 复制每个专家配置
cp chromatic-team/agents/chromatic-prism.md ~/.claude/agents/
cp chromatic-team/agents/chromatic-flow.md ~/.claude/agents/
cp chromatic-team/agents/chromatic-spark.md ~/.claude/agents/
cp chromatic-team/agents/chromatic-pixel.md ~/.claude/agents/
cp chromatic-team/agents/chromatic-grid.md ~/.claude/agents/
```

### Skills

```bash
# 创建目标目录
mkdir -p ~/.claude/skills/chromatic-coordinator

# 复制协调器
cp chromatic-team/skills/chromatic-coordinator/skill.md ~/.claude/skills/chromatic-coordinator/
```

## 目录结构验证

安装完成后，你的 `.claude` 目录应该包含：

```
~/.claude/
├── agents/
│   ├── chromatic-prism.md
│   ├── chromatic-flow.md
│   ├── chromatic-spark.md
│   ├── chromatic-pixel.md
│   └── chromatic-grid.md
└── skills/
    └── chromatic-coordinator/
        └── skill.md
```

## 卸载

如需卸载团队：

```bash
# 删除 agents
rm ~/.claude/agents/chromatic-*.md

# 删除 skill
rm -rf ~/.claude/skills/chromatic-coordinator
```

## 故障排除

| 问题 | 解决方案 |
|------|----------|
| 团队未被触发 | 检查文件路径是否正确，重启 Claude Code |
| 专家未被识别 | 确认 `.md` 文件格式正确，frontmatter 完整 |
| 协调器不工作 | 检查 `skill.md` 的 YAML frontmatter 格式 |

## 技术支持

如有问题，请检查：
1. 文件编码是否为 UTF-8
2. YAML frontmatter 格式是否正确
3. 文件名是否与配置中的 `name` 字段一致
