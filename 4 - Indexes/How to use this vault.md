# how to use this vault

a short guide to the flow. most of it is not new — the vault already did 70% of this. what's new is the inbox and the rituals.

---

## the folders (quick reminder)

- **0 - Inbox/** — dump zone. no thinking required.
- **1 - Rough Notes/** — scratch with shape (to read, reminders, ideas to follow up).
- **2 - Source Material/** — anything outside your head (books, articles, video, X, emergents, other).
- **3 - Tags/** — concept anchors. empty stubs become concept pages over time.
- **4 - Indexes/** — meta-pages like this one.
- **5 - Templates/** — breaky thought, full note.
- **6 - Child notes/** — syntheses, essay drafts.
- **7 - Adult notes/** — finished pieces.

---

## the inbox

drop anything in `0 - Inbox/` without thinking about where it belongs:

- screenshots of articles / tweets / book pages
- voice notes (transcribe them yourself or let claude do it)
- your own free-writing, half-thoughts, lines that came in the shower
- pdf excerpts
- images of marginalia
- links to articles you haven't read yet
- photos of handwritten notes

don't rename. don't sort. that's the whole point.

---

## the three rituals

### ingest
when the inbox has things in it, tell claude:

> "ingest the inbox"

claude will: identify each item, ocr / transcribe if needed, separate your voice from the source's voice, file it in the right folder using the breaky-thought template where it fits, add wikilinks, feed any tag pages that actually grew from the material, and report back on what it did and what it left undecided.

claude will *not* silently promote a rough note to a child note, rename your existing files, or clean up your lowercase.

### lint (the gap pass)
once a month, or when you feel the drift, tell claude:

> "lint the vault" or "where are the gaps"

claude returns a report (no silent edits) covering:
- orphan notes
- concepts that keep showing up but have no tag page yet
- stub tag pages that have enough pressure now to be worth writing
- contradictions between notes
- tags that keep co-occurring but have no bridge written between them
- ideas-to-follow-up that have accumulated supporting material since you wrote them
- for each emergent: which movements are written, which aren't, and what new source notes could feed the unwritten ones

this is the "trains of thought / gaps in thinking" part. read the report like a provocation, not a todo list.

### query
for anything substantive ("what did i say about the zero", "how does preciado's telebody connect to the yangtze river computer"), claude searches the vault first, quotes your prior claims with wikilinks, and only reaches outside when the vault genuinely doesn't have the thread. if an answer is worth keeping, claude will offer to save it as a child note or a tag-page section — it won't save silently.

---

## tag pages, grown-up edition

the files in `3 - Tags/` start as empty stubs. that's fine; they exist to be linked to. when one accumulates real pressure (say, three source notes pointing at it, or a contradiction worth surfacing), it earns a body. the shape is loose:

- one-paragraph orientation
- threads (bulleted claims, each linking to the source note that carries it)
- connections (to other tags, one line each)
- open questions / gaps
- optional claude-added observations, clearly marked

you don't have to grow them on a schedule. lint will tell you which ones are ready.

---

## writing conventions (for claude)

when claude adds anything inside one of your notes, it marks the block:

> _note added by claude, {month year}. {one-line framing.}_

so you can always see where your voice ends and claude's begins.

lowercase prose. italics for quotes. no corporate framing, no "in conclusion". if claude isn't sure about a citation or page number, it will say so instead of inventing one.

---

## the goodreads pipe

a launchd job (`~/.goodreads-sync/sync.py`) polls your three shelves once a day at 10:00 and feeds results into the vault:

- **currently-reading** — new book → creates `2 - Source Material/Books/[Title] - [Author]/_about.md` with the goodreads blurb, cover, isbn, dates. drops a flag in `0 - Inbox/` so next ingest fills the `## potential threads` section with connection proposals.
- **read** — book moved from currently-reading → shelf + rating + finish date get auto-updated on its `_about.md`. inbox flag invites a short retrospective at next ingest.
- **to-read** — maintained as `2 - Source Material/Books/_to-read.md` (one file, 100 books, newest first). new additions trigger an inbox flag. at ingest, claude researches each new entry and drops a one-paragraph "potential threads" under its header. anything you write there yourself is preserved across syncs — the script only overwrites the header block.

when a `goodreads-YYYY-MM-DD.md` appears in `0 - Inbox/`, it's not a note — it's a prompt for the next ingest. running ingest handles it, then deletes the flag.

**manual run** if you want an off-cycle sync: `python3 ~/.goodreads-sync/sync.py`.
**logs** live at `~/.goodreads-sync/logs/{stdout,stderr}.log`.
**unload** if you ever want to stop it: `launchctl bootout gui/$(id -u) ~/Library/LaunchAgents/com.masaeva.goodreads-sync.plist`.

---

## where the schema lives

`CLAUDE.md` at the vault root is the source of truth for how claude treats this vault. if you change a folder, rename a template, or invent a new convention, update that file (or tell claude and it will update it).
