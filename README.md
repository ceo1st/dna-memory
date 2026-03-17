# 🧬 DNA Memory

[English](./README_EN.md) | 中文

> 让 AI Agent 像人脑一样学习和成长

[![Star](https://img.shields.io/github/stars/AIPMAndy/dna-memory?style=flat)](https://github.com/AIPMAndy/dna-memory/stargazers)
[![License](https://img.shields.io/github/license/AIPMAndy/dna-memory)](https://github.com/AIPMAndy/dna-memory)
[![Python](https://img.shields.io/badge/Python-3.8+-blue)](https://www.python.org/)
[![OpenClaw](https://img.shields.io/badge/Built%20for-OpenClaw-purple)](https://github.com/openclaw/openclaw)

---

## 🚀 快速开始

```bash
# 安装
pip install dna-memory

# 使用
python -m dna_memory remember "我喜欢简洁的回复" -t preference
python -m dna_memory recall "偏好"
python -m dna_memory stats
```

---

## 📺 Demo 演示

```bash
$ cd ~/.openclaw/skills/dna-memory

# 记录重要偏好
$ python3 scripts/evolve.py remember "我喜欢简洁的回复" -t preference -i 0.9
✅ 已记录记忆: 我喜欢简洁的回复 [偏好: 0.9]

# 记录技能
$ python3 scripts/evolve.py remember "会用 Python 写 CLI 工具" -t skill -i 0.8
✅ 已记录记忆: 会用 Python 写 CLI 工具 [技能: 0.8]

# 查看记忆统计
$ python3 scripts/evolve.py stats
📊 记忆统计:
   短期记忆: 12 条
   长期记忆: 156 条
   记忆关联: 8 条
   遗忘阈值: 0.3

# 搜索相关记忆
$ python3 scripts/evolve.py recall "偏好"
🔍 搜索: 偏好
   - 我喜欢简洁的回复 [相关性: 0.95]
   - 喜欢用 Markdown 格式 [相关性: 0.87]

# AI 自动归纳模式
$ python3 scripts/evolve.py reflect
💡 模式归纳:
   - 用户偏好简洁风格
   - 技术栈: Python, CLI
   - 沟通风格: 直接高效
```

---

## 🧠 核心特性

### 三层记忆架构

| 层级 | 容量 | 遗忘周期 | 用途 |
|------|------|----------|------|
| 工作记忆 | 5-7 条 | 即时 | 当前对话上下文 |
| 短期记忆 | 100 条 | 7天 | 用户偏好/习惯 |
| 长期记忆 | ∞ | 智能 | 核心技能/知识 |

### 智能遗忘机制

- **权重衰减**：信息随着时间推移自动降低权重
- ** Relevance Filter**：只保留高相关性记忆
- **模式清理**：定期清除低价值重复信息

### 记忆关联

- 构建知识图谱，支持语义搜索
- 自动发现记忆之间的关联
- 支持多维度检索（时间、权重、类型）

---

## 📁 项目结构

```
dna-memory/
├── scripts/           # 命令行工具
│   ├── evolve.py     # 主程序：记忆存取
│   ├── reflect.py    # 模式归纳
│   └── compact.py    # 记忆压缩
├── memory/           # 记忆存储
│   ├── short_term.db    # 短期记忆
│   └── long_term.db    # 长期记忆
├── skills/           # OpenClaw Skill
└── tests/            # 测试用例
```

---

## 🔧 配置选项

```python
from dna_memory import Memory

memory = Memory(
    short_term_capacity=100,    # 短期记忆容量
    long_term_capacity=-1,     # 长期记忆无限
    forget_threshold=0.3,       # 遗忘阈值
    relevance_weight=0.7,      # 相关性权重
)
```

---

## 🤝 贡献

欢迎提交 Issue 和 PR！

1. Fork 本项目
2. 创建特性分支 (`git checkout -b feature/xxx`)
3. 提交更改 (`git commit -m 'Add xxx'`)
4. 推送到分支 (`git push origin feature/xxx`)
5. 创建 Pull Request

---

## 📄 License

MIT License - 随意使用，保留署名即可

---

## 👤 作者

**Andy** - [GitHub](https://github.com/AIPMAndy)

> 让 AI 成为真正的伙伴，而不是每次都要重新介绍的陌生人。
