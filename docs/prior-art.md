# 先例分析：avdergh/poe2-exile-architect

> **目的：明确我的差异点，避免重复造轮子。**
> 这条赛道已经有人做了，所以动手前必须先回答："我比它多做了什么？"

- 仓库：https://github.com/avdergh/poe2-exile-architect
- 许可：MIT
- 语言：Python 3.11+
- 已知：它把 AI Agent 接到 PoE2 数据 + 本地知识库 + **Headless PoB**，含简体中文 README

---

## 1. 它做了什么（列功能）

<!-- 读 README，把它的功能一条条列出来 -->

- [ ] 填

## 2. 它怎么做的（架构 / 技术选型）

<!-- 重点看：它怎么调用 PoB？用了什么向量库？LLM 负责哪一部分？有没有评测？ -->

- [ ] 填

## 3. 它没做什么 / 做得不好的地方

- [ ] 填

## 4. 我的差异点（**最重要，必须回答**）

> 我比它多做了什么？

候选答案（读完之后判断哪些成立）：

- [ ] **BD 低配化**：成本归因 + 替代搜索 + 天赋补偿（它做的是"理解 BD"，不是"改造 BD"）
- [ ] **中文 / 国服**：译名映射（V2）
- [ ] **双服**：国际服领先 5–7 天 → 版本前瞻（V2）
- [ ] **评测体系**：手工低配答案基准 + bad case 库

**我的结论**：

- [ ] 填

## 5. 能复用的部分

<!-- 哪些代码/思路可以直接借鉴？如果拷贝代码，必须遵守 MIT（保留版权声明 + README 致谢） -->

- [ ] 填

---

## 其他先例（次要，快速扫一眼即可）

| 项目 | 语言/许可 | 一句话 | 要不要细看 |
|---|---|---|---|
| `SFerenczy/poe2-agent` | Rust | ReAct agent + 把 PoB2 的 Lua VM 包在专用线程里 | 架构参考，值得看它是怎么调 PoB 的 |
| `jodavan/poe2-trading-mcp` | MCP | 14 个交易工具，聚合 poe2scout + trade2 | 交易层参考 |
| `chesler410/poe2-build-forge` | ? | 待核实 | 快速看一眼 |
| `PathOfBuilding-PoE2` | Lua / MIT | 计算引擎本体，有 `HeadlessWrapper.lua` | **必看**：怎么 headless 调用 |
