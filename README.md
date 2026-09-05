# ZYMCT 主站

[zymct.com](https://zymct.com) 的纯静态网站，页面、样式和脚本均位于 `index.html`，无需安装依赖或编译。

## 发布

GitHub 仓库：[CodeZephyer/zymct](https://github.com/CodeZephyer/zymct)。`main` 分支用于自动发布到现有 Cloudflare Pages 项目 `zymct`。

Cloudflare 构建设置：

- 框架预设：无（None）
- 生产分支：`main`
- 构建命令：`mkdir -p dist && cp index.html dist/index.html`
- 构建输出目录：`dist`

上述命令仅将首页复制到发布目录，确保只部署 `index.html`。

修改并检查 `index.html` 后，将改动提交到 GitHub 的 `main` 分支；Cloudflare 完成部署后，主站即更新。可在 Cloudflare 的部署记录中查看结果或回退版本。

## 日常更新

可以在 GitHub 网页编辑 `index.html` 并提交到 `main`，也可以在本地修改后提交并推送。仅保存本地文件不会触发发布，必须同步到 GitHub。

在 Cloudflare 的部署详情中核对提交编号与 `success` 状态，再打开 https://zymct.com 查看结果。以后若增加本地图片、CSS 或 JavaScript 文件，需要同时调整构建命令，将这些资源复制到 `dist`。
