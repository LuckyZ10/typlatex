# Typlatex

> Typora 的 LaTeX 风格主题家族 —— 写 Markdown，得到排版好的期刊论文。

![Typora](https://img.shields.io/badge/Typora-%3E%3D_1.6-0b53c2?style=flat-square)
![Themes](https://img.shields.io/badge/themes-6_variants-0b53c2?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-green?style=flat-square)

[English docs](README.md) · [主题画廊投稿](https://theme.typora.io/)

![typlatex-ink](screenshots/typlatex-ink.png)

文档渲染在一张宽度随窗口响应的**白纸卡片**上：**双栏两端对齐**的衬线正文、**三线表**、
图片**自动跨栏**、蓝色居中图注——一键导出真正的 **A4 双栏 PDF**。

## 特性一览

- **GitHub 式响应宽度** — 阅读区默认 `860px`，在 1400/1800px 宽屏上自动扩到
  `1024px`/`1200px`；导出仍保持真正的 A4 双栏与上下 20mm、左右 16mm 页边距。
- **`---` 是排版指令** — 分隔线被重新定义为隐形的「跨栏触发器」：紧随其后的
  内容横跨双栏，详见 [`---` 跨栏指令](#--跨栏指令)。
- **图片自动化** — 单独成段的图片自动跨双栏（相当于 `figure*`）；其后整行
  斜体自动变成蓝色居中图注，跟随图片的跨栏行为。
- **三线表** — booktabs 风格栏内表格 8.5pt；表格前放 `---` 即跨栏 9pt。
- **长公式不裁剪** — `$$` 公式块跨栏居中显示；长公式用 `aligned` + `\\` + `&`
  手动断行。
- **六款变体** — 期刊、书式、单栏三种版式，各有朴素与墨青两种装修；随时在
  「主题」菜单切换。

## `---` 跨栏指令

本主题家族的核心玩法。在 Typlatex 里，分隔线**不画线**——线被隐藏，整条
`---` 被重新解释为一条一次性的排版指令：*让下一块内容横跨双栏。*

```markdown
上一段留在栏内。

---

$$
\begin{aligned}
f(x) &= a+b+c+d+e \\
     &= g+h
\end{aligned}
$$
```

`---` 能让哪些内容跨栏：

| 下一块内容 | 效果 |
|------------|------|
| 段落 | 文字横跨双栏 |
| `$$` 公式块 | 整页居中；长公式用 `aligned` + `\\` + `&` 断行 |
| 表格 | booktabs 三线表跨栏，字号升为 9pt |

不想在源文件里留 `---`？在段首写 `<span class="full"></span>` —— 标记
本身不可见，该段落同样跨栏。

> **`---` 上方必须空一行。** 否则 Markdown 会把上一行解析成 setext
> 二级标题。

## 选你的版本

| | 朴素 | 墨青 |
|---|---|---|
| **期刊式** — 双栏连续排版 | [`typlatex`](screenshots/typlatex.png) | [`typlatex-ink`](screenshots/typlatex-ink.png) |
| **书式** — H2 通栏、每章起新双栏组 | [`typlatex-book`](screenshots/typlatex-book.png) | [`typlatex-book-ink`](screenshots/typlatex-book-ink.png) |
| **单栏传统** — 12pt、行距 1.6 | [`typlatex-article`](screenshots/typlatex-article.png) | [`typlatex-article-ink`](screenshots/typlatex-article-ink.png) |

**朴素**版标题克制、纯排版感；**墨青**版的 H2 是「右下大圆角深黑灰标签嵌
浅灰轨道」，加粗文字珊瑚红。上面六张截图是**同一份文档**——随时在
「主题」菜单切换。

<details>
<summary><b>六款完整预览</b></summary>

| 主题 | 预览 |
|------|------|
| `typlatex` | ![typlatex](screenshots/typlatex.png) |
| `typlatex-book` | ![typlatex-book](screenshots/typlatex-book.png) |
| `typlatex-ink` | ![typlatex-ink](screenshots/typlatex-ink.png) |
| `typlatex-book-ink` | ![typlatex-book-ink](screenshots/typlatex-book-ink.png) |
| `typlatex-article` | ![typlatex-article](screenshots/typlatex-article.png) |
| `typlatex-article-ink` | ![typlatex-article-ink](screenshots/typlatex-article-ink.png) |

</details>

## 安装

1. 下载并解压本仓库。
2. Typora → 文件 → 偏好设置 → 外观 → 打开主题文件夹。
3. 把想要的 `.css` 复制进去。
4. 重启 Typora，在「主题」菜单选择。

> 使用行内公式 `$…$` 需在 偏好设置 → Markdown 勾选「内联公式」。

## 写作指南

**图片与图注**：图片单独成段自动跨双栏（相当于 `figure*`）；行内图留在
栏内。图片后紧跟的整行斜体（空不空行都行）自动变成蓝色居中图注，跟随
图片的跨栏行为。

**表格**：三线表（booktabs 风格），默认栏内 8.5pt；上一行放 `---` 即
跨栏 9pt。

**公式**：行内公式随文字排版；独立公式块加 `---` 跨栏居中，不加则留在
栏内。

**标题**：H1 是文章标题（跨栏居中）；不自动编号——直接写 `## 1. 引言`，
或取消 CSS 末尾注释块的注释恢复自动编号。

## 自定义参数

每份 CSS 顶部的 `:root` 块：

| 变量 | 默认值 | 含义 |
|------|--------|------|
| `--page-width` | `178mm` | A4 内容宽 |
| `--page-margin` | `16mm` | 屏幕卡片内边距与 PDF 左右页边距 |
| `--preview-width` | `860px` | 屏幕阅读区宽度（宽屏断点会自动放大） |
| `--col-gap` | `7mm` | 栏间距 |
| `--font-size` | `10.5pt` | 正文字号（单栏版 12pt） |
| `--para-indent` | `0em` | 首行缩进（恢复 LaTeX 风格改 `2em` 并把 `--para-gap` 设 0） |
| `--para-gap` | `0.55em` | 段间距（不缩进时区分段落用） |
| `--caption-color` | `#0b53c2` | 图注颜色 |
| `--paper-color` | `#ffffff` | 屏幕纸张与 PDF 页面的背景色 |
| `--canvas-color` | `#e8e6e1` | 屏幕上纸张外的桌面底色 |

墨青版的标题几何（#212122 / #FBFBFB、35pt 圆角）在 CSS 中以 `装修`
注释标出。

## 使用须知

- `---` **上方**必须空一行，否则上一行会被 Markdown 解析成 setext
  二级标题。
- 跨栏元素会重排上方两栏，大图/大表放在自然段边界处效果最好。
- 空行无法当触发器：`---\nX` 与 `---\n\nX` 渲染结果相同，任何主题都
  无法区分。

## 许可

[MIT](LICENSE) — © 2026 LuckyZ10
