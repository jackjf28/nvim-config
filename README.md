# nvim-config

My personal Neovim configuration, built on **Neovim 0.12+ (nightly)** using the built-in `vim.pack` plugin manager — no external plugin manager required.

---

## Requirements

- Neovim `v0.12+` (uses `vim.pack`, `vim.lsp.config`, and other recent APIs)
- A [Nerd Font](https://www.nerdfonts.com/) for statusline and diagnostic icons
- `git` for plugin installation
- `tree-sitter` CLI for compiling parsers (install via `npm install -g tree-sitter-cli` or `cargo install tree-sitter-cli`)

### LSP / Formatting / Linting tools

Install these separately (e.g. via Mason or your system package manager):

| Tool | Purpose |
|---|---|
| `lua-language-server` | Lua LSP |
| `pyright` | Python LSP |
| `bash-language-server` | Bash LSP |
| `typescript-language-server` | TypeScript/JavaScript LSP |
| `gopls` | Go LSP |
| `clangd` | C/C++ LSP |
| `efm-langserver` | Linting & formatting bridge |
| `stylua` | Lua formatter |
| `luacheck` | Lua linter |
| `black` | Python formatter |
| `flake8` | Python linter |
| `prettier_d` | JS/TS/CSS/HTML formatter |
| `eslint_d` | JS/TS linter |
| `gofumpt` | Go formatter |
| `shfmt` | Shell formatter |
| `shellcheck` | Shell linter |
| `clang-format` | C/C++ formatter |

---

## Installation

```bash
git clone https://github.com/jackfarrell/nvim-config ~/.config/nvim
```

Then open Neovim — plugins will be fetched automatically via `vim.pack`.

---

## Plugins

| Plugin | Purpose |
|---|---|
| [echasnovski/mini.nvim](https://github.com/echasnovski/mini.nvim) | Suite of small utilities (pairs, surround, comments, git, diff, etc.) |
| [ibhagwan/fzf-lua](https://github.com/ibhagwan/fzf-lua) | Fuzzy finder for files, grep, LSP, buffers |
| [stevearc/oil.nvim](https://github.com/stevearc/oil.nvim) | File explorer as a buffer |
| [nvim-treesitter/nvim-treesitter](https://github.com/nvim-treesitter/nvim-treesitter) | Syntax highlighting via Tree-sitter |
| [neovim/nvim-lspconfig](https://github.com/neovim/nvim-lspconfig) | LSP configurations |
| [mason-org/mason.nvim](https://github.com/mason-org/mason.nvim) | LSP/tool installer |
| [creativenull/efmls-configs-nvim](https://github.com/creativenull/efmls-configs-nvim) | EFM language server configs |
| [saghen/blink.cmp](https://github.com/saghen/blink.cmp) | Completion engine |
| [L3MON4D3/LuaSnip](https://github.com/L3MON4D3/LuaSnip) | Snippet engine |
| [nvim-lua/plenary.nvim](https://github.com/nvim-lua/plenary.nvim) | Lua utility library |
| [ThePrimeagen/harpoon](https://github.com/ThePrimeagen/harpoon) | Fast file navigation |

---

## Key Mappings

> Leader key is `<Space>`

### General

| Key | Action |
|---|---|
| `jk` | Exit insert mode |
| `<leader>c` | Clear search highlights |
| `n` / `N` | Next/prev search result (centered) |
| `<C-d>` / `<C-u>` | Half page down/up (centered) |
| `J` | Join lines (keep cursor position) |
| `<leader>pa` | Copy full file path to clipboard |
| `<leader>td` | Toggle diagnostics |

### Buffers & Windows

| Key | Action |
|---|---|
| `<leader>bn` / `<leader>bp` | Next/previous buffer |
| `<leader>sv` / `<leader>sh` | Vertical/horizontal split |
| `<C-Arrow>` | Resize windows |

### File Navigation

| Key | Action |
|---|---|
| `-` | Open parent directory (Oil) |
| `<leader>ff` | Fuzzy find files |
| `<leader>fg` | Live grep |
| `<leader>fb` | Find buffers |
| `<leader>fh` | Search help tags |
| `<leader>fx` / `<leader>fX` | Document/workspace diagnostics |

### Harpoon

| Key | Action |
|---|---|
| `<leader>ha` | Add file to Harpoon |
| `<C-e>` | Toggle Harpoon quick menu |
| `<Space>1-5` | Jump to Harpoon file 1–5 |

### LSP

| Key | Action |
|---|---|
| `<leader>gd` | Go to definition (fzf) |
| `<leader>gD` | Go to definition |
| `<leader>gS` | Go to definition in vertical split |
| `K` | Hover documentation |
| `<leader>ca` | Code actions |
| `<leader>rn` | Rename symbol |
| `<leader>fr` | Find references |
| `<leader>ft` | Find type definitions |
| `<leader>fs` | Document symbols |
| `<leader>fw` | Workspace symbols |
| `<leader>fi` | Find implementations |
| `<leader>oi` | Organize imports |
| `<leader>D` | Line diagnostics |
| `<leader>d` | Cursor diagnostics |
| `<leader>nd` / `<leader>pd` | Next/prev diagnostic |

### Git (mini.diff / mini.git)

| Key | Action |
|---|---|
| `]h` / `[h` | Next/prev git hunk |
| `<leader>hs` | Stage hunk |
| `<leader>hp` | Preview diff overlay |
| `<leader>hb` | Git blame / show at cursor |

### Terminal

| Key | Action |
|---|---|
| `<leader>t` | Toggle floating terminal |
| `<Esc>` | Exit terminal to normal mode |
| `<C-q>` | Close floating terminal |

---

## Features

- **Transparent UI** — background set to none across all standard highlight groups
- **Custom statusline** — shows mode, git branch, filetype, file size, and cursor position with Nerd Font icons; dims on inactive windows
- **Format on save** — auto-formats via EFM on write for supported filetypes
- **Persistent undo** — undo history saved to `~/.vim/undodir`
- **Floating terminal** — toggleable terminal that persists across opens
- **Treesitter folding** — code folding powered by Tree-sitter expressions
