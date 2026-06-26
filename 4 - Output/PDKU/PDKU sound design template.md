Status: working doc
Tags: [[music]], [[hyperstition]], [[memes]]
Based on: [[Audio virology and memetic contagion]], [[Sonic Warfare - Steve Goodman]]

---

# PDKU sound design template

reusable framework for 31 days of daily shortform video. the principle: every video is an engram delivery system. the content is the message. the sound is the infection.

the sound design operates on a different layer than the script. the script speaks to the mind. the sound writes itself into the nervous system. they should never say the same thing at the same time — they converge, diverge, contradict, and that irresolvable tension is what keeps the viewer's body processing.

---

## the five layers

build every video from these five layers. not all need to be present. the minimum is layers 1 + 2.

### 1. THE BODY (sub-bass, 30-80Hz)

the foundation the viewer *feels*, not hears. phone speakers won't reproduce it; earbuds and headphones will. this means your content automatically rewards the closer, more intimate listening mode — headphones on = full experience, speaker = partial. that's a feature, not a bug.

**palette:**
- single sub pulse (~40Hz, 200ms, hard transient) — the heartbeat. use as punctuation
- low drone (55-80Hz, constant, -18dB below voice) — the room. creates sense of enclosure, of being *inside* something
- sub pulse at breathing tempo (~0.8Hz, ~40Hz) — arousal/entrainment. use when the content turns intimate or confrontational

**in ableton:**
- operator or wavetable. pure sine or triangle. no harmonics — the sub should be felt, never identified as a musical element
- sidechain to your voice (light, 2-3dB, slow release) so the sub ducks when you speak and swells in your pauses. the pauses become physical events
- bus compressor (glue compressor, slow attack, 4:1) to keep the sub consistent

### 2. THE VOICE

the only element the viewer consciously tracks. everything else is subliminal scaffolding for this.

**processing chain:**
- close-mic (LDC, 3-6 inches). the proximity effect adds low-end warmth that reads as intimacy/authority
- light compression (LA-2A style, 3-4dB GR) to keep dynamics controlled without killing the life
- room reverb — this is the key expressive tool. automate it across the video:
  - large/cathedral = distance, authority, uncanny (valhalla supermassive, decay 4-8s, high dampening)
  - small/warm = intimacy, closeness, seduction (valhalla room or stock reverb, decay 0.8-1.2s)
  - mismatch the reverb to the visual for subliminal unease (close-up face + cathedral reverb = the viewer's spatial processing flags *wrong*)
- NO de-esser on the initial breath/hook. the sibilance is part of the ASMR proximity trigger

**delivery modes:**
- whisper-close: for hooks, for vulnerability, for the moment before the argument
- direct-present: for the core argument, the thesis, the part you need them to remember
- command: for the turn, for the provocation, for the line that stings. more chest, less air, less reverb

### 3. THE GLITCH (high-frequency artifacts, 8-15kHz)

the knife that cuts the intimacy. prevents the viewer from settling into comfort. every time the sound starts to feel safe, a glitch reminds the body: this is not safe. this is not normal content.

**palette:**
- ring-modulated transients (150-300ms)
- bitcrushed micro-bursts
- digital artifacts, buffer glitches
- sounds that *almost* sound like notification pings but aren't (parasitize conditioned dopamine response)

**in ableton:**
- corpus or frequency shifter on an impulse. or: record actual notification sounds and process them through erosion/redux until they're unrecognizable but still trigger the association
- pan randomly. the glitches should appear from different spatial positions — the viewer can't localize the threat
- irregular spacing. never rhythmic. 2-6 seconds apart. randomize with a probability-gated midi clip or just place by hand

### 4. THE HARMONIC (mids, 200-800Hz)

the emotional undertow. enters late in the video, once the argument has built momentum. a single sustained tone that implies a second presence — a voice that isn't speaking, a body that isn't visible.

**palette:**
- sine + slight chorus/detuning. not clean, not dirty — in between. uncanny
- minor key for tension/unresolved. the tone should *not* resolve. it hangs
- binaural detuning (e.g. 200Hz L, 204Hz R) for theta-wave induction — creates suggestibility, dreamlike attention

**in ableton:**
- operator, two oscillators slightly detuned (2-6 cents). or: wavetable with slow LFO on pitch, <1Hz rate, tiny depth
- automate volume — the harmonic should creep in, not enter. the viewer shouldn't be able to identify the moment it started
- for the binaural: two separate sine oscillators panned hard L/R with a 3-5Hz frequency difference. only works on headphones. on speakers it just sounds like a single tone with slight wobble — still beautiful, still works, just loses the theta induction

### 5. THE VOID

the most important element. the thing that isn't there.

**techniques:**
- **the mid-scoop**: at climactic moments, automate an EQ to cut the 200-4kHz range. leave only sub-bass and high harmonics. the viewer's perception falls into the empty space between body and mind. they fill it with their own feeling. that's where the engram writes deepest
- **the hard silence**: at the end of every video, 0.5-1.5 seconds of absolute silence after a hard cut. the sudden absence of all sonic information is a physical event — like pressure dropping. the ears ring. the nervous system, which had been processing contradictory signals, has nothing to resolve. that silence is what they remember
- **the missing beat**: in sections with micro-percussive artifacts, occasionally leave a gap where the next click should be. the brain predicts it, doesn't get it, and the surprise of absence is more attention-grabbing than any sound

---

## the arc

every video follows the same emotional-sonic arc, regardless of content. this becomes the recurring signature — after a few days, the viewer's body *recognizes the shape* before the content starts. they begin to entrain to you.

```
HOOK (0-1.5s)     breath + sub + glitch. contradictory signals. thumb stops.
VOICE (1.5-6s)    thesis enters. uncanny reverb. drone underneath. body says: wrong but stay.
BUILD (6-18s)     drone rises. artifacts enter. binaural. pressure builds. body tenses.
TURN (18-26s)     drone drops. space contracts. voice gains authority. harmonic enters.
CUT (26-30s)      mid-scoop. silence. the engram writes.
```

the content fills this shape differently each day. the shape stays. the shape IS the brand. not a logo, not a color, not a face — a somatic pattern the viewer's nervous system learns to expect and crave.

---

## ableton session template

set up a default session with these tracks:

```
1. VOX         — voice, processing chain as above
2. SUB         — sub-bass layer (operator, sine, sidechain to VOX)
3. DRONE       — low drone (wavetable or serum, automate pitch)
4. GLITCH      — high-frequency artifacts (rack with corpus/redux/freq shifter)
5. HARMONIC    — sustained tone (operator, 2 osc detuned, slow automation)
6. BINAURAL    — theta induction (2 sines, hard panned, 3-5Hz difference)
7. BUS         — master bus compression, limiter, final EQ with automatable mid-cut
```

save this as `_PDKU_TEMPLATE.als`. duplicate for each day. the template is the protocol. the protocol produces the subjectivity.

---

## mixing principles

- voice is the only element that should be consciously audible. everything else operates below attention
- if you can identify the sub-bass as "a bass sound," it's too loud. it should be felt as pressure, not heard as frequency
- if you can identify the drone as "a note," it's too loud. it should be felt as atmosphere
- the glitches should be startling but not painful. the viewer shouldn't flinch — they should get a micro-jolt of alertness, like a muscle twitch
- the harmonic should be felt as *presence* — the sense that someone else is in the room
- test on earbuds (airpods), over-ear headphones, AND phone speaker. the phone speaker version should still work as a stripped-back experience — voice + glitches + void. the sub and binaural are headphone bonuses

---

## the virus

from goodman: *"the question is: what virus are you carrying?"*

this template is a delivery system. the content is the payload. the sound design is the vector. the viewer's nervous system is the host. every day, for 31 days, you write the same somatic pattern into a growing audience. the pattern becomes a habit becomes a craving becomes an identity. that's not metaphor. that's how memetic contagion works at the protocol level.

the only question is what you put inside it.

---

Connects to: [[Audio virology and memetic contagion]], [[Sonic Warfare - Steve Goodman]], [[Laozi as the original troll]], [[Music as cosmotechnics — the tao of alignment]]
