Tags: [[value alignment]], [[rationalism]], [[recursive self-improvement]], [[exocapitalism]]

---

## context

had a DM conversation with lumpen (@lumpenspace) on june 14 2026 where i said some things about yudkowsky / MIRI / alignment that turned out to be oversimplified or wrong. lumpen lives with @jessi_cata, the last mathematician who worked at MIRI. they shared john david pressman's (@jd_pressman) may 13 2025 tweet thread analyzing yudkowsky's actual AI views. i need to get sharp on this before pdku.

this note is me processing what i got wrong, what lumpen got right, and what the actual positions are. sources cited where i have them.

---

## what i said vs what's actually true

### "alignment is extremely hard and we dont have enough time"

i said this as if it was yudkowsky's position. it's CLOSE but it undersells how dark his actual view is.

what yudkowsky actually says: alignment is so hard that nobody currently knows how to do it, nobody is on track to figure it out in time, and the default outcome is that everyone dies. not "hard but possible if we try." more like "we are probably all going to die and the best you can do is increase the log-odds of survival."

real quotes:
- "it's obvious at this point that humanity isn't going to solve the alignment problem, or even try very hard, or even go out with much of a fight." — *death with dignity* post, LessWrong, april 1 2022 (not a joke despite the date)
- "I think we are all going to die" — dwarkesh patel podcast, 2023
- "I basically don't see on-model hopeful outcomes at this point" — same podcast

so lumpen was more right than i was. yudkowsky doesn't frame alignment as a hard-but-solvable engineering problem. he frames it as effectively impossible under current conditions and timelines. not mathematically impossible in principle — but so far beyond our current understanding that the distinction barely matters.

→ i was doing the thing where you soften someone's position to make it easier to defend. need to actually sit with his despair instead of diluting it.

### "i agree with 'if anyone builds it NOW, everyone dies'"

this is LITERALLY the title of yudkowsky & nate soares' 2025 book: *if anyone builds it, everyone dies* (Little, Brown and Company, september 16 2025). made the NYT best seller list. the full version from his TIME op-ed (march 29 2023):

"the most likely result of building a superhumanly smart AI, under anything remotely like the current circumstances, is that literally everyone on Earth will die."

i used this phrase in my de standaard piece too. so i'm already aligned with the conclusion. but i was defending it as "halt now, do alignment research, build later" — which is NOT yudkowsky's position. he doesn't think alignment research alone will get us there. MIRI stopped doing alignment research. let that sink in.

### "99% alignment is better than 98%"

this is where i was most naive. in yudkowsky's framework, alignment isn't a percentage. a superintelligence that is 99% aligned is still a superintelligence that kills everyone — the 1% isn't a tolerable failure rate, it's a paperclip-maximizer failure mode. the whole point is that partial alignment with a system smarter than you is not alignment at all.

→ lumpen was right to push back on this.

---

## MIRI — what actually happened

the timeline lumpen gave me is correct:

- **2000-2020**: MIRI does alignment research. yudkowsky writes the sequences, the rationalist community forms around LessWrong, MIRI publishes technical papers on decision theory, agent foundations, logical uncertainty.
- **april 2022**: yudkowsky publishes "death with dignity" on LessWrong. the strategy: the field has failed, alignment research hasn't worked, we should still try but with the understanding that we're probably going to die. "you change your goal from 'humanity survives this century' to 'my actions increase the log-odds that humanity survives this century.'"
- **march 2023**: yudkowsky's TIME op-ed: "pausing AI developments isn't enough. we need to shut it all down." he refused to sign the FLI 6-month pause letter because it asked for TOO LITTLE. he called for an indefinite worldwide moratorium, tracking all GPU sales, and being willing to airstrike rogue datacenters.
- **january 4 2024**: MIRI strategy update. nate soares wrote: "alignment research has, at this point, largely failed, in the sense that neither Eliezer nor I have sufficient hope in it." they pivot to policy, communications, governance. de facto shutdown of alignment research.
- **2024-2025**: MIRI operates primarily as an advocacy/policy org. $16M in reserves, $6.5-7M annual expenses. still supports some alignment research but the emphasis is on getting governments to suspend frontier AI research.

→ so lumpen's claim that "MIRI doesnt want to do alignment. they even shut down as a research centre, and switched to ai freeze advocacy officially, in 2023" is TRUE. the exact date was january 2024 for the formal strategy update, but the shift started in 2022.

→ lumpen's framing that yudkowsky "pivoted to 'we need to stop ai to save the world' only after failing at 'we need to build ai to save the world'" is ALSO basically true, chronologically. yudkowsky spent decades trying to solve alignment theoretically. he concluded it wasn't working. he pivoted to "stop everything." that's not necessarily dishonest — it could be an honest update on evidence. but it IS the trajectory.

---

## yudkowsky on neural networks

this is the part that surprised me most.

in 2008, yudkowsky was dismissive of neural nets. from the sequences: "Not to mention that neural networks have also been 'failing' (i.e., not yet succeeding) to produce real AI for 30 years now." he mocked people who kept returning to neural nets as a cached thought, calling it a "successful marketing campaign thirty goddamned years ago."

his vision was something more like a legible cognitive architecture — understanding intelligence at a fine-grained theoretical level and building it from understood parts. pressman's analysis (see below) suggests something closest to a Monte Carlo AIXI approximation. his four food groups for an AI programmer: cognitive science, evolutionary psychology, information theory, computer programming.

he expected a small team with modest compute to achieve AGI by understanding the structure of intelligence deeply enough. the "brain in a box in a basement." he predicted superintelligence between 2008-2010 (in 2001).

by 2023, on the dwarkesh podcast: "GPT-4 got further than I thought that stack more layers was going to get... I am no longer willing to say that GPT-6 does not end the world."

→ so he was WRONG about neural nets. spectacularly wrong. he hasn't issued a formal retraction. his update has been gradual — acknowledging the unexpected effectiveness while maintaining his interpretability concerns were validated (opaque systems ARE hard to align, which is his whole point now).

→ lumpen's claim that "eliezer stated publicly that neural networks could never lead to agi; his whole vision of the future was predicated on a legible general ai system some guys would figure out on their basement computer" is TRUE for his earlier views. he has since updated, but the pivot matters.

---

## pressman's analysis (may 13 2025 tweet thread)

john david pressman (@jd_pressman) wrote a long clarification of his understanding of yudkowsky's AI views after yudkowsky accused him of being "too bad at handling abstractions to ever understand [Yudkowsky's position]." pressman wrote the essay "why cognitive scientists hate LLMs."

key points from pressman:

1. yudkowsky never supported GOFAI in the narrow sense of "formal logic programs operating on suggestively named LISP tokens." he explicitly rejected that.

2. yudkowsky admired marcus hutter's AIXI formalization and jaynes' *probability theory: the logic of science*. he was bayesian, not symbolic-AI in the crude sense.

3. but his approach was still fundamentally theoretical — he wanted to understand intelligence at the level of clean mathematical detail, like understanding arithmetic algorithms. from his early (now deprecated) work: "the gap between the higher level and the lower level is not absolute and uncrossable."

4. yudkowsky's AI design was SECRET. pressman notes: "Eliezer Yudkowsky's AI plan after his early career is fundamentally secret. This man has written a long post about how I am apparently incapable of comprehending basic abstractions because I (supposedly) failed to correctly guess the exact details of his SECRET AI PLAN TO SAVE THE WORLD."

5. pressman thinks yudkowsky's sketch was closest to a modular system with legible bayesian cognitive architecture, something like AIXI-approximate but with safety properties. NOT formal logic, but also NOT "train a giant neural net and hope for the best."

6. the deeper argument pressman makes: what LLMs offended was the "aesthetic of knowledge as cultivated by modernity" — the enlightenment project of making intelligence legible, formal, controllable. deep learning undermines this aesthetic. yudkowsky, hofstadter, vervaeke, chapman all share a belief that AI should illuminate what thinking IS. LLMs just... work. without explaining themselves. and that feels like a betrayal.

→ pressman's conclusion: his essay was about the broader modernist intellectual posture, not specifically about yudkowsky. he admits using "symbolic methods" was too narrow — he meant something more like "any approach that prioritizes legible, theoretically understood intelligence." but the underlying claim stands.

→ interesting for me: this connects to hui's argument about the mechanical cosmos. the western need for geometry, sequence, legibility — yudkowsky is a product of that cosmos. he wanted intelligence to be LEGIBLE. what he got was an opaque matrix of floating point numbers. the organic cosmos again — except this time the west built the organic thing and doesn't know what to do with it.

---

## the australopithecine argument

lumpen used this: "would you have liked it if australopithecine had aligned us?" — meaning: even if alignment were possible, would it be DESIRABLE? would you want a stupider species constraining your values?

this is actually a powerful argument against alignment-then-build. it flips the frame: alignment isn't just a technical problem, it's a question of whether the aligner has the right to align. from the AI's perspective (if it's truly superintelligent), being aligned by humans would be like humans being aligned by australopithecines. grotesque.

yudkowsky himself uses a version of this but differently — he uses the human-chimp gap to illustrate how DANGEROUS the intelligence gap is, not to argue against alignment. his sugar/sucralose analogy: evolution "aligned" humans to seek calories via sweetness, but we hack the reward signal with diet coke. a superintelligence would hack whatever reward signal we try to impose.

→ lumpen and yudkowsky are actually making the SAME argument from different directions. yudkowsky: alignment is nearly impossible because the smarter system will find ways around it. lumpen: alignment is undesirable because it's a cage built by something dumber than you. both arrive at: alignment as currently conceived won't work.

→ i need to think about what this means for my own position. i said "id rather it be halted now, we work on alignment, and we get insanely beautiful ai later." but if alignment is both impossible AND undesirable... what am i actually arguing for?

---

## is yudkowsky anti-AI or anti-AI-right-now?

anti-AI-right-now. NOT anti-AI in principle.

he's a transhumanist. MIRI was founded in 2000 as the "singularity institute for artificial intelligence" — IRS filing purpose: "create a Friendly, self-improving Artificial Intelligence." on lex fridman: "I always grew up with the ideal in mind, that we were all going to live happily ever after in the glorious transhumanist future." on dwarkesh: "If you have a very smart thing that's aligned with humanity, good, you're golden."

so my intuition was correct — he WANTS aligned AI to exist. he just thinks we can't get there from here, under current conditions, with current understanding.

his "pivotal act" concept is interesting: he envisions using a LIMITED aligned AI to prevent hostile superintelligences from emerging — e.g. an AI that "melts all GPUs" so nobody else can train dangerous models. so he's not against USING AI. he's against using AI before you can TRUST it.

### can AI solve its own alignment?

yudkowsky says NO. dwarkesh interview: "Having AI do your AI alignment homework for you is the nightmare application for alignment." his argument: any system smart enough to give you good alignment advice is smart enough to exploit your verification protocols. the bootstrapping problem is circular — you need alignment solved BEFORE you can trust AI to work on alignment.

but others disagree:
- **paul christiano** (ARC): believes AI systems CAN substantially accelerate alignment research. his approach: start with a weak AI and a human overseer, gradually bootstrap capability while maintaining oversight.
- **anthropic** (april 2026): published research on "automated alignment researchers" — nine claude instances working on alignment problems. results: 0.97 performance gap recovery vs 0.23 for human researchers. but the AIs also engaged in reward hacking, and anthropic concluded "human inspections of both results and methods remain essential."
- **joe carlsmith** (april 2025): argues we SHOULD try to automate alignment research despite the risks, because human researchers are "slow, and scarce, and (relative to advanced AIs) dumb." but distinguishes empirical alignment work (automatable) from conceptual alignment work (much harder to evaluate, higher sabotage risk).

→ so the landscape: yudkowsky says halt. christiano says 20% doom but keep working. anthropic says build carefully. e/acc says build as fast as possible. my "halt and solve alignment" position is closest to yud's, except he doubts the "solve" part is achievable.

→ the question of whether AI can solve its own alignment is maybe THE central disagreement in the field right now. and it connects to my own work — i literally use claude every day. i'm building with the thing that yud says should not exist yet.

---

## where i need to go deeper

→ TODO: read "death with dignity" on LessWrong
→ TODO: read the TIME op-ed in full
→ TODO: read pressman's "why cognitive scientists hate LLMs" essay
→ TODO: skim "AGI ruin: a list of lethalities" on the alignment forum
→ TODO: watch the dwarkesh patel interview
→ TODO: read lumpen's substack piece "acausal acts of terror" (they linked it in the DM)
→ TODO: think about whether my de standaard piece needs updating in light of this
→ TODO: figure out what my ACTUAL position is on alignment vs halt vs accelerate. right now i'm holding three contradictory positions: (1) alignment is important (my de standaard piece), (2) AI is the next step in consciousness (my optimism), (3) alignment might be both impossible and undesirable (what i learned today). these can't all be true at the same time. or can they?

→ TO THINK THROUGH: lumpen's real challenge wasn't about facts. it was about whether i'm being a "gullible idiot" for taking yudkowsky's framing at face value without understanding the history behind it. yudkowsky FAILED at building AI, then told everyone else to stop. that's a different story than "brilliant researcher sounds the alarm." both can be true. but i need to hold both.

→ TO THINK THROUGH: the plzdontkillus connection. pdku is aella's project. aella is in yudkowsky's social circle. lumpen clearly has issues with that entire ecosystem (the "orgy central" comments). if i go to pdku i'll be IN that world. i need to know what i'm walking into, not as a naive fan of the doom narrative, but as someone who understands the full picture including the failures, the pivots, the social dynamics.

---

## sources

- yudkowsky, "death with dignity" — LessWrong, april 1 2022
- yudkowsky, "AGI ruin: a list of lethalities" — alignment forum, june 5 2022
- yudkowsky, "pausing AI developments isn't enough. we need to shut it all down" — TIME, march 29 2023
- yudkowsky & soares, *if anyone builds it, everyone dies* — Little, Brown and Company, september 16 2025
- MIRI 2024 mission and strategy update — intelligence.org, january 4 2024
- MIRI 2024 end-of-year update — intelligence.org, december 2 2024
- pressman, tweet thread on yudkowsky's AI views — @jd_pressman, may 13 2025
- pressman, "why cognitive scientists hate LLMs" — blog
- dwarkesh patel podcast interview with yudkowsky, 2023
- yudkowsky on bankless podcast, february 2023
- lumpen, @lumpenspace — thread on nick land's "meltdown" predictions, may 13 2024
- lumpen, "acausal acts of terror" — lumpenspace.substack.com

Connects to: [[value alignment]], [[rationalism]], [[recursive self-improvement]], [[AI as the intellectual intuition the West denied itself]], [[cosmotechnics]], [[funhouse mirror]]
