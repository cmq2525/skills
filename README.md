# skills

招聘相关技能集合，支持通过 Claude Code 的 `/plugin` 命令一键安装。

## 安装方法

在 Claude Code 中运行以下命令安装本插件：

```
/plugin install cmq/skills
```

或者手动添加到插件市场后安装：

```
/plugin marketplace add cmq/skills
/plugin install recruitment-skills@cmq/skills
```

## 包含技能

### reinforcement-learning-recruiter

专为筛选强化学习（RL）工程师简历设计。根据强化学习相关岗位描述（JD）评估候选人简历，重点评估候选人在分布式系统、安全沙箱/容器、强化学习框架等方向的经验，生成包含多维度评分、评分理由和潜在疑点的结构化评估报告。

**使用方法**：在 Claude Code 中加载插件后，上传简历文件（PDF/Word/文本）并要求评估候选人即可。

## 目录结构

```
.
├── .claude-plugin/
│   └── plugin.json          # 插件清单
├── skills/
│   └── reinforcement-learning-recruiter/
│       └── SKILL.md         # 技能定义
└── README.md
```

## 开发说明

本插件遵循 Claude Code 官方插件规范：
- 插件配置文件位于 `.claude-plugin/plugin.json`
- 所有技能存放在 `skills/` 目录下
- 每个技能拥有独立的子目录和 SKILL.md 文件
