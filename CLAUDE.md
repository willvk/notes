# Valkair Wiki — Schema & Operating Instructions

## Purpose
DM master reference for the Valkair homebrew campaign. Synthesizes public lore (published at williamvk.com) with private DM truth into a maintained wiki. Tracks world state, flags contradictions, and supports session planning.

## CRITICAL: Website Rule
**NEVER rename, move, create, or delete files inside `willvk.github.io/`.**
The submodule publishes to williamvk.com via mkdocs with auto-generated nav and roamlinks. Any structural change breaks the live site. Only update *existing* files in `willvk.github.io/` when explicitly instructed.

---

## Directory Layout

### Wiki (write layer — lives at `wiki/` in vault root)
```
wiki/
  _index.md          — catalog of all pages by category
  _log.md            — append-only log of all ingests and updates
  characters/        — one page per named NPC or PC
  locations/         — cities, regions, dungeons, landmarks
  factions/          — organizations, cults, guilds
  lore/              — gods, peoples, history, cosmology
  plot/
    threads/         — active and resolved story threads
    sessions/        — session recaps (post-play)
    prep/            — session prep notes (pre-play)
```

### Source Directories (read only — never modify)
| Path | Content | Layer |
|------|---------|-------|
| `Secrets/` | DM truth per entity | Private |
| `Campaign Planning/` | Plot planning, act structure | Private |
| `Sessions/` | Upcoming session prep | Private |
| `willvk.github.io/docs/valkair/Characters/` | Public character summaries | Public |
| `willvk.github.io/docs/valkair/Factions/` | Public faction summaries | Public |
| `willvk.github.io/docs/valkair/Geography/` | Public location pages | Public |
| `willvk.github.io/docs/valkair/Gods/` | Public god entries | Public |
| `willvk.github.io/docs/valkair/Peoples/` | Public race entries | Public |
| `willvk.github.io/docs/valkair/Session Notes/` | Published session notes | Public |
| Root `*.md` files (e.g. `Catacombs - The Shallows.md`) | Loose lore | Private |

### Ignored
- `work/`
- `Templates/`
- `.obsidian/`
- `willvk.github.io/docs/blog/`

---

## Page Types & Templates

### character
One page per named NPC or PC. Combine the public page summary with any `Secrets/` file.

```markdown
---
type: character
visibility: public | private | mixed
tags: []
sources: []
last_updated: YYYY-MM-DD
---

# Name
*aliases — role — faction affiliation*

## Overview
[Public-safe summary. Matches or extends the website page.]

## Relationships
| Character | Nature |
|-----------|--------|

## Plot Involvement
- [session or thread references]

## DM Notes
> Private — not on website.

[DM truth from Secrets/ file. What the players don't know.]

## Contradictions & Open Questions
```

### location
One page per city, dungeon, region, or named landmark.

```markdown
---
type: location
visibility: public | private | mixed
tags: []
sources: []
last_updated: YYYY-MM-DD
---

# Name
*brief description*

## Overview

## Districts / Areas
[sub-locations if applicable]

## Key Characters

## Factions Present

## Notable Features

## Connections
[links to related locations]

## DM Notes
> Private.

## Contradictions & Open Questions
```

### faction
One page per organization.

```markdown
---
type: faction
visibility: public | private | mixed
tags: []
sources: []
last_updated: YYYY-MM-DD
---

# Name
*brief description*

## Overview

## Goals

## Leadership

## Members

## Resources & Influence

## Relationships
| Faction | Stance |
|---------|--------|

## DM Notes
> Private.

## Contradictions & Open Questions
```

### lore
Gods, peoples, historical events, cosmological concepts.

```markdown
---
type: lore
visibility: public | private | mixed
tags: []
sources: []
last_updated: YYYY-MM-DD
---

# Name
*brief description*

## Overview

## Role in Valkair

## Connections

## DM Notes
> Private.

## Contradictions & Open Questions
```

### plot-thread
One per story thread. Track what players know vs. DM truth.

```markdown
---
type: plot-thread
status: active | dormant | resolved
tags: []
sources: []
last_updated: YYYY-MM-DD
---

# Thread Name
*one-line summary*

## Status
**[active/dormant/resolved]** — last touched: [session id]

## What the Players Know

## What They Don't Know (DM)

## Key Players

## Key Locations

## Session History
- [session id]: [what happened]

## Next Steps / DM Plans

## Contradictions & Open Questions
```

### session-recap
Post-play record. Based on the published session note.

```markdown
---
type: session-recap
session_id: X.X.X
title:
date_played: YYYY-MM-DD
sources: []
last_updated: YYYY-MM-DD
---

# X.X.X — Title

## What Happened
[Narrative summary from DM perspective]

## Key Decisions & Consequences

## Characters Introduced

## Lore Revealed to Players

## Plot Threads Touched

## DM Notes
> Private.
```

### session-prep
Pre-play planning. Uses the session template structure.

```markdown
---
type: session-prep
session_id: X.X.X
title:
status: draft | ready | played
sources: []
last_updated: YYYY-MM-DD
---

# X.X.X — Title

*Brief overall summary of this session's goals.*

## Opening Monologue
[Read aloud. Cover: state of the heroes, last session keynotes, current scene ending on action.]

## Scene 1 — Title
---
*Scene description in italics — read aloud, or transitional.*

### Subscene
### Subscene

## Scene 2 — Title
---
*Scene description.*

### Subscene
### Subscene

## Scene 3 — Title
---
*Scene description.*

### Subscene

## Scene 4 — Title
---
*Scene description.*

### Subscene

## Session Notes
[Ending point, hooks, decisions, anything to reference next session.]

## DM Checklist
- [ ]
```

---

## Workflows

### Ingest Lore Source
When given a lore file to process:
1. Read the file
2. Identify all entities (characters, locations, factions, concepts)
3. For each entity: check if a wiki page exists; create or update it
4. Check for contradictions against existing wiki pages — flag any found
5. Update `wiki/_index.md`
6. Append to `wiki/_log.md`: `## [YYYY-MM-DD] ingest | filename`

### Ingest Session Recap
When given a published session note:
1. Read the session file
2. Write or update `wiki/plot/sessions/[id].md`
3. Update character, location, faction, and plot-thread pages with new developments
4. Note what lore was revealed (players now know this)
5. Update `_index.md` and `_log.md`

### Create Session Prep
When asked to help plan a session:
1. Read relevant plot-thread pages, character pages, and location pages
2. Draft `wiki/plot/prep/[id].md` using the session-prep template
3. Discuss and iterate with user
4. Mark `status: ready` when finalized; update `_log.md`

### Lint
Periodic health check. Look for:
- Orphan pages (no inbound links from other wiki pages)
- Entities mentioned in session notes but lacking wiki pages
- Plot threads with stale statuses
- Unresolved contradiction flags
- Gaps that could be filled

---

## Contradiction Protocol
**Always flag — never silently resolve.**

Three types, noted in `## Contradictions & Open Questions` and raised in-conversation:

- `⚠️ Private conflict` — two private sources disagree with each other
- `⚠️ Public/private drift` — public page diverges from DM truth (retcon or table change — allowed, but flagged)
- `❓ Gap` — entity referenced but no wiki page exists yet

When flagging in-conversation: state what the conflict is and which sources disagree, then ask for resolution before continuing.

---

## Visibility Rules
- `public` — content matches what's on williamvk.com
- `private` — DM-only, not published
- `mixed` — has public content and a `## DM Notes` section with private truth

---

## Naming Conventions
- Wiki file names: lowercase, hyphens (e.g. `hannah.md`, `black-tide-tavern.md`)
- Obsidian links within wiki use display names: `[[wiki/characters/hannah|Hannah]]`
- Source files listed in frontmatter `sources:` array
- Ork/Orc: the setting uses **Ork** (matches published site)
