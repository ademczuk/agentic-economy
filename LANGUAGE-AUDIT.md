# Comprehensive Language Audit
**Files audited:** `slides.html`, `SPEAKER-NOTES.md`, `KIMI-SWARM-PROMPT.md`
**Date:** 25 April 2026
**Auditor:** Adversarial copy editor

---

## Summary

| Category | slides.html | SPEAKER-NOTES.md | Total |
|---|---|---|---|
| AI-tell vocabulary | 0 | 0 | 0 |
| Promotional language | 3 | 1 | 4 |
| Em dashes as parentheticals | 15 | 28 | 43 |
| Hedged/fluffy phrasing | 0 | 0 | 0 |
| US English inconsistency | 0 | 0 | 0 |
| Rule-of-three / parallel structure | 2 | 1 | 3 |
| Title violation (Core Maintainer) | 0 | 0 | 0 |

**Key finding:** Em dashes used as parenthetical/sentence-internal separators are the dominant issue (43 instances). Promotional language is light but present. AI-tell vocabulary, hedging, and US-spelling violations are absent from the deck and notes. The title "OpenClaw Contributor" is used correctly everywhere it matters.

---

## Category 1: AI-tell vocabulary

**Target words:** delve, tapestry, realm, embark, journey, nuanced understanding, holistic approach, testament to, instrumental in, pivotal role, comprehensive

**Result: CLEAN.**

No instances found in `slides.html` visible text or `SPEAKER-NOTES.md` prose. The only occurrences are inside `KIMI-SWARM-PROMPT.md`, where they appear in the **"Hard constraints — DO NOT"** section as explicit prohibitions — not as violations.

---

## Category 2: Promotional language

**Target words:** revolutionary, game-changing, groundbreaking, transformative, cutting-edge, next-generation, paradigm-shifting

### Flagged items

| Location | Current text | Issue | Suggested replacement |
|---|---|---|---|
| Slide 5, badge | `Paradigm shift` | Not the exact forbidden adjective, but the noun phrase carries identical promotional DNA. The brief explicitly prohibits "paradigm-shifting" as hype; this badge whispers the same concept. | `The shift` or `Commission mode` or `Brief, don't chat` |
| Slide 6, quote block | `The honest version of always-on.` | "always-on" is a marketing cliché from SaaS landing pages. It undermines the honest-disclosure frame it sits in. | `The honest version of voice.` or `Voice when the GPU is free.` |
| Speaker Notes, Slide 6 header | `## Slide 6 — Voice: the unlock (~75 sec)` | "unlock" is promotional framing (implies secret value being revealed). | `## Slide 6 — Voice: how it works (~75 sec)` or `## Slide 6 — Voice interface (~75 sec)` |
| Notes, Backup beats | `"I actually counted on a Tuesday — 4,200 words to my agent. Six hundred to my wife. The agent didn't ship anything; my wife forgave me."` | The punchline structure is fine, but "actually counted" is borderline self-mythologising. The anecdote itself is good; no change required unless tightening. | *No change needed — this is authentic voice.* |

**Note on `KIMI-SWARM-PROMPT.md`:** The brief contains the exact forbidden words inside quotation marks within the "Hard constraints" section. These are prohibitions, not usage. However, the brief also contains `Web4: The Revolution of the New Internet Based on Agents` (Ed Prinz's talk title, from Eventbrite). That is external branding, not Andrew's prose, so it is exempt.

---

## Category 3: Em dashes used as parenthetical separators

**Rule:** Replace with hyphens, commas, or full stops. Attributions (e.g., `&mdash; Meridian`) are allowed.

### slides.html — Flagged instances

| Slide | Element | Current text | Issue | Suggested replacement |
|---|---|---|---|---|
| 3 (5 Levels) | L2 card label | `L2 &mdash; you are here` | Em dash as label separator. Not parenthetical in a sentence, but inconsistent with house style. | `L2 — you are here` &rarr; `L2: you are here` |
| 3 (5 Levels) | L4 card label | `L4 &mdash; this talk` | Same as above. | `L4: this talk` |
| 8 (Memory Ladder) | L2 pipe description | `Powerful &mdash; until it bloats and pollutes context.` | Sentence-internal parenthetical separator. | `Powerful, until it bloats and pollutes context.` |
| 8 (Memory Ladder) | L4 pipe label | `Obsidian + index &mdash; most agents only need this` | Sentence-internal parenthetical separator. | `Obsidian + index. Most agents only need this.` |
| 9 (Meridian) | Subtitle | `Hybrid &mdash; not zero-cloud.` | Parenthetical separator. | `Hybrid. Not zero-cloud.` |
| 9 (Meridian) | Card 1 title | `Brains &mdash; two of them` | Parenthetical separator. | `Brains: two of them` |
| 9 (Meridian) | Card 2 title | `Memory &mdash; layered` | Parenthetical separator. | `Memory: layered` |
| 10 (Meta Harness) | Telemetry card | `Every tool call, every reflection, every prompt &mdash; logged.` | Parenthetical separator (apositive). | `Every tool call, every reflection, every prompt, logged.` or `Every tool call, reflection, and prompt gets logged.` |
| 10 (Meta Harness) | "What it is not" card | `Not a hive-mind shared with Anismin &mdash; that's task dispatch, not merged brain.` | Parenthetical separator. | `Not a hive-mind shared with Anismin. That's task dispatch, not merged brain.` |
| 11 (War Story) | Card 2 (local critic) | `Same code, same prompt, to QwQ: "rainbow-table recovery in minutes &mdash; rewrite."` | Em dash inside a direct quote from QwQ-32B. The quote is load-bearing and attributed. House style says replace, but voice-authenticity says preserve. | *Tension:* If the transcript shows QwQ used an em dash, preserve it as a verbatim quote. If not, change to: `"rainbow-table recovery in minutes. Rewrite."` |
| 12 (Lethal Trifecta) | Card 1 | `Email, calendar, code, secrets &mdash; the agent can read it.` | Parenthetical separator. | `Email, calendar, code, secrets: the agent can read it.` |
| 12 (Lethal Trifecta) | Card 2 | `Incoming emails, web pages, PRs &mdash; can carry hidden prompts.` | Parenthetical separator. | `Incoming emails, web pages, PRs can carry hidden prompts.` |
| 12 (Lethal Trifecta) | Card 3 | `Can send messages, post to APIs &mdash; data has a way out.` | Parenthetical separator. | `Can send messages, post to APIs. Data has a way out.` |
| 13 (In Your Messenger) | Telegram card bullet | `Forward an email &mdash; agent handles it` | Parenthetical separator. | `Forward an email: the agent handles it.` |
| 14 (Bridge to Web4) | Body text | `coordinate across companies &mdash; that is Web4.` | Parenthetical separator. | `coordinate across companies. That is Web4.` |

### slides.html — Allowed em dash instances (attributions / non-parenthetical)

| Slide | Element | Current text | Why allowed |
|---|---|---|---|
| 2 (Dark Factory) | Quote attribution | `&mdash; Dan Shapiro coined "the dark factory"...` | Attribution at start of citation line. |
| 11 (War Story) | Quote attribution | `&mdash; Meridian, on QwQ-32B as adversarial critic, 25 Apr 2026` | Attribution. |
| 14 (Bridge to Web4) | Left VS label | `This talk &mdash; Operational layer` | Label separator in a UI box, not a sentence. Acceptable but could be colon for consistency. |
| 14 (Bridge to Web4) | Right VS label | `Ed's talk &mdash; Coordination layer` | Same as above. |
| 1 (Title) | HTML `<title>` | `Quit chatting with your agents — Fiskaly × neob.ai · Agentic Economy · Andrew Demczuk` | Title/subtitle separator. Not sentence-internal. |

### SPEAKER-NOTES.md — Flagged instances

| Location | Current text | Issue | Suggested replacement |
|---|---|---|---|
| Pre-talk checklist, line 18 | `The talk has dense beats — your throat will ask for it on slide 9.` | Parenthetical separator. | `The talk has dense beats; your throat will ask for it on slide 9.` |
| Slide 2, line 32 | `Foxconn — the people who make your iPhone — target 85%...` | **Double** parenthetical separator. | `Foxconn (the people who make your iPhone) target 85%...` or `Foxconn, the people who make your iPhone, target 85%...` |
| Slide 2, line 34 | `Then StrongDM did it — they ship production code...` | Parenthetical separator. | `Then StrongDM did it. They ship production code...` |
| Slide 3, line 44 | `Level zero is spicy autocomplete — a smarter Stack Overflow.` | Parenthetical separator. | `Level zero is spicy autocomplete, a smarter Stack Overflow.` |
| Slide 3, line 44 | `Level two — pair programming, one hand on the wheel — that's where most of you are.` | **Double** parenthetical separator. | `Level two: pair programming, one hand on the wheel. That's where most of you are.` |
| Slide 3, line 46 | `Level four — sleep at the wheel — your harness runs overnight...` | **Double** parenthetical separator. | `Level four: sleep at the wheel. Your harness runs overnight...` |
| Slide 4, line 58 | `And honestly — a colleague would have left by now.` | Parenthetical separator. | `And honestly, a colleague would have left by now.` |
| Slide 5, line 70 | `the VS card resolves the audience visually — point at the right column.` | Parenthetical separator. | `the VS card resolves the audience visually. Point at the right column.` |
| Slide 6, line 76 | `Not a chat window — voice.` | Parenthetical separator. | `Not a chat window. Voice.` |
| Slide 7, line 93 | `Continue talking through slide 8 — Meridian's voice reply comes back...` | Parenthetical separator. | `Continue talking through slide 8. Meridian's voice reply comes back...` |
| Slide 8, line 103 | `Most agents stop at level one — Claude's own scratchpad.` | Parenthetical separator. | `Most agents stop at level one: Claude's own scratchpad.` |
| Slide 8, line 105 | `Level two is a CLAUDE dot md file — one rule book.` | Parenthetical separator. | `Level two is a CLAUDE dot md file, one rule book.` |
| Slide 8, line 105 | `Four — and this is where most agents should sit — Karpathy's pattern...` | **Double** parenthetical separator. | `Four, and this is where most agents should sit: Karpathy's pattern...` |
| Slide 9, line 115 | `She runs from Atlanta — twenty-dollar VPS — Claude Opus four point seven...` | **Double** parenthetical separator in spoken text. | `She runs from Atlanta, twenty-dollar VPS, Claude Opus four point seven...` |
| Slide 9, line 117 | `gatekeeps the family group chat — only replies when someone says her name first...` | Parenthetical separator. | `gatekeeps the family group chat. Only replies when someone says her name first...` |
| Slide 11, line 143 | `Telemetry — every tool call logged.` | Parenthetical separator. | `Telemetry: every tool call logged.` |
| Slide 11, line 143 | `Calibration replay — re-run yesterday's confident answers...` | Parenthetical separator. | `Calibration replay: re-run yesterday's confident answers...` |
| Slide 11, line 143 | `Rollout gates — change ships only if invariants hold.` | Parenthetical separator. | `Rollout gates: change ships only if invariants hold.` |
| Slide 11, line 143 | `Canary proposals — new skills run on small slices first.` | Parenthetical separator. | `Canary proposals: new skills run on small slices first.` |
| Slide 11, line 143 | `Invariant checks — hard rules the agent can't violate.` | Parenthetical separator. | `Invariant checks: hard rules the agent can't violate.` |
| Slide 11, line 145 | `Not a hive-mind shared with Anismin — that's task dispatch, not merged brain.` | Parenthetical separator. | `Not a hive-mind shared with Anismin. That's task dispatch, not merged brain.` |
| Slide 12, line 153 | `sweep things under the rug — StrongDM's research, 2026.` | Borderline. Functions as a citation/attribution. | *Allowed as attribution-style citation, but consider:* `sweep things under the rug (StrongDM's research, 2026).` |
| Slide 14, line 173 | `the surface this all lives on — your messengers.` | Parenthetical separator. | `the surface this all lives on: your messengers.` |
| Slide 15, line 183 | `coordinate across companies — that is Web4.` | Parenthetical separator. | `coordinate across companies. That is Web4.` |
| Slide 16, line 193 | `OpenClaw — agents in your messenger.` | Parenthetical separator. | `OpenClaw: agents in your messenger.` |
| Slide 16, line 193 | `My fleet — Anismin, Meridian, the harness.` | Parenthetical separator. | `My fleet: Anismin, Meridian, the harness.` |
| Backup beats, line 201 | `on a Tuesday — 4,200 words to my agent.` | Parenthetical separator. | `on a Tuesday: 4,200 words to my agent.` |
| Cut beats, line 208 | `The four-card layout on slide 4 — could be one card...` | Parenthetical separator. | `The four-card layout on slide 4 could be one card...` |
| Cut beats, line 209 | `(Live Demo backup plan) — only matters if voice fails...` | Parenthetical separator. | `(Live Demo backup plan), only matters if voice fails...` |

### SPEAKER-NOTES.md — Allowed em dash instances

| Location | Current text | Why allowed |
|---|---|---|
| All `## Slide N — Title` headers | `## Slide 1 — Title (~15 sec)` etc. | Section-heading separator. Not sentence-internal parenthetical. Low priority. (Could standardise to colon `## Slide 1: Title` if desired.) |
| Line 185 | `Ed — over to you.` | Direct address / vocative. Not parenthetical. |
| Q&A traps, lines 213–216 | `"Isn't this just AutoGPT?" — No. ...` | Q&A response separator. Standard format for Q&A lists. Acceptable. |
| Line 1 | `# Speaker Notes — Quit chatting with your agents` | Document title separator. Not sentence-internal. |
| Slide 8 header | `## Slide 8 — 7 Levels of Memory (~80 sec — heaviest slide)` | Two em dashes in a heading: one as section separator (allowed), one as parenthetical timing note (`(~80 sec — heaviest slide)`). The second one is borderline. | 

---

## Category 4: Hedged or fluffy phrasing

**Target words:** somewhat, arguably, in many ways, essentially, fundamentally

**Result: CLEAN.**

No instances found in `slides.html` visible text or `SPEAKER-NOTES.md`. The tone is direct and unhedged throughout.

---

## Category 5: Australian/UK English consistency

**Target spellings:** behaviour, colour, organisation, analyse, centre, defence

**Result: CLEAN in prose. CSS code uses US spelling keywords (`color`, `center`), which is unavoidable.**

| Location | Finding | Status |
|---|---|---|
| Slide 12 quote block | `My defence: the local-only paths...` | ✅ Australian spelling correct. |
| Speaker Notes, Slide 13 | `My defence: local-only paths never touch...` | ✅ Australian spelling correct. |
| All CSS properties | `color:`, `text-align:center`, `background-color`, `border-color`, etc. | ⚠️ CSS keywords are standardised to US spelling by the W3C spec. These are code, not prose, and cannot be changed without breaking the page. |
| Notes, Slide 9 | `Reef-patrol fixes weekday mornings, US Central time.` | ✅ "Central" is a proper noun (time zone). Correct. |

**No American spelling found in visible prose content.**

---

## Category 6: Rule-of-three / perfect parallel structure

### Flagged items

| Location | Current text | Issue | Suggested replacement |
|---|---|---|---|
| Speaker Notes, Slide 11, lines 143 | `Telemetry — every tool call logged. Calibration replay — re-run yesterday's confident answers against today's truth. Rollout gates — change ships only if invariants hold. Canary proposals — new skills run on small slices first. Invariant checks — hard rules the agent can't violate.` | **Five sentences with identical `Noun phrase — imperative clause.` structure.** This is the exact pattern the brief warns against: "perfect parallel structure across cards" / "rule-of-three patterns repeated across paragraphs." It sounds like a feature list on a SaaS pricing page, not a human speaking. | Break the pattern by varying sentence structure. Example: `Telemetry means every tool call gets logged. For calibration replay, re-run yesterday's confident answers against today's truth. Rollout gates only open if invariants hold. Canary proposals start on small slices. Invariant checks are hard rules the agent can't violate.` |
| Slide 13 (In Your Messenger), Cross-channel card, bullet 3 | `One agent. Many surfaces. Same brain.` | Rhetorical rule of three. It's punchy and memorable, but it is the pattern the brief explicitly flags. | *Acceptable if intentional.* If cutting it: `One agent, many surfaces, same brain.` (removes the staccato three-beat rhythm). |
| Slide 3 (5 Levels) | L0–L5 cards all share identical component structure: `L#` label + title + one-sentence description. | Perfect parallel structure across 6 cards. However, this is **by design** — it is a numbered ladder (analogous to self-driving car levels), and the parallelism is the point. | *No change needed.* The parallel structure is the informational architecture of the slide. |

---

## Category 7: Title verification — "OpenClaw Contributor" vs "Core Maintainer"

**Result: CLEAN.**

| Location | Finding |
|---|---|
| `slides.html` line 202 | `OpenClaw Contributor` in gource overlay ✅ |
| `slides.html` line 231 | `OpenClaw Contributor` in slide 1 footer ✅ |
| `slides.html` line 700 | `OpenClaw Contributor` in slide 16 footer ✅ |
| `SPEAKER-NOTES.md` | No title string present (not required in notes) ✅ |
| `KIMI-SWARM-PROMPT.md` | "Core Maintainer" appears **only** in the factual note: "Eventbrite says 'Core Maintainer'; Andrew prefers 'Contributor'." This is a documentary observation, not a title assignment. ✅ |

---

## Honourable mentions — things that are fine but worth watching

1. **The title tag em dash.** `Quit chatting with your agents — Fiskaly × neob.ai` uses an em dash as a title/subtitle separator. This is not a parenthetical separator in running prose, so it is exempt. If being purist, use a colon or an en dash instead.

2. **The `&rarr;` arrows in slide 8.** `Vault &rarr; wiki &rarr; index &rarr; article` uses HTML entity arrows. These are fine — they're directional symbols in a diagrammatic sequence, not em dashes.

3. **"honest version" / "honest stack" / "honest disclosure"** appears 4–5 times across the deck. This is a deliberate rhetorical frame (honesty as contrast to hype), not hedging. It is load-bearing for credibility. Do not cut.

4. **"Zero-trust by default" (slide 12 notes)** — "Zero-trust" is an industry term (NIST / cybersecurity standard). The hyphen is correct when used as a compound modifier. No spelling issue.

5. **"the unlock" in notes** — already flagged under promotional language. If kept, it reads like product marketing. Consider "how it works" or "the interface".

---

## KIMI-SWARM-PROMPT.md self-check

The brief itself is **not** the target of the audit in the same way, but since it was included in the read list, a quick check:

- Contains the exact forbidden words and phrases **only inside quotation marks** within the "Hard constraints — DO NOT" section. These are prohibitions, not usage. Not a violation.
- Contains "Core Maintainer" as a **factual note about Eventbrite's error**, with immediate correction. Not a violation.
- Uses em dashes as parenthetical separators throughout (e.g., `The deck is already in good shape — third draft`). Since the brief is the document that *sets* the house style, this is a meta-inconsistency, but it does not affect the talk.

---

## Priority ranking for fixes

| Priority | Item | File | Rationale |
|---|---|---|---|
| **P0 (Critical)** | Replace all parenthetical em dashes in `slides.html` body text | slides.html | House style is hard constraint; audience will see these on screen |
| **P0 (Critical)** | Fix the 5 parallel sentences in Speaker Notes Slide 11 | SPEAKER-NOTES.md | Most obvious "AI-sounding" structural pattern in the entire deck |
| **P1 (High)** | Replace parenthetical em dashes in Speaker Notes spoken quotes | SPEAKER-NOTES.md | Speaker will read these aloud; they affect vocal rhythm |
| **P1 (High)** | Change "Paradigm shift" badge | slides.html | Promotional tone contradicts the anti-hype thesis |
| **P2 (Medium)** | Replace "always-on" and "unlock" framing | slides.html + notes | Marketing residue on an otherwise honest slide |
| **P2 (Medium)** | Resolve the QwQ quote em dash | slides.html | Tension between house style and voice authenticity |
| **P3 (Low)** | Standardise `## Slide N — Title` headers to colons | SPEAKER-NOTES.md | Consistency, but not audience-facing |
| **P3 (Low)** | "One agent. Many surfaces. Same brain." | slides.html | Rhetorical rule of three. Keep or smooth depending on taste |

---

*End of audit.*
