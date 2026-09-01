# Scientific Research Workflows

This MiniMax Code Plugin packages nine complementary, local-first Skills from
[K-Dense Scientific Agent Skills](https://github.com/K-Dense-AI/scientific-agent-skills).
It helps researchers move from an early idea to a defensible study plan, analysis, manuscript, and
review without installing the upstream repository's unrelated, network-dependent, or
separately-licensed Skills.

## Included Skills

| Skill | Upstream version | Use it for |
| --- | ---: | --- |
| `scientific-brainstorming` | 1.1 | Generate and challenge candidate research directions. |
| `hypothesis-generation` | 2.1 | Turn observations into rival, testable hypotheses and predictions. |
| `experimental-design` | 1.1 | Plan randomization, blocking, controls, factorial designs, and study layouts. |
| `statistical-power` | 1.0 | Estimate sample sizes, detectable effects, and simulation-based power. |
| `statistical-analysis` | 1.1 | Select tests, check assumptions, estimate effects, and report results. |
| `uncertainty-and-units` | 1.0 | Check dimensions and propagate measurement uncertainty. |
| `scientific-writing` | 2.0 | Draft and audit evidence-traceable manuscripts and reports. |
| `peer-review` | 2.1 | Prepare authorized, constructive, evidence-bounded review drafts. |
| `scholar-evaluation` | 2.1 | Give qualitative developmental feedback on scholarly work. |

The Skills, references, assets, and scripts are sourced from upstream commit
[`1dd0fccf46fc3c9855c4a0c313a0c57fe4319883`](https://github.com/K-Dense-AI/scientific-agent-skills/commit/1dd0fccf46fc3c9855c4a0c313a0c57fe4319883).
To satisfy this repository's hosted-package validator, the scientific-writing templates use the
`[[DRAFT:...]]` label for unfinished fields; its local linter and scaffold helper were updated
consistently, with no change to the marker's meaning.
The bundle deliberately contains only Skills that declare the MIT license. The upstream repository
contains other Skills with different terms; those are not included here.

## Try it

```text
I am planning a two-site experiment comparing three treatments, but samples arrive in four weekly
batches. Help me define competing hypotheses, design randomization and blocking, estimate the sample
size for 80% power, and produce a preregistration-ready analysis outline. State every assumption and
do not invent pilot data.
```

Expected result: MiniMax Code separates hypotheses from established evidence, identifies the
experimental unit and likely batch/site confounders, proposes a reproducible blocked design, asks for
the effect-size inputs needed for power, and creates an analysis plan with explicit uncertainty and
reporting boundaries.

## Requirements

- MiniMax Code with Agent Skills support.
- Core guidance is platform-neutral and works without installing packages.
- Optional bundled command-line helpers require Python:
  - Python 3.11+ standard library for the brainstorming, hypothesis, writing, peer-review, and
    scholar-evaluation helpers.
  - Python 3.10+ plus `numpy`, `pandas`, and `pyDOE3` for experimental-design helpers.
  - Python 3.10+ plus `numpy`, `pandas`, `scipy`, `statsmodels`, `pingouin`, and `matplotlib` for
    statistical power and analysis helpers. `pymc`, `arviz`, and `lifelines` are optional for the
    corresponding Bayesian and survival workflows.
  - Python 3.12+ plus `pint`, `uncertainties`, `numpy`, and `scipy` for uncertainty-and-units numeric
    helpers.
- Supported on macOS, Windows, and Linux when the selected optional Python dependencies are available.
- No account or paid service is required.

## Data and network

- The Plugin defines no MCP server, telemetry, lifecycle hook, installer, or background process.
- Bundled scripts process bounded JSON, CSV, Markdown, or research data locally and do not make
  network requests.
- The Skills may read user-selected manuscripts, study plans, or datasets from the active workspace
  and may write requested local reports or intermediate artifacts.
- Confidential, unpublished, personal, clinical, or controlled material must remain local unless the
  user has authorization and explicitly chooses an external destination. The peer-review and writing
  Skills include stricter venue and confidentiality checks.
- No credentials required.

Disabling or uninstalling the Plugin removes these Skills from discovery. It does not remove Python
packages the user installed independently or delete files the user asked MiniMax Code to create.

## Attribution and maintenance

- Upstream project: <https://github.com/K-Dense-AI/scientific-agent-skills>
- Upstream snapshot: `1dd0fccf46fc3c9855c4a0c313a0c57fe4319883` (2026-08-31)
- Original author: K-Dense Inc.
- MiniMax Code package maintainer: [hetaoBackend](https://github.com/hetaoBackend)
- License: MIT; see [`LICENSE`](LICENSE).

This community package is an independently maintained selection, not an endorsement by K-Dense or
MiniMax. Future upstream updates require an explicit review of source changes, dependency behavior,
and each included Skill's license before the pinned snapshot is advanced.
