# my-skills



## Skills

| Skill | 触发方式 | 说明 |
|-------|---------|------|
| [clarify](https://github.com/dulk-dev/my-skills/blob/master/clarify/SKILL.md) | `clarify` / `clarify scope` / `interview requirements` | 代码感知的采访式需求澄清。逐条化解决策分支，通过结构化问答把模糊需求推进到可执行范围，由用户决定结束时机。 |
| [duck](https://github.com/dulk-dev/my-skills/blob/master/duck/SKILL.md) | `duck` / 追踪数据流 / 排查 bug / 理解陌生代码 / 评估方案 | 小黄鸭调试法。用向初学者解释的方式逐步说清问题与上下文，暴露盲点与隐藏假设，定位预期与实际行为的分歧点。 |
| [find-repos](https://github.com/dulk-dev/my-skills/blob/master/find-repos/SKILL.md) | `find repos` / 找参考仓库 / 从零实现常见功能 / 按代码找实现 | 查找并评估开源参考项目。GitHub CLI + WebSearch 检索候选，Grep MCP 按代码字面量反查真实实现，输出 3～5 个评估后的候选并推荐一个，不自动 clone。 |

## 安装

通过 [skills.sh](https://skills.sh) 安装：

```bash
npx skills add dulk-dev/my-skills
```

或本地克隆后加载：

```bash
git clone https://github.com/dulk-dev/my-skills.git
# 然后在 Agent 中通过 /skill 命令加载对应 SKILL.md
```

## License

MIT
