# VLOOK 在线版 · Typora 配置

本站托管 VLOOK 官方在线主题、排版增强插件和完整网络字体，使用 GitHub Pages 发布。

- 站点 https://faelonli.github.io/vlook-online/
- 官方项目 https://github.com/MadMaxChow/VLOOK
- 官方说明 https://madmaxchow.github.io/VLOOK/index.html#安装与使用
- 固定资源版本 `V2026.10.1`，上游提交 `5ba268d9682052712d9ed146d09fff9f3e2a64c6`
- 网络字体 `openfonts V2.2`，发布包 SHA-256 `2dda061bc3d22dfac4728d48faffdab476703522687eafcaf6931531edbf5078`

## 安装到 Typora

1. 使用 Typora 1.14 或更新版本。
2. 在偏好设置的 Markdown 中开启全部 Markdown 扩展语法和代码块选项。
3. 将 `typora-themes` 内的 CSS 复制到 Typora 主题目录。macOS 目录为 `~/Library/Application Support/abnerworks.Typora/themes`，也可在偏好设置 → 外观 → 打开主题目录中找到。
4. 在主题菜单选择 `Vlook Live Hope`。如刚复制的主题尚未出现，重启 Typora 后再选择。
5. 在偏好设置 → 导出中添加 HTML 模板，命名为 `VLOOK (live)`。
6. 将本仓库 `plugin-live.txt` 的完整内容复制到该模板的「在 <head /> 中添加」，开启导出主题样式。
7. 打开 Markdown 文档，选择文件 → 导出 → VLOOK (live)，然后在浏览器打开生成的 HTML。

## 日常使用

Hope 系列默认使用系统无衬线字体，macOS 使用系统字体及苹方，代码使用系统等宽字体。侧栏随文档明暗配色显示中性灰色，当前文件使用柔和的灰色高亮。

外观调整源文件为 `customizations/hope.css`，已合入三个 Hope 在线主题，并作为对应的 `.user.css` 文件提供给 Typora。

- Typora 内直接编辑 Markdown，主题提供编辑时的排版。
- 使用 `#`、`##`、`###` 组织章节，插入 `[TOC]` 生成目录。
- 表格、任务列表、代码块、数学公式和 Mermaid 图表使用 Typora 对应语法。
- VLOOK 的增强导航、演示及主题切换等交互在导出的 HTML 中使用，具体语法参考官方使用攻略。
- 导出文档引用本站的 CSS、JS 与网络字体，需要联网加载。首次加载较慢时请等待字体下载完成。
- 切换其他配色可在 Typora 的主题菜单选择其他 `Vlook Live ...` 主题。

## 部署与维护

GitHub Pages 通过 `.github/workflows/pages.yml` 从 `main` 分支根目录发布，`.nojekyll` 保证资源直接托管。
发布流程为字体等资源同步预留 30 分钟，适用于默认 10 分钟部署等待超时的情况。
仓库设置 → Pages → Source 应选择 GitHub Actions。
`V2026.10.1/` 存放主题 CSS、字体 CSS、插件 JS 和语言包，`fonts/` 存放字体文件，`typora-themes/` 存放本地在线主题入口。
升级时保留旧版本资源目录，将新版本主题、插件和字体配套上传，并同步更新本地主题与导出配置。

VLOOK 遵循 MIT 许可，见 LICENSE。字体来源为官方 openfonts 项目，各字体遵循其原作者的许可。
