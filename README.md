# Fact-check skill

Static Markdown guidance for structured claim review and media-literacy workflows. The repository includes a long skill specification, educational material, changelog, and two downloadable archives. It has no executable verifier, source-fetching program, scoring service, or test suite.

| Status | Evidence |
|---|---|
| Source reviewed | 2026-10-02; full recursive tree |
| Executable implementation | None in tracked files |
| Workflow | Instructions for a capable assistant/reviewer; results depend on available tools and evidence |
| Validation | No test set, benchmark, or reproducibility report included |
| License | LICENSE file present; review its terms before reuse |

## Repository contents

- `SKILL.md`: fact-checking procedure and output guidance.
- `educational-tips.md`: media-literacy learning material.
- `CHANGELOG.md`: author-maintained change history.
- `fact-check.skill` and `fact-check-skill-codex-only.zip`: downloadable archives. Their installation and parity with the Markdown source were not verified in this review.

The workflow draws on SIFT and CRAAP concepts, source triangulation, claim decomposition, and explicit uncertainty. Its numerical manipulation score is an author-defined heuristic. It is not a calibrated probability, validated scientific measure, or substitute for subject-matter review.

## Limits

A structured process cannot guarantee a correct verdict. Findings depend on source access, source quality, language coverage, currentness, model behavior, and human judgment. A generated HTML card is an instructed output format, not an included renderer.

Research-effect claims present in the skill specification lack a complete bibliography and should be checked against the cited study and its population/outcome before use. See [content review](CONTENT_REVIEW.md).

## Use

Read `SKILL.md` and follow only the steps supported by the active environment. Verify important claims against primary sources, distinguish evidence from inference, record access limitations, and avoid categorical verdicts when evidence is incomplete. No command-line installation or live fact-check is implemented by this repository.

## Security

See [SECURITY.md](SECURITY.md) before submitting private material, URLs, or screenshots to an assistant or external tool.

## Maintainer

[hmzainjamil](https://github.com/hmzainjamil)
