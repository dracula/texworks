### [TeXworks](https://tug.org/texworks/)

👉[English](./INSTALL.md)

#### 使用 Git 安装

如果你是 Git 用户，你可以通过克隆项目仓库来安装主题并保持更新：

```bash
git clone https://github.com/dracula/texworks.git
```

#### 手动安装

下载来自 [GitHub 的 _.zip_ 压缩包](https://github.com/dracula/texworks/archive/main.zip)并将其解压。

#### 启用主题

1. 提取 `syntax-patterns.txt`（语法高亮设置）、`theme.css`（QSS 配置）和 `src` 文件夹（图标素材），这些是必要的主题文件

2. 找到 TeXworks 的资源目录 `<Resources>`。

> ℹ️ **Note A**  
> 如果你不知道该资源目录在哪里，可以启动 TeXworks 编辑器：`帮助` -> `TeXworks 配置与资源` -> `资源`

3. 将前述三者移至 `<Resources>/configuration` 中：

```bash
mv syntax-patterns.txt theme.css src "<Resources>/configuration"
```

> ℹ️ **Note B**  
> `syntax-patterns.txt` **不可**被重命名或放至其他路径！`<Resources>/configuration`中已经存在它的同名文件，这是默认文件。你最好在覆盖前备份该默认文件。

4. 每当你按如下操作打开 TeXworks 时，Dracula 主题就能成功启用了！

```bash
<YourTeXworksPath>/texworks -stylesheet "<Resources>/configuration/theme.css"
```

> ℹ️ **Note C**  
> `theme.css` 和 `src` 可以被重命名或更换存放路径，只要保证路径更改正确。若你决定这么做的话，别忘了重命名后的 _.css_ 中的所有图标路径也需一并更改。

#### 高级设置（可选）

若你觉得每次用打开 TeXworks 需要命令行添加可选参数 `-stylesheet` 的方法太麻烦，可以选择执行以下操作。

> ❗ **Caution**  
> 若涉及到全局设置的修改，请一定要提前备份相关文件！

- **Windows**

  右键打开你的 TeXworks 快捷方式文件的`属性`面板，将`目标`输入框中的内容更改为：

  ```powershell
  <YourTeXworksPath>\texworks.exe -stylesheet "<Resources>\configuration\theme.css"
  ```

  这使得你每次通过快捷方式文件打开 TeXworks 后能启用主题。然而直接打开 TeX 相关文档仍需完成全局设置。
  
  若需如此，你需要`以管理员身份运行`打开`注册表编辑器`，给你的 TeX 发行版的项（一般位于 `Computers\HKEY_CLASSES_ROOT`）做更改。
  
  ```
  MiKTeX.tex.2.9
    ├── DefaultIcon
    └── shell
       └── open
          └── command
  ```
  
  上图所示的注册表项目结构以 MiKTeX 为例。你要给注册表项
  
  ```
  Computers\HKEY_CLASSES_ROOT\MiKTeX.tex.2.9\shell\open\command
  ```
  
  的字符串值（类型为 _REG_SZ_，若没有则新建）的数据修改为：

  ```powershell
  <YourTeXworksPath>\miktex-texworks.exe -stylesheet "<Resources>\configuration\theme.css" "%1"
  ```

  完成后即可为 _.tex_ 文件全局地启用主题。类似地，你还可以为 _.pdf_ 文件、_.bib_ 文件等完成全局设置，只要将对应的注册表项重复上述修改（分别对应 `MiKTeX.pdf.2.9` 和 `MiKTeX.bib.2.9`）。

- **Linux** 或 **macOS**

  若你想默认以例如暗色主题启动 TeXworks，可以在你的终端配置文件（如 `.bashrc`、`.zshrc`，macOS 通常使用 `.profile`）中创建一个别名命令：

  ```bash
  alias texworks='texworks -stylesheet "/path/to/darkbg.css"'
  ```
  
  保存更改后，使用
  
  ```bash
  source ~/.bashrc # 或对应配置文件名
  ```
  
  刷新配置，即可启用该别名。
