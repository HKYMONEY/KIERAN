# KIERAN

> **Kieran Obsidian Vault** — 自动同步仓库
> 由 bot-b (Linux VPS) 推送 → GitHub → 你 Windows Obsidian 拉取

---

## 📦 当前内容

| 文件 | 来源 | 用途 |
|------|------|------|
| `木吉他之路.md` | `/root/docs/` | 全局规划（28 章 / 503 行） |
| `童年专练包.md` | `/root/docs/` | 第一首歌专练（13 章 / 715 行） |

---

## 🔄 同步方式

- **bot-b 端**：`/root/docs/` 是源，commit + push 到本仓库
- **你端**：Windows Obsidian + Obsidian Git 插件，pull 拉取

### 你 Windows 端操作

1. 安装 [Git for Windows](https://git-scm.com/download/win)
2. 在 Obsidian 安装 **Obsidian Git** 插件
3. 设置 vault 根目录 = 本仓库的 clone 路径
4. 命令面板 → "Git: Pull"

---

## 📋 文件命名规范

- `*.md` Markdown 笔记（同步）
- 其它文件（图片/zip）默认不上传（见 `.gitignore`）

---

**最后同步时间**：见最近 commit
**bot-b 标识**：`bot-b <bot-b@hermes.local>`