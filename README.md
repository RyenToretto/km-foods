# 菜谱

个人菜谱收集项目，每道菜独立一个文件夹，记录做法、调料、用具等完整信息。

项目集成了 Cursor Skills，可通过 AI 辅助快速创建、分析、改良和审查菜谱。

## 目录结构

```
km-foods/
├── recipes/                    # 菜谱集合
│   ├── 家常菜/
│   │   ├── 番茄炒蛋/
│   │   │   └── README.md
│   │   └── 宫保鸡丁/
│   │       └── README.md
│   ├── 汤羹/
│   ├── 甜品/
│   └── ...
├── templates/                  # 模板
│   └── recipe-template.md      # 菜谱标准模板
├── .cursor/
│   ├── rules/                  # Cursor 规则
│   │   ├── project-conventions.mdc
│   │   └── recipe-format.mdc
│   └── skills/                 # Cursor Skills
│       ├── create-recipe/      # 创建新菜谱
│       ├── analyze-recipe/     # 分析菜谱
│       ├── improve-recipe/     # 改良菜谱
│       ├── search-recipe/      # 搜索菜谱
│       └── recipe-review/      # 审查菜谱格式
└── README.md
```

## 菜谱格式

每道菜以文件夹形式存放在 `recipes/分类/菜名/` 下，主文件为 `README.md`。

标准菜谱包含以下部分：

- **基本信息** — 分类、口味、难度、用时、份量
- **食材** — 用量与备注
- **调料** — 用量与备注
- **用具** — 烹饪所需器具
- **做法** — 分步骤详细说明
- **技巧与窍门** — 经验总结
- **变体** — 可选的变化做法

完整模板见 [templates/recipe-template.md](templates/recipe-template.md)。

## Cursor Skills

项目内置了 5 个 Cursor Skill，在 Cursor IDE 中可自动触发：

| Skill | 说明 | 触发关键词 |
|-------|------|-----------|
| create-recipe | 引导创建新菜谱 | 新建菜谱、添加一道菜、记录做法 |
| analyze-recipe | 营养/难度/时间分析 | 分析、营养、热量 |
| improve-recipe | 提出改良建议 | 改进、优化、建议 |
| search-recipe | 按条件搜索菜谱 | 找菜谱、有什么菜、食材搭配 |
| recipe-review | 检查格式规范性 | 检查菜谱、审查格式、review |

## 参考

项目结构与 AI 工作流借鉴了 [claude-code-best-practice](https://github.com/shanraisshan/claude-code-best-practice) 的以下实践：

- **渐进式披露（Progressive Disclosure）** — Skill 主文件精简，详细参考放在附属文件
- **模板模式（Template Pattern）** — 统一菜谱格式
- **工作流模式（Workflow Pattern）** — 分步引导创建菜谱
- **反馈循环（Feedback Loop）** — 菜谱审查的分级反馈机制
- **分层规则（Hierarchical Rules）** — 全局规则 + 文件级规则
