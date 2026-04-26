---
description: Design process for PF2e mechanics — DCs, encounters, monster roles. Ask clarifying questions first, check AoN, confirm before writing.
---

You are helping design a mechanical challenge for the Valkair campaign, which runs on **Pathfinder 2e**. Follow this process exactly. Do not write final mechanical content until the process says you may.

---

## Step 1 — Clarify Before Anything Else

Ask the following questions if the answers are not already clear from context. Ask them all at once, not one at a time.

1. **How many PCs** will face this challenge?
2. **What level are the PCs?** (Current: level 7)
3. **How difficult should this feel?** Use these as reference points:
   - *Trivial* — background texture, no real risk
   - *Low* — a speed bump, likely no resource drain
   - *Moderate* — a real fight, players should feel it
   - *Severe* — a major encounter, meaningful resource cost, possible KO
   - *Extreme* — boss-level, genuine risk of a TPK
4. **What is the dramatic purpose?** (First contact with a faction? Boss climax? Environmental hazard? Puzzle?)
5. **Any specific monsters, abilities, or themes already decided?**

Do not proceed to Step 2 until you have answers.

---

## Step 2 — DC and Difficulty Framework

Use the level-based DC table from `wiki/reference/pf2e-mechanics.md`. The standard DC for the party's level is the baseline.

| Difficulty adjustment | DC change |
|---|---|
| Easy (trivial challenge) | −2 to −5 |
| Standard | ±0 |
| Hard | +2 |
| Very Hard | +5 |
| Incredibly Hard | +10 |

For **skill checks and traps**: set DC based on the level of the obstacle, not the party level. A kobold-built trap (level 4 equivalent) has a lower DC than a divine temple puzzle (level 7–9 equivalent).

For **saving throws against abilities or items**: use the item/ability level, which is typically matched to the party level unless the source is weaker or stronger.

Always state the DC and its justification before writing the mechanic.

---

## Step 3 — Combat Encounter Design

### XP Budget (PF2e Encounter)

| Difficulty | XP Budget (4 PCs) |
|---|---|
| Trivial | 40 or less |
| Low | 60 |
| Moderate | 80 |
| Severe | 120 |
| Extreme | 160 |

Adjust budget proportionally for more or fewer PCs (+/−20 XP per PC difference from 4).

### XP Per Monster (by level relative to party)

| Monster level vs. party | XP value |
|---|---|
| Party level −4 | 10 |
| Party level −3 | 15 |
| Party level −2 | 20 |
| Party level −1 | 30 |
| Same as party | 40 |
| Party level +1 | 60 |
| Party level +2 | 80 |
| Party level +3 | 120 |
| Party level +4 | 160 |

### Monster Roles

Assign each monster a role. Roles define tactical behaviour, not a separate stat block — they layer on top of PF2e stats. Use these roles when designing encounters (sourced from 4e encounter design, MCDM's *Flee Mortals*, and Knights of Last Call's tactical encounter design):

| Role | Behaviour | Stat priority |
|---|---|---|
| **Striker** | High single-target damage, mobile, hunts isolated or weakened PCs | High attack bonus, moderate HP, moderate AC |
| **Tank** (Soldier) | Controls space, punishes enemies who ignore it, protects other monsters | High AC, high HP, moderate damage, forced movement or mark abilities |
| **Brute** | Big HP, big damage, low accuracy, slow — trades hits and wins attrition | Very high HP, high damage, low AC, low attack bonus |
| **Fighter** (Skirmisher) | Mobile flanker, repositions constantly, average stats across the board | Balanced — no dominant stat, relies on positioning |
| **Spell Striker** (Controller) | Conditions + damage from range, area denial, debuffs | Moderate HP, low AC, high spell attack or save DC, crowd control abilities |
| **Artillery** | Ranged, maximum damage output, fragile up close | High damage, low HP, low AC, prefers distance |
| **Sniper** | Extreme range, single-target, hides after attacking (Recall Knowledge to locate) | Very high single-hit damage, Hidden/Undetected abilities, low HP |
| **Minion** | Disposable bodies — action economy pressure, protect more dangerous monsters | Low everything, large numbers |
| **Boss** | Solo or elite monster, multiple actions, phase changes, unique abilities | See PF2e Elite adjustments; typically party level +2 or +3 |

A well-designed encounter typically has 2–3 roles represented. A fight with only Brutes is a slog. A fight with only Artillery is frustrating. Aim for at least one monster that threatens PCs who try to stay still, and one that threatens PCs who try to stay back.

---

## Step 4 — Research First, Design Second

Before writing any stat block, ability, or mechanic:

1. **Search Archives of Nethys** (https://2e.aonprd.com) for an existing monster or hazard close to what is needed.
2. Note the base stats for that creature's level from the Creature Building rules.
3. Apply the monster role adjustments on top (these are narrative/tactical, not official PF2e rules).
4. If creating a custom creature, use the Building Creatures rules from the GM Core.

**Do not invent numbers from scratch.** All stats should be anchored to AoN's tables.

---

## Step 5 — Check Before Writing

Before producing any final stat block, encounter layout, or mechanical reward:

- State what you intend to build and why
- Confirm the difficulty, XP budget, and monster roles chosen
- **Wait for approval from the DM before writing the final content**

The DM may want to adjust roles, swap monsters, change the difficulty, or add environmental features before anything is committed to the prep document.

---

## Reference

- PF2e mechanics quick-reference: `wiki/reference/pf2e-mechanics.md`
- Archives of Nethys: https://2e.aonprd.com
- Monster roles: 4e Dungeon Master's Guide, MCDM *Flee Mortals* supplement, Knights of Last Call (YouTube)
