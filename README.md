<div align="center">

<br/>

# 氛寸 · Fēn Cùn

**让每一瓶香，都用在它最好的那一刻。**

别人帮你挑香水，氛寸帮你用好香水。<br/>
从你已有的香柜里，告诉你此刻喷哪瓶、喷多少、喷在哪、能留多久、要注意什么，以及为什么。

<br/>

[![在线体验](https://img.shields.io/badge/在线体验-fencun.vercel.app-1a1a1a?style=for-the-badge)](https://fencun.vercel.app)

<br/>

<table>
  <tr>
    <td align="center"><img src="docs/screenshots/today-day-v13.png" width="260" alt="明韵主题下的今日推荐页：推荐卡、分寸建议与情境栏"/><br/><sub>今日之选 · 明韵</sub></td>
    <td align="center"><img src="docs/screenshots/today-night-v13.png" width="260" alt="暗香主题下的今夜推荐页：同一套推荐卡的深色版本"/><br/><sub>今夜之选 · 暗香</sub></td>
  </tr>
</table>

</div>

<br/>

## 它解决什么

站在香柜前，你从不缺香水，缺的是「今天到底用哪瓶、怎么用得恰到好处」的判断。

氛寸不做导购。它把你已有的香柜、此刻的天气与场合放在一起，先推一瓶，再把用法讲清楚：喷几下、喷在哪、隔多远能闻到、能留多久、有什么要留意。不认同就一键换成任意一瓶，用法即时重算。

## 它会怎么说

| 情境 | 氛寸 |
|---|---|
| 早间通勤，上海 28℃、湿度 80% | 「从你的香柜选**蓝风铃**：清爽柑橘扛这种黏腻天。喷 2 下（手腕＋颈侧），别上身。」 |
| 输入「见客户」 | 「你选的**信仰之水**在商务场偏稳。但今天室内空调密闭，建议只喷 1 下、喷衣领内侧。」 |
| 骤降到 12℃ 还下雨 | 「你常喷的清新柑橘会被压住、留不住。香柜里的**香料炸弹**更扛冷湿天，要不要换？」 |
| 一瓶搁了 35 天 | 「今天干冷的天正是它的主场，翻出来？」 |
| 出门归来 | 「今天，刚好吗」淡了点 · 刚好 · 太冲了 · 不合场合。一次点击，收敛明日用法。 |

## 核心能力

**今日之选** 自动感知实时天气与时段，从你的香柜打分推一瓶，附完整分寸建议。

**不迁就的裁决** good / caution / avoid 三档。真不合适就先说「今天不建议这瓶」，再告诉你坚持要用时怎么补救。

**自然语言场景** 输入「去前任婚礼」「第一次见投资人」，解析出场合、正式度、关系张力、是否饭局，喂进打分与用法。

**发现型钩子** 不等你问：常喷的那瓶今天会翻车，搁置已久的那瓶今天正合适。

**越用越懂你** 答一句「今天，刚好吗」，个人偏移按瓶收敛：嫌冲就少喷，答「刚好」就记住这套配置；高温天答「淡了」归因给天气，不冤枉香水。昨天刚喷的今天自然让位，久置的自然浮起。

**香历** 采纳或反馈的每一瓶自动落进月历，点开任一天是当日快照，可补一句话手记。无香的日子留白。

**演示香柜** 第一次打开就是满配：六瓶示例香水与近一个月的穿香记录。加进你自己的第一瓶，它就整体退场。

**昼夜双主题** 明韵与暗香两套设计语言，右上角随时切。

<div align="center">
<table>
  <tr>
    <td align="center"><img src="docs/screenshots/library-v13.png" width="200" alt="香柜页：香水列表与搜索添加入口"/><br/><sub>香柜</sub></td>
    <td align="center"><img src="docs/screenshots/journal-v13.png" width="200" alt="香历页：月历色点与当日快照"/><br/><sub>香历</sub></td>
    <td align="center"><img src="docs/screenshots/profile-v13.png" width="200" alt="我的分寸页：偏好画像与用香记录"/><br/><sub>我的分寸</sub></td>
  </tr>
</table>
</div>

## 它怎么想

打分、喷量与留香判定全部由确定性规则计算，可解释、可复现；DeepSeek 只负责听懂你的一句话场景，把算好的事实翻成人话。留香与扩散来自 ledecanteur（Fragrantica 社区数据）的真实投票，不采信厂商宣称；天气来自和风天气。LLM 编出来的数字会被整段拦下，LLM 不可用时照样出推荐。

**不伪精确** 留香、喷量、社交距离只给区间与档位，绝不给「留香 6.2 小时」。

**数据在你手里** 香柜、反馈与香历都存在浏览器本机，服务端不保存；「我的」页可导出、导入备份。

## 本地运行

需要 Node 24。

```bash
npm install
cp .env.example .env.local   # 可选：调试实时天气或 DeepSeek 时才需要填 key
npm run dev                  # http://localhost:3000
```

没有 key 也能跑：天气走季节与时段降级，解读走规则模板。

## 更多

[技术文档](docs/技术文档.md) 面向开发者与维护者：架构、规则依据、数据管线、文案规范与维护事项。

[贡献指南](.github/CONTRIBUTING.md) · [获取帮助](.github/SUPPORT.md) · [安全政策](.github/SECURITY.md)

## 许可

Copyright © 2026 MrBaoboer。源代码 [AGPL-3.0-only](LICENSE)，附 §7 商标条款：「氛寸」的名称与标识不在授权范围内，部署修改版请换成你自己的名称与标识。`public/data/` 派生自 ledecanteur / Fragrantica 社区数据，[条款单列](LICENSES/LicenseRef-fragrance-data.txt)；随产物分发的字体与依赖见 [THIRD-PARTY-NOTICES](THIRD-PARTY-NOTICES.md)。
