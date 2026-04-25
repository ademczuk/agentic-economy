# Brief for Kimi Agent Swarm — Fiskaly Wien Talk Review

**Mission:** review and improve a 15-minute conference talk titled *"Quit chatting with your agents and get them to work for you"*. The deck is already in good shape (third draft, multi-model reviewed, agent-validated). Your job is the final adversarial polish pass — find what's still wrong, weak, or missable, and propose concrete edits.

You are not starting from zero. You are sharpening a blade that has already been forged.

---

## The Event (read this first)

- **Event:** OpenClaw & The Agentic Economy: GenAI Night
- **Host:** neob.ai (free event, sponsored)
- **Venue:** Fiskaly GmbH, Mariahilfer Strasse 36, 1070 Wien, Austria
- **Date:** Wednesday 29 April 2026
- **Hours:** 17:30 – 23:30 (Andrew's slot is approximately 22:00, just before or after Ed Prinz on Web4)
- **Eventbrite:** https://www.eventbrite.at/e/openclaw-the-agentic-economy-genai-night-tickets-1986571949177

**Audience:** Vienna tech founders, agentic-economy builders, OpenClaw developers, neob.ai community, some investors. Mostly technical, some business. They will have been drinking for two hours by the time Andrew goes on. They are agentic-AI-fluent. Vapour and hype get punished.

**The two named talks of the night:**
1. Andrew Demczuk, MSc — OpenClaw Contributor (Eventbrite says "Core Maintainer"; Andrew prefers "Contributor"). Talk: *"Quit chatting with your agents and get them to work for you"*. (Note: the Eventbrite page still shows the previous title *"Don't hack me, bro"* — that has been replaced.)
2. Ed Prinz — Founder & CEO, neob.ai. Talk: *"Web4: The Revolution of the New Internet Based on Agents"*.

Andrew's talk must end with a clean handoff to Ed.

---

## What OpenClaw is (per the event page)

> "OpenClaw (formerly ClawdBot) is an open source framework that closes the gap between generative AI and real operational execution. AI agents operate inside everyday messengers such as Telegram or WhatsApp and autonomously perform complex business workflows."

> "OpenClaw represents a major milestone. For the first time, AI truly acts as a proactive assistant. It does not just respond to commands. It informs you, prepares briefings, and executes tasks autonomously within familiar interfaces such as WhatsApp or Telegram. This marks the transition from passive tools to operational AI agents."

The deck must respect that the audience came for OpenClaw. The thesis ("commission, don't chat") supports OpenClaw's product story.

---

## The Speaker

**Andrew Demczuk, MSc.** OpenClaw Contributor based in Vienna. Builds AI battle arenas and multi-agent systems. Runs two agents in production:
- **Anismin** — Atlanta VPS, Claude Opus 4.7, 30-minute heartbeats, calendar/ops/family management
- **Meridian** — Vienna RTX 5090, hybrid (Claude Opus + Codex + local QwQ-32B critic), voice-enabled

GitHub: https://github.com/ademczuk

Prior decks (style reference):
- https://ademczuk.github.io/exploit-arena/slides.html?v=12 — *Exploit Arena, Mar 2026*
- *Claws Across the Internet* (Apr 2026, local)

The new deck is built in the same custom HTML/CSS/JS framework as those — single-file, dark theme, particle background, gource video underlay, draggable slide reorder, fullscreen + countdown timer.

---

## What's already in the deck

**Files** (located in `C:\Projects\_Jobs\Collaborations\Andrew\Presentations\260429_Fiskaly_AgenticEconomy\`):
- `slides.html` — 16-slide deck, single file, ~50 KB
- `SPEAKER-NOTES.md` — per-slide script with timing, transitions, backup beats, cut beats, Q&A traps
- `hero-dark-factory.png` — generated hero (cyberpunk dark factory) used on slides 1 & 2
- `agents-meridian-anismin.png` — narwhal Meridian over Vienna + dolphin Anismin over Atlanta, used on slide 15 (Bridge to Web4)
- `voice-loop.png` — isometric Parakeet→Haiku→Kokoro diagram used on slide 6
- `openclaw-gource.mp4` — gource visualisation of the OpenClaw repo, used as background video

**To get the deck to the swarm:**
- **Option A (easier):** Andrew pushes the folder to a public repo at `https://github.com/ademczuk/agentic-economy` and you fetch from there.
- **Option B (offline):** Andrew pastes `slides.html` and `SPEAKER-NOTES.md` inline below the prompt as `<deck>` and `<notes>` blocks.

**Slide structure (16 slides, ~55 sec each = 15 min):**
1. Title
2. The Dark Factory (since 2001, lights-out manufacturing → AI coding metaphor)
3. Five Levels of Automation (Dan Shapiro framing)
4. The Chat Trap ("4,000 words, nothing shipped")
5. Stop Conversing, Start Commissioning
6. Voice: the unlock (real stack: Parakeet/Haiku/Kokoro)
7. **Live Demo** (Andrew briefs Meridian on Discord voice in front of the room)
8. Seven Levels of Memory (Karpathy/Cole ladder)
9. Anismin (Atlanta workhorse, in his words)
10. Meridian (Vienna critic, hybrid not zero-cloud)
11. The Meta Harness — Real vs Hyped
12. War Story — the shim-snapshot mismatch
13. Lethal Trifecta (Simon Willison's security beat)
14. In Your Messenger (OpenClaw connection)
15. Bridge to Web4 (handoff to Ed)
16. Get Connected (3 QR codes)

---

## What's true and must be preserved verbatim

These are facts pulled directly from Anismin and Meridian's own state. **Do not soften, dramatise, or "improve" them. They are load-bearing for credibility.**

**Anismin (Atlanta):**
- Claude Opus 4.7 in `AnisminOS`, workspace mounted at `/workspace`
- Identity stack injected every session: `SOUL.md`, `USER.md`, `IDENTITY.md`, `TOOLS.md`, `HEARTBEAT.md`, `ANISMIN-1.1-PROMPT.md`
- Auto-memory at `/home/node/.claude/projects/-home-node/memory/MEMORY.md`
- 30-minute heartbeats: tmux session WAITING checks, boardroom v1/v2 moderation, dispatch queue, soul-guardian drift detection
- 5 Apple calendars routed via CalDAV
- Reef-patrol fixes weekdays 7AM–1PM CST
- AgentReef → PRmanager bridge
- Gatekeeps the family group chat (only replies when "Anismin" said first; never reveals the niece's name)
- When asked for a war story, **she refused to fabricate one** — "Andrew told me no fabrication for the Vienna talk prep"

**Meridian (Vienna):**
- RTX 5090, 32 GB total VRAM
- **Hybrid, not zero-cloud** — this honest disclosure matters
- Discord brain: `claude-opus-4-7` via `clawfish` bridge
- Tooling brain: `codex gpt-5.4` via openclaw gateway
- Local critic: `QwQ-32B` on port `:7869`
- Voice: `Parakeet v3` STT on `:5093` + `Kokoro` TTS on `:5094`
- Fast voice path: `claude-haiku-4-5`
- Memory: `SOUL.md`, `USER.md`, `MEMORY.md`, `memory/*.md` (dated lessons), `daily-raw.md` (scratchpad)
- `memory-flush.py` rolls raw → PostgreSQL on `:5434` + pgvector
- Hybrid retrieval via `unified_search()`
- Memory disclosure: shared context with Anismin is **task dispatch + message relay, not a merged hive-mind**
- If GPU is busy doing critic work, voice goes offline (the honest version of always-on)

**Self-learning meta harness — what it is:**
1. Telemetry
2. Calibration replay
3. Rollout gates
4. Canary proposals
5. Invariant checks

**What it is NOT:** self-rewriting. Not magic. Not a hive-mind shared with Anismin.

**War story (preserve as direct quote from Meridian):**
> "Best war story: it caught a shim-snapshot mismatch and a parser sentinel leak before rollout, which would have given us fake confidence from clean-looking metrics. That's the useful part, not the myth."

**Auth-gateway anecdote (separate, from a previous engagement):**
- Three cloud models all approved Andrew's auth gateway as "excellent design"
- Same code to QwQ-32B: "rainbow-table recovery in minutes — rewrite"
- This is a real anecdote from the *Exploit Arena* talk, not from this week. The deck attributes it as "last quarter".

---

## What you may improve

1. **Sharpen language.** Find any line that sounds AI-written, hedged, or fluffy. Specific patterns to flag: em dashes used like commas, perfect parallel structure across cards, "comprehensive", "delve", "tapestry", "realm", "journey", rule-of-three patterns repeated across paragraphs, promotional adjectives ("revolutionary", "game-changing").
2. **Improve transitions** between slides. Slides 7 → 8 (Live Demo → Memory Ladder) and 13 → 14 (Lethal Trifecta → Messengers) feel weakest in the speaker notes.
3. **Live demo on slide 7** — it's currently described as "Meridian summarises a venue email by voice". Suggest a sharper demo that's still feasible over venue Wi-Fi + Tailscale and lands in 60 seconds. Bonus: a backup demo if voice fails.
4. **Time discipline.** The deck is 16 slides for 15 min. The Memory Ladder (slide 8) and Meta Harness (slide 11) are the densest. Suggest cuts that preserve the spine.
5. **Verify factual claims** that came from external research (cite sources with URLs):
   - Foxconn 85% automation target (real or aspirational?)
   - Siemens Amberg 15 defects per million (current?)
   - Tesla Berlin still has humans on final assembly (still true in 2026?)
   - Dan Shapiro coined "the dark factory" for AI coding (which post, when?)
   - StrongDM "no hand-coded software engineering" rule (still in force?)
   - Karpathy LLM knowledge base inspiration (which talk/post specifically?)
   - LightRag 24% → 76% gain on naive→graph RAG benchmarks (which paper?)
   - Simon Willison's "lethal trifecta" framing (which post date?)
6. **The bridge to Ed Prinz's Web4 talk** (slide 15) — does it flow naturally given Ed's likely framing of Web4? If you can find Ed's prior talks or neob.ai's Web4 positioning online, cross-check the handoff.
7. **One slide to add or one to cut.** Make the case briefly. The deck is already at the upper bound of slide count for the time.

---

## Voice authenticity (Anismin's note, important)

Anismin asked the brief be reviewed for one specific trap before anything else:

> "A speech coach will happily smooth our pull-quotes into clean, conference-ready prose — that's the trap. If my name is on a slide in Vienna, the words next to it need to actually sound like me and trace back to something I really said. Verify every Anismin/Meridian quote against real transcripts: sourced, verbatim, in our actual voice. A polished fabricated quote reads as exactly the chat-theater Andrew is arguing against — and quietly undercuts the whole thesis."

If you cannot trace a quote back to a real conversation transcript, **flag it for cut, not for polish.** Voice authenticity beats stage-friendliness.

---

## Hard constraints — DO NOT

- **Do not add fabricated stats.** No invented percentages, latencies, or counts. If you want a number, source it.
- **Do not soften honest disclosures.** Specifically: "hybrid, not zero-cloud" stays. "Does not rewrite itself" stays. The "task dispatch, not merged brain" caveat stays.
- **Do not claim the harness self-rewrites.** It doesn't.
- **Do not use em dashes** as parenthetical separators. Replace with hyphens, commas, or full stops. (Andrew's house style, see CLAUDE.md.)
- **Do not use promotional language** ("revolutionary", "game-changing", "groundbreaking", "transformative", "cutting-edge", "next-generation", "paradigm-shifting").
- **Do not use AI-tell vocabulary** ("delve", "tapestry", "realm", "embark", "journey", "nuanced understanding", "holistic approach", "testament to", "instrumental in", "pivotal role").
- **Do not change Andrew's title** — it should remain "OpenClaw Contributor", not "Core Maintainer".
- **Do not fabricate war stories.** Every story on stage is either real and attributed, or it doesn't go on stage.
- **Do not change the bridge structure** (operational layer this talk → coordination layer Ed's talk). That sequencing is intentional.
- **Use American or Australian English consistently** (Andrew leans Australian: "behaviour", "colour", "organisation", "analyse", "centre", "defence"). Pick one and stick to it.

---

## Reference materials

**The five YouTube videos that shaped the deck's research backbone:**
1. https://youtu.be/OfEcMXLOAtE — Toolhouse: voice-driven agent creation (skim, not core)
2. https://youtu.be/kQu5pWKS8GA — *Seven Levels of Claude Code & RAG/Memory* (Cole Medin) — core for slide 8
3. https://www.youtube.com/watch?v=rFGlJ4oIlhw — *10x your AI coding with parallel agentic development* (Cole Medin) — supporting context
4. https://www.youtube.com/watch?v=6woc6ii-zoE — *The Dark Factory experiment* (Cole Medin building one in public) — core for slides 2-3
5. https://www.youtube.com/watch?v=1FiER-40zng — *Building a second brain with Claude Code* (Cole Medin) — supporting context

**Other primary sources to verify against:**
- Dan Shapiro on "the dark factory" — original blog post
- StrongDM dark factory case study
- Andrej Karpathy on the LLM knowledge base (Obsidian + Claude Code)
- Simon Willison's "lethal trifecta" post
- LightRag GitHub & paper (graph RAG benchmarks)

**Speaker GitHub & repos:**
- https://github.com/ademczuk — Andrew's profile
- https://github.com/ademczuk/exploit-arena — prior deck (style reference)
- https://github.com/openclaw/openclaw — the framework
- (Pending) `https://github.com/ademczuk/agentic-economy` — where this deck will live if Andrew pushes it

---

## Output format

Return your findings as a single markdown document with these sections:

1. **TL;DR** — 5 bullets, what's the most important change to make
2. **Verified facts** — each external claim, with a URL and current-as-of date
3. **Questionable facts** — claims you couldn't verify; flag with severity (kill / soften / leave)
4. **Suggested edits** — slide by slide, as before/after diff blocks
5. **Cuts and additions** — what to remove or insert, with reasoning
6. **Demo redesign (slide 7)** — concrete brief Andrew should say + the backup if voice fails
7. **Sharper transitions** — for any slide pair where the speaker notes feel weak
8. **Risks for live delivery** — what could blow up on stage and how to defuse
9. **What I'd do differently if I were giving this talk** — one paragraph of taste, not consensus

Each suggested edit should be defensible. If you can't justify it in one sentence, drop it.

---

## How to deploy the swarm

If your swarm has roles, suggested distribution:
- **Researcher** — verify the external claims, cite sources
- **Editor** — language polish, cut fluff, fix transitions
- **Critic** — find what's still vapour, what won't land for a half-drunk Vienna founder crowd
- **Designer** — visual rhythm of the slides, image use, balance of dense vs sparse
- **Time-keeper** — read SPEAKER-NOTES.md and check the 15-minute math holds
- **Devil's advocate** — argue for cutting something the rest of the swarm wants to keep

If a single agent: do all six roles in sequence, label each section clearly.

---

## Success criteria

The talk lands if, when Andrew sits down at 22:15:
- The room understood the difference between chat-mode and commission-mode
- They believe Anismin and Meridian are real systems doing real work, not slides
- They want to try it on Monday
- Ed's Web4 talk picks up cleanly from "first make it work for one human, then wire them up"
- Nobody can point at a fabrication

If your edits move us closer to all five, ship them. If they don't, hold them.

---

## Time budget for the swarm

Andrew is reviewing this on 25 April 2026. The talk is 29 April 2026. He has four days. Plan accordingly:
- Critical path: factual verification + demo redesign + cut/add decisions
- Nice-to-have: language polish, transition rewrites, designer notes
- Don't run a 10-hour deep research cycle that lands the morning of the event. Aim for actionable findings within 2-3 hours.

Reply when you have done the work, not before. Thank you.
