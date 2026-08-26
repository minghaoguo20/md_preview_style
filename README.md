# Markdown Preview Style

一个只有 CSS 的 VS Code 扩展，用来美化 **Markdown 预览**（`Ctrl/Cmd + Shift + V`）。

目前它做的事情只有一件：把折叠块 `<details>` 渲染成带圆角边框的卡片（无背景色），summary 下方加分隔线、内容左右缩进。
颜色全部取自 VS Code 主题变量，所以浅色 / 深色主题都能自动适配。

## 效果

在 Markdown 里写：

```html
<details>
<summary>点击展开</summary>

正文内容，支持完整的 Markdown。

</details>
```

预览中会得到一个带边框的折叠卡片，而不是浏览器默认的裸三角形。

## 安装

<details>
<summary>方式一：本地打包安装（推荐）</summary>

需要 Node.js。在项目根目录执行：

```bash
npx @vscode/vsce package
code --install-extension md-preview-style-1.0.1.vsix
```

</details>

<details>
<summary>方式二：软链接到扩展目录（改 CSS 立即生效）</summary>

```bash
ln -s "$(pwd)" ~/.vscode/extensions/md-preview-style
```

Windows 用 `%USERPROFILE%\.vscode\extensions\`，Remote-SSH 场景用 `~/.vscode-server/extensions/`。
链接后重启 VS Code；之后每次改完 `style.css`，在预览里按 `Ctrl/Cmd + Shift + P` → `Developer: Reload Window` 即可看到新样式。

</details>

<details>
<summary>方式三：不装扩展，直接在设置里引用 CSS</summary>

如果只想给某个工作区用，可以跳过扩展，在 `.vscode/settings.json` 里写：

```json
{
  "markdown.styles": ["style.css"]
}
```

路径相对于工作区根目录。缺点是只对该工作区生效，换项目要重配。

</details>

## 自定义

所有样式都在 [`style.css`](./style.css) 里，一共不到 30 行，直接改即可。
可用的主题变量名（如 `--vscode-textSeparator-foreground`）可以在预览页面里用
`Developer: Open Webview Developer Tools` 查看。

预览的根容器 class 是 `.markdown-body`，写选择器时带上它可以避免影响 VS Code 其它 webview。

## License

[MIT](./LICENSE)
