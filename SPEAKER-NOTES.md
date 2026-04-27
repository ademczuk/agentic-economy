# Speaker Notes — Quit chatting with your agents (v8 / story-spine)

**Talk:** Quit chatting with your agents and get them to work for you
**Event:** OpenClaw × neob.ai · Agentic Economy Night · Fiskaly Wien
**Date:** Wednesday 29 April 2026 · ~22:00 slot · 30 min · paired with Ed Prinz on Web4
**Length target:** 30 minutes · 12 slides · variable timing

The talk is one story: *I commission an agent to write this talk into memory, in front of you, while I explain how. Eighteen seconds in, the file exists. That's the workbench.* Everything else hangs off the bet.

---

## Pre-talk checklist (T-30 min)

- [ ] Discord client logged in. **Voice and text channels both visible on the projector** (or one tap away).
- [ ] Tailscale connected to Vienna workstation. Ping Meridian (`/meridian status`)
- [ ] Slides loaded. `F` for fullscreen. `T` starts the 30-min timer.
- [ ] **T-10 min: send a silent priming text to Meridian in Discord**: *"Tonight: Fiskaly Wien talk. When I commission you live, the brief will ask for memory log + 3 lessons. Save to `memory/2026-04-29-fiskaly.md`. Do not pre-write."*
- [ ] **T-5 min: GPU load check.** If VRAM > 31 GB, voice may go offline. Plan for the text-only fallback.
- [ ] **Backup demo video** queued on lectern laptop in second tab — pre-recorded 30s clip of the same commission running cleanly. If voice fails on stage, switch tab and play it.
- [ ] AV tech briefing: *"At slide 4 I'll speak into my phone for ~10 seconds. About 12 seconds later, a file path appears in Discord text on the screen. About 18 seconds later, audio comes back. The Discord text channel needs to be visible the whole time."*
- [ ] Water on the lectern.

---

## Slide 1 — Title (~75 sec)

> "Quit chatting with your agents and get them to work for you. I'm Andrew. The talk is in the title.
>
> Here's the line that runs through it: a brief is a contract. A chat is a hostage situation.
>
> Tonight I'm going to bet a real piece of work on it. Live. In front of you."

**Cue:** click forward immediately. Don't pause. The pace here sets up the bet.

---

## Slide 2 — The Bet (~120 sec)

**This is the load-bearing slide. Read it slowly.**

> "Right now, on a workstation in this city, my agent is waiting for a brief. His name is Meridian.
>
> In about eight minutes, I'm going to commission him to log this exact talk into his memory. While I keep explaining how, he'll do it. By minute eighteen, the file will exist. You'll see the path appear on screen.
>
> If the bet pays off, you've watched the workbench complete a real piece of work in front of you. If it fails, you'll see exactly where it failed and why. Either way, that's the talk."

**Beat:** pause on "either way, that's the talk." Let the bet land. The audience now has stakes.

---

## Slide 3 — The Brief (~150 sec)

> "Before I commission, here's the thing I'm about to send him. A brief. Six fields.
>
> Goal: what you want. Context: what he needs to know. Done means: how you'll know it worked. Escalate if: what's a stop sign. Deadline: when you need it back. Verify: how the result is proven.
>
> If you can write a brief for a freelancer, you can commission an agent. Two minutes to write the first one. No code. No SDK. No platform.
>
> The deadline I'm giving him: eighteen seconds. The verify: write the result to a file at a known path. If the file exists, the commission paid off. If not, it didn't."

**Cue:** point at the six cards. Don't read all of them. Land on Goal and Verify.

---

## Slide 4 — The Commission (~75 sec — DEMO)

**ACTION SEQUENCE:**

1. Confirm Discord text channel is visible on projector
2. Press push-to-talk on phone
3. Speak slowly:
   *"Meridian, log tonight's talk in your memory. Event: OpenClaw Agentic Economy Night, Fiskaly Wien, 29 April 2026. Goal: extract three reusable lessons. Save to your dated lessons folder, post the file path in Discord, confirm by voice when done."*
4. Release PTT. Walk back to slides. Click forward to slide 5.

**While walking back:**
> "He has the brief. The clock starts. Let me name what's about to happen, in order, while it happens."

**Backup if voice fails at PTT:** *"Voice is offline, GPU is busy with a critic job. I'll DM the same brief instead. The pattern still runs."* Type the brief in Discord. Continue.

---

## Slide 5 — The Six Moves (~180 sec)

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

## Slide 6 — The Bet Paid Off (~90 sec)

> "Eighteen seconds. While I was naming the moves, the agent finished. The path is on screen. The lessons are saved. The follow-up is queued.
>
> I spoke a six-field brief out loud. Once. Walked away. Meridian decomposed, routed, verified, documented, surfaced for approval, queued follow-up. The room watched an artifact appear at a real file path. Not a slide. Not a claim. A file.
>
> That's a workbench. That's commissioning. The chat window doesn't do that."

**Beat:** hold the green DONE badge on screen for the room to see. Three seconds of silence is fine.

---

## Slide 7 — The Team (~120 sec)

> "Two real agents in production for the last six months. The one you just watched is Meridian, in Vienna. There's also Anismin, in Atlanta.
>
> Meridian is hybrid, not zero-cloud. Has a local critic that doesn't care about my feelings. Last quarter, three cloud models all approved an auth gateway as 'excellent design.' Same code to the local critic: 'rainbow-table recovery in minutes — rewrite.' That kind of catch is why a workbench includes a critic that doesn't work for you.
>
> Anismin runs my calendars, triages issues every thirty minutes, moderates the family group chat. Won't say my niece's name unless asked. When I asked her for a war story for this slide, she refused. Said *'Andrew told me no fabrication for the Vienna talk prep.'* That's the discipline.
>
> Then she gave me the structural advice that rewrote this talk. 'Drunk founders absorb a framework via pattern recognition while watching, not lecture-then-demo.' That's why the demo just ran in the middle. She was right."

**Beat:** pause on "she was right". Let the room catch that the agent helped design the talk.

---

## Slide 8 — The Honest Beat (~75 sec)

> "Before you start, one uncomfortable truth.
>
> The first two weeks of doing this feel slower than your old workflow. Not faster. Slower. You're learning to write a brief instead of typing into a chat. You're learning to wait for an artifact instead of reading a stream of tokens. You're learning to approve judgment, not typos.
>
> If I don't say that out loud, the serious people in this room will discover it alone in week one and trust me less. So: it's slower at first. By week three it's not. By week eight you can't go back."

**Beat:** "trust me less" is the credibility moment. Pause on it.

---

## Slide 9 — Day 1 / Day 30 / Day 90 (~90 sec)

> "Monday morning starter kit.
>
> Day one: pick a recurring annoying task. Write one six-field brief for it. Save what comes back to one folder. Run it once, by hand if you have to. You now have an OS prototype. Tonight.
>
> Day thirty: an Obsidian vault of dated lessons, one tripwire that has caught something real, briefs running from markdown instead of chat. You stop re-pasting context every morning.
>
> Day ninety: routing across two or more brains, one or two agents you trust, you're commissioning daily. Voice is optional, not the point.
>
> Nobody needs to be at Day 90 next week. Just don't be at Day 0 next month."

---

## Slide 10 — Hostage Callback (~60 sec)

> "The line that opened this talk:
>
> A brief is a contract. A chat is a hostage situation.
>
> You watched the contract execute in front of you. Eighteen seconds. Real file. Real lessons. Real follow-up.
>
> Walk home. Write one brief. Run it before you sleep."

**Beat:** read the mega text on the slide. The callback is the spine closing.

---

## Slide 11 — Connect (~60 sec)

> "The deck is at the QR. The brief template is in the deck. Photograph it now.
>
> Build the machinery. Not be the person doing every task faster. Build the machinery that lets good tasks get done reliably, cheaply, with accountability.
>
> Ed Prinz is up next on Web4. The operational layer is built. He'll show you the coordination layer. Find me after."

---

## Slide 12 — Walk Off (~30 sec)

**Read it. Walk off. Don't elaborate.**

> "Stop chatting. Start commissioning. Tonight."

**Beat:** silence. Walk to the side of the stage. Hand the room to Ed.

---

## Time discipline

| Slot | Slide | Cumulative |
|---|---|---|
| 0:00–1:15 | 1. Title | 1:15 |
| 1:15–3:15 | 2. The Bet | 3:15 |
| 3:15–5:45 | 3. The Brief | 5:45 |
| 5:45–7:00 | 4. Commission (live demo) | 7:00 |
| 7:00–10:00 | 5. Six Moves (narration) | 10:00 |
| 10:00–11:30 | 6. Bet Paid Off | 11:30 |
| 11:30–13:30 | 7. The Team | 13:30 |
| 13:30–14:45 | 8. Honest Beat | 14:45 |
| 14:45–16:15 | 9. Day 1/30/90 | 16:15 |
| 16:15–17:15 | 10. Hostage Callback | 17:15 |
| 17:15–18:15 | 11. Connect | 18:15 |
| 18:15–18:45 | 12. Walk Off | 18:45 |

**Total: ~18:45 of content. Buffer: 11:15 for organic stretch, audience reactions, demo wait time, Q&A.**

This deck is deliberately under the 30-min budget. The bet on slide 2 promises an 18-minute demo arc; over-running there is fine. Under-running gives Andrew breathing room and Q&A latitude.

---

## What to do if the demo runs long

- The artifact should be visible by the end of slide 5. If it isn't, click forward to slide 6 anyway. The "DONE" framing on slide 6 still works as a verbal claim — when the artifact does appear (slide 7 or later), gesture and acknowledge: *"There it is. Took longer than usual. That's venue Wi-Fi."*
- If voice never replies but text posts: same flow. Slide 6 is about the file existing, not the voice.
- If both fail: the line is *"Voice is offline. The honest version of always-on, exactly what slide 8 will warn. If it breaks, you see it break. That's the talk too."* Click forward. Do not retry. Do not apologise.

---

## What to do if the demo runs short

- If the artifact appears on slide 4 (during the commission speech): perfect. Acknowledge: *"That fast. He didn't even let me finish the explanation."* Click through slide 5 quickly, dwelling only on moves 4-6 (the parts the audience didn't see directly).
- If you finish all 12 slides in 20 minutes: stop. Take questions. Walk off at 27.

---

## The one cut, if running over

**Cut slide 11 (Connect)**. Read the QR aloud, gesture at the projector, and go straight to slide 12 (Walk Off). The connect slide buys nothing the QR doesn't already buy.

---

## Common Q&A traps

- *"Isn't this just AutoGPT?"* — No. AutoGPT had no holdout reviewer, no calibration replay, no tripwires from past failures, no commission contract. The brief is the difference.
- *"What about hallucinations?"* — They happen. The local critic catches the dangerous ones. The non-dangerous ones don't ship because the verify step requires a real artifact at a real path.
- *"How much does this cost?"* — Anismin runs on a $20 VPS. Meridian's hardware was a sunk cost. Cloud Opus is metered per call. The expensive thing is your time, and you're getting it back.
- *"Will I need to learn to code?"* — To run a brief, no. You write markdown. You read the artifact. The agent writes the code. If you can brief a freelancer, you can commission an agent.
- *"What about Ed's Web4?"* — That's the next talk. Don't steal Ed's thunder.

---

## What changed from v7 (so you know what's gone)

The 18-slide v7 deck is replaced. Major cuts:
- Karpathy LLM-as-OS thread (cut: authority appeal, doesn't earn its slot)
- Workbench thesis grid as standalone (cut: 6 moves emerge from the live demo)
- Chat trap as standalone (cut: implicit in the hostage callback)
- Voice rig diagram (cut: voice ran in the demo)
- Time freed slide (cut: the live demo IS time freed)
- Pitfalls grid (cut: one pitfall folded into the honest beat)
- Web4 bridge as a slide (cut: one verbal sentence to Ed)
- 10-year vision as standalone (cut: integrated into Connect)
- 3 QRs at close → 1 QR (deck + brief template)

The story is the spine. The bet is the hook. The artifact is the payoff. The hostage callback is the close. Everything else got out of the way.
