# Legal — Claude Code Rules

This repo holds **legally binding policy documents** for JamSky Games, LLC. Tread carefully.

## Non-negotiables

1. **Never auto-edit any `.md` policy file.** All changes to `PRIVACY_POLICY.md`, `TERMS_OF_SERVICE.md`, and `DISCORD_CODE_OF_CONDUCT.md` require explicit human approval — propose changes, do not apply them. The user reviews and either commits the change or rewords it.
2. **Always update the `_Last updated:_` date** at the top of any doc you propose changes to. Use today's date in the `YYYY-MM-DD` format already in use (e.g. `_Last updated: 2026-04-27_`).
3. **`TERMS_OF_SERVICE.md` also has a `_Version: X.Y_` line.** Bump it whenever proposing material changes (not for typo fixes). Major changes (new clauses, scope expansion) bump the major version; clarifications bump the minor.
4. **No PII in this repo.** These docs describe JamSky's data handling in the abstract — they should never include actual user emails, IDs, or session data.
5. **No autonomous PRs against this repo.** A scheduled agent watching this repo (e.g. effective-date watcher) should report findings, not push commits.

## What the docs cover

| File | Audience | Notes |
|---|---|---|
| `PRIVACY_POLICY.md` | End users | Incorporated by reference into `TERMS_OF_SERVICE.md`. **Must stay aligned with what Incorgnito actually collects** — see cross-repo coupling below. |
| `TERMS_OF_SERVICE.md` | End users | Governs use of Incorgnito and any future JamSky service. Versioned (`_Version: X.Y_`). |
| `DISCORD_CODE_OF_CONDUCT.md` | Discord community | Posted in the `#rules` channel; pairs with Discord AutoMod keyword filters. |

## Cross-repo coupling (critical)

`PRIVACY_POLICY.md` is **load-bearing** with `Incorgnito/`:

- Whenever Incorgnito adds a new SDK, permission, or data category, this Privacy Policy must be updated to disclose it. The reverse-direction problem (policy out of date with what's actually collected) is a real **App Store / Google Play rejection risk**.
- Incorgnito generates periodic reports at `Incorgnito/Documentation/Compliance/Privacy/Reports/PRIVACY_COMPLIANCE_*.md`. When proposing changes here, cross-reference the latest such report.
- A scheduled agent (`Privacy Policy ↔ data collection drift`) watches this coupling. If it flags a gap, treat as P1.

`TERMS_OF_SERVICE.md` references `PRIVACY_POLICY.md` via relative link `[Terms of Service](TERMS_OF_SERVICE.md)` and `[Privacy Policy](PRIVACY_POLICY.md)`. Don't break those links when renaming files.

## Repo conventions

- **No code, no build.** This is a Markdown-only repo.
- All docs use the same heading hierarchy and `_metadata_` line format (`_Last updated: YYYY-MM-DD_`).
- Two-space indents inside lists; `>` blockquotes for emphasis.
- Internal cross-links use relative paths (`./PRIVACY_POLICY.md`), not absolute URLs.

## Definition of Done (for any proposed change)

- [ ] Change is for a substantive reason, not a stylistic preference
- [ ] `_Last updated:_` date bumped to today
- [ ] `_Version:_` bumped if `TERMS_OF_SERVICE.md`
- [ ] Cross-references between docs still resolve
- [ ] No PII or test data introduced
- [ ] Plain English maintained (avoid lawyerese unless legally required)
- [ ] Human has reviewed and approved before commit
