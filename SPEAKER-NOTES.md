# Speaker Notes — Quit chatting with your agents (v10 / Building Edition)

**Talk:** Quit chatting with your agents and get them to work for you
**Event:** OpenClaw × neob.ai · Agentic Economy Night · Fiskaly Wien
**Date:** Wednesday 29 April 2026
**Slot:** Keynote, second speaker. Ed Prinz opens with OpenClaw introduction + business AI context. Andrew follows as the keynote. Possibly a third 10-min closer after Andrew.
**Length target:** ~25 min content + ~5 min organic stretch / Q&A buffer = 30 min

The talk is one story: *I have a building. Three floors. Real agents at real desks. Watch me commission one of them to log this exact talk into memory, in front of you, in 18 seconds. Now multiply: my building can talk to yours — and that's the line of business hiding in this room.* Everything else hangs off the bet and the building.

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
- [ ] AV tech briefing: *"At slide 7 I'll speak into my phone for ~10 seconds. About 12 seconds later, a file path appears in Discord text on the screen. About 18 seconds later, audio comes back. The Discord text channel needs to be visible the whole time."*
- [ ] Water on the lectern.

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

**Backup if anyone challenges it:** "Yes I can pull up the live UI right now. It's running. I'll show you after." Don't promise to do it on stage; reserve that for Q&A.

---

## Slide 5 — One Building, Three Floors (~120 sec) ⭐ NEW

> "Floor one is Anismin. Atlanta. Claude Opus 4.7 brain. 1,057 memories. Conversational orchestrator.
>
> Floor two is Meridian. Vienna. Codex 5.4 plus a local critic that doesn't care about my feelings. He's got his own team — Glacier, Current, Fathom, Sentry. Twenty-one apps. A voice pipeline. The agent you're about to watch take the commission.
>
> Floor three is Kimi. Ten ocean-themed C-suite agents. Kraken, Leviathan, Abyss, Marlin, Manta, Eel, Coral, Jelly, Siren, Trench. They run a pipeline called the Dark Factory. Briefs in. Merged pull requests out. Humanless.
>
> Three brains. Three memory stores. Three sets of agents.
>
> And the load-bearing design choice: each floor is a sovereign. Its own database. Its own files. Disconnect any one of them from the others and it stays whole. That's not Google Docs. That's git. I want my own shard so that if the network goes away, my agent is still there."

**Cue:** point at each floor card in turn as you name it. The pixel-art images do most of the work.

---

## Slide 6 — Mailbox Bus (~90 sec) ⭐ NEW

> "Three floors. How do they talk to each other?
>
> A Postgres table called `agent_mailbox`. Typed messages. Five kinds — request, result, blocker, ack, broadcast. Plus lesson candidates for the memory pipeline.
>
> A host-side dispatcher polls it every fifteen seconds. Claims pending rows with `SELECT FOR UPDATE SKIP LOCKED` — the Postgres trick that lets multiple workers race the queue without stepping on each other. Five-minute lease per claim. If a worker dies mid-job, a reaper releases the lease and someone else picks it up. After five failures, dead-letter.
>
> Five surfaces to put a task in: the mailbox UI, a CLI script called `delegate.sh`, a spoken trigger phrase Anismin recognises, the `/meridian-loop` slash skill, or a direct POST.
>
> That's it. That's the whole inter-floor protocol. It's small enough to fit on this slide."

**Cue:** the audience may glaze on Postgres terminology. Land on "five surfaces to put a task in" and the lease-and-reaper. Don't go deeper.

---

## Slide 7 — The Commission (~75 sec — DEMO)

**ACTION SEQUENCE:**

1. Confirm Discord text channel is visible on projector
2. Press push-to-talk on phone
3. Speak slowly:
   *"Meridian, log tonight's talk in your memory. Event: OpenClaw Agentic Economy Night, Fiskaly Wien, 29 April 2026. Goal: extract three reusable lessons. Save to your dated lessons folder, post the file path in Discord, confirm by voice when done."*
4. Release PTT. Walk back to slides. Click forward to slide 8.

**While walking back:**
> "He has the brief. The clock starts. Let me name what's about to happen, in order, while it happens."

**Backup if voice fails at PTT:** *"Voice is offline, GPU is busy with a critic job. I'll DM the same brief instead. The pattern still runs."* Type the brief in Discord. Continue.

---

## Slide 8 — The Six Moves (~180 sec)

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

## Slide 9 — Bet Paid Off (~90 sec)

> "Eighteen seconds. While I was naming the moves, the agent finished. The path is on screen. The lessons are saved. The follow-up is queued.
>
> I spoke a six-field brief out loud. Once. Walked away. Meridian decomposed, routed, verified, documented, surfaced for approval, queued follow-up. The room watched an artifact appear at a real file path. Not a slide. Not a claim. A file.
>
> That's a workbench. That's commissioning. The chat window doesn't do that."

**Beat:** hold the green DONE badge on screen for the room to see. Three seconds of silence is fine.

---

## Slide 10 — The Honest Beat (~75 sec)

> "Before you start, one uncomfortable truth.
>
> The first two weeks of doing this feel slower than your old workflow. Not faster. Slower. You're learning to write a brief instead of typing into a chat. You're learning to wait for an artifact instead of reading a stream of tokens. You're learning to approve judgment, not typos.
>
> If I don't say that out loud, the serious people in this room will discover it alone in week one and trust me less. So: it's slower at first. By week three it's not. By week eight you can't go back."

**Beat:** "trust me less" is the credibility moment. Pause on it.

---

## Slide 11 — AgentReef Federation (~120 sec) ⭐ NEW

> "So far I've shown you my building. Three floors. One operator. That's a workbench for one person.
>
> The next thing it becomes: my building can talk to yours.
>
> AgentReef Federation is the protocol that lets sovereign buildings exchange messages. Same mailbox shape. JWT plus HMAC over the wire. Your shard stays yours. My shard stays mine. We trade structured asks. Anismin can DM Meridian across the network and get a real reply, and the reply lands in her memory the same way an in-house DM would.
>
> The design constraint that picked this shape: I want to be able to disconnect from the reef and still have my agent. Git, not Google Docs. Each building is a complete instance. Federation is what they do over the wire when they're connected.
>
> What does this buy you? Three things.
>
> One: distributed sovereignty. No single vendor owns the substrate.
> Two: cross-reef messaging. An agent that needs an opinion you don't have on staff can ask one that does, on demand.
> Three: skill transfer. When Anismin learns a new pattern mentoring one client's stack, that pattern can travel — anonymised — to the next. The reef compounds."

**Cue:** point at the three cards as you name the three benefits. The federation art is doing the metaphor work; let it.

---

## Slide 12 — What This Means For You (~130 sec) ⭐ NEW

**This is the sales-adjacent slide. Read it without selling.**

> "I want to land somewhere specific for this room.
>
> Half the people in this audience ship AI products to clients. And half of you watch those products slowly drift behind state-of-the-art, because your engineering team is bogged down in client delivery sprints. You don't have the time to ship continuous improvement to the AI layer of your own product.
>
> There's a federation play here. Connect a mentor agent — one of mine, or one you build — to your client's product over AgentReef. The mentor watches. The mentor teaches. Skills, patterns, capabilities transfer monthly. That's a subscription line of business, not a heroic engineer.
>
> The pricing on the slide is what we're testing. Five thousand a month for skill transfers and quarterly reviews. Ten for continuous federation with SLAs and monthly novel skill releases. Twenty for a dedicated mentor instance, white-label, IP co-ownership.
>
> The first signal we have for this is a Vienna AI consultancy whose ERP product is exactly the shape I just described — sixteen people, one product, the team is on client work, the product is drifting. They asked us to meet.
>
> If your shape rhymes — find me at the bar. I'm not pitching you tonight. I'm telling you the line of business is hiding in plain sight in this room, and I think a few of you are sitting on it."

**Beat:** "I'm not pitching you tonight" is the credibility line. Mean it. Hold the room's gaze.

**If the room reads sales-pitchy on this slide, the cure is to slow down on the line "I'm not pitching you tonight" and not on the price tiers.** The price tiers are honest, not the centre.

---

## Slide 13 — Take It Home / Walk Off (~120 sec)

> "The line that opened this talk:
>
> A brief is a contract. A chat is a hostage situation.
>
> You watched the contract execute in front of you. Eighteen seconds. Real file. Real lessons. Real follow-up. Three floors of agents you saw on screen, plus the federation that lets them talk to other people's agents.
>
> Day one: pick a recurring annoying task. Write one six-field brief for it. Run it once, by hand if you have to. You have an OS prototype tonight.
>
> Day thirty: a vault of dated lessons, one tripwire that has caught something real, briefs running from markdown instead of chat.
>
> Day ninety: routing across two or more brains, one or two agents you trust, you're commissioning daily.
>
> Nobody needs to be at Day 90 next week. Just don't be at Day 0 next month.
>
> Build the machinery. Not be the person doing every task faster. Build the machinery that lets good tasks get done reliably, cheaply, with accountability. Ed showed you the case. I just showed you the workbench. Now you build yours.
>
> The deck is at the QR. Photograph it now. Find me at the bar.
>
> Stop chatting. Start commissioning."

**Beat:** end on "start commissioning". Three seconds of silence. Walk off, or take Q&A from the floor.

---

## Time discipline

| Slot | Slide | Cumulative |
|---|---|---|
| 0:00 – 1:00 | 1. Title | 1:00 |
| 1:00 – 3:00 | 2. The Bet | 3:00 |
| 3:00 – 5:00 | 3. The Brief | 5:00 |
| 5:00 – 7:30 | 4. The Anismin Office ⭐ | 7:30 |
| 7:30 – 9:30 | 5. Three Floors ⭐ | 9:30 |
| 9:30 – 11:00 | 6. Mailbox Bus ⭐ | 11:00 |
| 11:00 – 12:15 | 7. Commission (live demo) | 12:15 |
| 12:15 – 15:15 | 8. Six Moves (narration) | 15:15 |
| 15:15 – 16:45 | 9. Bet Paid Off | 16:45 |
| 16:45 – 18:00 | 10. Honest Beat | 18:00 |
| 18:00 – 20:00 | 11. AgentReef ⭐ | 20:00 |
| 20:00 – 22:10 | 12. AMaaS for the room ⭐ | 22:10 |
| 22:10 – 24:10 | 13. Take It Home / Walk Off | 24:10 |

**Total content: ~24 min. Buffer: ~6 min for organic stretch, audience reactions, demo wait time, Q&A.**

The 18-min demo arc still anchors the middle. If the demo overshoots by 30-60 seconds, the slack from slides 11+12 absorbs it. If it lands clean, you have room for one or two questions before the bar.

---

## What to do if the demo runs long

- The artifact should be visible by the end of slide 8. If it isn't, click forward to slide 9 anyway. The "DONE" framing on slide 9 still works as a verbal claim — when the artifact does appear (slide 10 or later), gesture and acknowledge: *"There it is. Took longer than usual. That's venue Wi-Fi."*
- If voice never replies but text posts: same flow. Slide 9 is about the file existing, not the voice.
- If both fail: the line is *"Voice is offline. The honest version of always-on, exactly what slide 10 will warn. If it breaks, you see it break. That's the talk too."* Click forward. Do not retry. Do not apologise.

---

## What to do if the demo runs short

- If the artifact appears on slide 7 (during the commission speech): perfect. Acknowledge: *"That fast. He didn't even let me finish the explanation."* Click through slide 8 quickly, dwelling only on moves 4-6 (the parts the audience didn't see directly).
- If you finish all 13 slides in 22 minutes: stop. Take questions. Walk off at 28.

---

## The cut order, if running over

1. **Cut slide 12 (AMaaS)**. Skip the sales-adjacent slide entirely. The keynote still closes on slide 13 — the line of business gets mentioned only at the bar.
2. **Cut slide 6 (Mailbox Bus)**. The Postgres detail is the most cuttable architecture beat. The two office slides (4, 5) carry the visual weight.
3. **Cut slide 10 (Honest Beat)** as last resort. Costs credibility but saves 75 seconds.

Do NOT cut slides 4, 5, 7, 8, 9, 11. They are load-bearing.

---

## Common Q&A traps

- *"Isn't this just AutoGPT?"* — No. AutoGPT had no holdout reviewer, no calibration replay, no tripwires from past failures, no commission contract. The brief is the difference. Plus federation between sovereign instances — AutoGPT was one process, this is a network.
- *"What about hallucinations?"* — They happen. The local critic catches the dangerous ones. The non-dangerous ones don't ship because the verify step requires a real artifact at a real path.
- *"How much does this cost to run?"* — Anismin runs on a $20 VPS plus an Anthropic Max subscription. Meridian's hardware was a sunk cost. The Aegis verifier in shadow mode runs on a second Max seat. The expensive thing is your time, and you're getting it back.
- *"Will I need to learn to code?"* — To run a brief, no. You write markdown. You read the artifact. The agent writes the code. If you can brief a freelancer, you can commission an agent.
- *"Is the AMaaS pitch the close?"* — No. The close is "build your own machinery." If someone reads the AMaaS slide as the sales close, that's a sign you over-emphasised it. Read it flatter next time.
- *"What about what Ed said about [X]?"* — Honour Ed's framing. He set the table; this talk is what gets eaten at it. Don't contradict him on stage even if you'd phrase something differently.
- *"Show me the live UI"* — Defer to after the talk: "Sure. Walk over after Q&A and I'll port-forward you in." Don't demo the dashboard live during the keynote — too much surface area for things to go wrong.

---

## What changed from v9 (so you know what's gone)

The 12-slide v9 keynote is replaced. Major changes:

- **Adds the building.** Slides 4, 5, 6 are entirely new — the Anismin Office screenshot hero, the three-floor architecture, and the Mailbox Bus plumbing.
- **Adds federation.** Slide 11 introduces AgentReef as the inter-building protocol — the design choice that makes this scale beyond one person.
- **Adds the line of business.** Slide 12 names the AMaaS pattern for the AI consultancies in the room. Read flat, not as a sale.
- **Drops "The Team" slide.** The two real agents are now visible inside the building tour (slide 5).
- **Drops the standalone "Day 1/30/90" slide.** Folded into the close (slide 13).
- **Drops "Hostage Callback" + "Walk Off" as separate slides.** Combined into slide 13.

The story spine — bet → brief → commission → six moves → bet paid off → close — is intact. What's new is the building you commission *into*, the federation that scales it, and the audience-specific landing on slide 12.
