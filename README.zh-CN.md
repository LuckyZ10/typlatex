# Typlatex

**Typora 的 LaTeX 风格主题家族 —— 写 Markdown，得到排版好的期刊论文。**

[English docs](README.md) · [主题画廊投稿](https://theme.typora.io/) · Typora ≥ 1.6 · MIT

![typlatex-ink](screenshots/typlatex-ink.png)

文档渲染在 **A4 白纸卡片**上：**双栏两端对齐**、衬线正文、LaTeX 式首行缩进、
**三线表**、图片**自动跨栏**、蓝色居中图注——一键导出真正的 **A4 双栏 PDF**。

---

## 选你的版本

| | 朴素 | 墨青 |
|---|---|---|
| **期刊式** — 双栏连续排版 | [`typlatex`](screenshots/typlatex.png) | [`typlatex-ink`](screenshots/typlatex-ink.png) |
| **书式** — H2 通栏、每章起新双栏组 | [`typlatex-book`](screenshots/typlatex-book.png) | [`typlatex-book-ink`](screenshots/typlatex-book-ink.png) |
| **单栏传统** — 12pt、行距 1.6 | [`typlatex-article`](screenshots/typlatex-article.png) | [`typlatex-article-ink`](screenshots/typlatex-article-ink.png) |

**朴素**版标题克制、纯排版感；**墨青**版的 H2 是"右下大圆角深黑灰标签嵌浅灰
轨道"，加粗文字珊瑚红。上面六张截图是**同一份文档**——随时在「主题」菜单切换。

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

1. 下载并解压本仓库
2. Typora → 文件 → 偏好设置 → 外观 → 打开主题文件夹
3. 把想要的 `.css` 复制进去
4. 重启 Typora，在「主题」菜单选择

> 使用行内公式 `$…$` 需在 偏好设置 → Markdown 勾选「内联公式」。

## 功能速览

**图片与图注**：图片单独成段自动跨双栏（相当于 `figure*`）；行内图留在栏内。
图片后紧跟的整行斜体（空不空行都行）自动变成蓝色居中图注，跟随图片的跨栏行为。

**用 `---` 触发跨栏**：分隔线是隐形的跨栏指令，下一块内容——段落、`$$` 公式、
表格——横跨双栏：

```markdown
---

$$
\begin{aligned}
f(x) &= a+b+c+d+e \\
     &= g+h
\end{aligned}
$$
```

长公式用 `aligned` + `\\` + `&` 手动断行；独立公式居中显示、不裁剪。

**表格**：三线表（booktabs 风格），默认栏内 8.5pt；上一行放 `---` 即跨栏 9pt。

**标题**：H1 是文章标题（跨栏居中）；不自动编号——直接写 `## 1. 引言`，
或取消 CSS 末尾注释块的注释恢复自动编号。

## 自定义参数

每份 CSS 顶部的 `:root` 块：

| 变量 | 默认值 | 含义 |
|------|--------|------|
| `--page-width` | `178mm` | A4 内容宽 |
| `--page-margin` | `16mm` | 屏幕与打印边距 |
| `--col-gap` | `7mm` | 栏间距 |
| `--font-size` | `10.5pt` | 正文字号（单栏版 12pt） |
| `--para-indent` | `0em` | 首行缩进（恢复 LaTeX 风格改 `2em` 并把段间距设 0） |
| `--para-gap` | `0.55em` | 段间距（不缩进时区分段落用） |
| `--caption-color` | `#0b53c2` | 图注颜色 |

墨青版的标题几何（#212122 / #FBFBFB、35pt 圆角）在 CSS 中以 `装修` 注释标出。

## 使用须知

- `---` **上方**必须空一行，否则上一行会被 Markdown 解析成 setext 二级标题
- 跨栏元素会重排上方两栏，大图/大表放在自然段边界处效果最好
- 空行无法当触发器：`---\nX` 与 `---\n\nX` 渲染结果相同，任何主题都无法区分

## 许可

[MIT](LICENSE) — © 2026 LuckyZ10
