# Evans 的 Hexo 博客

文章位于 `source/_posts/`。修改文章时，从 `main` 创建分支并提交 Pull Request。PR 会运行 Hexo 构建检查；合并到 `main` 后，GitHub Actions 将 `public/` 作为 Pages artifact 发布。

本地预览：

```bash
npm ci
npm run clean
npm run build
npm run server
```

`public/` 是生成目录，不提交到仓库。网站使用 A4 主题，配置分别在 `_config.yml` 与 `_config.a4.yml`。

首次启用自动发布时，在仓库的 **Settings → Pages → Build and deployment → Source** 选择 **GitHub Actions**。先切换发布源，再合并本次迁移 PR。旧的 `source` 分支只作为历史备份，以后文章 PR 以 `main` 为目标。
