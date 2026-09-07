# Xinyuan Liao 个人学术主页

纯静态个人主页（HTML + CSS + 原生 JS，无框架、无构建步骤），为 GitHub Pages 设计。

## 本地预览

```bash
cd personal-website
python -m http.server 8000
# 浏览器打开 http://localhost:8000
```

直接双击 `index.html` 也可以预览（本地字体与滚动动画略有差异，不影响部署效果）。

## 部署到 GitHub Pages（约 2 分钟）

**方式 A：命令行（推荐）**

1. 在 GitHub 网页上新建仓库，名字用 **`<你的用户名>.github.io`**（例如 `xnyua.github.io`），Public，不要勾选 README 初始化。
   - 这样主页地址就是 `https://<你的用户名>.github.io/`，顶级域名，最干净。
   - 如果这个名字已被占用或你想放在子路径，随便起名（如 `homepage`），主页地址为 `https://<你的用户名>.github.io/homepage/`。
2. 在本目录（`personal-website`）执行：

   ```bash
   git remote add origin https://github.com/<你的用户名>/<仓库名>.git
   git push -u origin main
   ```

   （本目录已 `git init` 并完成首次提交，直接 push 即可；Windows 上首次 push 会弹出 GitHub 登录窗口，登录一次即可。）
3. 仓库页 **Settings → Pages**：Source 选 `main` 分支 `/ (root)`，保存。约 1–2 分钟后生效。

**方式 B：网页上传（不想用命令行）**

GitHub 仓库页 → "uploading an existing file" → 把本目录所有文件（含 `.nojekyll`）拖进去提交，再按第 3 步开启 Pages。

> 若想用自定义域名（如 `xiaoliao.dev`）：仓库 Settings → Pages → Custom domain 填入，并在域名 DNS 加一条 CNAME 记录指向 `<用户名>.github.io`。

## 日常更新

| 想改什么 | 改哪里 |
|---|---|
| 头像照片 | 放一张方形照片到 `assets/photo.jpg`（≥512×512），自动替换字母头像 |
| News | `index.html` 中 `<ul class="news-list">`，最新在上 |
| 论文 | `index.html` 中 `<!-- ============ Publications ============ -->` 一节，按年份分组复制一个 `<li class="pub">` 即可 |
| 联系方式 | 页面中搜索 `xin-yuan.liao@connect.polyu.hk` |
| 主题配色 | `css/style.css` 顶部的 CSS 变量（`--accent` 为主色，现为理大红） |

## 待办清单（页面里已用 TODO 注释标出）

1. **GitHub 链接**：`index.html` 中搜索 `YOUR-USERNAME`，填入你的 GitHub 用户名并去掉外层 HTML 注释。
2. **PE-ETT（TPEL 在投）**：论文公开后在 Publications 的 "Under Review" 注释块里填入正式标题并取消注释；录用后改为对应期刊 badge。
3. **公司英文名**：三峡智控、陕汽的官方英文名如有出入请更正（Experience 一节）。
4. 隐私说明：手机号**没有**放上主页（学术主页公开电话会招骚扰），如确实需要可自行加。

> 论文条目的标题、作者、DOI 均已通过 Crossref + ORCID 双源核实（2026-09），含 ORCID 主页链接。

## 目录结构

```
personal-website/
├── index.html          # 全部内容（About/News/Experience/Publications）
├── css/style.css       # 样式（亮/暗双主题，响应式）
├── js/main.js          # 主题切换、移动端菜单、滚动高亮、入场动画
├── assets/             # favicon.svg、avatar.svg（字母头像占位）、photo.jpg（放入后自动生效）
├── .nojekyll           # 跳过 GitHub Pages 的 Jekyll 处理
└── README.md
```
