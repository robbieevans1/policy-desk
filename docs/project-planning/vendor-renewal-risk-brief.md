---
prd_id: "PRD-001"
title: "policy-desk Vendor Renewal Risk Brief"
description: "Transcript-grounded draft requirements and unresolved decisions for the vendor renewal risk brief."
status: "draft"
version: "0.1.0"
owners: ["Priya Raman (sponsor; PRD approval authority not established)"]
reviewers: []
created_date: "2026-10-07"
last_updated: "2026-10-07"
product_goal_ids: ["GOAL-001", "GOAL-002", "GOAL-003"]
product_goal_smart_status: "deferred"
fr_to_ac_coverage_threshold_pct: 80.0
fr_to_goal_coverage_threshold_pct: 100.0
diagram_format: "none"
lineage:
  supersedes: []
  superseded_by: []
source_brd_id: null
requirement_id_prefixes:
  fr: "FR"
  ac: "AC"
  nfr: "NFR"
  con: "CON"
  goal: "GOAL"
---

## Executive Summary

policy-desk will produce a vendor renewal risk brief to help TPRM analysts assemble a consistent, evidence-backed renewal picture for business owners. Analysts currently spend about three hours assembling a Tier 1 renewal review. The stated target is under 45 minutes, including analyst review, not generation alone. The baseline is approximate and has not yet been retrieved from renewal-case time records. [E01, E15, E20]

The brief covers vendor tier, findings, exceptions, contract value and re-sourcing, scorecards, financial health, incidents, and policy-derived approvals and deadlines. Blockers appear first. Every substantive statement points to a policy document or source record. The output is Markdown for pasting into a ProcureNet renewal ticket. It informs the business owner's decision; it does not recommend renewal or make the decision. [E02, E04-E09, E16]

Scheduled generation occurs 30 days before the policy-defined notice window opens. Business owners can also request a brief on demand. Both paths require TPRM analyst checking and correction before delivery to the business owner. Generation must take under two minutes; the human review service level remains unresolved. [E03, E09-E10, E12, E17]

This is a source-complete draft, not an approved or implementation-ready specification. Vendor eligibility, production integration, cost ceiling, retention reconciliation, and several operating details remain open. A CSV prototype for one vendor and a possible Tier 1 card-processor pilot were discussed; neither establishes production architecture or a committed release date. [E10-E14, E18-E19]

## Product Context

### Evidence boundary

The [kickoff transcript](../meetings/renewal-kickoff-transcript.md) is the only evidence for capability requirements, goals, constraints, decisions, and action ownership. Timestamp references below identify statements within that source. The transcript warns that attribution may be inaccurate; the logging/evaluation statement at 00:24:53 was explicitly corrected to Dana at 00:25:12. Inaudible words are not treated as evidence.

The [README](../../README.md) supplies existing-system context only. No corpus documents, external standards, or additional code have been used to settle product questions. Acceptance criteria operationalize explicit transcript decisions; unspecified behavior is recorded under Open Questions instead of supplied by the author.

For the lab's notice-window check only, [contract-renewal-procedure.md](../../corpus/contract-renewal-procedure.md), Section 2, independently confirms the corrected windows recorded in transcript evidence E17: 120, 90, 60, and 30 days for Tiers 1 through 4. This cross-check corroborates the transcript; it is not additional evidence for capability requirements or vendor scope.

### Existing system

The README describes grounded policy Q&A with an Agent Framework agent, a policy-retrieval tool, a local vector index, and post-answer verification of `[doc_id: ...]` citations against retrieved document IDs. Runtime uses Foundry chat and keyless Azure authentication. Offline tests do not call the network.

This is not evidence that source-record citation, renewal-data integration, analyst review, or audit retention already exists. Tom's statement that prompts and retrieved documents are logged is a transcript-reported baseline, not a capability verified by the README. [E13]

### Problem and opportunity

TPRM repeatedly assembles the same risk picture, Procurement discovers High findings too close to expiry, and business owners receive inconsistent documents that paste poorly into tickets. The capability addresses preparation and evidence presentation, not automated approval or vendor negotiation. [E01, E09, E15-E16]

### Evidence register

All E identifiers refer to the kickoff transcript, not independent sources.

| ID    | Transcript timestamps                | Evidence                                                                                                          |
| ----- | ------------------------------------ | ----------------------------------------------------------------------------------------------------------------- |
| E01   | 00:00:21-00:00:57                    | Repeated analyst work, late High findings, brief rather than decision                                             |
| E02   | 00:01:38-00:02:27                    | Policy/source-record citations; click through to finding; omit unsupported statements                             |
| E03   | 00:03:09-00:04:11                    | Generate 30 days before notice window opens, not before expiry                                                    |
| E04   | 00:04:14-00:05:02                    | Vendor tier; open findings/exceptions and expiry; current TCV; crossing $250,000; no amendment history            |
| E05   | 00:05:06-00:05:26                    | Last four scorecards, newest first; open improvement plan first; no computed ratings                              |
| E06   | 00:05:29-00:05:45                    | Treasury Green/Amber/Red, review date, watch list; Red stop until TPRC review; quarterly spreadsheet              |
| E07   | 00:05:47-00:06:35                    | Last 12 months of incidents, notification deadlines; ServiceNow fields and previous contact-data leak             |
| E08   | 00:06:38-00:07:10                    | Approvers/deadlines, business-owner approval, finding/exception blockers, CRO, concentration check, exit deadline |
| E09   | 00:09:04-00:10:53                    | Markdown paste into ProcureNet case; business-owner on-demand request                                             |
| E10   | 00:02:31-00:03:02; 00:11:11-00:13:47 | Scope dispute, estimated volumes, analyst review for both paths; tentative same-day review                        |
| E11   | 00:15:15-00:18:09                    | ProcureNet/Coupa export, API access delay, contract-PDF option; production choice left open                       |
| E12   | 00:20:39-00:22:09                    | Under two-minute generation; unsettled $1 versus $0.50 cost ceiling                                               |
| E13   | 00:22:20-00:23:56                    | Audit of what model saw; 30-day raw personal-data logs, 13-month summaries, seven-year renewal record conflict    |
| E14   | 00:24:14-00:25:24                    | Before/after analyst edits; correction evidence; Dana attribution correction                                      |
| E15   | 00:26:28-00:30:05                    | Negotiation out of v1; three-hour baseline; under 45 minutes including review; rewriting means failure            |
| E16   | 00:32:20-00:33:22                    | Explicit missing/stale-source indication; no guessing; no renewal recommendation; blockers first                  |
| E17   | 00:36:12-00:37:01                    | Corrected windows: Tier 1 120 days, Tier 2 90, Tier 3 60, Tier 4 30; policy-derived trigger                       |
| E18   | 00:39:08-00:41:03                    | Tentative pilot; CSV prototype; named actions for Tom, Marcus, Dana, Priya, Lena                                  |
| E19   | 00:41:23-00:43:14                    | Records reconciliation explicitly unowned; reviewer name, not phone; vendor-master lineage unknown                |
| E20   | 00:44:39-00:44:51                    | Closing clarification: 45 minutes including review; baseline three hours                                          |

## Users and Personas

| Role                                      | Transcript-established job and pain                                            | Intended outcome                                              | Evidence          |
| ----------------------------------------- | ------------------------------------------------------------------------------ | ------------------------------------------------------------- | ----------------- |
| TPRM analyst                              | Assemble records, verify the generated brief, correct errors before release    | Check rather than rewrite the brief                           | E01, E10, E15     |
| Business owner, represented by Lena Ortiz | Understand renewal impediments; paste brief into ticket; request one for a QBR | Receive a reviewed, usable brief while retaining the decision | E09-E10, E16      |
| Procurement, represented by Marcus Feld   | Avoid late discovery of findings and missed re-sourcing obligations            | See blockers and value-threshold flags early                  | E01, E04          |
| TPRM sponsor, Priya Raman                 | Control review quality and preparation effort                                  | Time reduction and visibility into analyst corrections        | E14-E15, E20      |
| CISO Office delegate, Dana Whitlock       | Establish what evidence the model saw and avoid contact-data leakage           | Auditable evidence and a defined data-handling boundary       | E07, E13-E14, E19 |

Vendor managers own scorecard ratings; Treasury supplies financial flags. These are source-data responsibilities, not newly assigned PRD approval roles. [E05-E06]

## Design Decisions

| ID     | Decision or disposition                                                                                                                               | Evidence   |
| ------ | ----------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- |
| DD-001 | Brief only; no renewal decision or recommendation                                                                                                     | E01, E16   |
| DD-002 | Generate 30 days before the notice window opens; use policy-defined windows. The earlier Tier 1 90-day claim is superseded by the 120-day correction. | E03, E17   |
| DD-003 | Last four scorecards, not only the latest; do not calculate ratings                                                                                   | E05        |
| DD-004 | Incidents cover 12 months, not the full contract term; analyst may retrieve full-term records separately                                              | E07        |
| DD-005 | Scheduled and on-demand briefs share analyst review before business-owner delivery                                                                    | E10        |
| DD-006 | Markdown, not a Word-document output requirement                                                                                                      | E09        |
| DD-007 | CSV for a one-vendor prototype; production export/API/PDF choice remains open                                                                         | E11, E18   |
| DD-008 | Negotiation email and negotiation positions excluded from v1                                                                                          | E15        |

Scope alternatives and proposed cost limits are not decisions. They remain OQ-001 and OQ-003.

## Product Goals

| ID       | Transcript-grounded goal                                                                         | Measure and target                                                                           | Evidence      |
| -------- | ------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------- | ------------- |
| GOAL-001 | Reduce Tier 1 brief preparation effort, including analyst review                                 | Approximate three-hour baseline to under 45 minutes; time records to be supplied by Priya    | E15, E18, E20 |
| GOAL-002 | Give business owners a cited, reviewed view of renewal impediments without making their decision | Every substantive statement cited; analyst review before delivery; no renewal recommendation | E02, E10, E16 |
| GOAL-003 | Preserve evidence for audit and assessment of generated-brief quality                            | Record what the model saw and keep before/after analyst edits; correction target not decided | E13-E14       |

SMART status is deferred. Quantified time and generation targets exist, but baseline verification, measurement protocol, achievability evidence, and release horizon remain unresolved. No deadline or correction-rate target is invented.

## Functional Requirements

These are requirements recorded from explicit meeting decisions, subject to human validation of this draft. Vendor eligibility is unresolved; no requirement authorizes an all-tier production rollout. For FR-001-FR-010 and FR-014-FR-018, the shared trigger is brief preparation or analyst review for a vendor/renewal in the eventual approved scope.

| ID     | Actor                       | Required outcome                                                                                                                                                                                                          | AC     | Goal     | Evidence           |
| ------ | --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------ | -------- | ------------------ |
| FR-001 | Analyst/business owner      | Show vendor identity and tier from the vendor record                                                                                                                                                                      | AC-001 | GOAL-001 | E02, E04           |
| FR-002 | Analyst/business owner      | Show open findings from the findings register                                                                                                                                                                             | AC-002 | GOAL-002 | E04                |
| FR-003 | Analyst/business owner      | Show open exceptions with their expiry dates                                                                                                                                                                              | AC-003 | GOAL-002 | E04                |
| FR-004 | Procurement/business owner  | Show current total contract value and whether renewal crosses $250,000 from an original award below that amount, flagging re-sourcing unless sole-source justification applies                                            | AC-004 | GOAL-002 | E04                |
| FR-005 | Analyst/business owner      | Show the last four scorecards, newest first, with overall rating and dimensions; place any open improvement plan first in the section                                                                                     | AC-005 | GOAL-001 | E05                |
| FR-006 | Analyst/business owner      | Show Treasury's financial flag, last-review date, and watch-list status                                                                                                                                                   | AC-006 | GOAL-002 | E06                |
| FR-007 | Analyst/business owner      | Show incidents from the last 12 months and whether notification deadlines were met                                                                                                                                        | AC-007 | GOAL-002 | E07                |
| FR-008 | Analyst/business owner      | Show required approvers and deadlines with policy citations, including business-owner approval, finding/exception restrictions, tier-dependent exception approvers, Critical CRO approval, and Tier 1 concentration check | AC-008 | GOAL-002 | E08                |
| FR-009 | Analyst/business owner      | Show the policy-cited exit-plan deadline for Tier 1/2 non-renewal: 60 days before expiry                                                                                                                                  | AC-009 | GOAL-002 | E08                |
| FR-010 | Business owner              | Put evidenced renewal blockers at the top of the brief                                                                                                                                                                    | AC-010 | GOAL-002 | E03, E06, E08, E16 |
| FR-011 | TPRM analyst                | Generate a scheduled brief 30 days before the policy-defined notice window opens, tied to the existing reminder trigger                                                                                                   | AC-011 | GOAL-001 | E03, E17           |
| FR-012 | Business owner              | Allow an on-demand brief request without waiting for scheduled generation                                                                                                                                                 | AC-012 | GOAL-001 | E09                |
| FR-013 | TPRM analyst/business owner | Route every generated brief through analyst record checking and correction before business-owner delivery                                                                                                                 | AC-013 | GOAL-002 | E10                |
| FR-014 | Business owner              | Provide the reviewed brief as Markdown suitable for pasting into a ProcureNet case comment                                                                                                                                | AC-014 | GOAL-001 | E09                |
| FR-015 | Analyst/business owner      | Cite every substantive statement to policy or actual source record, with click-through to cited findings; omit claims that cannot be cited                                                                                | AC-015 | GOAL-002 | E02                |
| FR-016 | Analyst/business owner      | Explicitly indicate unavailable or stale source information, including a known last-review date, rather than guessing or leaving a misleading blank                                                                       | AC-016 | GOAL-002 | E16                |
| FR-017 | TPRM sponsor/auditor        | Preserve the generated version and analyst-edited version as correction evidence                                                                                                                                          | AC-017 | GOAL-003 | E14                |
| FR-018 | Business owner              | Identify the reviewing analyst by name at the bottom of the reviewed brief                                                                                                                                                | AC-018 | GOAL-002 | E19                |

Detailed input fields, exact approval mappings, record-link syntax, freshness rules, and review mechanics remain open. The rules above are transcript-reported policy behavior, not independently verified policy interpretations.

## Non-Functional Requirements

### Performance and Capacity

NFR-001: Brief generation shall complete in under 120 seconds, excluding human review. [E12]

Acceptance: Given the eventual approved source configuration and eligible renewal, when generation begins, then the draft is available in less than 120 seconds. Load, percentile, source-fetch boundary, and performance test conditions remain OQ-008; this is a stated target, not demonstrated feasibility.

About 340 renewals annually across all tiers and perhaps 65 for Tier 1/2 are meeting estimates, not capacity requirements. Re-runs and on-demand requests add unquantified demand. Cost is OQ-003. [E10, E12]

### Reliability and Resilience

FR-016 defines the explicitly agreed unavailable/stale-source behavior. Availability, retry, recovery, and delivery-failure targets were not decided; see OQ-012. [E16]

### Security

Access permissions and other security controls for records, briefs, and audit evidence were not specified in the transcript. No security control is approved by this PRD. The access-control and data-protection decision is **Needs validation** pending stakeholder approval; OQ-010 remains open. Analyst review is not a substitute for authorization.

### Privacy

NFR-002: The brief and its source retrieval shall minimize sensitive contact data. Vendor account-manager phone numbers and incident-record contact details shall not be exposed in the brief; reviewer attribution shall use the reviewer's name, not phone number. [E07, E19]

Acceptance: Given a reviewed brief, when its content and footer are inspected, then vendor account-manager phone numbers and incident-record contact details are absent, the reviewer name is present, and a reviewer phone number is absent.

The transcript raises wider exposure risks from vendor-master contact data and ServiceNow on-call contacts, bridge numbers, and escalation chains. NFR-002 captures only the specifically stated exclusions and reviewer-name requirement. The transcript does not approve a broader allowlist, blanket ban on all names, redaction design, access-control rule, or logging policy. Those remain OQ-010; the explicit reviewer-name permission must not be generalized to all personal data. [E07, E19]

### Scalability and Elasticity

No scaling target or concurrency limit was decided. Volume depends on OQ-001 and OQ-008.

### Maintainability and Operability

CSV-column instability and pending API access are recorded risks, not an approved production mechanism. Ownership, freshness monitoring, and operational procedures remain OQ-002, OQ-007, and OQ-012. [E11]

### Observability

NFR-003: Audit evidence shall identify the source records presented to the model for a generated brief, so a later review can determine whether a particular finding was available to it. [E13] Status: **Needs validation** for security, access, and protection requirements; the transcript does not define those controls.

Acceptance: Given a brief and a source finding, when an auditor inspects the associated generation evidence, then the auditor can determine whether that finding was presented to the model. Exact identity/version/snapshot granularity, audit access, storage, and retention are unresolved in OQ-004 and OQ-011.

FR-017 additionally preserves before/after correction evidence. The transcript-reported current prompt/document logging is not proof that the required source-record audit capability exists. [E13-E14]

### Usability and Accessibility

Blocker-first presentation and the under-45-minute end-to-end target are established. Maximum length, accessibility standard, and the measurable boundary between checking and rewriting were not decided; see OQ-009 and OQ-013. Priya's objection to an eight-page brief is not a numerical page-limit requirement. [E07, E15-E16]

### Compatibility and Interoperability

NFR-004: Markdown brief content shall paste into ProcureNet case comments without the table degradation described for Word-document copying. [E09]

Acceptance: Given a reviewed Markdown brief, when pasted into a ProcureNet case comment, then its headings, tables, and citation content remain usable. Exact rendering and link-acceptance tests remain OQ-014.

Source systems are recorded under Dependencies; interoperability mechanisms remain undecided.

### Portability

No deployment or portability target was decided. OQ-012 includes the runtime/delivery environment.

## Constraints

| ID      | Imposed boundary                                           | Source and category                      | Acceptance impact                                                                                |
| ------- | ---------------------------------------------------------- | ---------------------------------------- | ------------------------------------------------------------------------------------------------ |
| CON-001 | Do not decide or recommend renewal                         | Priya; organizational; E01, E16          | Neither generated nor reviewed output says "recommend renew" or substitutes an approval decision |
| CON-002 | Do not compute scorecard ratings; vendor manager owns them | Priya; organizational; E05               | FR-005 uses recorded ratings rather than synthesized ratings                                     |
| CON-003 | Exclude renewal negotiation emails/positions from v1       | Priya, Procurement agreement; scope; E15 | No negotiation drafting capability in this release                                               |
| CON-004 | Do not include full amendment/value history in the brief   | Marcus withdrew the request; scope; E04  | FR-004 shows current TCV and re-sourcing flag, not amendment history                             |

These boundaries cannot be changed by this draft's author. Changing them requires a product decision not present in the transcript.

## Acceptance Criteria

All criteria are Not Started. They specify required behavior, not completed tests. Scope-dependent criteria cannot establish deployment eligibility until OQ-001 is resolved.

* AC-001: Given a vendor record, when a brief is prepared, then it shows the vendor and its recorded tier. Covers FR-001.
* AC-002: Given open findings for the vendor, when a brief is prepared, then those findings are shown with their source-record references. Covers FR-002.
* AC-003: Given open exceptions, when a brief is prepared, then it shows those exceptions and their recorded expiry dates, including dates shortly after renewal. Covers FR-003.
* AC-004: Given an original award below $250,000 and renewal value above $250,000, when a brief is prepared, then current TCV and the crossing flag are shown, with re-sourcing required unless sole-source justification applies. Full amendment history is absent. Covers FR-004 and CON-004. Exact equality and missing-input cases remain OQ-006.
* AC-005: Given at least four scorecards and an open improvement plan, when a brief is prepared, then the section starts with the plan and shows the four latest scorecards newest first, including recorded overall ratings and dimensions without recomputing ratings. Covers FR-005 and CON-002. Fewer-than-four behavior remains OQ-007.
* AC-006: Given current Treasury data, when a brief is prepared, then it shows the recorded Green/Amber/Red flag, last-review date, and watch-list status. Covers FR-006.
* AC-007: Given incident records within the agreed 12-month period, when a brief is prepared, then it shows those incidents and recorded notification-deadline compliance rather than defaulting to full-term history. Covers FR-007. The interval anchor remains OQ-007.
* AC-008: Given applicable cited policy and vendor facts, when a brief is prepared, then it lists required approvers/deadlines, business-owner approval, Critical/High findings without exceptions as approval blockers, Critical exception escalation to CRO, tier-dependent exception approval, and Tier 1 concentration check. Covers FR-008. Unstated mapping details remain OQ-015.
* AC-009: Given a Tier 1/2 non-renewal, when its deadline is presented, then the cited exit-plan deadline is 60 days before expiry. Covers FR-009.
* AC-010: Given an overdue reassessment, a Critical/High finding without an exception, or a Treasury Red flag pending TPRC review, when a brief is prepared, then the evidenced blocker and policy reason appear at the top without a renewal recommendation. Covers FR-010 and CON-001.
* AC-011: Given the transcript-reported policy windows of 120/90/60/30 days for Tiers 1/2/3/4, when the scheduled generation date is derived, then it is respectively 150/120/90/60 days before expiry. A Tier 1 brief is not scheduled 120 or 30 days before expiry. These are timing examples, not approval of all-tier scope. Covers FR-011.
* AC-012: Given an eligible business owner's on-demand request, when submitted outside the scheduled trigger, then a brief enters the same analyst-review path. Instant delivery or a same-day SLA is not asserted. Covers FR-012.
* AC-013: Given a scheduled or on-demand generated brief, when analyst verification/correction has not occurred, then it is not delivered to the business owner as a reviewed brief; after review, the reviewed brief goes to the business owner. Covers FR-013.
* AC-014: Given a reviewed brief, when the business owner receives its content, then Markdown is available for pasting into a ProcureNet case comment. Covers FR-014.
* AC-015: Given a brief statement, when included, then it cites supporting policy or an actual source record; a finding citation supports click-through to the finding. If support cannot be cited, the claim is omitted. Explicit unavailable-source status under FR-016 is not a guessed vendor fact. Covers FR-015.
* AC-016: Given stale Treasury information or unreachable incident records, when a brief is prepared, then the affected information is explicitly identified as unavailable/not current with a known last-review date rather than guessed or left blank as though nothing happened. Covers FR-016.
* AC-017: Given analyst corrections to a generated brief, when review completes, then both before and after content remain available as correction evidence. Covers FR-017. Retention duration awaits OQ-004.
* AC-018: Given a reviewed brief, when its bottom attribution is inspected, then it identifies the reviewing analyst by name, not phone number. Covers FR-018.

## Traceability Matrix

### FR-to-AC Coverage

| Source ID   | Source title      | Target ID   | Coverage   |
| ----------- | ----------------- | ----------- | ---------- |
| FR-001      | Vendor/tier       | AC-001      | 1          |
| FR-002      | Findings          | AC-002      | 1          |
| FR-003      | Exceptions        | AC-003      | 1          |
| FR-004      | Value/re-sourcing | AC-004      | 1          |
| FR-005      | Scorecards        | AC-005      | 1          |
| FR-006      | Financial health  | AC-006      | 1          |
| FR-007      | Incidents         | AC-007      | 1          |
| FR-008      | Approvals         | AC-008      | 1          |
| FR-009      | Exit deadline     | AC-009      | 1          |
| FR-010      | Blockers first    | AC-010      | 1          |
| FR-011      | Scheduled trigger | AC-011      | 1          |
| FR-012      | On demand         | AC-012      | 1          |
| FR-013      | Analyst review    | AC-013      | 1          |
| FR-014      | Markdown          | AC-014      | 1          |
| FR-015      | Citations         | AC-015      | 1          |
| FR-016      | Source gaps       | AC-016      | 1          |
| FR-017      | Corrections       | AC-017      | 1          |
| FR-018      | Reviewer name     | AC-018      | 1          |

Coverage is 18/18 = 100%, above the template's 80% drafting threshold. Coverage measures linked criteria only, not requirement completeness, test execution, or stakeholder approval.

### FR-to-GOAL Alignment

| Source ID   | Target ID   | Coverage   |
| ----------- | ----------- | ---------- |
| FR-001      | GOAL-001    | 1          |
| FR-002      | GOAL-002    | 1          |
| FR-003      | GOAL-002    | 1          |
| FR-004      | GOAL-002    | 1          |
| FR-005      | GOAL-001    | 1          |
| FR-006      | GOAL-002    | 1          |
| FR-007      | GOAL-002    | 1          |
| FR-008      | GOAL-002    | 1          |
| FR-009      | GOAL-002    | 1          |
| FR-010      | GOAL-002    | 1          |
| FR-011      | GOAL-001    | 1          |
| FR-012      | GOAL-001    | 1          |
| FR-013      | GOAL-002    | 1          |
| FR-014      | GOAL-001    | 1          |
| FR-015      | GOAL-002    | 1          |
| FR-016      | GOAL-002    | 1          |
| FR-017      | GOAL-003    | 1          |
| FR-018      | GOAL-002    | 1          |

Alignment is 18/18 = 100%, meeting the template's 100% drafting target. No BRD or feasibility handoff was supplied; no feasibility disposition register applies.

## MVP and Release Framing

The agreed capability comprises FR-001-FR-018 and CON-001-CON-004, but its vendor population is not agreed. Priya proposed Tier 1/2; Marcus proposed every vendor; Lena proposed contracts with total value over $250,000, explicitly distinguishing total contract value from annual spend. Priya deferred resolution to an offline discussion. None of these positions is adopted here. [E10]

The assigned prototype uses one vendor from the CSV. Production source integration remains undecided among export, API, and contract-PDF indexing. A prototype choice is not the MVP's production architecture. [E11, E18]

Lena volunteered a Tier 1 card processor with expiry at the end of May, tentatively. Tom estimated a late-December brief trigger and late-January notice window; Priya called it a good but tight target. The vendor, precise expiry, year, pilot consent, and release commitment remain unconfirmed. [E18]

Negotiation drafting is a later idea, not a v1 requirement. All-tier expansion is not a confirmed later release either; it is an unresolved initial-scope alternative.

## Success Metrics

| Goal     | Measurement                                     | Baseline                                                              | Target                                                                    | Window/source and unresolved details                                                             |
| -------- | ----------------------------------------------- | --------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| GOAL-001 | Tier 1 assembly effort including analyst review | About 180 minutes                                                     | Under 45 minutes                                                          | Renewal-case time records; Priya to retrieve baseline; sample, aggregation, and target date open |
| GOAL-001 | Generation duration excluding analyst review    | No brief-generation baseline                                          | Under 120 seconds                                                         | Generation measurement boundary, load, and percentile open in OQ-008                             |
| GOAL-002 | Statement citation and review compliance        | Existing policy citation contract is contextual, not a brief baseline | Every substantive statement supported; review before delivery             | AC-013/AC-015; test population and review evidence mechanics open                                |
| GOAL-003 | Analyst correction evidence and frequency       | Not supplied                                                          | Before/after versions retained; no correction-frequency threshold decided | Priya wants to know how often analysts correct output; coding and calculation open in OQ-009     |

The time targets imply a reduction greater than 75% from the approximate baseline; this arithmetic is not an additional success target. Priya will supply 10-15 past renewal reviews for testing, but the transcript does not establish a test split, passing score, evaluation cadence, or approval rubric. [E15, E18, E20]

Telemetry acceptance intent is limited to NFR-003 and FR-017: determine what records the model saw and preserve corrections. No telemetry SDK, exporter, instrument names, span schema, sampling policy, or new data-retention policy is selected. OQ-011 records that gap rather than turning authoring guidance into product evidence.

## Operational Readiness

Production readiness is not established. Required evidence includes the decided source-access path, finalized logging requirements, Records reconciliation, and confirmed pilot details. The exact operational acceptance gate is not assigned by the meeting.

Audit acceptance must allow investigation of whether a finding was presented to the model, and correction evidence must preserve before/after brief content. How that evidence remains available over the renewal-record lifecycle, with personal-data safeguards, is unresolved. [E13-E14, E19]

Human review is mandatory on both request paths. Assignment, review completion evidence, delivery mechanism, review turnaround, and handling of re-runs are open. Same-day review was requested by Lena and tentatively acknowledged by Priya as "Probably"; it is not a committed SLA. [E10]

## Dependencies and Meeting Actions

### Data dependencies

| Data                                     | Transcript-reported location            | Unresolved boundary                                     |
| ---------------------------------------- | --------------------------------------- | ------------------------------------------------------- |
| Vendor identity/tier, contract dates/TCV | ProcureNet; Coupa nightly CSV available | Production path and original-award/renewal-value fields |
| Findings/exceptions                      | ProcureNet TPRM module                  | Access, expiry semantics, record links                  |
| Scorecards                               | ProcureNet                              | Access, incomplete history, dimensions                  |
| Financial flag/review date/watch list    | Treasury quarterly emailed spreadsheet  | Access, schema, freshness                               |
| Incidents/notification compliance        | ServiceNow third-party incident table   | Access, time anchor, safe fields                        |
| Approvals/windows/deadlines              | Policy documents                        | Applicable sections, full mappings, conflicts           |

These locations come from E04-E08 and E11. The CSV column list described in the meeting includes contract ID, vendor, dates, TCV, tier, and vendor manager; it is not evidence that all other brief inputs are included.

### Assigned actions

| Owner         | Action                                                                                   | Meeting-stated timing             | Status                             |
| ------------- | ---------------------------------------------------------------------------------------- | --------------------------------- | ---------------------------------- |
| Tom Okafor    | Write export/API/contract-indexing options and a one-vendor CSV prototype                | Not specified                     | Assigned; completion not evidenced |
| Marcus Feld   | Add Tom to export distribution and send column list                                      | "Today" at the 2026-09-22 meeting | Assigned; completion not evidenced |
| Dana Whitlock | Send audit logging requirements to Tom                                                   | "By Friday" at the meeting        | Assigned; completion not evidenced |
| Priya Raman   | Pull Tier 1 time baseline and 10-15 past renewal reviews                                 | Not specified                     | Assigned; completion not evidenced |
| Lena Ortiz    | Confirm card processor expiry and willingness to pilot                                   | Not specified                     | Assigned; completion not evidenced |
| Priya Raman   | Arrange scope discussion with Lena and Marcus                                            | Not specified                     | Assigned; completion not evidenced |
| Unassigned    | Ask Records how seven-year renewal records and 13-month summarized evidence fit together | Before building, per Dana         | Explicitly unowned                 |

Action assignment is not approval authority. Dates are meeting-relative, not newly promised deadlines. [E18-E19]

## Risks and Assumptions

### Key Assumptions

No unsupported product assumptions are adopted. The following tentative statements remain evidence-qualified, not decisions.

| ID      | Tentative statement                                                           | Evidence status                            | Impact if false                        | Recorded follow-up                    |
| ------- | ----------------------------------------------------------------------------- | ------------------------------------------ | -------------------------------------- | ------------------------------------- |
| ASM-001 | Tier 1 baseline is about three hours                                          | Approximate; case time logs not supplied   | Reduction baseline changes             | Priya to pull baseline; E15, E18, E20 |
| ASM-002 | Renewal volumes are about 340 all-tier and 65 Tier 1/2                        | Meeting estimates                          | Review workload/cost differs           | No validation owner assigned; E10     |
| ASM-003 | Card processor expiry is end of May                                           | Lena said "I think"; year/date unconfirmed | Pilot trigger changes                  | Lena to confirm; E18                  |
| ASM-004 | Existing vendor-master tab might share the prior problematic export's lineage | Explicitly unknown                         | Contact-data exposure boundary unclear | OQ-010; E19                           |

### Risk Register

Probability and severity were not rated in the transcript and are left unassessed.

| ID       | Evidence-grounded risk                                                  | Consequence                                              | Meeting follow-up or open question                         |
| -------- | ----------------------------------------------------------------------- | -------------------------------------------------------- | ---------------------------------------------------------- |
| RISK-001 | Vendor scope is disputed                                                | Review volume and release eligibility undefined          | Priya's scope conversation; OQ-001                         |
| RISK-002 | API access delayed; CSV columns change; PDFs may be old scans           | Data availability and production design uncertain        | Tom's options write-up; OQ-002                             |
| RISK-003 | Brief retained seven years but summarized model evidence only 13 months | Later renewal investigation may lack supporting evidence | Unowned Records question; OQ-004                           |
| RISK-004 | Contact data previously leaked through an automated export              | Brief/log data could expose inappropriate source fields  | Dana logging write-up; field handling unresolved in OQ-010 |
| RISK-005 | Missing/stale sources can look like no risk                             | Business owner could misunderstand evidence gaps         | Explicit missing-source behavior; FR-016                   |
| RISK-006 | Analysts rewrite output instead of checking it                          | Time/quality goal fails                                  | Preserve edits; FR-017; threshold OQ-009                   |
| RISK-007 | Pilot runway is tight if data access is not sorted                      | Tentative late-December trigger may not be achievable    | Lena confirmation and source-access actions; OQ-005        |

## Open Questions

All entries are Open. Where the transcript does not assign a decision owner, the owner is Unassigned. No option below is a recommendation.

| ID     | Unresolved question                                                                                                                                                                      | Evidence/gap                                                                             | Owner explicitly assigned in meeting                                         |
| ------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| OQ-001 | Which vendors are eligible: all vendors, Tier 1/2, or total contract value over $250,000? Does eligibility differ for on-demand briefs?                                                  | Three competing cuts deferred; E10                                                       | Priya to arrange discussion with Lena/Marcus; final authority unspecified    |
| OQ-002 | Which production data path is approved: export, API, contract indexing, or another decision emerging from the options review? Who makes that architecture decision?                      | Options left open; dependencies on other teams; E11                                      | Tom writes options; decision owner unassigned                                |
| OQ-003 | What is the cost ceiling per brief, and what costs/re-runs count toward it?                                                                                                              | $1 and $0.50 discussed; settle after prototype; E12                                      | Unassigned                                                                   |
| OQ-004 | How are seven-year briefs/review records reconciled with 30-day raw personal-data logs and 13-month summarized logs? What retention applies to source evidence and edits?                | Records consultation requested; E13, E19                                                 | Explicitly unassigned                                                        |
| OQ-005 | What is the pilot vendor and exact expiry date/year, and is pilot participation confirmed? What is the committed release horizon?                                                        | Tentative end-of-May expiry and late-December trigger; E18                               | Lena confirms expiry and consent; release owner unassigned                   |
| OQ-006 | Where do original-award value, proposed renewal value, and sole-source justification come from? What happens at exactly $250,000 or when inputs are missing?                             | Crossing rule agreed; export fields insufficiently specified; E04, E11                   | Unassigned                                                                   |
| OQ-007 | What makes a source current? Which date anchors the 12-month incident interval? What should happen with fewer than four scorecards, conflicting records, or an unknown last-review date? | Source-gap principle agreed, definitions absent; E05-E07, E16                            | Unassigned                                                                   |
| OQ-008 | Under what load and percentile is under-two-minute generation measured, and do fetch/queue/retry time count? What concurrency/capacity is required?                                      | Target stated; feasibility depends on source design; E10, E12                            | Unassigned                                                                   |
| OQ-009 | How are analyst effort, correction frequency, and "checking versus rewriting" measured? What sample/aggregation and quality threshold determine success?                                 | Time baseline and edits requested; protocol absent; E14-E15, E18, E20                    | Priya supplies baseline/reviews; measurement decisions unassigned            |
| OQ-010 | Which source fields may enter briefs, prompts, and audit evidence; which require removal/redaction; what access-control and data-protection rules apply, and who approves them? Does vendor-master extraction share the prior leak's data path? | Contact-data concerns and explicit reviewer name/not-phone; E07, E19; security controls not decided | Dana supplies logging requirements; stakeholder decision and approval owner unassigned |
| OQ-011 | What source identity/version/snapshot and prompt evidence must be retained to prove what the model saw? What telemetry schema, storage, access, and protection controls are required?     | Audit intent agreed; detailed logging write-up pending; security and access decision unresolved; E13-E14 | Dana supplies logging requirements to Tom                                    |
| OQ-012 | Who assigns analysts and operates scheduled generation? How are completion, delivery, failures, retries, duplicate requests, and re-runs handled; where is the capability deployed?      | Common review path decided, operational mechanisms absent; E03, E10-E11                  | Unassigned                                                                   |
| OQ-013 | What is the review/delivery SLA for scheduled and on-demand briefs? What length/readability/accessibility requirements apply?                                                            | Same-day tentative, not committed; no numeric length or accessibility standard; E07, E10 | Unassigned                                                                   |
| OQ-014 | What is source-record citation syntax and link behavior, including spreadsheets, CSVs, and PDFs? Which Markdown rendering/paste checks are required?                                     | New record citations and paste requirement; E02, E09, E11                                | Unassigned                                                                   |
| OQ-015 | Which exact policy sections, tier-dependent exception approvers, concentration-check conditions, and deadline/exception validity rules apply? How are policy/data conflicts handled?     | Policy lookup intended; complete mapping absent; E08, E17                                | Unassigned                                                                   |
| OQ-016 | What review/sign-off roles and approval gate authorize this PRD and the pilot? What resources/budget are committed?                                                                      | Sponsor and actions named, formal approvals/resources not decided                        | Unassigned                                                                   |

## Glossary

| Term          | Meaning in this draft                                                                                                |
| ------------- | -------------------------------------------------------------------------------------------------------------------- |
| TPRM          | Third-party risk management                                                                                          |
| TCV           | Total contract value; distinct from annual spend                                                                     |
| Notice window | Policy-defined interval before contract expiry; generation occurs another 30 days earlier                            |
| ProcureNet    | Procurement system described in the transcript as Coupa underneath                                                   |
| QBR           | Business-owner review occasion for which Lena requested an on-demand brief                                           |
| CRO           | Approval role named for Critical exceptions; full policy authority remains OQ-015                                    |
| TPRC          | Review body named for Treasury Red stops; full policy authority remains OQ-015                                       |
| Source record | Actual vendor, finding, exception, scorecard, financial, incident, or contract evidence underlying a brief statement |

## Sign-Off

### Approval Checklist

* Sponsor is Priya Raman; no PRD approval is recorded.
* Product owner, technical sign-off authority, quality lead, and required compliance approvers are not assigned.
* Lena's pilot offer is tentative, not product sign-off.
* Approval date is not established.
* Open decisions have not been waived.

### Waivers

None recorded. Template coverage defaults are authoring checks, not meeting-approved launch gates.

### Handoff Readiness

Status remains Draft. The latest Validate-phase PRD Quality Reviewer report
(`PRD-001-quality-20261007T143641Z`) returned `FAIL`: Validate exit is
`BLOCKED` by the unresolved security decision and core ISO quality-threshold
findings, with additional cautions recorded in the lab log. The
transcript-backed contact-data exclusions are captured in NFR-002; broader
privacy handling and retention remain open. Finalize was not entered because
its prerequisite gate did not pass. The 18 functional
requirements have 100% recorded acceptance-criteria and goal linkage, but
that coverage does not establish quality, test execution, implementation
readiness, or stakeholder approval. Open scope, architecture, data-handling,
measurement, and ownership decisions remain unresolved. No backlog planning
or tracker mutation was requested.

## Disclaimer

> [!CAUTION]
> **Disclaimer:** This agent is an assistive tool only. It does not provide product management approval, technical feasibility validation, or business sign-off and does not replace product managers, engineering leads, business stakeholders, or other qualified human reviewers. The output consists of suggested requirements, acceptance criteria, and product specifications to support a user's own product planning and decision-making. All Product Requirements Documents, functional requirements, non-functional requirements, and constraint definitions generated by this tool must be independently reviewed and validated by appropriate product and engineering reviewers before adoption. Outputs from this tool do not constitute product approval, requirements sign-off, or engineering commitment.

## Document Metadata

* Draft authored on 2026-10-07 from the 2026-09-22 kickoff transcript.
* Canonical structure: requirements-author PRD template, version 1.0.0, Microsoft HVE-Core.
* Template attribution: Microsoft HVE-Core Team; template licensed CC BY 4.0. No license is asserted over the meeting evidence.
* Process diagrams and research/feasibility disposition registers are omitted because no diagram decision or relevant handoff/research input was supplied.
* Frontmatter title replaces a duplicate level-one heading to follow documentation formatting conventions.
