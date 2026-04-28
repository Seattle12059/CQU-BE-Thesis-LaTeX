# CQU-BE-Thesis-LaTeX

重庆大学本科毕业论文（设计）LaTeX 模板。

本项目支持两种编译方式：可以上传到 Overleaf 在线编译，也可以在本地 LaTeX 环境编译。本地编译推荐使用 [TinyTeX](https://yihui.org/tinytex/)。

> 说明：模板格式请以学校、学院当年发布的最新要求为准，提交前建议自行核对封面、页眉页脚、目录、图表、参考文献等细节。

## 项目结构

```text
.
├── main.tex          # 主文件，统一加载模板设置和正文内容
├── tex/              # 封面、摘要、目录、章节、参考文献、致谢等内容
├── data/figures/     # 正文图片默认目录
├── fig1.PNG
├── fig2.PNG
└── readme.md
```

正文内容主要在 `tex/` 目录下维护，`main.tex` 通过 `\input{...}` 组织各个部分。

## Overleaf 编译

1. 在 Overleaf 新建项目，选择上传本项目文件，或上传打包后的 zip。
2. 将主文件设置为 `main.tex`。
3. 在 `Menu` 中将编译器设置为 `XeLaTeX`。
4. 点击 `Recompile` 编译，输出文件为 `main.pdf`。

本模板使用了 `ctex`、`fontspec` 等宏包，请使用 `XeLaTeX` 编译，不建议使用 `pdfLaTeX`。

## 本地编译

推荐使用 TinyTeX 作为本地 LaTeX 发行版。TinyTeX 体积较小，基于 TeX Live，适合只为论文项目准备本地编译环境。

安装 TinyTeX 后，在项目根目录执行：

```powershell
latexmk -xelatex -interaction=nonstopmode -file-line-error main.tex
```

如遇到缺少宏包的问题，可根据日志提示使用 `tlmgr` 补装，例如：

```powershell
tlmgr install <package-name>
```


## 常用维护说明

- 论文主体章节：编辑 `tex/chapter1.tex` 到 `tex/chapter5.tex`。
- 中英文摘要：编辑 `tex/abstract.tex`。
- 参考文献：编辑 `tex/references.tex`。
- 致谢：编辑 `tex/thanks.tex`。
- 图片资源：优先放在 `data/figures/`，在正文中直接使用文件名引用。
- 编译产物：`*.aux`、`*.log`、`*.toc`、`*.pdf` 等文件已通过 `.gitignore` 忽略。

