# Slide 7 Live Demo Redesign — Maximum Impact in 60 Seconds

## 1. Current Demo Critique (What's Weak)

### The Brief
> *"Meridian, summarise the Vienna venue email in three lines. Reply by voice."*

### Why It Undercuts the Thesis

| Flaw | Why It Hurts |
|------|-------------|
| **Passive consumption** | Summarising an email is *reading*, not *shipping*. A basic chatbot can do this. It does not prove the agent "works for you." |
| **No tangible artifact** | The audience hears audio and... that's it. Nothing persists. Nothing they can verify. For a technical crowd, audio-only proof is vapour. |
| **Does not foreshadow** | Slide 8 is the 7-level memory ladder. The demo should tee that up. Reading an email from memory does not showcase memory *architecture*. |
| **Low stakes** | A drunk founder at 22:00 has seen Siri read emails. This demo does not differentiate from a voice assistant. |
| **Not a commission** | "Summarise this" is a query. A commission is: *brief, criteria, deadline, walk away*. The speaker is still functionally waiting for a response. |

### The Honest Version of the Problem
The current demo proves that voice *works*. It does not prove that **commissioning** works. The audience will leave slide 7 thinking "cool voice interface" instead of "holy shit, he briefed an agent and kept presenting while it logged the event to persistent memory."

---

## 2. Recommended Demo Redesign

### The New Brief (Exact Words)

> *"Meridian, log tonight's talk in your memory. Event: OpenClaw Agentic Economy Night, Fiskaly Wien, 29 April 2026. One-line lesson: stop chatting, start commissioning. Save it to your dated lessons, post the file path in Discord, and confirm by voice when done."*

### Why This Brief Lands Harder

| Element | How It Proves the Thesis |
|---------|------------------------|
| **"Log in your memory"** | Active write, not passive read. The agent is *doing work*. |
| **"Save it to your dated lessons"** | Produces a persistent file in a real filesystem (`memory/*.md`). |
| **"Post the file path in Discord"** | Visual artifact on the projector. The audience *sees* `memory/2026-04-29-fiskaly.md` appear in chat. |
| **"Confirm by voice when done"** | Dual-channel delivery: text for proof, voice for theatre. |
| **Speaker walks away** | After the brief, the speaker clicks to slide 8 and keeps talking. Meridian works asynchronously. |

### Expected Agent Actions (Timeline)

| Time | Action | Channel |
|------|--------|---------|
| T+0s | Speaker delivers brief, releases PTT, walks back to slides | Voice |
| T+3s | Parakeet STT → clawfish bridge → Claude Opus parses intent | Internal |
| T+8s | Meridian writes `memory/2026-04-29-fiskaly.md` with event + lesson | Filesystem |
| T+12s | Meridian posts in Discord text: "Logged. File: `memory/2026-04-29-fiskaly.md`" | Text / Projector |
| T+15s | Kokoro TTS generates: "Done. Saved to your dated lessons." | Voice |
| T+18s | Audio plays in Discord voice channel (speaker's ear / room) | Voice |

**Total elapsed: ~18 seconds.** The speaker is already on slide 8, 20 seconds into the memory ladder explanation, when Meridian's voice comes back. The speaker pauses, nods, says "There he is," and continues.

### The Meta Layer
This demo is *self-referential*. The talk's thesis is "commission, don't chat." The demo IS a commission. And the content being saved ("stop chatting, start commissioning") reinforces the message in the agent's own memory. When slide 8 says "Memory is a 7-level ladder," the speaker can add: *"Meridian just wrote to level 3 — state files — while I was talking. That's the index pattern."*

---

## 3. Backup Plan (If Voice Fails)

### The Trigger
Voice failure is detectable within 10 seconds. If no audio comes back after the brief, the speaker does not wait. They continue presenting. At the first natural pause on slide 8 (after L1-L2, ~30 seconds in), they glance at the Discord text channel.

### Recovery Lines (Exact)

**If voice fails but text posts:**
> *"Voice went quiet — that's the venue Wi-Fi over Tailscale, same talk, different tube. But the file posted."*
> [Read Discord text aloud] *"'Logged. File: memory/2026-04-29-fiskaly.md.' He wrote that while I was talking. That's the point."*

**If both voice and text fail:**
> *"And there you see it. Voice is offline — GPU's probably loaded for critic work. That's the honest version of always-on, which is exactly what I said on the last slide. If it breaks, you see it break. That's the talk too."*
> [Click forward, keep presenting. Do not apologise. Do not try again.]

### Why This Recovery Works
It turns failure into *proof of the thesis*. The speaker said on slide 6: "When the GPU is busy doing critic work, voice goes offline. The honest version of always-on." If voice fails, the failure validates that claim. The audience sees a speaker who told the truth, and the truth happened. That builds more credibility than a flawless demo.

---

## 4. Failure Mode Matrix

| What Breaks | Probability | What to Say (Exact) | How to Recover |
|-------------|-------------|---------------------|----------------|
| **Tailscale latency spikes** | Medium | *"Tailscale's having a moment. Same stack, same truth — just slower."* | Wait 5 extra seconds. If text posts, read it. If nothing, use the GPU-loaded line above. |
| **Discord voice quality drops / robot voice** | Medium | *"That's Kokoro on a loaded GPU. The honest version of local TTS."* | Let it finish. Do not interrupt. The garbled voice proves it's real, not a pre-record. |
| **TTS latency >20 sec** | Low-Medium | *"GPU's busy. The critic is running. That's the trade-off I told you about."* | Continue through slide 8. If TTS drops mid-slide, acknowledge with a nod. Do not stop. |
| **Parakeet STT mishears the brief** | Low | *"He heard 'log' as 'dog'. That's local STT on venue Wi-Fi. Still real."* | If the response is nonsense, laugh, read the Discord text instead, say: *"And that's why I have layered memory — so the human can correct the transcript."* |
| **Meridian generates wrong content** | Low | *"He logged it. The content is his interpretation. I don't rewrite it in real-time — that's the chat trap I'm arguing against."* | Post the file path. If the lesson line is wrong, treat it as a teaching moment: *"That's a draft. The harness will calibrate it on replay."* |
| **Discord client crashes / disconnects** | Low | *"Discord dropped. The agent is still running on the Vienna box. The stack doesn't need Discord to exist."* | Switch to the backup window (pre-staged, see checklist). Or skip the demo and say: *"That's why it's a harness, not a chatbot. It survives interface failure."* |
| **GPU OOM (out of memory)** | Low | *"Thirty-two gigabytes, all in use. That's the real stack."* | No recovery possible. Use the "honest version" line and move on. |

### Graceful Recovery Principles
1. **Never apologise for the stack.** The stack is the thesis. If it breaks, the break is the thesis.
2. **Never try the same thing twice.** One brief, one chance. If it fails, move on.
3. **Always have a verbal off-ramp pre-memorised.** The "honest version" line is load-bearing.
4. **Keep presenting.** The demo is 60 seconds. The talk is 15 minutes. Do not sacrifice slide 8 for slide 7.

---

## 5. Pre-Stage Checklist Additions

Add these to the existing T-15 min checklist in `SPEAKER-NOTES.md`:

### New Items (Pre-Talk)

- [ ] **Verify Meridian can write to `memory/*.md`.** Run a test brief 30 minutes before the talk: *"Meridian, write a test line to `memory/test-vienna.md`."* Delete the test file after.
- [ ] **Pre-stage the brief content in Meridian's context.** 5 minutes before slide 7, send a silent Discord text to Meridian: *"In 5 minutes I will brief you to log tonight's talk. Event: OpenClaw Agentic Economy Night, Fiskaly Wien, 29 April 2026. Lesson: stop chatting, start commissioning."* This primes the memory without the audience seeing it.
- [ ] **Discord text channel visible on projector, not just voice channel.** The backup depends on the audience seeing text. Pin the text channel alongside the voice channel.
- [ ] **Phone on do-not-disturb except Discord.** No notifications, no calls, no Slack pings during the demo.
- [ ] **Backup Discord window open on laptop.** If the phone client fails, the laptop client is one click away.
- [ ] **Check GPU load before slide 7.** Quick text to Meridian: *"status"*. If VRAM is >31 GB, voice may be offline. Adjust expectations mentally.
- [ ] **Brief the AV tech.** Tell them: "At slide 7, I will speak into my phone for 5 seconds. Please do not cut the audio. Then I will walk back to the slides. Audio will come back from the phone 15 seconds later. That's the demo."
- [ ] **Test Tailscale ping from venue Wi-Fi.** `ping meridian-vienna` from the phone. If latency >300 ms, the voice reply will be slow. Mentally prepare the "Tailscale is having a moment" line.

---

## 6. Post-Demo Flow (Seamless Transition)

### The Exact Sequence

1. **T+0:** Speaker delivers brief, releases PTT, walks back to centre stage.
2. **T+2:** Speaker clicks to slide 8 (Memory Ladder). Begins: *"While Meridian writes that to his dated lessons, here's how he remembers things..."*
3. **T+15-25:** Meridian's voice comes back. Speaker pauses mid-sentence, nods, says: *"There he is. Saved."* [Does NOT stop to listen fully.]
4. **T+18:** Speaker continues slide 8 content: *"Memory is a seven-level ladder. Most agents stop at level one..."*
5. **T+30:** If Discord text posted, speaker gestures at the projector: *"And the file path is right there. You can see it. That's level three — state files — in real time."*

### Why This Flow Works
- The speaker **never stops presenting**. The demo is asynchronous by design.
- The voice reply is an **interruption the speaker handles gracefully**, not a pause point.
- Slide 8 content **naturally absorbs the demo output**. The memory ladder explains what just happened.
- The audience sees **continuity**: brief → walk away → agent works → agent confirms → speaker never broke stride.

### If Voice Is Late (Arrives on Slide 9 or 10)
Do not go back. Do not acknowledge late. The moment has passed. If Meridian's voice comes back during slide 9, the speaker can say: *"And there's Meridian, catching up. Asynchronous by design."* Then ignore it and continue.

---

## 7. Length Recommendation

**The demo should NOT be shortened.** 60 seconds is already tight. The current design (brief + walk away + async reply) uses roughly 18 seconds of actual demo time and 42 seconds of the speaker presenting while the demo resolves. This is the correct ratio.

**Do not lengthen it either.** The talk is 16 slides for 15 minutes. Every second over 60 on slide 7 steals from slide 8 (Memory Ladder), which is the heaviest content slide and needs its full 80 seconds.

**The 60-second envelope should be:**
- 5 sec: Speaker briefs Meridian
- 3 sec: Speaker walks back, clicks to slide 8
- 52 sec: Speaker presents slide 8 while Meridian works asynchronously
- ~18 sec into slide 8: Meridian's voice reply lands
- Speaker acknowledges in <3 sec, continues

This makes the demo feel like **part of the talk's rhythm**, not an interruption. That's the "commission, don't chat" pattern in its purest form.

---

## 8. Summary: What Changes on the Slide

### Slide 7 HTML Changes

Replace the three demo cards with:

```html
<div class="card-grid card-grid-3 mt-3" style="max-width:1050px">
  <div class="card card-glow-orange" style="padding:14px">
    <h3 style="font-size:0.9rem"><span class="text-orange">The brief I'll say</span></h3>
    <p style="font-size:0.78rem;font-style:italic">"Meridian, log tonight's talk in your memory. Event: OpenClaw Agentic Economy Night, Fiskaly Wien, 29 April 2026. One-line lesson: stop chatting, start commissioning. Save it, post the file path in Discord, and confirm by voice."</p>
  </div>
  <div class="card card-glow-purple" style="padding:14px">
    <h3 style="font-size:0.9rem"><span class="text-purple">What he'll do</span></h3>
    <p style="font-size:0.78rem">Write to his dated lessons in <span class="mono">memory/*.md</span>, post the file path in Discord text, run TTS, and drop the confirmation into the voice channel.</p>
  </div>
  <div class="card card-glow-cyan" style="padding:14px">
    <h3 style="font-size:0.9rem"><span class="text-cyan">If the demo gods say no</span></h3>
    <p style="font-size:0.78rem">Voice goes offline when the GPU is loaded for critic work. That's the honest version of always-on. The text post still lands. If both fail, you saw it break. That's the talk too.</p>
  </div>
</div>
```

### Speaker Notes Changes (Slide 7)

Replace the slide 7 section in `SPEAKER-NOTES.md` with:

```markdown
## Slide 7 — LIVE DEMO (~60 sec)

> "I'll show you. Pinning Discord on the projector now."

**Action:**
1. Switch projector to Discord text + voice channel
2. Press push-to-talk
3. Say out loud: *"Meridian, log tonight's talk in your memory. Event: OpenClaw Agentic Economy Night, Fiskaly Wien, 29 April 2026. One-line lesson: stop chatting, start commissioning. Save it, post the file path in Discord, and confirm by voice when done."*
4. Walk back to slide. Click forward to slide 8.
5. Continue talking through slide 8 — Meridian's reply comes back asynchronously. Acknowledge with a nod: "There he is."
6. If text posted, gesture at projector: "File path is right there."

**If voice fails:**
- If text posted: *"Voice went quiet — that's the venue Wi-Fi over Tailscale, same talk, different tube. But the file posted."* Read the Discord text aloud.
- If both fail: *"Voice is offline — GPU's probably loaded for critic work. That's the honest version of always-on, which is exactly what I said on the last slide. If it breaks, you see it break. That's the talk too."* Click forward. Do not try again.

**Pre-stage (T-5 min):**
- Send silent text to Meridian priming the event name and lesson.
- Verify write access to `memory/*.md` with a test brief (delete after).
- Check GPU load. If VRAM >31 GB, voice may be offline. Mentally prepare the "honest version" line.
```

---

## 9. Risk-Adjusted Demo Decision Tree

```
T-5 min: Check GPU load
  |
  +-- VRAM < 30 GB (voice likely works)
  |     --> Run full demo: voice + text dual-channel
  |
  +-- VRAM 30-31.5 GB (voice marginal)
  |     --> Run demo but pre-memorise "honest version" line
  |     --> If voice fails, text is the primary output
  |
  +-- VRAM > 31.5 GB or Meridian unresponsive
  |     --> Skip live brief entirely
  |     --> Say: "Meridian's GPU is fully loaded right now — critic running, voice offline. 
  |          That's the honest version of always-on. The file is still there." 
  |     --> Show pre-staged Discord text from the priming message.
  |     --> This is actually a STRONGER demo of "commission, don't chat" — 
  |          the agent was already working before you got on stage.
```

---

## 10. Final Sanity Check

| Question | Answer |
|----------|--------|
| Does this prove "commission, don't chat"? | **Yes.** The speaker gives a brief with a deliverable, walks away, and keeps presenting. The agent works asynchronously. |
| Is it real? | **Yes.** All systems exist. `memory/*.md` is a real path. The write is a real filesystem operation. |
| Is it under 60 seconds? | **Yes.** The brief is 5 seconds. The rest is the speaker presenting while the agent works. |
| Can it break gracefully? | **Yes.** Three tiers of backup: voice+text → text only → verbal off-ramp. |
| Does it foreshadow slide 8? | **Yes.** The agent writes to "dated lessons" — level 3 of the memory ladder. |
| Is it compelling to a drunk founder? | **Yes.** They see a file path appear in chat in real time while the speaker keeps talking. That's agency, not a voice trick. |

---

*Document generated for the 29 April 2026 Fiskaly Wien talk. All claims are traceable to the Meridian stack as documented in `KIMI-SWARM-PROMPT.md`.*
