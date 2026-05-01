# Onslaught Companion App — TODO

Feature backlog for the companion app. Roughly grouped by area, but order is not strict priority.

## Character sheet — editable fields
- Make **Initiative editable**. And other character sheet fields.
- **Edit character sheet to edit Hit Dice.**
- Add **general actions** to character sheets.

## Combat mechanics
- **Hit Die loss cascading damage** — damage chains through lost dice correctly.
- **Hit Die check flow:** "Do you want to add armor? Select from active effects: armor, spells, equipment, etc." (possibly affects equipment durability). Maybe the UX is: enter the amount of damage on the roll → choose whether to use armor or an ability → then it opens the actual roll and result check.
- **Initiative die cost if you use an ability** — modal pop-up to let the player choose which dice to spend to pay for the ability.
- **Equipment durability + opt-in check contribution** — equipment gets `durability: { max, current, costPerUse }`. When the player opts an item into a check (hit die defense, etc.), durability auto-decrements by `costPerUse` on roll. Ties into Hit Die check flow above.

## Abilities & effects
- **Effects tagging system** — structured effects on abilities, equipment, and spells. Types: Stat modifier, Reserve modifier, Hit Die effect, Status effect (freeform note as escape hatch). Activation modes: passive (always on while equipped/known), active (toggleable with auto-decrementing duration), opt-in (offered during checks, consumes durability if tied to equipment). Char sheet shows inline stat breakdowns (tap any stat → see the stack) and an "Active Effects" section. Spell cast flow auto-applies a spell's effects to chosen target on success.
- **Abilities modal on character sheet** for actions that are prepared. Add equipped or ability modifications for stats (adding health die, modifying stats, bonus reserve die, temp Hit Die). Needs a custom field asking which stat to modify and by how much. *Jazz will send a list.*
- **Track the abilities** and how they affect the spell cost or other stats.
- **Learned vs Equipped abilities** — track two flags per ability: *Learned* (selected at level-up, permanent) and *Equipped* (subset toggled on for active play, swapped at Long Rest). Long Rest opens a "Choose Equipped" modal. Many abilities synergize (descriptions like "If you also have X Equipped, do Y") — UI should highlight active synergies. *Equip cap rule TBD from Jazz — for now show "X learned · Z equipped" without enforcing a cap.*
- **Round/turn/day/chapter duration tracking** — effects can tick on four timescales: turn, round, day, chapter. Char-sheet trigger buttons: **End my turn** (this character done acting — ticks turn-duration effects), **End of round** (round fully over — ticks round-duration effects). **Long Rest** already serves as the day-end trigger. **Chapter end** is rare and manual. Effects hitting 0 auto-remove with a toast. Includes momentum tracking and ongoing spell effects (haste, etc.).

## New mechanics
- **Exhaustion / Comforts tracking** — *Jazz will send mechanics.*

## Table tools
- **Enemy tracker?**

## Future / phase 3
- **Real-time cross-device sync** — backend (Firebase or Supabase) for shared character-sheet state across players' devices during live sessions. Enables a caster applying a buff spell directly to a target's sheet in real time. Adds authentication, conflict resolution, and offline handling.

Anything else?
