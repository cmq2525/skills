# cmq2525/skills

cmq2525 的工作技能集合，支持通过 Claude Code 的 `/plugin` 命令一键安装。目前已有的 skill 以技术岗位简历筛选为主，未来会持续扩展。

## 安装方法

在 Claude Code 中运行以下命令添加市场并安装插件：

```
/plugin marketplace add cmq2525/skills
/plugin install cmq-work-skills@cmq-skills
```

安装完成后，上传候选人简历（PDF/Word/文本）并说"帮我筛选这份简历"，Claude 将自动调用对应的 skill 进行评估。

## 包含技能

### reinforcement-learning-recruiter

专为筛选强化学习（RL）工程师简历设计。根据 Agentic RL 方向的岗位描述评估候选人，重点考察分布式系统、安全沙箱/容器、强化学习框架（verl/slime/Areal）及分布式 RL 训练经验，生成包含五维度评分、评分理由和潜在疑点的结构化报告。

**评分维度**：工程与系统构建（30%）、分布式系统与 K8s（25%）、安全容器与沙箱隔离（10%）、强化学习框架与分布式训练（25%）、加分项（10%）

### llm-infra-recruiter

专为筛选大模型基础设施（LLM Infra）工程师简历设计。重点考察国产算力（昇腾/沐曦/摩尔线程）算子开发经验（硬性门槛）、分布式并行训练与通信优化、性能分析与故障诊断能力，生成包含五维度评分、评分理由和潜在疑点的结构化报告。

**评分维度**：国产算力算子开发（35%）、分布式并行训练与通信优化（30%）、性能分析与故障诊断（15%）、工程基础与系统能力（10%）、加分项（10%）

## 目录结构

```
.
├── .claude-plugin/
│   ├── plugin.json          # 插件清单
│   └── marketplace.json     # 市场目录
├── skills/
│   ├── reinforcement-learning-recruiter/
│   │   ├── SKILL.md                              # 技能定义
│   │   └── reinforcement_learning_engineer_jd.md # 原始 JD
│   └── llm-infra-recruiter/
│       ├── SKILL.md                              # 技能定义
│       └── llm_infra_engineer_jd.md              # 原始 JD
└── README.md
```

## 开发说明

本插件遵循 Claude Code 官方插件规范：

- 插件配置文件位于 `.claude-plugin/plugin.json`
- 市场目录文件位于 `.claude-plugin/marketplace.json`
- 所有技能存放在 `skills/` 目录下，每个技能拥有独立的子目录和 `SKILL.md` 文件
- 每个技能目录下附有对应的原始 JD 文件，供评估时交叉验证使用
