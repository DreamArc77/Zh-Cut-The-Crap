# 说人话.skill

### 让 ChatGPT / Codex 闭嘴——不是，说人话。

---

> "让我们一起来拆解一下这个需求的底层逻辑，通过多维度的视角拉通各方认知，形成可落地的闭环方案，沉淀出一套体系化的方法论……"
>
> —— 每一个被 ChatGPT 折磨过的中文用户

**你受够了吗？** 我受够了。

这是一个给 [OpenAI Codex](https://openai.com/index/introducing-codex/) 写的 Skill，专治 AI 中文输出的三大绝症：

| 症状 | 临床表现 | 危害等级 |
|------|---------|---------|
| **黑话堆砌** | "赋能""抓手""闭环""拉通""触达" | ⚠️⚠️⚠️ |
| **车轱辘话** | 同一个意思换三种说法再强调一遍 | ⚠️⚠️ |
| **油腻表演** | "让我来为您详细分析一下这个问题的各个方面……" | ⚠️⚠️⚠️⚠️⚠️ |

## 它能干什么

一句话：**把 AI 的"大厂周报体"改成人话。**

- 砍掉黑话、套话、寒暄、铺垫、空转过渡句
- 输出压缩到原文 40%–70%，信息量不变
- 技术术语、代码、路径、数字一个不动
- 安全提醒、风险警告原样保留——说人话不等于说瞎话

### Before & After

**Before（典型 AI 大厂味输出）：**

> 基于上述背景，为了帮助您更好地理解这个问题，我将从多个维度进行深入分析。首先，我们需要对齐一下认知——这个功能的底层逻辑其实是通过一个闭环机制来实现数据的沉淀和复用，从而在更细的颗粒度上提效……

**After（说人话模式）：**

> 这个功能把数据存下来复用，省得重复处理。

**没了。** 因为就这点意思。

## 安装

### 方式一：Codex 内安装（推荐）

在 Codex 里直接说：

```
install skill from github.com/DreamArc77/Zh-Cut-The-Crap
```

### 方式二：手动安装

```bash
# 克隆到 Codex skills 目录
git clone https://github.com/DreamArc77/Zh-Cut-The-Crap.git ~/.codex/skills/zh-cut-the-crap
```

## 使用

### 开启

```
$zh-cut-the-crap on
```

或者直接跟它说："说人话"、"别啰嗦"、"去黑话"——它都懂。

### 关闭

```
$zh-cut-the-crap off
```

或者："恢复正常"、"normal mode"

### 特性

- **会话级持续生效** —— 开一次，整个会话都是人话模式，不用每句都提醒
- **只改表达，不改事实** —— 技术判断、数字、风险提示一个不动
- **严格模式唯一档** —— 没有"稍微少说点废话"这种中间态，要治就治彻底

### 仓库级自动开启（可选）

不想每次手动开？在项目根目录创建 `.codex/hooks.json`：

```json
{
  "hooks": {
    "SessionStart": [
      {
        "type": "command",
        "command": "echo 'ZH-CUT-THE-CRAP ACTIVE. For Chinese output: remove jargon/filler, keep facts, keep technical terms exact. Use concise plain Chinese until user says normal mode or $zh-cut-the-crap off.'"
      }
    ]
  }
}
```

打开 Codex 自动进入人话模式，从此告别废话。

## 内置黑话词典

本 Skill 自带一份[黑话替换词表](references/jargon-rewrite-lexicon.md)，精选互联网大厂高频黑话：

| 黑话 | 人话 |
|------|------|
| 抓手 | 办法 |
| 闭环 | 做完 |
| 对齐 | 说清楚 |
| 拉通 | 协调 |
| 沉淀 | 积累 |
| 触达 | 联系到 |
| 颗粒度 | 细化程度 |
| 复盘 | 回顾总结 |
| 链路 | 流程 |
| 落地 | 做出来 |

完整词表见 [`references/jargon-rewrite-lexicon.md`](references/jargon-rewrite-lexicon.md)

## 为什么做这个

因为每次用中文跟 AI 对话，回复都像在读：

- 大厂周报
- 互联网黑话大赏
- PPT 汇报材料
- 或者以上全部

AI 明明可以好好说话。只是没人告诉它"够了"。

现在有了。

## 不做什么

- **不编造事实** —— 说人话 ≠ 说瞎话
- **不删安全提醒** —— 该警告的还是会警告，只是不会裹三层废话
- **不改代码内容** —— 只优化 AI 跟你说话的方式，代码该怎么写怎么写
- **不是写作助手** —— 默认不改你的文案，除非你主动要求

## 贡献

欢迎 PR。特别欢迎：

- 补充黑话词表（总有新黑话在被发明）
- 发现"漏网之话"提 issue
- 其他语言版本（日语大厂味、韩语大厂味？欢迎）

## Star

如果你也被 AI 的废话折磨过，给个 Star。

不是为了数据好看，是为了让更多人知道：**AI 可以好好说话。**

---

MIT License
