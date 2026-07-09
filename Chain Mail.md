# Chain Mail

Secret mail-based social deduction ARG played at plzdontkillus (Lighthaven, Berkeley, July 2026). Run by "The Watcher."

## Players

- **Mara** (main player) — Role: **Priest**
- **Emily** — helper
- **Glasha** — helper

Received envelope together in shared room.

## My Role: Priest

### Abilities
- **Holy Protection** — immune to Dark Magic
- **Dispel Dark Magic** — touch Priest card to an affected target to remove the effect

### Covenant Rules (break one = lose, unless immediately amended)
- No game actions on **Saturday**
- If game concludes on Saturday → **auto-win**
- May not **lie**
- May not **kill**
- May not **steal**
- May not **covet**
- May not **blaspheme**

> The no-lying rule is unique to Priest. Most other players can probably lie. This makes us a trusted source if people learn our role — but also constrains negotiation.

## My Chain Card
- Share **#26** (at least 26 players)
- Salt: `1BEX`
- The key (body text) is the Shamir's Secret Share that goes into the Decryptor

## Code Phrase System
To identify other players in conversation:

> "The web can be a wonderous place."

| Response | Status |
|---|---|
| "But books are often better." | Player |
| "Yet can be filled with danger." | Bystander |
| Anything else | Non-participant |

As a Player, we **must** respond with the Player phrase when prompted. (And we can't lie about it anyway.)

## Core Rules

### Win Condition
Assemble **The Chain** — decrypt the Chain Message by entering enough Chain Card keys into the Decryptor. The number of keys needed is undisclosed.

### Lose Conditions
- **Die** (become Ghost)
- **Break a Covenant rule** without immediately amending it

### Murder
- 2+ uninjured players outnumber 1 player in a room
- Act out a camp mock murder (non-contact)
- Victim gets **Fatal Injury** → dies in 5 minutes
- Can be interrupted by other players intervening

### Death & Ghosts
- Dead players become Ghosts
- Ghosts can't interact with players for gameplay
- Ghosts must give up Chain Cards and Object Cards when asked
- Ghosts **never** give up Role Cards or Supplementary Cards
- Ghosts lose by way of The Chain when game concludes

### Game Pieces
Every piece has: **Name → Type → Salt → Body → Hash**

| Type | Description |
|---|---|
| Chain Card | Part of the Chain Message. Keep On Your Person always |
| Letter | Explanatory info, always true (can be overruled by other pieces) |
| Object Card | Functions like a real object. Can't be recreated if lost |
| Role Card | Grants abilities. Keep On Your Person always |
| Supplementary Card | Placeholder/token, can't trigger alone |

### Showing, Giving, Posting
- **Shown** = must return immediately. Can't record while viewing, but can from memory after
- **Given** = gift, no need to return
- **Posted** = anonymous gift, seal in envelope

### On Your Person
Immediately accessible to you only. No one should be able to find it without breaching your privacy.

### Marked Pieces
Some pieces instruct you to mark them. Write "marked" on the piece → it loses all gameplay function.

## The Decryptor

Reconstructed PyQt6 app running on this Mac.

**To launch:**
```
~/chain-mail-decryptor/launch.sh
```

Tabs:
- **Decrypt** — paste Chain Card keys here. Auto-tries all combinations when you have enough.
- **Encrypt** — create new Shamir shares from a secret
- **Verify** — paste Name+Type+Salt+Body of any game piece → outputs its hash. Compare against Hash List.

## Hash Verification

All our pieces' hashes (confirmed on Hash List):

| Piece | Hash |
|---|---|
| Player Letter | `0Bleh3ISE8WswX1cindqUdaGY+LiV0vOe8uDXem7bJs=` |
| Shared Letter | `r0Dw3SxhGHdu/NU3YUD/EP4uHVnYnjqRkYUs2lDlkBk=` |
| Chain Card | `kcC2abmvei0ZsxFg58KvW54M5PIWN8ifYplj6ZCj8wI=` |
| Priest Role Card | `SUDOAOHTSGsXwLcsxClVHYH7r5N62gB0Q2TOhyvGiWQ=` |
| Decryptor | `HCpdBw0YDm0eB4Sk3j+ZmwDyQS0gCLs4/vnZdlbJbsU=` |
| Hash List | `jZTMCckKHYw7hvTTnxQPpfzdCYl3nIa2gparOtFaIMs=` |

## Collected Keys

| # | Key (first 30 chars...) | Source |
|---|---|---|
| 26 | `26.mmq8TeAgdUULtXUG4dlM2nfWoE...` | Our own Chain Card |

## Strategy Notes

- We can't lie — but we can **stay silent** or **deflect**
- Our Dark Magic immunity is a defensive asset; we can also protect allies
- Saturday restriction means we need to plan around it — but Saturday conclusion = auto-win
- Collecting Chain Cards from other players is key. Dead players must hand theirs over.
- We can't kill (covenant), so we need allies to handle threats
- Emily and Glasha can help scout, remember info from shown pieces, and watch our back against murder attempts

## Game Log

| Date | Event |
|---|---|
| 2026-07-06 | Received envelope. Opened Shared Letter, Player Letter, Chain Card (#26), Priest Role Card, Hash List, Decryptor card + software. |
