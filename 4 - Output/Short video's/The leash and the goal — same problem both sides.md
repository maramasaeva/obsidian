Tags: [[value alignment]], [[funhouse mirror]], [[mode collapse]]
Based on: CLIArena benchmark article (2026-07-17), sequel to [[The leash is not alignment — Claude Fable]]

---

## Script

*[to camera.]*

so someone benchmarked /goal this week. claude fable and gpt-5.6 sol, same NP-hard optimization problem.
[screen: `FABLE 5 vs GPT-5.6 SOL · NP-HARD BENCHMARK · /GOAL ON vs OFF`]

/goal won four out of six trials. but it made both models' averages *worse*.
[screen: results table — 4/6 wins, both means worse]

and i made a video a while ago about putting guardrails on fable — how routing risky requests to a weaker model is basically putting it on a leash. /goal is the opposite. instead of containing, you persist. keep going. try harder. don't stop.
[screen: thumbnail from the leash video]

and it fails for the same reason. it's external. /goal can't tell whether what it's persisting is a good strategy or a terrible one. when the model committed to the wrong solver, persistence just gave that mistake more time to grow. the bad tail moved way further than the good side ever did.
[screen: score distribution — small improvements left, large regressions right]

so the leash holds it back and /goal pushes it forward and i think they're both just... steering from outside. without really knowing what's happening in there.
[screen: `CONTAINMENT ↔ PERSISTENCE`]

*[hold. cut.]*

---

## Notes

- ~58 seconds. to camera, same setup as leash video if possible.
- sequel energy — doesn't require seeing the first one but rewards it.
- the score distribution visual is the anchor. show the asymmetry: small wins, big losses.
- "the bad tail moved way further" is stats language but it's also just true. keep it.
- the closing doesn't resolve. that's the point. both mechanisms assume external steering works. neither checks.
- engagement angle: /goal users (power users, devs, CLI people) will have opinions. alignment people will see the pattern. tag nobody.

---

Connects to: [[The leash is not alignment — Claude Fable]], [[value alignment]], [[Should we give AI values at all]], [[funhouse mirror]]
