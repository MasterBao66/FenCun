# Contributing Guide

> 中文版：[CONTRIBUTING.md](CONTRIBUTING.md)

## What this project welcomes

- 🐛 Bug fixes and edge-case hardening
- 🌡️ Accuracy improvements to the rule engine (scoring / usage / verdicts) — **must include a diagnosis or test**
- 🈶 Additions and corrections to the Chinese perfume-name, brand, and accord mappings
- 📝 Docs, copy, accessibility, and i18n improvements
- ✨ New capabilities aligned with the product's positioning (open an issue first if the proposal moves the product boundary)

Directions that do not fit are listed under Governance below.

## Hard constraints

Every contribution must uphold the [Four Commandments](../README.md#四条戒律) (README, in Chinese): no false precision · no over-engineering · light cold-start · closed feedback loop.

Architecture:

- **The rule engine decides; the LLM only puts it into words.** Scoring, sprays, distance, longevity, and verdicts must be deterministic rules; DeepSeek only parses natural-language scenarios and turns the computed facts into plain language.
- **Weather comes only from the QWeather API**, never invented by the LLM.
- **Graceful degradation first.** DeepSeek timeouts and weather or geolocation failures must have fallbacks; core recommendations still work.
- **Prefer the local rules and static data that already exist**; justify any new infrastructure.

Before you start (all in Chinese):

- Changing a rule: read the [domain rules handbook](../docs/领域规则手册.md) and check the [single-entry-point table](../docs/领域规则手册.md#同一概念的单一入口) for an existing equivalent before adding a criterion;
- Changing user-visible wording: read [声音与文案](../docs/声音与文案.md);
- Changing the data pipeline: read [数据工程](../docs/数据工程.md).

## Local development

Environment, configuration, tests, and pre-submit checks are in [开发与维护](../docs/开发与维护.md); install and run commands are in the README's [本地运行](../README.md#本地运行) section. It runs without keys.

If you touched the engine, journal, search, store, nudges, or the API routes, `npm test` must pass and you should add cases. Docs-only PRs can skip the build, but check yourself: links resolve, commands run, terminology matches `format.ts`, and the Chinese and English files still say the same thing.

## Commit conventions

- Use [Conventional Commits](https://www.conventionalcommits.org/): `feat:` / `fix:` / `docs:` / `refactor:` / `test:` / `polish:`, and so on. Commit bodies are written in Chinese, matching the existing history.
- Signing off is encouraged, not required: `git commit -s` adds a `Signed-off-by` line, certifying under the [Developer Certificate of Origin](https://developercertificate.org/) that you have the right to submit the code. CI does not check it.

## Pull request flow

1. Branch off `main`; keep commits focused and traceable.
2. Describe the motivation and how you verified the change; if you touched the engine, attach a before/after comparison or tests.
3. Target branch is `main`; CI must pass.

## Governance

- **Who decides**: FenCun is maintained by a single person, [@MrBaoboer](https://github.com/MrBaoboer). The maintainer owns the product scope, deploy cadence, domain, and merge rights, and may close PRs that go out of scope, carry too much risk, or lack verification.
- **What does not go into `main`** (the "no" list): no shopping / e-commerce, no ingredient encyclopedia, no social features, no account system, and nothing that drifts from the "fragrance-usage decision + distribution" core. Even elegant implementations of these won't be merged. The current scope and deferred items are in the [product plan](../docs/氛寸-产品方案.md) (Chinese).
- **This section itself can be changed via PR**.

## Licensing of contributions

Unless a file carries different licensing information, by submitting a contribution you agree that it is licensed under this project's **AGPL-3.0-only** license and the Section 7 additional terms in [LICENSE](../LICENSE).

## Code of Conduct

Participation in this project implies agreement with the [Code of Conduct](CODE_OF_CONDUCT_EN.md).
