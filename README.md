# ZYMCT 主站

[zymct.com](https://zymct.com) 的纯静态网站，无需安装依赖或编译。主站入口位于 `index.html`，作者介绍页位于 `about/index.html`，相关静态资源存放在各自的 `assets/` 目录中。

## 发布

GitHub 仓库：[CodeZephyer/zymct](https://github.com/CodeZephyer/zymct)。`main` 分支用于自动发布到现有 Cloudflare Pages 项目 `zymct`。

Cloudflare 构建设置：

- 框架预设：无（None）
- 生产分支：`main`
- 当前构建命令：`mkdir -p dist && cp index.html dist/index.html`
- 构建输出目录：`dist`

仓库同时保留完整的 `dist/` 发布目录，因此现有 Cloudflare 设置无需立即修改，也能发布主站、作者页和静态资源。Cloudflare Pages 支持子目录页面，每个页面目录使用自己的 `index.html` 即可。

后续若能修改 Cloudflare 构建设置，建议将构建命令更新为 `mkdir -p dist && cp index.html dist/index.html && cp -R about assets dist/`，从源目录自动刷新完整发布内容。

修改并检查 `index.html` 后，将改动提交到 GitHub 的 `main` 分支；Cloudflare 完成部署后，主站即更新。可在 Cloudflare 的部署记录中查看结果或回退版本。

## 日常更新

可以在 GitHub 网页编辑 `index.html` 并提交到 `main`，也可以在本地修改后提交并推送。仅保存本地文件不会触发发布，必须同步到 GitHub。

在 Cloudflare 的部署详情中核对提交编号与 `success` 状态，再打开 https://zymct.com 查看结果。更新作者页时，需要同步刷新 `about/` 和 `dist/about/`；以后若增加新的顶层页面或资源目录，也需要一并放入 `dist/`。
