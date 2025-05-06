# tmdl-tools

Neovim Plugin for TMDL / DAX / Power Query support.

## Initial action plan

### 📁 1. Project structure

```bash
nvim.tmdl-tools/
├── lua/
│   └── tmdltools/
│       ├── init.lua             # Main plugin entrypoint
│       ├── treesitter.lua       # Treesitter grammar integration
│       ├── lsp.lua              # LSP or pseudo-LSP setup
│       ├── formatter.lua        # Formatter integration (e.g., conform/null-ls)
│       ├── cmp.lua              # Completion sources/snippets
│       └── utils.lua            # Helper functions
├── plugin/
│   └── tmdltools.lua            # Auto-load setup
├── README.md
├── LICENSE
└── grammars/                    # Extracted/sourced grammars from VS Code or custom
```

### ⚙️ 2. Core milestones

- [ ] ✅ MVP Phase 1: Syntax + Snippets
  - [ ] Extract grammars from VS Code extensions (TMDL, DAX, M).
  - [ ] Convert or stub Treesitter grammars (can start with regex highlighting if needed).
  - [ ] Configure filetype detection (_.tmdl, _.pq, etc.).
  - [ ] Set up snippet support (via LuaSnip or ultisnips) for common DAX/M formulas.
- [ ] 🛠 Phase 2: Formatters and Linting
  - [ ] Use conform.nvim or none-ls.nvim to:
  - [ ] Call DAX Formatter API
  - [ ] Pretty-print TMDL (it's JSON-like)
  - [ ] Optionally add linting logic (e.g., invalid TMDL structure)
- [ ] 🤖 Phase 3: Completion & Intelligence
  - [ ] Stub LSPs or mock completion sources using nvim-cmp.
  - [ ] Add hover, signature help, go to definition if supported externally or by parsing.
- [ ] 📦 Phase 4: Plugin UX
  - [ ] Add plugin configuration options (setup{} function).
  - [ ] Add :TmdlFormat, :TmdlLint, etc. commands.
  - [ ] Add auto-commands for formatting-on-save, filetype hooks.

### 🧠 3. Tooling Sources

- Treesitter: Either create minimal grammars or adapt existing ones (e.g., F#, SQL).
- VS Code Extension Assets:
  - tmLanguage.json → regex highlighter or basis for Treesitter grammar
  - Completion data → convert to snippets or cmp source
