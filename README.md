# statgpu website

Public website: <https://statgpu.github.io/>

- [English documentation](https://statgpu.github.io/en/)
- [中文文档](https://statgpu.github.io/cn/)
- [Benchmark dashboard](https://statgpu.github.io/dashboard/)
- [Source project](https://github.com/TheHiddenObserver/statgpu)

This repository publishes the statgpu organization website. Documentation,
frontend code, and benchmark inputs remain in `TheHiddenObserver/statgpu`.
Generated HTML, JavaScript, CSS, search indexes, and benchmark bundles are
built by GitHub Actions and are not committed here.

## Publication source

The current website is pinned to source commit
[`227aca4358c35a73380c7cab965fbff9b334f150`](https://github.com/TheHiddenObserver/statgpu/commit/227aca4358c35a73380c7cab965fbff9b334f150)
from [PR #132](https://github.com/TheHiddenObserver/statgpu/pull/132).
Publishing this revision does not merge the PR or change the source repository.

The deployment builds with `STATGPU_SITE_BASE=/` and
`STATGPU_SITE_URL=https://statgpu.github.io/`. Source and contribution links
continue to point to the source project.

## Build and publish

1. In this repository's **Settings → Pages**, select **GitHub Actions** as
   the publishing source.
2. The deployment workflow runs when its file is updated on `main`, or from
   **Actions → Deploy statgpu organization website → Run workflow**.
3. The workflow builds and verifies both URL bases, checks reproducibility and
   source cleanliness, runs the dashboard and Chromium/Firefox/WebKit browser
   suites, then publishes one artifact to GitHub Pages.

Upstream pushes and PR merges do **not** automatically update this website.
To publish another reviewed revision, update both full source commit pins in
`.github/workflows/deploy.yml` to the same SHA, update the revision above, and
commit the change to this repository. Re-running a workflow republishes its
pinned revision.

Build jobs receive read-only repository access. Only the deployment job gets
`pages: write` and `id-token: write`. No personal access token, repository
secret, or global workflow-permission change is needed.

## 中文说明

本站发布在 <https://statgpu.github.io/>，文档、前端代码和基准数据仍在
[`TheHiddenObserver/statgpu`](https://github.com/TheHiddenObserver/statgpu)
维护。当前发布固定使用上方的完整提交 SHA，不会合并 PR #132。

源项目的推送或合并不会自动更新网站。发布新版本时，应将部署工作流中的
两个源代码提交 SHA 同步更新为已检查的版本，并更新此页的版本记录。
也可以在本仓库 Actions 页面手动运行工作流，重新发布当前固定版本。

工作流使用 GitHub 自带的临时令牌，只有发布任务获得 Pages 发布权限；
不需要创建或保存个人访问令牌。
