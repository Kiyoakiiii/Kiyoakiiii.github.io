# Hanwen Chen — Personal Homepage

单页静态网站，没有构建步骤，直接部署到 GitHub Pages。

```
homepage/
├── index.html      # 整个网站（HTML + CSS + 一点 JS 用于深色模式切换）
├── files/          # 简历 PDF（页面上的 CV 按钮链接到这里）
└── .nojekyll       # 告诉 GitHub Pages 不要用 Jekyll 处理
```

## 部署到 GitHub Pages

1. 在 GitHub 新建一个**公开**仓库，名字必须是 `Kiyoakiiii.github.io`（用户名 + `.github.io`，大小写不敏感）。
   不要勾选 "Add a README"，保持空仓库。
2. 在本文件夹里执行：

   ```bash
   cd homepage
   git init -b main
   git add .
   git commit -m "Initial homepage"
   git remote add origin https://github.com/Kiyoakiiii/Kiyoakiiii.github.io.git
   git push -u origin main
   ```

3. 打开仓库的 **Settings → Pages**，确认 Source 是 "Deploy from a branch"，Branch 选 `main` / `/ (root)`。
4. 等 1–2 分钟后访问 <https://kiyoakiiii.github.io>。

## 以后怎么更新

改 `index.html`（或替换 `files/` 里的 PDF），然后：

```bash
git add .
git commit -m "Update homepage"
git push
```

推送后一两分钟网站就会更新。

## 可选

- **自定义域名**：买域名后在 Settings → Pages → Custom domain 填写，并在域名服务商处添加 CNAME 记录指向 `kiyoakiiii.github.io`。
- **头像**：把照片放到 `files/avatar.jpg`，在 `index.html` 的 `<h1>` 前加一行 `<img src="files/avatar.jpg" alt="Hanwen Chen" style="width:96px;height:96px;border-radius:50%;object-fit:cover;margin-bottom:20px">`。
- **隐私**：`files/` 里的简历 PDF 包含电话号码，公开发布后任何人都能下载。如果不想公开电话，先在 `.tex` 里删掉电话那一行，重新编译 PDF 再放进来。
