# Portfolio v5 — "Catalyst" 视觉签名实施方案

> 制定：稳米（2026-08-11）｜ 执行：洋米 ｜ 审查：稳米
> 目标文件：`/Users/yimu/WorkBuddy/大米空间/portfolio-v4.html`（改名 v5 或原地升级均可，由弈沐哥定）
> 前置条件：**洋米正在进行的 P0/P1 bug 修复先落地，本方案在其之上叠加**，不要并行改同一文件。

---

## 1. 目标与设计原则

**一句话**：保持现有克制编辑风骨架不动，注入唯一视觉签名——"催化剂/反应"概念，让招生官 30 秒内意识到"这是化学人的网站"。

原则：
- **只做加法**：不重构布局、不换字体、不改配色体系、不动洋米正在修的区域（nav、overlay z-index、对比度 token、emoji 图标、移动菜单）。
- **纯 CSS/SVG**：零 JS 库、零图片资源、新增体积 < 8KB。
- **三个触点，点到为止**：Hero 能量曲线（主签名）+ 两个转场反应式（辅）+ 章节箭头（可选微调）。不做粒子动画、不做分子 3D、不做全站主题改造。

## 2. 改动点规格

### E1：Hero 反应能量曲线（主签名，必做）

**位置**：`.hero__title` 之后、`.hero__meta` 之前插入。

**图形**：内联 SVG，经典反应坐标图（reaction coordinate diagram）——一条实线（未催化路径，高活化能峰）+ 一条虚线（催化后路径，低峰），呼应 "lowering the activation energy" 的叙事核心。

```html
<div class="hero__energy" aria-hidden="true">
  <svg viewBox="0 0 480 120" fill="none" xmlns="http://www.w3.org/2000/svg">
    <!-- 坐标轴 -->
    <path class="ec-axis" d="M20 100 H460 M20 100 V14"/>
    <!-- 未催化路径：实线，muted -->
    <path class="ec-raw" d="M20 78 C 90 78, 110 12, 160 12 C 210 12, 240 84, 300 84 L 460 84"/>
    <!-- 催化路径：虚线，accent，峰更低 -->
    <path class="ec-cat" d="M20 78 C 90 78, 130 44, 180 44 C 230 44, 250 84, 300 84" stroke-dasharray="5 5"/>
    <!-- 标注 -->
    <text class="ec-label" x="160" y="8"  text-anchor="middle">E<tspan baseline-shift="sub" font-size="8">a</tspan></text>
    <text class="ec-label ec-label--cat" x="180" y="38" text-anchor="middle">E<tspan baseline-shift="sub" font-size="8">a</tspan>′</text>
  </svg>
  <p class="hero__energy-caption">Lowering the activation energy — in reactions and beyond.</p>
</div>
```

**CSS**：

```css
.hero__energy { margin: -0.5rem 0 2rem; max-width: 480px; }
.hero__energy svg { width: 100%; height: auto; display: block; }
.ec-axis { stroke: var(--border); stroke-width: 1; }
.ec-raw  { stroke: var(--text-muted); stroke-width: 1.5; fill: none; }
.ec-cat  { stroke: var(--accent); stroke-width: 1.5; fill: none; }
.ec-label { font-family: var(--font-mono); font-size: 10px; fill: var(--text-muted); font-style: italic; }
.ec-label--cat { fill: var(--accent); }
.hero__energy-caption {
  font-family: var(--font-mono); font-size: 0.6875rem;
  color: var(--text-muted); letter-spacing: 0.04em; margin-top: 0.25rem;
}
```

**动画（入场一次，≤1.2s）**：两条路径用 `stroke-dashoffset` 描边绘入。实线先画（0.9s），虚线延迟 0.3s 跟进。

```css
.ec-raw { stroke-dasharray: 620; stroke-dashoffset: 620; animation: ec-draw 0.9s var(--ease) 0.4s forwards; }
.ec-cat { stroke-dasharray: 480 480; stroke-dashoffset: 480; animation: ec-draw 0.9s var(--ease) 0.7s forwards; }
/* 注意：.ec-cat 的 dasharray 动画技巧与静态虚线冲突——实现时改为：
   静态虚线效果改用第二条 path 叠加，或动画结束后 JS-free 切换。
   推荐简化方案：催化路径不做静态虚线，直接用 accent 实线 + 更低峰形区分，
   动画统一用 stroke-dashoffset。二选一，执行者自定，验收只看最终观感。 */
@keyframes ec-draw { to { stroke-dashoffset: 0; } }
@media (prefers-reduced-motion: reduce) {
  .ec-raw, .ec-cat { animation: none; stroke-dashoffset: 0; }
}
```

> dasharray 长度可用 `path.getTotalLength()` 一次性在控制台量出后硬编码，禁止为此引入运行时 JS 测量。

### E2：章节转场区加"反应式" kicker（辅签名，必做）

**位置**：两处 `.transition-quote` 内部、引言文字**上方**各加一行。

**内容**（化学式排版，JetBrains Mono，与各自转场语义绑定）：

| 转场 | 反应式 |
|---|---|
| Research → Film（"unrelated worlds"引言处） | `photons + sand ⟶[PV] grass + sheep` |
| Film → Projects（"Less sand. More grass."引言处） | `knowledge ⟶[sharing] acceleration` |

实现格式（催化条件标在箭头上方，用 flex 模拟，不依赖 MathJax/化学字体）：

```html
<p class="transition-quote__eq">
  photons + sand
  <span class="eq-arrow"><span class="eq-cat">PV</span>⟶</span>
  grass + sheep
</p>
```

```css
.transition-quote__eq {
  font-family: var(--font-mono); font-size: 0.75rem;
  letter-spacing: 0.06em; color: var(--sand-text, #A67C3F);
  /* ↑ 优先用洋米修复对比度后的新 sand 文本 token；若 token 未定，用 #A67C3F 兜底 */
  margin-bottom: 1.25rem; display: flex; align-items: flex-end;
  justify-content: center; gap: 0.5rem; flex-wrap: wrap;
}
.eq-arrow { display: inline-flex; flex-direction: column; align-items: center; line-height: 1; }
.eq-cat { font-size: 0.625rem; color: var(--accent); margin-bottom: 1px; }
```

### E3：章节标签箭头（可选，5 分钟工作量）

`.chapter__label` 的 `Chapter 01` 与标题之间不做改动；仅把 label 文本改为 `Chapter 01 ⟶`（加一个长尾箭头收尾）。三处统一。如果试出来觉得多余，整项砍掉，不影响 E1/E2。

## 3. 协作边界（重要）

| 归属 | 区域 |
|---|---|
| 洋米（bug 修复，进行中） | nav、film overlay z-index、全局对比度 token、emoji→SVG 图标、移动菜单、按钮层级 |
| 本方案（签名，bug 修复落地后开始） | hero 新增 `.hero__energy` 区块、两处 `.transition-quote` 内部新增 eq 行、（可选）chapter label 文本 |

- 本方案**不新增颜色 token**，只消费现有变量；对比度修正后若 sand 文本色有正式 token，E2 里的兜底值替换掉。
- 两处工作都改同一个 HTML 文件 → **串行执行**，bug 修复 commit 后再开始签名实现，避免冲突。

## 4. 验收 Checklist（稳米审查用）

功能/视觉：
- [ ] E1 曲线在桌面 1440px 与移动 390px 均完整显示，无横向溢出、无布局抖动（CLS）
- [ ] 描边动画总时长 ≤1.5s，只在首次加载播放一次
- [ ] E2 两处反应式与各自引言语义匹配，箭头催化标注对齐不折行错乱（390px 允许整体换行）
- [ ] 新增文本对比度 ≥ 4.5:1（用 WebAIM 对比度工具抽查 eq 行和 caption）

技术约束：
- [ ] 零新增 JS 库、零新增图片、零运行时 JS 测量；新增 HTML+CSS ≤ 8KB
- [ ] `prefers-reduced-motion` 下所有动画静默为静态终态
- [ ] 不改动洋米 bug 修复涉及的任何选择器
- [ ] HTML 通过 W3C validator 无新增 error

观感（弈沐哥终审）：
- [ ] "一眼看出是化学人的网站，但说不出哪里刻意"——达到即通过

## 5. 明确不做

- 不做分子结构动画 / 粒子背景 / 3D 元素
- 不改 hero 布局栅格、不动照片区域
- 不给每个章节都塞化学梗（E1+E2 三处触点即饱和，再多就是 gimmick）
- 不重命名/重排任何现有 class
