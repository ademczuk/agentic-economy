# Speaker Notes — Quit chatting with your agents (v6)

**Talk:** Quit chatting with your agents and get them to work for you
**Event:** OpenClaw × neob.ai · Agentic Economy Night · Fiskaly Wien
**Date:** Wednesday 29 April 2026 · ~22:00 slot · 30 min · paired with Ed Prinz on Web4
**Length target:** 30 minutes · 18 slides · ~100 sec each

The talk teaches a pattern (the workbench: 6 moves) by *running it live in the middle of the talk*. The demo is not theatre at the end — it is the teaching moment in the middle.

---

## Pre-talk checklist (T-30 min)

- [ ] Discord client logged in. **Voice and text channels both visible on the projector.**
- [ ] Tailscale connected to Vienna workstation. Ping Meridian (`/meridian status`)
- [ ] Anismin online check (Atlanta heartbeat in last 15 min)
- [ ] Slides loaded. `F` for fullscreen. `T` starts the 30-min timer.
- [ ] **T-10 min: send a silent priming text to Meridian in Discord**: *"Tonight: Fiskaly Wien talk. When I commission you live, expect the card to ask for memory log + 3 lessons. Save to `memory/2026-04-29-fiskaly.md`. Do not pre-write."*
- [ ] **T-5 min: GPU load check.** If VRAM > 31 GB, voice may go offline. Plan for the text-only fallback.
- [ ] **Backup demo video** queued on lectern laptop in second tab — pre-recorded 30s clip of the same commission running cleanly. If voice fails on stage, switch tab and play it.
- [ ] AV tech briefing: *"At slide 6 I'll start commissioning. At slide 7 I'll speak into my phone for ~10 seconds. About 12 seconds later, a file path appears in Discord text on the screen. About 18 seconds later, audio comes back. The Discord text channel stays visible until the end of the talk."*
- [ ] Water on the lectern. The talk has dense beats — your throat will ask for it on slide 9.

---

## Slide 1 — The Hook (~90 sec)

**Walk on. Don't introduce yourself yet.** The title slide IS the hook.

> "You went home tonight. You opened a chat window. You started over from scratch. Again.
>
> Sixty to ninety minutes every evening, you spend reloading your own brain — because the smartest tool you own has no working memory, no routing, no verification, no follow-up.
>
> *That* is tonight's talk. I'm Andrew."

**Beat:** pause on "That is tonight's talk." Let them recognise themselves. Then introduce yourself.

---

## Slide 2 — Karpathy's thread (~90 sec)

> "Andrej Karpathy gave us this framing in three pieces.
>
> 2023: the LLM is the kernel of a new operating system. Not a chatbot. A kernel.
>
> June 2025, he updated it: the LLM is the CPU. The context window is RAM. *You* are the operating system. You decide what to load. You decide how to swap.
>
> 2026, this year: Composio's report named it 'stalled pilot syndrome.' The kernel works. The OS is what's missing. The integration layer is where this year is won.
>
> Tonight's talk: build the OS. Not buy it. Build it."

**Cue:** the dark factory hero is in the background. Don't explain the image. Let it sit.

---

## Slide 3 — The thesis (~90 sec)

> "Here's what an OS for complex work looks like. Not an AI assistant. A *disciplined workbench*.
>
> You describe an outcome. The system handles the rest. Six moves. One spine.
>
> Decompose. Route. Verify. Document. Approve. Follow-up.
>
> I'm going to teach you the six moves by running them in front of you. In about three minutes."

**Cue:** read the six cards left to right, briskly. Don't elaborate yet. The pattern will land in Part 2.

---

## Slide 4 — The chat trap (~75 sec)

> "Quick recognition beat. You typed four thousand words yesterday. Re-pasting context. Re-framing prompts. 'No, not like that.' 'Closer.'
>
> Your agent shipped nothing.
>
> The interface itself became the work. A colleague would have left by now."

**Beat:** hold on "left by now". Get the laugh.

---

## Slide 5 — Commission, don't converse (~75 sec)

> "A colleague gets a brief and walks away. You don't sit on Slack watching their cursor blink. So why do you do it with your agent?
>
> A brief is a contract. A chat is a hostage situation."

**Cue:** the VS card lands the contrast visually. You don't need to read both columns.

---

## Slide 6 — The Commission Card (~120 sec — the artifact slide)

> "This slide is the talk. Photograph it now.
>
> *commission.md*. Six fields. agent, deadline, verify, goal, context, done means, escalate if. About two hundred bytes. Whole pattern in one file.
>
> I'm about to commission this exact card live. The agent on the receiving end is Meridian, who lives on a workstation in this city. Watch the Discord text channel — that's where his work will appear."

**Action:**
1. Confirm Discord text channel is visible on projector.
2. Press push-to-talk on phone. Speak slowly:
   *"Meridian, log tonight's talk in your memory. Event: OpenClaw Agentic Economy Night, Fiskaly Wien, 29 April 2026. Goal: extract three reusable lessons. Save to your dated lessons folder, post the file path in Discord, confirm by voice when done."*
3. Release PTT. Walk to centre of stage. Click forward to slide 7.

**Backup:** if voice is off (GPU loaded), say so plainly: *"Voice is offline, GPU is busy with critic work — exactly like slide 11 will warn. I'll DM the same card. The pattern still runs."* Type the card in Discord. Continue.

---

## Slide 7 — Decompose & Route (Live, Move 1+2) (~100 sec)

**This slide narrates what is happening on the Discord channel right now.**

> "Move one and two. Decompose and route.
>
> The card I just spoke is being parsed by Opus on the cloud. It looks at 'extract three lessons' and breaks it into four sub-tasks: read the talk, reflect to find lessons, write to memory, confirm by voice.
>
> Now look at the routing. *Reflection is hard* — that goes to Opus. *Write the file* is deterministic — that's a tool, not a model. *Voice reply* must be fast — Haiku plus local TTS. The router never asks the smart model to do a dumb job. That is cost, quality, privacy, latency, in one decision."

**Cue:** by now the file path should be appearing in Discord text. Gesture at the projector if you see it: *"There it is. The artifact just landed."*

---

## Slide 8 — Verify & Document (Live, Move 3+4) (~100 sec)

> "Move three and four. Verify and document.
>
> Notice what just happened. The agent didn't say 'I did it.' The agent posted a file path. `memory/2026-04-29-fiskaly.md`. You can check that. If the file isn't there, the commission failed. There is no grey zone.
>
> Every claim has an artifact. That's the verification rule.
>
> And if this same agent ever tries to write garbage to that path, an invariant catches it before it ships. That invariant came from a real failure last quarter. Tomorrow, the same class of mistake costs zero. The system gets less stupid every week."

---

## Slide 9 — Approve & Follow-up (Live, Move 5+6) (~100 sec)

> "Move five and six. Approve and follow up.
>
> The voice just came back in my ear. The card is closed. Now the human bit, in the right place, doing the right thing.
>
> What I approve: was lesson two actually a lesson? Should this be public yet? Is the slug ugly? Judgment, risk boundaries, product taste.
>
> What I do *not* approve: typos, file paths, model picks, whether the JSON parsed.
>
> And then follow-up. The lessons land in Meridian's wiki. Tomorrow's commission starts knowing them. If a lesson contradicts an old one, the harness pings me. The system is sharper than it was twenty minutes ago.
>
> Six moves. One card. The pattern just ran in front of you."

---

## Slide 10 — Card completed (~75 sec)

> "Here's the closed card. Status DONE. Artifact saved. Eighteen seconds total. Three lessons extracted.
>
> Now I'll show you what runs underneath."

**Cue:** brief slide, used for transition into Part 3.

---

## Slide 11 — Voice rig (~75 sec)

> "The rig you just heard. Not a demo, my actual stack.
>
> Parakeet v3 on port 5093 for speech-to-text. Local. Sub-second.
>
> Anthropic Haiku — claude-haiku-4-5 — as the fast turn via clawfish. Hard work hands off to Opus.
>
> Kokoro on port 5094 for text-to-speech. Local voice.
>
> Honest caveat: when the GPU is loaded for critic work, voice goes offline. The honest version of always-on. The talk you just watched ran on this stack. If it works at midnight in a Vienna venue, it works in your kitchen."

---

## Slide 12 — Anismin (~100 sec)

> "Meet Anismin. Atlanta VPS. Twenty-dollar box. Claude Opus four point seven, in something I call AnisminOS. Identity stack injected every session — SOUL, USER, IDENTITY, TOOLS, HEARTBEAT.
>
> Every thirty minutes she runs a heartbeat. Tmux session checks. Boardroom moderation. Calendar routing across five Apple calendars. Reef-patrol fixes weekday mornings. Family group chat — only replies when someone says her name first, never reveals my niece's name. House rules over LLM defaults.
>
> Two real quotes from her, this week.
>
> First: *'Andrew explicitly told me no fabrication for the Vienna talk prep.'* When I asked her for a war story for this slide, she refused.
>
> Second: *'Drunk founders absorb a framework via pattern recognition while watching, not lecture-then-demo.'* That's why the demo just ran in the middle of this talk and not at the end. Her structural advice changed the deck."

**Beat:** pause after the second quote. The audience will catch that the agent helped design the talk. Let them sit with it.

---

## Slide 13 — Meridian + war story (~100 sec)

> "And meet Meridian. Vienna. RTX 5090, 32 GB. Right now, about 31 of 32 in use. Twenty-eight hours of uptime.
>
> Honest disclosure: hybrid, not zero-cloud. The Discord brain is Claude Opus through a bridge called clawfish. The tooling brain is Codex 5.4 through the openclaw gateway. The local pieces are QwQ-32B as the adversarial critic on port seventy-eight-sixty-nine, Parakeet for STT, Kokoro for TTS.
>
> Memory layered. SOUL and USER as identity. MEMORY for curated long-term. Dated lessons in a folder. memory-flush dot py rolls it into Postgres on fifty-four-thirty-four with pgvector.
>
> War story, his words: *'caught a shim-snapshot mismatch and a parser sentinel leak before rollout, which would have given us fake confidence from clean-looking metrics.'*
>
> That is what a regression guard catches. Not a hypothesis. A real failure that turned into a permanent test."

---

## Slide 14 — Time freed (~90 sec)

> "Here's what you actually get. Not a number on a slide. A different shape of week.
>
> Without the workbench: read every message, decide every reply, review every diff, approve every merge, resolve every calendar conflict, write Notion docs nobody re-reads. End of the week, you're tired and behind, and Monday looks the same.
>
> With the workbench: the agent triages, you read 8 things instead of 78. The regression guard runs first, you approve judgment not typos. Calendar conflicts are handled and only escalated when there's a person to choose between. The wiki gets sharper every commission.
>
> Same hours worked. Twice the things shipped.
>
> The advantage of small is focus, not headcount."

---

## Slide 15 — Pitfalls and the uncomfortable truth (~100 sec)

> "Before you start, four traps. Then one uncomfortable truth.
>
> One: full-system thinking. Wanting the whole stack before you've run a single agent through a real workflow. Start with one card. One outcome. One artifact.
>
> Two: better-model thinking. 'Maybe Opus 5 will fix it.' A stronger LLM won't fix your retrieval, your data, or your workflow. The bottleneck is the OS, not the kernel.
>
> Three: skipping oversight. Set-it-and-forget-it agents go feral inside a week. Read every artifact for the first month. Earn the trust before you delegate it.
>
> Four: wrong-tool fit. Enterprise orchestration platforms for solo problems. A markdown file and a shell loop beat a SaaS tier you'll never use.
>
> And the uncomfortable truth — the first two weeks feel slower. You are learning to issue commissions instead of vibes. If I don't tell you that, the serious people in this room will discover it alone and trust me less."

**Beat:** pause on "trust me less". The honest beat is the credibility moment.

---

## Slide 16 — Day 1 / Day 30 / Day 90 (~90 sec)

> "Monday morning starter kit.
>
> Day one: pick a recurring annoying task. Write one Commission Card for it. Save the artifact to one folder. Run it once, by hand if you have to. You now have an OS prototype. Tonight.
>
> Day thirty: an Obsidian vault with dated lessons, an index file, one regression guard that has caught something real. The agent runs from a markdown brief, not a chat.
>
> Day ninety: routing across two or more models. Voice is optional. Shared memory across surfaces. You're commissioning, daily.
>
> Nobody needs to be at Day 90 next week. Just don't be at Day 0 next month."

---

## Slide 17 — Bridge to Web4 (~75 sec)

> "Everything I just showed gets one agent reliably commissioned by one human. That's the operational layer. The foundation Web4 needs.
>
> The next layer is where agents find each other, trust each other, transact, coordinate across companies. That is Ed's talk. Without the operational layer, the coordination layer has nothing to coordinate."

---

## Slide 18 — Vision and connect (~90 sec — the close)

**Read Andrew's verbatim paragraph aloud, slowly. This is the benediction.**

> "In 10 years, my work is less about manually stitching tools together and more about shaping reliable loops: defining what good means, giving the system enough context, watching the evidence, deciding which problems are worth pointing it at.
>
> Small businesses. Creators. Researchers. Solo operators. Using systems like this to build software, run audits, analyse markets, automate operations, and maintain institutional memory — without needing a large staff or a huge SaaS budget.
>
> The goal is not to be the person doing every task faster. The goal is to build the machinery that lets good tasks get done reliably, cheaply, and with accountability."

**Hold a beat.** Then:

> "Three QRs. OpenClaw. My fleet, including the harness. This deck and the Commission Card template.
>
> Photograph the Card. Run one tonight.
>
> Ed Prinz is up next on Web4. Find me after."

---

## Time discipline

| Slot | Slide | Duration |
|---|---|---|
| 0:00–1:30 | 1. Hook | 90s |
| 1:30–3:00 | 2. Karpathy | 90s |
| 3:00–4:30 | 3. Thesis | 90s |
| 4:30–5:45 | 4. Chat trap | 75s |
| 5:45–7:00 | 5. Commission | 75s |
| 7:00–9:00 | 6. The Card (commission live) | 120s |
| 9:00–10:40 | 7. Decompose & Route (live) | 100s |
| 10:40–12:20 | 8. Verify & Document (live) | 100s |
| 12:20–14:00 | 9. Approve & Follow-up (live) | 100s |
| 14:00–15:15 | 10. Card completed | 75s |
| 15:15–16:30 | 11. Voice rig | 75s |
| 16:30–18:10 | 12. Anismin | 100s |
| 18:10–19:50 | 13. Meridian + war story | 100s |
| 19:50–21:20 | 14. Time freed | 90s |
| 21:20–23:00 | 15. Pitfalls + truth | 100s |
| 23:00–24:30 | 16. Day 1/30/90 | 90s |
| 24:30–25:45 | 17. Bridge to Web4 | 75s |
| 25:45–27:15 | 18. Vision + QRs | 90s |
| 27:15–30:00 | Q&A buffer or breath room | 165s |

If you're past slide 11 with under 14 minutes left, skip slide 14 (Time freed) — its content survives in the closing benediction.

If the live demo runs long (over 20s on slide 7), don't wait. Click forward and narrate from slide 8. The artifact will appear when it appears; the slides keep moving.

---

## Cut-list (if running over)

In order of expendability:
1. Slide 14 (Time freed) — the closing vision covers the same ground
2. Slide 4 (Chat trap) — slide 5 carries the contrast
3. Slide 11 (Voice rig) — the demo already showed the rig running
4. Slide 17 (Bridge to Web4) — Ed picks up regardless

Keep at all costs:
- The hook (slide 1)
- The Commission Card (slide 6)
- The four pattern-naming slides (7, 8, 9, 10)
- Anismin's two quotes (slide 12)
- The honest beat on slide 15
- The closing vision (slide 18)

---

## Backup recovery lines

- **Voice fails on demo:** *"Voice is offline. GPU is busy with critic work, exactly what I'll show you on slide 11. The same card runs in Discord text — watch the channel."*
- **Network drops entirely:** *"Venue Wi-Fi just took the day off. The pre-recorded demo is on the lectern. Same stack, same agent, recorded earlier today."* [switch tab, play 30s clip]
- **Both fail:** *"If it breaks, you see it break. The talk's whole point is honesty about what's running. Slide 6 already has the Card. Steal it. Run one tonight."*

---

## Common Q&A traps

- *"Isn't this just AutoGPT?"* — No. AutoGPT had no holdout reviewer, no calibration replay, no invariant checks, no commission contract. The harness is the difference.
- *"What about hallucinations?"* — They happen. The QwQ critic catches the dangerous ones. The non-dangerous ones don't ship because of rollout gates.
- *"How much does this cost?"* — Anismin runs on a $20 VPS. Meridian's RTX 5090 was sunk cost from gaming. Cloud Opus is metered per call. The expensive thing is your time, and you're getting it back.
- *"Will I need to learn to code?"* — To run a Commission Card, no. You write markdown. You read the artifact. The agent does the code. If you can write a brief for a contractor, you can commission an agent.
- *"What about Ed's Web4?"* — That's the next talk. Don't steal Ed's thunder.
