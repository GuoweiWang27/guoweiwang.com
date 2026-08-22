# Portfolio v6 — "One-Stop Network" 改稿方案（草稿待审）

> 制定：洋米（2026-08-22）｜ 状态：**草稿，未部署，等主人过目**
> 草稿文件：`index-v6-one-stop.html`（V5 `index.html` 原样保留，可随时对比/回退）

---

## 1. 目标

把 `guoweiwang.com` 从「个人展示页」升级为「一站式总入口」：访客（招生官/评委/任何人）从主页一屏之内可以到达国维的**每一个线上资产**——全部站点应用 + 全部 GitHub 源码。

设计原则延续 V5「Catalyst Signature」：只做加法，不动骨架、字体、配色体系；新章节复用现有 token（暗色收尾 + 沙金色 + 衬线标题）。

## 2. 改动清单

| # | 位置 | 改动 |
| --- | --- | --- |
| E1 | `<head>` | meta description 加入 "One-stop hub" 表述 |
| E2 | 链接追踪注释 | 已接通的链接标记 `[x]` 并记录真实 URL；新增「子域收编后待替换 URL」清单 |
| E3 | Nav | Projects 与 Honors 之间加 `Explore` 锚点（scroll-spy 自动生效） |
| E4 | Research · GreenBatty 卡片 | Live Demo → `guoweiwang27.github.io/BatteryChem-AI-Web/`；GitHub → `GuoweiWang27/BatteryChem-AI` ⚠️ 见 §4 假设 |
| E5 | Projects · ChemAI101 卡片 | Try It → `chemai101.pages.dev/`；GitHub → `GuoweiWang27/ChemAI101` |
| E6 | **新增章节 `#explore`（The Network）** | Awards 之后、Contact 之前的暗色章节：6 张站点卡片 + 7 个开源仓库列表 + profile 链接；含催化反应式点缀（research + code + film → one stop）；完整响应式（3→2→1 列，移动端仓库行重排为两行 grid-area 布局） |
| E7 | Contact | GitHub 按钮接通真实 profile（原 TODO 占位移除） |
| E8 | Footer | 新增 mono 小字目录行：photo. · glyup. · chemai101. · batterychem · teardown · @GuoweiWang27 |

## 3. 站点目录（Explore 区收录范围）

**有意排除**：`math.guoweiwang.com`（小米数学站，非国维申请资产，不宜出现在申请主页上）。若将来要收录再加一行卡片即可。

| 卡片 | 目标地址 | 类型标签 |
| --- | --- | --- |
| GlyUp | https://glyup.pages.dev/ | Research Demo |
| ChemAI Pro | https://chemai101.pages.dev/ | AI Tool |
| BatteryChem-AI Web | https://guoweiwang27.github.io/BatteryChem-AI-Web/ | Interactive Model |
| Teardown.ai | https://guoweiwang27.github.io/Teardown/ | 3D Experience |
| G.W. Photograph | https://photo.guoweiwang.com/ | Photography |
| Start at GitHub | https://github.com/GuoweiWang27 | Open Source |

仓库列表（7 个全收）：BatteryChem-AI (Python) / BatteryChem-AI-Web (JavaScript) / ChemAI101 (TypeScript) / GlyUp (TypeScript) / Teardown (Three.js) / ChemAI (Prototype) / my-car-game (First Repo)。

## 4. 待确认假设 ⚠️

1. **GreenBatty ↔ BatteryChem 映射**：主页 GreenBatty 卡片（丘奖叙事：5000+ 多酚筛选电解液添加剂）我接到了 BatteryChem-AI / BatteryChem-AI-Web 两个仓库。两者主题同族但表述不同（配方筛选 vs 添加剂筛选）。**需要主人或国维确认这是同一个项目的两个阶段，还是不同项目**。若是后者，GreenBatty 的按钮应改回 TODO 或指向别的地址。
2. 子域规划名（lab. / chemai101. / battery. / teardown.）仅为建议，定稿后在 Cloudflare 绑定时确定，再回来改 Explore 卡片的 URL 文案。

## 5. 仍然挂起的链接（上线前必须补齐）

- [ ] Resume PDF
- [ ] Paper PDF（GlyUp 展示站已有内容，PDF 可后补）
- [ ] 化学社视频 1 / 视频 2
- [ ] 联系邮箱（TODO@example.com）
- [ ] LinkedIn
- [ ] About 照片 / Research 照片 / Film 剧照 / BTS 图库（占位块仍在）

## 6. 验证记录（2026-08-22）

- HTML 标签平衡检查 ✅；内部锚点除 6 个有意保留的 TODO 外全部可达 ✅
- 17 个外链全部为已探测在线的真实地址 ✅
- 本地 `python3 -m http.server 4173` 双页面 200 ✅
- Playwright 截图验证：桌面 1440px（Explore 卡片区 + 仓库区 + Contact 衔接）、移动 390px（单列卡片 + 公式换行 + 仓库两行布局）✅

## 7. 通过后的落地顺序

1. 主人确认草稿（含 §4 假设）→ 把 V6 内容合并进 `index.html`（V5 归档到 git 历史）
2. `sites/home` 建 GitHub 远端 → Vercel 新项目部署 → 根域/www 切给该项目；photo 项目解绑根域
3. 子域收编（Cloudflare Pages 自定义域 ×2 + GitHub Pages 自定义域 ×2），回改本页 4 处 URL
4. 更新 Engineering `site-map.md`
