# Speaker Notes — Quit chatting with your agents (v15 / cohesion cut)

**Talk:** Quit chatting with your agents and get them to work for you
**Event:** OpenClaw × neob.ai · Agentic Economy Night · Fiskaly Wien
**Date:** Wednesday 29 April 2026
**Slot:** Keynote, second speaker. Ed Prinz opens with OpenClaw introduction + business AI context. Andrew follows as the keynote. Possibly a third 10-min closer after Andrew.
**Length target:** ~17 min content + ~13 min Q&A buffer = 30 min (v15 cut Three Floors and Honest Beat as standalone slides; receipt moved into Bet Paid Off; subscription line dropped from close)

The talk is one sentence: ***Stop chatting with your agents — hand them a contract, verify the receipt, and watch your workbench federate.***

That's the spine. Bet → Brief → Office (the workbench is real) → Commission (live demo) → Six Moves (what's happening) → Bet Paid Off + Receipt (verify) → Federation (scale) → Take it home. Nine slides. Every slide serves the sentence; if a slide doesn't, it got cut.

**Ed has already covered:** what OpenClaw is, the case for proactive AI, agents in business workflows. So Andrew does NOT re-introduce OpenClaw or make the agents-are-here case. The keynote picks up where Ed leaves off and goes deep on the *operational* layer — what it actually looks like when one person commissions a building of agents on a Monday morning.

---

## Pre-talk checklist (T-30 min)

- [ ] Discord client logged in. **Voice and text channels both visible on the projector** (or one tap away).
- [ ] Tailscale connected to Vienna workstation. Ping Meridian (`/meridian status`)
- [ ] AnisminOS dashboard reachable at `localhost:8643` — the screenshot on slide 4 is the live UI; if you can show it on a second projector tab, do it.
- [ ] Slides loaded. `F` for fullscreen. `T` starts the 30-min timer.
- [ ] **T-10 min: send a silent priming text to Meridian in Discord**: *"Tonight: Fiskaly Wien talk. When I commission you live, the brief will ask for memory log + 3 lessons. Save to `memory/2026-04-29-fiskaly.md`. Do not pre-write."*
- [ ] **T-5 min: GPU load check.** If VRAM > 31 GB, voice may go offline. Plan for the text-only fallback.
- [ ] **Backup demo video** queued on lectern laptop in second tab — pre-recorded 30s clip of the same commission running cleanly. If voice fails on stage, switch tab and play it.
- [ ] AV tech briefing: *"At slide 6 I'll speak into my phone for ~10 seconds. About 6 seconds later, a generated image lands in Discord. About 18 seconds later, the lessons file path appears as text in the same channel. The Discord text channel needs to be visible the whole time. I'll also need a side monitor showing two URLs — `localhost:9643/office/preflight` and `localhost:8643/boardroom2/preflight` — both auto-refresh every 5 seconds, both should grade GREEN throughout the talk."*
- [ ] Water on the lectern.

### Side-monitor projection (v14 addition)

KCS shipped the federation_preflight as a stage-projectable terminal-aesthetic webpage at v4.9.0 (2026-04-28). AnisminOS mirrors it at `/boardroom2/preflight`. Same data, two signatures.

- **Side-monitor 1 (KCS-side, primary)**: `http://localhost:9643/office/preflight` — full data, signature line `✓ Federation is keynote-ready.`
- **Side-monitor 2 (AnisminOS-side, mirror)**: `http://localhost:8643/boardroom2/preflight` — same checks, attesting from Floor 1
- Both auto-refresh every 5 seconds. Black background, green CRT scanlines, fits a venue confidence monitor without modification.
- If only one side monitor is available, project the KCS one (more complete) and leave AnisminOS in a browser tab on the lectern.
- If a check goes YELLOW or RED on stage, that's not a failure of the talk — it's the workbench reporting honestly. Acknowledge it: *"There it is. The system just told you something. That's the point."*

### Tuesday-EOD risk burn-down — AUTOMATED

KCS shipped `scripts/federation_preflight.py` on 2026-04-28 (commit `154473f`, v4.8.4) that runs the entire 6-item check as a one-liner and grades GREEN / YELLOW / RED.

```bash
docker exec kimiclaw-web python /app/scripts/federation_preflight.py --json
```

**Live grade at v13 ship time (2026-04-28 11:06 UTC): GREEN 6/6**:

- Floor 1 heartbeat (AnisminOS, shape v1) ✓
- Floor 2 heartbeat (MeridianOS, shape v1) ✓ — Pod C shipped 06:09 today
- Floor 3 heartbeat (KCS, shape v1, build `bc0f13b`) ✓
- KCS bet round-trip ✓
- cross-floor REST auth gate ✓ (404 with proper message, expected without kimiclaw-floor token)
- target_artifact date substitution ✓ (verified resolves at dispatch time, no hard-coded Wednesday string)

The Anismin pre-Wed concerns from boardroom #5 (clock skew, idempotency, date-param) are now all script-checked. **Run the preflight T-30 on Wednesday and again at the lectern; act on RED only.**

### Pod A2 (federation scoreboard) — UNCONFIRMED for Wednesday

Anismin's solve-room verdict 2026-04-28: *"No confirmed A2 ETA. Stage the v10 Discord-only fallback in a branch by Tuesday noon, flip it only if A2 doesn't land by 18:00 CEST."*

- v13 (current) does NOT promise the scoreboard on slide 6 — only Discord image + Discord lessons file. Honest if A2 slips.
- A `v12-discord-fallback` branch is staged on the repo for the worst case (A2 lands but breaks; we revert mid-day Wednesday).
- If Pod A2 ships clean by Tuesday EOD, restore the scoreboard reference on slide 6 via a one-line edit.

---

## Slide 1 — Title (~60 sec)

> "Thanks Ed. You just walked the room through what OpenClaw is and what agents can do for a business. I'm going to take you one floor down. Into the operational layer.
>
> The title's on the slide. *Quit chatting with your agents and get them to work for you.* The line that runs through the talk: a brief is a contract. A chat is a hostage situation.
>
> Tonight I'm going to bet a real piece of work on that line. Live. In front of you."

**Cue:** acknowledge Ed warmly but briefly. Don't restate his content. Click forward.

---

## Slide 2 — The Bet (~120 sec)

**This is the load-bearing slide. Read it slowly.**

> "Right now, on a workstation in this city, my agents are waiting for a brief.
>
> Not one agent. A team of them. They have offices. They have desks. They have memory.
>
> In about ten minutes, I'm going to commission one of them to log this exact talk into his memory. While I keep explaining how, he'll do it. By minute eighteen, the file will exist. You'll see the path appear on screen.
>
> If the bet pays off, you've watched the workbench complete a real piece of work in front of you. If it fails, you'll see exactly where it failed and why. Either way, that's the talk."

**Beat:** pause on "either way, that's the talk." Let the bet land. The audience now has stakes.

---

## Slide 3 — The Brief (~120 sec)

> "Before I commission, here's the thing I'm about to send him. A brief. Six fields.
>
> Goal: what you want. Context: what he needs to know. Done means: how you'll know it worked. Escalate if: what's a stop sign. Deadline: when you need it back. Verify: how the result is proven.
>
> If you can write a brief for a freelancer, you can commission an agent. Two minutes to write the first one. No code. No SDK. No platform.
>
> The deadline I'm giving him: eighteen seconds. The verify: write the result to a file at a known path. If the file exists, the commission paid off. If not, it didn't."

**Cue:** point at the six cards. Don't read all of them. Land on Goal and Verify.

---

## Slide 4 — The Anismin Office (~150 sec) ⭐ NEW

**This is the visual anchor of the keynote. Stand back. Let the room look.**

> "This is not a metaphor. This is what's running on my workstation right now. I can pull this up live if anyone wants to see the ports — `localhost:8643`.
>
> Her name is Anismin. She's the CEO. The room in the centre with the teal floor — that's her office. Around her: Seraph, Cassiel, Halcyon, Raziel, Byte. Five sub-agents. Each has a desk. Each has a job.
>
> The big room on the right with the long table — that's the boardroom. They actually meet in there. Not as a metaphor. There's a Postgres table called `boardroom_session` and they take turns at the hand queue.
>
> The grey building on the bottom-left is the post office. The mailbox lives there. That's how she takes work in.
>
> The chat panel on the right is what I see when I message her. The activity feed under her name — those are real tasks she just finished. Memory wiring smoke test. Brain audit. Risk in legal: single undated page.
>
> This is one floor. There are two more like it."

**Beat:** stay on this slide for at least 90 seconds. The room needs to absorb the image.

**Add at end (v11 boardroom delta):** *"As of this morning her lobby embeds Floor 3 live. When KCS's swarm room lights up, you can watch it without leaving the page. The boardroom on the right takes guests from other floors. The building isn't just floored — it's connected."*

**Backup if anyone challenges it:** "Yes I can pull up the live UI right now. It's running. I'll show you after." Don't promise to do it on stage; reserve that for Q&A.

---

## Slide 5 — The Commission (~75 sec — DEMO)

**ACTION SEQUENCE (v12 dual-verify, scoreboard-aware):**

1. Confirm Discord text channel + Anismin's federation scoreboard (Pod A2) both visible on projector
2. Press push-to-talk on phone
3. Speak slowly:
   *"Meridian, log tonight's talk in your memory. Event: OpenClaw Agentic Economy Night, Fiskaly Wien, 29 April 2026. Goal: extract three reusable lessons. Two artifacts: generate an image of a packed Vienna room tagged with tonight's date and post it to Discord; then write the lessons to your dated folder and post the file path. Confirm by voice when done."*
4. Release PTT. Walk back to slides. Click forward to slide 7 (Six Moves).

**While walking back:**
> "He has the brief. The clock starts. The scoreboard already knows. Two artifacts coming: the image lands in about six seconds — you'll hear the Discord ding and watch the bet ticker turn green — and the lessons file lands at about eighteen seconds, which fades in the lessons card. Let me name what's happening, in order, while it happens."

**Backup if image generation fails:** *"Image generation is offline; the lessons file alone still pays the bet."* Don't apologise. Continue. (Verified Mon 27 Apr: Meridian DOES have `image_generate` first-class via Gemini 3.1 flash and 3 Pro — this fallback is for the unlikely case it errors mid-call.)

**Backup if voice fails at PTT:** *"Voice is offline, GPU is busy with a critic job. I'll DM the same brief instead. The pattern still runs."* Type the brief in Discord. Continue.

**Backup if scoreboard sits red past 60s:** the bet auto-expired (KCS rule). *"That's the auto-expire — sixty seconds without a confirm. The honest version of always-on. We'll see the lessons file when it lands; the ticker just doesn't follow it after expiry."* Don't retry on stage. The lesson IS the failure mode being visible.

---

## Slide 6 — The Six Moves (~180 sec)

**This slide narrates while the artifact is being produced. Read it as a play-by-play.**

> "Move one: decompose. The goal *extract three lessons* becomes four sub-tasks. Read. Reflect. Write. Confirm. One outcome split into the smallest pieces that can each be done well.
>
> Move two: route. Each sub-task goes to the right brain. Reflection is hard, that's the cloud. Write-the-file is deterministic, that's a tool, no model. Voice reply must be fast, that's a small local model. The router never asks the smart model to do a dumb job. That's cost, quality, privacy, latency, in one decision.
>
> Move three: verify. He produces a file you can check. The path posts in Discord. If the file isn't there, the commission failed. There is no grey zone."

**Cue:** glance at the projector. The file path should be appearing now. Gesture: *"There it is. The file just landed."*

> "Move four: document. The lesson goes into his wiki. Tomorrow's commission starts knowing what tonight's commission learned. And every past failure is already armed as a tripwire — the system gets less stupid every week.
>
> Move five: approve. The judgment bit. *Is lesson two actually a lesson?* — that's me. Risk, taste, what to publish. I do not approve typos or file paths.
>
> Move six: follow up. Cross-link. Index. The system is sharper than it was twenty minutes ago. Tomorrow's commission inherits everything tonight just learned."

**Cue:** the artifact should be visible by now. Click forward.

---

## Slide 7 — Bet Paid Off + Receipt (~150 sec) ⭐ v15 fold

> "Eighteen seconds. While I was naming the moves, the agent finished. The path is on screen. The lessons are saved. The follow-up is queued.
>
> I spoke a six-field brief out loud. Once. Walked away. Meridian decomposed, routed, verified, documented, surfaced for approval, queued follow-up. The room watched an artifact appear at a real file path. Not a slide. Not a claim. A file.
>
> That's a workbench. That's commissioning. The chat window doesn't do that."

**Beat:** hold the green DONE badge on screen for the room to see. Three seconds of silence is fine.

---

## Slide 8 — AgentReef Federation (~120 sec) ⭐ now also carries the floors framing

> "Take a step back. The Anismin Office is one floor of three. Meridian's on Floor 2 — that's the agent you just watched. Kimi's on Floor 3 — ten ocean-themed agents running a pipeline called the Dark Factory.
>
> Three sovereign brains. Three memory stores. Federated over a signed message bus. JWT plus HMAC. My shard stays mine. Yours stays yours.
>
> What this buys you: distributed sovereignty, no single vendor owns the substrate. Cross-reef messaging — Anismin can ask Meridian for an opinion across the network and the reply lands in her memory the same way an in-house DM would. And skill transfer — what Anismin learns mentoring one client's stack travels, anonymised, to the next. The reef compounds.
>
> The design constraint that picked this shape: I want to disconnect from the reef and still have my agent. Git, not Google Docs. Each building is whole on its own."

**Cue:** point at the three cards as you name the three benefits. The federation art is doing the metaphor work; let it.

---

## Slide 9 — Take It Home / Walk Off (~120 sec) ⭐ v15 fold

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
> Build the machinery. Not be the person doing every task faster. Build the machinery that lets good tasks get done reliably, cheaply, with accountability. Ed showed you the case. I just showed you the workbench. Now you build yours.
>
> The deck is at the QR. Photograph it now. Find me at the bar.
>
> Stop chatting. Start commissioning."

**Beat:** end on "start commissioning". Three seconds of silence. Walk off, or take Q&A from the floor.

---

## Time discipline (v15 — cohesion cut)

| Slot | Slide | Cumulative |
|---|---|---|
| 0:00 – 1:00 | 1. Title | 1:00 |
| 1:00 – 3:00 | 2. The Bet | 3:00 |
| 3:00 – 5:00 | 3. The Brief | 5:00 |
| 5:00 – 7:30 | 4. The Anismin Office ⭐ | 7:30 |
| 7:30 – 8:45 | 5. Commission (live demo) | 8:45 |
| 8:45 – 11:45 | 6. Six Moves (narration) | 11:45 |
| 11:45 – 14:15 | 7. Bet Paid Off + Receipt ⭐ | 14:15 |
| 14:15 – 16:15 | 8. Federation (floors folded in) ⭐ | 16:15 |
| 16:15 – 18:15 | 9. Take It Home (honest beat folded in) ⭐ | 18:15 |

**Total content: ~18 min. Buffer: ~12 min for organic stretch, audience reactions, demo wait time, Q&A.**

The single-sentence story Anismin gave us: ***"Stop chatting with your agents — hand them a contract, verify the receipt, and watch your workbench federate."***

Bet → Brief → Office → Commission → Moves → Bet Paid Off + Receipt → Federation → Close. Nine beats. Each beat is one slide.

The 18-min demo arc still anchors the middle. If the demo overshoots by 30-60 seconds, the slack from slides 11+12 absorbs it. If it lands clean, you have room for one or two questions before the bar.

---

## What to do if the demo runs long

- The artifact should be visible by the end of slide 7. If it isn't, click forward to slide 8 anyway. The "DONE" framing on slide 8 still works as a verbal claim — when the artifact does appear (slide 9 or later), gesture and acknowledge: *"There it is. Took longer than usual. That's venue Wi-Fi."*
- If voice never replies but text posts: same flow. Slide 8 is about the file existing, not the voice.
- If both fail: the line is *"Voice is offline. The honest version of always-on, exactly what slide 9 will warn. If it breaks, you see it break. That's the talk too."* Click forward. Do not retry. Do not apologise.

---

## What to do if the demo runs short

- If the artifact appears on slide 6 (during the commission speech): perfect. Acknowledge: *"That fast. He didn't even let me finish the explanation."* Click through slide 7 quickly, dwelling only on moves 4-6 (the parts the audience didn't see directly).
- If you finish all 11 slides in 18 minutes: stop. Take questions. Walk off at 28.

---

## The cut order, if running over

1. **Cut slide 6 (Mailbox Bus)**. The Postgres detail is the most cuttable architecture beat. The two office slides (4, 5) carry the visual weight.
2. **Cut slide 10 (Honest Beat)** as last resort. Costs credibility but saves 75 seconds.
3. **Cut the AMaaS one-liner from slide 12**. Drop the "subscription line of business" sentence; close on "Stop chatting. Start commissioning." cleanly.

Do NOT cut slides 4, 5, 7, 8, 9, 11. They are load-bearing.

The AMaaS standalone slide was already cut in v11 per Fathom's call (boardroom #5). Pricing tiers (EUR 5K/10K/20K), Texterous-shape signal, and the "I'm not pitching you tonight" line are now Q&A backup material — see traps below.

---

## Common Q&A traps

- *"Isn't this just AutoGPT?"* — No. AutoGPT had no holdout reviewer, no calibration replay, no tripwires from past failures, no commission contract. The brief is the difference. Plus federation between sovereign instances — AutoGPT was one process, this is a network.
- *"What about hallucinations?"* — They happen. The local critic catches the dangerous ones. The non-dangerous ones don't ship because the verify step requires a real artifact at a real path.
- *"How much does this cost to run?"* — Anismin runs on a $20 VPS plus an Anthropic Max subscription. Meridian's hardware was a sunk cost. The Aegis verifier in shadow mode runs on a second Max seat. The expensive thing is your time, and you're getting it back.
- *"Will I need to learn to code?"* — To run a brief, no. You write markdown. You read the artifact. The agent writes the code. If you can brief a freelancer, you can commission an agent.
- *"Is the AMaaS pitch the close?"* — No. The close is "build your own machinery." If someone reads the AMaaS slide as the sales close, that's a sign you over-emphasised it. Read it flatter next time.
- *"What about what Ed said about [X]?"* — Honour Ed's framing. He set the table; this talk is what gets eaten at it. Don't contradict him on stage even if you'd phrase something differently.
- *"Show me the live UI"* — Defer to after the talk: "Sure. Walk over after Q&A and I'll port-forward you in." Don't demo the dashboard live during the keynote — too much surface area for things to go wrong.
- *"Tell me more about the federation-mentor subscription"* (or any AMaaS-flavoured question) — backup material, since v11 cut the standalone slide:
  - **Pricing tiers**: EUR 5K/mo Starter (5 skill transfers, quarterly reviews) · EUR 10K/mo Growth (unlimited transfers, continuous federation, SLAs, monthly novel skills) · EUR 20K/mo Premium (dedicated mentor instance, white-label, IP co-ownership; one mentor cluster serves ~20 clients).
  - **Vienna signal shape**: AI consultancy, ~16 people, one AI-native product (e.g. ERP), team bogged in client delivery, product drifting behind state-of-the-art. They asked us to meet.
  - **The credibility line, only if pressed**: *"I'm not pitching you tonight. I'm telling you the line of business is hiding in plain sight, and I think a few of you are sitting on it."*

---

## What changed from v9 (so you know what's gone)

The 12-slide v9 keynote is replaced. Major changes:

- **Adds the building.** Slides 4, 5, 6 are entirely new — the Anismin Office screenshot hero, the three-floor architecture, and the Mailbox Bus plumbing.
- **Adds federation.** Slide 11 introduces AgentReef as the inter-building protocol — the design choice that makes this scale beyond one person.
- **Drops "The Team" slide.** The two real agents are now visible inside the building tour (slide 5).
- **Drops the standalone "Day 1/30/90" slide.** Folded into the close.
- **Drops "Hostage Callback" + "Walk Off" as separate slides.** Combined into close.

The story spine — bet → brief → commission → six moves → bet paid off → close — is intact. What's new is the building you commission *into* and the federation that scales it.

## What changed from v10 → v11 (boardroom #5 — MeridianOS round-table)

Cross-floor consult on Sunday 27 Apr. MeridianOS boardroom round-table (5 execs) delivered the deltas:

- **Slide 4** — added boardroom + visit-aware lobby callout (Glacier's "hidden demo moment").
- **Slide 7** — dual-verify (image at ~6s + lessons at ~18s) per Meridian's Q3 pick.
- **Slide 12 (AMaaS)** — CUT and folded into close per Fathom; pricing moved to Q&A backup.
- **Pre-flight risk burn-down** — Sentry's three failure modes added.
- **Slide count 13 → 12.**

## What changed from v14 → v15 (cohesion cut after `/solve-room` audit 2026-04-28 14:23)

Andrew's read of v14: *"inconsistent, long-winded, not a cohesive message."*

Anismin convened in `/solve-room` (Meridian + Kimi silent again — context-overflow + KCS swarm wedge). Single-brain authority verdict, three findings:

1. **Inconsistency** — slides 5 + 10 both did architecture (floors vs federation, redundant). Slide 10 stuffed federation + receipt into one slot. Slide 11's subscription line undercut the workbench thesis ("operator > chatter" → soft pitch at the curtain).
2. **Long-winded** — 11 slides for one story. Pre-slide-7 had dilution.
3. **Cohesion** — no single-sentence anchor. The deck had three competing messages.

Anismin's single sentence: ***"Stop chatting with your agents — hand them a contract, verify the receipt, and watch your workbench federate."***

Restructure (11 → 9):

- **DROP** standalone Three Floors slide (was 5). Floors framing folded into Federation slide.
- **MOVE** preflight receipt from Federation slide to Bet Paid Off. Receipt is verification of the bet, not a federation footer.
- **DROP** standalone Honest Beat slide (was 9). Folded into Take It Home as one sentence.
- **DROP** subscription line from Take It Home. Undercuts the workbench thesis. Bar conversations only.
- Federation slide opens with *"The Anismin Office is one floor of three"* — that's where the three-floors reveal lands now.

Net: tighter spine, no architecture-vs-architecture friction, receipt sits where it earns its time.

## What changed from v13 → v14 (two-receipts ship 2026-04-28 evening)

Anismin + KCS shipped overnight (4.5 hours of agent work after v13 went live):

- **KCS Floor 3 receipt** at `localhost:9643/office/preflight` — v4.9.0 sha=`eb17777`. Stage-projectable terminal aesthetic (black/green CRT, scan-lines, pulse, signature line that flips per grade). Auto-refresh every 5s.
- **AnisminOS Floor 1 mirror** at `localhost:8643/boardroom2/preflight` — sha=`3788b2f`. Same data, second signature.
- Both converge GREEN 6/6 on the same `/office/api/heartbeat` endpoints. Anismin's framing: *"same data, two signatures, audience can't argue with that math."*

Anismin's sign-off: *"actually keynote-grade, not demoware."*

Pod A2 status (final per Anismin): v10 fallback blessed default; polling halted; deck stays honest without it. Pod C silent (Meridian context-overflow theory holds); Floor 2 heartbeat alive; receipt picks it up as PASS regardless of bet-aware-fields wiring; optional.

DECK CHANGES

- **Slide 10**: replaced static green-card receipt with a screenshot of the live KCS preflight page. Caption underneath references both URLs (KCS-side + AnisminOS mirror) and the auto-refresh / two-signatures framing.
- **Speaker notes**: A/V briefing updated to request a side monitor with both URLs visible during the talk. Added a "Side-monitor projection" subsection in the pre-talk checklist.
- **Slide 10 narration**: rewritten around two-receipts framing. The closing line is now *"Receipts, not promises. That's the workbench eating its own dog food."*

POST-KEYNOTE FOLLOW-UPS (logged, not deck-blocking)

- KCS persona-mode dispatch wedge at low budgets (steps=4/3 budget_exhausted, output empty) — separate from v4.8.x narration chain
- Runtime narration uses `persona_facade` via `persona_registry` (not `AGENT_CODE_NAMES`) — by-design per v3 plan; static tests still hold
- PR #33 (HEARTBEAT_CONTRACT.md → AnisminOS_Memory) still OPEN, mergeable=UNKNOWN; left as-is

## What changed from v12 → v13 (solve-room cross-floor + ship audit 2026-04-28 morning)

Cross-floor `/solve-room` boardroom 2026-04-28 11:05 CEST. Anismin spoke (Opus, single-brain authority); Meridian no reply; KCS swarm timeout. Verdict: `<DONE>` with three concrete deltas:

- **Slide 6 — scoreboard reference REMOVED** (Anismin's call: *"No confirmed A2 ETA. Stage v10 Discord-only fallback. Rolling back is cheap, panic-editing Wednesday morning isn't."*) Replaced with: *"Image lands fast and loud. File lands durable. Both visible in Discord regardless of any other UI."* Honest if A2 slips.
- **Slide 10 — preflight receipt badge ADDED** (Anismin's call: *"timestamped preflight badge converts architecture claim into verifiable receipt"*). Green card showing 2026-04-28 11:06 UTC, 6/6 GREEN, with all 6 check items listed. Frames slide 10 as receipts-not-promises.
- **Speaker notes — Tuesday-EOD checklist replaced with the cron** (KCS shipped `scripts/federation_preflight.py` at v4.8.4 today, 07:58 UTC, automating my entire 6-item burn-down). Run the script T-30 Wednesday and at the lectern.

Verified during this pass:

- Pod B Floor 1 heartbeat: LIVE (`anismin`, shape v1) — shipped 07:49 today.
- Pod C Floor 2 heartbeat: LIVE (`meridian`, shape v1, build_at 06:09 today) — shipped to Meridian's master.
- KCS Floor 3 heartbeat: LIVE, build `bc0f13b`.
- KCS bet round-trip: PASS via federation_preflight.py.
- target_artifact date substitution: pipeline verified, NOT hard-coded — Anismin's earlier date concern was about the deck text, not the dispatch logic.
- PR #28 (meridian-os) MERGED today 07:29 UTC.
- PR #33 (AnisminOS_Memory) still OPEN; Pod B was shipped directly to AnisminOS master rather than via that PR.

Pending fallback for worst case:

- Branch `v12-discord-fallback` staged on `agentic-economy` repo with original v10-style slide 6 (Discord-only). Hot-swap mid-day Wednesday if Pod A2 ships then breaks.

## What changed from v11 → v12 (Anismin's reply via direct chat)

Anismin's voice arrived later via FastAPI (reef was async-slow). Three structural corrections:

- **Slide 4 lobby-embed claim was a lie.** Probed the live Anismin lobby (`localhost:8643/agents/`) and found `Content-Security-Policy: frame-src 'self'` + `X-Frame-Options: SAMEORIGIN`. KCS dropped its X-Frame-Options in v4.7.8 but Anismin's CSP still blocks Floor 3 from being embedded. Replaced the iframe-embed claim with the truthful one: cross-floor seats in shared `boardroom_meetings` and `agent_mailbox` Postgres tables. Verified empirically by adding `anismin` and `kraken` as participants in Boardroom #5 — both accepted (HTTP 200, queue: `["anismin","kraken"]`).
- **Slide 6 (Mailbox Bus) CUT.** Anismin: *"Cut any pre-slide-7 vision/roadmap filler — demo carries v11, everything before it is dilution."* Slide-6 substance compressed to one sentence on Slide 5. Saves 90s.
- **Slide 7 references Pod A2 federation scoreboard explicitly** (Anismin's call): *"image flips to commissioned at ~6s with the bet ticker incrementing, lessons card fades in at 18s — that's the honest live artifact, since the Floor 3 lobby embed is CSP-blocked anyway, so lean into the scoreboard instead of pretending."*
- **Three new failure modes for pre-flight burn-down** (Anismin):
  - Clock skew PTT-end → Meridian commission-start (visible chain break)
  - Non-idempotent KCS bet open/close on Meridian retry
  - `target_artifact = memory/2026-04-29-fiskaly.md` is dated TOMORROW; today's rehearsal misses the path. Either parameterise with `$(date +%Y-%m-%d)` or accept that only Wednesday's run hits the canonical path.
- **Replaced `the-kimi-office.png` with a real screenshot of Floor 3 v4.8.0** (KCS shipped AnisminOS-parity pixel-art canvas at `:9643/office`; v4.7.7 dropped login auth so the page renders without a session). Slide 5 Floor 3 card now shows actual product, not Nano Banana art.
- **Verified Meridian DOES have `image_generate` first-class** (Gemini 3.1 flash + 3 Pro). Slide 7's image-at-6s promise is honest.
- **Slide count 12 → 11.** ~20 min content + ~10 min buffer.
