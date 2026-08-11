# Portfolio V4 计划 — "The Catalyst"

> 暖白学术风 · 纯英文 · 以人为核心
> GENIUS Olympiad Gold Medal 作为已完成成就展示
> 所有项目按已完成状态呈现

---

## 设计理念

**核心转变：让招生官看到一个人，而不是一份简历。**

1. **暖白学术风取代深色科技风** — 视觉上更接近斯坦福官网的温度，而不是一个 SaaS 产品。浅色背景 + 砂石色点缀 + 少量 Stanford Cardinal 红，像翻开一本精装学术期刊。

2. **照片是视觉主角，不是装饰** — 6 张真实照片占页面 40%+ 面积。Hero 区第一眼看到的是国维的脸，不是一行 tagline。招生官每天看几百份材料，一张真实的、有温度的照片比任何文案都先抓住注意力。

3. **新增 About 区块** — 这是 v3 完全没有、v4 最重要的结构变化。骑行 2000km、"kilometer 40 想到反应机理"这种细节，让招生官记住的是一个有趣的人，而不只是一串成就。斯坦福要的是 "interesting"，不只是 "impressive"。

4. **"催化剂"主线贯穿但不刻意** — 实验室（化学催化）→ 沙漠（生态催化）→ 社团/工具（学习催化），三个 Chapter 自然流动，不强行点题。读完之后"catalyst"这个词会留在脑子里，但不是因为被反复灌输，而是因为故事本身就是这条线。

5. **文案从 marketing copy 改为真实的声音** — 第一人称口语，像在和招生官聊天。去掉 "by training / by instinct" 这种 LinkedIn headline 式的包装，换成 "I'm spending most of my time between a chemistry lab and a video editing timeline" 这种真实的表达。

6. **视觉节奏有呼吸感** — 文字区 → 大图区 → 引言过渡 → 文字区，交替出现，不是信息轰炸。每个 Chapter 之间用一句引言做过渡，给招生官消化的空间，也制造记忆锚点。

---

## Context

v3 的问题：太像科技公司 landing page，缺少"人"的温度。招生官想看到一个 17 岁的真实的人，不是一个品牌。v4 的核心转变：从"展示成就"转向"讲一个人的故事"。

---

## 设计系统

### 色彩

```
--bg-primary:    #faf8f5    暖白（主背景）
--bg-secondary:  #f0ece4    米色（交替区块）
--bg-card:       #ffffff    纯白（卡片）
--text-primary:  #1a1a1a    深棕（正文）
--text-secondary:#5c5549    暖灰（辅助文字）
--text-muted:    #9c9488    浅暖灰
--accent:        #8C1515    Stanford Cardinal（极少量点缀，不滥用）
--sand:          #D4A76A    砂石色（沙漠/温暖元素）
--teal:          #2a7c6f    深青绿（科研元素）
--border:        rgba(26, 26, 26, 0.08)
```

### 字体

```
标题: Playfair Display（保留，学术衬线感）
正文: Source Serif 4（替换 Inter，更有书卷气）
标签/数据: JetBrains Mono（保留）
```

### 视觉原则

- 大面积留白，呼吸感
- 照片占页面 40%+ 面积，是视觉主角而非装饰
- 文字克制，每段不超过 3 行
- 无 hover 特效堆砌，交互极简
- 圆角更大（12-16px），柔和不锐利

---

## 页面结构（7 个区块）

### 1. Hero — 第一印象（全屏）

**布局**：左文右图，6:4 分割

**左侧文字**：
```
Guowei Wang

I study catalysts —
not just reactions, but change.

Researcher · Filmmaker · Builder
Beijing, China
```

- 去掉 "Class of 2027"
- 去掉 "by training / by instinct" 的 marketing 语气
- 三个身份词简洁并列
- 加 "Beijing, China" 锚定真实感

**右侧照片占位**：
```
📷 HERO-PHOTO
位置：Hero 右侧，占 40% 宽度
内容：国维在实验室的半身照（自然光，穿白大褂，
      手里拿着试管或在操作仪器，微笑或专注表情）
要求：自然光拍摄，不要摆拍感，背景是真实的实验室
尺寸：至少 800x1000px，竖构图
色调：暖色调，与页面背景协调
```

**下方**：两个按钮 `Read My Story` + `Get in Touch`

---

### 2. About — 让招生官认识这个人（新增区块）

**这是 v3 完全没有的，也是 v4 最重要的新增。**

**布局**：左侧一张生活照 + 右侧 2-3 段文字

**照片占位**：
```
📷 ABOUT-PHOTO
位置：About 区块左侧，占 45% 宽度
内容：国维的生活照（以下任选一）：
  方案A：骑行途中，戴头盔，背后是山路或城市天际线
  方案B：在沙漠拍摄现场，手持相机，背后是光伏板和羊群
  方案C：和社团同学在一起做实验的合影
要求：自然、有笑容、能看到环境背景
尺寸：至少 800x600px，横构图
```

**文字内容**（口语化，有温度）：
```
I'm a high school senior at BFSU Affiliated in Beijing,
spending most of my time between a chemistry lab and a
video editing timeline.

My research started with a question about catalysts —
how tiny amounts of platinum can transform waste glycerol
into something useful. That question led me to a Peking
University lab, a first-author paper, and eventually to
the Tengger Desert, where I discovered that the biggest
catalyst isn't always a molecule.

When I'm not in the lab, I'm probably on my bike. I ride
about 2,000 km a year — it's how I think. Some of my best
ideas about reaction mechanisms came somewhere around
kilometer 40.
```

**右下角小细节**（增加人味）：
```
Currently reading: [书名占位]
Favorite molecule: Ferrocene (it spins)
km cycled this year: 1,847
```

---

### 3. Chapter 1 — Research（科研）

**布局**：保留 v3 的时间线结构，但视觉上更轻

**三个时间节点**（全部按已完成展示）：

**3a. 英才计划 + JSR 论文（Featured，最大卡片）**

**照片占位**：
```
📷 RESEARCH-LAB
位置：Featured 卡片内，顶部横幅
内容：实验室工作照（以下任选）：
  方案A：国维在操作 XRD/TEM 仪器的侧面照
  方案B：实验台上的催化剂样品特写（试管/烧瓶/粉末）
  方案C：实验室全景，国维在其中工作
要求：能看到真实的科研环境，不是摆拍
尺寸：至少 1200x400px，宽幅横构图
```

内容保持 v3 的准确表述：
- National Yingcai Program · Peking University
- 0.1% admission rate
- First-author paper in JSR
- Pt-Fe-CeO₂ catalyst for glycerol oxidation
- XRD / TEM / XPS

**3b. 丘成桐 GreenBatty（按已完成展示）**
- Yau Science Award · Tsinghua University
- Bio-inspired catalytic system for CO₂ reduction
- 展示最终成果（决赛入围/获奖，按实际情况填）

**3c. Stanford Summer Program**
- 8-week residential program
- 简短一行即可，不过度强调

---

### 4. Chapter 2 — The Solar Shepherd（短片，核心记忆点）

**这是最能打动招生官的区块，给最大的视觉空间。**

**布局**：全宽沉浸式，上方大图/视频 + 下方信息

**视频/图片占位**：
```
📷 FILM-HERO
位置：Chapter 2 顶部，全宽，高度 60vh
内容（优先级排序）：
  最佳：短片中的标志性画面截图 — 光伏板下的羊群，
        金色夕阳，牧羊人的剪影
  次选：沙漠拍摄现场的工作照 — 国维扛着相机在沙漠中
  备选：光伏板阵列的航拍俯瞰图
要求：电影感，宽幅，高分辨率
尺寸：至少 1920x800px
色调：金色/暖色调（沙漠日落光线）
叠加：半透明暗色渐变 + 白色标题文字
```

**视频播放器占位**：
```
🎬 VIDEO-EMBED
位置：大图下方，居中，16:9 比例
内容：《光伏牧羊人》完整短片（5:56）
平台：YouTube 或 Vimeo embed
备选：如暂无上传，用封面图 + Play 按钮 +
      "Watch on YouTube" 外链
```

**信息区**：

标题区：
```
The Solar Shepherd
A Catalyst for Ecological Restoration
GENIUS Olympiad Gold Medal · 2026
```

Four Questions（保留，但改为更沉浸的排版）：
```
四个问题竖排，每个占一行，左侧有细竖线装饰
字体用 Playfair Display italic
背景用极浅的砂石色
```

指标卡（保留 v3 的四个，更新 GENIUS 为 Gold Medal）：
- 82% IR Radiation Reduced
- Gold Medal — GENIUS Olympiad 2026
- 5:56 — Four narrative layers
- 1 of 2 from mainland China

引言保留：
```
"The desert is healing, and technology —
technology is just the catalyst."
```

---

### 5. Chapter 3 — Building for Everyone（项目 + 社团）

**布局**：三列卡片网格（保持 v3 结构，视觉调整为暖白风格）

**三个项目**：

**5a. Chemistry & Life Society**
```
📷 CLUB-PHOTO
位置：卡片顶部
内容：社团活动照（以下任选）：
  方案A：社团成员围在实验台前做实验的合影
  方案B：社团录制科普视频的幕后照
  方案C：社团活动海报或视频截图拼贴
尺寸：卡片宽度 x 200px
```
- Founded & led · 50,000+ views
- Public chemistry education videos
- Hands-on experiments · Peer teaching

**5b. ChemAI 101**
- AI-powered chemistry learning assistant
- Python · Personalized explanations · Adaptive practice
- 不需要照片，用代码风格的装饰图标

**5c. GlyUp**
- Glycobiology data visualization
- Automated glycan structure analysis
- 不需要照片，用数据可视化风格的装饰图标

---

### 6. Honors（奖项，精简展示）

**布局**：水平滚动或两行网格，每个奖项是一个小徽章

**内容**（更新 GENIUS 为 Gold Medal）：
- GENIUS Olympiad Gold Medal
- National Yingcai Program (0.1%)
- JSR First-Author Publication
- UK Chemistry Olympiad
- AP Capstone Diploma
- 14 APs · 10+ Fives
- GPA 3.99 / 4.00
- Stanford Summer Program

---

### 7. Contact + Footer

**布局**：简洁，居中

```
Let's talk about catalysts — or anything else.

📧 [email占位: guowei@xxx.com]
🔗 [GitHub占位: github.com/guoweiwang]
🔗 [LinkedIn占位: linkedin.com/in/guoweiwang]
```

Footer：
```
© 2026 Guowei Wang
Designed as a catalyst for conversation.
```

---

## 照片清单汇总（需要准备 5-6 张）

| 编号 | 用途 | 内容 | 构图 | 最低尺寸 |
|------|------|------|------|---------|
| HERO-PHOTO | Hero 右侧 | 实验室半身照，自然光，白大褂 | 竖构图 | 800x1000 |
| ABOUT-PHOTO | About 左侧 | 骑行/沙漠拍摄/社团合影 | 横构图 | 800x600 |
| RESEARCH-LAB | 科研卡片顶部 | 操作仪器/实验台/实验室 | 宽幅横构图 | 1200x400 |
| FILM-HERO | 短片区全宽背景 | 光伏板下羊群/沙漠夕阳/拍摄现场 | 超宽幅 | 1920x800 |
| VIDEO-EMBED | 短片播放器 | 短片封面图或 YouTube embed | 16:9 | 1280x720 |
| CLUB-PHOTO | 社团卡片顶部 | 社团活动/录制/合影 | 横构图 | 600x300 |

---

## 与 v3 的关键差异

| 维度 | v3 | v4 |
|------|----|----|
| 色调 | 深色科技风 | 暖白学术风 |
| 第一印象 | 成就列表 | 一个人的脸 + 一句话 |
| About 区块 | 无 | 新增，口语化自我介绍 + 骑行细节 |
| 照片 | 零张 | 5-6 张真实照片 |
| GENIUS 表述 | Selected Project | Gold Medal |
| 写作语气 | Marketing copy | 真实的高中生在说话 |
| Hero "Class of" | Class of 2027（斯坦福年份） | 去掉，只写 Beijing, China |
| 丘成桐 | "Present"进行中 | 已完成，展示成果 |
| 视频 | 占位播放器 | YouTube/Vimeo embed 占位 |
| 个人爱好 | 无 | 骑行 2000km + 摄影 |

---

## 技术实现

- 单文件 HTML（保持 v3 的纯静态方式）
- 响应式（移动端优先）
- 照片用占位色块 + 文字说明（标注需要什么照片）
- 视频用 iframe 占位
- Intersection Observer 滚动动画（保留 v3 的 reveal 机制，但更克制）
- 无外部依赖（只用 Google Fonts）

---

## 验证

- 浏览器打开 v4.html 检查所有区块渲染
- 移动端响应式检查（375px / 768px / 1024px）
- 所有占位符标注清晰（照片/链接/视频）
- 文案无语法错误
- 与 v3 对比，确认"人味"提升
