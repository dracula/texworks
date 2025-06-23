# Notice

> Although this project involves TeXworks, it does not represent the official actions or endorsement of the TeXworks project. Please read the following carefully.

## Motivation

[TeXworks](https://tug.org/texworks/) is a simple and excellent $\TeX$ editor that I really like. However, public information suggested that almost no one customizes its themes. Perhaps because it currently does not support official theming.

The good news is that its interface is built on the `Qt` framework. By designing QSS files to and modifying syntax highlighting settings, this enables support for dark mode or other color themes. This project was inspired by [texworks-dark-theme](https://github.com/ezellohar/texworks-dark-theme).

## Work

This project includes code from the following sources:

- [`darkbg.css`](https://github.com/ezellohar/texworks-dark-theme/blob/main/darkbg.css)

  - **Author**: [@ezellohar](https://github.com/ezellohar)

  - **License**: GPL-3.0

- [`syntax-patterns.txt`](https://github.com/TeXworks/texworks/blob/main/res/resfiles/configuration/syntax-patterns.txt)

  - **Author**: TeXworks
  - **License**: GPL-2.0

In this project, I

- Renamed original QSS file
- Redesigned UI appearance making it more modern
- Updated palettes based on the [Color Palette](https://github.com/dracula/dracula-theme/blob/main/README.md#color-palette)
- Updated syntax patterns based on the [Dracula Specification](https://spec.draculatheme.com)
- Added and updated comments

> [!IMPORTANT]
> These modifications may be affected by future changes in TeXworks. If official actions of the TeXworks project change in the future, it may lead to the need for corresponding adjustments to this project.

Original copyrights belong to the respective authors. Here, I would like to express my gratitude and respect to them.

All the above modifications are copyrighted © 2025 by Wᴏɴɢ Chung and licensed under GPL-3.0 (see the [`LICENSE`](./LICENSE) file for full terms).

**Feedback and contributions are welcome!**

## Limitations

Stefan Loffler once [said](https://tug.org/pipermail/texworks/2011q2/004333.html):

> In fact, the string given in syntax-patterns.txt is simply wrapped into a QRegExp object (see src/TeXHighlighter.cpp at 226).

Therefore, we can know TeXworks' syntax highlighting uses (somewhat) outdated `QtRegExp` instead of modern methods like TextMate Grammars or Semantic Highlighting found in other editors. It allows custom highlighting rules, providing flexibility and user control.

However, this brings some restrictions. For example, as far as I know, it

- Lacks context awareness so that it can't seem to understand nested structures or multi-line commands

- Does not support greedy mode and look-behind assertions

- Can not highlight only captured groups in regular expressions

On the other hand, while the current patterns for syntax highlighting of this project have been as much as possible in accordance with Dracula Specification, they also reflect my personal coding habits in some parts. Given the current lack of official guidance from Dracula for $\TeX$ and my own technical limitations, this project still requires optimization and assistance from various communities and experts.

---

_Last updated: 2025-06-23_

---

<a id="zh-CN"></a>

<details>

  <summary>中文版</summary>

</br>

# 注意事项

> 本项目虽涉及 TeXworks，但不代表 TeXworks 官方的行为或立场。请仔细阅读以下内容。

## 项目动机

[TeXworks](https://tug.org/texworks/) 是一款简约且优秀的 $\TeX$ 编辑器，我非常喜欢它。然而，公开信息显示几乎没多少人为其定制主题，可能是因为目前官方还未支持主题功能。

好消息是，TeXworks 的界面基于 `Qt` 框架构建。通过设计 QSS 文件并修改语法高亮设置，可以支持深色模式或其他配色主题。本项目的灵感来自于 [texworks-dark-theme](https://github.com/ezellohar/texworks-dark-theme)。

## 工作内容

本项目包含以下来源的代码：

* [`darkbg.css`](https://github.com/ezellohar/texworks-dark-theme/blob/main/darkbg.css)

  * **作者**：[@ezellohar](https://github.com/ezellohar)
  * **许可协议**：GPL-3.0

* [`syntax-patterns.txt`](https://github.com/TeXworks/texworks/blob/main/res/resfiles/configuration/syntax-patterns.txt)

  * **作者**：TeXworks
  * **许可协议**：GPL-2.0

我在本项目中

* 重命名原始 QSS 文件
* 重新设计界面外观，使其更现代化
* 基于 [`Dracula 调色标准`](https://github.com/dracula/dracula-theme/blob/main/README.md#color-palette)更新配色方案
* 根据 [`Dracula 语法高亮规范`](https://spec.draculatheme.com)更新语法模式设置
* 增加和更新代码注释

> ❗ **Important**
> 这些修改可能会受到 TeXworks 未来变动的影响。若 TeXworks 官方发生调整，本项目可能因此需要相应更新。

原始版权归各自作者所有，在此向他们表示感谢与敬意。

上述所有修改的版权: © 2025 Wᴏɴɢ Chung，采用 GPL-3.0 许可（有关完整条款详见 [`LICENSE`](./LICENSE) 文件）。

**欢迎反馈与贡献！**

## 局限说明

Stefan Löffler曾[表示](https://tug.org/pipermail/texworks/2011q2/004333.html)：

> 实际上，syntax-patterns.txt 中的字符串仅被封装为 QRegExp 对象（详见 src/TeXHighlighter.cpp 第 226 行）。

由此可知，TeXworks 的语法高亮采用了较为陈旧的 `QRegExp`，而非其他编辑器常用的现代方法，如 TextMate Grammars 或 Semantic Highlighting 。其允许自定义高亮规则，提供了一定的灵活性和用户控制权。

然而这也带来一些限制。据我所知，比如

* 语法高亮缺少上下文意识而无法识别嵌套结构或跨行命令
* 不支持贪婪模式和回顾断言
* 无不支持捕获组高亮，即无法只高亮正则表达式中的一部分

另一方面，本项目的语法高亮规则虽尽量遵循 `Dracula 语法高亮规范`，但部分内容也参考了我个人的编码习惯。鉴于目前缺乏 Dracula 对 $\TeX$ 官方指导，加之我个人技术水平局限，本项目仍有待各个社区及专家的优化和协助。

---

_最后更新：2025-06-23_

</details>