# poe2-copilot

《流放之路 2》(Path of Exile 2) 装备估价与 **BD 低配化**工具。

输入一个热门 BD，输出一个**便宜得多、强度损失可量化**的低配版。

---

## 解决什么问题

poe.ninja 上的热门 BD 动辄几十上百 D，大多数玩家买不起。"低配版"是每个赛季都会重新出现的硬需求。

这个工具做三件事：

1. **成本归因** —— 算出构筑里每件装备占总预算多少，揪出占大头的「三大件」
2. **替代搜索** —— 为贵装备找功能等效的便宜替代（同词缀低档位 / 换基底 / 黄装替暗金）
3. **数值校验 + 天赋补偿** —— 验证换装后掉了多少伤害与生存，再用天赋点把丢掉的抗性/属性补回来

## 设计原则

> **数值计算不交给 LLM。**

LLM 只做三件事：理解自然语言意图、编排工具调用、把结果解释成人话。
伤害与生存的计算交给 [Path of Building](https://github.com/PathOfBuildingCommunity/PathOfBuilding-PoE2) 的 headless 引擎，天赋路径用图搜索。

理由很实际：LLM 算数会错，而 ARPG 玩家对数值错误零容忍。

## 状态

🚧 开发中（2026-10 起）。进度见 [docs/progress.md](docs/progress.md)。

| 里程碑 | 状态 |
|---|---|
| M0 数据地基（装备解析 + 词缀数据 + 构筑抓取） | 进行中 |
| M1 成本归因 | 未开始 |
| M2 机制知识库 RAG | 未开始 |
| M3 Agent 化 | 未开始 |
| M4 微调支线 | 未开始 |
| M5 替代搜索 + 天赋补偿 | 未开始 |
| M6 评测与发布 | 未开始 |

## 前置要求

- Python 3.11+
- [Path of Building Community (PoE2)](https://github.com/PathOfBuildingCommunity/PathOfBuilding-PoE2)
  —— 本工具**调用**它的计算引擎，**不复制**其代码

## 开发

```bash
git clone <repo-url>
cd poe2-copilot
python -m venv .venv
.venv\Scripts\activate        # Windows
pip install -r requirements.txt
```

## 目录结构

```
poe2-copilot/
├── src/            源代码
├── data/items/     装备文本样本（只放少量样本，大批量用 scripts/ 自行采集）
├── docs/           设计与评测文档
│   ├── prior-art.md       先例分析（避免重复造轮子）
│   ├── eval-baseline.md   评测基准：手工低配答案
│   └── progress.md        进度日志
└── scripts/        数据采集等一次性脚本
```

## 致谢 / 第三方

- **Path of Building Community (PoE2)** —— MIT 许可，版权归其作者所有。
  本工具依赖它的计算引擎完成数值校验。
- **GGG 官方天赋树数据** —— `grindinggear/poe2-skilltree-export`。
- 游戏数据（物品、词缀、技能宝石）版权归 Grinding Gear Games 所有，
  本仓库仅包含少量样本用于测试，不打包分发完整数据集。

## License

MIT —— 见 [LICENSE](LICENSE)。
