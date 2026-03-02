# Chromatic 团队安装指南

## 安装步骤

### 1. 复制配置文件到本机

将团队配置复制到 Claude Code 的配置目录：

```powershell
# 创建目标目录（如果不存在）
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.claude\agents"
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.claude\skills\chromatic-coordinator"

# 复制专家配置
Copy-Item -Path "agents\*.md" -Destination "$env:USERPROFILE\.claude\agents\" -Force

# 复制协调器技能
Copy-Item -Path "skills\chromatic-coordinator\skill.md" -Destination "$env:USERPROFILE\.claude\skills\chromatic-coordinator\" -Force
```

### 2. 验证安装

重启 Claude Code 后，验证团队是否可用：

```
/chromatic-coordinator 帮我设计一个简单的登录页面
```

如果协调器正常响应，说明安装成功。

---

## 文件位置

| 文件类型 | 目标位置 |
|----------|----------|
| 专家配置 | `C:\Users\{用户名}\.claude\agents\chromatic-*.md` |
| 协调器技能 | `C:\Users\{用户名}\.claude\skills\chromatic-coordinator\skill.md` |

---

## 完整安装命令（PowerShell）

```powershell
# 设置源目录（修改为实际路径）
$sourceDir = "N:\编程备份\4.0团队\chromatic-team"

# 创建目标目录
$agentsDir = "$env:USERPROFILE\.claude\agents"
$skillsDir = "$env:USERPROFILE\.claude\skills\chromatic-coordinator"

New-Item -ItemType Directory -Force -Path $agentsDir
New-Item -ItemType Directory -Force -Path $skillsDir

# 复制所有专家配置
Copy-Item -Path "$sourceDir\agents\chromatic-*.md" -Destination $agentsDir -Force

# 复制协调器技能
Copy-Item -Path "$sourceDir\skills\chromatic-coordinator\skill.md" -Destination $skillsDir -Force

Write-Host "Chromatic 团队安装完成！" -ForegroundColor Green
Write-Host "请重启 Claude Code 后使用 /chromatic-coordinator 命令" -ForegroundColor Yellow
```

---

## 使用示例

### 视觉定调
```
/chromatic-coordinator 为我的金融科技App设计一套配色方案
```

### 布局设计
```
/chromatic-coordinator 帮我设计一个数据仪表盘的布局
```

### 代码实现
```
/chromatic-coordinator 用Tailwind实现一个卡片组件
```

### 质量审查
```
/chromatic-coordinator 审查 localhost:3000 的UI有没有问题
```

---

## 故障排查

### 问题：协调器无法触发

**解决方案**：
1. 确认文件已正确复制到目标位置
2. 重启 Claude Code
3. 检查 skill.md 文件格式是否正确

### 问题：专家无法触发

**解决方案**：
1. 确认专家配置文件已复制到 agents 目录
2. 检查专家 name 字段格式是否正确（应为 `chromatic-xxx`）

---

## 版本信息

- **版本**：v4.0
- **更新日期**：2026-03-02
- **兼容**：Claude Code CLI
