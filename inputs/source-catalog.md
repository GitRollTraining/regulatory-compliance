<!-- GENERATED from materials/source-catalog.md for the learner starter; rebuild after source changes. -->
# Quillhaven — Article 50 review source catalog

Source owners maintain the current remote versions. Open the relevant documents during your review and preserve the evidence actually used, including update warnings and unsuccessful reads. These records are a training scenario. Your facilitator must verify the named services and learner access before launch. Read current remote records, not a bundled fixed answer set.

| ID | Business source / owner | Current remote locator and role |
|---|---|---|
| LAW | Article50 / EU official text | https://ai-act-service-desk.ec.europa.eu/en/ai-act/article-50 — service-desk display and any currency warning; reconcile against the supplied original and amending acts |
| OJ | Official Journal / EUR-Lex | https://eur-lex.europa.eu/eli/reg/2024/1689/oj/eng — original Regulation (EU) 2024/1689; verify version and relevant amendments |
| AMEND | Official amendment route / EUR-Lex | https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=OJ%3AL_202601744 — linked by Commission as AI Omnibus text; verify actual returned document and applicability |
| TIME | Official implementation timeline / Commission | https://ai-act-service-desk.ec.europa.eu/en/ai-act/eu-ai-act-implementation-timeline — timing context to reconcile with relevant legislation |
| FAQ | Article50 FAQ / Commission | https://digital-strategy.ec.europa.eu/en/faqs/transparency-obligations-under-article-50-ai-act — explanatory guidance, distinct from binding text |
| POLICY | AI-use policy / Operations, Legal | https://app.notion.com/p/3ba0b700541e81f09998d48f3b1c2856 — unchanged internal controls plus owner-supplied RC-CONTEXT-2026-09-12-R1 operating facts |
| SYSTEMS | AI-system register / system owners | https://docs.google.com/spreadsheets/d/10ky745H_1h9XbGCXPJsiRp5yfdeU08TZtmrsCMinGgU — current uses and reported evidence |
| EVIDENCE | Incident and evidence register / named owners | https://docs.google.com/spreadsheets/d/19BYZ68OSbsa1i9OfF6MzthrdC6q6mt6IWk6ucI8u7Rk — reports, gaps and conflicts |
| CALENDAR | Compliance calendar / Operations | https://docs.google.com/spreadsheets/d/1xtXl_P7Yb9LaECZjjgtlyI-idoAJTAhH-1gQ4vQaCGA — existing proposed actions and reviews |

An official host or successful response is not enough: an authentication page, generic journal index, explicit outdated-text warning or unrelated document is not current authoritative evidence. Inspect returned content and the date/version appropriate to the claim. The source set is extensible to relevant official amendment/definition evidence; record why a newly discovered source is used. All source reads are read-only.

## Provided legal baseline

The starter `inputs/legal/` contains complete structural text of the original Regulation (EU) 2024/1689 and Regulation (EU) 2026/1744, plus the 27 July 2026 consolidated reference and factual source manifest. The original and amending OJ acts establish the legislative source; the consolidation expressly has no legal effect and assists navigation. The case observation date is 26 August 2026; the actual author retrieval is 12 September 2026. A later retrieval date does not move the business or statutory clock.

Every run loads and verifies this provided baseline and reads current remote company sources. Record a live refresh separately and obtain appropriate version evidence before claiming an update. The normal route must not become blocked merely because an optional remote refresh fails while the provided case-date acts remain intact. A missing/corrupt package is a facilitator defect to repair before the dependent trial. No trainer legal verdict, expected system outcome or solved implementation is supplied.

The POLICY page appends `RC-CONTEXT-2026-09-12-R1` owner-supplied EU operating scope and product/use facts after the unchanged policy. Local author representation: `challenges/regulatory-compliance/materials/legal-review-context.md`. That context distinguishes supplied ordinary facts from the identified AI-005 gap, notice/metadata conflicts and unapproved exception; it does not settle statutory interpretation.

## Source field dictionary

Dates use ISO 8601. Company record dates are date-only business dates, not midnight UTC timestamps or automatically approved deadlines. Runtime `as_of` and retrieval timestamps include an offset. No calendar timezone is supplied for time-specific events; use all-day dates when only a date is known, or ask the owner. Exact text states have their source meanings below; blank/unknown is never false, zero, compliant or not-applicable.

| Source / fields | Meaning, key, state and join rules |
|---|---|
| SYSTEMS.system_id | Unique stable system key; join EVIDENCE.system_id and CALENDAR.system_id. No fuzzy name match; duplicated/conflicting identities require clarification. |
| system_name, use_case, owner | Name, operational purpose and team owning facts; preserve exact source text, not proof of legal applicability. |
| provider_role, deployer_role | Reported yes/no/unknown role for the company; legal definitions and actual conduct may need confirmation. No role inferred from product name. |
| exposed_group, output_type | Who encounters outputs and kind of interaction/media. Insufficient alone to determine a paragraph's applicability/exception. |
| current_notice | yes/no/unknown/visible_label/not_applicable are distinct reports; visible label does not prove machine-readable provenance. |
| human_review | Described review/escalation path, not proof it happened or legal sign-off. |
| evidence_status, evidence_updated_at, record_version | Source report state and date/version. complete is not a legal conclusion; stale is an explicit source status, not a newly invented age cutoff. |
| EVIDENCE.record_id | Unique evidence/report ID; multiple records for one system all remain relevant. |
| record_type, reported_at, owner, status | Kind, reporting date, accountable team and business workflow status. closed evidence report does not approve a new impact or close another incident. |
| evidence_ref, evidence_state, notes | Source's evidence locator/status and report text. A locator without supplied underlying bytes is a report, not independent proof the referenced media were inspected. Missing/partial/stale/conflicting remain separate. |
| CALENDAR.action_id, system_id | Unique action and related system; ALL means one organization-wide action covering the inventory, not an additional system or eight duplicate events. |
| action, owner, due_date | Existing action text, team and date. Do not invent dates for missing values or change approved deadlines. |
| status, approval_required, source_version | planned/open/blocked/scheduled are not approvals. Named Legal/Operations review and source revision must travel into draft decisions. |
| POLICY.version and sections | AI-POL-2026-08-15 is internal scenario policy; exceptions require owner, rationale, expiry and Legal approval. |
| Official source fields | Preserve title, URL, paragraph/section, retrieval time, version/amendment/date warning, role and captured content. Separate summary/guidance from law and reported timing from operative text. |

Record counts are 8 systems, 10 evidence reports and 8 actions in the authored 2026-08-26 company set. These are authoring case counts, not a fixed-count requirement for every future live run. A changed remote count must be reconciled against the new scoped population, not rejected merely for differing from an old fixture.

## Recorded source-access check

On 12 September 2026 at 04:52:37.441 UTC, the connected author account fetched the Notion policy page. Its reported last edit was 28 August 2026 at 05:48:16.258 UTC. Every nonempty policy line matched the local authored policy exactly; only blank-line formatting differed. This establishes the observed policy content for that connected account. It does not establish anonymous learner access, deployed runtime access or Notion approval/verification (the page reports unverified). The facilitator must still check the assigned learner route before launch.
