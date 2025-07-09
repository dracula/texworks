### [TeXworks](https://tug.org/texworks/)

👉[中文版](https://github.com/dracula/texworks/INSTALL.zh-CN.md)

#### Install using Git

If you are a git user, you can install the theme and keep up to date by cloning the repo:

```bash
git clone https://github.com/dracula/texworks.git
```

#### Install manually

Download using the [GitHub _.zip_ download](https://github.com/dracula/texworks/archive/main.zip) option and unzip them.

#### Activating theme

1. Extract `syntax-patterns.txt` (syntax highlighting settings), `theme.css` (QSS configuration), and the `src` folder (icon assets), which are the necessary theme files

2. Find TeXworks' resource directory `<Resources>`.

> ℹ️ **Note A**  
> You can open TeXworks editor if you don't know where the resource directory is: `Help` -> `Settings and Resources...` -> `Resources`

3. Move the aforementioned three to `<Resources>/configuration`:

```bash
mv syntax-patterns.txt theme.css src "<Resources>/configuration"
```

> ℹ️ **Note B**  
> `syntax-patterns.txt` **can not** be renamed or put on other paths! Its eponymous file already exists in `<Resources>/configuration`. This is the default file. You'd better back up the default file before overwriting.

4. Every time you open TeXworks by following the operations below, Dracula theme can be successfully enabled!

```bash
<YourTeXworksPath>/texworks -stylesheet "<Resources>/configuration/theme.css"
```

> ℹ️ **Note C**  
> `theme.css` and `src` can be renamed or have their storage paths changed as long as the path changes are correct. If you decide to do so, don't forget that all the icon paths in the renamed _.css_ file need to be changed as well.

#### Advanced Configuration (optionally)

If you find it inconvenient to manually add the optional `-stylesheet` argument every time you launch TeXworks from the command line, you can follow the steps below for a more permanent solution.

> ❗ **Caution**  
> If you plan to modify global settings, make sure to back up any relevant files beforehand!

- **Windows**

  Right-click on TeXworks' shortcut file and select `Properties`. Then update the content in the `Target` input field to:

  ```powershell
  <YourTeXworksPath>\texworks.exe -stylesheet "<Resources>\configuration\theme.css"
  ```

  This ensures that the theme is applied every time you launch TeXworks via the shortcut. However, opening _.tex_ files directly will still require modifying the global settings.

  To do this, you need to run the `Registry Editor` as an `administrator` and modify the registry entry for your TeX distribution (usually located under `Computer\HKEY_CLASSES_ROOT`).

  The following structure shows the example path for MiKTeX:

  ```
  MiKTeX.tex.2.9
    ├── DefaultIcon
    └── shell
       └── open
          └── command
  ```

  Navigate to the registry key:

  ```
  Computer\HKEY_CLASSES_ROOT\MiKTeX.tex.2.9\shell\open\command
  ```

  Edit or create a new string value (type: _REG_SZ_) and set its data to:

  ```powershell
  <YourTeXworksPath>\miktex-texworks.exe -stylesheet "<Resources>\configuration\theme.css" "%1"
  ```

  After completing these steps, the theme will be enabled globally for TeXworks. You can similarly apply these global settings to other file types such as _.pdf_ and _.bib_ files by performing the same modification on their corresponding registry keys (e.g. `MiKTeX.pdf.2.9` and `MiKTeX.bib.2.9`).

- **Linux** or **macOS**:

  To launch TeXworks in the theme by default, you can create an alias in your shell configuration file (e.g. `.bashrc`, `.zshrc`, or `.profile` on macOS):

  ```bash
  alias texworks='texworks -stylesheet "/path/to/darkbg.css"'
  ```

  After saving the changes, reload your shell configuration with

  ```bash
  source ~/.bashrc # or the respective file
  ```

  and the alias will be ready to use.
