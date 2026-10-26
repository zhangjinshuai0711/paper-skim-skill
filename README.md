# paper-skim · 论文略读

一个用于 Codex / Claude Code 等代理的自创 skill：用通俗中文快速讲懂科研论文。

## 它做什么

- **快速略读**：先讲 Introduction 的问题与动机，再重点拆 Methods 的机制；实验与讨论只提支撑核心创新的证据和边界。
- **逐章补读**：说"下一章"即从上次位置继续，术语按需展开（"DPO 是什么""NDCG 怎么算"）。
- **小步问答推进**：讲一段、问一个简短问题确认理解，不生成试卷、不搞考试。
- **可选整理 Zotero 笔记**：读完后可把讨论整理成一份可复用的中文 Markdown 阅读笔记（模板见 [skill/references/note-template.md](skill/references/note-template.md)）。

不用于：完整双语翻译、正式审稿、交互课程制作。

## 安装

### Codex

```bash
git clone https://github.com/zhangjinshuai0711/paper-skim.git
mkdir -p ~/.codex/skills
cp -r paper-skim/skill ~/.codex/skills/paper-skim
```

### Claude Code 兼容

skill 采用标准 `SKILL.md` frontmatter（name + description）结构，同样放入 `~/.claude/skills/paper-skim/` 即可使用。

## 使用

对代理说：

> 用 paper-skim 带我读这篇论文，先重点讲 Introduction 和 Methods，再逐章补读，术语按需解释，最后给我整理 Zotero 笔记的选项。

## 文件结构

```
skill/
├── SKILL.md                    # 核心阅读与讲解规则
├── agents/openai.yaml          # OpenAI/Codex 界面元数据
└── references/note-template.md # Zotero 笔记整理模板
```

## License

MIT
