# Stage Manager Timing Report
## "Quit chatting with your agents" — Fiskaly Wien, 29 April 2026
### Prepared by: Stage Manager (Time-Keeper Role)

---

## Executive Verdict: OVERBUDGET

| Metric | Value |
|--------|-------|
| Hard budget | 15:00 (900s) |
| Claimed content time | 14:40 (880s) |
| **Realistic content time** | **16:45 (1005s)** |
| **+ Transition pauses** | **~40s** |
| **TOTAL REALISTIC** | **17:25 (1045s)** |
| **Overrun vs budget** | **+2:25 (+145s)** |
| Overrun percentage | **16% over budget** |

**Bottom line:** Even with perfect delivery and no demo hiccups, this deck realistically needs **17+ minutes**. The 16 x 55s math is fiction. The speaker will run long unless aggressive cuts are made proactively, not reactively.

---

## 1. Full Timing Table

| Slide | Title | Claimed | **Realistic** | Cum (Claim) | **Cum (Real)** | Flag | Notes |
|:-----:|-------|:-------:|:-------------:|:-----------:|:--------------:|:----:|-------|
| 1 | Title | 15s | **15s** | 0:15 | **0:15** | | Short intro, hard to stretch |
| 2 | The Dark Factory | 60s | **65s** | 1:15 | **1:20** | | "Let the image breathe" beat = +5s |
| 3 | Five Levels of Automation | 75s | **80s** | 2:30 | **2:40** | | 6 cards to scan, visual cue = +5s |
| 4 | The Chat Trap | 45s | **50s** | 3:15 | **3:30** | | "Left by now" pause is load-bearing |
| 5 | Commission, Don't Converse | 45s | **45s** | 4:00 | **4:15** | OK | Punchy, hits target |
| 6 | Voice: the unlock | 75s | **80s** | 5:15 | **5:35** | | Stack diagram + 3 cards + caveat = +5s |
| 7 | **LIVE DEMO** | 60s | **90s** | 6:15 | **7:05** | **WILL RUN LONG** | See Demo Analysis below |
| 8 | Seven Levels of Memory | 80s | **95s** | 7:35 | **8:40** | **WILL RUN LONG** | Densest slide per brief. 7 pipeline steps. |
| 9 | Anismin | 70s | **85s** | 8:45 | **10:05** | **WILL RUN LONG** | 3-card grid + refusal pause = +15s |
| 10 | Meridian | 70s | **80s** | 9:55 | **11:25** | **LIKELY LONG** | Laugh line wait = +10s |
| 11 | Meta Harness | 60s | **75s** | 10:55 | **12:40** | **WILL RUN LONG** | 6-card grid, densest per brief = +15s |
| 12 | War Story | 60s | **70s** | 11:55 | **13:50** | **LIKELY LONG** | "Slow on 'rewrite'" beat = +10s |
| 13 | Lethal Trifecta | 45s | **50s** | 12:40 | **14:40** | | Triangle visual = +5s |
| 14 | In Your Messenger | 45s | **45s** | 13:25 | **15:25** | | Straightforward |
| 15 | Bridge to Web4 | 45s | **50s** | 14:10 | **16:15** | | Handoff gesture = +5s |
| 16 | Get Connected (CTA) | 30s | **30s** | 14:40 | **16:45** | | QR codes are static |
| — | **Transition pauses** (15x) | 0s | **~40s** | — | **~17:25** | NOT BUDGETED | ~2.5s each, slide 7→8 alone = 8s |

**Key columns explained:**
- **Claimed** = Speaker's estimate from SPEAKER-NOTES.md
- **Realistic** = Stage manager's estimate based on word count, visual density, pause cues, and live delivery friction
- **Cum (Real)** = Running total at realistic pace — where you actually are on the clock

---

## 2. "Will Run Long" Flags Per Slide

| Slide | Risk Level | Why It Will Run Long |
|:-----:|:----------:|----------------------|
| **7** | **CRITICAL** | 60s demo budget is fantasy. Wi-Fi + Tailscale + STT→LLM→TTS round-trip = 90s minimum. See Demo Analysis. |
| **8** | **HIGH** | Heaviest slide per brief. 7 memory levels in a pipeline. 140 words of notes. Audience needs time to parse. |
| **9** | **HIGH** | 145 words + 3-card grid + emotional "refusal lands" pause. This slide has a soul; you can't rush it. |
| **11** | **HIGH** | 5 mechanisms + "what it is not" card across 6 cards. Brief explicitly flags as densest. |
| **10** | **MEDIUM** | 135 words + laugh line wait. If the room doesn't laugh, the wait becomes awkward dead air. |
| **12** | **MEDIUM** | "Slow on 'rewrite'" cue means deliberate pacing. The auth-gateway anecdote is a second story within one slide. |
| **2, 3, 6** | LOW | Each ~5s over. Acceptable variance. |

**Slides that will NOT run long:** 1, 5, 14, 16 — these are already tight or can be delivered at claimed pace.

---

## 3. Demo Timing Reality Check (Slide 7)

**The claim:** 60 seconds for a live voice demo over venue Wi-Fi + Tailscale.
**The reality:** Not even close.

### Step-by-step demo timeline:

| Step | Action | Minimum | Likely | Maximum |
|------|--------|:-------:|:------:|:-------:|
| 1 | Speaker intro line | 5s | 5s | 5s |
| 2 | Switch projector / verify Discord visible | 10s | 15s | 25s |
| 3 | Press PTT, compose | 3s | 5s | 10s |
| 4 | Speak the 23-word brief | 8s | 8s | 8s |
| 5 | **Network round-trip** (Tailscale + Wi-Fi + STT + LLM + TTS) | 15s | 25s | 60s+ |
| 6 | Walk back to lectern | 5s | 5s | 8s |
| 7 | Click to slide 8 | 2s | 2s | 3s |
| 8 | Start slide 8 intro while waiting | 10s | 15s | 20s |
| 9 | Meridian's reply arrives in speaker's ear | — | 10s | 30s |
| 10 | Acknowledge: "There he is." | 3s | 3s | 5s |
| | **TOTAL (if voice works)** | **61s** | **93s** | **171s** |
| | **+ Voice fails → DM backup** | | **+20s** | **+30s** |

### Why 60s is impossible:
1. **Venue Wi-Fi at a free sponsored event** = unpredictable contention, especially at 22:00 when everyone's been on their phones for 2+ hours
2. **Tailscale adds a VPN hop** = extra 20-50ms minimum, more if DERP relay kicks in
3. **Claude Opus 4.7 reasoning time** for email summarisation = 10-20s even with fast path
4. **Kokoro TTS generation** = 5-10s for 3 lines of summary
5. **Speaker walks back to lectern** = 5s of physical movement that can't be compressed

### Verdict:
| Scenario | Time | Probability |
|----------|------|:-----------:|
| Best case (everything fast) | 75s | 20% |
| Realistic average | **90s** | 50% |
| Voice fails, DM backup | 110s | 25% |
| Network flaky, long wait | 150s+ | 5% |

**Recommendation:** Budget **90s** for the demo. If you only have 60s, skip the live voice and use the DM card as a static "this is what he would have said" display. The credibility hit from a flaky demo is worse than no demo.

---

## 4. Transition Pauses: Are They Accounted For?

**Answer: NO. Zero seconds budgeted. Realistically ~40 seconds needed.**

The speaker notes say: "Timer starts when you click slide 2. 15:00 budget." But:

- 15 transitions between 16 slides
- Even a fast click-forward takes **2 seconds**
- Some transitions have explicit cues that take longer:
  - Slide 3→4: "highlight L2 and L4 cards visually" = **3s**
  - Slide 5→6: "VS card resolves, point at right column" = **3s**
  - Slide 6→7: "Speaking of which..." = **2s**
  - **Slide 7→8: Walk back, click, start talking = 8s (MAJOR)**
  - Slide 15→16: "turn slightly toward Ed, handoff gesture" = **5s**

**Total transition overhead: ~40 seconds minimum**

This means even if the speaker hits EVERY claimed time perfectly (impossible), the deck still needs **880s + 40s = 920s = 15:20**. The budget is already blown before the first word is spoken.

---

## 5. Cut Hierarchy (What Drops First, Second, Third)

The current notes say: "If you're past slide 8 with under 7 minutes left, skip slide 13."

**This is a band-aid, not a fix.** Skipping slide 13 saves only 45s. When you're 100s+ behind, that's insufficient.

### Recommended Cut Hierarchy:

| Priority | Slide | Content Action | Time Saved | Cumulative | Trigger Point |
|:--------:|-------|----------------|:----------:|:----------:|---------------|
| **1st** | 13: Lethal Trifecta | **Skip entirely** | 50s | 50s | At 9:00 elapsed, on slide 8 |
| **2nd** | 12: War Story | **Skip entirely** OR deliver as one-liner | 70s | 120s | At 10:00 elapsed, on slide 9 |
| **3rd** | 9: Anismin | **Compress to refusal quote only** | 65s | 185s | At 11:00 elapsed, on slide 10 |
| **4th** | 4: Chat Trap | **Compress to headline + right card only** | 30s | 215s | At 12:00 elapsed, on slide 11 |
| **LAST** | 7: Demo | **Go static** (no live voice) | 60s | 275s | If network looks bad at setup |

### Why this order:
1. **Slide 13 (Lethal Trifecta)** — The audience is technical; they know security risks. The "what it is not" card on slide 11 already covers safety mindset. This is the easiest cut with lowest narrative damage.
2. **Slide 12 (War Story)** — The shim-snapshot quote is strong, but if you've already established credibility via slides 9-10, the war story becomes "nice to have." The auth-gateway anecdote is from a prior talk anyway.
3. **Slide 9 (Anismin)** — Meridian was just demo'd live; he's fresher in memory. Anismin's most important beat is the refusal quote, which can be delivered in 20s. The heartbeat/ops details are impressive but compressible.
4. **Slide 4 (Chat Trap)** — This is emotional hook territory. Only cut if desperate. The title already says "quit chatting" — the hook is established.
5. **Demo goes static** — If the network looks flaky during setup (slide 6), abandon ship before you're committed. A failed live demo kills more credibility than a skipped one.

---

## 6. Panic Protocol: 8:00 Elapsed, Only on Slide 5

**Scenario:** The clock shows 8:00. You just advanced to slide 5 (Commissioning). You should be on slide 9.

**Reality:** 7:00 remains. 12 slides left (5 through 16). Needed pace: 35s/slide. Impossible for remaining density.

### DO NOT speed-talk.
The audience has been drinking for 2 hours. Speed kills credibility. Compression is better than acceleration.

### EXECUTE IMMEDIATE CUTS:

| Slide | Normal Time | Panic Time | Savings |
|-------|:-----------:|:----------:|:-------:|
| 5 Commission | 45s | 25s (headline + right card only) | 20s |
| 6 Voice | 80s | 50s (stack diagram only) | 30s |
| 7 Demo | 90s | **0s — SKIP LIVE** (static DM card) | 90s |
| 8 Memory | 95s | 50s (L1, L4, L7 only) | 45s |
| 9 Anismin | 85s | 30s (refusal quote only) | 55s |
| 10 Meridian | 80s | 45s ("hybrid not zero-cloud" + stack) | 35s |
| 11 Meta Harness | 75s | 40s (list the 5 mechanisms) | 35s |
| 12 War Story | 70s | **0s — SKIP** | 70s |
| 13 Lethal Trifecta | 50s | **0s — SKIP** | 50s |
| 14 Messenger | 45s | 45s (deliver as-is) | 0s |
| 15 Bridge to Web4 | 50s | 50s (deliver as-is) | 0s |
| 16 CTA | 30s | 30s (deliver as-is) | 0s |
| | **TOTAL** | **~335s = 5:35** | **~430s saved** |

**You finish at ~13:35.** Clean. CTA intact. Ed gets his handoff. The thesis survives because slides 1-3 (framing) and 14-16 (OpenClaw handoff) are preserved.

---

## 7. Closing CTA at 14:30: Realistic?

**Answer: NO. The CTA will start at ~16:15 under realistic pacing. That's 1:15 past the 15:00 hard stop.**

### The math:
- Slide 16 (CTA) starts at realistic cumulative: **~975s = 16:15**
- The CTA itself needs **30s**
- Walk-off + applause needs **15s**
- Total to clear the stage: **~17:00**

### The 14:30 rule is impossible because:
1. It assumes the claimed 880s total (not the realistic 1005s)
2. It ignores the ~40s of transition pauses
3. It assumes the demo takes 60s (not 90s)
4. It assumes zero slides run long

### Recommendation:
- **Target CTA start at 14:00, not 14:30** (or even 13:30 to be safe)
- If at 13:00 you're not on slide 12, trigger **Tier 1 + Tier 2 cuts immediately**
- Keep the "walk off at 15:00 even if mid-sentence" rule — it's good discipline
- Add a stage manager note: **If CTA hasn't started by 14:45, skip to slide 16 immediately** and drop whatever slide you're on

---

## 8. What If the Speaker Is Behind at Key Checkpoints?

| Checkpoint | Should Be | If You're Here Instead | Action |
|:----------:|:---------:|:---------------------:|--------|
| 3:00 | Slide 4 (Chat Trap) | Slide 3 or earlier | Compress slide 4 to 30s. You're fine. |
| 5:00 | Slide 6 (Voice) | Slide 5 or earlier | On track. No action. |
| 7:00 | Slide 8 (Memory) | Slide 7 (demo running) | Demo budget is 90s. If it hasn't started, go static. |
| **9:00** | Slide 10 (Meridian) | **Slide 8 or 9** | **Trigger Tier 1: Skip slide 13.** |
| **11:00** | Slide 12 (War Story) | **Slide 10 or 11** | **Trigger Tier 2: Skip slide 12.** |
| **13:00** | Slide 14 (Messenger) | **Slide 12 or 13** | **Trigger Tier 3: Compress Anismin. Skip slide 13.** |
| **14:00** | Slide 16 (CTA) | **Slide 14 or 15** | **PANIC: Jump to slide 16 immediately.** |

---

## 9. Overall Timing Verdict: OVERBUDGET

| Criterion | Assessment |
|-----------|:----------:|
| Fits in 15:00 as claimed? | **NO** |
| Fits in 15:00 with minor cuts? | **NO** |
| Fits in 15:00 with Tier 1 + Tier 2 cuts? | **YES** |
| Demo timing realistic? | **NO** — 60s claim is 90s reality |
| Transition pauses accounted? | **NO** — 40s completely unbudgeted |
| Closing CTA at 14:30 realistic? | **NO** — CTA starts at 16:15 |
| Skip-slide-13 rule sufficient? | **NO** — needs earlier + deeper cuts |
| Talk salvageable with cuts? | **YES** — spine is strong, middle is compressible |

### The Three Things That Must Change Before Stage:

1. **Demo budget: 60s → 90s.** Adjust all downstream slide timing accordingly. If the demo hasn't delivered audio by 90s, pivot to DM backup without apology.

2. **Cumulative checkpoint targets must be revised.** The speaker is aiming for a 14:40 CTA that will never happen. Publish realistic checkpoints (see Section 8).

3. **Pre-emptive cut decision tree.** Don't wait until slide 8 to decide about slide 13. The speaker should decide at slide 6 whether Tier 1 cuts will be needed, based on how the first 5 slides felt.

### What Works in the Current Plan:
- The "walk off at 15:00 even if mid-sentence" discipline is excellent. Keep it.
- The backup beats (if finishing early) are good insurance.
- The Q&A trap answers are concise and won't balloon time.
- The reorder panel in slides.html means the speaker can hide slides in real-time if needed.

---

## Appendix: Recommended Revised Time Targets (For the Speaker)

Print this. Tape it to the lectern.

| Slide | Start By | Hard Limit |
|:-----:|:--------:|:----------:|
| 1 | 0:00 | 0:15 |
| 2 | 0:15 | 1:20 |
| 3 | 1:20 | 2:40 |
| 4 | 2:40 | 3:30 |
| 5 | 3:30 | 4:15 |
| 6 | 4:15 | 5:35 |
| 7 (demo) | 5:35 | **7:05** |
| 8 | 7:05 | 8:40 |
| 9 | 8:40 | 10:05 |
| 10 | 10:05 | 11:25 |
| 11 | 11:25 | 12:40 |
| 12 | 12:40 | 13:50 |
| 13 | 13:50 | 14:40 |
| 14 | 14:40 | 15:25 |
| 15 | 15:25 | 16:15 |
| 16 (CTA) | 16:15 | **16:45** |
| **Walk off** | **—** | **15:00** |

Wait. That's still 16:45. **This proves the point: the deck is overbudget.**

**To fit in 15:00, you MUST cut ~105s from the realistic estimate. Here's the minimal cut set:**

| Cut | Savings |
|-----|:-------:|
| Demo: 90s → 75s (aggressive, risky) | 15s |
| Slide 8: 95s → 80s (L1, L4, L7 only) | 15s |
| Slide 9: 85s → 60s (compress ops detail) | 25s |
| Slide 10: 80s → 65s (cut laugh line wait) | 15s |
| Slide 11: 75s → 60s (faster through mechanisms) | 15s |
| Slide 12: 70s → 55s (drop auth-gateway anecdote) | 15s |
| Transitions: 40s → 30s (rush them) | 10s |
| **TOTAL SAVED** | **~110s** |

With these cuts, you finish at 15:00. But every one of these cuts hurts the talk. The better answer: **accept that this is a 17-minute talk and negotiate with the organisers, or cut slides 12 and 13 proactively.**

---

*Report prepared: Stage Manager analysis*
*Source files: SPEAKER-NOTES.md, slides.html, KIMI-SWARM-PROMPT.md*
