# interview-prep-skill

一个面向 Hermes、OpenClaw、Codex 等智能体运行环境的面试准备 Skill。

核心能力：基于岗位说明和候选人背景/简历，生成完整的面试准备报告，包括岗位拆解、匹配度分析、职业规划建议、面试问题预测、面试反问问题、面试建议，以及1-2分钟中英文自我介绍。

## 目录结构

```text
skill/interview-prep-coach/
├── SKILL.md
├── agents/
│   ├── openai.yaml
│   ├── hermes.yaml
│   └── openclaw.yaml
├── assets/
└── references/
```

第一版 Skill 只把核心逻辑放在 `SKILL.md` 中。`agents/` 只保留轻量适配信息，不重复实现 Skill 逻辑。`assets/` 和 `references/` 暂时保留为空目录，后续在真实使用中发现稳定模板或专项参考资料确实有价值时再补充。

## Codex 使用方式

把 Skill 文件夹复制到 Codex skills 目录：

```bash
mkdir -p ~/.codex/skills
cp -R skill/interview-prep-coach ~/.codex/skills/
```

示例调用：

```text
使用 $interview-prep-coach 基于以下岗位说明和候选人背景，生成一份完整的面试准备报告。
```

## Hermes/OpenClaw 使用方式

本 Skill 的核心入口是：

```text
skill/interview-prep-coach/SKILL.md
```

如果运行环境需要 manifest，可以参考 `agents/hermes.yaml` 或 `agents/openclaw.yaml`，但应始终以 `SKILL.md` 作为唯一逻辑来源。
