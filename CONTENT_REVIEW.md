# Content review register

Reviewed 2026-10-02 against the tracked tree. This is a documentation audit, not validation of the skill's fact-checking accuracy.

| Area | Status | Evidence or next action |
|---|---|---|
| Executable behavior | Not applicable | No code or automated source-fetching/verdict engine is present; describe as assistant guidance |
| SIFT/CRAAP references | Needs citation review | Add primary method references and explain adaptation; do not imply affiliation or endorsement |
| Research effect statistics in `SKILL.md` | Unverified | The text gives percentages and incomplete citations. Add full references and exact outcome/population or remove the numbers |
| Manipulation & Falsehood Score | Heuristic, unvalidated | Document formula as author-defined; do not present as probability or validated scale |
| Confidence and verdict labels | Needs calibration review | Define observable evidence thresholds and test inter-reviewer consistency before quantitative confidence claims |
| Multilingual verification claims | Unverified | Provide language-specific source and reviewer coverage evidence |
| HTML evidence card | Instruction only | No renderer or HTML output code is included |
| Downloadable archives | Parity unverified | Compare archive contents with canonical Markdown and document supported host/install mechanism |
| Privacy and source submissions | Needs handling policy | Define minimization, provider exposure, retention, deletion, and sensitive-source exclusions |
| Tests and release process | Missing | No test corpus, evaluation protocol, CI workflow, release evidence, or support policy found |

A targeted literature search found the cited topics have study-specific populations and outcome measures. For example, the 2021 accuracy-prompt meta-analysis reports an approximately 10% decrease relative to baseline sharing intentions for false headlines, not a general 15-20% effect claim. The skill's shorthand should not be reused without matching the exact study and outcome. See [the study](https://pmc.ncbi.nlm.nih.gov/articles/PMC9051116/) and [Nature paper](https://www.nature.com/articles/s41586-021-03344-2).

No overall validity score is assigned: there is no evaluation set or independent audit evidence.
