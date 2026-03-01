# Chromatic (幻彩工坊) 团队

> **团队类型**：混合型（Hybrid Team）
> **创建日期**：2026-03-01
> **版本**：3.0

## 📋 团队概述

Chromatic 是一个专注于 UI/UX 设计和前端实现的专业团队，采用混合型协作模式，能够根据任务特点灵活选择串行、并行或混合执行模式。

### 🎯 团队目标

提供从视觉设计到前端实现的完整 UI/UX 解决方案，包括色彩系统、交互流程、动画效果、组件实现、设计系统和质量评审。

### 👥 专家成员

| 代号 | 角色 | 核心能力 |
|------|------|----------|
| **Prism** | 色彩专家 | 视觉风格设计、色彩系统、配色方案 |
| **Flow** | 布局流程专家 | 信息架构、交互流程、页面布局 |
| **Spark** | 动画特效专家 | 动画设计、微交互、过渡效果 |
| **Pixel** | 前端实现专家 | UI组件开发、React/Vue实现 |
| **Grid** | 设计系统专家 | Design Tokens、组件规范 |
| **Lens** | UI评审专家 | 可用性测试、设计评审 |

## 🚀 使用方法

### 安装团队

1. **复制文件到技能目录**：
   ```bash
   # 复制整个团队包到 Claude 技能目录
   cp -r "N:\编程备份\3.0团队\chromatic-team" "C:\Users\Mr.Chen\.claude\skills\"
   ```

2. **验证安装**：
   - 检查 `C:\Users\Mr.Chen\.claude\skills\chromatic-team\` 目录
   - 确认包含 `skills/chromatic-coordinator/skill.md`
   - 确认包含 `agents/` 目录下的6个专家配置

### 触发团队

直接在对话中提及 UI/UX 相关任务：

```
用户: 我需要设计一个现代化的登录页面

助手: 我将使用幻彩工坊团队来帮你设计登录页面。
      <Uses Skill tool to invoke chromatic-coordinator skill>
```

## 📊 团队协作模式

### 混合型协作

Chromatic 采用混合型协作模式，根据任务特点智能选择执行方式：

#### 串行场景（强依赖）
- **示例**：视觉设计 → 交互设计 → 前端实现
- **流程**：Prism → Flow → Pixel

#### 并行场景（独立任务）
- **示例**：多专家评审同一设计
- **流程**：所有专家同时工作，独立分析不同维度

#### 混合场景（分阶段）
- **示例**：设计阶段（串行）→ 实现阶段（并行）
- **流程**：
  - 阶段1（串行）：Prism → Flow
  - 阶段2（并行）：Pixel ∥ Grid ∥ Spark

## 📁 目录结构

```
chromatic-team/
├── README.md                              # 本文件
├── INSTALL.md                             # 详细安装指南
├── agents/                                # 专家配置
│   ├── chromatic-prism.md                 # 色彩专家
│   ├── chromatic-flow.md                  # 布局流程专家
│   ├── chromatic-spark.md                 # 动画特效专家
│   ├── chromatic-pixel.md                 # 前端实现专家
│   ├── chromatic-grid.md                  # 设计系统专家
│   └── chromatic-lens.md                  # UI评审专家
└── skills/
    └── chromatic-coordinator/
        └── skill.md                       # 协调器技能
```

## 🔧 MCP 工具支持

部分专家支持 MCP 工具以增强能力：

| 专家 | MCP工具 | 用途 |
|------|---------|------|
| Prism | 无 | - |
| Flow | 无 | - |
| Spark | mcp__sequential-thinking__sequentialthinking | 复杂动画流程设计 |
| Pixel | 无 | - |
| Grid | 无 | - |
| Lens | mcp__chromatic-lens | UI设计评审、可访问性验证 |

## 📝 工作流程示例

### 示例1：设计新功能UI

```
用户任务：设计用户个人中心页面

执行流程：
1. 需求沟通（协调器）
2. 模式识别：混合模式
3. 阶段1（串行）：
   - Prism: 视觉风格设计
   - Flow: 信息架构设计
4. 阶段2（并行）：
   - Pixel: UI组件实现
   - Spark: 动画效果实现
   - Grid: Design Tokens定义
5. 阶段3（串行）：
   - Lens: UI评审和质量检查
6. 汇总输出
```

### 示例2：快速设计评审

```
用户任务：评审现有设计的可用性

执行流程：
1. 需求沟通（协调器）
2. 模式识别：并行模式
3. 并行执行：
   - Prism: 视觉一致性检查
   - Flow: 交互流程分析
   - Lens: 可用性评估
4. 汇总评审报告
```

## 🎨 团队特色

- **灵活协作**：根据任务特点智能选择串行、并行或混合模式
- **完整覆盖**：从设计到实现的全流程支持
- **质量保证**：内置评审机制，确保输出质量
- **标准化**：遵循现代 UI/UX 最佳实践

## 📖 相关文档

- [详细安装指南](INSTALL.md)
- [协调器文档](skills/chromatic-coordinator/skill.md)
- [专家配置文档](agents/)

## 🆘 常见问题

**Q: 团队如何选择执行模式？**
A: 协调器会分析任务的依赖关系，智能选择最合适的执行模式。

**Q: 可以指定某个专家工作吗？**
A: 可以，在需求沟通时明确指定需要的专家。

**Q: 如何查看专家的工作成果？**
A: 协调器会汇总所有产出，并提供完整的报告。

---

**团队版本**：3.0
**最后更新**：2026-03-01
**维护者**：Super Team Builder
