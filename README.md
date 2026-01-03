# Fetch (Post-BM Manual)

WeakAura for MM Hunter Fetch: Eagle (Spell ID 1232995). Fixes the broken `/cast Fetch` macro after learning BM manual.

## Problem

Three spells named "Fetch" exist. WoW macros use names, not IDs. `/cast Fetch` becomes ambiguous.

| Spell ID | Name | Source |
|----------|------|--------|
| 125050 | Fetch | BM Pet |
| 125048 | Fetch | Trigger |
| 1232995 | Fetch: Eagle | MM Spotting Eagle |

## Solution

SecureActionButton casts by Spell ID, bypassing name conflict.

## Install

1. Import `fetch_eagle.txt` into WeakAuras
2. Create macro:
   ```
   #showtooltip
   /click WA_FetchEagle_Btn LeftButton 1
   ```
3. Bind to key

## Requirements

- WeakAuras 5.17+
- MM Hunter with Fetch: Eagle learned (Trueshot Lodge manual)

## Files

- `fetch_eagle.json` - Source
- `fetch_eagle.txt` - Import string
