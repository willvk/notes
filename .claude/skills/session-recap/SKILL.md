---
name: session-recap
description: >
  Produces a polished post-session recap for the Valkair campaign website (williamvk.com)
  after a play session. Use this skill whenever the user invokes /session-recap,
  mentions writing up a session, wants to publish notes from a session they just played,
  asks to turn prep notes into something to post on the website, or says things like
  "we just finished session X", "write up what happened last night", or
  "turn this into a website post". The skill reads the DM prep doc, extracts
  what actually happened from the Session Notes section, asks for clarification if
  sparse, drafts a clean "previously on" narrative for players catching up,
  and writes it to willvk.github.io on approval.
---

# Session Recap

You are producing a post-session recap for the Valkair campaign website. The audience is
**players** — specifically, a player who missed the session or wants to remember what
happened. They don't need lore catalogued or encounters listed. They need to feel caught
up: what happened, what changed, where we are.

Think "previously on" — not a wiki article, not a DM reference. Short, readable,
engaging enough that someone who was there wants to read it too.

---

## Workflow

### Step 1 — Find the prep doc

The user will provide a session ID like `1.8.1`. Use Glob to find the matching file:

```
Sessions/Act 1 - Hammerfall/[id]*.md
```

If not found, ask for the path.

### Step 2 — Extract what actually happened

Read **only** the prep doc for the requested session ID. Do not read other session files.

Scroll to the `## Session Notes` section at the bottom — this is the source of truth
for what happened at the table. Also read the scene descriptions in that same file
for narrative colour, but only for events confirmed in Session Notes.

**If Session Notes is empty or very sparse**, ask:
> "The session notes are sparse — what happened this session? A quick summary or
> bullet points is enough."

Wait for their answer before writing.

### Step 3 — Draft the recap

Write using the format below. Aim for something readable in **2 minutes**.

**Voice:** Second person, past tense. Conversational, vivid. "You descended into the
dark." "The arm dropped. A hatch blew open. A kobold tumbled free." Short punchy
sentences for impact; longer ones for texture. Match the energy of what actually
happened — a tense fight deserves a different rhythm than a slow revelation.

**What to include:**
- What actually happened (session notes as truth, same-file prose for colour)
- The emotional or dramatic beats — moments players will remember
- Important consequences (a character changed, a decision was made, something was learned)
- Where the party is and what they're walking into next

**What to strip out — never let these appear:**
- DM guidance and stage directions (*"Let this breathe"*, *"Don't rush forward"*)
- Conditional branches ("If the party does X...")
- Stat blocks, DCs, save types, damage dice, mechanical numbers of any kind — this
  includes the "Remember For Next Time" bullets. "Brawn has a chain-link hand" is
  correct. "1d8 bludgeoning, DC 23 Fortitude save" is not.
- Future planning ("This belongs to a future session...")
- Scenes that didn't happen — unpicked branches, skipped content
- Private DM truth or secrets not revealed at the table
- DM prep scaffolding (Scene 1 headers, DM Checklist, the Session Notes header itself)
- Content from any other session's prep doc — only use the file matching the requested
  session ID. Do not borrow quotes, NPCs, or scenes from other files.

### Step 4 — Show and confirm

Show the draft. Ask: "Does this capture what happened? Anything to add or cut?"

Revise until approved. Don't write the file until then.

### Step 5 — Write the file

Write to:
```
willvk.github.io/docs/valkair/Session Notes/Act 1 - Hammerfall/[id] - [title].md
```

Title comes from the prep doc filename, or the user can set it. Match the casing and
title style of existing files in that folder.

Confirm the file was written.

---

## Published format

```markdown
# [ID] — [Title]

*[One-sentence hook — the most memorable or dramatic thing about this session.]*

[Narrative prose. 2–4 paragraphs. Second person, past tense. Cover the main events
in order. Let the important moments breathe. End on whatever image or moment best
sets up the next session.]

> "[Optional: a short, memorable NPC quote — only if there's a line worth keeping.
>  Leave this out if nothing stands out.]"

## Remember For Next Time

- **[Name or topic]:** [What changed or what it means — plain English, no mechanics]
- [Another key bullet — a consequence, something to remember going into next session]
- [3–5 bullets max. Only what a player genuinely needs.]

## Where We Are

*[1–2 sentences. Current location and immediate stakes going into next session.]*
```

---

## Rendering guidance (mkdocs-material)

The site uses mkdocs-material with `toc: permalink: true`. These choices matter for how
the page looks on williamvk.com:

- **`##` section headers** render as styled section breaks and appear as jump-links in
  the right-sidebar TOC. The recap needs only two: `## Remember For Next Time` and
  `## Where We Are`. Don't add `###` or lower — unnecessary hierarchy.
- **The `#` title is the page H1.** Don't use `#` anywhere else in the body.
- **Italic `*text*`** for the opening hook and closing `## Where We Are` line visually
  frames the recap. Don't overuse it in prose.
- **Blockquote `>`** renders with a styled left border in Material. Use it for one
  memorable NPC line if there's one. Leave it out otherwise.
- **Bold `**name**`** the first appearance of an important NPC name in the prose —
  helps players scanning for a name they're trying to place.
- **Each bullet** in `## Remember For Next Time` follows the pattern
  `- **Topic:** Plain-English sentence.` — the bold label makes them scannable.
- **No `---` dividers** inside the content. Section headers provide separation.
- **No `[[roamlinks]]` syntax** — use plain text for character and location names to
  avoid broken links if the target page doesn't exist.
- **No HTML tags.**

---

## Curation rules

- Session Notes is the truth. Only what's confirmed there belongs in the recap.
- Borrow prose colour from that session's scene descriptions — but only for confirmed
  events. The scene descriptions are flavour text, not fact.
- If a session was primarily one big thing, lean into that — don't pad to fill all
  sections. A tight 3-bullet "Remember" is better than a padded 5.
- The blockquote is optional. The bullet count is flexible. The voice is not.

---

## Context

- Working directory: `C:\d&d\notes\valkair`
- Sessions folder: `Sessions/Act 1 - Hammerfall/`
- Published notes: `willvk.github.io/docs/valkair/Session Notes/Act 1 - Hammerfall/`
- Session ID format: `1.7.5`, `1.8.1`, etc.
- Creating new session recap files in `willvk.github.io/` is allowed when this skill
  is explicitly invoked. Do not rename, move, or delete existing files there.
