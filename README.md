# Personal Website (GitHub Pages + al-folio)

这个仓库已经初始化为一个可部署的个人网站，基于 [al-folio](https://github.com/alshedivat/al-folio)。

## 你现在需要做的 4 件事

1. 修改站点地址配置：`_config.yml`
   - `url: https://YOUR_GITHUB_USERNAME.github.io`
   - `baseurl: ""`（如果仓库名是 `<username>.github.io`）
   - 如果你用项目仓库（比如 `my-site`），则改成 `baseurl: "/my-site"`

2. 填写个人信息
   - 首页文案：`_pages/about.md`
   - 社交账号：`_data/socials.yml`
   - 头像：`assets/img/prof_pic.jpg`

3. 添加你的项目
   - 项目列表页：`_pages/projects.md`
   - 项目内容：`_projects/0_featured_project.md`（可复制新增更多）

4. 推送并发布到 GitHub Pages
   - 把仓库推送到 GitHub
   - 进入 `Settings -> Actions -> General -> Workflow permissions`，开启 **Read and write permissions**
   - 进入 `Settings -> Pages -> Build and deployment`
   - Source 选择 **Deploy from a branch**
   - Branch 选择 **gh-pages / (root)**
   - 推送到 `main` 后会自动构建并发布

## 当前默认结构

- `/` 首页 About
- `/projects/` 项目页
- 其他示例页面已从导航隐藏（可按需开启）

## 本地预览（可选）

```bash
bundle install
bundle exec jekyll serve
```

然后打开 `http://127.0.0.1:4000`。
