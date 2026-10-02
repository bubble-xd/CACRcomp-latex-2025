# 2026 第十一届全国密码技术竞赛作品设计报告 LaTeX 模板

本项目依据官方提供的《附件二——作品设计报告（模板）》Word 文件制作，并将年份及届次更新为 2026 年第十一届，使用 XeLaTeX 编译。

[查看模板编译效果](template.pdf)

![模板封面预览](imgs/preview-2026.png)

## 模板特性

- A4 纵向排版，四边页边距均为 2 cm；
- 复刻 2026 年封面、作品类别选项和匿名评审提示；
- 第二页为独立基本信息表，并从页码 1 开始编号；
- 正文包含官方模板规定的页眉、页码及一级、二级标题样式；
- 预设楷体、华文楷体、黑体、宋体和 Times New Roman 字体；
- 正文使用 14 pt 楷体、固定 24 pt 行距；一级、二级标题分别为 15 pt 华文楷体和 14 pt 黑体，段前段后各 12 pt；
- 信息表使用宋体，标签为 15 pt，摘要填写文字为 10.5 pt；外框 1.5 pt，内部横线 0.5 pt；
- 作品类别选中时显示勾选框，填写后的作品编号使用黑色。

## 环境要求

推荐使用 TeX Live 2026，并通过 XeLaTeX 编译。模板默认使用以下字体：

- `KaiTi`（楷体）；
- `STKaiti`（华文楷体）；
- `SimHei`（黑体）；
- `SimSun`（宋体）；
- `Times New Roman`。

Windows 通常已安装这些字体。在其他操作系统中使用时，需要安装对应字体，或在 `template.tex` 的字体设置区域替换为可用字体。

## 使用方法

在 `template.tex` 顶部“作品信息”区域填写作品信息：

```tex
\newcommand{\WorkNumber}{系统分配的作品编号}
\newcommand{\WorkTitle}{作品题目}
\newcommand{\WorkDate}{2026年10月1日}
\newcommand{\SelectedCategory}{密码应用技术}
\newcommand{\WorkAbstract}{作品摘要}
\newcommand{\WorkKeywords}{关键词一；关键词二；关键词三；关键词四；关键词五}
```

`\SelectedCategory` 支持以下取值：

- `软件设计`
- `硬件制作`
- `工程实践`
- `密码应用技术`
- `其它`

留空时不会勾选任何类别。正文中的一级标题和二级标题可以根据作品实际情况增删。

## 编译方法

在项目目录运行：

```powershell
latexmk -xelatex -interaction=nonstopmode -halt-on-error template.tex
```

如需强制清理后重新编译：

```powershell
latexmk -C
latexmk -xelatex -gg -interaction=nonstopmode -halt-on-error template.tex
```

编译完成后生成 `template.pdf`。

## 文件结构

```text
.
├── imgs/
│   ├── logo-2026.jpeg    # 中国密码学会标志
│   └── preview-2026.png  # README 封面预览
├── .gitignore
├── README.md
├── template.pdf          # 模板编译效果
└── template.tex          # LaTeX 主文件
```

## 提交前检查

1. 填写竞赛系统自动分配的作品编号。
2. 确认作品类别、题目、摘要和关键词填写完整。
3. 删除封面中的红色填写提示及匿名评审提示文字。
4. 检查封面和正文，不得出现单位名称、指导教师姓名或团队成员姓名。
5. 使用 XeLaTeX 完整编译，并逐页检查表格、图片、公式和分页。

## 说明

所提供的 Word 原件封面写作“2025 年第十届”，本项目已更新年份及届次。原件封面与信息表分别使用“密码应用技术”和“密码技术应用”，本项目统一使用“密码应用技术”。

本项目用于竞赛作品设计报告排版。若竞赛官方后续发布了新版模板或补充要求，应以最新官方文件为准。
