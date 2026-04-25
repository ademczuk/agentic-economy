# Visual Design Assessment — Agentic Economy Deck (16 Slides)

**Event:** Fiskaly Wien, 29 Apr 2026 · Projector · Room with ambient light · Audience may be 2+ drinks in
**Deck:** `slides.html` · Single-file dark-themed HTML/CSS/JS · Custom framework
**Assessor role:** Designer (visual rhythm, legibility, balance, projector suitability)

---

## 1. Visual Rhythm & Energy Curve

### Energy Map (low → very high)

| Slide | Title | Density | Marker |
|-------|-------|---------|--------|
| 1 | Title | **LOW** | · Breathing room |
| 2 | The Dark Factory | **MEDIUM** | ░ Setup slide |
| 3 | 5 Levels | **HIGH** | █ 6 tiny cards |
| 4 | Chat Trap | **HIGH** | █ Lopsided cards |
| 5 | Commission | **MEDIUM** | ░ VS layout |
| 6 | Voice Stack | **MEDIUM** | ░ Image + cards |
| 7 | Live Demo | **MEDIUM** | ░ Demo moment |
| 8 | Memory Ladder | **VERY HIGH** | █ 7 pipeline steps |
| 9 | Anismin | **VERY HIGH** | █ 12 bullets + quote |
| 10 | Meridian | **VERY HIGH** | █ 9 bullets + dense body |
| 11 | Meta Harness | **HIGH** | █ 6 cards |
| 12 | War Story | **HIGH** | █ Quote + lopsided cards |
| 13 | Lethal Trifecta | **MEDIUM** | ░ 3 cards + signs |
| 14 | In Your Messenger | **MEDIUM** | ░ 3 cards |
| 15 | Bridge to Web4 | **MEDIUM** | ░ VS layout + bg image |
| 16 | CTA | **LOW** | · Breathing room |

### The Rhythm Problem

**Slides 8–12 form a 5-slide wall of text with no breathing room.** This is the core pacing disaster:

```
Slide 7 (Live Demo)     ← audience engaged, energy up
Slide 8 (Memory Ladder) ← 7 steps thrown at them immediately
Slide 9 (Anismin)       ← 12 bullets, dense body text
Slide 10 (Meridian)     ← 9 bullets, dense body text  
Slide 11 (Meta Harness) ← 6 more cards
Slide 12 (War Story)    ← quote + lopsided cards
Slide 13 (Lethal)       ← first chance to breathe
```

After the live demo (slide 7), the audience is primed. Then they get hit with **37 discrete information chunks** across 5 slides (7 pipeline steps + 12 bullets + 9 bullets + 6 cards + 2 cards). That is not a talk; that is a data dump.

**Slides 3–4** are also a mini-cluster: two consecutive dense slides early in the talk, right when the audience is still warming up.

**The only true breathing moments are slides 1 and 16.** Slide 7 (Live Demo) is technically low-density on the slide, but it's high-cognitive-load live performance — the speaker is the content. The deck needs at least one more visual "reset" slide between 8 and 12.

**Recommendation:** Insert a visual-only or near-textless slide between slides 7 and 8, or cut one of slides 8–12 entirely. The 5-slide dense cluster will lose the room.

---

## 2. Image Use

### Image Inventory

| Image | Slides Used | Assessment |
|-------|-------------|------------|
| `hero-dark-factory.png` | **1, 2** | ⚠️ **Overused** — back-to-back identical hero |
| `voice-loop.png` | 6 | ✅ Good — single use, informative diagram |
| `agents-meridian-anismin.png` | 15 | ✅ Good — single use, thematic bridge slide |
| `openclaw-gource.mp4` | All (bg) | ✅ Good — ambient motion, subtle |

### Hero Image Overuse (Critical)

**Slides 1 and 2 both use `hero-dark-factory.png` at `opacity: 0.32` (`.slide-bg.full`).** This is the most visible design flaw in the deck. Two consecutive slides with the same full-bleed background image reads as "I only had one image." For a room of technical founders who will judge production values, this undermines credibility.

**Fix:** Remove the hero image from slide 2. The Dark Factory metaphor works without the visual — the words carry it. Or generate a second factory image with a different angle/depth. If neither is possible, drop slide 2 to `opacity: 0.12` (standard `.slide-bg` level) so it reads as texture, not "same slide again."

### Slides That Need Images But Have None

| Slide | Why It Needs a Visual | Suggestion |
|-------|----------------------|------------|
| **3 — 5 Levels** | Six text cards is abstract; a ladder/stair visual would anchor the concept | Simple CSS/SVG stepped diagram showing L0→L5 progression |
| **8 — Memory Ladder** | Seven pipeline steps is a wall of text; a pyramid or staircase visual would help | Karpathy's own ladder redrawn as 7 stacked blocks |
| **11 — Meta Harness** | Five mechanisms in six cards is abstract; a loop/feedback diagram would clarify | Simple telemetry → calibration → gates → canary → invariant cycle diagram |
| **12 — War Story** | The shim-snapshot mismatch is invisible; a before/after diff visual would land the point | Two small code diff blocks side by side (even simplified/fake) |

The deck relies heavily on card-grids for information architecture. Cards are fine for detail slides, but **abstract concept slides need diagrams**, not more cards.

---

## 3. Text Density — The 3 Worst Offenders

### 🥇 Slide 9 — Anismin (~145 words)

**What's on it:**
- Badge + big headline + divider
- One dense body sentence with 5 monospace file references
- 3 cards × 4 bullets each = 12 bullets
- Quote block

**Why it's a problem:** This is the slide after the already-dense Memory Ladder. The audience has just parsed 7 memory levels and now gets 12 operational bullets plus a dense identity-stack sentence. At 55 seconds per slide, that's ~4.5 seconds per bullet. Impossible to absorb.

**Redesign:**
- **Cut to 2 cards, not 3.** Merge "Calendar & ops" and "Family & etiquette" into one "Ops & boundaries" card.
- **Reduce bullets from 4 to 2 per card.** The audience doesn't need every CalDAV detail on screen. "5 Apple calendars via CalDAV" and "Reef-patrol fixes weekdays" can become "Calendar + task automation" and "Scoped access rules".
- **Move the quote to the body.** The "she refused to fabricate" quote is strong — give it the full quote block treatment without competing cards.

### 🥈 Slide 8 — Memory Ladder (~130 words)

**What's on it:**
- 7 pipeline steps with labels + descriptions
- pipe-desc font: **0.76rem**

**Why it's a problem:** Seven items is too many for a 55-second slide. The descriptions are tiny (0.76rem) and will be unreadable from the back row. The audience can't process 7 memory levels in under a minute.

**Redesign:**
- **Show only 4 levels: L1, L2, L4, L7.** L3 and L5 are transitional; L6 is niche. L4 (Obsidian) is where most agents should be. L7 (Agentic RAG) is the aspirational ceiling. L1 and L2 show where most people currently sit. This cuts the cognitive load by 43%.
- **Increase pipe-desc to 0.85rem minimum.** 0.76rem on a projector is illegible past the third row.
- **Or:** Replace the pipeline with a **pyramid diagram** — 4 stacked layers with colour coding. Visual > vertical list for spatial memory.

### 🥉 Slide 10 — Meridian (~130 words)

**What's on it:**
- Dense body sentence with VRAM stats and uptime
- 2 cards: "Brains" (4 bullets) + "Memory" (5 bullets)
- 9 total bullets, many with monospace references

**Why it's a problem:** This is slide 10 of 16, deep in the dense cluster. The audience has already seen 7 memory levels and 12 Anismin bullets. Now 9 more bullets about a second agent's stack. Stack details are important for credibility, but the screen is not the place for port numbers.

**Redesign:**
- **Reduce to 3 bullets per card.** "Brains" card: Discord path, local critic, voice. "Memory" card: Identity files, curated memory, hybrid retrieval. That's 6 bullets total vs 9.
- **Move VRAM/uptime to a small stat block** (like the stat-grid component already in CSS) — make it a big number: "30.7 / 32.6 GB VRAM in use" as a visual anchor, not buried in body text.
- **Drop the "If a speaker tells you..." mono line.** It's a good punchline, but the slide is already full. Move it to speaker notes.

---

## 4. Visual Balance — Card Layouts

### Lopsided Cards (Projector Risk)

| Slide | Layout | Problem | Severity |
|-------|--------|---------|----------|
| **4 — Chat Trap** | 2 cards | Left: 4 bullets. Right: 1 big word + 1 short sentence. Left card will be ~2× taller. | 🔴 High |
| **12 — War Story** | 2 cards | Left: 2 short sentences. Right: 1 massive paragraph (rainbow-table anecdote). Right card will be ~2.5× taller. | 🔴 High |
| **10 — Meridian** | 2 cards | Left: 4 bullets. Right: 5 bullets + longer lines. Right will be slightly taller. | 🟡 Medium |
| **9 — Anismin** | 3 cards | All 3 have 4 bullets each. Relatively balanced. | 🟢 Low |
| **11 — Meta Harness** | 3×2 grid | Cards have similar content length. Balanced. | 🟢 Low |

### Grid Balance Analysis

**Slide 4 (Chat Trap):** The right card's "nothing" is a strong visual, but it creates a massive vertical gap below it while the left card extends downward. On a projector, this asymmetry looks broken — like a layout error.

**Fix for Slide 4:** Center-align the content in both cards vertically. Or add more visual weight to the right card — a large icon, an empty-box graphic, or even just more padding to approximate the left card's height.

**Fix for Slide 12:** The right card's auth-gateway anecdote is a paragraph, not bullets. Paragraphs in cards always create height imbalance. **Convert to 3 short bullets:**
- "Three cloud models approved it as 'excellent'"
- "Same code to QwQ-32B: 'rainbow-table recovery in minutes'"
- "The model that doesn't care about your feelings"

---

## 5. Legibility at Distance — Projector Assessment

### Font Size Audit (Critical for Projector)

| CSS Class | Size | Back-Row Legibility | Usage |
|-----------|------|---------------------|-------|
| `.mega` | clamp(2.4rem, 5.6vw, 4.2rem) | ✅ Excellent | Headlines only |
| `.big` | clamp(1.4rem, 3.6vw, 2.6rem) | ✅ Good | Slide titles |
| `.mid` | clamp(1.05rem, 2.3vw, 1.6rem) | ✅ Readable | Subheads |
| `.body` | clamp(0.85rem, 1.45vw, 1.1rem) | ⚠️ Marginal | Body paragraphs |
| `.small` | clamp(0.7rem, 1vw, 0.85rem) | ❌ Too small | Meta info, URLs |
| `.card p/li` | 0.82rem | ❌ Too small | Card body text |
| `.pipe-desc` | 0.76rem | ❌ **Critical** | Pipeline descriptions |
| `.lv-desc` | 0.72rem | ❌ **Critical** | Level card descriptions |
| `.lv-num` | 0.7rem | ❌ **Critical** | Level numbers |
| `.codeblock` | clamp(0.7rem, 0.95vw, 0.82rem) | ❌ Too small | Code samples |

### The Problem

**Card text at 0.72–0.82rem will be unreadable from the back row of a projector room.** The `clamp()` functions scale with viewport width, but projector aspect ratios and distances mean the effective resolution is much lower than a laptop screen. A 0.72rem font on a projector from 15 meters is roughly equivalent to 6px on a laptop — illegible.

**Slides most affected:**
- **Slide 3 (5 Levels):** `.lv-desc` at 0.72rem, `.lv-num` at 0.7rem — the descriptions will be fuzzy grey smears from the back.
- **Slide 8 (Memory Ladder):** `.pipe-desc` at 0.76rem — 7 lines of tiny text.
- **Slide 5 (Commission):** Inline list items at 0.86rem — borderline but may pass.
- **Slide 9–12:** Card bullets at 0.82rem — readable only for front half of room.

**Minimum safe projector sizes:**
- Body text: **0.95rem minimum**
- Card text: **0.88rem minimum**
- Descriptions: **0.85rem minimum**
- Any text you expect people to read: **never below 0.85rem**

### Contrast Check

The dark theme uses:
- Background: `#0a0e1a` (very dark blue-black)
- Text: `#f1f5f9` (off-white) — contrast ratio ~17:1 ✅ Excellent
- Dim text: `#94a3b8` (slate) — contrast ratio ~7.5:1 ✅ Good
- Muted text: `#64748b` (slate-500) — contrast ratio ~4.8:1 ⚠️ Marginal for small text

The muted text (`#64748b`) is used for `.small`, labels, and meta info. At 0.7rem on a projector, this will be genuinely hard to read. **Lighten muted to `#8899aa` for projector-safe contrast, or increase font size.**

---

## 6. Colour Consistency

### Gradient Usage Audit

| Gradient Class | Colours | Slides Used | Assessment |
|----------------|---------|-------------|------------|
| `.text-gradient` | blue → cyan | 3, 8 | ✅ Consistent |
| `.text-gradient-purple` | purple → pink | 5, 10, 15 | ✅ Consistent |
| `.text-gradient-green` | green → cyan | 11, 14 | ✅ Consistent |
| `.text-gradient-red` | red → orange | 4, 12, 13 | ✅ Consistent |
| `.text-gradient-claw` | purple → cyan | 2 | ⚠️ Very similar to `.text-gradient` (blue→cyan) |
| `.text-gradient-electric` | electric → purple | **Unused** | 🔴 Dead code |
| `.text-gradient-voice` | orange → pink | 1, 6, 16 | ✅ Strong brand signature |
| `.text-gradient-yellow` | yellow → orange | **Unused** | 🔴 Dead code |

### Issues

1. **`.text-gradient-claw` (slide 2)** uses purple→cyan. `.text-gradient` (slides 3, 8) uses blue→cyan. On a projector, purple and blue are nearly indistinguishable in gradient form. The audience won't perceive these as different brand colours. **Suggestion:** Make `.text-gradient-claw` use a more distinct pair — orange→purple or yellow→red — so slide 2 has its own visual identity.

2. **Dead gradient classes:** `.text-gradient-electric` and `.text-gradient-yellow` are defined but unused. Not harmful, but unnecessary CSS.

3. **Badge-to-gradient matching is generally good:** Each slide's badge colour matches its gradient accent. This is a strong, consistent system.

### Slide That Feels Visually "Off"

**Slide 11 (Meta Harness):** The sixth card is styled differently: `border-color:var(--border);background:rgba(0,0,0,0.4)` instead of a glow class. This card says "What it is *not*". The visual flattening is intentional (muted = negative space), but on a projector it will look like a broken card — the border will be barely visible against the dark background. **Suggestion:** Give it a subtle grey glow or border so it reads as intentional, not a rendering error.

---

## 7. Slide-Specific Issues

### Slide 1 — Title
**Assessment: ✅ Good**
- Clean, minimal, hero image sets tone.
- One concern: the `hero-dark-factory.png` at 0.32 opacity with white text overlay — check that the image doesn't have bright areas that blow out the headline. (Depends on the actual PNG; can't verify without seeing it.)

### Slide 2 — The Dark Factory
**Assessment: ⚠️ Needs work**
- **Same hero image as slide 1.** Immediate visual fatigue.
- The quote block is strong but competes with the body text for attention.
- **Fix:** Remove hero image or reduce to 0.12 opacity. Let the quote block breathe.

### Slide 3 — 5 Levels
**Assessment: 🔴 Poor (for projector)**
- **6 level cards in a row.** On a 16:9 projector, `flex:1` with `min-width:140px` and `gap:8px` means each card gets ~170px width.
- **Font sizes:** `lv-title` at 0.85rem, `lv-desc` at 0.72rem — back-row illegible.
- **The "you are here" card (L2)** has a glow effect which helps, but L4 and L5 also have custom border colours without the glow, creating inconsistent visual hierarchy.
- **Fix:**
  - Reduce to **5 cards** (merge L0+L1 into "Assisted coding") or **use 2 rows of 3**.
  - Increase `lv-desc` to **0.88rem minimum**.
  - Increase `lv-title` to **1.0rem**.
  - Give L2 the glow, L4 a cyan glow, L5 a red glow — make the progression visually obvious.

### Slide 4 — Chat Trap
**Assessment: ⚠️ Needs work**
- **Lopsided cards** (left tall, right short).
- The "nothing" in the right card is a great punchline but the visual imbalance undermines it.
- **Fix:** Add vertical centering to cards. Or add a large "0" or empty box icon to the right card to balance height.

### Slide 5 — Commission
**Assessment: ✅ Good**
- VS layout is balanced, both sides have 4 bullets.
- The mono punchline at bottom is a nice touch.
- Minor: the `vs-label` at 0.7rem is small for projector.

### Slide 6 — Voice Stack
**Assessment: ✅ Good**
- Only slide with a real diagram (`voice-loop.png`). This is the model for what other abstract slides should do.
- Image + cards layout is well-balanced.
- The quote block at bottom is honest and grounded.

### Slide 7 — Live Demo
**Assessment: ✅ Good**
- Waveform animation adds kinetic energy.
- 3 cards with concise content.
- The "If the demo gods say no" card is brilliant — it signals competence.
- This is the right density for a live-demo slide.

### Slide 8 — Memory Ladder
**Assessment: 🔴 Poor**
- **7 pipeline steps.** Too many for 55 seconds.
- **0.76rem descriptions** — illegible on projector.
- Each step has a different border colour, creating a rainbow effect that distracts from the content.
- **Fix:** Show 4 levels only (L1, L2, L4, L7). Increase all text to 0.9rem. Or replace with a pyramid/stack visual.

### Slide 9 — Anismin
**Assessment: 🔴 Poor**
- **Most text-heavy slide** (~145 words).
- 12 bullets across 3 cards is overwhelming.
- The body sentence has 5 monospace references crammed together — reads as dense code soup.
- **Fix:** Cut to 2 cards × 2 bullets. Move identity-stack details to speaker notes. Let the "refused to fabricate" quote be the star.

### Slide 10 — Meridian
**Assessment: 🔴 Poor**
- Second-most text-heavy (~130 words).
- The body sentence with VRAM stats is a data dump.
- 9 bullets in 2 cards is too many after Anismin.
- **Fix:** Use a stat block for VRAM. Cut to 3+3 bullets. Drop the mono punchline.

### Slide 11 — Meta Harness
**Assessment: ⚠️ Needs work**
- 6 cards in a 3×2 grid is a lot to scan.
- The "What it is NOT" card has flat styling that looks broken.
- Each card has only 1 sentence — the density is actually manageable, but 6 cards still feels like a grid of Post-it notes.
- **Fix:** Convert to a **process flow diagram** (telemetry → calibration → gates → canary → invariant) with the "NOT" card as a separate callout below. Visual flow > card grid.

### Slide 12 — War Story
**Assessment: ⚠️ Needs work**
- **Severely lopsided** — right card has a paragraph wall.
- The quote block at top is strong. The cards below compete with it.
- **Fix:** Convert right card to 3 short bullets. Or make the quote the full slide and move cards to the next slide (but deck is already at 16).

### Slide 13 — Lethal Trifecta
**Assessment: ✅ Good**
- **Note:** The `.lethal-triangle` CSS class (lines 183–189) is **defined but unused**. The actual slide uses flex cards with `+` signs between them — a much better projector choice than an absolute-positioned triangle.
- 3 cards at `max-width:240px` will be readable.
- The `+` signs at 1.6rem are visible and clear.
- Quote block at bottom is well-placed.
- **Dead code cleanup:** Remove the unused `.lethal-triangle`, `.lethal-node` CSS rules to save ~15 lines.

### Slide 14 — In Your Messenger
**Assessment: ✅ Good**
- 3 cards, 3 bullets each — balanced and readable.
- The quote block is a strong closer for this section.
- This slide correctly bridges to OpenClaw.

### Slide 15 — Bridge to Web4
**Assessment: ✅ Good**
- Background image (`agents-meridian-anismin.png`) differentiates from earlier slides.
- VS layout cleanly separates "this talk" from "Ed's talk."
- The mono line at bottom is a clean thesis statement.
- Good handoff energy.

### Slide 16 — Get Connected
**Assessment: ⚠️ Needs work**
- **3 QR codes at ~200–250px displayed size.**
- QR code scannability from projector distance is questionable. A 200px QR on a screen viewed from 10+ meters requires very steady hands and good phone cameras.
- **3 QRs is decision paralysis.** Which one? The audience will spend 10 seconds deciding instead of scanning.
- The colours (purple, orange, cyan) are on-brand but the QR generator uses light text on dark backgrounds which can reduce scan reliability.
- **Fix:**
  - **Make one QR dominant** — OpenClaw (the product) at 300px+. Move GitHub and deck to smaller secondary links below.
  - **Test scanability** from 5 meters with a mid-range phone. If it doesn't scan reliably, replace with a short URL in large text.
  - **Consider:** One big QR to `openclaw.net` + the GitHub URL in large monospace text. The deck URL is least important — speakers can share it verbally.

---

## Summary: Top 3 Priority Visual Fixes

### 1. Fix the 5-Slide Text Wall (Slides 8–12) 🔴
**Impact:** Audience will tune out during the densest section of the talk.
**Action:** Cut one slide from the cluster (sacrifice: slide 11 Meta Harness — move its content to speaker notes for slide 10). On remaining slides, cut bullets by 40% and increase font sizes to 0.9rem minimum.

### 2. Stop Reusing the Hero Image (Slides 1–2) 🔴
**Impact:** Reads as low production value; undermines credibility with a technical audience.
**Action:** Remove hero image from slide 2 entirely, or generate a second factory image. Drop slide 2 bg to standard 0.12 opacity if keeping.

### 3. Increase Card Text to Projector-Safe Sizes (Slides 3, 8, 9, 10) 🔴
**Impact:** Back half of the room cannot read level descriptions, pipeline steps, or bullet details.
**Action:** Global minimum card text size: 0.88rem. Specific fixes:
- Slide 3: `lv-desc` 0.72rem → 0.9rem, `lv-title` 0.85rem → 1.0rem
- Slide 8: `pipe-desc` 0.76rem → 0.9rem, show 4 steps not 7
- Slides 9–10: `card li` 0.82rem → 0.9rem, cut bullets by 30%

---

## Overall Visual Coherence Score: 6/10

**What's working:**
- Consistent dark theme with good base contrast
- Badge/gradient colour system is disciplined
- The Voice Stack slide (6) and Live Demo slide (7) are excellent — they show what the deck can do at its best
- The bridge slide (15) has good energy and clear purpose
- Particle background + gource video creates ambient depth without distraction

**What's hurting the score:**
- Hero image overuse (-1.5)
- 5-slide dense cluster with no breathing room (-1.5)
- Card text sizes below projector-safe thresholds (-1.0)
- Lopsided card layouts on slides 4 and 12 (-0.5)
- Slide 16 QR scannability uncertainty (-0.5)

**With the top 3 fixes applied, this becomes an 8/10 deck.** The framework is solid; the content just needs breathing room and projector-safe font sizes.

---

## Quick-Reference: Redesign Cheat Sheet

| Slide | Rating | Fastest Fix |
|-------|--------|-------------|
| 1 | ✅ Good | — |
| 2 | ⚠️ Needs work | Remove or reduce hero image opacity |
| 3 | 🔴 Poor | Increase font sizes; consider 2 rows of 3 |
| 4 | ⚠️ Needs work | Center cards vertically or balance content |
| 5 | ✅ Good | — |
| 6 | ✅ Good | — |
| 7 | ✅ Good | — |
| 8 | 🔴 Poor | Show 4 levels, not 7; increase font size |
| 9 | 🔴 Poor | Cut to 2 cards × 2 bullets; let quote breathe |
| 10 | 🔴 Poor | Stat block for VRAM; 3+3 bullets |
| 11 | ⚠️ Needs work | Convert to process flow diagram |
| 12 | ⚠️ Needs work | Convert paragraph to 3 bullets; balance cards |
| 13 | ✅ Good | Remove unused `.lethal-triangle` CSS |
| 14 | ✅ Good | — |
| 15 | ✅ Good | — |
| 16 | ⚠️ Needs work | One dominant QR; test scanability |
