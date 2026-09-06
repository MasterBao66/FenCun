# 贡献指南

> English version: [CONTRIBUTING_EN.md](CONTRIBUTING_EN.md)

## 欢迎什么

- Bug 修复与边界情况加固
- 规则引擎的准确性改进（打分 / 用法 / 裁决），须附诊断或测试
- 香名 / 品牌 / 香调中文映射的补全与纠正
- 文档、文案、可访问性与国际化改进
- 与产品定位一致的新能力；会动到产品边界的，先开 Issue 对齐

## 动手前

任何贡献都要守住[四条戒律](../docs/技术文档.md#21-四条戒律)：不伪精确 · 不过度设计 · 轻冷启动 · 有反馈闭环。

- 决策权在规则引擎，表达权在 LLM：打分与用法判定必须是确定性规则，天气永远来自和风天气 API。
- 优雅降级优先：DeepSeek、天气或定位失败都要有兜底，核心推荐照常出。
- 新增判据前先查[单一入口表](../docs/技术文档.md#51-速查与单一入口)有没有同义的一条；改用户可见的字之前先读[声音与文案](../docs/技术文档.md#7-声音与文案)。
- 要新增基础设施，先说明为什么非它不可。

## 本地开发

需要 Node 24，以 `package.json` 的 `engines.node` 为准。

```bash
git clone https://github.com/MrBaoboer/FenCun.git
cd FenCun
npm ci
cp .env.example .env.local   # 可选：调试实时天气或 DeepSeek 时才需要填 key
npm run dev                  # http://localhost:3000
```

不配 key 也能跑。目录结构与维护事项见[技术文档](../docs/技术文档.md)。

## 提交前

```bash
npm run lint && npm test && npm run build
```

改了引擎、香历、搜索、存储、钩子或 API 路由的逻辑，要补用例。只改文档的 PR 不必跑这三条，但要核一遍：链接可达、命令能跑、术语与 `format.ts` 一致、中英两份内容对得上。

## 提交与 PR

- 采用 [Conventional Commits](https://www.conventionalcommits.org/)：`feat:` / `fix:` / `docs:` / `refactor:` / `test:` / `polish:` 等，正文写中文即可。
- DCO 签名（`git commit -s`）鼓励但不强制，CI 不校验。
- 从 `main` 开分支，PR 描述写清动机与验证方式；改了引擎的附前后对比或测试；CI 须通过。

## 治理

- 氛寸由 [@MrBaoboer](https://github.com/MrBaoboer) 单人维护，掌握产品边界、部署节奏、域名与合并权，可关闭越界、风险过高或验证不足的 PR。
- 不进主线：导购 / 电商、成分百科、社交、账号体系，以及偏离「用香决策」主线的能力。现行范围与后置项见[技术文档 · 产品边界](../docs/技术文档.md#2-产品边界)。
- 本节自身也可以通过 PR 修改。

## 授权与行为准则

提交贡献即表示你同意按本项目的 **AGPL-3.0-only** 及 [LICENSE](../LICENSE) 中的第 7 条附加条款授权发布。参与本项目即视为同意遵守[行为准则](CODE_OF_CONDUCT.md)。
