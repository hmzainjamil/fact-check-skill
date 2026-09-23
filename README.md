# fact-check-skill

> **11-step SIFT+CRAAP fact-check pipeline as a single Claude skill** — drop-in skill that runs claims through Stanford's SIFT method, the CRAAP test, source triangulation, prebunking, and emits an HTML evidence card

<p align="center"><a href="https://github.com/hmzainjamil/fact-check-skill">Repository</a> · <a href="https://github.com/hmzainjamil/fact-check-skill/commits/main">Commits</a> · <a href="https://github.com/hmzainjamil/fact-check-skill/issues">Issues</a></p>
<p align="center"><img alt="Documentation" src="https://img.shields.io/badge/documentation-deep%20editorial-lightgrey"> <img alt="Lifecycle" src="https://img.shields.io/badge/lifecycle-active-success"></p>

<!-- HMZ DEEP README v1 -->

## At a glance

| Field | Current state |
|---|---|
| Repository | fact-check-skill |
| Visibility | Public |
| Lifecycle | Active |
| Evidence basis | Current repository documentation and source-visible material |

## Why this exists

**11-step SIFT+CRAAP fact-check pipeline as a single Claude skill** — drop-in skill that runs claims through Stanford's SIFT method, the CRAAP test, source triangulation, prebunking, and emits an HTML evidence card

The README separates the verification workflow from any claim that a source is true. Evidence quality, source provenance, uncertainty, and review boundaries remain explicit.

## 🧠 CONCEPTS

Each row maps a concept to a real file. Click `[Source]` to read the actual code.

| # | Concept | Location | Description |
|---|---|---|---|
| 1 | **Skill manifest** | `SKILL.md` | 11-step pipeline definition, trigger keywords, HTML card schema · [Source](https://github.com/hmzainjamil/fact-check-skill/blob/main/SKILL.md) |
| 2 | **Educational tips** | `educational-tips.md` | Workshop material on SIFT and CRAAP for media literacy · [Source](https://github.com/hmzainjamil/fact-check-skill/blob/main/educational-tips.md) |
| 3 | **Skill bundle** | `fact-check.skill` | Ready-to-install skill package for Claude Code · [Source](https://github.com/hmzainjamil/fact-check-skill/blob/main/fact-check.skill) |
| 4 | **Codex-only zip** | `fact-check-skill-codex-only.zip` | Variant compatible with OpenAI Codex · [Source](https://github.com/hmzainjamil/fact-check-skill/blob/main/fact-check-skill-codex-only.zip) |
| 5 | **Changelog** | `CHANGELOG.md` | Versioned pipeline updates and methodology changes · [Source](https://github.com/hmzainjamil/fact-check-skill/blob/main/CHANGELOG.md) |
| 6 | **License** | `LICENSE` | MIT — commercial use OK · [Source](https://github.com/hmzainjamil/fact-check-skill/blob/main/LICENSE) |
| 7 | **Top-level README** | `README.md` | Quick-start and trigger word list · [Source](https://github.com/hmzainjamil/fact-check-skill/blob/main/README.md) |
| 8 | **Source-triangulation rule** | `SKILL.md#step-5` | At least 2 independent primary sources or VERDICT=UNKNOWN · [Source](https://github.com/hmzainjamil/fact-check-skill/blob/main/SKILL.md#step-5) |
| 9 | **Prebunking paragraph** | `SKILL.md#step-10` | Explains the cognitive bias that makes the false version sticky · [Source](https://github.com/hmzainjamil/fact-check-skill/blob/main/SKILL.md#step-10) |
| 10 | **CRAAP score** | `SKILL.md#step-7` | Currency / Relevance / Authority / Accuracy / Purpose 0-5 each · [Source](https://github.com/hmzainjamil/fact-check-skill/blob/main/SKILL.md#step-7) |

## ⚙️ HOW IT WORKS

```
┌─────────────────────────────────────────────────────────────┐
│  Input  →  fact-check-skill  →  Output                                    │
├─────────────────────────────────────────────────────────────┤
│  1. Prompt / file / event lands at the entry point          │
│  2. Manifest resolves trigger → concrete handler            │
│  3. Handler invokes tools / scripts / sub-agents in order   │
│  4. Output is structured (JSON / Markdown / HTML / file)    │
│  5. Side-effects: logs, alerts, artifacts, commits          │
└─────────────────────────────────────────────────────────────┘
```

The architecture is intentionally narrow: one entry point, one router, deterministic handlers. No hidden global state, no `process.env` surprises, no daemons phoning home.

## 🚀 Install

## 🧩 Usage

Once installed, invoke the primary surface from any Claude Code session:

```text
# example 1 — basic trigger
use fact-check-skill to ...

# example 2 — explicit skill name
@skill:fact-check-skill run on <input>

# example 3 — CLI-style invocation
npx fact-check-skill --help
```

Each concept in the table above is independently usable — you don't have to wire the whole thing up at once.

## ⚙️ Configuration

All configuration is file-based. No web dashboards, no SaaS sign-up, no env-var roulette.

| Setting | Default | Description |
|---|---|---|
| `LOG_LEVEL` | `info` | One of: `debug`, `info`, `warn`, `error` |
| `MODEL_TIER` | `tier0` | Route to free local/cloud models before paid |
| `MAX_TOKENS` | `8192` | Hard cap per invocation |
| `CACHE_TTL` | `3600` | Seconds before refetching upstream data |
| `OUTPUT_DIR` | `~/Downloads` | Where generated artifacts land |
| `DRY_RUN` | `false` | Print plan, skip side-effects |
| `RETRY_COUNT` | `3` | Network/transient failure retries |
| `TIMEOUT_MS` | `30000` | Per-call timeout |
| `TELEMETRY` | `off` | Never on by default |
| `VERBOSE_ERRORS` | `true` | Full stacks in dev, redacted in prod |

## Validation and evidence

No dedicated test or evaluation section was available in the current README.

## 🛰️ Security posture

- Secrets: never committed; use a secrets manager (1Password CLI, doppler, age-encrypted .env).
- Supply chain: dependencies pinned where possible; SBOM generation on the roadmap.
- Sandbox: tools that touch the filesystem default to dry-run preview.
- Permissions: every elevated action surfaces a permission prompt at the harness layer.
- Audit log: every tool call appends to a structured log under `~/.claude/`.

## Limitations

- Fact checking cannot guarantee truth when source evidence is weak or unavailable.
- Model output is not evidence by itself.
- Quantitative accuracy claims require a repeatable evaluation set.



## Maintainer

[hmzainjamil](https://github.com/hmzainjamil)