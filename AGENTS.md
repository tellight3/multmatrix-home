# AGENTS.md

这个仓库是 `multmatrix.com` 的静态主页。

## Git 工作流

这个项目保持简单，只使用 `main` 分支。

- 只在 `main` 分支工作。
- 不要创建新分支。
- 不要创建 PR。
- 不要创建 draft PR。
- 不要使用 `codex/*` 分支。
- 如果当前不在 `main`，先切换到 `main`。
- 修改前先执行 `git pull origin main`。
- 修改完成后直接 commit 到 `main`。
- commit 后直接 push 到 `origin main`。
- 如果工作区不干净，不要擅自覆盖未提交修改，应先说明情况。
- 完成后用中文总结：
  - 修改了哪些文件
  - 是否已经 commit
  - 是否已经 push 到 `origin main`
  - 如何本地预览

## 网站目标

首页要做成一个简单、清楚、SEO 友好的 SaaS 产品落地页。

主页主要推广 MultMatrix 的 AI 字幕工具：

`https://sub.multmatrix.com/`

用户打开首页后，应该在 3 秒内明白：

MultMatrix helps users generate subtitles for videos, preview them in sync, and download editable VTT/SRT subtitle files.

## 页面原则

简单清楚优先。

- 不要炫技。
- 不要堆很多 section。
- 不要写很多营销废话。
- 不要做复杂动画。
- 不要让首页像功能大全。
- 不要为了好看牺牲可读性。
- 每个区块文字要短。
- 页面正文使用英文。
- Codex 可以用中文总结修改内容。

首页推荐结构：

1. Header
2. Hero
3. Synchronized subtitle demo
4. Three core features
5. How it works
6. FAQ
7. Footer

## 核心 Demo

首页最重要的展示是：

视频播放 + 视频字幕显示 + 下方或旁边字幕列表同步滚动。

真实 Demo 媒体：

- Video: `https://media.multmatrix.com/default.mp4`
- VTT subtitle: `https://media.multmatrix.com/default.vtt`

Demo 实现要求：

- 使用原生 `<video>`。
- `video` 必须有 `controls`。
- `video` 必须设置 `preload="metadata"`。
- 不要 autoplay。
- 不要 loop。
- 不要 muted autoplay。
- 使用 `<track>` 加载 VTT 字幕。
- 使用少量原生 JavaScript 加载并解析 VTT。
- 显示 synchronized transcript panel。
- 视频播放时，根据 `currentTime` 高亮当前字幕行。
- 当前字幕行要自动滚动到可见位置。
- 点击字幕行可以跳转视频到对应时间。
- 每行字幕显示时间和文本。
- 如果 VTT 因 CORS、MIME type 或网络问题加载失败，显示静态 fallback subtitle lines，不要让页面报错。
- 手机端 transcript panel 放在视频下方，不能溢出屏幕。

## 内容重点

首页只突出 3 个核心能力：

1. Generate subtitles
2. Preview in sync
3. Download VTT/SRT

How it works 只保留 3 步：

1. Paste a video link
2. Generate subtitles
3. Preview and download

FAQ 保留 4-5 个简短问题：

- What is MultMatrix?
- Can I preview subtitles online?
- Can I download VTT or SRT subtitle files?
- Can I translate subtitles?
- What video links are supported?

不要把 burned-in subtitle video 放到主要位置。
不要重点宣传硬字幕视频。
首页第一目标是让用户理解“视频字幕生成 + 同步预览 + 字幕下载”。

## SEO 要求

SEO 非常重要。不要因为简化页面而删除 SEO 内容。

- `title` 必须包含 `AI Subtitle Generator`。
- `meta description` 要自然说明可以 generate, preview in sync, and download subtitles for videos。
- 保留或改进 Open Graph metadata。
- 保留或改进 Twitter card metadata。
- 页面只能有一个 H1。
- H1 建议使用：`AI Subtitle Generator for Videos`
- FAQ 必须保留，并使用自然英文。
- 页面正文自然包含这些关键词，但不要堆砌：
  - AI subtitle generator
  - video subtitle generator
  - subtitle preview
  - VTT/SRT subtitles
  - subtitle translation
- 保持语义化 HTML。
- 不要破坏 `robots.txt` 和 `sitemap.xml`。

## 技术规则

- 保持静态网站，可以部署到 GitHub Pages / Cloudflare Pages。
- 优先修改现有 `index.html`。
- 不要安装依赖。
- 不要引入 React、Next.js、Vue、Tailwind 或构建工具。
- 只使用原生 HTML/CSS/JavaScript。
- 所有主要 CTA 都链接到 `https://sub.multmatrix.com/`。
- 页面必须适配移动端。
- 不要编造不存在的功能、价格、用户评价、合作伙伴。

## 视觉方向

- 现代 SaaS 风格。
- 深色科技背景。
- 蓝紫色渐变可以使用，但不要过度。
- 卡片式布局。
- 字体层级清楚。
- 间距统一。
- 移动端友好。
- 整体应该干净、清楚、可信。

## 完成前检查

完成任务前必须检查：

- 当前分支是 `main`。
- 页面只有一个 H1。
- 所有主要 CTA 都指向 `https://sub.multmatrix.com/`。
- video 使用 `controls` 和 `preload="metadata"`。
- 没有新增依赖。
- 没有创建分支。
- 没有创建 PR。
- 已经 commit。
- 已经 push 到 `origin main`。
