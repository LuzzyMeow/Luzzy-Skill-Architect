# AGENTS.md — Luzzy-Skill-Architect

## 项目概述

元技能架构师工具包，用于创建、诊断、升级 Agent Skills 的全生命周期工程。遵循 agentskills.io 开放标准，内建 PPER 思考协议（CoT+ReAct）。

## 技术栈

- Python 3.8+
- Markdown 文档
- agentskills.io 规范

## 目录结构

```
/workspace/projects/
├── SKILL.md                          # 入口：PPER协议 + 五阶段流程 + 质量门禁
├── README.md                         # 项目说明
├── references/                       # 按需加载的参考文档
│   ├── maturity-model.md             # L0-L5 成熟度升级详解
│   ├── design-patterns.md           # 六种设计模式 + 决策树
│   ├── anti-patterns.md              # 十种反模式 + 修复案例
│   ├── ecosystem-map.md              # 技能 vs 其他 Agent 机制
│   ├── vendor-extensions.md          # 平台扩展字段参考
│   ├── evaluation-guide.md           # L3 批量评测体系
│   └── skill-fusion.md               # 技能融合方法论
├── assets/
│   ├── templates/                    # 技能骨架模板
│   └── protocols/                    # 思考协议模板
└── scripts/
    ├── validate-trigger.py           # L1 触发词自动验证
    ├── fusion-analyzer.py            # 融合兼容性自动评分
    └── check-updates.py              # 源仓库更新检测
```

## 关键入口

- **SKILL.md**: 核心技能定义文件，PPER 协议入口
- **scripts/validate-trigger.py**: 触发词验证脚本
- **scripts/fusion-analyzer.py**: 技能融合分析脚本
- **scripts/check-updates.py**: 源仓库更新检测

## 运行与预览

- 本项目为工具包/文档工程，**不支持预览**
- Python 脚本可独立运行：
  ```bash
  python scripts/validate-trigger.py .
  python scripts/fusion-analyzer.py <skill1> <skill2>
  python scripts/check-updates.py
  ```

## 用户偏好与长期约束

- 使用 Python 3.8+
- 遵循 agentskills.io 规范
- PPER 思考协议是核心方法论

## 常见问题和预防

- 触发词验证失败：检查 SKILL.md 的 description 字段是否符合规范
- 融合评分过低：检查技能间是否满足四维准入评估标准
