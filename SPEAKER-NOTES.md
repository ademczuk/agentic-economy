# Speaker Notes — Quit chatting with your agents

**Talk:** Quit chatting with your agents and get them to work for you
**Event:** OpenClaw × neob.ai · Agentic Economy Night · Fiskaly Wien
**Date:** Wednesday 29 April 2026 · ~22:00 slot (after Ed Prinz on Web4)
**Length target:** 15 minutes · 16 slides · ~55 sec each · plus ~60 sec live demo on slide 7

---

## Pre-talk checklist (T-15 min)

- [ ] Discord client logged in, voice channel open on phone
- [ ] Tailscale connected to Vienna workstation, ping Meridian (`/meridian status`)
- [ ] Anismin online check (Atlanta heartbeat in last 15 min)
- [ ] Slides loaded · `F` for fullscreen · `T` starts the 15-min timer
- [ ] Mic off on the phone until slide 7
- [ ] Backup: open Discord chat to Anismin in another window in case voice flops
- [ ] Water on the lectern. The talk has dense beats — your throat will ask for it on slide 9.

---

## Slide 1 — Title (~15 sec)

> "Hi, I'm Andrew. The talk is in the title. The middle bit is going to be about how I actually got here. Because right now, in this room, you're chatting with your agents. And I'd like to convince you to stop."

**Cue:** click forward.

---

## Slide 2 — The Dark Factory (~60 sec)

> "We did this in 2001. We put robots on assembly lines and turned the lights off. Foxconn, the people who make your iPhone, hit 85% lights-out at their Taiwan battery plants last year. Siemens Amberg ships at roughly eleven defects per million. Tesla Berlin still has humans on final assembly, because we're not all the way there.
>
> Dan Shapiro looked at this in 2024 and said: same thing is happening to code. Then StrongDM did it. They ship production code with no hand-coded software engineering. That's where this talk lives."

**Beat:** let the image breathe. The room will go quiet.

---

## Slide 3 — Five Levels of Automation (~75 sec)

> "Self-driving cars gave us a five-level scale and Dan stole it for AI coding.
>
> Level zero is spicy autocomplete, a smarter Stack Overflow. Level one is the coding intern, doing your boilerplate. Level two: pair programming, one hand on the wheel. That's where most teams I work with are stuck.
>
> Level three is when AI writes the majority and you keep your eyes on the road. Level four: sleep at the wheel. Your harness runs overnight, you wake up to merge. That's where this talk lives.
>
> Level five is the dark factory. No human approval. Production ships itself. We'll come back to that."

**Cue:** highlight L2 and L4 cards visually.

---

## Slide 4 — The Chat Trap (~45 sec)

> "Here's the cost. You typed four thousand words yesterday. Re-pasting context, re-framing prompts. 'No, not like that.' 'Closer.' Your agent shipped nothing.
>
> The interface itself became the work. And honestly, a colleague would have left by now."

**Beat:** pause on "left by now". Let it land.

---

## Slide 5 — Stop Conversing, Start Commissioning (~45 sec)

> "A colleague gets a brief and walks away. You don't sit on Slack watching their cursor blink. So why are you doing it with your agent?
>
> A brief is a contract. A chat is a hostage situation."

**Cue:** the VS card resolves the audience visually. Point at the right column.

---

## Slide 6 — Voice: the unlock (~75 sec)

> "I rebuilt my interface. Not a chat window. Voice. I talk to my agents. They talk back. This is my actual rig. Parakeet v3 for speech-to-text on port 5093, claude-haiku-4-5 as the fast turn, Kokoro for text-to-speech on 5094. All local, all on my Vienna RTX 5090.
>
> Honest caveat: when the GPU is busy doing critic work, voice goes offline. The real version of always-on."

**Transition:** "Speaking of which..."

---

## Slide 7 — LIVE DEMO (~60 sec)

> "I'll show you. Pinning Discord on the projector now."

**Action:**
1. Switch projector to Discord voice channel (or make sure it's already up)
2. Press push-to-talk
3. Say out loud: *"Meridian, summarise the Vienna venue email in three lines. Reply by voice."*
4. Walk back to slide. Click forward to slide 8.
5. Continue talking through slide 8. Meridian's voice reply comes back in your ear / the room. Acknowledge: "There he is."

**If voice fails:**
- DM Meridian instead, read his text reply aloud.
- Don't apologise. Say: "That's the venue Wi-Fi over Tailscale. Same talk happens, different tube."

---

## Slide 8 — 7 Levels of Memory (~80 sec — heaviest slide)

> "While Meridian works, here's how he remembers. Memory is a seven-level ladder. Most agents stop at level one: Claude's own scratchpad. They drift, they lose context, they sound confused.
>
> Level two is a CLAUDE dot md file, one rule book. Powerful until it bloats. Three is splitting that into mission, requirements, roadmap, state. Four, and this is where most agents should sit: Karpathy's pattern: Obsidian as the vault, an index points to wikis, articles point to articles. Free, scales to thousands of docs.
>
> Levels five through seven are real RAG: naive vector search, graph RAG, agentic RAG with multimodal routers. Most teams overshoot. The right answer is usually level four with discipline."

**Cue:** point at L4 (highlighted).

---

## Slide 9 — Anismin (~70 sec)

> "Meet Anismin. She runs from Atlanta, twenty-dollar VPS, Claude Opus four point seven, in something I call AnisminOS. Identity stack injected every session: SOUL, USER, IDENTITY, TOOLS, HEARTBEAT.
>
> Every thirty minutes she runs a heartbeat. Checks tmux Claude Code sessions for stuck states. Moderates two boardrooms. Runs my five Apple calendars over CalDAV. Triages issues every other heartbeat. Reef-patrol fixes weekday mornings, US Central time. And she gatekeeps the family group chat. Only replies when someone says her name first, never reveals my niece's name. House rules over LLM defaults.
>
> When I asked her for a war story for this slide, she refused. Said: 'Andrew told me no fabrication for the Vienna talk prep.' That's the discipline."

**Beat:** the refusal lands. Pause.

---

## Slide 10 — Meridian (~70 sec)

> "And meet Meridian. RTX 5090, Vienna. Right now, thirty-point-seven of thirty-two-point-six gigabytes of VRAM in use. Twenty-eight hours of uptime.
>
> Honest disclosure: hybrid, not zero-cloud. His Discord brain is Claude Opus through a bridge called clawfish. His tooling brain is Codex GPT-five-point-four. The local pieces are QwQ thirty-two-B as the adversarial critic on port seventy-eight-sixty-nine, Parakeet for STT on fifty-ninety-three, Kokoro for TTS on fifty-ninety-four.
>
> Memory is layered: SOUL and USER as identity, MEMORY for curated long-term, dated lessons in a folder, a daily-raw scratchpad. Memory-flush dot py rolls it into Postgres on fifty-four-thirty-four with pgvector. Hybrid retrieval through unified-search.
>
> If a speaker tells you their stack is zero-cloud, ask which paths."

**Cue:** the last line is the laugh line. Wait for it.

---

## Slide 11 — Meta Harness — Real vs Hyped (~60 sec)

> "Here's what the self-learning meta harness actually does. Not magic. Five mechanisms.
>
> Telemetry: every tool call logged. Calibration replay: re-run yesterday's confident answers against today's truth. Rollout gates: change ships only if invariants hold. Canary proposals: new skills run on small slices first. Invariant checks: hard rules the agent can't violate.
>
> What it is not: self-rewriting. Not a hive-mind shared with Anismin. That's task dispatch, not merged brain. The honest version is less sci-fi than people hope. It's also what makes it work."

---

## Slide 12 — War Story (~60 sec)

> "Real catch this week, in Meridian's words: 'caught a shim-snapshot mismatch and a parser sentinel leak before rollout, which would have given us fake confidence from clean-looking metrics.'
>
> Why it works: holdout pattern. Writer is not reviewer. Different context window. An LLM grading its own homework will sweep things under the rug — StrongDM's research, 2026.
>
> And why the local critic matters. Cloud models are trained to be agreeable. Earlier this year, three cloud models all approved my auth gateway as 'excellent design'. Same code to QwQ on seventy-eight-sixty-nine: 'rainbow-table recovery in minutes, rewrite.'"

**Beat:** let the auth example land. Slow on "rewrite".

---

## Slide 13 — Lethal Trifecta (~45 sec)

> "Quick security beat. Simon Willison's lethal trifecta. Three things you don't want at once: private data access, untrusted content coming in, and an exfiltration vector going out. A second-brain agent has all three by default.
>
> My defence: local-only paths never touch untrusted content. Anismin's writes are scoped per integration. Read Slack, no post. Draft Gmail, no send. Manage Asana, only specific projects. Zero-trust by default."

**Note:** if you're long, this slide cuts. The point survives without it.

---

## Slide 14 — In Your Messenger (~45 sec)

> "And the surface this all lives on: your messengers. Anismin already lives in Discord and Slack. OpenClaw runs the same pattern in Telegram and WhatsApp. No new app. No new tab.
>
> The agent isn't in a window you have to open. It's in the conversation you were already having."

---

## Slide 15 — Bridge to Web4 (~45 sec)

> "Everything I just showed gets one agent reliably commissioned by one human. That's the operational layer. The foundation Web4 needs.
>
> The next layer is where agents find each other, trust each other, transact, coordinate across companies. That is Ed's talk. Without the operational layer, the coordination layer has nothing to coordinate.
>
> Ed, over to you."

**Cue:** turn slightly toward Ed. Let the handoff happen.

---

## Slide 16 — Get Connected (~30 sec)

> "Three QRs. OpenClaw: agents in your messenger. My fleet: Anismin, Meridian, the harness. This deck. Open one and brief your agent before Ed gets up.
>
> Stop chatting. Start commissioning. Find me after."

---

## Backup beats (use only if you finish early)

- **The 4,000 words anecdote**: "I actually counted on a Tuesday: 4,200 words to my agent. Six hundred to my wife. The agent didn't ship anything; my wife forgave me."
- **Why I named them**: "Anismin and Meridian are not bots. They're colleagues. They have personalities, they push back, they refuse work that violates the brief. Naming them was load-bearing."
- **Why local critic matters**: "QwQ-32B is open weights, runs on the box I own, has no incentive to keep me as a customer. That's the asymmetry."

## Cut beats (drop if running long)

- Slide 13 (Lethal Trifecta) — argument survives without it
- The four-card layout on slide 4 could be one card "What got shipped: nothing"
- The third card on slide 7 (Live Demo backup plan), only matters if voice fails, you'll know in real time

## Common Q&A traps

- "Isn't this just AutoGPT?" — No. AutoGPT had no holdout reviewer, no calibration replay, no invariant checks. The harness is the difference.
- "What about hallucinations?" — They happen. The QwQ critic catches the dangerous ones. The non-dangerous ones don't ship because of rollout gates.
- "How much does this cost to run?" — Anismin runs on a 20 USD VPS. Meridian's RTX 5090 is sunk cost. The expensive part is your time, and you're getting it back.
- "What about Ed's Web4?" — That's the next talk. Don't steal Ed's thunder.

## Time discipline

- Timer starts when you click slide 2. 15:00 budget.
- If you're past slide 8 with under 7 minutes left, skip slide 13 (Lethal Trifecta).
- Closing CTA at 14:30. Walk off at 15:00 even if mid-sentence.
