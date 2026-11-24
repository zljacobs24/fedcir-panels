# Contributing

Thank you for helping improve fedcir-panels. The project is intended to remain a free, understandable, and low-maintenance resource for Federal Circuit argument preparation. Contributions should make the underlying data and methodology easier to trust, not merely add more features.

## Before starting

1. Read `README.md` for the repository layout and `CLAUDE.md` for the detailed methodology, settled decisions, and known limitations.
2. Open or comment on an issue before substantial work. Describe the user need, proposed output, data source, and validation plan.
3. Do not revisit a decision marked as settled in `CLAUDE.md` without discussing it with the owner first.

## Principles

- **Keep maintenance small.** Prefer plain files, existing scripts, and the static site over new services, frameworks, or dependencies.
- **Pilot before scaling.** Test data or AI-assisted features on a small, reviewable sample, record the result, and obtain agreement before processing the archive.
- **Preserve provenance.** A reader should be able to trace a displayed fact or model output to the court source and the rule or process that produced it.
- **Separate raw and derived data.** Keep source material, raw model output, proposed corrections, approved corrections, and published aggregates distinguishable.
- **State limitations plainly.** Record assumptions, validation scope, unresolved errors, and places where human judgment remains necessary.
- **Protect the dashboard's focus.** The main panel view should remain easy to skim. Deeper research tools belong in clearly separated views or tabs.

## Court sources and local artifacts

Use the court's public sitemap, RSS feeds, PDFs, calendars, daily schedule page, and direct recording links as documented in `CLAUDE.md`. Do not bypass bot checks or other access protections.

PDFs, audio, temporary downloads, and exploratory outputs belong under `work/` or another ignored location. Do not commit large reproducible source files merely for convenience.

## Methodology and AI-assisted data

Prefer deterministic text rules for fields that can be extracted reliably. When a model is used:

- constrain its task and output format;
- retain the unmodified input and raw output;
- keep an audit trail for proposed changes;
- validate a sample before scaling; and
- document the model, date, validation, and known limitations.

For transcripts, keep raw ASR output unchanged. Corrections should be proposed against a supplied vocabulary, recorded with their segment, timestamp, confidence, and rationale, and published separately from the raw transcript. Do not attribute speech to a named judge or advocate without human verification. Prefer aggregate analysis over publishing unverified quotations attributed to named speakers.

## Documentation synchronization

`CLAUDE.md` is the detailed project record. Add each new method choice, rule, validation result, and known limitation there.

If a change affects what the public site counts or claims, update `docs/methodology.html` in the same pull request. Keep the plain-language public explanation consistent with the detailed project notes.

Use the Oxford (serial) comma throughout project prose.

## Development workflow

1. Fork the repository or create a focused feature branch.
2. Keep the pull request limited to one coherent change.
3. Run the relevant scripts or checks, and report what was tested in the pull-request description.
4. Confirm that generated or downloaded files have not been committed accidentally.
5. Explain any new dependency, service, recurring cost, or maintenance task.

Maintainer automation may commit directly to `main`. Other contributors should submit changes through pull requests and use their own GitHub identity and no-reply email.

## Validation

There is no single build command for every contribution. At minimum:

- run modified Python scripts on an appropriate sample;
- open changed static pages locally and check desktop, phone, and print behavior when applicable;
- verify generated JSON or CSV files can be rebuilt from documented inputs; and
- inspect `git diff` and `git status` before submitting.

Include the commands run, sample size, and outcome in the pull request.
