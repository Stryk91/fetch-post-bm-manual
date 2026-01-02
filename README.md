# Fetch (Post-BM Manual)

WeakAura + Secure Button for Marksmanship Hunter's **Fetch: Eagle** (Spell ID 1232995).

## The Problem

After learning "Fetch" from the Beast Mastery manual at Trueshot Lodge in Highmountain, the normal `/cast Fetch` macro stops working for Marksmanship Hunters. This is because there are multiple "Fetch" spells:

| Spell ID | Name | Notes |
|----------|------|-------|
| 125050 | Fetch | Pet ability (BM) |
| 125048 | Fetch | Trigger spell |
| 1232995 | Fetch: Eagle | MM Spotting Eagle version |

WoW's macro system only accepts spell **names**, not IDs - so `/cast Fetch` becomes ambiguous.

## The Solution

This WeakAura creates a SecureActionButton that casts by **Spell ID** (1232995), bypassing the name conflict.

## Features

- Shows icon when:
  - You have a soft target or mouseover that's dead
  - Target is lootable
  - Fetch: Eagle is off cooldown
- Clickable WA icon
- Macro-compatible secure button
- Supports `@mouseover` targeting

## Installation

1. Import `fetch_eagle.txt` into WeakAuras
2. Create this macro:

```
#showtooltip
/click WA_FetchEagle_Btn LeftButton 1
```

3. Bind the macro to a key

## Files

- `fetch_eagle.json` - Source JSON (for editing)
- `fetch_eagle.txt` - WA import string

## Technical Details

- Uses TWW API: `C_Spell.GetSpellCooldown()`, `C_Spell.IsSpellUsable()`, `C_Spell.GetSpellTexture()`
- Standalone SecureActionButton parented to UIParent (always available for `/click`)
- Region overlay button for clicking the WA icon directly
- Unit attribute set to "mouseover" for flexible targeting

## Requirements

- WeakAuras 5.17+
- Hunter class, Marksmanship spec
- Fetch: Eagle spell learned (Trueshot Lodge manual)

## Credits

Built with [wa-encoder-rs](https://github.com/stryk/wa-encoder-rs) - Native Rust WeakAura encoder/decoder.
