# Chromatic (幻彩工坊) 安装指南

> 📌 **重要提示**：本指南适用于 Windows 系统，安装位置为 `C:\Users\Mr.Chen\.claude\skills\`

---

## 📦 安装前准备

### 系统要求

- **操作系统**：Windows 11
- **Claude Code**：已安装并配置
- **用户目录**：`C:\Users\Mr.Chen\`
- **源文件位置**：`N:\编程备份\3.0团队\chromatic-team\`

### 检查清单

- [ ] Claude Code 已正确安装
- [ ] 用户技能目录存在：`C:\Users\Mr.Chen\.claude\skills\`
- [ ] 团队包文件完整：`N:\编程备份\3.0团队\chromatic-team\`
- [ ] 已备份旧版本（如有需要）

---

## 🔧 安装步骤

### Step 1：清理旧版本（如存在）

**⚠️ 警告**：此操作将永久删除旧版本，请确认已备份！

```bash
# 删除旧版本
rm -rf "C:\Users\Mr.Chen\.claude\skills\chromatic-team"
rm -rf "C:\Users\Mr.Chen\.claude\skills\chromatic-coordinator"
```

### Step 2：复制团队包

```bash
# 复制整个团队包到技能目录
cp -r "N:\编程备份\3.0团队\chromatic-team" "C:\Users\Mr.Chen\.claude\skills\"
```

### Step 3：验证安装结构

│   └── chromatic-lens.md
└── skills\
    └── chromatic-coordinator\
        └── skill.md
```

### Step 4：验证文件完整性

**检查点**：确认以下文件存在且内容完整

```bash
# 检查协调器
ls "C:\Users\Mr.Chen\.claude\skills\chromatic-team\skills\chromatic-coordinator\skill.md"

# 检查所有专家
ls "C:\Users\Mr.Chen\.claude\skills\chromatic-team\agents\"

# 统计文件数量（应显示：6个专家配置 + 1个协调器）
ls "C:\Users\Mr.Chen\.claude\skills\chromatic-team\agents\" | wc -l
```

**预期结果**：
- 协调器文件：1个
- 专家配置：6个
- 总文件数：7个

---

## ✅ 安装验证

### 方法1：通过 Claude Code 验证

1. **重启 Claude Code**
2. **输入测试命令**：
   ```
   我需要设计一个简单的登录表单
   ```
3. **观察响应**：
   - 应自动触发 chromatic-coordinator
   - 协调器应显示团队信息

### 方法2：通过文件检查验证

```bash
# 检查协调器 description
head -n 5 "C:\Users\Mr.Chen\.claude\skills\chromatic-team\skills\chromatic-coordinator\skill.md"

# 应显示：
# ---
# name: chromatic-coordinator
# description: Chromatic (幻彩工坊) team coordinator skill...
```

### 方法3：通过技能列表验证

在 Claude Code 中执行：
```
/list skills
```

应显示：
- `chromatic-coordinator` - Chromatic (幻彩工坊) team coordinator skill

---

## 🔍 故障排查

### 问题1：协调器未被触发

**症状**：提及 UI/UX 任务时，没有自动触发协调器

**可能原因**：
- description 格式错误
- 触发关键词不清晰

**解决方案**：
1. 检查 `skill.md` 中的 description 字段
2. 确认无双引号，单行格式
3. 确认包含触发关键词

### 问题2：专家无法触发

**症状**：协调器尝试触发专家时失败

**可能原因**：
- 专家文件路径错误
- 专家 description 格式错误
- 触发词不匹配

**解决方案**：
1. 检查 `agents/` 目录下的文件名
2. 确认格式：`chromatic-{expert-name}.md`
3. 检查 description 中的示例是否包含完整的触发格式

### 问题3：MCP 工具无法使用

**症状**：专家尝试使用 MCP 工具时失败

**可能原因**：
- MCP 工具未在 tools 字段中声明
- 协调器未授权
- MCP 服务器未启动

**解决方案**：
1. 检查专家配置中的 tools 字段
2. 确认协调器已授权该 MCP 工具
3. 验证 MCP 服务器运行状态

### 问题4：文件路径错误

**症状**：专家报告找不到文件

**可能原因**：
- 信息传递机制路径格式错误
- 目录结构不匹配

**解决方案**：
1. 检查协调器触发指令中的路径格式
2. 确认使用 `.[chromatic]` 作为工作目录前缀
3. 验证 phases/ 和 outputs/ 目录结构

---

## 📋 卸载指南

如需卸载 Chromatic 团队：

```bash
# 删除团队目录
rm -rf "C:\Users\Mr.Chen\.claude\skills\chromatic-team"

# 清理可能的工作目录
rm -rf ".chromatic"
```

---

## 🆘 获取帮助

如遇到安装问题：

1. **检查日志**：查看 Claude Code 的错误信息
2. **验证结构**：对照"安装步骤"中的目录结构
3. **查阅文档**：参考 `README.md` 和相关配置文件
4. **重新安装**：如问题持续，尝试完全卸载后重新安装

---

## 📊 安装检查清单

完成安装后，确认以下所有项：

- [ ] 团队目录已创建：`C:\Users\Mr.Chen\.claude\skills\chromatic-team\`
- [ ] 协调器文件存在：`skills/chromatic-coordinator/skill.md`
- [ ] 6个专家配置全部存在
- [ ] 协调器可以被触发
- [ ] 所有专家可以被正确触发
- [ ] MCP 工具（如有）可以正常使用
- [ ] 工作目录结构正确（phases/、outputs/、inbox.md）
- [ ] README.md 和 INSTALL.md 文件完整

**✅ 全部通过后，安装成功！**

---

**安装指南版本**：3.0
**最后更新**：2026-03-01
