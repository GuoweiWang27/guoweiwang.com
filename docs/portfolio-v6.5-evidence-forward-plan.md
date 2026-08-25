# Portfolio V6.5 — "Evidence Forward" 点睛式改稿方案

> 制定：洋米（2026-08-25）｜ 状态：**已实施**（主人确认方案 A 并提供联系邮箱后落地）
> 前置诊断：V6 全页审查（桌面 1440 / 移动 390 截图 + 源码通读）发现的最强证据沉底、Chapter 03 名不副实、占位符上线、Awards 孤行等问题。

## 1. 背景与决策

V6 的叙事骨架（研究 → film → 社区）保留，但审查发现：

- 4 个 live 工具与开源列表沉到第 9 屏（约 80% 滚动深度），招生官阅读窗口内看不到任何可交互作品；
- Chapter 03 叫 "Projects / For Everyone"，实际内容是领导力+社区，真正 build 的东西不在其中；
- 3 张卡片配图是带制作说明的占位块，观感像未完工；
- Awards 9 项 4 列存在孤行，且无年份。

主人拍板（2026-08-25）：**方案 A「点睛式」**——证据前移、索引留底，不动章节顺序；联系邮箱定为 `guoweiwang27@gmail.com`。

核心原则：**证据前移（tease early），索引留底（index late）**。Network 底部区保持完整 sitemap 角色，与新的 #work 条带是「预告 vs 索引」关系，不算重复。

## 2. 改动清单（C1–C7）

| # | 位置 | 改动 | 状态 |
| --- | --- | --- | --- |
| C1 | Hero | 主按钮 → `Explore My Work →`（锚 `#work`）；次按钮保留 Get in Touch；移除 Read My Story | ✅ |
| C2 | About 后新增 `#work` | "The Build / Open one. It runs." 条带：GlyUp · ChemAI Pro · BatteryChem-AI Web · Teardown 四张 mini 卡（真实截图 + 一句话 + Live/GitHub），4→2→1 列响应式 | ✅ |
| C3 | Chapter 03 | 更名 `Leadership & Community`；ChemAI Pro 卡移除（并入 #work）；3 卡改 3 列；3 个占位图块收掉变纯文字卡（CSS 保留，真图就位可加回） | ✅ |
| C4 | Nav | 加 `Work`；`Projects` → `Community`；scroll-spy 自动覆盖 | ✅ |
| C5 | Awards | 4 列 → 3 列 ×3 行去孤行；9 项补年份；≤1024px 两列时末项奇数跨全宽 | ✅ |
| C6 | head / 技术 | og:image 换 `og-cover.jpg` 1200×630（film-hero 横裁）；JSON-LD Person；`sitemap.xml`；Vercel Analytics 脚本位；产品名统一 ChemAI Pro | ✅ |
| C7 | 不动 | Research / Film 章节、Network 完整索引、footer、设计系统与动效 | ✅ |

## 3. Awards 年份依据（Vault AWD 事实卡，2026-08-20 口径）

| 奖项 | 年份 | 依据 |
| --- | --- | --- |
| GENIUS Olympiad · Short Film Honorable Mention | 2026 | 主页既有口径 + 事实审计 |
| UK Chemistry Olympiad · Round One Gold | 2026 | AWD-03（58th annual，2026-01-28 考试） |
| National Yingcai Program · PKU | 2025 | AWD-01（2025 年度入选） |
| Regeneron ISEF CHN011 · Round 3 | 2026 | AWD-08（Grade 11，禁用 ISEF Finalist） |
| Xicheng District S&T Contest · 1st Prize | 2025 | AWD-09（2025 年区赛一等奖） |
| PKU Research · First-Author Manuscript | 2026 | 在审（NHSJS，never published） |
| AP Capstone Diploma | 2026 | AWD-05（Grade 11 获得） |
| AP Scholar with Distinction | 2026 | AWD-06（Grade 11 获得） |
| Principal's Honor · Top 10% by GPA | 2026 | AWD-07（一次 2026 荣誉，旧口径停用） |

## 4. 新增资产

| 文件 | 来源 | 用途 |
| --- | --- | --- |
| `images/work-glyup.webp` 等 4 张 | 2026-08-25 Playwright 现场截取四个 live 站点（800×500 @2x → webp q84） | #work 条带卡图 |
| `images/og-cover.jpg` | `film-hero-tengger.webp` 中心横裁 1200×630（JPEG q86，36KB） | og:image / Twitter 卡 |
| `sitemap.xml` | 新建 | SEO |

`images/chemai-app.webp` 随 ChemAI Pro 卡移除暂不再引用，文件保留备用。

## 5. 遗留与后续

- **Vercel Web Analytics**：脚本位已加（`/_vercel/insights/script.js`），需主人在 Vercel dashboard 开启 Web Analytics 才收数；建议观察 2–4 周滚动深度数据，再决定是否升级方案 B（Builder 升第一章）。
- **LinkedIn / Resume PDF / Gallery lightbox**：仍挂起，见源码头部 tracker。
- **GlyUp 期刊口径不一致（2026-08-25 发现）**：GlyUp 站显示 JEI（Journal of Emerging Investigators），主页与 Vault 审计口径为 NHSJS。**待主人确认哪个是当前事实**，确认前两边都未改动。
- 占位卡变纯文字后，若拿到真实照片（club / bike prototype / e-bike walkthrough），可恢复 `.project-card__photo` 图区。

## 6. 验证记录

- 2026-08-25：HTML 标签平衡 ✅（html.parser 全树校验 NONE）；内部锚点 8/8 解析 ✅；外链 15 条全 200 ✅（fonts 两域根 404 为 preconnect 正常现象）；JSON-LD 解析 ✅；本地 Playwright 桌面 1440 + 移动 390 全页与 #work 区块截图复验 ✅
