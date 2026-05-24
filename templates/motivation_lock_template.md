# Motivation Lock

> 用途：在 `question_lock.md` 之后、`paper_protocol.md` 之前的一道额外锁。
> question_lock 锁的是"研究问题与对立假设"。
> motivation lock 锁的是"**为什么读者必须读这篇 paper**"。
>
> 二者关系：question_lock 是科学问题层，motivation lock 是 contribution claim 层。
> motivation 没锁定 → 不允许进入 paper_protocol → 不允许写任何正文段落。

## Why this lock exists

实证背书（PaperSpine 设计哲学 + Alvesson & Sandberg 2020）：

- 学术写作最常见的失败不是"研究不好"，而是"没想清楚为什么读者要在乎"
- 一旦边写边想 motivation，最终 introduction 会变成"现状—问题—我们做了 X"的填空模板
- motivation lock 强迫在写作前用一句 ≤ 30 字的话锁定 paper 的**唯一中心动机**

## 锁定项（必填，不允许"待定"）

### 1 · 一句话 motivation

`{读者类型}` + `{当前默认信念 / 缺口 / 假设}` + `{本文做了什么使其重新审视 / 推翻 / 重塑}`

示例：

> "图情与同评研究领域**长期默认 reviewer 评分由维度加权综合**，但**本文用 4 年 ICLR 数据证明 reviewer 是 gestalt-first**，迫使重新审视聚合评分的解释力。"

### 2 · 目标读者画像（≤ 3 类）

不是"对所有研究者有用"。

明确：
- 主读者群（拍板"该不该接收"的人）
- 次读者群（在文献综述中可能引你的人）
- 不针对的群（明确排除以免分散叙事）

### 3 · 一句话"reader 离开本文后能做什么"

读者读完后能形成的具体下一步行动：
- 引用本文 + 调整研究设计？
- 在自己 paper 里改写 limitation 章节？
- 启动 / 放弃某个研究方向？

如果填不出来 → motivation 还没准。

### 4 · 与 question_lock 中的 main_claim 对照

motivation 必须能从 main_claim 推出，但 main_claim 不等于 motivation。

| | main_claim（question_lock）| motivation（本文）|
|---|---|---|
| 形式 | 描述性命题 | 价值性命题 |
| 示例 | "reviewer 在维度上 ICC 低于在 rating 上" | "聚合评分的解释力被高估" |

填写时，明确写出从 main_claim 到 motivation 的"so what"跳跃。

### 5 · 三个 contribution claim（≤ 1 句话各）

按重要性排序：
1. （理论 / 概念贡献）
2. （方法 / 实证贡献）
3. （实践 / 治理含义）

要求：每条都能在 paper Discussion 章被反复引用。如果某条 contribution 在 Discussion 里挂不到任何具体段落，删除。

### 6 · "为什么是现在写"

阐明本文的 timing 必要性。三选一：
- **数据可获得性突变**（如：OpenReview 开放历史数据使 X 第一次成为可能）
- **领域共识被打破**（如：Z 假设近期被 Y 文献质疑，现在是清算时机）
- **政策 / 工具变化**（如：LLM 大规模进入评审 → 必须先建立 baseline）

### 7 · "为什么是你写"（self-evidence，不写进 paper）

诚实写下你比同行的相对优势：
- 数据：你有什么别人不易获得？
- 方法：你掌握什么别人少用？
- 视角：你处在什么 niche 位置？

如果三条都不沾边 → 警报：可能这篇 paper 别人能比你写得更好。

### 8 · "为什么不是其他人"

简短列出领域中可能被认为更适合写这个题的同行 2-3 人，说明为什么他们没写（或没这么写）。

理由模板：
- 数据访问壁垒
- 范式差异
- 关注重心不同
- 时机问题

## Lock 标记

填完以上 8 项后：

```
- 锁定日期：YYYY-MM-DD
- 锁定者：{你的名字}
- 状态：✅ LOCKED
- 任何变更须显式日志（见下方）
```

## 不允许出现的内容

- "本文意义在于…"——所有 motivation 必须以"读者 / 领域"为主语，不能以"本文"为主语
- "首次研究…"——除非有 prior art search 证据，禁用"首次"
- "丰富了 X 领域"——空话，删
- "对推动 X 学科发展具有重要意义"——空话，删
- "希望对相关研究者有所启发"——空话，删

## 状态变更日志

- YYYY-MM-DD · 初次锁定
- YYYY-MM-DD · 修改原因：{}，新版本要点：{}
