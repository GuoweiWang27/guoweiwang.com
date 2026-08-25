# Portfolio v6 — "One-Stop Network" 改稿方案（草稿待审）

> 制定：洋米（2026-08-22）｜ 状态：**草稿，未部署，等主人过目**
> 草稿文件：`index-v6-one-stop.html`（V5 `index.html` 原样保留，可随时对比/回退）
> 修订：2026-08-22 二稿——按主人决定调整展示策略（GitHub 代码真源前置、Teardown 只留开源、my-car-game / 数学站不露出）

---

## 1. 目标与展示策略（主人已定调）

- **GitHub = 代码真源**，在主页上以醒目的「Open Source & Code」区块单独提出，放在 Explore 区**第一位**。
- 主页产品卡片只放**点开就能用的网页端**（To C），不放纯代码仓库的网页壳。
- Teardown 不做网页卡片，只进开源列表；ChemAI 原型、my-car-game、math.guoweiwang.com 不露出。
- 仓库公开/私有的判断标准是**内容敏感度**，不是「有没有网页版」；部署平台（Vercel/CF Pages）都能从私有仓库部署，私有化不阻塞网页端。

## 2. 改动清单

| # | 位置 | 改动 |
| --- | --- | --- |
| E1 | `<head>` | meta description 加入 "One-stop hub" 表述 |
| E2 | 链接追踪注释 | `[x]` 标记已接通链接；新增展示裁剪记录与子域收编 URL 清单 |
| E3 | Nav | Projects 与 Honors 之间加 `Explore` 锚点（scroll-spy 自动生效） |
| E4 | Research · GreenBatty 卡片 | Live Demo → `guoweiwang27.github.io/BatteryChem-AI-Web/`；GitHub → `GuoweiWang27/BatteryChem-AI` ⚠️ 见 §5 假设 |
| E5 | Projects · ChemAI101 卡片 | Try It → `chemai101.pages.dev/`；GitHub → `GuoweiWang27/ChemAI101` |
| E6 | **新增章节 `#explore`（The Network）** | 暗色章节，结构：**Open Source & Code（4 仓库列表 + profile 链接）→ Try Them Live（6 张产品卡片）**，催化反应式点缀；完整响应式（3→2→1 列，移动端仓库行两行 grid-area 布局） |
| E7 | Contact | GitHub 按钮接通真实 profile |
| E8 | Footer | mono 目录行：photo. · glyup. · chemai101. · batterychem · @GuoweiWang27（teardown 已按主人要求移除） |

## 3. Explore 区收录清单（二稿定稿版）

**Open Source & Code（4 个仓库，全部公开）：**

| 仓库 | 语言 | 定位 |
| --- | --- | --- |
| BatteryChem-AI | Python | 筛选平台核心（网页端的背后） |
| ChemAI101 | TypeScript | Gemini 化学学习助手（Vite+React） |
| GlyUp | TypeScript | 一作论文的催化研究展示应用 |
| Teardown | Three.js | 相机 3D 拆解（只留开源，不做网页卡片） |

**Try Them Live（6 张卡片）：**

| 卡片 | 目标地址 | 类型标签 |
| --- | --- | --- |
| GlyUp | https://glyup.pages.dev/ | Research Demo |
| ChemAI Pro | https://chemai101.pages.dev/ | AI Tool |
| BatteryChem-AI Web | https://guoweiwang27.github.io/BatteryChem-AI-Web/ | Web App |
| G.W. Photograph | https://photo.guoweiwang.com/ | Photography |
| The Solar Shepherd | https://www.youtube.com/watch?v=DwX1_EKxOBU | Film |
| Start at GitHub | https://github.com/GuoweiWang27 | Open Source（CTA 卡） |

**明确不展示：** BatteryChem-AI-Web 仓库行（以 Web App 卡片代替）、ChemAI 原型仓库、my-car-game、math.guoweiwang.com。
> 更新（2026-08-25）：Teardown 于 2026-08-23 启用独立子域 `teardown.guoweiwang.com` 后，按最新状态加入产品卡（现为 7 张卡），本节原"不展示 Teardown 卡"结论作废。

## 4. GitHub 仓库公开/私有审计（建议，待主人拍板）

| 仓库 | 建议 | 理由 |
| --- | --- | --- |
| BatteryChem-AI | 公开 ✅ | 核心研究代码，申请加分项；若担心丘奖评审前创意暴露可临时转私有、出结果后转回 |
| BatteryChem-AI-Web | 公开 ✅ **（已拍板 2026-08-22：保持公开）** | 纯前端无敏感数据；网页留在 GitHub Pages 不动，后续收编到 battery.guoweiwang.com 时再考虑托管平台 |
| ChemAI101 | 公开 ✅ 但**先修 API key** | `VITE_GEMINI_API_KEY` 构建时打进 bundle，公开仓库 + 泄露 key = 任何人可烧配额。修法：key 换新 + Worker 代理转发，再公开宣传 |
| GlyUp | 公开 ✅ | 展示型应用，无敏感数据 |
| Teardown | 公开 ✅ | 按主人决定只做开源代码展示 |
| ChemAI | 建议归档（GitHub Archive） | 被 ChemAI101 取代的原型，不删不展示 |
| my-car-game | 保持现状（公开但不展示） | 纪念意义，无风险；主页不露出即可 |

## 5. 假设确认状态

1. **GreenBatty ↔ BatteryChem 映射**：✅ **已确认（2026-08-22 主人拍板）——是同一个项目**，主页按钮接线维持不变。
2. 子域规划名（lab. / chemai101. / battery.）仅为建议；teardown 按主人决定不绑子域、不做网页卡片，上线绑定时最终定名。

## 6. 仍然挂起的链接（上线前必须补齐）

- [ ] Resume PDF / Paper PDF
- [ ] 化学社视频 1 / 视频 2
- [ ] 联系邮箱（TODO@example.com）/ LinkedIn
- [ ] About / Research / Film 剧照 / BTS 图库照片

## 7. 验证记录

- 2026-08-22 一稿：HTML 标签平衡 ✅；17 外链全在线 ✅；本地 4173 双页 200 ✅；Playwright 桌面 1440 + 移动 390 截图 ✅
- 2026-08-22 二稿：重构后标签平衡 ✅；my-car-game / ChemAI 原型 / Teardown 卡片已从页面正文移除 ✅；外链收敛为 11 个业务链接 ✅；桌面 + 移动截图复验 ✅

## 8. 通过后的落地顺序

1. 主人确认草稿（含 §5 假设、§4 审计）→ V6 合并进 `index.html`
2. `sites/home` 建 GitHub 远端（登录信息可从 Codex 取）→ Vercel 新项目部署 → 根域/www 切换；photo 项目解绑根域
3. 子域收编：glyup → lab.、chemai101 → chemai101.、BatteryChem Web → battery.（CF Pages）；回改本页 URL
4. ChemAI101 API key 轮换 + Worker 代理（在推广前完成）
5. 更新 Engineering `site-map.md`
