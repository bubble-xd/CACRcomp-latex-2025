<div align="center">
  <img src="imgs/logo.png" width="132" alt="中国密码学会标志">

  # 2025 全国密码技术竞赛作品设计报告 LaTeX 模板

  基于 2025 年第十届全国密码技术竞赛官方 Word 模板整理的社区版 LaTeX 模板

  [![LaTeX](https://img.shields.io/badge/LaTeX-LuaLaTeX%20%7C%20XeLaTeX-008080?logo=latex&logoColor=white)](https://www.latex-project.org/)
  [![Year](https://img.shields.io/badge/template-2025-1f6feb)](#)
  [![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
</div>

> [!IMPORTANT]
> 本项目是方便参赛者排版的非官方社区模板。提交前请以当届组委会发布的官方通知和 Word 模板为准。

## 模板特点

- 对齐 2025 官方模板的 A4 页面、2 cm 页边距、封面、基本信息表和正文结构。
- 按 Word 原始样式使用宋体、华文楷体、黑体、楷体 GB2312、Calibri 与
  Times New Roman；缺少系统字体时自动使用开源近似字体。
- 完整支持五类作品：软件设计、硬件制作、工程实践、密码应用技术与其它。
- 将作品编号、题目、日期、摘要、关键词和类别集中在 `template.tex` 顶部配置。
- 正文自动生成规范编号，并提供统一页眉、页码、图表、公式和代码排版基础。
- 默认显示灰色写作提示，一行切换即可生成干净的提交版本。
- 可直接上传至 Overleaf，也可在本地使用 LuaLaTeX 或 XeLaTeX 编译。

## 效果预览

<div align="center">
  <img src="imgs/preview.png" width="720" alt="2025 全国密码技术竞赛 LaTeX 模板首页预览">
</div>

## 快速开始

### 1. 修改作品信息

打开 `template.tex`，找到“只需修改本区内容”：

```latex
\newcommand{\WorkNumber}{CACR2025XXXXXX}
\newcommand{\WorkTitle}{作品题目}
\newcommand{\ReportDate}{2025年\quad 月\quad 日}
\newcommand{\WorkAbstract}{请在此填写作品内容摘要。}
\newcommand{\WorkKeywords}{关键词一；关键词二；关键词三；关键词四；关键词五}
```

选择作品类别时，仅将目标类别设为 `true`：

```latex
\SoftwareDesigntrue
\HardwareProductionfalse
\EngineeringPracticefalse
\CryptographyAppfalse
\OtherCategoryfalse
```

### 2. 编写正文

模板已按官方示例提供以下结构：

```text
1. 作品功能与性能说明
2. 设计与实现方案
   2.1 实现原理
   2.2 运行结果
   2.3 技术指标
3. 系统测试与结果
   3.1 测试方案
   3.2 功能测试
   3.3 性能测试
   3.4 测试数据与结果
4. 应用前景
5. 结论
```

这些标题是官方模板提供的参考结构，可根据作品实际情况适当增删。

### 3. 生成提交版本

正式提交前，将：

```latex
\TemplateHintstrue
```

改为：

```latex
\TemplateHintsfalse
```

并删除封面上的匿名评审提醒文字。

## 编译方法

### Overleaf

1. 下载本仓库或使用 ZIP 导入 Overleaf。
2. 将编译器设置为 **LuaLaTeX**（也支持 XeLaTeX）。
3. 将主文档设置为 `template.tex`。
4. 点击“重新编译”。

### 本地编译

推荐使用 TeX Live 2024 或更新版本。LuaLaTeX 直接生成 PDF，在部分 Windows
环境中也能避开 `xdvipdfmx.exe` 的异常弹窗：

```bash
latexmk -lualatex template.tex
```

也可以直接运行两次 LuaLaTeX，以更新交叉引用：

```bash
lualatex template.tex
lualatex template.tex
```

在 Overleaf 或 `xdvipdfmx` 工作正常的系统中，也可以使用
`latexmk -xelatex template.tex`。

## 文件结构

```text
CACRcomp-latex-2025/
├── imgs/
│   ├── logo.png          # 中国密码学会标志
│   └── preview.png       # 模板首页预览
├── .gitignore
├── LICENSE
├── README.md
├── template.pdf          # 编译效果示例
└── template.tex          # 主文档，从这里开始
```

## 提交前检查

- [ ] 作品编号与报名系统分配的编号一致。
- [ ] 仅勾选正确的作品类别。
- [ ] 封面和正文未出现单位、指导老师或团队成员姓名。
- [ ] 已关闭灰色模板提示并删除匿名评审提醒。
- [ ] 关键词共五个。
- [ ] 图、表、公式和引用编号连续且可交叉引用。
- [ ] 最终 PDF 无缺字、溢出、空白页或字体替换问题。
- [ ] 已再次核对当届官方通知，确认格式要求没有更新。

## 版本依据与说明

本版本依据仓库随附开发时使用的“附件二——作品设计报告（模板）”整理，目标是复现其结构并改善 LaTeX 使用体验。它不是中国密码学会官方发布物，也不代表组委会对 LaTeX 格式的认可。

本项目派生自 [Reverier-Xu/CACRcomp-latex](https://github.com/Reverier-Xu/CACRcomp-latex)，感谢原作者提供早期模板。原项目与本项目均按照 MIT License 开源，版权与许可信息见 [LICENSE](LICENSE)。

## 贡献

欢迎通过 Issue 反馈排版差异、编译问题或当届模板更新，也欢迎提交 Pull Request。反馈格式问题时，建议附上：

- 使用的 TeX Live / Overleaf 版本；
- 完整编译日志中的首个错误；
- 最小可复现的 `.tex` 片段；
- 与官方模板对应页面的截图。

## License

[MIT License](LICENSE)
