# Luzzy-Skill-Architect

> 元技能架构师 — 创建、诊断、升级 Agent Skills 的全生命周期工程工具。

遵循 [agentskills.io](https://agentskills.io/specification) 开放标准，内建 PPER 思考协议（CoT+ReAct），覆盖从零创建到成熟度评估的完整技能工程方法论。

---

## 快速开始

```bash
# 克隆
git clone https://github.com/LuzzyMeow/Luzzy-Skill-Architect.git

# 安装为 WorkBuddy 技能
cp -r Luzzy-Skill-Architect ~/.workbuddy/skills/

# 运行自验证
python scripts/validate-trigger.py .
```

---

## 核心能力

| 维度 | 内容 |
|------|------|
| **思考协议** | PPER（Perception → Planning → Execution → Reflection）固定执行引擎 |
| **五阶段流程** | 理解意图 → 结构设计 → 撰写产出 → 验证触发 → 迭代打磨 |
| **技能融合** | 2+技能合并为 Skill Family，1+1≥2保障，四维准入评估，三层融合场景，自更新机制 |
| **成熟度模型** | L0-L5 六级阶梯，带完整升级路径 |
| **设计模式** | 七种可复用模式（Trigger-First / Progressive Disclosure / Domain Variant / Workflow Chain / Tool Augmentation / Template Factory / Skill Fusion） |
| **反模式库** | 十种常见错误，每个含 Before/After 案例 |
| **质量门禁** | 五个阶段 × 多层硬性检查清单 |
| **生态决策** | Skill vs CLAUDE.md vs MCP vs Rules 定位指南 |
| **评测体系** | L1 触发测试 + L2 单次执行 + L3 批量评测（evals.json） |

---

## 目录结构

```
Luzzy-Skill-Architect/
├── SKILL.md                          # 入口：PPER协议 + 五阶段流程 + 质量门禁
├── references/                       # 按需加载的参考文档
│   ├── maturity-model.md             # L0-L5 成熟度升级详解
│   ├── design-patterns.md            # 六种设计模式 + 决策树
│   ├── anti-patterns.md              # 十种反模式 + 修复案例
│   ├── ecosystem-map.md              # 技能 vs 其他 Agent 机制
│   ├── vendor-extensions.md          # 平台扩展字段参考
│   ├── evaluation-guide.md           # L3 批量评测体系
│   └── skill-fusion.md               # 技能融合方法论（准入评估/自更新）
├── assets/
│   ├── templates/                    # 技能骨架模板
│   │   ├── skill-basic.md            # L1 单文件技能
│   │   ├── skill-structured.md       # L2-L3 带拆分技能
│   │   └── skill-family.md           # L5 编排型技能家族
│   └── protocols/                    # 思考协议模板
│       ├── pper-protocol.md          # 完整四阶段协议
│       ├── otav-protocol.md          # 轻量 Observe-Think-Act-Verify
│       └── react-protocol.md         # 探索型 Thought-Action-Observation
└── scripts/
    ├── validate-trigger.py           # L1 触发词自动验证
    ├── fusion-analyzer.py            # 融合兼容性自动评分
    └── check-updates.py              # 源仓库更新检测
```

---

## 使用示例

### 创建新技能

```
User: "帮我创建一个数据库迁移技能"
→ Luzzy-Skill-Architect 激活
→ Phase 1-2: 意图捕获 + 结构设计
→ Phase 3: 产出 db-migration/SKILL.md + references/{postgres,mysql}.md
→ Phase 4: 验证 description 触发准确率
→ Phase 5: 迭代至 L3 成熟度
```

### 审计现有技能

```
User: "审查我的 deploy 技能"
→ 反模式检测：发现 description 泄露执行步骤（AP-1）
→ 成熟度诊断：当前 L1，可升级至 L3
→ 给出具体修复方案和目录重组建议
```

### 融合技能

```
User: "把我的 code-review 和 test-runner 合并成一个 PR-check 技能"
→ Phase 2.5 融合分析：四维评分 100/100 → VERDICT: STRONG
→ 生成 pr-checks/ 编排器 + 保留子技能完整目录
→ 记录源仓库地址，启用自更新机制
```


## Design Philosophy

- **Standards-first**: Only the six standard fields from the agentskills.io spec; vendor extensions are knowledge appendices
- **Structure-driven**: Design the directory tree before writing SKILL.md — never generate a directory you can't justify
- **Self-referential demonstration**: This skill itself perfectly follows every principle it teaches (trigger-only description, dense body format ≤500 lines, progressive disclosure via references/)
- **Progressive guidance**: Teaches progressive disclosure, description trigger theory, and token budget concepts naturally within the workflow

---

## Reference Sources

| Item | Link |
|------|------|
| agentskills.io specification | https://agentskills.io/specification |
| anthropics/skills | https://github.com/anthropics/skills |
| agentskills/agentskills | https://github.com/agentskills/agentskills |
| Claude Code Skills docs | https://code.claude.com/docs/en/skills.md |
| Agent Skills 101 tutorial | https://blog.serghei.pl/posts/agent-skills-101/ |
| Nested skills discussion (#137) | https://github.com/agentskills/agentskills/issues/137 |

---

## Compatibility

- **Target platform**: Fully cross-platform, spec-level
- **Spec version**: agentskills.io open standard
- **Dependencies**: `skills-ref` (optional, for format validation); Python 3.8+ (optional, for trigger scripts)
- **Supported agent platforms**: WorkBuddy, Claude Code, VS Code Copilot, Cursor, Gemini CLI, OpenAI Codex, Windsurf, and more

## Contributing

Issues and PRs are welcome:

1. Fork this repository
2. Create a feature branch: `git checkout -b feature/your-feature`
3. Ensure self-validation passes: `python scripts/validate-trigger.py .`
4. Follow the project's [Design Philosophy](#design-philosophy) and [anti-patterns reference](references/anti-patterns.md)
5. Submit a PR describing your changes

Before submitting, confirm no new anti-patterns were introduced.

## License

Apache 2.0 — see the LICENSE file in the repository (if not included, refer to https://www.apache.org/licenses/LICENSE-2.0).
