# Folkbench 中转站公开快照专题站

本站由 Folkbench 维护，发布地址为 https://folkbench.github.io/relay-rank/ 。

唯一数据源是 [folkbench-data](https://github.com/Folkbench/folkbench-data) 的已校验归档。排序沿用主站规则，包含合作档位和运营加分；部分数据为展示样本，不承诺全部真实实测或可复算。

首页按模型展示最多五条符合来源筛选条件的记录；模型页展示其余公开记录及已有历史；站点页涵盖全量公开目录。缺失日期不补造。

[主站榜单](https://folkbench.com/rankings?utm_source=github&utm_medium=pages&utm_campaign=relay-board&utm_content=repo-about) · [方法说明](https://folkbench.com/methodology?utm_source=github&utm_medium=pages&utm_campaign=relay-board&utm_content=repo-methodology)

## 运维

- `FOLKBENCH_TOOLING_SHA` 固定为已审核的 Folkbench/folkbench 工具提交完整 SHA。
- 数据归档跑通后启用 `PUBLIC_DISTRIBUTION_ENABLED=true`，Pages 使用 GitHub Actions 来源。
- 构建使用公开仓库 `scripts/distribution/cli.ts relay-site`；失败不覆盖当前部署。
- 所有回到主站的链接使用 github / pages / relay-board 的 UTM；不使用商业跳转。
- 默认不采集 github.io 站内访问量，不创建新的统计项目；回到主站后沿用现有 PostHog 归因。
- 搜索验证可配置 GOOGLE_SITE_VERIFICATION、BING_SITE_VERIFICATION、BAIDU_SITE_VERIFICATION，均为公开验证标记；登录与 sitemap 提交由维护者完成。
- 正常 Git hooks 需要 `FOLKBENCH_DISTRIBUTION_TOOL_ROOT` 指向上述固定版本的公共工具工作区，并设置 `core.hooksPath=.githooks`。

## 徽章

```markdown
[![公开快照](https://folkbench.github.io/relay-rank/badge.svg)](https://folkbench.github.io/relay-rank/)
```
