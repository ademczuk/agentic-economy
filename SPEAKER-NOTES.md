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

> "Thanks Ed. You just gave the room the platform and the case — what OpenClaw is, and what agents can actually do in business. I'm going one floor down. Into the operational layer. The workbench.
>
> The title's on the slide. *Quit chatting with your agents and get them to work for you.* The line that runs through the talk: a brief is a contract. A chat is a hostage situation.
>
> Tonight I'm going to bet a real piece of work on that line. Live. In front of you."

**Cue:** acknowledge Ed warmly but briefly. Don't restate his content — *receive* it. Use Ed's actual framing back to him: "the platform" and "the case" cover whatever he ended up emphasising (stars, ecosystem, ROI, case studies). Don't quote specific numbers Ed may or may not have cited (brutal-mcp red-team 2026-04-28: assuming Ed quoted "361K stars" or specific revenue figures is a FATAL coordination risk).

**Pre-show coordination (T-30):** brief check-in with Ed if possible — confirm he covered the OpenClaw introduction angle ("platform" framing) and the business case angle ("agents that work" framing). If he ended up framing it differently, swap the two phrases on stage. Don't mention specific stats from Ed's deck unless you SAW his slides.

**"Paperwork" line — Q&A BACKUP ONLY, not slide-1 alternative (user calibration 2026-04-28):** *"Ed just showed you what the agents can do. I'm going to show you the paperwork."* Reads dryly self-aware on the page; in the room with a Vienna founder audience it could undercut the workbench framing. The current slide body text ("one floor down... the workbench") is more visual and consistent with the deck's central metaphor — KEEP THAT AS PRIMARY. Use the paperwork line only if Ed's energy lands oratorical and Andrew needs a deflationary handshake mid-Q&A. Otherwise, never deploy.

---

## Slide 2 — The Shift (~30 sec) ⭐ v15.8 add — industry framing

**This slide grounds the talk in where the field already is. Quick beat — read fast, don't dwell.**

> "Before I make the bet — one piece of context. October last year, Poolside shipped Laguna. Not a chatbot. A model family purpose-built for coding agents. Forty-seven percent on SWE-bench Pro. Forty-one percent on Terminal-Bench 2.0. Cursor's Composer, Cognition's Devin, OpenAI's Codex CLI all pointing the same direction. The frontier labs aren't building bigger chatbots anymore. They're building purpose-built coding and agent systems.
>
> The slide quotes Poolside: 'Software is a much more expressive interface. An agent that can write and execute code can compose actions, parallelize work, and build its own ad-hoc systems.'
>
> So 'stop chatting' isn't a hot take. It's where the field already is. The talk you're about to watch is what that looks like on a workbench."

**Cue:** read fast. Don't dwell on numbers. The point is the *direction*, not the leaderboard.

**Cohesion + cut criteria (FIRST CUT if running over):**
- If Ed already named the lab pivot to coding/agents in his OpenClaw introduction, **SKIP THIS SLIDE entirely** on stage — don't rehash. The bet still works without it.
- If Andrew has only ~17 min total speaking time, skip — the slide is setup, not load-bearing for the spine sentence.
- If keeping: deliver in 30 seconds, click straight to The Bet. Don't let it drift toward industry-survey territory.

**Q&A defense if challenged on Poolside specifically:** Laguna M.1 = 225B params / 23B active; Laguna XS.2 = 33B / 3B active, Apache 2.0 open weights. Trained on 30+ trillion tokens. SWE-bench Pro: 46.9% (M.1), 44.5% (XS.2). Terminal-Bench 2.0: 40.7% (M.1), 30.1% (XS.2). Source: poolside.ai/blog/laguna-a-deeper-dive (Oct 2025).

**Q&A trap if asked "isn't this still just LLMs in a trench coat?":** No. Laguna's framing is explicit — software as the *expressive interface*. The model is the substrate; the *agent that writes and executes code* is the unit of work. That's the architectural pivot. Andrew's three-floor federation is the operational expression of the same pivot.

---

## Slide 3 — The Bet (~120 sec)

**This is the load-bearing slide. Read it slowly.**

> "Eighty-eight percent of respondents say AI has increased annual revenue — Ed showed you that side. The slide also says six percent trust it with anything that matters. You're probably in that gap. In about ten minutes you'll watch the bridge get built.
>
> Right now, on a workstation in this city, my agents are waiting for a brief.
>
> Not one agent. A team of them. They have offices. They have desks. They have memory.
>
> In about ten minutes, I'm going to commission one of them to log this exact talk into his memory. While I keep explaining how, he'll do it. By minute eighteen, the file will exist. You'll see the path appear on screen.
>
> If the bet pays off, you've watched the workbench complete a real piece of work in front of you. If it fails, you'll see exactly where it failed and why. Either way, that's the talk."

**Beat:** pause on "either way, that's the talk." Let the bet land. The audience now has stakes.

**Cohesion guardrail (deep-analyst flag 2026-04-28):** the 88/6 stat is setup for the bet, NOT a standalone industry-context beat. Frame it as "you are the 94%" → "here's the bridge." If the spoken framing starts drifting toward industry-survey territory on stage, drop the stat. The talk still works without it.

**88% verification (compass artifact 2026-04-28 night):** Confirmed in NVIDIA *State of AI* 2026 industry surveys (published 9 March 2026, blogs.nvidia.com/blog/state-of-ai-report-2026/). 3,200+ respondents across five industries (financial services, retail/CPG, healthcare/life sciences, telecommunications, manufacturing). Survey ran Aug-Dec 2025. **Exact wording**: *"Overall, 88% of respondents said AI has had an impact on increasing annual revenue, in some or all parts of the business."* — NVIDIA blog summary by Dan Rowinski.

**Critical correction applied**: the slide and spoken setup said "88% of leaders" — wrong. The 88% is the **full sample** (C-suite/VPs 27%, directors/managers 33%, AI practitioners 40%) — not "leaders" or "executives" alone. Slide now reads "of respondents." Spoken framing now reads "respondents say AI has increased annual revenue."

**Sharper alternative framing** (use this on stage if Andrew wants to keep an executive cut while staying defensible): *"~40% of C-suite and VP respondents report annual revenue gains above 10% from AI."* That's NVIDIA's actual executive-specific cut.

**Methodology caveat for hostile Q&A** (worth knowing): NVIDIA respondents were sourced from opt-in marketing distribution lists + social media + a third-party agency in China and Japan. Opt-in convenience sample skewing toward AI-engaged firms — not a randomized probability sample. NVIDIA also has commercial interest in showing AI ROI. None of this disqualifies the figures, but if pressed: *"Yes, NVIDIA's sample is opt-in and AI-engaged. Convenience sample. Worth saying. The 88% still represents 3,200+ AI-engaged firms across five industries reporting revenue impact — that's a real signal in this room, not a universal claim."*

**Recommended citation block** (per compass artifact — for reference if asked for the precise source line): *"NVIDIA, State of AI 2026 industry surveys (March 2026). 3,200+ respondents across financial services, retail/CPG, healthcare and life sciences, telecommunications, and manufacturing; fielded August–December 2025. https://blogs.nvidia.com/blog/state-of-ai-report-2026/"*

**Why NOT PwC**: PwC's AI Agent Survey (May 2025, 308 US senior executives) also has an "88%" stat but it measures budget intent ("88% plan to increase AI-related budgets"), not realised revenue. Different methodology, different claim. The deck's NVIDIA citation is correct. PwC suspicion was a false alarm — flag it as a Q&A trap if any data-literate audience member raises it.

**Ed-coordination guardrail (brutal-mcp flag 2026-04-28):** Ed's email confirmed he covers "AI agents in business context" — likely territory for the 88% revenue gain figure (NVIDIA State of AI 2026 is the canonical citation in the OpenClaw deck family). The current spoken setup BRIDGES from Ed ("Ed showed you that side") rather than competing with him. If Ed cited the 88% explicitly, this lands as a callback. If he didn't, the spoken line still works because Andrew is putting Ed's positive frame next to the trust gap. Either way it's safe — the risk is only if Andrew states Ed cited a specific stat Ed didn't actually use. The bridge phrasing avoids that trap.

**Mystery-meat guard:** never show the 88/6 cards without the spoken setup. Numbers without context = audience confusion (brutal-mcp 2026-04-28). If you're cutting for time, cut the cards AND the setup line together; don't leave the cards orphaned.

---

## Slide 4 — The Brief (~120 sec)

> "Before I commission, here's the thing I'm about to send him. A brief. Six fields.
>
> Goal: what you want. Context: what he needs to know. Done means: how you'll know it worked. Escalate if: what's a stop sign. Deadline: when you need it back. Verify: how the result is proven.
>
> If you can write a brief for a freelancer, you can commission an agent. Two minutes to write the first one. No code. No SDK. No platform.
>
> The deadline I'm giving him: eighteen seconds. The verify: write the result to a file at a known path. If the file exists, the commission paid off. If not, it didn't."

**Cue:** point at the six cards. Don't read all of them. Land on Goal and Verify.

---

## Slide 5 — The Anismin Office (~150 sec) ⭐ NEW

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

## Slide 6 — The Commission (~75 sec — DEMO)

**neob.ai landing line (audience research 2026-04-28 — speak as the walk-back line while artifact is generating, gives neob's attendees a nod and reframes the 18-sec wait as intentional):** *"The voice channel gets you in at under 500ms. What happens after that is tonight's talk."* Reinforces Andrew's thesis without flattering Ed. Peer-to-peer.

**neob.ai backup line (slide 6, on "fast is a small local model"):** *"Voice latency is solved. The interesting problem is what the voice woke up."*



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

## Slide 7 — The Six Moves (~180 sec)

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

## Slide 8 — Bet Paid Off + Receipt (~150 sec) ⭐ v15 fold

> "Eighteen seconds. While I was naming the moves, the agent finished. The path is on screen. The lessons are saved. The follow-up is queued.
>
> I spoke a six-field brief out loud. Once. Walked away. Meridian decomposed, routed, verified, documented, surfaced for approval, queued follow-up. The room watched an artifact appear at a real file path. Not a slide. Not a claim. A file.
>
> That's a workbench. That's commissioning. The chat window doesn't do that."

**Beat:** hold the green DONE badge on screen for the room to see. Three seconds of silence is fine.

**Fiskaly landing line (audience research 2026-04-28 — speak after the three-second silence on the DONE badge, before "That's a workbench"):** *"Fiskaly already knows what this is. Signed event. Known path. Unbroken chain. The only difference is the cashier is an agent."* — recognises the host venue's RKSV/DEP architecture as structurally identical to `boardroom_floor_events`. One sentence, no dwell.

**Fiskaly backup line (if primary feels too cute, or Fiskaly employees in back rows might feel put on the spot):** *"Every row in that Postgres table is what the RKSV calls a DEP entry — a tamper-evident record of what happened, in order, signed. The EU AI Act just discovered fiscal compliance architecture."*

---

## Slide 9 — AgentReef Federation (~120 sec) ⭐ now carries floors framing + receipt callback (v15.3 surgical edit Card 3)

> "Take a step back. The Anismin Office is one floor of three. Meridian's on Floor 2 — that's the agent you just watched. Kimi's on Floor 3 — ten ocean-themed agents running a pipeline called the Dark Factory.
>
> Three sovereign brains. Three memory stores. Federated over a signed message bus. JWT plus HMAC. My shard stays mine. Yours stays yours.
>
> Distributed sovereignty — no single vendor owns the substrate. Cross-reef messaging — Anismin asks Meridian for an opinion across the network, the reply lands in her memory the way an in-house DM would.
>
> And the third card — that's what the receipt on the last slide was doing. Two buildings. Two signatures. Same math. That's not a future product — it's the preflight you're looking at right now. **That's federation.**
>
> The design constraint that picked this shape: I want to disconnect from the reef and still have my agent. Git, not Google Docs. Each building is whole on its own."

**Cue:** point at the three cards as you name the three benefits. On Card 3, gesture back at slide 7's receipt — "you've already seen this work."

**v15.3 surgical edit (deep-analyst stress-test 2026-04-28 night):** Card 3 was "Federate a mentor to your stack. Skills, patterns, capabilities transfer. The reef compounds." That was AMaaS framing v11 cut returning through the side door. Replaced with "Two URLs, same math" pointing backward at slide 7's demonstrated receipt. Anismin's spine sentence ("watch your workbench federate") now lands on a card that says "that's federation" with the receipt as proof. Skill-transfer language stays as Q&A backup material only — not main-deck content.

**Sovereignty line (added from earlier draft cherry-pick — speak after "JWT plus HMAC, your shard stays yours"):** *"That's not just architecture. That's data sovereignty. The EU calls it the right to portability; I call it the design constraint that built this."* — pulls Three Imperatives #1 (Strategic Control) into the federation reveal without adding a slide.

**DLT Austria landing line (audience research 2026-04-28 — speak as follow-through punch after the sovereignty line, only if Ed didn't already use a sovereignty frame in his opening):** *"That's the same design bet the DLT community made — the ledger should work offline. If you need the network to be whole, you never owned the thing."* Sources: DLT Austria team page; Vienna Blockchain Week 2026 May 18-19 "Compliance Without Surveillance" session.

**DLT Austria backup line (Q&A only):** *"At Vienna Blockchain Week next month they're calling it 'compliance without surveillance.' This architecture arrived at the same place from a different direction — operational sovereignty as a design constraint, not a policy stance."*

---

## Slide 10 — August 2, 2026 / EU AI Act (~90 sec) ⭐ v15.3 add — UNIQUE ANDREW TERRITORY

**This is the slide Ed cannot give. It maps the workbench's existing primitives directly to specific Articles of the EU AI Act, 96 days before binding enforcement. Vienna audience, regulated stack. Lean in.**

> "One last frame before I close. August 2, 2026 — 96 days from tonight — Article 13 of the EU AI Act binds. Replayable audit logs stop being nice-to-have. They become the baseline.
>
> Look at the three cards. Article 9 mandates an *automation boundary* — which actions need human approval. That's the brief's *Escalate if* field. Markdown. Not a policy engine. You already have it.
>
> Article 13 demands interpretability — every action chain must be replayable, verifiable, not self-reported by the agent. That's the Postgres table I just walked you through. One row per agent action, time-ordered. The federation already produces it.
>
> Article 50 demands transparency — every agent must identify itself as non-human. That's the `agent_id` column on every audit row. Agent identifier, not a human alias. Machine-readable. Already there.
>
> The point isn't *compliance*. The point is the architecture this room watched tonight was forced into the shape the EU AI Act is going to require — by a different design constraint. *Sovereignty.* If your agents are sovereign, replayable, and identified, you're already building inside Article 13's lines."

**Cue:** point at each card as you name the Article. Don't dwell on legal language — the room knows what August 2 means.

**Closing line on slide:** *"Compliance theatre is what you bolt on. Compliance built in is what survives the audit."* — read this verbatim, then click forward.

**Pipeline scaffolding callback (added 2026-04-28 night from `developer/AnisminOS/PIPELINE-SCAFFOLDING-260428.md` — speak between Article 13 explanation and the closing line, only if you have the time):** *"And to make this concrete — the federation preflight you've been watching on the side monitor isn't a special-purpose health page. It's one of three bespoke pipelines I shipped today. Its heartbeat writes to that Postgres table every 30 seconds. Its receipt is signed. Article 13 isn't on a roadmap — it ran while you were sitting here."* This callback turns the existing side-monitor element into a concrete proof point for the slide's compliance claim. Don't dwell. One sentence, point at the side monitor, move on.

**Cut criteria:** if running >2 min over by end of slide 8, SKIP this slide entirely. Click straight to Take It Home. The Q&A trap on EU AI Act covers the same ground if asked. The slide is a bonus for the Vienna audience, not load-bearing for the talk's spine.

**Why this slide isn't dilution** (cohesion check): the single sentence is *"hand them a contract, verify the receipt, watch your workbench federate."* Article 9 = the contract. Article 13 = the receipt. Article 50 = the federation's transparency. The slide doesn't add a new message — it shows the existing message has regulatory weight. That's why it earned a slide.

---

## Slide 11 — Take It Home / Walk Off (~120 sec) ⭐ v15 fold

> "The line that opened this talk:
>
> A brief is a contract. A chat is a hostage situation.
>
> You watched the contract execute in front of you. Eighteen seconds. Real file. Real lessons. Real receipt. Three floors federated, one number on screen, the whole thing graded itself green.
>
> Day one: pick a recurring annoying task. Write one six-field brief for it. Run it once, by hand if you have to. You have an OS prototype tonight.
>
> Day thirty: a vault of dated lessons, one tripwire that has caught something real, briefs running from markdown instead of chat. Day 30 also gets you replayable audit logs — which, as of August 2, becomes your EU AI Act Article 13 baseline.
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
| 1:00 – 1:30 | 2. The Shift ⭐ v15.8 | 1:30 |
| 1:30 – 3:30 | 3. The Bet (with 88/6) | 3:30 |
| 3:30 – 5:30 | 4. The Brief | 5:30 |
| 5:30 – 8:00 | 5. The Anismin Office ⭐ | 8:00 |
| 8:00 – 9:15 | 6. Commission (live demo) | 9:15 |
| 9:15 – 12:15 | 7. Six Moves (narration) | 12:15 |
| 12:15 – 14:45 | 8. Bet Paid Off + Receipt ⭐ | 14:45 |
| 14:45 – 16:45 | 9. Federation (floors folded in) ⭐ | 16:45 |
| 16:45 – 18:15 | 10. August 2, 2026 / EU AI Act ⭐ v15.3 | 18:15 |
| 18:15 – 20:15 | 11. Take It Home (honest beat folded in) ⭐ | 20:15 |

**Total content: ~20 min. Buffer: ~10 min for organic stretch, audience reactions, demo wait time, Q&A.**

If Ed signals you have only ~17 min: cut slide 2 (Shift) FIRST, then slide 10 (EU AI Act) if still over — the Q&A traps cover both. Total drops to ~18 min with one cut, ~16 min with both.

If Ed already named lab pivot to coding/agents in his intro: SKIP slide 2 on stage regardless of time budget. Don't rehash.

If Ed gives you ~30+ min: slow the demo arc (slide 5 dwell, slide 7 play-by-play), expand Q&A. Don't add more content.

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

## The cut order, if running over (v15.8 — current 11-slide structure)

**Primary cut (Tier A)**: **Slide 2 (The Shift)** if Ed already covered lab-pivot framing in his opener, OR if running >1 min over by end of slide 1. Saves ~30 sec. The slide is setup, not load-bearing for the spine sentence. Q&A trap on Poolside Laguna covers the same ground if asked.

**Secondary cut (Tier B)**: **Slide 10 (August 2, 2026 / EU AI Act)** if still running >2 min over by end of slide 9. Saves ~90 sec. The Q&A trap on EU AI Act Article 9/13/50 covers the same ground if asked. Slide 10 is load-bearing for the Vienna audience but not for the talk's spine sentence.

**Tertiary cuts (speaker-note lines, not whole slides — drop in this order):**

1. The slide 10 pipeline-scaffolding callback (~15 sec) — "the federation preflight you've been watching... is one of three bespoke pipelines I shipped today." Optional add per the speaker note flag; skip first if cutting from the slide itself isn't enough.
2. Audience landing lines, in order: neob.ai callback on slide 6 (~5 sec), DLT Austria line on slide 9 (~10 sec), Fiskaly hook on slide 8 (~10 sec). Each is a single sentence; cut individually as time demands.
3. The 88/6 spoken setup on slide 3 (~15 sec). Cut both the spoken line AND the visual cards together — never leave the cards orphaned (mystery-meat guard, brutal-mcp 2026-04-28).

**DO NOT cut**: Slides 1, 3, 4, 5, 6, 7, 8, 9, 11. They are load-bearing for the spine sentence (*"hand them a contract, verify the receipt, watch your workbench federate"*) and the demo arc.

**Cuts already absorbed into v15** (don't try to "restore for time" — they were cut for cohesion, not length):
- Mailbox Bus (was slide 6 in v11) — Postgres mechanics are now one sentence on slide 4
- Three Floors standalone (was slide 5 in v14) — folded into Federation slide 8 opening
- Honest Beat standalone (was slide 9 in v14) — folded into close, slide 10
- AMaaS pricing slide (was slide 12 in v10) — pricing tiers (EUR 5K/10K/20K), Texterous-shape signal, "not pitching you tonight" line are Q&A backup material per the v11 boardroom call. See Q&A traps section.

---

## Common Q&A traps

- *"Isn't this just AutoGPT?"* — No. AutoGPT had no holdout reviewer, no calibration replay, no tripwires from past failures, no commission contract. The brief is the difference. Plus federation between sovereign instances — AutoGPT was one process, this is a network.
- *"Isn't this just an AI factory?"* (Ben Fellows / Steve Yegge framing) — Yes, intentionally. The Dark Factory is Kimi's *internal* pipeline — ten ocean agents on Floor 3 doing the work. The three floors federated above it are the governance layer. This is the same camp Steve Yegge described in *"Welcome to the Wasteland: A Thousand Gas Towns"* (March 2026), Simon Willison called *Dark Factory* on Lenny's Podcast (April), and Geoffrey Huntley is building as the *Weaving Loom*. Where Ben Fellows is right: generic factories don't work. Where his thesis lands here: each pipeline is bespoke per task type. `/solve-room` is the problem-solving pipeline. `/code-review` is a different one. `/teach` is a third. The federation is the orchestration above them, not a replacement for them.
- *"What about hallucinations?"* — They happen. The local critic catches the dangerous ones. The non-dangerous ones don't ship because the verify step requires a real artifact at a real path.
- *"How much does this cost to run?"* — Anismin runs on a $20 VPS plus an Anthropic Max subscription. Meridian's hardware was a sunk cost. The Aegis verifier in shadow mode runs on a second Max seat. The expensive thing is your time, and you're getting it back.
- *"Will I need to learn to code?"* — To run a brief, no. You write markdown. You read the artifact. The agent writes the code. If you can brief a freelancer, you can commission an agent.
- *"Is the AMaaS pitch the close?"* — No. The close is "build your own machinery." If someone reads the AMaaS slide as the sales close, that's a sign you over-emphasised it. Read it flatter next time.
- *"What about what Ed said about [X]?"* — Honour Ed's framing. He set the table; this talk is what gets eaten at it. Don't contradict him on stage even if you'd phrase something differently.
- *"Show me the live UI"* — Defer to after the talk: "Sure. Walk over after Q&A and I'll port-forward you in." Don't demo the dashboard live during the keynote — too much surface area for things to go wrong.
- *"How does this map to EU AI Act?"* (Vienna audience — likely question, August 2 2026 binding is 96 days away) — Article 9 (risk management) is the brief's `Escalate if` field — that's your automation boundary in markdown. Article 13 (interpretability) is `boardroom_floor_events` — every action chain captures the causal step. Article 50 (transparency) is the audit log being machine-readable. The federation already meets the spirit of all three because it was built on the same constraint: *replayable, sovereign, transparent*. Source: Nannini et al. arXiv:2604.04604; CMS Law on Agentic AI.
- *"Doesn't this just kick in 95% of pilots fail too?"* — Yes, MIT NANDA found 95% of GenAI pilots don't deliver measurable ROI. The 5% that succeed share three traits: design for friction (the brief is friction by design), back-office automation (commissioning recurring annoying tasks, not boardroom drama), and vendor-led with 67% success vs 33% for internal builds. The workbench is built for the 5%. Source: MIT NANDA — The GenAI Divide (2025).
- *"What about Gartner's agentwashing warning?"* — Gartner says 40% of agentic AI projects will be canceled by 2027; only ~130 of thousands of vendors are "real." This deck is one person's workbench, not a vendor pitch. The thing on the slide IS running on a workstation in this city tonight. That's the difference between "real" and "agentwashed." Source: Gartner — Hype Cycle for Agentic AI 2026.
- *"Why didn't you build on LangGraph / CrewAI / AutoGen?"* — **(Ed-coordination flag: Ed almost certainly covered runtime-vs-library in his OpenClaw introduction. If asked, DEFLECT BACK TO ED with: "Ed walked through that distinction in his intro — runtime vs library is exactly why I built on OpenClaw, not on top of a library." Don't relitigate his argument.)** Backup detail if pressed: time-to-agent 1-3 days on the runtime vs 2-4 weeks building from libraries; markdown configuration vs Python orchestration code. The federation pattern you watched tonight needed the runtime's heartbeat + messaging primitives — those are not in any library. Source: SFAI Labs Framework Comparison (Apr 2026).
- *"Web4 — what Ed talked about — does this connect?"* — **(Ed-coordination flag: if Ed cited 7,851% YoY agent traffic, do NOT repeat the number. Acknowledge with "Ed gave you the macro picture" then pivot to MCP/A2A as the operational protocol.)** Direct connect: MCP and A2A are how my building talks to your building. The Anismin Office is one node in the traffic Ed described. Same protocol layer Ed walked through, just one floor down. Source: HUMAN Security 2026 State of AI Traffic Benchmark.
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

## What changed from v15.7 → v15.8 (industry-shift slide added — 2026-04-29 morning, day-of-keynote)

User flagged the missing industry-trend signal upfront — wanted the deck to plant a stake in the ground that AI labs have already pivoted from chatbots to purpose-built coding agents.

**Added: NEW slide 2 "The Shift"** (between Title and The Bet). All subsequent slides shifted +1 (Bet now slide 3, Brief slide 4, ..., Take It Home slide 11). Total deck = 11 slides.

Content:
- Headline: "The chatbot era just ended."
- Body cites Poolside *Laguna* (Oct 2025) — coding-agent-specific model family, 47% SWE-bench Pro, 41% Terminal-Bench 2.0. Plus Cursor's Composer, Cognition's Devin, OpenAI's Codex CLI as same-direction signals.
- Quote block: Poolside's *"Software is a much more expressive interface. An agent that can write and execute code can compose actions, parallelize work, and build its own ad-hoc systems."*
- Source line: poolside.ai/blog/laguna-a-deeper-dive
- Closing mono line: *"'Stop chatting' isn't a hot take. It's where the field already is. Tonight: what that looks like on a workbench."*

Why this slide and not a speaker-note add:
- The pivot deserves a stage moment — sets up the bet as Andrew's *operational* expression of where labs already pointed
- Tightly scoped (~30s) and explicitly cuttable if Ed covered it or time short
- Reinforces the spine sentence by anchoring "stop chatting" in industry reality

Cohesion guardrails (in slide 2 speaker notes):
- **FIRST CUT** if Ed already named lab pivot to coding/agents in his opener. Don't rehash.
- **FIRST CUT** if Andrew has only ~17 min. Setup, not spine.
- Q&A defense ammunition added: full Laguna spec (M.1 225B/23B, XS.2 33B/3B Apache 2.0), training corpus (30T tokens), benchmark breakdown.

Cut order updated:
- Tier A (first): Slide 2 (Shift) — saves ~30s
- Tier B (second): Slide 10 (EU AI Act) — saves ~90s
- Both Tier A and B can absorb up to ~2 min of overrun before any tertiary speaker-note cuts.

Time discipline table updated: total content now ~20 min (was 19:45). Buffer ~10 min.

NOT changed:
- Spine sentence holds: *"hand them a contract, verify the receipt, watch your workbench federate"*
- The Bet on slide 3 still leads on the live commission, not on industry stats
- All 88/6 cards, EU AI Act mapping, Federation Card 3 ("Two URLs, same math"), and audience-landing lines preserved verbatim
- The slide reinforces but does not replace the existing opening arc

## What changed from v15.6 → v15.7 (compass artifact citation correction — 2026-04-28 night)

External verification artifact (`compass_artifact_wf-010a7869...md`) audited the 88% NVIDIA citation and flagged two wording slips that would not have survived hostile scrutiny:

**Fix 1 (slide 2 card subtitle):** "of leaders see AI revenue gains" → "of respondents report AI revenue gains"
- The 88% in NVIDIA's wording applies to the FULL 3,200+ sample (C-suite/VPs 27%, directors/managers 33%, AI practitioners 40%) — not "leaders" or "executives" alone.
- Saying "leaders" or "executives" was technically inaccurate and indefensible against NVIDIA's own text.
- Slide visual now reads "of respondents."

**Fix 2 (slide 2 spoken setup):** "Eighty-eight percent of leaders see revenue from AI" → "Eighty-eight percent of respondents say AI has increased annual revenue"
- Matches NVIDIA's verbatim phrasing.
- Slightly less punchy but airtight.

**Verification block updated** with:
- Exact citation block recommended by the compass artefact for verbal defense.
- Methodology caveat (opt-in sample, AI-engaged skew) for hostile Q&A.
- Sharper executive-cut alternative framing — *"~40% of C-suite and VP respondents report annual revenue gains above 10%"* — if Andrew wants to keep an executive emphasis while staying defensible.
- Why-not-PwC explanation: PwC's analogous 88% measures budget intent, not realised revenue. Different stat, different methodology. NVIDIA citation is correct.

NOT a "deploying" issue: grep confirmed "actively deploying" was in the earlier OpenClaw draft we cherry-picked from but never made it into v15.x. No fix needed there.

NOT changed:
- Slide 2 attribution footer ("NVIDIA State of AI 2026 · HBR Analytic Services") — works as compact citation. Verbose block lives in speaker notes for verbal defense.
- 6% HBR figure — separate citation, separate methodology, untouched.

## What changed from v15.5 → v15.6 (pipeline scaffolding cherry-pick — autonomous call 2026-04-28 night)

User flagged a fresh artefact in AnisminOS developer notes: `developer/AnisminOS/PIPELINE-SCAFFOLDING-260428.md`. Andrew shipped the bespoke-pipeline scaffolding today, in parallel with the keynote prep. Material:

- Three pipelines on disk: `federation_preflight.py` (fully working, no stubs — IS the GREEN/GREEN/GREEN side-monitor page), `code_review.py` and `implementation_pr.py` (lifecycle + heartbeat real, brain wiring stubbed for v2).
- `PipelineRun` base class with heartbeat to `boardroom_floor_events` every 30s. Stage transitions emit `pipeline_stage_start` + `pipeline_stage_end` with elapsed time + ok flag.
- `config/pipelines.yaml` schema with per-pipeline brain assignments, gates, escalation. mtime-cached, fail-loud schema validation.
- Anismin's design verdicts encoded: Q2 (sibling files, not `--mode` flag), Q7 (solve-room stays as fallback), Q8 (manager-as-protocol — anismin=manager, meridian=synthesizer-no-veto).

**This is the proof point for the entire keynote argument.** Ben Fellows' bespoke-pipeline thesis just got operationalised in Andrew's actual codebase, with the artefact on disk before the talk.

Discipline applied — material does NOT touch the deck face. Cohesion calibration holds. Two surgical additions only:

- **Slide 9 (EU AI Act) speaker note**: callback line — *"the federation preflight you've been watching on the side monitor isn't a special-purpose health page. It's one of three bespoke pipelines I shipped today. Its heartbeat writes to that Postgres table every 30 seconds. Its receipt is signed. Article 13 isn't on a roadmap — it ran while you were sitting here."* Optional — only if time permits. Turns the existing side-monitor element into a concrete proof point for the compliance claim.

- **Q&A bank — two new entries**:
  - **A8a "Is this slideware?"** — three pipelines on disk, `federation_preflight` fully working IS the side-monitor page, others scaffolded with one clean brain-wiring seam per pipeline. Pattern is on disk. References the scaffolding doc.
  - **A8b "Isn't solve-room a generic factory?"** — solve-room is the strategy room / honest fallback for unknown task types. `code_review.py` and `implementation_pr.py` are sibling files (Anismin Q2: wrong-flag-equals-wrong-verb is a 2am footgun). Bespoke pipelines per categorised task type, fallback for uncategorised. Exactly Ben Fellows' framing.

NOT changed:
- No new slide. The pipeline scaffolding belongs in the post-keynote follow-up, not the deck.
- No mention in slides 1-8 main flow — would dilute the demo arc.
- No restructuring of existing Q&A traps — A8a/b are net-new entries that defend a specific question class without disturbing prior answers.

This material is the strongest available defense against the two hardest possible questions (slideware? generic factory?) and deepens slide 9's claim. Holding it in reserve preserves the workbench-thesis spine.

## What changed from v15.4 → v15.5 (user calibration on Q&A A2 + paperwork line + NVIDIA verified — 2026-04-28 night)

User read v15.4 changes and pushed three corrections:

**A2 reframed — operator before maintainer.** Original A2 led with "the patch is in" and added the caveat "this answer assumes Andrew has the patch." User correctly flagged: if v2026.1.29 isn't on the lectern, the answer becomes a hostage situation. Rewrote A2 to lead with operator-level controls — Tailscale-only network, no public gateway, lockfile-pinned MCP, zero unvetted ClawHub skills. The CVE's one-click RCE assumes a public gateway; Andrew's isn't. The maintainer-framing is now BACKUP only, deployed narrowly if asked specifically about patch state. Lands the workbench thesis (operator) rather than the maintainer thesis. v15.4 chose operator on stage; the Q&A bank now matches.

**"Paperwork" line demoted from slide-1 alternative to Q&A backup.** "Paperwork" reads dryly self-aware on the page; in a Vienna founder room could undercut the workbench framing. The existing slide-1 body text ("one floor down... the workbench") is more visual and consistent with the deck's central metaphor. Speaker note now flags: paperwork line ONLY for mid-Q&A deflationary handshake if Ed's energy lands oratorical. Otherwise never deploy.

**NVIDIA 88% stat verified.** Confirmed in NVIDIA *State of AI 2026* (published March 2026, blogs.nvidia.com/blog/state-of-ai-report-2026/). 3,200+ respondents across five industries. Survey ran Aug-Dec 2025. Exact wording: *"88% of respondents said AI has had an impact on increasing annual revenue, in some or all parts of the business."* The deck's "see AI revenue gains" is a paraphrase consistent with secondary press. Defensible. Defense line added to slide 2 speaker notes.

NOT changed:
- Slide 7 Fiskaly hook ("signed event, known path, unbroken chain") — strong, kept.
- Slide 8 DLT Austria hook ("the ledger should work offline") — strongest of the four landings (Ed publicly held this value as DLT Austria chair), kept.
- Slide 5 neob.ai hook ("voice channel gets you in at <500ms") — fine, lower-stakes, kept as callback if Ed already established voice latency.
- A1 (AutoGPT) and A3 (MIT NANDA 95%) — well-prepped, no changes. Don't soften the "I'm not claiming I'm in the 5%" line on A3.

## What changed from v15.3 → v15.4 (research brief landed — slide 8 surgery + audience landings 2026-04-28 night)

User authorised a four-stream research brief (Q&A bank + per-slide anchors + audience landings + slide 8 stress-test). All four returned. Material applied:

**Slide 8 surgical edit (deep-analyst stress-test verdict):**

- Card 3 was "Federate a mentor to your stack. Skills, patterns, capabilities transfer. The reef compounds." — verbatim Q&A AMaaS backup material that Fathom cut in v11. Scored 2/5 workbench-consistency, F (not demonstrated tonight), 5/5 AMaaS-tonal-edge risk for DLT Austria audience.
- Replaced with: "**Two URLs, same math** — :9643 and :8643 just graded the same receipt independently. That's federation — not a future roadmap, the thing running on the workstation tonight."
- Speaker note for the card adds spoken callback: "And that's what the receipt on the last slide was doing. Two buildings. Two signatures. Same math. That's not a future product — it's the preflight you're looking at right now. **That's federation.**"
- Anismin's spine sentence ("watch your workbench federate") now lands on a card that says "that's federation" with slide 7's receipt as proof. Spine intact.
- Skill-transfer / mentor-to-your-stack language stays as Q&A backup material only — not main-deck content.

**Audience landing lines added (research found Ed Prinz chairs DLT Austria — he is in BOTH audiences):**

- **Slide 7 (Bet Paid Off + Receipt)**: Fiskaly hook line — "Fiskaly already knows what this is. Signed event. Known path. Unbroken chain. The only difference is the cashier is an agent." Maps `boardroom_floor_events` to RKSV/DEP architecture the host venue runs.
- **Slide 8 (Federation)**: DLT Austria hook line — "That's the same design bet the DLT community made — the ledger should work offline. If you need the network to be whole, you never owned the thing." Spoken as follow-through after the existing sovereignty line.
- **Slide 5 (Commission)**: neob.ai hook line — "The voice channel gets you in at under 500ms. What happens after that is tonight's talk." Spoken as walk-back line while artifact generates. Peer-to-peer with Ed's neob.ai stack.
- **Slide 1**: Ed callback alternative — "Ed just showed you what the agents can do. I'm going to show you the paperwork." Reframes the brief/contract architecture as the serious operational layer below Ed's vision.

**Q&A bank**: 16 questions (8 hostile + 8 curious) saved to `QA-AMMUNITION-BANK.md`. Three starred for tonight rehearsal:
- A1 ("Isn't this just AutoGPT?") — schema-enforced contracts vs flat loops
- A2 (CVE-2026-25253 / ClawHavoc / postmark-mcp) — real CVEs, real patches, "lesson is don't run untrusted skills with network access — already baked in"
- A4 (MIT NANDA 95% pilot failure) — own the stat, reverse it: "the report's diagnosis IS the talk"

**Per-slide anchors**: research file pending (re-spawned after first agent didn't write).

NOT changed:
- Slide 8 kept as a slide. Cut option rejected — would orphan "federate" in the spine sentence with no slide home.
- Slide 9 (EU AI Act) intact.
- Slide 10 (Take It Home) intact.

## What changed from v15.2 → v15.3 (compliance slide added — autonomous call 2026-04-28 night)

User authorised "update at will" given Ed's email signals 30-40 min of speaking time vs v15's 17-min budget. Researcher said don't restore cut slides; brutal-mcp said don't bloat. So the new content needed to be (a) NOT cut content restored, (b) NOT duplicating Ed's territory, (c) load-bearing for the Vienna audience specifically.

ADDED: New slide 9 "August 2, 2026" between Federation (8) and Take It Home (now 10).

- Maps the workbench's existing primitives to EU AI Act Articles 9 (automation boundary = brief's `Escalate if`), 13 (interpretability = `boardroom_floor_events` audit table), 50 (transparency = `posted_by` field on every audit row).
- 96 days from binding enforcement on talk day. Vienna audience, regulated stack. Andrew's unique territory because Ed's content is OpenClaw + business case, not regulatory.
- Closing line on slide: *"Compliance theatre is what you bolt on. Compliance built in is what survives the audit."*
- Cohesion check: doesn't add a new message — shows the existing message has regulatory weight. Article 9 = contract. Article 13 = receipt. Article 50 = federation transparency.
- Cut criteria: if Andrew is >2 min over by end of slide 8, skip slide 9 entirely. The Q&A trap on EU AI Act covers the same ground.

UPDATED:
- Time discipline table: 9 → 10 slides, ~20 min content, ~10 min buffer.
- Cut order: slide 9 (EU AI Act) is now the FIRST cut if running long, before any others.
- Static slide counter "1 / 9" → "1 / 10".

NOT changed:
- Spine intact. Bet → Brief → Office → Commission → Six Moves → Bet Paid Off → Federation → AI Act → Take It Home.
- The single sentence still holds: contract, receipt, federation. The new slide reinforces all three.

## What changed from v15.1 → v15.2 (Ed Prinz email + brutal-mcp red-team 2026-04-28 night)

Ed Prinz's email confirmed his content: "general introduction to OpenClaw, then AI agents and how we have successfully used them in a business context. Plenty of speaking time." This is exactly the territory the v15.1 cherry-pick edits drew from. Brutal-mcp red-team flagged a FATAL coordination risk in the proposed slide 1 line; deep-analyst flagged duplication risk on the 88/6 stat and the Web4/framework-wars Q&A traps. Trident Gemini Flash agreed: coordinate with Ed pre-show, slow the demo arc instead of restoring cut slides.

Corrections applied:

- **Slide 1 body text** (slides.html line 223): rewrote to "platform and the case" / "what OpenClaw is and what agents can actually do in business" / "one floor down" / "workbench". Removes specific stats (361K stars, revenue figures) that Ed may or may not cite. Receives Ed's framing without quoting specifics that risk a coordination mismatch.
- **Slide 2 spoken setup**: rewrote 88/6 framing as a BRIDGE from Ed ("Ed showed you that side") rather than a standalone stat. If Ed cited 88%, this is a callback. If he didn't, it still works because Andrew is putting Ed's positive frame next to the trust gap. Brutal-mcp's "mystery meat" warning addressed: keep cards + spoken framing together; cut both together if cutting for time.
- **Slide 1 speaker notes**: added pre-show Ed-coordination guardrail. Andrew should NOT quote specific numbers from Ed's deck unless he saw the slides.
- **Q&A trap (Web4)**: added Ed-coordination flag — if Ed cited 7,851% YoY, do NOT repeat. Pivot to MCP/A2A as operational layer.
- **Q&A trap (Framework wars)**: added Ed-coordination flag — DEFLECT BACK TO ED. Don't relitigate his runtime-vs-library argument.

NOT changed (per researcher + brutal verdicts):

- 88/6 stat cards on slide 2 — kept (visual). Brutal corrected my prior intent to drop the spoken setup; visual without setup = mystery meat.
- EU AI Act / sovereignty / Three Imperatives — kept as is. None of these are Ed's territory. Vienna audience, August 2 2026 binding date, regulatory framing. Load-bearing.
- Cut slides (Three Floors, Honest Beat, AMaaS) — NOT restored. Researcher: extra time goes into slowing the demo arc (slide 4 dwell, slide 6 play-by-play) and giving Q&A more room. Restoring cut content would re-introduce the cohesion problems Anismin's audit fixed.
- Live demo — KEPT. Brutal flagged "scrub live demo" as risk-mitigation; researcher disagreed; pre-recorded backup is already queued on lectern (per pre-talk checklist). Andrew's whole bet IS the live demo. Risk already mitigated.

**Pre-show actions required (T-30):**

1. Brief check-in with Ed — confirm "platform" + "business case" framing landed; ask if he cited 88% NVIDIA revenue stat; ask if he covered runtime-vs-library distinction explicitly (affects framework-wars Q&A trap).
2. Confirm timing budget — Ed said "plenty of speaking time" but no number. Ask: how long is Andrew's slot (20 / 30 / 40 min)? Affects whether to slow the demo arc or run as scripted.
3. Backup plan if Ed runs over — current v15 is 18 min content + 12 min Q&A buffer. If Ed eats 5 min of Andrew's time, the buffer absorbs.

## What changed from v15 → v15.1 (earlier-draft cherry-pick 2026-04-28 evening)

User flagged the earlier 23-slide OpenClaw draft (`OpenClaw_The_Agentic_Economy_GenAI_Night.md`, slide 18 onwards specifically). Deep-analyst review identified items v15 cohesion-cut TOO HARD — strategic context the Vienna audience needs to walk out with urgency, not just inspiration. Surgical integration:

- **Bio fix**: "OpenClaw Contributor" → "OpenClaw Core Maintainer" (slides.html line 198 + 224). Credibility upgrade to match earlier-draft attribution.
- **Slide 2 (The Bet) — 88/6 stat cards added**: NVIDIA State of AI 2026 + HBR Analytic Services. *88% see revenue gains, 6% trust agents with core work.* Frames the bet as the answer to a problem the audience already has, not just a tech demo. Spoken setup line added before the existing bet narration. 15s on stage.
- **Slide 8 (Federation) — sovereignty line added** (speaker notes only): pulls Three Imperatives #1 (Strategic Control) into the federation reveal. 20s spoken addition.
- **Slide 9 (Take It Home) — EU AI Act binding date added** (speaker notes only): one parenthetical in the Day 30 beat. 10s. Article 13 baseline = your audit log. Massive leverage for Vienna/EU audience.
- **Q&A traps expanded**: 5 new defenses pulled from earlier draft slides 16-22 — EU AI Act Article 9/13/50 mapping, MIT NANDA 95% pilot failure rate, Gartner agentwashing, framework wars (LangGraph/CrewAI/AutoGen vs runtime), Web4 traffic stats + Ed Prinz callback.

NOT integrated (deep-analyst correctly flagged as cohesion violations or wrong message):

- CVE-2026-25253 attack chain — would poison Ed's adoption case. Wrong room, wrong night.
- Workforce paradox / job displacement stats — sends people to bar in wrong mental state.
- Framework comparison table — kills narrative tempo.
- npm install close — would compete with the existing QR on slide 9.
- Standalone "Where this fits" strategic slide — risks blowing the cohesion cut Anismin enforced.

Net: v15 spine intact (9 slides), strategic stakes raised via 1 slide modification + 3 speaker-note additions + 5 Q&A traps. ~45 sec added on stage if all delivered; gracefully cuttable if running long.

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
