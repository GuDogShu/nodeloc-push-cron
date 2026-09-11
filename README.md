# nodeloc-push-cron

用 GitHub Actions 的定时任务，每 5 分钟触发一次 NodeLoc 站点（`user.nodeloc.nl`）的定时推送接口。

- 触发地址：`https://user.nodeloc.nl/cron/push.php`
- 密钥保存在本仓库的 **Actions Secret**（`CRON_KEY`），不写在代码里。
- 本仓库仅负责「到点敲门」；实际推送间隔由站点设置页的配置决定。

## 说明

- GitHub 的 `schedule` 是尽力而为：高峰期可能有几分钟延迟，极端情况下会被跳过。
- 仓库若连续 60 天无活动，定时工作流会被 GitHub 自动禁用，因此内置了每月一次的保活提交。
- 公开仓库的 Actions 执行时间完全免费且无额度上限。
