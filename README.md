# Guowei Home

`guoweiwang.com` 个人总入口主页的工程仓库。

- GitHub：`https://github.com/GuoweiWang27/guoweiwang.com`
- 线上（GitHub Pages 预览通道）：`https://guoweiwang27.github.io/guoweiwang.com/`
- 生产地址（待 Vercel 接管根域）：`https://guoweiwang.com`

## 当前版本

**Portfolio V6「One-Stop Network」（生产版）**

- `index.html`：V6 正式版——Catalyst Signature 视觉签名 + `#explore` 一站式网络章节
  （Open Source 代码真源区块前置 + 6 张产品卡片），GreenBatty / ChemAI101 / GitHub
  真实链接已接通，Nav 含 Explore 锚点，Footer 含站点目录行。
- `images/HeroPhoto.webp`：首屏优化图片。
- `docs/portfolio-v4-plan.md`：V4 设计与内容计划。
- `docs/portfolio-v5-catalyst-signature-plan.md`：V5 视觉签名实施方案。
- `docs/portfolio-v6-one-stop-plan.md`：V6 方案与仓库审计记录（含主人拍板结论）。

页面内仍保留少量上线前素材 tracking（Resume/PDF/视频/邮箱/LinkedIn 占位），
补齐方式见 `docs/portfolio-v6-one-stop-plan.md` §6。

## 定位

- 统一入口：摄影、STEM 项目、申请展示和实验项目。
- 对外第一屏：Guowei Wang 的个人网站首页。
- 后续其他主页版本与模块以本仓库为合并入口。

## 本地预览

```bash
python3 -m http.server 4173
```

打开 `http://127.0.0.1:4173/`。

## 部署

- 现阶段：GitHub Pages 从 `main` 分支根目录发布，push 即上线（约 1 分钟生效）。
- 目标状态：Vercel 导入本仓库接管 `guoweiwang.com` 根域 + www，Pages 预览通道保留。
  操作步骤见 `/Users/yimu/Documents/Guowei/Engineering/docs/maintenance-guide.md`。

## 来源

V4/V5 原稿与方案保留在 `/Users/yimu/WorkBuddy/大米空间/`，本目录自 V4 迁移起作为工程真源。
