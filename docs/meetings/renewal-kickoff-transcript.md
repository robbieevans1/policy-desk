# Meeting Transcript — Vendor Renewal Risk Brief: Kickoff

**Meeting:** policy-desk — Vendor Renewal Risk Brief (kickoff)
**Date:** 2026-09-22
**Time:** 10:00 – 10:47 (Eastern)
**Duration:** 46 min 51 s
**Location:** Teams meeting (Conference Room 4B joined as a room device)
**Organizer:** Priya Raman

**Attendees:**

- Priya Raman — Third-Party Risk Lead, TPRM Office (sponsor)
- Marcus Feld — Procurement Manager (in Conference Room 4B)
- Dana Whitlock — CISO Office delegate (in Conference Room 4B)
- Tom Okafor — Software Engineer, policy-desk team
- Lena Ortiz — Head of Payments Operations, business owner (joined late)
- Jordan Lee — TPRM Office intern (notes)

> Transcript auto-generated; speaker attribution may contain errors.

---

[00:00:04] Priya Raman (TPRM Lead): Okay, I think we're recording. Can everyone hear me?

[00:00:08] Marcus Feld (Procurement): We're here in 4B. Dana's with me.

[00:00:11] Priya Raman (TPRM Lead): Great. Lena's coming out of the payments ops stand-up, so she'll be a few minutes late. Jordan, you're on notes?

[00:00:18] Jordan Lee (Intern): Yes, I've got the doc open.

[00:00:21] Priya Raman (TPRM Lead): Thanks. So, context. policy-desk has been good for the "what does the policy say" questions. What we're here for is the next thing, the renewal risk brief. Every time a contract comes up for renewal, my analysts spend a ridiculous amount of time assembling the same picture. What tier, what findings are open, how's the scorecard, is Treasury worried, were there incidents. Then it goes to the business owner, who mostly wants to know "is anything stopping me renewing."

[00:00:52] Marcus Feld (Procurement): And then it comes to us, and we find out three weeks before expiry there's an open High finding.

[00:00:57] Priya Raman (TPRM Lead): Which is the other problem, yes. So policy-desk produces the brief. It doesn't make the decision. It produces the brief.

[00:01:06] Tom Okafor (policy-desk): Can I share my screen? I mocked up something rough so we're not talking in the abstract.

[00:01:12] Priya Raman (TPRM Lead): Go for it.

[00:01:24] Tom Okafor (policy-desk): Can you see my screen? Markdown file, grey background.

[00:01:28] Marcus Feld (Procurement): The room display's still on the lobby — Dana, can you —

[00:01:33] Dana Whitlock (CISO Office): It's the input button. There.

[00:01:36] Marcus Feld (Procurement): Okay, we see it.

[00:01:38] Tom Okafor (policy-desk): It's made up, not wired to anything. Vendor and tier at the top, then findings, performance, financial health, incidents, required approvals. Every line has a bracket saying where it came from, like "supports payments processing, a critical business service, TIER-MTX section 2."

[00:02:01] Priya Raman (TPRM Lead): And that bracket is non-negotiable for me. Every statement in the brief points at either a policy document or the actual source record. If it says there's an open finding, I want to click through to the finding. If it says the renewal needs CRO sign-off, it cites the section. If it can't cite it, it doesn't say it.

[00:02:22] Tom Okafor (policy-desk): The policy citations we already do. Citing source records is new.

[00:02:27] Dana Whitlock (CISO Office): Agree with Priya, though. Cite it or drop it.

[00:02:31] Marcus Feld (Procurement): Can I raise scope now? I think it should be every vendor, every renewal. The Tier 3s and 4s are where things slip, because nobody's looking.

[00:02:41] Priya Raman (TPRM Lead): I want to start with Tier 1 and Tier 2. That's where the procedure requires the full review with scorecards and financials. A Tier 4 brief would be three lines.

[00:02:51] Marcus Feld (Procurement): Three lines nobody's currently writing.

[00:02:54] Priya Raman (TPRM Lead): Fair. Let's come back to it when Lena's here.

[00:02:58] Tom Okafor (policy-desk): How many renewals a year are we talking?

[00:03:02] Marcus Feld (Procurement): All tiers, about three hundred forty. Tier 1 and 2 together, maybe sixty-five.

[00:03:09] Priya Raman (TPRM Lead): Timing first. When does it get generated?

[00:03:14] Marcus Feld (Procurement): Thirty days before expiry?

[00:03:16] Priya Raman (TPRM Lead): Way too late.

[00:03:18] Marcus Feld (Procurement): No, sorry — the notice window for Tier 1 is ninety days, so the renewal case opens ninety days out. I meant somewhere inside that.

[00:03:29] Priya Raman (TPRM Lead): If it lands inside the window the analyst is already scrambling. The brief should be ready when the case opens. And if there's an overdue reassessment, that blocks renewal, so you need runway.

[00:03:42] Dana Whitlock (CISO Office): Same for a security finding that needs remediation. That's not a two-week job.

[00:03:47] Tom Okafor (policy-desk): So generate it the day the window opens?

[00:03:50] Marcus Feld (Procurement): ProcureNet already sends a reminder thirty days before each window opens. It's in the procedure. Tie it to that.

[00:03:57] Priya Raman (TPRM Lead): I like that. Thirty days before the notice window opens. Same trigger as the reminder.

[00:04:03] Tom Okafor (policy-desk): Before the window, not before expiry. Writing that down, because someone will build it wrong.

[00:04:09] Priya Raman (TPRM Lead): Jordan, bold that one.

[00:04:11] Jordan Lee (Intern): Got it.

[00:04:14] Tom Okafor (policy-desk): Let me go through contents and where each piece lives. Tier's in the vendor master. Open findings?

[00:04:21] Priya Raman (TPRM Lead): Findings register, the TPRM module in ProcureNet. And open exceptions with their expiry dates. If an exception expires two weeks after the renewal date, the business owner needs to know they're renewing into a breach.

[00:04:35] Marcus Feld (Procurement): Can we also get the full contract value history, every amendment back to original award? Actually — scratch that. Nobody reads it. Just current total contract value, and whether the renewal takes it over two-fifty. If the original award was under two hundred fifty thousand and the renewal pushes it over, it has to be re-sourced unless there's a sole-source justification. People miss that constantly.

[00:05:02] Tom Okafor (policy-desk): Current TCV plus a re-sourcing flag. No history.

[00:05:06] Tom Okafor (policy-desk): Performance?

[00:05:08] Priya Raman (TPRM Lead): The last scorecard. Overall rating and the dimensions.

[00:05:12] Dana Whitlock (CISO Office): The renewal procedure says the last four, doesn't it?

[00:05:15] Priya Raman (TPRM Lead): It does. Okay, last four, most recent first, and any open improvement plan at the top of that section. And don't compute the rating, the vendor manager owns it.

[00:05:26] Tom Okafor (policy-desk): Happy not to. Financial health?

[00:05:29] Priya Raman (TPRM Lead): Treasury's Green, Amber, Red flag, date of last review, and whether they're on the watch list. Red is a stop — no extension until the TPRC has reviewed.

[00:05:40] Tom Okafor (policy-desk): Is that in ProcureNet?

[00:05:42] Marcus Feld (Procurement): It's a spreadsheet Treasury emails quarterly.

[00:05:45] Tom Okafor (policy-desk): Of course it is.

[00:05:47] Priya Raman (TPRM Lead): Incidents. Last twelve months, and whether they hit their notification deadlines.

[00:05:52] Dana Whitlock (CISO Office): The procedure says incidents during the term. Some terms are three years.

[00:05:56] Priya Raman (TPRM Lead): For the brief, twelve months. The analyst can pull the full term if needed. I don't want an eight-page brief.

[00:06:03] Dana Whitlock (CISO Office): Fine. Those come from our third-party incident records, which is a ServiceNow table with a lot in it you don't want. On-call contacts, bridge numbers, escalation chains. Last year someone automated an export off the vendor master for a reconciliation report, it landed in a Teams channel with two hundred people in it, and it had every vendor account manager's mobile number. I spent two weeks on that. I still get emails about it.

[00:06:31] Priya Raman (TPRM Lead): I remember.

[00:06:33] Dana Whitlock (CISO Office): Anyway.

[00:06:35] Tom Okafor (policy-desk): Noted.

[00:06:38] Priya Raman (TPRM Lead): Then required approvals and deadlines per policy. Who signs off and by when. The business owner always approves. A Critical or High finding without an exception means it can't be approved at all. Exception approvers depend on tier, Critical goes to the CRO, and Tier 1 needs my office's concentration check.

[00:06:59] Marcus Feld (Procurement): And the exit plan deadline. Sixty days before expiry for Tier 1 and 2 if they don't renew. Nobody remembers that one.

[00:07:07] Tom Okafor (policy-desk): Is that a lookup or is the model reasoning about it?

[00:07:10] Priya Raman (TPRM Lead): Mostly lookup. Every deadline with its citation.

[00:08:58] *Lena Ortiz joined the meeting.*

[00:09:04] Lena Ortiz (Head of Payments Ops): Hi, sorry. Stand-up ran over. Can you hear me?

[00:09:10] Priya Raman (TPRM Lead): We can. Quick catch-up: brief generated thirty days before the notice window opens, every line cited, covering tier, findings and exceptions, scorecards, financial flag, twelve months of incidents, approvals and deadlines.

[00:09:41] Lena Ortiz (Head of Payments Ops): That's basically what I get from your team now, just in a different format every time.

[00:09:53] Priya Raman (TPRM Lead): So what format do you want?

[00:10:00] Lena Ortiz (Head of Payments Ops): Something I can paste straight into the renewal ticket. Right now I get a Word doc, I copy bits into the ProcureNet case, the table turns into soup.

[00:10:20] Tom Okafor (policy-desk): Case comments take markdown. If the brief's markdown, it pastes clean.

[00:10:30] Lena Ortiz (Head of Payments Ops): Then markdown. And I want to be able to ask for one whenever. If I'm going into a QBR, I should be able to ask policy-desk for the brief, not wait for the system.

[00:10:53] Tom Okafor (policy-desk): On demand from the business owner. Okay.

[00:10:59] Lena Ortiz (Head of Payments Ops): And it comes to me directly?

[00:11:05] Priya Raman (TPRM Lead): Mm. We'll get to the flow.

[00:11:11] Marcus Feld (Procurement): While Lena's here — scope.

[00:11:17] Priya Raman (TPRM Lead): Lena, Marcus wants every vendor. I want Tier 1 and 2 to start.

[00:11:28] Lena Ortiz (Head of Payments Ops): I'd cut it differently. I think about money, not tiers. Anything over two hundred fifty thousand, I want a brief. I've got a three-year deal at four hundred total that's Tier 3, and nobody looks at it.

[00:11:56] Priya Raman (TPRM Lead): Over two-fifty a year is Tier 2 on spend alone.

[00:12:02] Lena Ortiz (Head of Payments Ops): Annual, sure. I mean contract value.

[00:12:09] Marcus Feld (Procurement): Which is my point. Do every vendor and you never have this argument.

[00:12:17] Priya Raman (TPRM Lead): And my team reviews three hundred forty briefs a year.

[00:12:23] Marcus Feld (Procurement): Reviews?

[00:12:27] Priya Raman (TPRM Lead): I'm coming to that. We won't solve scope here. Let's take that offline — I'll find time with you both.

[00:12:41] Lena Ortiz (Head of Payments Ops): Sure.

[00:12:46] Priya Raman (TPRM Lead): The flow. The brief gets generated, it goes to one of my analysts, they check it against the records, fix what's wrong, then it goes to the business owner. I'm not having an AI telling Lena to renew without one of my analysts looking at it first.

[00:13:20] Lena Ortiz (Head of Payments Ops): Honestly, I'd rather that.

[00:13:27] Tom Okafor (policy-desk): The on-demand ones too?

[00:13:31] Priya Raman (TPRM Lead): I don't want two processes.

[00:13:37] Tom Okafor (policy-desk): Then on-demand isn't instant.

[00:13:41] Lena Ortiz (Head of Payments Ops): Same day is fine. Not a week.

[00:13:47] Priya Raman (TPRM Lead): Same day. Probably.

[00:15:15] Tom Okafor (policy-desk): The hard part is data. Apart from the policy citations, everything lives somewhere else. Tier, findings, exceptions, scorecards in ProcureNet. Financials in a spreadsheet. Incidents in ServiceNow. And the contract — dates, value —

[00:15:50] Marcus Feld (Procurement): ProcureNet. It's Coupa underneath, and there's a Coupa export, nightly CSV. Contract ID, vendor, dates, TCV, tier, vendor manager. Finance already uses it. I can get you on the distribution.

[00:16:19] Tom Okafor (policy-desk): Fine for a prototype, but I don't want production depending on a CSV someone can change the columns of. There's an API, but we don't have access yet. My request's been with the integration team since August.

[00:16:45] Marcus Feld (Procurement): That API's been "coming" for two years.

[00:16:54] Dana Whitlock (CISO Office): Or we index the contract PDFs. They're all in the repository. Then you get the actual clauses — notice periods, auto-renewal — not what someone typed into a field.

[00:17:20] Tom Okafor (policy-desk): That's a different problem. Then it's reading contracts, and the citation is a page in a PDF.

[00:17:33] Dana Whitlock (CISO Office): Which is a better citation than a CSV row.

[00:17:39] Marcus Feld (Procurement): Until the PDF is a 2019 scan nobody can read.

[00:17:47] Priya Raman (TPRM Lead): We can't pick this today. We need an architecture decision on that. Tom?

[00:17:57] Tom Okafor (policy-desk): I can lay out the options. I shouldn't be the one picking, two of the three depend on other teams.

[00:18:09] Priya Raman (TPRM Lead): Fair. Leave it open.

[00:20:39] Tom Okafor (policy-desk): Non-functionals. A policy question takes eight to twelve seconds today. A brief pulls from five or six sources. What's acceptable?

[00:20:58] Lena Ortiz (Head of Payments Ops): I don't want to sit there ten minutes.

[00:21:04] Priya Raman (TPRM Lead): Under two minutes for generation. Review is separate.

[00:21:12] Tom Okafor (policy-desk): Doable if the data's local. If we're hitting APIs live I'd want to measure first. And cost — I'd want each brief under, like, a dollar. Long prompts, lots of context.

[00:21:36] Marcus Feld (Procurement): A dollar? I was going to say fifty cents.

[00:21:43] Tom Okafor (policy-desk): Three hundred forty briefs at a dollar is three hundred forty dollars a year.

[00:21:51] Marcus Feld (Procurement): It's real money when Finance asks why it's a dollar and not fifty cents. Plus re-runs.

[00:22:01] Tom Okafor (policy-desk): I'll try for fifty. I won't promise it before I see the data.

[00:22:09] Priya Raman (TPRM Lead): We'll settle the number once there's a prototype.

[00:22:20] Dana Whitlock (CISO Office): Logging. If this reads the findings register and incident records, I need to know exactly what it saw. If someone renews and six months later says "the brief didn't mention the finding," I need to show whether the finding was in front of the model.

[00:22:52] Tom Okafor (policy-desk): We log retrieved documents and the prompt today. We'd extend that to source records.

[00:23:03] Dana Whitlock (CISO Office): And how long do you keep the prompt?

[00:23:09] Tom Okafor (policy-desk): Thirty days raw, then summarized. There's a section in the retention schedule on AI assistant logs.

[00:23:21] Dana Whitlock (CISO Office): Thirty days raw if there's personal data, thirteen months summarized. But a renewal review is a seven-year record. So the brief lives seven years and what the model saw lives thirteen months. Somebody should ask the Records office before we build it, not after.

[00:23:56] Priya Raman (TPRM Lead): Good point. Note that.

[00:24:02] Jordan Lee (Intern): Who should I put for it?

[00:24:06] Priya Raman (TPRM Lead): We'll sort owners at the end.

[00:24:14] Tom Okafor (policy-desk): Do we keep the analyst's edits? Before and after?

[00:24:20] Priya Raman (TPRM Lead): Yes. I want to know how often my people correct it. That's how I'll know if it's any good.

[00:24:33] Dana Whitlock (CISO Office): And that's evidence for — [inaudible] — the model risk people are going to [inaudible] anyway, so —

[00:24:47] Priya Raman (TPRM Lead): Dana, you cut out. The room mic, I think.

[00:24:53] Marcus Feld (Procurement): Model risk will want evaluation evidence for anything that supports a decision, and they'll ask at the first review. The analyst edits are that evidence.

[00:25:12] Dana Whitlock (CISO Office): Sorry, that was me, not Marcus — the room's putting everything on his mic. But yes, that's what I said.

[00:25:24] Jordan Lee (Intern): I'll put it under Dana.

[00:26:28] Lena Ortiz (Head of Payments Ops): Slightly off topic. If the brief knows the scorecards and SLA breaches, could it also draft the renewal negotiation email? "Three SLA breaches this year, we want service credits and a price hold." That's what I actually spend my time on.

[00:27:00] Tom Okafor (policy-desk): Technically it's a short step.

[00:27:04] Priya Raman (TPRM Lead): Not for v1. Out of scope. The brief is about risk. Once it's drafting negotiation positions it's talking to the vendor, and that's a conversation with Procurement and Legal.

[00:27:27] Marcus Feld (Procurement): Very much so.

[00:27:31] Lena Ortiz (Head of Payments Ops): Fair. Putting it on the list for later.

[00:27:37] Priya Raman (TPRM Lead): Jordan, under "later," not requirements.

[00:29:05] Priya Raman (TPRM Lead): Let me say what success looks like. Today a Tier 1 renewal takes an analyst about three hours to assemble. Pulling findings, chasing Treasury, reading incident records, working out approvals. The target is under forty-five minutes for a Tier 1, including the analyst's review.

[00:29:46] Tom Okafor (policy-desk): Including review. So the analyst should be checking, not rewriting.

[00:29:55] Priya Raman (TPRM Lead): If they're rewriting it, it's failed.

[00:30:01] Tom Okafor (policy-desk): Is the three hours tracked?

[00:30:05] Priya Raman (TPRM Lead): Roughly. They log time against renewal cases. I can pull it.

[00:32:20] Dana Whitlock (CISO Office): What happens when a source is down? Treasury's spreadsheet is stale, ServiceNow's unreachable.

[00:32:32] Tom Okafor (policy-desk): The brief says so. "No current rating available, last review dated whatever."

[00:32:43] Priya Raman (TPRM Lead): Never guess. A blank is worse than "not available," because a blank reads as "nothing to report."

[00:32:57] Lena Ortiz (Head of Payments Ops): Does it tell me "recommend renew"?

[00:33:03] Priya Raman (TPRM Lead): No. It tells you what's in the way and cites why. The decision is yours.

[00:33:16] Lena Ortiz (Head of Payments Ops): Then blockers at the top. Not page three.

[00:33:22] Tom Okafor (policy-desk): Easy.

[00:36:12] Priya Raman (TPRM Lead): Marcus, before you go — I checked the procedure. Tier 1 is a hundred and twenty days, not ninety. Ninety is Tier 2, sixty Tier 3, thirty Tier 4.

[00:36:36] Marcus Feld (Procurement): Is it? I always think ninety.

[00:36:43] Priya Raman (TPRM Lead): A hundred and twenty. So for a Tier 1 the brief's generated a hundred and fifty days before expiry.

[00:36:55] Marcus Feld (Procurement): Huh. That's actually better for us.

[00:37:01] Tom Okafor (policy-desk): Which is why the trigger reads the window from the policy instead of hard-coding numbers.

[00:39:08] Lena Ortiz (Head of Payments Ops): Can I volunteer a pilot? Tier 1 card processor, expiry end of May, I think.

[00:39:22] Tom Okafor (policy-desk): A hundred twenty before end of May is end of January, thirty before that is end of December. Tight if data access isn't sorted.

[00:39:41] Priya Raman (TPRM Lead): Tight, but a good target.

[00:39:47] Marcus Feld (Procurement): I have to drop in a minute.

[00:39:53] Priya Raman (TPRM Lead): Actions, then. Tom, write up the data-source options — export, API, indexing the contracts — and a prototype brief for one vendor off the CSV.

[00:40:12] Tom Okafor (policy-desk): Yes.

[00:40:14] Priya Raman (TPRM Lead): Marcus, get Tom on the export distribution and send the column list.

[00:40:22] Marcus Feld (Procurement): Today.

[00:40:26] Priya Raman (TPRM Lead): Dana, your logging requirements for audit, to Tom.

[00:40:32] Dana Whitlock (CISO Office): By Friday.

[00:40:36] Priya Raman (TPRM Lead): I'll pull the Tier 1 time baseline and ten to fifteen past renewal reviews for testing. Lena, confirm the card processor's expiry and that you're happy to pilot it.

[00:40:59] Lena Ortiz (Head of Payments Ops): Will do.

[00:41:03] Priya Raman (TPRM Lead): And I'll set up the scope conversation with Lena and Marcus.

[00:41:11] Marcus Feld (Procurement): Thanks all, dropping.

[00:41:15] *Marcus Feld left the meeting.*

[00:41:23] Jordan Lee (Intern): The Records question — who's that?

[00:41:30] Priya Raman (TPRM Lead): Someone needs to ask Records how the seven years and the thirteen months fit together.

[00:41:40] Dana Whitlock (CISO Office): Not me. I've got the logging write-up.

[00:41:46] Tom Okafor (policy-desk): It's more a TPRM question than engineering.

[00:41:52] Priya Raman (TPRM Lead): Just put it down as open. We'll find someone.

[00:41:58] Jordan Lee (Intern): Okay. No owner.

[00:42:04] Lena Ortiz (Head of Payments Ops): Will the brief say who reviewed it?

[00:42:11] Tom Okafor (policy-desk): Reviewer's name at the bottom, sure.

[00:42:17] Dana Whitlock (CISO Office): Name. Not phone number.

[00:42:21] Tom Okafor (policy-desk): Name.

[00:42:27] Priya Raman (TPRM Lead): Okay. Thanks, all, really useful. I'll tidy up the notes and send them round this afternoon, and we'll pick up from there.

[00:42:43] Lena Ortiz (Head of Payments Ops): Thanks Priya.

[00:42:45] *Lena Ortiz left the meeting.*

[00:42:54] Dana Whitlock (CISO Office): One more before I go. The vendor master tab you'd pull the business owner from — is that the same one last year's export came off?

[00:43:10] Tom Okafor (policy-desk): No idea. Possibly.

[00:43:14] Dana Whitlock (CISO Office): Hm. Okay.

[00:43:18] *Dana Whitlock left the meeting.*

[00:44:39] Priya Raman (TPRM Lead): — sorry, it's still recording. Jordan, in the notes, put the target as forty-five minutes for a Tier 1 including review. Not "faster." The number. Baseline three hours.

[00:44:51] Jordan Lee (Intern): Forty-five minutes, including review. Okay.

[00:46:51] *Recording stopped.*
