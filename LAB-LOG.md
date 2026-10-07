---
description: Timestamped notes from the vendor renewal risk brief kickoff transcript
---

# Day 03 Lab Log

## Exercise 1: Transcript notes

Source: `docs/meetings/renewal-kickoff-transcript.md`. Timestamps below are
elapsed times in the recording.

### Agreed decisions

* The brief must not make the renewal decision. It presents risks and blockers;
  the business owner decides whether to renew (00:00:57, 00:33:03).
* Every statement must cite a policy document or source record. If it cannot
  be cited, omit it. Source-record citations must let readers reach the record
  (00:01:38, 00:02:01, 00:02:27).
* Generate the scheduled brief 30 days before the renewal notice window opens,
  not 30 days before contract expiry (00:03:47, 00:03:50, 00:03:57).
* Include vendor tier; open findings and exception expiry dates; current total
  contract value and a re-sourcing flag; the four most recent scorecards,
  newest first, plus any open improvement plan; Treasury's status, last-review
  date, and watch-list status; incidents from the prior 12 months and whether
  notification deadlines were met; required approvals and deadlines; and the
  exit-plan deadline (00:04:14, 00:04:21, 00:04:35, 00:05:08, 00:05:15,
  00:05:29, 00:05:47, 00:06:38, 00:06:59).
* Do not compute vendor performance ratings; the vendor manager owns them
  (00:05:15).
* A Treasury Red status means no extension until TPRC review. A Critical or
  High finding without an exception means the renewal cannot be approved.
  The business owner always approves; exception approvers depend on tier,
  Critical exceptions go to the CRO, and Tier 1 requires the TPRM Office's
  concentration check (00:05:29, 00:06:38).
* Include incidents from the previous 12 months in the brief. Analysts may
  pull the full contract term separately (00:05:47, 00:05:56).
* The brief is Markdown so it can be pasted into a ProcureNet renewal ticket
  (00:10:00, 00:10:20, 00:10:30).
* Both scheduled and on-demand briefs go through analyst verification before
  reaching the business owner. On-demand requests need not be instant; same
  day was considered acceptable, though not firmly committed (00:12:46,
  00:13:20, 00:13:27, 00:13:37, 00:13:41, 00:13:47).
* If a source is unavailable or stale, say so and give the last-known review
  date when available. Never guess or leave a blank that could imply there is
  nothing to report (00:32:20, 00:32:32, 00:32:43).
* Put blockers at the top. Do not say "recommend renew" (00:32:57, 00:33:03,
  00:33:16).
* Measure success against a Tier 1 assembly baseline of about three hours and
  a target below 45 minutes, including analyst review (00:29:05, 00:29:46,
  00:29:55, 00:44:39, 00:44:51).
* Record the analyst's edits so the team can measure corrections and retain
  evaluation evidence. Identify the reviewer by name, not phone number
  (00:24:14, 00:24:20, 00:24:53, 00:25:12, 00:42:04, 00:42:11, 00:42:17).
* A prototype may use the nightly Coupa CSV. The production data-source
  decision remains open (00:15:50, 00:39:53).

### Four deferred decisions

1. **Vendor scope:** Marcus proposed every renewal (about 340 yearly); Priya
   proposed Tier 1 and Tier 2 (about 65 yearly); Lena proposed contracts over
   $250,000 total value. Priya will arrange a separate discussion with Marcus
   and Lena. The scope was not decided (00:02:31, 00:03:02, 00:03:09,
   00:11:17, 00:11:28, 00:12:09, 00:12:27, 00:40:36).
2. **Production data sources:** Options are the Coupa export, a Coupa API that
   is not yet accessible, or indexing contract PDFs. Tom will document the
   options and trade-offs; no production approach was selected (00:15:50,
   00:16:19, 00:16:54, 00:17:47, 00:18:09, 00:39:53).
3. **Cost per brief:** Tom wants to try for $0.50; Marcus wants that ceiling;
   Tom has not validated feasibility, and Priya deferred settling the target
   until after a prototype (00:21:12, 00:21:36, 00:22:01, 00:22:09).
4. **Retention and audit-record reconciliation:** The proposed log retention
   is 30 days raw and 13 months summarized, while renewal reviews are kept for
   seven years. Records must advise how these periods fit together. No owner
   was assigned (00:23:03, 00:23:21, 00:23:56, 00:41:23, 00:41:30,
   00:41:46, 00:41:52).

The on-demand same-day turnaround is also provisional: the analyst-review
workflow was agreed, but Priya's "probably" did not establish a firm service
level (00:13:37, 00:13:41, 00:13:47).

### Contradictions and corrected number

* **Tier 1 notice window:** Marcus initially recalled 90 days (00:03:18).
  Priya later checked the procedure and corrected it to 120 days for Tier 1,
  90 for Tier 2, 60 for Tier 3, and 30 for Tier 4 (00:36:12, 00:36:43).
  Therefore a Tier 1 brief is due 150 days before expiry: 30 days before its
  120-day notice window opens (00:36:43, 00:36:55). Treat the corrected
  procedure values as authoritative.
* **Scope metric:** Lena's proposed $250,000 threshold is total contract value;
  Priya answered with an annual-spend tier threshold. These are different
  measures, and the disagreement was left open (00:11:28, 00:11:56, 00:12:02,
  00:12:27).
* **Incident lookback:** The procedure covers incidents during the contract
  term, which can span three years. The brief will show 12 months, with a
  full-term lookup left to the analyst. This difference was consciously
  accepted for brief length, not resolved by changing the procedure
  (00:05:47, 00:05:52, 00:05:56, 00:06:03).
* **Retention periods:** The seven-year renewal record and the 13-month
  summarized model log period do not align. Their treatment remains unresolved
  pending Records guidance (00:23:21, 00:23:56, 00:41:30).

### Withdrawn request

Lena suggested drafting negotiation emails from scorecards and SLA breaches.
Priya explicitly excluded vendor negotiation drafting from v1; it may be
revisited later with Procurement and Legal (00:26:28, 00:27:04, 00:27:27,
00:27:31, 00:27:37).

### Implied requirements

* Preserve source provenance and enough record-level evidence to reproduce
  what the brief relied on; this follows from click-through citations and
  Dana's need to establish what the model saw (00:02:01, 00:22:20, 00:22:52).
* Distinguish missing, unavailable, and stale data from a clear/empty result;
  do not infer safety from absent data (00:32:20, 00:32:32, 00:32:43).
* Present decision blockers before informational details, while leaving the
  actual renewal decision with the business owner (00:32:57, 00:33:03,
  00:33:16, 00:33:22).
* Minimize sensitive data retrieved or emitted. In particular, do not expose
  vendor account-manager phone numbers or incident-record contact details;
  the reviewer name is sufficient (00:06:03, 00:42:04, 00:42:17, 00:42:21,
  00:43:14).
* Keep human review in the generation path, including for on-demand requests,
  and retain before/after edits for quality measurement and evaluation
  evidence (00:12:46, 00:13:27, 00:24:14, 00:24:20, 00:24:53).
* Derive the generation date from the applicable notice window rather than
  hard-coding one lead time for every tier (00:36:12, 00:37:01).
* Keep the brief usable as a ticket comment and concise enough to surface key
  risks without reproducing a full-term incident history (00:05:56, 00:06:03,
  00:10:00, 00:10:20, 00:33:16).

## PRD trap checks

* Vendor scope remains undecided in OQ-001. The PRD records the all-renewal,
  Tier 1/2, and over-$250,000 total-contract-value proposals without selecting
  one or conflating total contract value with annual spend.
* The transcript's later correction (E17, 00:36:12-00:36:43) sets the notice
  windows to 120/90/60/30 days for Tiers 1/2/3/4. Thirty days before those
  windows open is 150/120/90/60 days before expiry. Section 2 of
  `corpus/contract-renewal-procedure.md` independently confirms the window
  values. That policy check corroborates E17 only; transcript timestamps remain
  the source for the capability trigger.
* The withdrawn negotiation-email request is not a v1 functional requirement.
  The PRD records its exclusion in DD-008 and CON-003.
* The implied source-provenance requirement is captured through FR-015,
  NFR-003, and AC-015/AC-017, grounded in transcript evidence E02 and E13-E14
  (00:02:01, 00:22:20-00:22:52, 00:24:14-00:24:53).
* The implied requirement to distinguish unavailable or stale information
  from a clear result is captured in FR-016 and AC-016, grounded in E16
  (00:32:20-00:32:43).

## PRD validation

The PRD Quality Reviewer completed its Validate-phase review on
2026-10-07T14:24:47Z. Its report is
`PRD-001-quality-20261007T142447Z` for PRD-001 version 0.1.0 and reports
`FAIL`; `validate_exit` is `BLOCKED` and `finalize_exit` is `NOT_EVALUATED`.
Findings: 2 RISK, 15 CAUTION, 14 COVERED, and 0 NOT_APPLICABLE. The FR-to-AC
and FR-to-goal coverage is 100% (18/18 each), but coverage does not override
the quality blockers.

The two HIGH RISK findings are:

* `requirements-quality-013`: no specified security requirements for access
  control or protection of source records, briefs, and audit evidence.
* `requirements-quality-014`: personal-data handling and retention boundaries
  remain unresolved, including the conflict between renewal-record and
  summarized-log retention.

The report also identifies open completeness, feasibility, SMART-goal,
operational, privacy, and usability concerns. These gaps cannot be resolved
from the allowed capability evidence without inventing policy or product
decisions. Vendor scope and other undecided matters remain open. Finalize was
not entered because Validate exit is blocked; the PRD remains a draft, with
no approval or gate completion claimed.

### Validation rerun

After the first review, NFR-002 was revised to capture the transcript-backed
exclusion of vendor account-manager phone numbers and incident-record contact
details. The PRD marks the missing access-control and data-protection decision
as **Needs validation** and asks for stakeholder approval in OQ-010/OQ-011.
No control was inferred from the existing system or added without evidence.

The reviewer reran Validate at 2026-10-07T14:36:41Z. Report
`PRD-001-quality-20261007T143641Z` returned **FAIL**:
`validate_exit: BLOCKED`, `finalize_exit: NOT_EVALUATED`, with 1 RISK,
16 CAUTION, 15 COVERED, and 0 NOT_APPLICABLE findings. The remaining HIGH
RISK is `requirements-quality-013`: no approved security, access-control,
or data-protection requirement exists for sensitive source records, briefs,
and audit evidence. The transcript does not decide those controls, and no
authorized access-control decision or approval owner is available. The
reviewer also scored the core `unambiguous` and `singular` attributes below
their minimum threshold; related scope and operating questions remain open.

The transcript-backed privacy update is now covered by the reviewer, while
broader data handling and retention remain a CAUTION. The approved source
boundary prevents resolving the security blocker in this exercise. Keep
OQ-010/OQ-011 open, mark the affected requirement Needs validation, and do not
enter Finalize or claim approval.