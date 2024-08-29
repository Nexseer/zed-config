# 探索 Zed 编辑器：代码编辑器的未来

👉 [English](README.md) | 简体中文

# 一、Zed 是什么？🧐

> Zed is a next-generation code editor designed for high-performance collaboration with humans and AI.

Zed Editor 是一款支持多人协作的代码编辑器，由 Atom 编辑器的原作者主导开发，底层采用 Rust，主打 “高性能” 😮，无论是插入延迟、启动时间还是内存占用都十分优秀。

Zed Editor 以一种全新的视觉美感进入人们的视野，其旨在为开发者提供一个高效、流畅、且直观的 👍 编程环境。

> 创始人 Nathan 在访谈中的一些看法 💭：
>
> “我梦寐以求的工具既要功能强大，又要拥有简约时尚的外观，并且运行速度飞快。但是，超快的速度和强大的功能很难兼得。可以说我职业生涯的大部分时间都在努力实现这二者的结合，这正是 Zed 的目标。同时我们倾向于在用户体验上坚持简约主义。”
>
> “我不想用按钮取代命令行体验，那对我来说没什么意义。我喜欢接近机器，用语言的方式与它交流。我希望 IDE 能够意识到终端和命令行的存在并干净地集成它们，而不是试图在可视化界面里定义一切。作为 Unix 哲学的自然延伸和补充，我觉得这更适合我。但是，如果我可以通过一个快捷键来运行测试，而不是切换到终端，然后上下键选择再回车，那我很乐意接受它。但我不希望它隐藏了本质，因为这其实就是在运行一个命令。”
>
> “我一直以来的目标是打造一款轻量、简约、体验近似文本编辑器，但又拥有 IDE 强大功能的产品，尽量避免那种延迟的体验和笨重的 UI。这正是我很早之前就想要的，同时它还应该是可扩展的。”

# 二、为什么选择 Zed ？😎

## 1. Fast ⚡

Zed Editor 的轻量级设计让它能够迅速启动，是注重效率的开发人员的理想选择。它以简约为核心，专注于速度和资源的优化利用，确保在不繁琐配置的情况下即可轻松上手。同时，它也提供了丰富的个性化选项，能够满足极客用户的高级需求。

## 2. Intelligent 💻

Zed Editor 集成了 AI 辅助编码功能，使得开发体验更加智能化和高效。无论是代码补全、错误检测，还是自动重构，AI 都能在你编码的每一步提供帮助。这种智能辅助不仅加快了开发速度，还减少了手动编码中的错误和重复工作。

## 3. Collaborative 📶

Zed Editor 最具现代化功能的是团队协作支持。其通过 Channel 和 CRDTs 来支持多人协作开发，意味着开发团队可以同时多人修改同一个文件，并可以同时进行交流讨论。

> 更多的细节可以查看参考 📋 这篇文章：[Zed: 用 Rust 实现终极编辑器之梦](https://cloud.tencent.com/developer/article/2385576)

# 三、怎么使用 Zed ？ 😉

## 1. 快速入门 📝

Zed Editor 目前支持 Mac 与 Linux 系统，后续会提供对于 Windows 系统的官方支持！！Mac 系统支持 `Catalina (10.15) - Sonoma (14.x)` 版本， Linux 系统需要安装相关依赖，查看 [System Requirements - Zed](https://zed.dev/docs/system-requirements) 。

👉 [Linux 安装 Zed](https://zed.dev/docs/linux)

👉 [Mac 安装 Zed](https://zed.dev/docs/getting-started)

Zed Editor 官方尚未发布适用于 Windows 的版本。

不过，有几种方法可以在 Windows 上使用 Zed 编辑器：

1. 自行编译或用其他人编译好的；
2. 使用 WSL (Windows Subsystem for Linux)：在 WSL 中运行 Zed Editor 的 Linux 版本。

## 2. 自定义配置 ✍️

👉 官方手册：[Configuring Zed - Zed](https://zed.dev/docs/configuring-zed)

👉 官方默认设置：[zed/assets/settings/default.json](https://github.com/pjlast/zed/blob/3273f5e4041f67b6703c07a14a1a106c03e36962/assets/settings/default.json)

打开设置 `settings.json`，有以下两种办法：

1. 快捷键 `Ctrl ,`

2. 打开命令面板 `Crtl Shift P`，输入 `zed: open settings` 来打开 `settings.json` 文件。

### Vim 模式

Zed Editor 原生支持 Vim 模式，在 `settings.json` 文件添加：`"vim_mode": true,`

### 代理

在 `settings.json` 文件添加：`"proxy": "http://127.0.0.1:7890",`，方便后续 Zed AI 的使用，关闭并重新启动Zed编辑器，使新的代理设置生效。

### 主题配置

👉 查看各种主题效果：[Zed themes](https://zedz.dev/themes)

1. 通过右上角头像下拉框中的 `Theme`，可以预览内置主题
2. 通过右上角头像下拉框中的 `Extension`，安装主题插件，我使用的就是 `base16` 插件，选择其中的 `snazzy` 主题
3. 自定义主题：将主题json文件（如[GitHub - Brunowilliang/zedspace](https://github.com/Brunowilliang/zedspace)中的`zedspace.json`）放置 `.config/zed/themes/` 下，在 `settings.json` 文件添加：

```json
// 更换主题名
"theme": {
    "mode": "dark",
    "light": "One Light",
    "dark": "ZedSpace Dark Theme"
},
```

👉 更多配置查看官方手册：[Themes - Zed](https://zed.dev/docs/themes)

### 外观配置

```json
"ui_font_size": 22,
// 用户界面（UI）中的字体样式
"ui_font_family": "Cascadia Mono PL",
"buffer_font_size": 26,
// 代码编辑区（Buffer）的字体样式
"buffer_font_family": "JetBrains Mono",
"buffer_font_weight": 500,
"relative_line_numbers": true,
// 隐藏标签栏中的导航历史按钮
"tab_bar": {
  "show_nav_history_buttons": false
},
// 启用文件图标显示，在标签页中显示文件类型对应的图标
// 在标签页中显示文件的 Git 状态
"tabs": {
  "file_icons": true,
  "git_status": true
},
// 内联提示设置
"inlay_hints": {
  "enabled": true,
  "font_family": "Consolas"
},
// 根据缩进级别进行着色
"indent_guides": {
  "coloring": "indent_aware"
},
// 启用软换行，当行长度超过编辑器宽度时自动换行
"soft_wrap": "editor_width",
```

### 基础配置

Zed Editor 内置格式化功能，通过语言服务器协议（LSP）来实现代码格式化。

```json
"tab_size": 2,
// 启用文件保存时自动格式化功能
"format_on_save": "on",
// 设置垂直滚动的边距
"vertical_scroll_margin": 6,
// 编辑器启动时不会自动恢复上次打开的文件或会话
"restore_on_startup": "none",
// 禁用在新行继续注释的功能
"extend_comment_on_newline": false,
// 将特定的文件扩展名与它们对应的文件类型进行关联
"file_types": {
	"C++": ["c", "h", "cpp", "hpp"],
    "*.mdx": ["markdown"]
},
// 文件扫描时要排除的文件和目录模式
"file_scan_exclusions": [
  "**/.git",
  "**/.svn",
  "**/.hg",
  "**/CVS",
  "**/.DS_Store",
  "**/Thumbs.db",
  "**/.classpath",
  "**/.settings",
  "**/vendor",
  "**/.tmp*"
],
// 搜索时要排除的文件和目录
"search.exclude": {
  "**/*.snap": true
  "**/.git": true
  "**/.github": false
  "**/.nuxt": true
  "**/.output": true
  "**/.pnpm": true
  "**/.vscode": true
  "**/.yarn": true
  "**/node_modules": true
  "**/out/**": true
  "**/package-lock.json": true
  "**/pnpm-lock.yaml": true
  "**/temp": true
  "**/yarn.lock": true
  "**/CHANGELOG*": true
  "**/LICENSE*": true
},
"terminal": {
  "font_family": "Cascadia Code NF",
  "toolbar": {
    "title": false
  },
  // 启用在终端中选择文本时自动复制到剪贴板的功能
  "copy_on_select": true
},
"git": {
  // 启用 Git 集成功能
  "enabled": true,
  // 定期从远程仓库获取最新的更改
  "autoFetch": true,
  // 设置自动获取的时间间隔为 300 秒（5分钟）
  "autoFetchInterval": 300,
  // 当编辑器窗口获得焦点时自动获取最新的 Git 更改
  "autoFetchOnFocus": true,
  // 当编辑器窗口切换时自动获取最新的 Git 更改
  "autoFetchOnWindowChange": true,
  // 在构建项目时自动获取最新的 Git 更改
  "autoFetchOnBuild": true,
  // 在编辑器中显示文件的 Git 状态
  "git_status": true,
  // 在指定的构建事件（如构建、运行、调试）时自动获取最新的Git更改
  "autoFetchOnBuildEvents": [
    "build",
    "run",
    "debug"
  ],
  // 设置在构建事件发生后延迟 1500 毫秒（1.5秒）再进行自动获取
  "autoFetchOnBuildEventsDelay": 1500,
  // 设置在构建后延迟 1500 毫秒（1.5秒）再进行自动获取
  "autoFetchOnBuildDelay": 1500,
  // 在编辑器的行号栏（gutter）中显示 Git 状态，仅显示已跟踪文件的状态
  "git_gutter": "tracked_files",
  // ，在代码行旁边显示最后一次修改该行的提交信息
  "inline_blame": {
    "enabled": false,
    "position": "right"
  }
},
```

### 开发配置

Zed Editor 在语言配置方面做得非常好，提供了开箱即用的多语言支持、自动格式化、代码补全等功能，极大地简化了开发者的配置工作。

👉 [Configuring Languages - Zed](https://zed.dev/docs/configuring-languages)

👉 [All Languages - Zed](https://zed.dev/docs/languages)

- **`source.organizeImports: true`**：在格式化代码时自动整理导入语句。
- **`source.fixAll.eslint: true`**：在格式化代码时自动修复所有 ESLint 报告的问题。

Rust 中日常编码中频繁使用 `check`，定期或在代码审查前使用 `clippy`。`clippy` 是 Rust 的一个 lint 工具，提供了更多的代码风格和错误检查。

```json
"languages": {
  "C++": {
    "formatter": {
      "external": {
        "command": "clang-format",
        "arguments": ["-style={BasedOnStyle: Google, IndentWidth: 2}"]
      }
    }
  },
  "Go": {
    "code_actions_on_format": {
      "source.organizeImports": true
    }
  },
  "Rust": {
    "tab_size": 2
  },
  "TSX": {
    "formatter": {
      "external": {
        "command": "prettier",
        "arguments": ["--stdin-filepath", "{buffer_path}", "--tab-width", "2"]
      }
    },
    "code_actions_on_format": {
      "source.organizeImports": true,
      "source.fixAll.eslint": true
    }
  },
  "JavaScript": {
    "formatter": {
      "external": {
        "command": "prettier",
        "arguments": ["--stdin-filepath", "{buffer_path}", "--tab-width", "2"]
      }
    },
    "code_actions_on_format": {
      "source.fixAll.eslint": true
    }
  },
  "TypeScript": {
    "formatter": {
      "external": {
        "command": "prettier",
        "arguments": ["--stdin-filepath", "{buffer_path}", "--tab-width", "2"]
      }
    },
    "code_actions_on_format": {
      "source.organizeImports": true,
      "source.fixAll.eslint": true
    }
  }
},

"lsp": {
  "rust-analyzer": {
    "initialization_options": {
      "checkOnSave": {
        // rust-analyzer.check.command (default: "check")
        // "command": "clippy"
      }
    }
  },
  "eslint": {
    "settings": {
      "codeActionOnSave": {
        "rules": ["import/order"]
      }
    }
  }
}
```

### 数据收集设置

不允许 Zed Industries 收集匿名使用数据~

```json
"telemetry": {
  "diagnostics": false,
  "metrics": false
}
```

## 3. 快捷键 ⌨️

Zed Editor 的快捷键配置（[Key bindings - Zed](https://zed.dev/docs/key-bindings)）以 `json/jsonc` 作为配置格式，形式如下：

```json
[
  {
    "context": "Workspace",
    "bindings": {}
  }
]
```

`context` 上下文条件，只有在满足特定的上下文条件下，对应的快捷键绑定才会生效。

- Pane
- Workspace
- Editor
- Menu
- Terminal
- Assistant
- ProjectPanel
- ProjectSearch
- BufferSearch
- Search
- Dock
- EmptyPane
- SharedScreen
- VimControl
- vim_mode == normal
- vim_mode == visual
- vim_mode == insert
- vim_mode == replace
- vim_mode == operator
- vim_mode == waiting

`bindings` 顾名思义，指定的快捷键；类型可以是字符串、对象、数组。

### 系统默认快捷键

打开命令面板 `Crtl Shift P`，输入 `zed: open default keymap`，打开默认键位映射文件。

### 自定义快捷键

输入 `zed: open keymap` 来打开 `keymap.json` 文件，进行<u>自定义修改</u>。

```json
[
  {
    "bindings": {
      "ctrl-shift-p": "command_palette::Toggle",
      "ctrl-shift-k": "zed::OpenKeymap",
      "ctrl-shift-x": "zed::Extensions",
      "f11": "zed::ToggleFullScreen",
      "ctrl-alt-n": "task::Spawn",
      "ctrl-alt-r": "task::Rerun",
      "ctrl-alt-o": "zed::OpenLocalTasks",
      "ctrl-\\": "workspace::NewCenterTerminal",
      "ctrl-t": "terminal_panel::ToggleFocus"
    }
  },
  {
    "context": "Workspace",
    "bindings": {
      "shift shift": "workspace::NewSearch"
    }
  },
  {
    "context": "Editor",
    "bindings": {
      "ctrl-a": "editor::SelectAll",
      "ctrl-w": "pane::CloseActiveItem",
      "alt-enter": "editor::ToggleCodeActions"
    }
  },
  {
    "context": "Editor && VimControl && !VimWaiting && !menu",
    "bindings": {
      "H": "pane::ActivatePrevItem",
      "L": "pane::ActivateNextItem",
      "K": "editor::Hover",
      "g h": "editor::MoveToBeginningOfLine",
      "g l": "editor::MoveToEndOfLine",
      "g b": "pane::GoBack",
      "g r": "editor::GoToTypeDefinition",
      "g i": "editor::GoToImplementation",
      "space c f": "editor::Format",
      "space c r": "editor::Rename",
      "space e": "project_panel::ToggleFocus",
      "space f o": "outline::Toggle",
      "space f p": "projects::OpenRecent",
      "space f q": "file_finder::Toggle",
      "space g [": "editor::GoToPrevHunk",
      "space g ]": "editor::GoToHunk",
      "space g b": "editor::ToggleGitBlame",
      "space g d": "editor::ToggleHunkDiff",
      "space g r": "editor::RevertSelectedHunks",
      "space m o": "markdown::OpenPreview",
      "space m p": "markdown::OpenPreviewToTheSide",
      "space o": "tab_switcher::Toggle",
      "space p d": "diagnostics::Deploy",
      "space w c": "pane::CloseAllItems",
      "space w k": "pane::SplitUp",
      "space w j": "pane::SplitDown",
      "space w h": "pane::SplitLeft",
      "space w l": "pane::SplitRight"
    }
  },
  {
    "context": "ProjectPanel && not_editing",
    "bindings": {
      "j": "menu::SelectNext",
      "k": "menu::SelectPrev",
      "a": "project_panel::NewFile",
      "A": "project_panel::NewDirectory",
      "c": "project_panel::Copy",
      "d": "project_panel::Delete",
      "p": "project_panel::Paste",
      "r": "project_panel::Rename",
      "x": "project_panel::Cut",
      "y p": "project_panel::CopyPath",
      "y r": "project_panel::CopyRelativePath"
    }
  },
  {
    "context": "Dock || Terminal || Editor",
    "bindings": {
      "ctrl-h": ["workspace::ActivatePaneInDirection", "Left"],
      "ctrl-l": ["workspace::ActivatePaneInDirection", "Right"],
      "ctrl-k": ["workspace::ActivatePaneInDirection", "Up"],
      "ctrl-j": ["workspace::ActivatePaneInDirection", "Down"]
    }
  },
  {
    "context": "Terminal",
    "bindings": {
      "ctrl-t": "workspace::ToggleBottomDock"
    }
  }
]
```

### Vim mode 内置

打开命令面板 `Crtl Shift P`，输入 `vim: open default keymap`，打开 Vim 模式下的默认键位映射文件。

- 内置的 `vim-surround` 插件，如果你想修改、或者删除单引号和双引号：

```
ds<existing>
cs<existing><desired>

# 删除以下的[]
[1, 2, 3] -> ds[

# 将以下的[]修改为()
[1, 2, 3] -> cs[(
```

- 内置的 `vim-commentary` 插件，可视模式下的 `gc` 和普通模式下的 `gcc` 起切换注释作用。

- 内置的 `netrw` 插件，项目面板支持大多数按键绑定。

### 快捷键整理

**全局快捷键**

| 快捷键         | 功能           |
| -------------- | -------------- |
| `ctrl shift p` | 切换命令面板   |
| `ctrl shift k` | 打开快捷键设置 |
| `ctrl shift x` | 打开扩展插件   |
| `F11`          | 切换全屏模式   |
| `ctrl alt n`   | 运行任务       |
| `ctrl alt r`   | 重新运行任务   |
| `ctrl alt o`   | 打开本地任务   |
| `ctrl \`       | 全屏终端       |
| `ctrl t`       | 底部终端       |

**工作区（Workspace）快捷键**

| 快捷键         | 功能                     |
| -------------- | ------------------------ |
| `shift shift`  | 万能搜索                 |
| `ctrl n`       | 新建文件                 |
| `ctrl s`       | 保存当前文件             |
| `ctrl shift s` | 另存为                   |
| `ctrl ?`       | AI 助手面板              |
| `ctrl shift c` | 协作面板（非终端下生效） |

**编辑器（Editor）快捷键**

| 快捷键      | 功能         |
| ----------- | ------------ |
| `ctrl a`    | 全选         |
| `ctrl w`    | 关闭标签页   |
| `ctrl y`    | 取消撤回操作 |
| `alt up`    | 向上移动行   |
| `alt down`  | 向下移动行   |
| `alt enter` | 代码操作     |

**Vim 模式快捷键**

| 快捷键        | 功能                             |
| ------------- | -------------------------------- |
| `{`           | 移动到段落的开始                 |
| `}`           | 移动到段落的结束                 |
| `/`           | 从光标当前位置向下搜索           |
| `?`           | 从光标当前位置向上搜索           |
| `n`           | 下一个搜索匹配项                 |
| `N`           | 上一个搜索匹配项                 |
| `H`           | 上一个标签页                     |
| `L`           | 下一个标签页                     |
| `K`           | 显示悬停信息                     |
| `g h`         | 移动到行首                       |
| `g l`         | 移动到行尾                       |
| `g b`         | 返回到上一个光标位置             |
| `g d`         | 跳转到定义                       |
| `g D`         | 跳转到声明                       |
| `g r`         | 跳转到类型定义                   |
| `g i`         | 跳转到实现                       |
| `g A`         | 跳转到当前单词的所有引用         |
| `g s`         | 在当前文件中查找大纲             |
| `g S`         | 在整个项目中查找大纲             |
| `g ]`         | 跳转到下一个诊断                 |
| `g [`         | 跳转到上一个诊断                 |
| `<space> c f` | 格式化                           |
| `<space> c r` | 重命名                           |
| `<space> e`   | 打开文件资源管理器               |
| `<space> f o` | 查找文件大纲                     |
| `<space> f p` | 打开最近的项目                   |
| `<space> g [` | 跳转到上一个 Git 更改            |
| `<space> g ]` | 跳转到下一个 Git 更改            |
| `<space> g b` | 切换`git blame`                  |
| `<space> g d` | 切换显示当前 `hunk` 的差异       |
| `<space> g r` | 还原选定的 `hunks`               |
| `<space> m o` | 打开 Markdown 预览               |
| `<space> m p` | 在侧边打开 Markdown 预览         |
| `<space> o`   | 标签切换                         |
| `<space> p d` | 错误管理面板                     |
| `<space> w c` | 关闭所有标签页                   |
| `<space> w k` | 向上分割面板                     |
| `<space> w j` | 向下分割面板                     |
| `<space> w h` | 向左分割面板                     |
| `<space> w l` | 向右分割面板                     |
| `[ x`         | 选择上一级语法节点，扩大选择范围 |
| `] x`         | 选择下一级语法节点，缩小选择范围 |

> `git blame` 是 Git 中的一个命令，用于追溯指定文件的历史修改记录。它可以显示文件中每一行代码的最后一次修改信息，包括提交哈希值、作者、日期和时间。
>
> `hunk` 包含了在某个提交中被添加、删除或修改的行。
>
> `[ x` 与 `] x` 命令利用 Tree-sitter 生成的语法树，使得代码编辑器能够智能地选择代码块，从而提高代码编辑和导航的效率。

**项目面板（Project Panel）快捷键**

| 快捷键  | 功能         |
| ------- | ------------ |
| `j`     | 向下         |
| `k`     | 向上         |
| `a`     | 新建文件     |
| `A`     | 新建目录     |
| `c`     | 复制         |
| `d`     | 删除         |
| `p`     | 粘贴         |
| `r`     | 重命名       |
| `x`     | 剪切         |
| `y p`   | 复制路径     |
| `y r`   | 复制相对路径 |
| `<ESC>` | 返回 Editor  |

**面板导航快捷键**

| 快捷键   | 功能           |
| -------- | -------------- |
| `ctrl h` | 跳转到左侧面板 |
| `ctrl l` | 跳转到右侧面板 |
| `ctrl k` | 跳转到上方面板 |
| `ctrl j` | 跳转到下方面板 |

**多光标**

启动多光标模式：按住 Alt 键并点击鼠标左键，可以在多个位置创建光标。

| 快捷键 | 功能                             |
| ------ | -------------------------------- |
| `g a`  | 光标当前词的每个副本添加可视选择 |

**Ex 命令**

| 快捷键          | 功能         |
| --------------- | ------------ |
| `:E[xplore]`    | 打开项目面板 |
| `:C[ollab]`     | 打开协作面板 |
| `:Ch[at]`       | 打开聊天面板 |
| `:A[I]`         | 打开 AI 面板 |
| `:No[tif]`      | 打开通知面板 |
| `:fe[edback]`   | 打开反馈窗口 |
| `:cl[ist]`      | 打开诊断窗口 |
| `:te[rm]`       | 打开终端     |
| `:Ext[ensions]` | 打开扩展窗口 |

# 四、AI 使用 🌟

## 1. Supermaven 智能补全 ✨

<u>Supermaven —— The FREE GitHub Copilot Alternative</u>

在 `settings.json` 文件添加：

```json
"features": {
	"inline_completion_provider": "supermaven"
}
```

点击右下角状态栏中的 Supermaven 图标以登录。

| 快捷键       | 功能                                 |
| ------------ | ------------------------------------ |
| `tab`        | 接受当前的内联补全                   |
| `ctrl right` | 接受当前内联补全，直至下一个单词边界 |
| `alt \`      | 手动触发内联补全请求                 |

## 2. AI Assistant ⭐

👉 [Configurating the Assistant](https://zed.dev/docs/assistant/configuration)

Zed editor 支持以下：

- Zed AI
- Anthropic
- GitHub Copilot Chat
- Google AI
- Ollama
- OpenAI

**Zed AI 目前可以免费使用！！**🎉

👉 [Introducing Zed AI](https://zed.dev/blog/zed-ai)

> Zed AI is available now, free during our initial launch period. Sign in to Zed to access an AI-powered assistant panel and inline code transformations that integrate directly with your editing environment.

Zed AI brings LLMs directly into your editor with an extensible, text-centric approach.

Zed AI 通过可扩展的、以文本为中心的方法将 LLM 直接引入您的编辑器。

### 如何开启Zed AI ？

1. GitHub 帐户登录

2. 点击右下角按钮或者快捷键 `ctrl ?` 打开 AI 助手

3. 选择对应的模型

4. 点击 `Send`，同意相关协议即可使用

![](Pasted%20image%2020240822152835.png)

### Assistant Panel

在助手面板你可以与大语言模型进行互动

- **`You`**: 用户输入的内容或提出的问题。
- **`Assistant`**: AI 助手提供的响应和建议。
- **`System`**: 系统级别的指令或配置，用于设置对话上下文和提供背景信息。

![](Pasted%20image%2020240824211941.png)

👉 命令详情：[Commands - Zed](https://zed.dev/docs/assistant/commands)

| 快捷键         | 功能                           |
| -------------- | ------------------------------ |
| `ctrl n`       | 创建 `context`                 |
| `ctrl enter`   | 确认发送                       |
| `ctrl shift >` | 将选中文本作为引用插入 AI 助手 |
| `alt m`        | 助手面板切换模型选择器         |

### Prompting

点击按钮进入 Prompt Library

![](Pasted%20image%2020240824213606.png)

设置添加 Prompt：👉 [Cursor Directory](https://cursor.directory/) 进行参考

![](Pasted%20image%2020240824213751.png)

在 Assistant Panel 中 输入 `/prompt` + `自定义 Prompt` 即可快速调用！😘

# 五、协作 💥

> “理想的协作环境应该涵盖整个代码开发的生命周期。” —— 创始人 Nathan

协作一直是 Zed Editor 愿景的重要组成部分。从一开始构建 Zed Editor 时就融入了 CRDTs 和文本协同编辑功能。至此编写代码不再是一项孤独的任务，而是一个创造性的、激发思维的过程。

在过去，协作依赖于 Github、屏幕共享、通讯软件等方式，但这会影响你工作的流畅，而你理想中的协作应该始终在代码编辑器中进行，所有操作都集中在此。

👉 [Channels - Zed](https://zed.dev/docs/channels)

👉 [Collaboration - Zed](https://zed.dev/docs/collaboration)

> GitHub 的协作模式感觉像是在发电子邮件，它是异步的信息流，这种方式确实适用于某些情况，所以仍然是一种至关重要的协作方式。

# 六、插件商城 🔌

> “那么我宁愿拥有一个更快的、扩展更少的 Zed，也不愿让它变成一个臃肿的系统”。—— 创始人 Nathan

插件商城中丰富的插件，旨在扩展编辑器的功能，满足不同开发者的需求。

通过右上角头像下拉框中的 `Extension` 或者使用自定义的快捷键 `ctrl shift x`，安装需要的插件！！

Zed Editor 扩展是被编译打包为 WebAssembly (WASM)。这种设计选择有助于提高扩展的性能和安全性，同时也确保了跨平台兼容性。
