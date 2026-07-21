# known-unknowns [![skills.sh](https://skills.sh/b/wang-cankun/known-unknowns)](https://skills.sh/wang-cankun/known-unknowns)

[English](./README.md) | 简体中文

这是一个小巧、可组合的 Agent Skill，适合这样的时刻：你知道一件事值得认真讨论，却还不知道该问什么。

它借助拉姆斯菲尔德矩阵（Rumsfeld matrix），让隐性知识变得可以表达，让尚未看见的可能性进入视野，也让不确定的判断可以接受检验。它的目的不是给所有内容贴标签，而是推动讨论真正向前走。

## 快速开始（30 秒）

1. 运行 [skills CLI](https://github.com/vercel-labs/skills)：

   ```bash
   npx skills@latest add Wang-Cankun/known-unknowns
   ```

2. 选择 `known-unknowns`，再选择要安装到哪些编程 Agent。

3. 开始讨论：

   ```text
   $known-unknowns 帮我想清楚这个产品创意是否值得做。
   ```

安装器默认安装到当前项目。如果希望所有项目都能使用，请加上 `-g`：

```bash
npx skills@latest add Wang-Cankun/known-unknowns -g
```

## 它解决什么问题？

普通的 AI 对话经常卡在两个地方：

- **你知道的比你能说出来的更多。** 你能辨认出合适的感觉、区别或取舍，却想不起描述它的词。
- **你无法询问一个从未听说过的选项。** 真正有用的那部分可能性，始终没有进入讨论。

`known-unknowns` 因此给 Agent 换了一项任务：先提供词汇、选项、反例或检验方法，让你多看见问题的一个面向，再提出下一个问题。

## 这张地图

| | 你知道 | 你不知道 |
| --- | --- | --- |
| **你已经意识到** | 已知信息（known knowns）：已经说清并确认 | 已知盲点（known unknowns）：知道问题存在，但还没有答案 |
| **你尚未意识到** | 隐性知识（unknown knowns）：有所感觉，却还说不出来 | 未知领域（unknown unknowns）：你甚至不会想到要问的选项 |

每个区域对应一种推进方式：

- **确认并收束（confirm and compress）** 已经确定的信息。
- **调查（investigate）** 已经明确的盲点，通过证据、推理或实验寻找答案。
- **提供可辨认的词汇（lend words）**，给出具体候选，让用户辨认、拒绝或修正。
- **巡视选项空间（give a tour）**，介绍此前没有出现过的选择，以及各自的适用条件、成本和取舍。

四个符号记录每一项所处的阶段：`✓` 已确定，`?` 已明确的问题，`!` 等待辨认的候选判断，`~` 尚未探索的边界。

## 一次讨论如何进行？

### 1. 先画一张草图

Agent 根据你的主题画出完整矩阵，并把自己的推断标为 `!`。第一版地图可以是错的：纠正一个具体判断，通常比回答一轮空白访谈更容易。

### 2. 每轮只推进一个面向

每一轮都会重新画出紧凑的地图，先为其中一个区域贡献实质内容，再只问一个问题。如果需要用户辨认，问题会附带几个有名称的候选项；如果面对的是不确定性，问题会带上一种检验方法。

### 3. 带走一份可以复用的简报

讨论结束前，Agent 会检查尚未解决的条目，并做一次跳出框架检查（frame-break check）：当前地图之外，是否还有一个足以改变结论的假设或选项？如果没有，它会整理出一份简报，包括你确认的词汇、已经做出的选择、暂时搁置的缺口，以及仍未照亮的部分。

## 试试看

```text
$known-unknowns 我知道哪些界面让人觉得平静，却说不清原因。帮我找到描述它的词汇。
```

```text
$known-unknowns 带我看看：为 AI 助手加入记忆，有哪些我可能还不知道的实现路线？
```

```text
$known-unknowns 帮我判断是否应该接受这份工作，并检验我可能忽略了哪些前提。
```

这个 Skill 会使用你选择的语言进行讨论。

## 管理安装

查看已经安装的 Skill：

```bash
npx skills@latest list
```

更新这个 Skill：

```bash
npx skills@latest update known-unknowns
```

移除这个 Skill：

```bash
npx skills@latest remove known-unknowns
```

如果只想查看仓库提供了哪些 Skill，而不进行安装：

```bash
npx skills@latest add Wang-Cankun/known-unknowns --list
```

## 仓库结构

```text
.
├── README.md
├── README_CN.md
└── skills/
    └── known-unknowns/
        ├── SKILL.md
        └── agents/
            └── openai.yaml
```

仓库根目录面向读者；[`skills/known-unknowns`](./skills/known-unknowns) 才是可以安装的 Skill 包。

## 许可证

MIT
