# VLOOK 在线版 · Typora 配置

本站托管定制的 VLOOK Hope 在线主题和排版增强插件，统一使用系统字体，使用 GitHub Pages 发布。

- 站点 https://faelonli.github.io/vlook-online/
- 官方项目 https://github.com/MadMaxChow/VLOOK
- 官方说明 https://madmaxchow.github.io/VLOOK/index.html#安装与使用
- 固定资源版本 `V2026.10.1`，上游提交 `5ba268d9682052712d9ed146d09fff9f3e2a64c6`

## 安装到 Typora

1. 使用 Typora 1.14 或更新版本。
2. 在偏好设置的 Markdown 中开启全部 Markdown 扩展语法和代码块选项。
3. 将 `typora-themes` 内的 CSS 复制到 Typora 主题目录。macOS 目录为 `~/Library/Application Support/abnerworks.Typora/themes`，也可在偏好设置 → 外观 → 打开主题目录中找到。
4. 在主题菜单选择 `Vlook Live Hope`。如刚复制的主题尚未出现，重启 Typora 后再选择。
5. 在偏好设置 → 导出中添加 HTML 模板，命名为 `VLOOK (live)`。
6. 将本仓库 `plugin-live.txt` 的完整内容复制到该模板的「在 <head /> 中添加」，开启导出主题样式。
7. 打开 Markdown 文档，选择文件 → 导出 → VLOOK (live)，然后在浏览器打开生成的 HTML。

## 日常使用

Hope 系列统一使用系统无衬线字体，macOS 使用系统字体及苹方，代码使用系统等宽字体。侧栏随文档明暗配色显示中性灰色，当前文件使用柔和的灰色高亮。图片下方自动生成的 `CAPTION/题注 (...)` 编辑提示已隐藏，实际图注仍按原有语法显示。 `==高亮文字==` 使用黄色底色与深色文字，反引号包围的行内代码使用红色文字，深色模式下使用较亮的红色。

外观调整源文件为 `customizations/hope.css`，已合入三个 Hope 在线主题，并作为对应的 `.user.css` 文件提供给 Typora。

- Typora 内直接编辑 Markdown，主题提供编辑时的排版。
- 使用 `#`、`##`、`###` 组织章节，插入 `[TOC]` 生成目录。
- 表格、任务列表、代码块、数学公式和 Mermaid 图表使用 Typora 对应语法。
- VLOOK 的增强导航、演示及主题切换等交互在导出的 HTML 中使用，具体语法参考官方使用攻略。
- 导出文档联网加载本站的 CSS 和 JS，字体直接使用阅读设备的系统字体。
- 主题精简为 `Vlook Live Hope`（自动明暗）、`Vlook Live Hope Light`（浅色）、`Vlook Live Hope Dark`（深色）。
- 已精简其余主题、调试映射和网络字体包，导出页面的字体切换入口已隐藏。旧字体选择会自动恢复为系统字体，旧版 `fs-*-min.css` 地址通过轻量兼容样式继续工作。

## 部署与维护

GitHub Pages 通过 `.github/workflows/pages.yml` 从 `main` 分支根目录发布，`.nojekyll` 保证资源直接托管。
发布流程为资源同步预留 30 分钟，适用于默认 10 分钟部署等待超时的情况。
仓库设置 → Pages → Source 应选择 GitHub Actions。
`V2026.10.1/` 存放 Hope 三个版本的主题 CSS、插件 JS、语言包和旧字体地址的兼容样式，`typora-themes/` 仅保留 Hope 三个本地在线主题入口及其定制样式。
升级时保留旧版本资源目录，将新版本主题和插件配套上传，并检查系统字体适配，并同步更新本地主题与导出配置。

VLOOK 遵循 MIT 许可，见 LICENSE。

系统字体适配在 `vlook-min.js` 的字体初始化、应用和 WebFont 加载逻辑中统一使用 `local`。升级插件时需保留这三处适配及 `customizations/hope.css` 的界面覆盖规则。
