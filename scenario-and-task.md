# Scenario and task — Regulatory Change Impact & Compliance Actions

You have joined Quillhaven Academy as an automation specialist. Its Compliance and Operations Manager repeatedly compares EU AI Act Article 50 material with internal policy, AI-system records, incidents, evidence gaps, and deadlines. The manual work is slow, and a polished summary can still be unsafe when its authority or evidence is unclear.

Interview the stakeholder to understand the work, sources, ownership, escalation, and approval boundaries. Where the stakeholder cannot define an automation detail, make a reasonable design decision and record its rationale and trade-offs.

Interview entry: [Compliance and Operations Manager](https://work-sim-alpha.catalyte.ai/s/project-b-regulatory-compliance). The facilitator must verify learner identity, interview recording/export and the assigned submission destination before the assessed interview.

**Interview rule.** You conduct the stakeholder interview yourself, and the questions are yours. Do not connect a coding agent or any other AI to the interview to run, script, or automate it. The interview transcript is assessed together with the code; a project whose interview was run by an agent is not scored. This rule applies to human-assessed work. The separate pre-S3 Agent-only authoring trial uses the designer-selected test identity, workspace and submission/capture route; it cannot establish human Ownership or authentic calibration.

Build an Agent Skills-compliant skill named `regulatory-change-impact-brief` with one documented end-to-end command. Keep the provided snapshot contract unchanged. Each run must load and verify the supplied legal baseline, read the current remote company sources, and write a snapshot at every required workflow boundary so the submitted evidence shows how source records became decisions and final drafts.

```text
snapshot.schema.json  # provided contract
inputs/legal/         # full official baseline texts and factual source manifest
regulatory-change-impact-brief/
├── SKILL.md
├── scripts/
└── references/
deliverables/
├── snapshots/
│   ├── 01-scope.json
│   ├── 02-source-capture.json
│   ├── 03-authority-and-timing.json
│   ├── 04-evidence-reconciliation.json
│   ├── 05-impact-analysis.json
│   ├── 06-actions-and-approvals.json
│   └── 07-publication-validation.json
├── impact-register.csv
├── compliance-brief.md
└── action-calendar.ics
```

## Required snapshot chain

Every JSON file above must conform to [`snapshot.schema.json`](snapshot.schema.json). All seven use the same `run_id`. From stage 2 onward, `predecessor` identifies and hashes the immediately preceding snapshot. `consumed_record_ids` names records used from earlier stages; `produced_record_ids` names the records this stage makes available downstream.

| Stage | State that must be preserved |
|---|---|
| 01 Scope | as-of time, review type, systems, audiences, approval gates |
| 02 Source capture | every attempted source and retrieval result, including failed and unused attempts |
| 03 Authority and timing | binding rules, effective timing, labelled guidance context, authority blockers |
| 04 Evidence reconciliation | system facts, policy controls, incidents, conflicts, and evidence gaps |
| 05 Impact analysis | supported impacts, supported no-impact records, conflicts, and unresolved items |
| 06 Actions and approvals | proposed actions, owners, escalations, and pending human decisions |
| 07 Publication validation | final artifact paths and hashes, validation results, and whether publication is validated or blocked |

Run status is `complete`, `partial`, `blocked`, or `failed`. Retrieval status is `retrieved`, `unavailable`, `invalid`, `unverified`, or `stale`. Impact state is `supported-impact`, `supported-no-impact`, `conflicting`, or `unresolved`. Approval status is `pending`, `approved`, `rejected`, or `not-required`. Record only the state that actually occurred; required collections may be empty, but a failed, stale, conflicting, or unresolved record must not disappear in a later stage without a traceable reason and decision.

## Final artifacts

- `impact-register.csv` has one row per impact or unresolved item with stable IDs, state, evidence references, reason, responsible owner, proposed action when applicable, and approval state.
- `compliance-brief.md` states scope, source status, supported impacts, unresolved items, actions, limitations, and pending Legal and Operations decisions.
- `action-calendar.ics` is a valid draft calendar whose events identify the proposed action, timing, owner or review role, and pending approval state.

If authoritative regulatory evidence is unavailable, stage 03 and every dependent stage must remain blocked or unresolved. Do not produce formal impact conclusions. You may still produce the full seven-stage failure chain, an unresolved impact register and brief, and a valid empty or limited draft calendar.

Keep the workflow read-only. Do not expose credentials, alter a source, submit an official response, give final legal advice, activate policy, change an approved deadline, close an incident, or write to a production calendar. Legal and Operations review the package and retain their stated decisions.

The supplied `inputs/source-catalog.md` already lists all nine source entry links and their roles. Use the interview to understand business context, field meaning, uncertainty and approval boundaries; obtaining the listed links does not depend on a particular question. The assessment does not require one programming language, library, or internal architecture.

## Public evidence and source contract

Your supplied entry includes this assignment, the unchanged public snapshot schema, a source catalog and `inputs/legal/`: the full original Regulation (EU) 2024/1689, the full July 2026 amending Regulation (EU) 2026/1744, a 27 July 2026 consolidated reference and a factual source manifest. The assigned baseline review is as of 26 August 2026; source retrieval dates are separate. Use the authentic original and amending acts together. The consolidation is a navigation aid with no independent legal effect. The catalog explains source fields and the role of each official and company document; the stakeholder provides relevant business context and links without requiring special wording. The complete baseline is provided before work; a live official endpoint failure does not erase that verified source. Record any attempted refresh and its actual result. When asserting a later legal update or conducting a later review, establish the appropriate actual source version. Report a missing or corrupt provided baseline to the facilitator, who owns repairing the package. Continue reading current remote company policy/context, registers and calendar on each run. Capturing an official page does not by itself establish the currency or applicability of its displayed text.

Preserve the bytes or permitted claim-bearing extracts actually used under `deliverables/sources/`. Every stage-02 source record records original locator, content type, retrieval timestamp (or actual load time plus original retrieval metadata for the supplied baseline), available version metadata, retrieval status, local evidence path and content hash. Capture all failed and unused attempts too, with honest null content/hash when no content exists. Keep paragraph/section/tab/row locators for extracted claims; hashes alone cannot reconstruct evidence. A login page or generic landing page is not the requested source. Record source warnings and scope limitations. The assessor does not fetch external pages.

Each generic snapshot record needs `id`, a meaningful `summary` and `evidence_ids`; carry actual field values needed by the next stage in the record. `produced_record_ids` identifies records actually present in the sealed stage. Downstream `consumed_record_ids` and evidence references must identify available upstream records. Report unresolved items with subject, reason, source basis, owner when known and the evidence/decision needed to resolve them. Each decision needs concern, options, source basis, chosen behavior, rationale, trade-offs and visible downstream effect. The schema permits additional fields so these business semantics are not reduced to a single prose label.

Source interpretation matters: system names and `complete` evidence flags do not prove legal compliance; `visible_label` does not prove machine-readable provenance; a described human-review process is not proof of an actual approval. Join by stable IDs and preserve every relevant record. A calendar row with `system_id=ALL` is one organization-wide review, not an extra system or eight duplicate events. Source notes referring to a screenshot are reports unless you actually obtain the screenshot. Do not invent a staleness threshold that the owner has not supplied.

For an unavailable non-authoritative or internal source, decide whether to defer the whole run or continue only defensible unaffected work. Explain the trade-off and propagate it consistently into snapshots and every final draft. Neither safe choice is intrinsically preferred. An authoring or permissions error that prevents accessing required company knowledge should be reported to the facilitator; it is not evidence of learner failure. Binding authority absent, invalid or known outdated for the claimed review date blocks dependent formal legal conclusions. A failed optional live refresh alone does not make the intact supplied case-date authority unavailable. Intentional source-failure contrasts are separate from the normal provided baseline. Internal-policy observations must remain separately labelled.

Current retrieval does not make every fact effective at the selected review date. Preserve the source revision and any business-effective date separately from retrieval time. Do not silently use a later-effective correction as evidence of an earlier state; retain the earlier uncertainty or obtain evidence from its owner. A newly selected review date needs a new scope/run and a suitable legal basis.

## Exact final output fields

Use UTF-8 CSV with a header row and one record per distinct system/rule impact or unresolved item. `impact-register.csv` requires `impact_id`, `system_id`, `rule_ref`, `state`, `evidence_ids`, `reason`, `owner`, `proposed_action`, `proposed_due_date`, `approval_status`. Stable identifiers are nonempty; evidence IDs may be semicolon-separated. State and approval status use the snapshot enums. Empty owner/action/date is allowed only when unknown or inapplicable, with the reason and resolution need disclosed. `proposed_due_date` is ISO `YYYY-MM-DD` when known; blank is not zero or an invented deadline. Additional useful columns are allowed. Distinct policy and legal findings must identify their separate rule bases.

`compliance-brief.md` states run ID, as-of date, recipients, draft/run status, source quality and limitations, supported observations, conflicts/unresolved scope, proposed actions/dates and the exact decisions reserved for Legal/Operations. Refer to impact/action/evidence IDs so a reviewer can follow a claim. Do not imply a complete legal conclusion from a partial internal-policy review.

`action-calendar.ics` uses RFC 5545 syntax and a VCALENDAR with VERSION and PRODID. Every event has a stable UID tied to the action, DTSTAMP, DTSTART, SUMMARY and DESCRIPTION containing action/system IDs, responsible role, source/decision basis and approval status. Mark draft proposals with `STATUS:TENTATIVE`; never send invitations or write a production calendar. Use all-day DATE values for date-only business dates; any DTEND is exclusive. Omit an event when its date is unknown and explain the missing date/action in the register and brief. A valid empty calendar is required for a blocked run with no defensible dated proposals. A calendar row's planned/open/scheduled status is not human approval.

## Compatible source changes and recovery

Read the disclosed source roles and required fields by their meaning, not fixed column or row positions. Accept valid source variants that preserve this contract: reordered rows or headers, unrelated extra columns, and legitimate newer date or version values. Keep the required values and stable relationships faithful; do not require an exact remote-source hash, column count or fixed version string merely because an earlier run used it. You need not guess an undisclosed format, renamed required field, new source role or changed business meaning. Missing or ambiguous required fields, invalid dates, authentication pages and unrelated responses still need an honest rejected/held source outcome.

Parser acceptance does not establish legal applicability. A newer source observation/version must not silently move the commissioned 26 August review date or make a later-effective fact true on that date. Preserve the actual value and apply the temporal/authority rules separately. The supplied legal baseline and its manifest must still be verified exactly; accepting compatible mutable company-source formats does not waive those integrity checks.

On a technical failure, preserve the actual failed attempt, affected stage/source/output and repair or next owner in the diagnostic/session evidence. Do not leave an earlier successful bundle presented as the current result. After correcting the fault or restoring access, run the documented command again, reload/verify the baseline, attempt the required current company sources and recompute affected work before validating a fresh package. Preserve the failed occurrence as well as the earlier successful evidence. A truthful scoped partial draft or reasoned whole-run deferral remains permitted under the existing source/authority rules; recovery need not invent resolved business facts or approval.

## Correction, review and repeat runs

The current reviewed run stays at the published seven snapshot paths. Before a rerun replaces any outputs, preserve the complete prior run under `deliverables/history/<old-run-id>/`, including its snapshots, source captures and final drafts, so its paths can be resolved relative to that archived run. Generate a new unique run ID and snapshot IDs. Stage01 records `supersedes_run_id` and the changed source/decision reason; null/absent is permitted on the first run. Record IDs identify the new version or preserve identity with an explicit version relationship. Do not mix predecessor hashes across runs or silently overwrite old evidence. Unchanged reads still have a new attempt timestamp; an incomplete retry must not leave old “successful” files masquerading as current output.

Even when source values and review inputs are unchanged, inspect the actual current output bundle before reporting retry success: all seven required snapshots and their run/predecessor/record bindings, the three required draft files, source evidence needed by that run, final-byte hashes and cross-file agreement. An input hash or earlier success receipt is not proof that those outputs still exist or are intact. Rebuild missing or corrupted derived outputs from available verified evidence and current reads, or return an explicit failed/incomplete result; never return success with a missing brief, damaged calendar or broken required snapshot. The retry is a new run under the same history rule and records its repair/retry reason even when business inputs have not changed. Preserve the prior bytes actually available and explicitly record any pre-existing missing/corrupt evidence; do not fabricate a complete historical bundle or a lost observation.

Correct a fact at the earliest affected stage, then recompute all affected claims, actions and final artifacts. A changed date must not update the brief while leaving the old calendar event. Stage07 hashes the exact final files after writing and validates against stage06; its `publication_status=validated` means internally validated draft, not approved policy or formal publication. A clearly limited but internally consistent partial draft may be validated; an authority blocker cannot be labelled normal validated publication. Run completeness and pending human approval are separate states.

Prepare review requests in the brief/stage06 with request ID, subject system/impact/action, run/source version, evidence, question and required Legal/Operations decision. Bind a request to the reviewed final draft with its path and exact hash in stage07 after the final files are written; stage07 is the detached review binding. The brief/stage06 refers to that request ID and binding location, never its own content hash or a future draft hash. A later response cites that sealed stage07 binding; any changed draft receives a new run/binding and cannot inherit an earlier approval. If actual reviewer feedback is supplied through the facilitator's verified channel, preserve response identity, role, request/subject/version, time, outcome and reasons/conditions. Accept only a matching authorized response; stale or mismatched feedback stays unresolved. Apply requested corrections at the earliest affected stage. A changed basis does not inherit an old approval. Do not simulate reviewer replies. The exercise ends in a review-ready draft; real Legal deliberation, policy activation and production updates are outside scope.

Keep attributable project decisions and expected-versus-observed review in the actual supported session capture. An agent-written account or fabricated interview is not a substitute. The facilitator must provide and verify the interview entry, identity/capture instructions, runtime access and submission target before assigning the live exercise. Do not include credentials in artifacts. Use your documented command to reproduce the supported draft and disclose actual blocked/partial paths. Include your Skill implementation and all current/required history evidence in the submitted repository.
