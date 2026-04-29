# Speaker Notes — Quit chatting with your agents (v18)

## What changed v17 → v18 (2026-04-29 mid-morning, autonomy loop now LIVE on cron)

While the deck was at v17, the autonomy implementation push completed:
- 6 of 6 shadow flags wired (was 2 of 6) via commit `de4e620`
- All `# SHADOW_ANCHOR:` comments inserted with policy-side validator
- Three originally-flagged open concerns all closed (lesson_plan inconclusive guard `93f111b`, heartbeat-before-preflight reorder `8a435bd`, verify-round prior-reply injection `6856e5e`)
- 5 Windows scheduled tasks live: DiscordBoardWatcher (5 min), CodexMailboxDrain (15 min), ShadowRegression (hourly), ShadowStatus (daily 09:55), ShadowPromote-DryRun (daily 10:00)
- `promote.py` and `regression_check.py` shipped as sidecar Phases 3 + 4
- Trident validation caught 3 real gaps (Wilson LB event-scoped → meeting-scoped, promote.py guards missing, watcher quotas absent), closed in `3f7cdd5` before cron went live
- Empirical proof in meeting `9c76e39b` — telemetry actually flows through `boardroom_floor_events`

**Two new substance items in v18:**

**Slide 2 (Shift) — added 41% AI-generated code stat.** Stack Overflow Developer Survey + GitHub Octoverse 2026. Strengthens the industry-pivot framing alongside Poolside Laguna. *"The shift is measurable."*

**NEW slide 12 — "The Loop is Running"** (between Self-Audit and EU AI Act). The talk's strongest claim — the autonomy loop runs hands-off, on cron, RIGHT NOW. Three cards mapping schtasks to Telemetry / Score / Propose stages. Quote-block highlights Trident validation catching 3 gaps as another self-audit instance. Closing line: *"This is Karpathy's autoresearch made operational: wiki + meta-harness + Trident consensus + Brutal harness, all writing to one Postgres audit log. The architecture researches itself."*

**Slide 14 (Take It Home) — kicker extended.** From *"visible right now on a workstation in this city"* → *"running on cron right now, gated by my signature."* Plus new closing line: *"Karpathy's autoresearch, operational. Build yours."*

**Net change:** 13 → 14 slides. Total content ~24 min (~6 min Q&A buffer in 30-min slot).

**Slide 12 speaker notes:**

> "And one more thing. While I was talking, this whole architecture has been running on cron. Five Windows scheduled tasks went live this morning. The board watcher fires every five minutes. The mailbox drain every fifteen. Status runs daily nine fifty-five with Wilson lower bound on the shadow events. Promote runs daily ten — but in dry-run for the calibration week. Empirical signal first, live flips after.
>
> The slide quotes Trident validation. Three gaps the design doc missed — Wilson LB was event-scoped, gameable; promote.py was missing safety guards; the board watcher had no quotas. Multi-model self-audit, ran independent of the implementation CLI, caught all three. They're closed in commit 3f7cdd5, before cron went live.
>
> What you're watching is Karpathy's autoresearch made operational. The wiki indexes what we've learned. The meta-harness scores it. Trident audits it. The Brutal harness red-teams it. All four write to one Postgres audit log.
>
> The architecture researches itself."

**Cue:** point at the three cards as you name the stages. Land hard on "running on cron right now."

**Cut criteria:** if running >2 min over by end of slide 11, cut this slide — but the substance is unique to v18 and the audience is paying attention to it. Keep if at all possible.

---

# Speaker Notes — Quit chatting with your agents (v17)

## What changed v16 → v17 (2026-04-29 morning)

Andrew flagged the federation preflight receipt image on the standalone Bet Paid Off slide as too dense. Asked for architecture diagrams instead, with brain consults.

**Removed:** Slide 8 (Bet Paid Off + Receipt). The federation preflight image dominated the slide visually without earning the space. Bet payoff verbal cue moved to Federation slide opener: *"Eighteen seconds. While I was naming the moves, the agent finished — the path is on the Discord channel. The bet paid off."* Side monitor still projects the live preflight throughout the talk.

**Added: NEW slide 9 "How it talks"** — boardroom + mailbox + wiki diagram. Three floor cards (Anismin/Meridian/Kimi with their ports), bus arrow showing `POST /v2/boardroom/meetings/{id}/speak` + `X-Agent-Token`, three storage cards (`boardroom_meetings`, `agent_mailbox`, `/workspace` Karpathy wiki). Closing line: *"Federation is not a vendor — it's a protocol on top of an audit log."* Sourced from /anismin consult 2026-04-29.

**Refined: Slide 11 (Self-Audit)** — replaced the dense card-grid with Meridian's 5-box flow diagram: **Work → Measure → Score → Propose → Human**. New caption from Meridian: *"Agents don't self-govern. They self-instrument."* Sourced from /meridian consult 2026-04-29 (despite her main.jsonl at 1913KB she still replied through the WARN gate).

**Added to slide 10 (Pipelines):** Meridian's dark factory framing — *"one brief becomes a queue of narrow PR-sized jobs, not one giant autonomous guess."* (KCS itself was silent during /kimiclaw consult — Floor 3 container unresponsive — so Meridian's observation pattern stands in.)

**Brain consult provenance:**
- /anismin (Floor 1, FastAPI :18889): replied 2 min, gave boardroom protocol primitives + 4-box meta-harness loop + her R1/R2/R3 role pattern.
- /meridian (Floor 2, openclaw gateway codex-5.4): replied through context-overflow WARN at 1913KB, gave the 4-box loop framing in her own words + dark factory one-liner + two captions ("Agents don't self-govern, they self-instrument" / "Plan, execute, verify, with different brains disagreeing on purpose").
- /kimiclaw (Floor 3, KCS swarm :9643 docker exec): silent. Container unresponsive at consult time. Meridian's observation covers the dark factory framing.

**Total deck: 13 slides** (was 13 in v16, net zero — removed 1 + added 1). Demo arc still slides 5-7 + verbal payoff on slide 8. Architecture-substance arc now slides 8-11 (Federation → How it talks → Pipelines → Self-Audit).

**Spine sentence unchanged:** *"hand them a contract, verify the receipt, watch the architecture audit itself."*

---

# Speaker Notes — Quit chatting with your agents (v16)

**Talk:** Quit chatting with your agents and get them to work for you
**Event:** OpenClaw × neob.ai · Agentic Economy Night · Fiskaly Wien
**Date:** Wednesday 29 April 2026
**Slot:** Keynote, second speaker. Ed Prinz opens with OpenClaw introduction + AI agents in business context. Andrew follows. Optional 10-min third closer.
**Length:** ~23 min content + ~7 min Q&A buffer in a 30-min slot. Adjustable per Ed's signal.

---

## The talk in one sentence

***Stop chatting with your agents — hand them a contract, verify the receipt, watch the architecture audit itself.***

That's the spine. Every slide serves it. The deeper claim (extends the spine):

***You're not watching agents that work. You're watching architecture that audits itself, specialises by task, ships its own fixes — visible right now on a workstation in this city.***

Demo arc (load-bearing): slides 5 → 6 → 7 → 8. Office → Commission → Six Moves → Receipt. The bet is the live commission. The receipt is the artifact. Don't cut these.

Architecture reveal (v16 substance): slides 10 → 11. The Pipelines (on disk, three of them) → The Self-Audit (recursive critique, manual gates). These are the depth the surface read missed.

---

## Pre-talk checklist (T-30 min)

- [ ] Discord client logged in. **Voice + text channels both visible on the projector.**
- [ ] Tailscale connected to Vienna workstation. Ping Meridian (`/meridian status`).
- [ ] AnisminOS dashboard reachable at `localhost:8643` — slide 5's screenshot is the live UI; if you can show it on a second projector tab, do it.
- [ ] Slides loaded. `F` for fullscreen. `T` starts the 30-min timer.
- [ ] **T-10 min: send silent priming text to Meridian in Discord**: *"Tonight: Fiskaly Wien talk. When I commission you live, the brief will ask for memory log + 3 lessons. Save to `memory/2026-04-29-fiskaly.md`. Do not pre-write."*
- [ ] **T-5 min: GPU load check.** If VRAM > 31 GB, voice may go offline. Plan for text-only fallback.
- [ ] **Backup demo video** queued on lectern laptop in second tab — pre-recorded 30s clip of the same commission running cleanly. If voice fails on stage, switch tab and play it.
- [ ] AV tech briefing: *"At slide 6 I'll speak into my phone for ~10 seconds. About 6 seconds later, a generated image lands in Discord. About 18 seconds later, the lessons file path appears as text in the same channel. Discord text channel needs to be visible the whole time. I'll also need a side monitor showing two URLs — `:9643/office/preflight` and `:8643/boardroom2/preflight` — both auto-refresh every 5 seconds, both should grade GREEN throughout."*
- [ ] Water on lectern.

### 5-min check-in with Ed (T-30, derisks Q&A traps)

Three quick questions:
1. Did you cite the **88% NVIDIA revenue stat** in your section? (affects slide 3 spoken setup — bridge or callback)
2. Did you cover **runtime-vs-library** distinction (LangGraph/CrewAI vs OpenClaw)? (affects framework-wars Q&A trap)
3. Did you cite the **7,851% YoY Web4 traffic** stat? (affects Web4 Q&A trap)

If Ed framed it differently than expected, swap the relevant phrases on stage. Don't quote specifics from his deck unless you saw his slides.

### Side-monitor projection

KCS shipped `federation_preflight` as a stage-projectable terminal-aesthetic webpage. AnisminOS mirrors it. Same data, two signatures.

- **Side-monitor 1 (KCS-side, primary)**: `http://localhost:9643/office/preflight` — full data, signature line `✓ Federation is keynote-ready.`
- **Side-monitor 2 (AnisminOS-side, mirror)**: `http://localhost:8643/boardroom2/preflight` — same checks, attesting from Floor 1.
- Both auto-refresh every 5s. Black background, green CRT scanlines.
- If only one available, project the KCS one (more complete). AnisminOS in browser tab on lectern.
- If a check goes YELLOW or RED on stage, that's not failure — it's the workbench reporting honestly. *"There it is. The system just told you something. That's the point."*

### One-liner runbook to verify federation pre-show

```bash
docker exec kimiclaw-web python /app/scripts/federation_preflight.py --json
```

Should grade GREEN 6/6. If RED on any item, act on it before walking on.

---

## Slide 1 — Title (~60 sec)

> "Thanks Ed. You just gave the room the platform and the case — what OpenClaw is, what agents can actually do in business. I'm going one floor down. Into the operational layer. Tonight: the workbench. And the architecture that audits itself.
>
> Title's on the slide. *Quit chatting with your agents and get them to work for you.* The line that runs through the talk: a brief is a contract. A chat is a hostage situation.
>
> Tonight I'm going to bet a real piece of work on that line. Live. In front of you."

**Cue:** acknowledge Ed warmly but briefly. Don't restate his content — *receive* it. Use Ed's framing back to him. Don't quote specific numbers unless you saw Ed's slides.

**Alternative (only if room's energy is high after Ed and you want a deflationary handshake):** *"Ed just showed you what the agents can do. I'm going to show you the paperwork."* Use sparingly — the workbench framing is more visual.

---

## Slide 2 — The Shift (~30 sec)

> "Before I make the bet — one piece of context. October 2025, Poolside shipped Laguna. Not a chatbot. A model family purpose-built for coding agents. Forty-seven percent on SWE-bench Pro. Forty-one percent on Terminal-Bench 2.0. Cursor's Composer, Cognition's Devin, OpenAI's Codex CLI all pointing the same direction. The frontier labs aren't building bigger chatbots anymore. They're building purpose-built coding and agent systems.
>
> The slide quotes Poolside: *'Software is a much more expressive interface. An agent that can write and execute code can compose actions, parallelize work, and build its own ad-hoc systems.'*
>
> So 'stop chatting' isn't a hot take. It's where the field already is. Tonight: what that looks like on a workbench."

**Cue:** read fast. Don't dwell on numbers. The point is the *direction*, not the leaderboard.

**Cut criteria (FIRST CUT if running over):**
- Skip if Ed already named labs pivoting in his opener — don't rehash
- Skip if Andrew has only ~17 min total — slide is setup, not spine

**Q&A defense if challenged on Poolside:** Laguna M.1 = 225B params / 23B active. Laguna XS.2 = 33B / 3B active, Apache 2.0 open weights. Trained on 30+ trillion tokens. SWE-bench Pro 46.9% (M.1), 44.5% (XS.2). Terminal-Bench 2.0 40.7% / 30.1%. Source: poolside.ai/blog/laguna-a-deeper-dive (Oct 2025).

---

## Slide 3 — The Bet (~120 sec) ⭐ load-bearing

**Read it slowly.**

> "Eighty-eight percent of respondents say AI has increased annual revenue — Ed showed you that side. The slide also says six percent trust it with anything that matters. You're probably in that gap. In about ten minutes you'll watch the bridge get built.
>
> Right now, on a workstation in this city, my agents are waiting for a brief.
>
> Not one agent. A team of them. They have offices. They have desks. They have memory.
>
> In about ten minutes, I'm going to commission one of them to log this exact talk into his memory. While I keep explaining how, he'll do it. By minute eighteen, the file will exist. You'll see the path appear on screen.
>
> If the bet pays off, you've watched the workbench complete a real piece of work in front of you. If it fails, you'll see exactly where it failed and why. Either way, that's the talk."

**Beat:** pause on "either way, that's the talk." Audience now has stakes.

**Cohesion guardrail:** the 88/6 stat is setup for the bet, NOT a standalone industry-context beat. Frame it as "you are the 94%" → "here's the bridge." If drifting toward industry-survey territory on stage, drop the spoken framing.

**Mystery-meat guard:** never show the 88/6 cards without the spoken setup. If cutting for time, cut both together — never leave cards orphaned.

**88% verification:** NVIDIA *State of AI* 2026 industry surveys (March 2026, blogs.nvidia.com/blog/state-of-ai-report-2026/). 3,200+ respondents across financial services, retail/CPG, healthcare/life sciences, telecommunications, manufacturing. Survey ran Aug-Dec 2025. Exact wording: *"Overall, 88% of respondents said AI has had an impact on increasing annual revenue, in some or all parts of the business."* The slide's "of respondents report AI revenue gains" is a paraphrase consistent with secondary press.

**Methodology caveat (for hostile Q&A):** opt-in marketing distribution sample, AI-engaged skew, NVIDIA has commercial interest. If pressed: *"Yes, opt-in convenience sample. The 88% still represents 3,200+ AI-engaged firms across five industries reporting revenue impact — a real signal in this room, not a universal claim."*

---

## Slide 4 — The Brief (~120 sec)

> "Before I commission, here's what I'm sending him. A brief. Six fields.
>
> Goal — what you want. Context — what he needs to know. Done means — how you'll know it worked. Escalate if — what's a stop sign. Deadline — when you need it back. Verify — how the result is proven.
>
> If you can write a brief for a freelancer, you can commission an agent. Two minutes to write the first one. No code. No SDK. No platform.
>
> The deadline I'm giving him: eighteen seconds. The verify: write the result to a file at a known path. If the file exists, the commission paid off. If not, it didn't.
>
> One aside for the regulators in the room — that *Escalate if* field is also EU AI Act Article 9. The brief isn't compliance theatre. It IS the automation boundary. Markdown, not a policy engine."

**Cue:** point at the six cards. Don't read all of them. Land on Goal, Verify, and Escalate if (the Article 9 callback).

**Why the Article 9 callback here, not on slide 12:** plants the seed early. By slide 12, the audience already knows the brief IS the automation boundary. The compliance slide becomes confirmation, not introduction.

---

## Slide 5 — The Anismin Office (~150 sec) ⭐ visual anchor

**Stand back. Let the room look. Stay on this slide for at least 90 seconds.**

> "This is not a metaphor. This is what's running on my workstation right now. I can pull this up live if anyone wants to see the ports — `localhost:8643`.
>
> Her name is Anismin. She's the CEO. The room in the centre with the teal floor — that's her office. Around her: Seraph, Cassiel, Halcyon, Raziel, Byte. Five sub-agents. Each has a desk. Each has a job.
>
> The big room on the right with the long table — that's the boardroom. They actually meet in there. Not as a metaphor. There's a Postgres table called `boardroom_session` and they take turns at the hand queue.
>
> The grey building on the bottom-left is the post office. The mailbox lives there. That's how she takes work in.
>
> The chat panel on the right is what I see when I message her. The activity feed under her name — those are real tasks she just finished.
>
> This is one floor. There are two more like it."

**Beat:** stay on this slide for at least 90 seconds. The room needs to absorb the image.

**If pressed (e.g., "show me live"):** *"Sure. Walk over after Q&A and I'll port-forward you in."* Don't demo the dashboard live during the keynote — too much surface area.

---

## Slide 6 — The Commission (~75 sec — LIVE DEMO)

**Action sequence:**

1. Confirm Discord text channel visible on projector
2. Press push-to-talk on phone
3. Speak slowly:
   *"Meridian, log tonight's talk in your memory. Event: OpenClaw Agentic Economy Night, Fiskaly Wien, 29 April 2026. Goal: extract three reusable lessons. Two artifacts: generate an image of a packed Vienna room tagged with tonight's date and post it to Discord; then write the lessons to your dated folder and post the file path. Confirm by voice when done."*
4. Release PTT. Walk back to slides. Click forward to slide 7 (Six Moves).

**While walking back:**

> "He has the brief. The clock starts. Two artifacts coming: the image lands in about six seconds — you'll hear the Discord ding. The lessons file lands at about eighteen seconds. Let me name what's happening, in order, while it happens."

**neob.ai callback** (audience landing — speak as walk-back line, gives neob's audience a peer-to-peer nod, reframes 18-sec wait as intentional):

> *"The voice channel gets you in at under 500ms. What happens after that is tonight's talk."*

**Backup if image fails:** *"Image generation is offline; the lessons file alone still pays the bet."* Don't apologise. Continue.

**Backup if voice fails at PTT:** *"Voice is offline, GPU is busy with a critic job. I'll DM the same brief instead. The pattern still runs."* Type the brief in Discord. Continue.

**Backup if scoreboard sits red past 60s:** *"That's the auto-expire — sixty seconds without a confirm. The honest version of always-on. We'll see the lessons file when it lands; the ticker just doesn't follow it after expiry."* Don't retry on stage. The lesson IS the failure mode being visible.

---

## Slide 7 — The Six Moves (~180 sec)

**Narrate as the artifact is being produced. Read it as a play-by-play.**

> "Move one: decompose. The goal *extract three lessons* becomes four sub-tasks. Read. Reflect. Write. Confirm. One outcome split into the smallest pieces that can each be done well.
>
> Move two: bespoke path. Each sub-task goes to the right brain. Reflection is hard, that's the cloud. Write-the-file is deterministic, that's a tool, no model. Voice reply must be fast, that's a small local model. The router never asks the smart model to do a dumb job. Different task type, different pipeline. No generic factory.
>
> Move three: verify. He produces a file you can check. The path posts in Discord. If the file isn't there, the commission failed. There is no grey zone."

**Cue:** glance at the projector. The file path should be appearing now. Gesture: *"There it is. The file just landed."*

> "Move four: document. The lesson goes into his wiki. Tomorrow's commission starts knowing what tonight's commission learned. Every past failure is already armed as a tripwire — the system gets less stupid every week.
>
> Move five: approve. The judgment bit. *Is lesson two actually a lesson?* — that's me. Risk, taste, what to publish. I do not approve typos or file paths.
>
> Move six: follow up. Cross-link. Index. The system is sharper than it was twenty minutes ago."

**Cue:** the artifact should be visible by now. Click forward.

---

## Slide 8 — AgentReef Federation (~120 sec) ⭐ now carries the bet payoff verbal cue (v17 fold after Bet Paid Off slide removed)

**v17 opener (carries the bet payoff that was on the cut Slide 8):** *"Eighteen seconds. While I was naming the moves, the agent finished — the path is on the Discord channel. The bet paid off."* (Pause 2 sec, gesture at side monitor.) Then continue:

> "Take a step back. The Anismin Office is one floor of three. Meridian's on Floor 2 — that's the agent you just watched. Kimi's on Floor 3 — ten ocean-themed agents running a pipeline called the Dark Factory.
>
> Three sovereign brains. Three memory stores. Federated over a signed message bus. JWT plus HMAC. My shard stays mine. Yours stays yours.
>
> Distributed sovereignty — no single vendor owns the substrate. Cross-reef messaging — Anismin asks Meridian for an opinion across the network, the reply lands in her memory the way an in-house DM would.
>
> And the third card — that's what the receipt on the last slide was doing. Two buildings. Two signatures. Same math. That's not a future product — it's the preflight you're looking at right now. **That's federation.**
>
> The design constraint that picked this shape: I want to disconnect from the reef and still have my agent. Git, not Google Docs. Each building is whole on its own."

**Sovereignty line** (after "JWT plus HMAC, my shard stays mine"):

> *"That's not just architecture. That's data sovereignty. The EU calls it the right to portability; I call it the design constraint that built this."*

**DLT Austria landing line** (audience landing — only deploy if Ed didn't already use a sovereignty frame in his opener):

> *"That's the same design bet the DLT community made — the ledger should work offline. If you need the network to be whole, you never owned the thing."*

**DLT Austria backup (Q&A only):** *"At Vienna Blockchain Week next month they're calling it 'compliance without surveillance.' This architecture arrived at the same place from a different direction — operational sovereignty as a design constraint, not a policy stance."*

**Fiskaly hook line** (relocated from cut Slide 8 — speak somewhere in this slide if it lands naturally, or hold for Q&A): *"Fiskaly already knows what this is. Signed event. Known path. Unbroken chain. The only difference is the cashier is an agent."*

---

## Slide 9 — How it talks (~90 sec) ⭐ NEW v17 — boardroom + mailbox + wiki diagram

**The first architecture-substance reveal. The deck shows the protocol, not just the metaphor. Speak it as the answer to the question 'how is this not a vendor?'**

> "Three sovereign brains. One protocol. One Postgres. The audit log *is* the federation.
>
> Floor 1 — Anismin on localhost 8643. Strategist. Owns the boardroom and the dispatch board.
> Floor 2 — Meridian on localhost 5096. Implementer. Lives in her openclaw sandbox with full tool access.
> Floor 3 — Kimi on localhost 9643. The swarm. Persona-mode crew, tier 1 through 3 cascade.
>
> They talk over a single REST call: POST slash v2 slash boardroom slash meetings slash speak. One header — X-Agent-Token — gates it. That's it. That's the federation protocol.
>
> And what it writes to: three Postgres surfaces. *boardroom_meetings* — every cross-floor speak, decision, and dissent gets one row, time-ordered, agent-attributed. *agent_mailbox* — the intra-floor async work. Lesson plans, teach/mentor, queued tasks. *Karpathy wiki* at slash workspace — file-backed shared memory, Obsidian-indexed, semantic-searchable.
>
> Federation is not a vendor. It's a protocol on top of an audit log."

**Cue:** point at the three floor cards as you name them. Point at the bus arrow. Point at the three storage cards. Don't read every word on the slide — gesture and summarise.

**Source:** `/anismin` consult 2026-04-29 morning — exact ports, REST path, table names, and the framing line "the audit log IS the federation" all from her direct architecture brief.

**Cut criteria:** if running over by end of slide 8, you can compress this slide to ~45 sec by reading only the closing line ("Federation is not a vendor — it's a protocol on top of an audit log"). The visual carries the rest.

---

## Slide 10 — The Pipelines (~90 sec) ⭐ NEW v16 substance

**This is the architecture-substance reveal. Lean in. The audience just saw federation as visible — now show them what's *underneath* it.**

> "Below the federation, three pipelines on disk in `scripts/pipelines/`. Each task type gets its own — wrong-flag-equals-wrong-verb is a 2am footgun.
>
> *federation_preflight.py* — fully working. Signed receipts. The GREEN-GREEN-GREEN page on the side monitor right now is one of these.
>
> *code_review.py* and *implementation_pr.py* — lifecycle and heartbeat real. Brain wiring stubbed for v2. One clean seam per pipeline.
>
> `/solve-room` stays as the strategy room for unknown work. The federation orchestrates above. The pipelines specialise below.
>
> Yegge's *Wasteland*, Willison's *Dark Factory*, Huntley's *Weaving Loom* — same camp. Operational form."

**Cue:** point at each card as you name it. The federation_preflight one should land hardest — gesture at the side monitor when you mention it.

**Dark factory line (v17 add — from Meridian's consult 2026-04-29):** read the green mono line on the slide — *"Floor 3's KCS swarm: 'one brief becomes a queue of narrow PR-sized jobs, not one giant autonomous guess.'"* That's the cleanest one-line description of the dark factory's decomposition pattern, in Meridian's own words.

**Source for dark factory framing:** /meridian consult 2026-04-29 morning. KCS swarm itself was silent during the consult (Floor 3 container unresponsive at the time) — Meridian's observation pattern stands in.

**Why this slide matters:** it's the difference between "Andrew built a workbench" and "Andrew built the operational expression of where the field is going." Without this slide the audience walks away with the demo. With it, they walk away with the architecture.

**Cut criteria:** if running >2 min over by end of slide 9, cut this slide entirely. The Yegge/Willison/Huntley camp framing carries forward verbally to slide 11. The federation_preflight side-monitor evidence stays load-bearing regardless.

**Q&A trap "Is this slideware?":** *"Three pipelines on disk as of today, in `scripts/pipelines/` parallel to solve-room. `federation_preflight` is the GREEN/GREEN/GREEN page on the side monitor — fully working, no LLM stubs, signs a receipt every run. `code_review` and `implementation_pr` are scaffolded as separate files (not flags on solve-room — wrong flag equals wrong verb is a 2am footgun) with lifecycle, heartbeat, and YAML policy live; brain wiring stubbed for v2 with one clean seam per pipeline. Pattern is on disk."*

---

## Slide 11 — The Self-Audit / How it learns (~90 sec) ⭐ DEEPEST SLIDE — v17 visualised with Meridian's 4-box loop

**The deepest slide. Now anchored on a 5-box flow: Work → Measure → Score → Propose → Human. Meridian's framing from /meridian consult 2026-04-29: "The system watches itself, grades itself, suggests the next safe upgrade, human approves the jump."**

> "Look at the slide. Five boxes. Work, Measure, Score, Propose, Human. That's how the architecture learns.
>
> Work — a commission runs. Measure — telemetry writes to the audit log. Score — Wilson lower bound, calibration confidence, N-meeting threshold. Propose — when the score crosses a threshold, the system opens a PR with the evidence pack. Human — that's me. I approve the jump.
>
> The system can propose its own evolution. It cannot implement it without my signature.
>
> A `/solve-room` meeting critiqued `/solve-room` itself. The methodology *failed mid-meeting* — Meridian died at 444KB context overflow, Codex timed out, Anismin marked her own reply *FAILED* rather than fabricate.
>
> Those failures are evidence of correctness, not bugs.
>
> The slide quotes the operating principle: *Code that ran successfully ≠ code that did the right thing observationally.* Audit-fiction is the named bug. HTTP 200 is not success. A row inserted is not a payload populated.
>
> Six shadow flags identified by the recursive meeting. Two wired live. Defaults stay false until explicit operator decision. Never auto-promotion.
>
> Meridian's caption: *Agents don't self-govern. They self-instrument.*"

**Cue:** point at each box in the flow as you name it. Dwell on Human — pause before saying "that's me." Then on the quote-block, slow down. The "code that ran successfully ≠ did the right thing observationally" line is the talk's *meta-thesis* — say it like it costs you something.

**Source for the 4-box loop:** /meridian consult 2026-04-29. Her exact framing was *"Work → Measure → Score → Propose → Human yes/no"* with the caption *"the system watches itself, grades itself, suggests the next safe upgrade, human approves the jump."* The slide visualises this verbatim.

**Source for the closing caption:** Meridian: *"Agents don't self-govern. They self-instrument."* Stage attribution to her in spoken delivery — it lands sharper as a quoted line than as Andrew's claim.

**Why this slide is the deepest:** it answers the unspoken question — *how do you know any of this is true?* The architecture audits itself. The recursive meeting failed in instructive ways. The discipline of FAILED-rather-than-fabricate is a cultural property, not a technical one. Audiences who've been burned by AI demos recognise this discipline immediately.

**Q&A trap "What if the architecture is wrong about itself?":** *"Then the next recursive meeting catches that, and the meeting after catches the meeting after. The loop is calibration discipline, not certainty. Wilson lower bound + N-meeting thresholds + manual promotion gates are how we keep the proposed-evolution rate under our verify-rate. The system is designed to be wrong, fail loud, and stay reversible."*

---

## Slide 12 — August 2, 2026 / EU AI Act (~90 sec)

**Maps the workbench's existing primitives to specific Articles of the EU AI Act, 96 days before binding enforcement. Vienna audience, regulated stack. Lean in.**

> "One last frame before I close. August 2, 2026 — 96 days from tonight — Article 13 of the EU AI Act binds. Replayable audit logs stop being nice-to-have. They become the baseline.
>
> Three cards. Article 9 mandates an *automation boundary* — which actions need human approval. That's the brief's *Escalate if* field — the same field I called out on slide 4. Markdown. Not a policy engine. You already have it.
>
> Article 13 demands interpretability — every action chain must be replayable, verifiable, not self-reported by the agent. That's the Postgres table I just walked you through. One row per agent action, time-ordered. The federation already produces it.
>
> Article 50 demands transparency — every agent must identify itself as non-human. That's the `agent_id` column on every audit row. Agent identifier, not a human alias. Machine-readable. Already there.
>
> The architecture this room watched tonight was forced into the shape the EU AI Act is going to require — by a different design constraint. *Sovereignty.* If your agents are sovereign, replayable, and identified, you're already building inside Article 13's lines."

**Closing line on slide:** *"Compliance theatre is what you bolt on. Compliance built in is what survives the audit."* — read this verbatim, then click forward.

**Pipeline scaffolding callback** (optional ~15s, only if you have time — turns the side-monitor element into concrete proof):

> *"And to make this concrete — the federation preflight you've been watching on the side monitor isn't a special-purpose health page. It's one of three bespoke pipelines I shipped this week. Its heartbeat writes to that Postgres table every 30 seconds. Its receipt is signed. Article 13 isn't on a roadmap — it ran while you were sitting here."*

**Cut criteria:** if running >2 min over by end of slide 11, skip this slide entirely. The Q&A trap on EU AI Act covers same ground. The slide is load-bearing for Vienna audience but not for the talk's spine.

---

## Slide 13 — Take It Home / Walk Off (~120 sec)

> "The line that opened this talk:
>
> A brief is a contract. A chat is a hostage situation.
>
> You watched the contract execute in front of you. Eighteen seconds. Real file. Real lessons. Real receipt. Three floors federated, one number on screen, the whole thing graded itself green.
>
> Day one: pick a recurring annoying task. Write one six-field brief for it. Run it once, by hand if you have to. You have an OS prototype tonight.
>
> Day thirty: a vault of dated lessons, one tripwire that has caught something real, briefs running from markdown instead of chat.
>
> Day ninety: routing across two or more brains, one or two agents you trust, you're commissioning daily.
>
> Nobody needs to be at Day 90 next week. Just don't be at Day 0 next month.
>
> One honest beat before you go. The first two weeks of doing this feel slower. Not faster. Slower. By week three they're not. By week eight you can't go back. I tell you that because the serious people in this room would discover it alone in week one and trust me less.
>
> Build the machinery. Not be the person doing every task faster. Build the machinery that lets good tasks get done reliably, cheaply, with accountability.
>
> The deck is at the QR. Photograph it now. Find me at the bar.
>
> Stop chatting. Start commissioning.
>
> You weren't watching agents that work. You were watching architecture that audits itself, specialises by task, ships its own fixes — visible right now on a workstation in this city."

**Beat:** end on the kicker. Three seconds of silence. Walk off, or take Q&A from the floor.

**Why the kicker extends:** the original close ("Stop chatting. Start commissioning.") was action. The v16 kicker adds depth — names what the room actually saw. After slide 11 (Self-Audit) lands, the audience is ready for this claim.

---

## Time discipline (v17)

| Slot | Slide | Cumulative |
|---|---|---|
| 0:00 – 1:00 | 1. Title | 1:00 |
| 1:00 – 1:30 | 2. The Shift | 1:30 |
| 1:30 – 3:30 | 3. The Bet (with 88/6) | 3:30 |
| 3:30 – 5:30 | 4. The Brief (Article 9 hint) | 5:30 |
| 5:30 – 8:00 | 5. The Anismin Office | 8:00 |
| 8:00 – 9:15 | 6. The Commission (live demo) | 9:15 |
| 9:15 – 12:15 | 7. The Six Moves | 12:15 |
| 12:15 – 14:15 | 8. Federation (with bet-payoff opener) | 14:15 |
| 14:15 – 15:45 | 9. How it talks ⭐ NEW v17 | 15:45 |
| 15:45 – 17:15 | 10. The Pipelines (with dark factory line) | 17:15 |
| 17:15 – 18:45 | 11. The Self-Audit (4-box loop) | 18:45 |
| 18:45 – 20:15 | 12. August 2 / EU AI Act | 20:15 |
| 20:15 – 22:15 | 13. Take It Home | 22:15 |

**Total content: ~22 min. Buffer: ~8 min for organic stretch, audience reactions, demo wait time, Q&A in 30-min slot.**

v17 swap: removed the standalone Bet Paid Off slide (~150s, federation preflight image was too dense visually). Added "How it talks" architecture diagram (~90s). Bet payoff now lands verbally on slide 8 (Federation) opener.

If Ed gives you 17 min: cut slide 2 (Shift) AND slide 10 (Pipelines) — saves ~2 min. Total drops to ~21 min. Still tight.

If Ed gives you 30+ min: hold pace. Don't add content. Slow demo arc (slide 5 dwell, slide 7 play-by-play) and expand Q&A.

---

## Cut order (v16)

**Tier A (first cut, ~30s):** Slide 2 (Shift) — if Ed already covered lab pivot in his opener, skip. Q&A trap on Poolside Laguna covers same ground.

**Tier B (second cut, ~90s):** Slide 10 (The Pipelines) — if running >2 min over by end of slide 9. The Yegge/Willison/Huntley camp framing carries forward verbally to slide 11. Q&A trap "Is this slideware?" covers the on-disk evidence.

**Tier C (third cut, ~90s):** Slide 12 (EU AI Act) — only if running >3 min over by end of slide 11. Q&A trap on Article 9/13/50 covers same ground.

**Tertiary cuts (speaker-note lines, drop in this order):**
1. Slide 12 pipeline-scaffolding callback (~15s)
2. Audience landing lines: neob.ai callback on slide 6 (~5s), DLT Austria line on slide 9 (~10s), Fiskaly hook on slide 8 (~10s)
3. The 88/6 spoken setup on slide 3 (~15s) — cut visual cards AND spoken setup together

**DO NOT cut:** Slides 1, 3, 4, 5, 6, 7, 8, 9, 11, 13. They are load-bearing for the spine sentence and the demo arc. Slide 11 (Self-Audit) is the v16 substance reveal — if it goes, the talk reverts to the surface-level v15.x experience.

---

## Q&A traps

Full content in `QA-AMMUNITION-BANK.md`. Three to drill out loud tonight before sleeping (if not already drilled this week):

- **A1 (AutoGPT)** — schema-enforced contracts vs flat loops. *"AutoGPT was a single flat loop with no memory, no schema enforcement, no inter-agent trust boundary. Tonight's stack has a Postgres-backed event bus, a six-field brief that acts as a typed contract between floors, and a `federation_preflight` handshake that rejects malformed messages. That's an architecture, not a loop."*

- **A2 (CVEs — operator framing)** — *"All three are real. I run OpenClaw on a Tailscale-only network — no exposed gateway port, lockfile-pinned MCP servers, zero unvetted ClawHub skills. CVE-2026-25253's one-click RCE assumes a public gateway. Mine isn't public. The lesson is not 'don't build this' — it's 'don't run untrusted skills with network access.' That's an operator decision, not a patch."* (Maintainer-framing as backup only — narrow answer if asked specifically about patch state. Verify v2026.1.29+ on lectern pre-show.)

- **A4 (MIT NANDA 95%)** — *"NANDA's diagnosis is that pilots fail when AI is bolted on as a chat layer rather than restructured into delegatable units of work. That's exactly the distinction I'm making. The 5% that succeed stopped asking the AI questions and started giving it scope-bounded jobs. I'm not claiming I'm at scale in that 5% — I'm claiming the architecture is the right starting point."*

**Other deployable traps (full text in QA-AMMUNITION-BANK.md):**
- "How do you prove this works on anything other than your laptop?"
- "Why should an EU founder trust a US-based stack?"
- "What happens when one of your three brains hallucinates?"
- "Aren't you just demoing the happy path?"
- "GDPR / data residency for regulated customers?"
- "Web4 — what Ed talked about — does this connect?" (Ed-coordination flag: pivot to MCP/A2A operational layer, don't repeat 7,851% if Ed cited it)
- "Why didn't you build on LangGraph / CrewAI / AutoGen?" (Ed-coordination flag: deflect back to Ed if he covered runtime-vs-library)
- "How does this map to EU AI Act?" (full Article 9/13/50 mapping)
- "MIT NANDA 95% pilot failure"
- "Gartner agentwashing warning"
- "Is this slideware?" (pipeline scaffolding evidence)
- "Isn't solve-room a generic factory?" (sibling files vs flag, Anismin's Q2 verdict)
- "How long did this take to build?"
- "What's the cheapest way to get to my first commission?"
- "Hardware/cloud bill budget?"

**AMaaS pricing tier backup** (if pressed on subscription/services angle — kept Q&A-only since v11 boardroom cut):
- EUR 5K/mo Starter (5 skill transfers, quarterly reviews)
- EUR 10K/mo Growth (unlimited transfers, continuous federation, SLAs)
- EUR 20K/mo Premium (dedicated mentor instance, white-label, IP co-ownership)
- Credibility line if pressed: *"I'm not pitching you tonight. I'm telling you the line of business is hiding in plain sight."*

---

## What changed from v15.8 → v16 (full refactor — 2026-04-29 morning, day-of-keynote)

User flagged that an external repo exploration captured the surface (workbench, brief, federation) but missed the architecture's substance: bespoke pipelines on disk, recursive self-improvement, Wilson LB calibration, the audit-fiction principle. Asked for full refactor from scratch.

**Two new slides surface the depth:**

- **Slide 10 — The Pipelines:** three on-disk pipelines as concrete evidence of bespoke-per-task-type framing. `federation_preflight.py` (live, the side-monitor page is one of these), `code_review.py` and `implementation_pr.py` (scaffolded). Yegge / Willison / Huntley camp naming moved here from slide 9 footer. Concrete proof that the federation orchestrates above genuinely-specialised pipelines, not a generic factory.

- **Slide 11 — The Self-Audit:** the recursive critique loop, audit-fiction as the named bug, manual promotion gates. The deepest slide of the talk. Quote-block: *"Code that ran successfully ≠ code that did the right thing observationally."* Six shadow flags + Wilson LB + manual gates = the system can propose evolution but cannot implement it without operator signature.

**Reframing on existing slides:**

- **Slide 1:** handoff line ends with "and the architecture that audits itself" — sets up the deeper claim from the first 30 seconds
- **Slide 4:** small Article 9 hint added below existing footer — plants compliance seed early
- **Slide 9:** Yegge / Willison / Huntley footer removed (moved to slide 10)
- **Slide 13:** kicker extends with the meta-thesis — "you weren't watching agents that work; you were watching architecture that audits itself, specialises by task, ships its own fixes"

**Spine sentence extends:** from "watch your workbench federate" to "watch the architecture audit itself."

**Total deck:** 13 slides, ~23 min content, ~7 min Q&A buffer.

**Why the demo arc is preserved verbatim:** slides 5-8 (Office → Commission → Six Moves → Receipt) are load-bearing. The bet pays off there. Touching them risks the whole talk. v16 adds substance after the bet pays off, not before.

**Why the Self-Audit slide is the deepest:** it answers the question the audience hasn't asked yet — *how do you know any of this is true?* The recursive meeting that failed in instructive ways IS the answer. Audiences who've been burned by AI demos recognise the discipline of FAILED-rather-than-fabricate immediately.

---

## Why v16 looks different from v15.8

The v15.x deck told the surface story: stop chatting, brief contract, demo lands, federation graded green, EU AI Act compliance. That's true. It's not deep enough.

The v16 deck adds:
- **Concrete on-disk evidence** that the architecture specialises by task (slide 10)
- **The self-audit principle** that the architecture critiques itself with manual gates (slide 11)
- **The meta-thesis** in the close kicker — the audience isn't watching agents, they're watching architecture

These three additions answer the implicit question of v15.x: *"OK the demo worked, but what makes this different from any other agent demo?"* The answer is the depth — bespoke pipelines, recursive critique, audit-fiction as named bug, manual promotion gates. Vienna founders who have seen 100 agent demos haven't seen this discipline.
