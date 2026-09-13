# PPT Production Router

一个为 AI Agent 设计的 PPT 生产路由 Skill：先根据交付目标选择正确工作流，再开始制作，而不是把所有工具堆到同一份演示里。

适合课堂汇报、答辩、短视频演示、路演、客户可编辑交付，以及旧 PPT / PDF / 截图的翻新需求。

## 安装

适用于支持 `SKILL.md` 的 Codex 环境：

```bash
npx skills add https://github.com/zyyzyy860-netizen/ppt-production-router --skill ppt-production-router
```

安装完成后，重启 Codex。也可以手动把本仓库放到：

```text
~/.codex/skills/ppt-production-router
```

## 怎么用

在 Codex 里直接输入主题即可：

```text
做一个关于香蕉的 PPT
```

默认会生成 10 页、16:9、可编辑的 PPTX，并自动选择黑板粉笔、黑白水墨、水彩或黑白高级编辑视觉风格。输入“做一个 6 页关于香蕉的 PPT”即可指定页数。只有你主动提出“视频成片”“海报感”或“无需编辑”时，才会改用整页生图路线。

也可以补充要求，例如：

```text
用 ppt-production-router 做一份“香蕉的旅行地图”课堂汇报。
6 页，适合大学生上台讲，视觉要有记忆点，最后交付可编辑 PPTX。
```

或：

```text
我有一份旧 PPT 截图，想保持原来的品牌风格，替换成新的内容。
请用 ppt-production-router 规划并执行这次翻新。
```

## 它会做什么

| 你的需求 | 优先路线 |
| --- | --- |
| 视频、答辩、路演、现场演示 | 视觉演示路线：`codex-slides`、`frontend-slides` 或 `guizang-ppt-skill` |
| 客户后续要改文字、图片、表格或图表 | 原生 PPTX 路线：`ppt-master` 或 `slide-skill` |
| 有品牌旧稿，需要延续视觉风格 | `deck-dna` 后接原生交付流程 |
| PDF、截图、图片稿要改字或还原 | `GordenImage2PPTX` |

它会先制作封面、常规页和最复杂页作为校样；确认可读性、信息密度和交付格式后，再生成整套内容。

## 可选：在 PowerPoint 里现场操作

如果你在 Windows 上安装了 Microsoft PowerPoint 桌面版，可以额外接入 `ppt-mcp`，让 AI 直接操作已经打开的 PowerPoint 窗口：逐字输入、添加页面、调整文本和原生形状都会实时显示。

```powershell
winget install --id astral-sh.uv --exact
codex mcp add ppt-mcp -- uvx ppt-mcp
```

重启 Codex 后，先打开一份 PPT，再告诉它：

```text
在当前打开的 PowerPoint 里，新建一页并逐字写入标题。
```

该能力需要 Windows 与 Microsoft PowerPoint；WPS 兼容性不保证。

## 设计原则

- 交付目标先于工具选择。
- 一页只表达一个可验证的结论。
- 视觉形式从主题和素材中生长，避免通用 AI 模板感。
- 不靠缩小字号塞内容；超出页面承载能力就删减或拆页。
- 原生交付必须在目标 PowerPoint 环境中检查可编辑性。

## License

[MIT](LICENSE)
