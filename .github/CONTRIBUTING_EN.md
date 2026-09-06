# Contributing Guide

> 中文版：[CONTRIBUTING.md](CONTRIBUTING.md)

## What is welcome

- Bug fixes and edge-case hardening
- Accuracy improvements to the rule engine (scoring / usage / verdicts), with a diagnosis or test attached
- Additions and corrections to the Chinese perfume-name, brand, and accord mappings
- Docs, copy, accessibility, and i18n improvements
- New capabilities aligned with the product's positioning; open an issue first if the proposal moves the product boundary

## Before you start

Every contribution must uphold the [Four Commandments](../docs/技术文档.md#21-四条戒律) (Chinese): no false precision · no over-engineering · light cold-start · closed feedback loop.

- The rule engine decides; the LLM only puts it into words. Scoring and usage verdicts must be deterministic rules, and weather always comes from the QWeather API.
- Graceful degradation first: DeepSeek, weather, and geolocation failures all need fallbacks, and the core recommendation must still appear.
- Before adding a criterion, check the [single-entry-point table](../docs/技术文档.md#51-速查与单一入口) for an existing equivalent; read [Voice and copy](../docs/技术文档.md#7-声音与文案) before changing any user-visible wording. Both are in Chinese.
- Justify any new infrastructure before adding it.

## Local development

Requires Node 24; `engines.node` in `package.json` is the source of truth.

```bash
git clone https://github.com/MrBaoboer/FenCun.git
cd FenCun
npm ci
cp .env.example .env.local   # optional: only needed to exercise live weather or DeepSeek
npm run dev                  # http://localhost:3000
```

It runs without keys. Repository layout and maintenance notes are in the [technical docs](../docs/技术文档.md) (Chinese).

## Before submitting

```bash
npm run lint && npm test && npm run build
```

If you touched the engine, journal, search, store, nudges, or API routes, add test cases. Docs-only PRs can skip these three, but check them yourself: links resolve, commands run, terminology matches `format.ts`, and the Chinese and English files still say the same thing.

## Commits and pull requests

- Use [Conventional Commits](https://www.conventionalcommits.org/): `feat:` / `fix:` / `docs:` / `refactor:` / `test:` / `polish:`, and so on. Commit bodies in Chinese are fine.
- DCO sign-off (`git commit -s`) is encouraged, not required; CI does not check it.
- Branch off `main`; describe the motivation and how you verified the change; attach a before/after comparison or tests for engine changes; CI must pass.

## Governance

- FenCun is maintained by a single person, [@MrBaoboer](https://github.com/MrBaoboer), who owns the product scope, deploy cadence, domain, and merge rights, and may close PRs that go out of scope, carry too much risk, or lack verification.
- Not merged into `main`: shopping / e-commerce, ingredient encyclopedia, social features, account systems, and anything that drifts from the "fragrance-usage decision" core. The current scope and deferred items are in [technical docs · product boundary](../docs/技术文档.md#2-产品边界) (Chinese).
- This section itself can be changed via PR.

## Licensing and Code of Conduct

By submitting a contribution you agree that it is licensed under this project's **AGPL-3.0-only** license and the Section 7 additional terms in [LICENSE](../LICENSE). Participation implies agreement with the [Code of Conduct](CODE_OF_CONDUCT_EN.md).
