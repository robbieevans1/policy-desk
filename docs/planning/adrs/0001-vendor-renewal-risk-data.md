---
id: '0001'
title: Vendor Renewal Risk Brief Data Acquisition
status: proposed
proposed_date: '2026-10-07'
deciders:
  - Robert - lab participant and exercise ADR decider
consulted:
  - Engineering
  - TPRM
  - Procurement
  - CISO Office
  - Business owner
informed: []
tags:
  - vendor-renewal
  - data-acquisition
supersedes: null
superseded-by: null
related: []
asr_triggers:
  - kind: security
    evidence: PRD NFR-002 and OQ-010; kickoff transcript 00:06:03-00:06:35 and 00:15:15-00:18:09
    note: Source acquisition must minimize exposure of vendor and incident contact fields.
  - kind: performance
    evidence: PRD NFR-001; kickoff transcript 00:20:39-00:22:09
    note: The production source path must support draft generation in under 120 seconds.
  - kind: maintainability
    evidence: PRD OQ-002; kickoff transcript 00:16:19-00:16:45
    note: CSV schema instability and delayed API access materially affect integration maintenance.
effort: M
affected_components:
  - policy-desk Container App and brief-generation path
  - Coupa nightly export distribution
  - ProcureNet findings and scorecard access dependencies
success_criteria:
  - metric: CSV ingest schema validation
    target: Incompatible or missing required columns are detected and surfaced; no malformed feed is silently accepted.
    measurement_window: Each export ingestion
    source: Implemented ingestion checks and run evidence
  - metric: Missing or stale source disclosure
    target: A brief identifies unavailable or stale CSV data rather than guessing or presenting a misleading blank.
    measurement_window: Each generated brief
    source: Analyst-reviewed brief and source freshness metadata
  - metric: Source traceability
    target: Contract/vendor claims from the CSV identify the source export and record reference; findings and scorecards cite their own records when those separate dependencies are available.
    measurement_window: Each generated brief
    source: Generated brief and captured model-input/source evidence
  - metric: Generation duration
    target: Draft generation completes in less than 120 seconds under the eventually defined acceptance conditions.
    measurement_window: Defined performance test and pilot measurement
    source: Generation timing telemetry
---

# Vendor Renewal Risk Brief Data Acquisition

## Context

The vendor renewal risk brief needs contract/vendor data as well as findings, exceptions, and scorecards. The kickoff identified a nightly Coupa export as immediately available, Coupa API access as delayed, and contract PDFs as a possible but potentially unreliable source. The selected CSV path therefore covers only the fields demonstrated in the meeting; it is not evidence that the export contains ProcureNet findings or scorecards. This ADR records a lab exercise decision, not organizational production authorization.

> Kickoff transcript, 00:15:15-00:16:19: ProcureNet is reported as the home of tier, findings, exceptions, and scorecards; the nightly Coupa export is described with contract ID, vendor, dates, TCV, tier, and vendor manager.
> Kickoff transcript, 00:16:19-00:16:45: engineering objects to production dependence on a CSV with changeable columns; API access has not been granted and is described as long delayed.
> Kickoff transcript, 00:16:54-00:17:39: contract PDFs could support clause and page citations, but some are old scans that may be unreadable.
> PRD, Data dependencies and OQ-002: the production path is open; the listed CSV fields do not establish findings, scorecard, or source-link coverage.
> PRD NFR-001, NFR-002, OQ-010, and OQ-014: generation has a less-than-two-minute target, contact data must be excluded, source-field boundaries remain open, and record citation/link behavior needs definition.
> README and infra/main.bicep: the current application performs policy retrieval over a local vector index; Bicep declares Foundry, model deployments, Container Apps, Log Analytics, and audit blob storage, but declares no Coupa or ProcureNet integration.

The roles in `consulted` identify relevant consultation perspectives from the kickoff. They are not evidence that these stakeholders reviewed or approved this ADR. The lab decider is authorized to make this exercise decision only; production approval remains outside this ADR's authority.

## Decision Drivers

* Obtain usable contract/vendor data without waiting for the delayed API access request.
* Keep the source path maintainable and detect schema changes rather than silently misreading data.
* Preserve evidence traceability and explicitly disclose stale or unavailable values.
* Exclude sensitive contact fields from brief inputs and output.
* Support the PRD's less-than-120-second generation target without claiming that target is already met.
* Keep findings and scorecards accurately represented as separate dependencies.

## Considered Options

1. **Nightly Coupa CSV.** The export is available now and supports the lab prototype. It requires schema validation and freshness handling. Its described columns do not prove that findings, exceptions, scorecards, or record links are present.
2. **Coupa API.** A structured integration may avoid reliance on a manually distributed, changing-column export and may allow fresher reads. Access is not available; its data coverage, versioning, limits, latency, availability, and citation affordances have not been verified.
3. **Contract-PDF indexing.** Contract pages could ground clause-level statements and may surface terms not captured in typed fields. Some PDFs may be unreadable scans; extraction reliability is uncertain, and contract documents do not provide current ProcureNet findings or scorecards.

## Decision Outcome

Chosen option: **Nightly Coupa CSV for the lab exercise**, because it provides available data access without waiting for the delayed API, while local ingestion can be evaluated against the generation-time target. This is a proposed exercise decision only; it does not authorize production adoption. Revisit the choice when Coupa API access becomes available.

The deciding driver is **available data access without waiting for the delayed API**. The under-two-minute generation target is a criterion to verify, not a measured result or guarantee.

| Driver | Nightly Coupa CSV | Coupa API | Contract-PDF indexing |
|---|---|---|---|
| Available access now | Best evidenced: nightly export was offered for the prototype | Fails now: access not granted and delayed | Repository copies reported available; completeness/access not verified |
| Schema and freshness | Schema-change risk; nightly freshness may lag | Potentially structured/fresher, but contract and service behavior are unverified | Document versions and extraction quality require handling |
| Contract evidence | Typed fields in described export; clauses not established | Depends on fields exposed by an unverified API | Page-level contract evidence possible when readable |
| Findings and scorecards | Not evidenced in the listed CSV fields | Not evidenced as covered by Coupa API; separate ProcureNet access may be needed | Not supplied by contract documents |
| Generation-time fit | Local ingestion is selected for evaluation; target not yet verified | Unknown until access and interface are available | OCR/indexing and retrieval cost against target are unknown |

### Consequences

* Good, because the lab can exercise an immediately available export path while the API request remains blocked.
* Good, because ingestion can validate the expected schema and fail visibly instead of silently accepting a changed layout.
* Good, because source freshness, record identity, and traceability can be made explicit and evaluated before delivery.
* Bad, because a nightly snapshot can be stale relative to Coupa and requires a freshness rule and visible stale-data behavior.
* Bad, because export column changes can interrupt ingestion and require schema-change monitoring and maintenance.
* Bad, because the export's described fields do not establish coverage of current findings or scorecards; those require separate approved ProcureNet access and must not be implied by this decision.
* Neutral, because contract clause text and page-level PDF citations are not obtained through this selected CSV path.

## Risks and Mitigations

| Risk | Mitigation / required follow-up |
|---|---|
| Export schema changes or malformed files | Validate required columns and types at ingestion; reject incompatible input visibly and notify the operator rather than silently mapping it. Exact schema/version and failure operations remain implementation work. |
| Snapshot is stale or missing | Capture export time and source freshness metadata; label stale/unavailable data explicitly and do not guess. Freshness thresholds remain to be defined. |
| CSV claims cannot be traced to source rows | Preserve export identity and row/record reference in generated evidence; define citation syntax and link behavior before claiming click-through support. |
| Contact fields leak into model input or brief | Use an explicit field allowlist and exclude vendor account-manager phone numbers and incident contact details. Broader field boundary and access controls remain open. |
| Findings and scorecards appear covered when they are not | Treat ProcureNet findings and scorecards as separate access dependencies; omit unsupported claims and disclose unavailable sources. The Coupa export must not be represented as supplying those records. |
| Generation exceeds the PRD target | Measure end-to-end generation under defined conditions; this ADR does not assert that local ingestion meets the target. |

## Rollback / Exit Strategy

If the export is missing, stale beyond the subsequently approved threshold, or fails schema validation, stop use of that feed for the affected brief and surface the data gap for analyst review. Do not fall back silently to unapproved PDF extraction or assume API access. The analyst must obtain or verify information through approved source procedures before delivery. Revisit or replace this decision when Coupa API access becomes available or evidence shows that CSV quality, security, or performance is unacceptable; document a changed architectural choice in a superseding ADR rather than silently changing this record.

## Affected Components

### Existing resources and system behavior

The current Bicep file provisions a Container App with system-assigned identity, a Foundry account/project and chat/embedding deployments, Log Analytics, and an audit blob store. The README describes policy Q&A using a local vector index and citation verification. Neither source declares the Coupa CSV ingestion, a ProcureNet connection, or a findings/scorecard interface.

### Proposed additions and separate dependencies (not present in Bicep)

The lab decision proposes evaluating local ingestion of the nightly Coupa CSV in the policy-desk brief-generation path. No new resource, endpoint, credential, storage location, or production network path is approved by this ADR. Separate approved access to ProcureNet findings and scorecards remains required and must be designed and represented independently. Any resulting deployment change must distinguish proposed integrations from existing Bicep resources.

## Deployment View

```text
EXISTING BICEP RESOURCES
+-------------------------------------------------------------------+
| Azure resource group                                              |
|                                                                   |
| +----------------------+       +--------------------------------+ |
| | Container Apps env   |------>| policy-desk Container App      | |
| +----------+-----------+       +----+-----------------+---------+ |
|            |                        |                 |           |
|            v                        |                 v           |
| +----------------------+            |          +--------------+   |
| | Log Analytics        |            |          | Audit blob   |   |
| +----------------------+            |          | storage      |   |
|                                     |          +--------------+   |
|                                     v                             |
| +----------------------------------------------------------------+|
| | Foundry account                                                ||
| | +--------------------+     +---------------------------------+ ||
| | | policy-desk project|---->| Chat and embedding deployments  | ||
| | +--------------------+     +---------------------------------+ ||
| +----------------------------------------------------------------+|
|                                                                   |
| App system identity role assignments:                             |
| * Cognitive Services OpenAI User scoped to Foundry                |
| * Storage Blob Data Contributor scoped to audit storage            |
+-------------------------------------------------------------------+

PROPOSED / NOT DECLARED IN BICEP
+---------------------+       +-----------------------------------+
| Coupa nightly CSV   |------>| Proposed local CSV ingestion in   |
| export              |       | policy-desk brief-generation path |
+---------------------+       +----------------+------------------+
                                               |
                                               v
                                      +------------------+
                                      | Brief uses       |
                                      | contract/vendor  |
                                      | export fields    |
                                      +------------------+

SEPARATE ACCESS DEPENDENCIES; NOT DECLARED IN BICEP
+-----------------------+       +--------------------------------+
| ProcureNet findings   |- - -> | Separate approved data access  |
+-----------------------+       +----------------+---------------+
                                                 |
+-----------------------+                        v
| ProcureNet scorecards |- - ->          Brief, when available
+-----------------------+
```

### Legend

* `---->` depicts a connection or flow declared in the current Bicep for existing resources, or the selected proposed CSV flow in the separate proposed section.
* `- - >` depicts a separate, unresolved access dependency; it is not a configured integration.
* The two labeled sections distinguish resources already declared in `infra/main.bicep` from proposed or unimplemented data access.

### Key Relationships

* The existing Container App uses the Foundry project/models and is assigned audit-blob write access in Bicep; it also emits platform logs to Log Analytics through its environment.
* The Coupa CSV path is a proposed data flow for the lab decision and is not yet declared or provisioned in Bicep.
* Findings and scorecards remain distinct ProcureNet dependencies; this decision does not connect them or assert coverage.

## More Information

Sources: [kickoff transcript](../../meetings/renewal-kickoff-transcript.md), especially 00:15:15-00:18:09; [vendor renewal risk brief PRD](../../project-planning/vendor-renewal-risk-brief.md), especially Data dependencies, NFR-001, NFR-002, OQ-002, OQ-010, and OQ-014; [README](../../../README.md); [current Bicep deployment](../../../infra/main.bicep).

Review this proposed decision when Coupa API access becomes available, when export schema/freshness evidence changes, or when separate ProcureNet access and validated deployment design are ready. The repo remains classified as unknown; this ADR makes no public/private visibility claim. No backlog handoff or organizational production approval is included.
