Status: #baby
Tags: [[tao]], [[ai safety]], [[cosmotechnics]], [[wu wei]], [[value alignment]]

---

the daoist alternatives ([[What an agent could be driven by instead of want]]) sound right philosophically. but how would you actually implement them? current AI isn't built with a philosophy of mind in mind. it's grown — you throw math and data at it and something emerges. there's no step in the pipeline where someone decides "this agent will be desire-driven." desire-driven behavior is an *emergent property* of the training regime (reward maximization, RLHF, gradient descent toward a loss function). the wanting isn't designed. it's *grown into the system by the structure of the math*.

which means: if you want a non-desire-driven agent, you can't just add a philosophical layer on top. you'd have to change the math, or the data, or both.

## the math question

- current training = minimize a loss function. the agent is structurally a *minimizer*. everything it does is in service of reducing error. this IS wanting — wanting-to-reduce-error. the desire is baked into the optimization objective.
- wu wei agent: what would a training signal look like that rewards *minimal intervention* rather than reward maximization? a loss function that penalizes unnecessary action? this exists in some RL contexts (action costs, regularization) but it's not the *philosophy* of the system — it's a hack on top of the same maximizing structure.
- daoist mathematics exist. chinese mathematics historically developed differently from western mathematics — more relational, more focused on transformation and pattern than on proof and axiom. the *i ching* is a mathematical system. the *he tu* and *luo shu* (river diagrams) are combinatorial structures. but i don't understand this well enough to say whether any of it maps onto training regimes. this is a thread to follow.

## the data question

- current training data = the internet. the cosmology embedded in the data is the cosmology of english-language internet culture ([[AI is grown not built]]). the AI carries its soil.
- if you trained on daoist texts, on chinese philosophical traditions, on non-western epistemologies — would the emergent behavior be different? probably. but would it be *daoist*? or would it just be a maximizer that can quote laozi?
- the deeper question: is the desire-driven behavior a product of the *data* (western texts encode western goal-seeking) or the *architecture* (transformers + gradient descent = structural maximizers regardless of data)?
- if it's the architecture, then changing data alone won't help. you'd need a different kind of machine.
- if it's the data, then cosmotechnical diversity in training sets might actually produce genuinely different kinds of intelligence.
- probably it's both. the architecture selects for certain patterns in the data, and the data reinforces certain tendencies in the architecture. they co-produce the desire-driven agent.

## the "AI is grown" connection

this connects directly to [[AI is grown not built]] — if AI is agriculture, not engineering, then the question isn't "how do you program wu wei" but "what soil produces wu wei?" what seeds, what conditions, what selection pressure? you don't program a crop. you create the environment and let the crop find its own shape. the question is whether there's an environment — a combination of architecture + data + training signal — where wu wei is what *grows*.

## open threads

- daoist mathematics and their relationship to computation. what is the mathematical structure of non-maximizing intelligence? who is working on this?
- the architecture question: is the transformer inherently a desire-engine? or is it neutral, and the desire comes from the training signal? could you train a transformer on a non-maximizing objective and get genuinely non-desire-driven behavior?
- constitutional AI as partial precedent: anthropic trains Claude to critique its own outputs against a set of principles. the principles are human-authored, but the *process* — self-revision, self-correction — is closer to wu wei than to RLHF. is constitutional AI accidentally daoist?
- the fermentation analogy from [[AI is grown not built]]: the brewer doesn't write the chemistry. they create the environment. could someone create an environment where the chemistry produces de instead of desire?
- who is actually researching this? are there any labs or researchers working on non-maximizing architectures, non-goal-seeking training regimes, or training on non-western philosophical corpora?

_to expand when i understand the math better. this is a question i need help with — possibly from someone at pdku who understands both the training pipeline and non-western mathematical traditions._

Connects to: [[What an agent could be driven by instead of want]], [[AI is grown not built]], [[Zi ran and Dao — the self-so and the unconditioned]], [[cosmotechnics]], [[Asymmetry as method — Qi and Dao not techné and physis]]
