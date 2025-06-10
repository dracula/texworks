# Notice

> Although this project involves TeXworks, it does not represent the official actions or endorsement of the TeXworks project. Please read the following carefully.

## Motivation

TeXworks is a simple and excellent $\TeX$ editor that I really like. However, public information suggested that almost no one customizes its themes. Perhaps because it currently does not support official theming.

The good news is that its interface is built on the Qt framework. By designing QSS files to and modifying syntax highlighting settings, this enables support for dark mode or other color themes. This project was inspired by [texworks-dark-theme](https://github.com/ezellohar/texworks-dark-theme).

## Work

This project includes code from the following sources:

- [`darkbg.css`](https://github.com/ezellohar/texworks-dark-theme/blob/main/darkbg.css)

  - **Author**: GitHub user [ezellohar](https://github.com/ezellohar)

  - **License**: GPL-3.0

- [`syntax-patterns.txt`](https://github.com/TeXworks/texworks/blob/main/res/resfiles/configuration/syntax-patterns.txt)

  - **Author**: [TeXworks](https://tug.org/texworks/)

  - **License**: GPL-2.0

In this project, I

- Renamed original QSS file
- Redesigned UI appearance making it more modern
- Updated palettes based on the [Color Palette](https://github.com/dracula/dracula-theme/blob/main/README.md#color-palette)
- Updated pattern syntax settings based on the [Dracula Specification](https://spec.draculatheme.com/)
- Added and updated comments

> [!IMPORTANT]
> These modifications may be affected by future changes in TeXworks. If official actions of the TeXworks project change in the future, it may lead to the need for corresponding adjustments to this project.

Original copyrights belong to the respective authors. Here, I would like to express my gratitude and respect to them.

All the above modifications are copyrighted © 2025 by Wᴏɴɢ Chung and licensed under GPL-3.0 (see the [`LICENSE`](./LICENSE) file for full terms).

Feedback and contributions are welcome!

## Limitations

Stefan Loffler once [said](https://tug.org/pipermail/texworks/2011q2/004333.html):

> In fact, the string given in syntax-patterns.txt is simply wrapped into a QRegExp object (see src/TeXHighlighter.cpp at 226).

Therefore, we can know syntax highlighting of TeXworks uses (somewhat) outdated QtRegExp instead of modern methods like TextMate Grammars or Semantic Highlighting found in other editors. It allows custom highlighting rules, providing flexibility and user control.

However, this brings some restrictions. For example, as far as I know, it

- Lacks context awareness so that it can't seem to understand nested structures or multi-line commands

- Does not support greedy mode and look-behind assertions

- Can not highlight only captured groups in regular expressions

On the other hand, while the current patterns for syntax highlighting of this project have been as much as possible in accordance with Dracula Specification, they also reflect my personal coding habits in some parts. Given the current lack of official guidance for $\TeX$ and my own technical limitations, this project still requires optimization and input from various communities and experts.

---

_Last updated: 2025-06-10_
