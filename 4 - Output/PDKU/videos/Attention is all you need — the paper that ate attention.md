Tags: [[hyperstition]], [[exocapitalism]], [[surveillance]], [[loops]]
Status: #baby

---

## the parallel

june 12, 2017. eight researchers at google publish a paper called "attention is all you need." the title refers to self-attention — a mathematical mechanism that lets a neural network weigh which parts of an input matter most for understanding every other part. it replaced the sequential bottleneck of RNNs with parallel, direct token-to-token relationships. the key innovation: every element can attend to every other element simultaneously.

the same year, tiktok launches internationally.

the paper's attention mechanism — query, key, value — computes which tokens should attend to which other tokens. the recommendation algorithms built on top of it compute which content should capture which humans' attention. the mathematical operation called "attention" is being used, at industrial scale, to harvest the biological phenomenon called attention.

the paper is called "attention is all you need." the systems built from it are consuming all the attention humans have.

that's not a metaphor. that's a loop.

---

## the chronological map

### the machine attention track

- **jun 2017** — "attention is all you need" (vaswani et al.). 8 authors, all google except one 20-year-old intern (aidan gomez, university of toronto). the mechanism: self-attention. every token directly computes a relationship with every other token. no sequential dependency. the formula: `Attention(Q, K, V) = softmax(Q·Kᵀ / √d_k) · V`. multi-head attention runs 8 parallel heads, each learning different relationship types.
- **jun 2018** — GPT-1 (openai, 117M params). decoder-only transformer.
- **oct 2018** — BERT (google, 340M params). encoder-only transformer.
- **feb 2019** — GPT-2 (1.5B params). "too dangerous to release."
- **may 2020** — GPT-3 (175B params). few-shot learning emerges.
- **nov 2022** — ChatGPT. 1 million users in 5 days.
- **mar 2023** — GPT-4 + Claude 1. same day.
- **feb 2024** — meta publishes HSTU — a trillion-parameter transformer architecture now powering recommendations across facebook, instagram, reels, threads.

7 of 8 authors left google. 6 founded companies. the paper has 100,000+ citations. the architecture became the substrate for every major AI system that exists.

### the human attention track

- **2004** — gloria mark (UC irvine): average time on a single screen before switching = **2.5 minutes**
- **2006** — aza raskin invents infinite scroll. he later estimates it wastes 200,000 human lifetimes per day. he co-founds the center for humane technology out of regret.
- **2012** — mark's data: screen attention drops to **75 seconds**
- **2013** — vine launches (6-second videos). instagram adds video (15 seconds).
- **sep 2016** — douyin launches in china (15-second videos)
- **sep 2017** — tiktok launches internationally (15 seconds)
- **2019** — lorenz-spreen et al. in nature communications: topics gain and lose collective attention on decreasing timescales. the acceleration is measurable across twitter, google, reddit, wikipedia. driven by increasing content production exhausting limited attention resources.
- **Q1 2020** — tiktok: most downloads for any app ever in a single quarter (315M+). covid lockdowns.
- **aug 2020** — instagram reels launches globally. youtube shorts follows.
- **~2020** — mark's data: screen attention drops to **47 seconds**
- **sep 2021** — tiktok hits 1 billion monthly active users. faster than facebook (8.7 years), instagram (7.7 years), youtube (8.1 years).

from 2.5 minutes to 47 seconds in under two decades. the architecture that optimizes for capturing attention is accelerating the depletion of the resource it captures.

### the neuroscience

the fMRI studies are damning:
- **meshi (2013)**: nucleus accumbens response to social reputation gains predicted facebook use intensity. monetary reward response did not. the hook is specifically social.
- **sherman, UCLA (2016)**: 32 teenagers in an instagram-simulated fMRI paradigm. photos with many likes activated reward processing regions. when viewing risky content, activation in the cognitive-control network *decreased*. social media engagement literally suppresses impulse-control systems.
- **2023 PRISMA review** (brain sciences): 11 neuroimaging studies. activation patterns partially overlap substance-use disorder paradigms. key structures: amygdala, vmPFC, ventral striatum.
- chronic use: reduced gray matter volume in nucleus accumbens. weakened prefrontal cortex regulation. structural changes in anterior cingulate cortex, basal ganglia, amygdala.

variable ratio reinforcement — the same unpredictable reward schedule as slot machines. the schedule most resistant to extinction. tristan harris called pull-to-refresh "a slot machine in your pocket."

average person checks phone 96 times per day. meta's own data: average user attends to a single post for a maximum of 2 seconds.

---

## the eight authors — where they scattered

| author | 2017 | now |
|---|---|---|
| ashish vaswani | google brain | CEO, essential AI ($1B valuation, may 2026) |
| noam shazeer | google brain | openai (joined jun 18, 2026). previously character.ai, then back to google for gemini, then left again |
| niki parmar | google research | anthropic (joined dec 2024). previously adept AI, essential AI |
| jakob uszkoreit | google research | CEO, inceptive (biotech, RNA molecule design) |
| llion jones | google research | CTO, sakana AI (tokyo, ~$2.6B valuation) |
| aidan gomez | U of toronto (intern) | CEO, cohere ($7B+ valuation) |
| lukasz kaiser | google brain | senior researcher, openai. contributed to o1 |
| illia polosukhin | had already left google | CTO, NEAR protocol (blockchain) |

---

## the debunking that matters

the microsoft "8-second attention span" claim (2015) — that human attention dropped below a goldfish's — is fabricated. BBC journalist simon maybin (2017) traced it: the figures came from a site called statistic brain, which cited sources that contained no such data. no scientist can explain how you'd measure a goldfish's attention span. goldfish memory lasts months.

but gloria mark's real data doesn't need the fabrication. 2.5 minutes → 75 seconds → 47 seconds. the trend is measurable without the myth.

---

## the hyperstition angle

this is a self-fulfilling prophecy twice over:

1. the paper creates the architecture. the architecture powers the recommendation systems. the recommendation systems capture attention. the captured attention funds the companies that build better architectures. the loop closes.

2. the paper's *name* — "attention is all you need" — is itself a kind of spell. it announced what the next decade would optimize for. it told us what the systems would consume. naming is binding.

eight people wrote a paper about mathematical attention. the systems built from it restructured biological attention across billions of brains. the paper has been cited 100,000 times. the average human can now focus on a screen for 47 seconds.

the loop is the thing.

---

Connects to: [[Infected by sound - sonic warfare and memetic viruses]], [[Audio virology and memetic contagion]], [[Laozi as the original troll]], [[Eschatology as self-fulfilling prophecy]], [[Sexuality as a technology of attention]]
