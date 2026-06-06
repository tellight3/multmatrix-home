# AGENTS.md

这个仓库是 multmatrix.com 的静态主页。

## Git 工作流规则

这个项目保持简单，不使用复杂分支流程。

- 只在 `main` 分支上工作。
- 不要创建新分支。
- 不要创建 PR。
- 不要创建 draft PR。
- 不要使用 `codex/*` 分支。
- 修改完成后，直接 commit 到 `main`。
- commit 后直接 push 到 `origin main`。
- 如果当前不在 `main` 分支，请先切换到 `main` 并执行 `git pull origin main`。
- 如果工作区不干净，不要擅自覆盖未提交修改，应先说明情况。
- 每次完成任务后，用中文总结：
  - 修改了哪些文件
  - 是否已经 commit
  - 是否已经 push 到 `origin main`
  - 如何本地预览

## 网站目标

把首页做成一个简单、清楚、SEO 友好的 SaaS 产品落地页。

主页主要推广 MultMatrix 的 AI 字幕工具：

https://sub.multmatrix.com/

用户打开首页后，应该在 3 秒内明白：

MultMatrix can generate subtitles for videos, preview them in sync with the video, and download editable subtitle files.

## 核心展示重点

首页最重要的展示不是炫技，也不是复杂功能清单。

核心 Demo 应该展示：

- 视频播放
- 视频画面上有字幕
- 下方或旁边有同步字幕列表
- 视频播放时，当前字幕行高亮
- 当前字幕行自动滚动到可见位置
- 点击字幕行可以跳转视频时间

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
- 下方或旁边显示 synchronized transcript panel。
- 视频播放时根据 `currentTime` 高亮当前字幕行。
- 当前字幕行应自动滚动到可见位置。
- 点击字幕行可以 seek 到对应时间。
- 如果 VTT 因 CORS、MIME type 或网络问题加载失败，显示静态 fallback subtitle lines，不要让页面报错。

## 页面内容方向

页面正文文案使用英文。

首页应该简单，不要复杂。推荐结构：

1. Header
   - Brand: MultMatrix
   - 简单导航：Demo / How it works / FAQ
   - CTA: Try the Subtitle Tool

2. Hero
   - H1: AI Subtitle Generator for Videos
   - 一句话说明：
     Generate subtitles, preview them in sync with your video, and download editable VTT/SRT files.
   - Primary CTA: Start Generating Subtitles
   - Secondary CTA: Watch Demo

3. Main Demo
   - 视频播放器
   - 同步字幕列表
   - 简短说明

4. Simple feature row
   只保留 3 个核心功能：
   - Generate subtitles
   - Preview in sync
   - Download VTT/SRT

5. How it works
   只保留 3 步：
   - Paste a video link
   - Generate subtitles
   - Preview and download

6. FAQ
   保留 4-5 个简短问题：
   - What is MultMatrix?
   - Can I preview subtitles online?
   - Can I download subtitle files?
   - Can I translate subtitles?
   - What video links are supported?

7. Footer
   简单即可。

## 重要规则

- 保持静态网站，可以部署到 GitHub Pages / Cloudflare Pages。
- 优先修改现有 `index.html`。
- 不要引入 React、Next.js、Vue、Tailwind 或构建工具。
- 不要安装依赖。
- 所有主要 CTA 都链接到 `https://sub.multmatrix.com/`。
- 不要编造不存在的功能、价格、用户评价、合作伙伴。
- 页面要适配手机端。
- SEO 要自然，不要堆关键词。
- 页面要简单、清楚、现代，不要炫技。
- 不要堆很多 use cases。
- 不要把 burned-in subtitle video 放在主要位置。
- 不要让首页像功能清单大全。

## 视觉方向

- 现代 SaaS 风格
- 深色科技背景
- 蓝紫色渐变
- 卡片式布局
- 字体层级清晰
- 间距统一
- 移动端友好
- 不要复杂动画
- 不要为了好看牺牲清楚

## SEO 要求

- `title` 包含 `AI Subtitle Generator`。
- `meta description` 自然说明可以 generate, preview in sync, and download subtitles for videos。
- 页面只能有一个 H1。
- FAQ 文案自然，不要关键词堆砌。
- 语义化 HTML。

## 完成前检查

- 检查当前分支是否是 `main`。
- 检查所有主要 CTA 是否指向 `https://sub.multmatrix.com/`。
- 检查是否只有一个 H1。
- 检查移动端布局。
- 检查 video 是否设置 `controls` 和 `preload="metadata"`。
- 检查没有加入无用依赖。
- 修改完成后直接：
  - `git add .`
  - `git commit`
  - `git push origin main`
