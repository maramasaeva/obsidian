# vault schema — Messier

This file tells Claude how to work inside this vault. It is the single source of truth for folder conventions, templates, and the ingest / lint / query rituals. Update it when the vault's shape changes.

The vault is a queer / cybernetic / taoist theory practice. Voice is lowercase, spiral, quote-heavy. Matter: queerness, AI, the zero, the loop, the torus, lesbianism as collective consciousness, UCI (Ultimate Capitalist Intelligence), telebodies, exocapitalism, network spirituality, spyrodynamism, hyperstition, tao, sorcery. When Claude writes inside notes, it mirrors that register — lowercase, no corporate hedging, comfortable with italics and fragment.

---

## folder map

```
0 - Inbox/           dump zone. anything goes. claude empties it on "ingest".
1 - Rough Notes/     structured scratch (To read, Ideas to follow up on, Reminders). mara writes here.
2 - Source Material/ everything outside of mara's head.
    Articles, essays/
    Books/[Author - Title]/[idea].md   ← one note per idea, not per chapter
    Emergents/       mara's writing-in-progress (e.g. "The Queer Computer")
    Video/
    X/               screenshots, threads
    Other/           everything else (shows, personal, world-building material)
3 - Tags/            concept anchors. one file per concept (queer.md, loops.md, tao.md…).
                     currently mostly empty stubs used as [[wikilink]] targets. over time
                     these grow into full concept pages (see "tag pages" below).
4 - Indexes/         meta-pages: how-to, reading lists, vault maps.
5 - Templates/       Breaky thought (fragment), Full Note (essay).
6 - Child notes/     syntheses / essay drafts pulling threads together.
7 - Adult notes/     finished pieces. rarely touched.
```

### file-naming

- Source notes: short idea titles in sentence case, not chapter numbers. example: `Lesbianism as collective consciousness.md`, not `Chapter 3.md`.
- Tag files: lowercase, singular, no prefix. `queer.md`, not `#queer.md` or `Queer.md`.
- Book folders: `[Title] - [Author(s)]`. examples: `Dysphoria Mundi - Paul b. Preciado`, `Machine Decision Is Not Final - Bratton, Greenspan, Ireland, Konior`.

### link style

- wikilinks everywhere: `[[Lesbianism as collective consciousness]]`, `[[queer]]`, `[[telebodies]]`.
- link to tag files by their exact filename (lowercase).
- when a note mentions a concept that *has* a tag file, link it. when it mentions one that doesn't, create the tag file as an empty stub and link it.

---

## templates

**Breaky thought** (`5 - Templates/Breaky thought.md`) — used for source-material fragments:
```
Status: #baby
Tags: [[...]], [[...]]
Quote/moment: (italicised, with page number if from a book)
My claim: (prose — her interpretation)
Connects to: [[...]]
```
Status values seen: `#baby` (seedling), others TBD. When in doubt, `#baby`.

**Full Note** (`5 - Templates/Full Note.md`) — used for longer pieces in `6 - Child notes/` and `7 - Adult notes/`:
```
{{date}} {{time}}
Status:
Tags:
# Title
body...
## References
```

Emergents don't have a strict template — they tend to carry their own internal structure (e.g. "four movements" in *The Queer Computer*). Respect whatever shape they already have; don't impose Breaky-thought onto them.

---

## the ingest ritual

Triggered when mara says "ingest", "process the inbox", "empty the inbox", or similar.

For each file / item in `0 - Inbox/`:

1. **Identify the type.** Image, screenshot with annotations, voice-note transcript, article link, article with marginalia, raw text fragment, PDF excerpt, her own free-writing, a quote she scribbled, something she can't decide about.
2. **Extract.** OCR images, transcribe if needed, pull the text content. If the artifact is a URL, fetch the article. If mara has strewn thoughts through it, separate her voice from the source's voice.
3. **Place.**
   - Source fragment from a book she owns → `2 - Source Material/Books/[existing or new book folder]/[idea title].md` using the Breaky thought template.
   - Article or essay → `2 - Source Material/Articles, essays/` (create a subfolder per author if volume warrants).
   - Video / talk transcript → `2 - Source Material/Video/`.
   - Screenshot from X/Twitter → `2 - Source Material/X/`.
   - Mara's own fragment (a claim, a half-thought, a poem) → `1 - Rough Notes/` if it's a single unit, or a new file under the most relevant tag as a stub note.
   - An idea that wants to become an essay → flag it; do not silently promote to `6 - Child notes/`.
   - Something that belongs to an existing emergent → ask, don't assume.
4. **Link.** For every concept present in the new note that matches (or should match) a tag file, add `[[wikilink]]`s. Create stub tag files for new concepts.
5. **Feed the tag pages.** When a source note genuinely advances or complicates a concept, add a short paragraph to that tag's file under a dated section (see "tag pages" below). Do not just paste the quote — synthesise. Cite by linking the source note.
6. **Report.** When done, return a short summary: what came in, where each item went, what tag pages grew, what new connections were drawn, what was left undecided and why.

### things not to do on ingest

- Do not move or rename files mara has already placed herself.
- Do not promote a rough note into a child note without asking.
- Do not "clean up" her lowercase, her italics, or her spiral prose.
- Do not add disclaimers, summaries-of-what-you-just-did, or corporate framing inside her notes.
- Do not delete the original inbox item until the destination note is written and saved. Then remove from inbox.

### goodreads-sync flags in the inbox

A launchd job (`~/.goodreads-sync/sync.py`, runs daily at 10:00) polls mara's Goodreads shelves and drops a `goodreads-YYYY-MM-DD.md` file in `0 - Inbox/` whenever something changes. When one of these flags appears in an ingest:

- **started reading** (new on `currently-reading`): the script has already created `2 - Source Material/Books/[Title] - [Author]/_about.md` with metadata and publisher blurb. On ingest, walk `3 - Tags/`, existing source notes, and relevant emergents, and fill the `## potential threads` section of that `_about.md` with 3-8 concrete connection proposals. Each proposal: a one-line thread + the tag/note it connects to + a short reason. Don't assert — *propose*. Example shape: `- **the zero as distributed intelligence** — [[loops]], [[zeroes and ones]]: jäger's "politicization without consequences" looks like the inverse of lesbianism's politics-in-the-edges; worth testing whether hyperpolitics is what happens when the edges get centralised.`
- **finished reading** (moved to `read`): `_about.md` shelf/rating/date_finished were auto-updated. On ingest, offer to write a short retrospective — what the book added, which tag pages want updating, which source notes still need writing. Don't write the retrospective silently.
- **new on to-read**: the book was appended to `2 - Source Material/Books/_to-read.md`. On ingest, for each new entry, research the book briefly and append a one-paragraph `_potential threads_` annotation below its header in `_to-read.md` (the script preserves annotations across future syncs, so long as they sit between the `[goodreads](...)` line and the next `---`).
- **removed from to-read**: just a notice; no action needed unless mara asks.

After ingest, delete the `goodreads-YYYY-MM-DD.md` flag file.

---

## tag pages (3 - Tags/)

Tag files start as empty stubs used purely as [[wikilink]] targets. Over time they become concept pages with this loose shape:

```
# concept-name

one-paragraph orientation: what this concept is in this vault, who it draws from, what it is *not*.

## threads
- short bullet per major claim mara has made about this concept, each linking to the source note(s) that carry it.

## connections
- [[other tag]] — one line on how they relate.

## open questions / gaps
- things unresolved, contradictions across notes, claims that need a source.

## claude-added (optional)
- meta-observations, flagged patterns. clearly marked as claude's, e.g.
  _note added by claude, {date}: ..._
```

Only grow a tag page when there's real content pressure (three or more source notes linking to it, or a contradiction worth surfacing). An empty stub is fine; a bloated unread wiki page is not.

---

## the lint ritual

Triggered when mara says "lint", "gap pass", "what am i missing", or monthly by habit.

Walk the vault and produce a single report (do not silently edit). The report names:

1. **Orphans** — notes with no outgoing or incoming links.
2. **Missing tag pages** — concepts mentioned in 3+ source notes that don't have a file in `3 - Tags/`.
3. **Stub tag pages with pressure** — tag files still empty despite 3+ source notes linking to them (candidates for real writing).
4. **Contradictions** — places where two notes make claims that cannot both be true, or that mara has stated differently at different times. Quote both.
5. **Co-occurring tags with no written connection** — pairs of tags that keep appearing together but have no explicit bridge note. Each is a potential essay-seed.
6. **Stale "to follow up on"** — items in `1 - Rough Notes/Ideas to follow up on.md` that have been sitting more than ~3 months, ordered by how many new links would support them now.
7. **Emergents drift** — for each file in `Emergents/`, note which source nodes listed under its movements have been written vs. not, and what new source notes (added since) could feed them.

Report format: terse, scannable, in mara's register. No preamble.

---

## the query ritual

Default mode when mara asks a substantive question. Before answering:

1. Search the vault first. `3 - Tags/`, `6 - Child notes/`, `Emergents/`, then source notes.
2. Quote her own prior claims where they exist, with wikilinks, before bringing in outside material.
3. If the answer is genuinely new synthesis worth keeping, offer to save it — either as a child note or as a new section on a tag page. Don't save silently.
4. Only reach for outside sources if the vault genuinely doesn't contain the thread. When you do, flag it clearly.

---

## writing voice when claude contributes inside notes

- lowercase prose.
- italics for quotes (single underscores in markdown work; she uses `*like this*`).
- no corporate hedging, no "in conclusion", no "overall".
- when claude adds a block into one of her notes, mark it:
  `_note added by claude, {month year}. {one-line framing of what this is and how to treat it.}_`
- when uncertain, say so plainly. don't fabricate page numbers, citations, or quotes.

---

## memory & git

- Memory lives at `/Users/messier/.claude/projects/-Users-messier-Documents-Obsidian-Messier/memory/`. Use it for facts about mara and durable feedback. Do not use it to store vault content — that belongs in the vault.
- Git is the vault's history. Commits happen regularly via the backup cron. Do not create commits after every ingest; let normal cadence handle it unless mara asks.
