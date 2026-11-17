# AI 中转站排行 · AI API 中转站公开快照

AI 中转站排行公开快照由 Folkbench 维护，每天按模型整理 API中转线路的公开榜单，覆盖 Claude / GPT / Gemini 中转站等常见模型。想找中转站推荐时，可以先在这里按模型查看各家中转站的来源名次、可用率和公开价格，再进入主站档案核对细节。

本站由 Folkbench 维护，发布地址为 https://folkbench.github.io/relay-rank/ 。

唯一数据源是 [folkbench-data](https://github.com/Folkbench/folkbench-data) 的已校验归档。排序沿用主站规则，包含合作档位与运营加分；部分数据为展示样本。本页提供公开快照，不是原始运行记录；部分数据为展示样本。

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

## 兜底发布与 IndexNow

- 原定时任务保持不变，另有两个入口：数据仓库归档成功后的 `repository_dispatch`（`public-snapshot-archived`）通知，以及北京时间 23:35 的备用定时。自动触发时，如果线上 `publish-state.json` 已经是最新快照，就直接结束，不重复发布。
- 自动发布失败时，本仓库会开一个「公开快照站点自动发布失败」issue，之后发布成功会自动关闭。
- 配置仓库变量 `INDEXNOW_KEY` 后，发布产物输出 `/relay-rank/{key}.txt`；部署成功后，把 sitemap 中 lastmod 等于本次归档日期的 URL 推送到 IndexNow。推送失败只记日志，不影响发布结果。

## 其它公开快照视图

- [中转站检测周报](https://folkbench.github.io/integrity-weekly/)：模型身份探针的每周汇总
- [AI 中转站对比](https://ai-relay-bench.github.io/)：同一模型在各中转站的并排对比
- [AI API 价格对比](https://aiapi-rank.github.io/)：中转站公开标价与官方参考价
- [AI 中转站大全](https://ai-zhongzhuan.github.io/)：站点目录、公开资料与新手指南
- [模型检测快照](https://ai-model-check.github.io/)：每日模型身份探针汇总
